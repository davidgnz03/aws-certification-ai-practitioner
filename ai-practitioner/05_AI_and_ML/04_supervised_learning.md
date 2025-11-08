# ML Algorithms — Supervised Learning

## Introducción

**Supervised Learning (Aprendizaje Supervisado)** es una técnica de Machine Learning donde el modelo **aprende una función de mapeo** entre **entradas conocidas** y **salidas conocidas (etiquetadas)**.  
El objetivo es que el modelo pueda **predecir el resultado correcto para nuevos datos no vistos**.

> ⚙️ En palabras simples: “Le mostramos ejemplos al modelo y le decimos cuál es la respuesta correcta, para que aprenda a generalizar.”

---

## Características Principales

- Requiere **datos etiquetados (labeled data)**.  
- Muy **potente** para predicción y clasificación.  
- Puede ser **computacionalmente costoso** cuando hay millones de datos.  
- Es la técnica más común en aplicaciones de negocio.

---

## Tipos de Problemas en Supervised Learning

### 🔢 **Regression (Regresión)**

**Objetivo:** predecir un valor numérico continuo.  
El modelo aprende relaciones cuantitativas entre las variables de entrada y la variable de salida.

#### Características:
- La **salida (output)** es continua, puede tomar cualquier valor dentro de un rango.  
- Se utiliza cuando el resultado es **una cantidad o medida**.

#### Ejemplos:
- Predicción del precio de una casa 🏠  
- Predicción de precios de acciones 📈  
- Pronóstico del clima 🌦️  

#### Casos de uso:
- Finanzas (estimación de ingresos o costos).  
- Bienes raíces (predicción de precios).  
- IoT (predicción de consumo energético).  

---

### 🧩 **Classification (Clasificación)**

**Objetivo:** predecir una **categoría o clase discreta**.  
El modelo aprende a **asignar etiquetas** basándose en los patrones del dataset.

#### Características:
- La **salida (output)** es discreta (por ejemplo, “sí/no”, “spam/no spam”, “gato/perro”).  
- Se usa cuando hay **decisiones categóricas** o etiquetas predefinidas.

#### Tipos de clasificación:
- **Binary Classification:** dos clases posibles (Ej. fraude o no fraude).  
- **Multiclass Classification:** múltiples clases (Ej. tipos de flores, niveles de riesgo).  
- **Multi-label Classification:** una muestra puede pertenecer a varias clases (Ej. una película puede ser “acción” y “comedia”).  

#### Ejemplos:
- Detección de fraude 💳  
- Clasificación de imágenes 📸  
- Retención de clientes 🧠  
- Diagnóstico médico 🩺  

#### Algoritmo clave:
- **K-Nearest Neighbors (K-NN):**
  - Clasifica basándose en la **similitud** con sus vecinos más cercanos.  
  - No requiere entrenamiento complejo.  
  - Sencillo y efectivo para datasets pequeños o medianos.

---

## Dataset Splitting — Entrenamiento, Validación y Prueba

El proceso de entrenamiento se divide en **tres subconjuntos principales** para evitar sobreajuste (overfitting) y evaluar correctamente el modelo.

| Conjunto | Propósito | Porcentaje típico |
|-----------|------------|------------------|
| **Training Set** | Entrenar el modelo, ajustar pesos y parámetros. | 60–80% |
| **Validation Set** | Ajustar hiperparámetros y validar desempeño durante el entrenamiento. | 10–20% |
| **Test Set** | Evaluar el desempeño final del modelo con datos nunca vistos. | 10–20% |

### Ejemplo visual:
```
Dataset Total → 100%
├── Training Set (70%)
├── Validation Set (15%)
└── Test Set (15%)
```


> 💡 *El conjunto de prueba siempre debe permanecer sin tocar hasta la evaluación final.*

---

## 🧠 Feature Engineering (Ingeniería de Características)

La **ingeniería de características** es el proceso de **transformar datos crudos en variables útiles (features)** que mejoren el rendimiento del modelo.  
Es una etapa **crítica** especialmente en **aprendizaje supervisado**, donde la calidad de las características determina el éxito del modelo.

### Objetivos:
- Seleccionar los atributos más **relevantes**.  
- Crear nuevas variables que **resuman información importante**.  
- Transformar datos para que sean **comprensibles y útiles** para el modelo.

---

### 🔍 Técnicas de Feature Engineering

| Técnica | Descripción |
|----------|--------------|
| **Feature Extraction** | Derivar nuevas características a partir de datos existentes. Ej: extraer “año” de una fecha. |
| **Feature Selection** | Elegir solo las variables que más aportan al modelo. Ej: eliminar columnas redundantes. |
| **Feature Transformation** | Escalar o normalizar datos para mejorar el rendimiento. Ej: `StandardScaler` o `MinMaxScaler`. |

---

## Feature Engineering en Datos Estructurados

Los **datos estructurados** (como los tabulares) requieren una selección y transformación de características numéricas o categóricas.

### Ejemplo:
Predicción del precio de una casa 🏡  
**Features:** tamaño, ubicación, número de habitaciones, edad del inmueble.

### Tareas comunes:
1. **Feature Creation:** crear nuevas variables derivadas (por ejemplo, precio por m²).  
2. **Feature Selection:** eliminar atributos con poca relevancia.  
3. **Feature Transformation:** normalizar valores para que todas las columnas tengan un rango similar.  

> 📊 Este proceso mejora la estabilidad y precisión del modelo, especialmente en regresión.

---

## Feature Engineering en Datos No Estructurados

Los **datos no estructurados** (texto, imágenes, audio, video) requieren transformaciones específicas para convertirlos en representaciones numéricas.

### 📜 Text Data
- Se utiliza **NLP (Natural Language Processing)** para procesar texto.  
- Técnicas comunes:
  - **Tokenización:** dividir el texto en palabras o subpalabras.  
  - **Stopword removal:** eliminar palabras irrelevantes (“de”, “y”, “el”).  
  - **TF-IDF:** medir la importancia de una palabra dentro de un corpus.  
  - **Embeddings:** representar palabras o frases como vectores numéricos (Word2Vec, BERT).  

**Ejemplo:** análisis de sentimiento de reseñas de clientes.

---

### 🖼️ Image Data
- Se utilizan técnicas de **Computer Vision** y **Deep Learning**.  
- Cada imagen se convierte en una **matriz de píxeles** (valores numéricos).  
- Técnicas comunes:
  - **Normalización de píxeles.**  
  - **Extracción de características visuales** (bordes, texturas, color).  
  - **Uso de modelos preentrenados (ResNet, VGG, MobileNet)** para *feature extraction*.  

**Ejemplo:** Clasificación de imágenes o reconocimiento facial.

---

## Resumen General

| Concepto | Descripción | Ejemplo |
|-----------|--------------|---------|
| **Supervised Learning** | Aprende de datos etiquetados para predecir resultados. | Predicción de precios, clasificación de spam |
| **Regression** | Predice valores numéricos continuos. | Precio de casas, clima |
| **Classification** | Predice categorías discretas. | Fraude/no fraude, diagnóstico médico |
| **Training Set** | Entrena el modelo. | 60–80% del dataset |
| **Validation Set** | Ajusta hiperparámetros. | 10–20% |
| **Test Set** | Evalúa desempeño final. | 10–20% |
| **Feature Engineering** | Crea y transforma características relevantes. | Nuevas columnas, normalización, embeddings |

---

## Conclusión

El **aprendizaje supervisado** es la base de la mayoría de las aplicaciones prácticas de Machine Learning.  
Su éxito depende de tres pilares:

1. **Datos de calidad** (bien etiquetados).  
2. **División adecuada** entre entrenamiento, validación y prueba.  
3. **Feature Engineering efectivo**, que transforme los datos en información útil.

> 🧩 “Un buen modelo no solo aprende de los datos; aprende de las **características adecuadas** de los datos.”
