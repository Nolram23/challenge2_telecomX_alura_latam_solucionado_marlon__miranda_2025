#  Predicción de Cancelación de Clientes (Churn) TelecomX parte 2

##  Descripción
Este proyecto busca **predecir qué clientes tienen mayor probabilidad de cancelar sus servicios** mediante modelos de Machine Learning.  
El objetivo principal es ofrecer **herramientas de análisis y predicción** que permitan a la empresa diseñar **estrategias de retención** efectivas.

---

##  Contenido del repositorio
- `datos_tratados.json` → Dataset preprocesado.  
- `EDA.ipynb` → Análisis exploratorio de datos (visualizaciones, correlaciones, distribución de variables).  
- `Modelado.ipynb` → Entrenamiento y evaluación de modelos.  
- `REPORT.md` → Informe detallado de resultados y factores de churn.  
- `README.md` → Descripción del proyecto.

---

##  Análisis de datos
- **EDA** mostró que variables como `tenure` (antigüedad), `Contract`, `MonthlyCharges`, `TotalCharges` y servicios de soporte (ej. `OnlineSecurity`, `TechSupport`) están fuertemente relacionadas con el churn.
- Los clientes con **contratos mes a mes**, **cargos mensuales altos** y **baja antigüedad** tienen mayor probabilidad de cancelar.

---

##  Modelos utilizados
1. **RandomForestClassifier (optimizado con GridSearch y class_weight)**  
   - ROC-AUC: **0.845**  
   - Recall Churn: **74.7%**  
   - Mejor modelo para identificar clientes en riesgo.  

2. **KNN (con SMOTE, escalado y optimización de hiperparámetros)**  
   - ROC-AUC: **0.778**  
   - Recall Churn: **57.0%**  
   - Útil como contraste, pero con menor desempeño (underfitting).  

---

##  Factores más influyentes en el churn
- **Contrato mes a mes** → aumenta el churn.  
- **Ausencia de servicios de soporte/seguridad** (ej. `OnlineSecurity_no`, `TechSupport_no`).  
- **Internet tipo fibra óptica** → clientes más exigentes y sensibles al servicio.  
- **Método de pago `electronic check`** → asociado con mayor churn.  
- **Antigüedad (`tenure`)** → factor protector (clientes antiguos permanecen más).  
- **Cargos mensuales altos (`MonthlyCharges`)** → aumentan la probabilidad de cancelación.  

---

##  Estrategias de retención propuestas
- Incentivar **contratos de largo plazo** con descuentos o beneficios.  
- Ofrecer bundles de **seguridad y soporte técnico** a clientes en riesgo.  
- Promover la migración a **pagos automáticos** (tarjeta/crédito).  
- **Ajustes temporales de precio** para clientes nuevos con cargos altos.  
- **Programas de fidelidad** por antigüedad.  
- Intervención temprana (0–3 meses) con campañas de onboarding y atención proactiva.  

---

##  Próximos pasos
- Explorar **modelos de boosting** (XGBoost, LightGBM).  
- Ajustar el **umbral de decisión** para priorizar recall en churn.  
- Incorporar nuevas variables (historial de incidencias, variabilidad de consumo).  
- Desplegar un **dashboard interactivo** para visualizar probabilidades de churn por cliente.  

---

##  Autor
Proyecto desarrollado por **Marlon Jhesid Miranda Contreras**  
📍 Data Science & Machine Learning  -  Grupo G8 de alura latam y programa ONE by ORACLE.
