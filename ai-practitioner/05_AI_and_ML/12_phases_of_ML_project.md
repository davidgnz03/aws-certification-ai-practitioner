# Phases of a Machine Learning Project

El desarrollo de un proyecto de **Machine Learning (ML)** sigue un ciclo estructurado que abarca desde la definición del problema de negocio hasta la implementación y mejora continua del modelo.  
Cada fase es crucial para asegurar que los resultados del modelo estén alineados con los objetivos del negocio y sean técnicamente sólidos.

---

## 🧭 1. Business Problem Definition

El primer paso consiste en **definir claramente el problema de negocio** que se desea resolver mediante ML.

### Objetivos:
- Comprender las metas de negocio, restricciones y expectativas.  
- Establecer **KPI (Key Performance Indicators)** que medirán el éxito.  
- Determinar **presupuesto, valor esperado y prioridades**.  
- Identificar los **stakeholders** involucrados: líderes de negocio, data scientists, ingenieros de datos, etc.

> 🎯 *Ejemplo: Reducir el churn de clientes en un 10% en los próximos seis meses.*

---

## 🧩 2. ML Problem Framing

Transformar el problema de negocio en un **problema técnico de Machine Learning**.

### Actividades:
- Evaluar si **ML es la solución adecuada** (vs reglas fijas o heurísticas).  
- Determinar el tipo de problema:
  - Clasificación, regresión, clustering, etc.  
- Definir la variable objetivo (*target variable*) y las características relevantes (*features*).  
- Colaboración entre **Data Scientists, ML Architects, Data Engineers** y **Subject Matter Experts (SMEs)** para alinear expectativas.

> 💡 *Ejemplo: Si el negocio quiere “predecir la pérdida de clientes”, el problema técnico es una clasificación binaria: “se queda / se va”.*

---

## 🧱 3. Data Collection and Preparation

Los datos son el combustible del Machine Learning.  
En esta fase se **recopila, limpia y prepara** la información necesaria.

### Actividades:
- **Data Collection:** recopilar datos de diversas fuentes (bases de datos, APIs, sensores, logs, etc.).  
- **Data Integration:** unificar los datos en un repositorio accesible (por ejemplo, data lake o data warehouse).  
- **Data Preprocessing:** limpieza, manejo de valores nulos, normalización, eliminación de duplicados.  
- **Data Visualization:** explorar los datos con gráficos para detectar patrones, sesgos o inconsistencias.  

---

### 🔍 Exploratory Data Analysis (EDA)

El análisis exploratorio de datos ayuda a comprender la estructura, calidad y relaciones entre variables.

#### Técnicas comunes:
- **Histogramas** → distribución de variables numéricas.  
- **Boxplots** → detección de valores atípicos.  
- **Correlation Matrix (Matriz de Correlación):**
  - Mide la relación entre variables (cuán “ligadas” están).
  - Ayuda a identificar las características más relevantes para el modelo.

> 🧠 *Ejemplo: si dos variables están fuertemente correlacionadas, puede eliminarse una para evitar redundancia.*

---

## ⚙️ 4. Feature Engineering

La **ingeniería de características** consiste en crear, transformar o seleccionar variables para mejorar el desempeño del modelo.

### Tipos:
- **Feature Creation:** derivar nuevas variables útiles.  
- **Feature Transformation:** escalar, normalizar o codificar datos.  
- **Feature Selection:** identificar las variables más relevantes.

**Ejemplo:**  
Convertir la fecha de una transacción en variables como “día de la semana”, “hora” o “mes”.

> 🧩 Una buena ingeniería de características puede mejorar la precisión del modelo más que cambiar el algoritmo.

---

## 🧠 5. Model Development

Una vez listos los datos, comienza la fase de **entrenamiento y optimización del modelo**.

### Actividades:
- Seleccionar el algoritmo de ML apropiado (regresión, árbol de decisión, red neuronal, etc.).  
- Entrenar el modelo con el conjunto de entrenamiento.  
- Ajustar **hiperparámetros** para optimizar el rendimiento.  
- Evaluar los resultados con el conjunto de validación.  

### Iterative Process:
El desarrollo es iterativo:
- Si el modelo no cumple los objetivos → volver a la fase de **Feature Engineering** o **Data Augmentation**.  
- Si el modelo cumple los KPI definidos → continuar hacia la fase de prueba y despliegue.

> 🔁 *“Entrenar, evaluar, ajustar, repetir” hasta que se cumplan los objetivos del negocio.*

---

## 📊 6. Model Evaluation

Medir el desempeño del modelo con métricas apropiadas según el tipo de problema:

| Tipo de Modelo | Métricas Comunes |
|----------------|------------------|
| Clasificación | Accuracy, Precision, Recall, F1, AUC-ROC |
| Regresión | MAE, RMSE, R² |
| Clustering | Silhouette Score, Inertia |
| NLP | BLEU, ROUGE, Perplexity |

### Pregunta Clave:
> ❓ “¿El modelo cumple los objetivos de negocio?”

Si **no**, regresar a fases previas:  
- Mejorar datos → *Data Augmentation*  
- Crear nuevas variables → *Feature Engineering*

Si **sí**, pasar a despliegue.

---

## 🚀 7. Model Testing and Deployment

### Objetivo:
Poner el modelo en producción para realizar inferencias sobre datos reales.

### Consideraciones:
- Validar con datos de prueba (Test Set).  
- Escoger tipo de despliegue:
  - **Real-time** (API, baja latencia)  
  - **Batch** (procesamiento por lotes)  
  - **Serverless**, **On-premises**, **Edge**, etc.  
- Configurar pipelines de inferencia y monitorización.

> ☁️ En AWS, modelos pueden desplegarse usando servicios como **SageMaker**, **Lambda**, **ECS**, o **Bedrock**.

---

## 🔎 8. Monitoring and Debugging

Una vez en producción, es esencial monitorear el rendimiento del modelo.

### Actividades:
- Comparar predicciones con resultados reales (drift detection).  
- Identificar degradaciones de precisión o latencia.  
- Detectar sesgos o comportamientos inesperados.  
- Registrar logs de inferencia y métricas de uso.

**Métricas Clave:**
- Latencia de inferencia.  
- Tasa de error.  
- Desviación del rendimiento esperado.

> 🧠 *El monitoreo continuo garantiza que el modelo mantenga su efectividad a lo largo del tiempo.*

---

## 🔁 9. Iteration and Retraining

El ciclo de vida del ML es **continuo e iterativo**.  
Los modelos deben **adaptarse a nuevos datos** y **cambiar con el entorno**.

### Actividades:
- Incorporar **nuevos datos** (Data Refresh).  
- Ajustar hiperparámetros.  
- Reentrenar modelos periódicamente.  
- Versionar modelos y datasets.  

> 📈 *La mejora continua mantiene la precisión, relevancia y confiabilidad del sistema.*

---

## 🧭 Resumen Visual del Ciclo de un Proyecto ML

```plaintext
Business Problem
   ↓
ML Problem Framing
   ↓
Data Collection and Preparation
   ↓
Feature Engineering
   ↓
Model Training & Evaluation
   ↓
Are business goals met?
   ├── No → Feature Augmentation / Data Augmentation → Retrain
   └── Yes → Model Testing & Deployment → Monitoring & Debugging → Add new data & Retrain
```

---

## 🧠 Conclusión

Un proyecto de Machine Learning exitoso **no termina con el entrenamiento del modelo**.  
Debe existir un proceso completo que garantice su **alineación con los objetivos del negocio**, su **rendimiento técnico**, y su **evolución constante** conforme cambia la realidad de los datos.

> 🚀 Machine Learning no es un evento, es un ciclo continuo de aprendizaje y mejora.