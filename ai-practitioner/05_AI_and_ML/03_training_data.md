# Training Data — Fundamentos del Aprendizaje Automático

## Introducción

El **entrenamiento de un modelo de Machine Learning (ML)** depende en gran medida de la **calidad y estructura de los datos** utilizados.  
Una de las reglas más importantes es:

> **Garbage In → Garbage Out**  
> Si los datos de entrenamiento son de baja calidad, el modelo producirá resultados igualmente deficientes.

Por tanto, la **preparación y curación del dataset** es la etapa más crítica para construir un modelo robusto, confiable y generalizable.

---

## Importancia del Training Data

El dataset define:
- Qué **tipo de algoritmos** pueden usarse.  
- Qué tan **efectivo** será el aprendizaje.  
- Qué tan **preciso y confiable** será el modelo.  

Un buen conjunto de entrenamiento debe ser:
- **Relevante** (alineado al problema real).  
- **Suficiente** (cantidad adecuada).  
- **Balanceado** (sin sesgos excesivos).  
- **Limpio** (sin errores o datos faltantes).  

---

## Tipos de Datos: Labeled vs Unlabeled

### 🏷️ **Labeled Data (Datos Etiquetados)**

- Los datos incluyen **características de entrada (features)** y **salidas esperadas (labels)**.  
- Permiten entrenar modelos para **aprender relaciones directas entre entrada y salida**.  
- Son esenciales para **Supervised Learning (aprendizaje supervisado)**.

**Ejemplo:**
- Dataset con imágenes de animales, donde cada imagen tiene una etiqueta con el tipo de animal (“gato”, “perro”, “caballo”).  

**Casos de uso comunes:**
- Clasificación de imágenes  
- Detección de fraude  
- Reconocimiento de voz  
- Análisis de sentimiento  

---

### 🔍 **Unlabeled Data (Datos No Etiquetados)**

- Solo contienen **características de entrada**, sin etiquetas asociadas.  
- Se utilizan para descubrir **patrones ocultos, estructuras o agrupamientos** dentro de los datos.  
- Se aplican en **Unsupervised Learning (aprendizaje no supervisado)**.

**Ejemplo:**
- Conjunto de imágenes sin etiquetas, donde el modelo intenta agrupar las similares.  

**Casos de uso comunes:**
- Agrupamiento de clientes (clustering)  
- Reducción de dimensionalidad  
- Detección de anomalías  
- Análisis exploratorio  

---

## Tipos de Datos: Structured vs Unstructured

### 📊 **Structured Data (Datos Estructurados)**

Datos organizados de forma tabular o en formatos bien definidos (filas y columnas).

#### ▪️ Tabular Data
- Los registros se representan por **filas**, y cada columna representa un **atributo o característica**.  
- Es el formato más común en bases de datos relacionales.

**Ejemplo:**
| Customer_ID | Name | Age | Total_Purchase |
|--------------|------|-----|----------------|
| 1001 | Ana | 32 | 2500 |
| 1002 | Luis | 45 | 7800 |

**Casos de uso:**
- Modelos de predicción de ventas.  
- Segmentación de clientes.  
- Modelos de churn o scoring crediticio.  

#### ▪️ Time Series Data
- Registros de datos recopilados en **intervalos de tiempo sucesivos**.  
- El orden temporal es importante, y los valores pueden depender de observaciones pasadas.

**Ejemplo:**
- Precios de acciones diarios.  
- Temperaturas horarias.  
- Demanda energética semanal.  

**Casos de uso:**
- Predicción de series temporales.  
- Forecast de demanda.  
- Detección de anomalías en tendencias.  

---

### 🖼️ **Unstructured Data (Datos No Estructurados)**

Datos que **no siguen un formato fijo o tabular**, y que pueden provenir de texto libre, imágenes, audio o video.  
Representan la **mayoría de los datos generados en el mundo actual** (más del 80%).

#### ▪️ Text Data
- Texto libre como artículos, publicaciones en redes sociales o reseñas de clientes.  
- Requieren **procesamiento de lenguaje natural (NLP)** para ser interpretados.  

**Ejemplo:**  
Comentarios de productos en un e-commerce o tweets sobre una marca.

**Casos de uso:**
- Análisis de sentimiento.  
- Clasificación de texto.  
- Chatbots.  
- Resumen automático de documentos.  

#### ▪️ Image Data
- Información en forma de **imágenes digitales o videos**.  
- Utiliza técnicas de **Computer Vision** y **Deep Learning (CNNs, ResNet, Vision Transformers)**.

**Ejemplo:**  
Fotografías de animales, radiografías médicas o imágenes satelitales.

**Casos de uso:**
- Detección de objetos.  
- Reconocimiento facial.  
- Clasificación médica.  

---

## Aprendizaje Supervisado vs No Supervisado

### 🧭 **Supervised Learning**
- El modelo aprende a **mapear entradas conocidas a salidas conocidas**.  
- Utiliza **labeled data**.  
- El objetivo es **predecir resultados o clasificar ejemplos futuros**.  

**Ejemplos de algoritmos:**
- Linear Regression  
- Logistic Regression  
- Decision Trees / Random Forests  
- Neural Networks  

**Casos de uso:**
- Predicción de precios.  
- Detección de spam.  
- Diagnóstico médico automatizado.  

---

### 🧩 **Unsupervised Learning**
- El modelo **no tiene etiquetas de salida** y busca **patrones o relaciones ocultas** en los datos.  
- Utiliza **unlabeled data**.  
- El objetivo es **entender la estructura subyacente**.  

**Ejemplos de algoritmos:**
- K-Means Clustering  
- DBSCAN  
- Principal Component Analysis (PCA)  
- Autoencoders  

**Casos de uso:**
- Agrupamiento de clientes por comportamiento.  
- Reducción de dimensionalidad.  
- Recomendaciones basadas en similitud.  

---

## Resumen General

| Tipo | Datos Usados | Objetivo | Ejemplo de Algoritmo | Ejemplo de Aplicación |
|------|---------------|-----------|----------------------|------------------------|
| **Supervised Learning** | Labeled | Aprender mapeo entrada → salida | Logistic Regression, Random Forest | Clasificación de imágenes, predicción de precios |
| **Unsupervised Learning** | Unlabeled | Encontrar patrones o agrupamientos | K-Means, PCA, Autoencoder | Segmentación de clientes, detección de anomalías |
| **Structured Data** | Tabular, numérico, temporal | Organización clara y cuantificable | Árboles de decisión, XGBoost | Análisis financiero, ventas |
| **Unstructured Data** | Texto, imagen, audio, video | Datos sin formato fijo | CNN, LSTM, Transformers | NLP, visión por computadora |

---

## Conclusión

El **tipo y la calidad del dataset** determinan directamente la **eficacia del modelo de Machine Learning**.  
Elegir entre **datos etiquetados o no etiquetados**, y entender si son **estructurados o no estructurados**, es fundamental para definir la **estrategia de entrenamiento** y **selección de algoritmos**.

En resumen:  
> “**Un buen modelo empieza con buenos datos.**”
