# Machine Learning — Términos Clave para el Examen AWS AI Practitioner

En el examen de **AWS Certified AI Practitioner**, es común encontrar siglas y nombres de **modelos o algoritmos de Machine Learning**.  
A continuación, se presenta una descripción clara y resumida de los principales términos que debes conocer.

---

## 🧠 **GPT — Generative Pre-trained Transformer**

- **Tipo:** Modelo fundacional / Generative AI / Transformer  
- **Función:** Generar texto o código a partir de un *prompt* (entrada).  
- **Características:**
  - Pre-entrenado en grandes volúmenes de texto (internet, libros, artículos).  
  - Utiliza la arquitectura **Transformer**.  
  - Capaz de generar **texto coherente, traducciones, resúmenes y respuestas contextuales**.  
- **Ejemplos:** ChatGPT, Amazon Titan Text G1, Claude, Gemini, etc.  

---

## 🔁 **BERT — Bidirectional Encoder Representations from Transformers**

- **Tipo:** Modelo Transformer (enfocado en *encoding*)  
- **Función:** Entender el significado de una frase leyendo el texto en **dos direcciones (bidireccional)**.  
- **Características:**
  - Diseñado para **comprensión del lenguaje (NLP)**, no generación.  
  - Ideal para tareas como **clasificación de texto**, **búsqueda semántica**, o **análisis de sentimiento**.  
- **Ejemplo:** Google BERT (y derivados como RoBERTa o DistilBERT).  

> 💡 *GPT = genera texto | BERT = comprende texto*

---

## 🔄 **RNN — Recurrent Neural Network**

- **Tipo:** Red Neuronal  
- **Función:** Procesar **datos secuenciales** (uno tras otro), donde el orden importa.  
- **Aplicaciones comunes:**
  - **Reconocimiento de voz**
  - **Predicción de series temporales (time-series)**
  - **Procesamiento de texto**
- **Características:**
  - Mantiene un “estado” que guarda información del paso anterior (memoria temporal).  
  - Variantes modernas incluyen **LSTM (Long Short-Term Memory)** y **GRU (Gated Recurrent Unit)**.  

---

## 🧩 **ResNet — Residual Network**

- **Tipo:** Deep Convolutional Neural Network (CNN)  
- **Función:** Reconocimiento y clasificación de imágenes.  
- **Características:**
  - Usa **conexiones residuales (skip connections)** para evitar la pérdida de información en redes muy profundas.  
  - Facilita el entrenamiento de **redes con cientos o miles de capas**.  
- **Aplicaciones:**
  - **Reconocimiento facial**
  - **Detección de objetos**
  - **Clasificación de imágenes**  
- **Ejemplo:** ResNet-50, ResNet-101 (común en visión por computadora).

---

## ⚖️ **SVM — Support Vector Machine**

- **Tipo:** Algoritmo clásico de ML (no neuronal)  
- **Función:** Clasificación y regresión.  
- **Características:**
  - Encuentra el **hiperplano óptimo** que separa las clases en un espacio de alta dimensión.  
  - Muy útil cuando el número de muestras es pequeño pero las dimensiones son altas.  
- **Aplicaciones:**
  - Clasificación de texto o imágenes.  
  - Detección de anomalías.  
  - Reconocimiento de patrones.  

---

## 🌊 **WaveNet**

- **Tipo:** Modelo Generativo (basado en redes convolucionales 1D)  
- **Función:** Generar **formas de onda de audio crudo** (raw audio waveform).  
- **Desarrollado por:** DeepMind (subsidiaria de Google).  
- **Aplicaciones:**
  - **Síntesis de voz natural (Text-to-Speech)** — base de *Google Assistant* y *Google Cloud TTS*.  
  - Modelos de audio realista a partir de texto.  
- **Ventaja:** Produce voces más naturales y realistas que los modelos tradicionales concatenativos.

---

## 🎭 **GAN — Generative Adversarial Network**

- **Tipo:** Modelo Generativo (red neuronal dual)  
- **Función:** Generar datos sintéticos (imágenes, audio o video) que se asemejan a los reales.  
- **Arquitectura:**
  - **Generador:** crea datos falsos (imágenes, sonidos, etc.).  
  - **Discriminador:** evalúa si los datos son reales o generados.  
  - Ambos compiten, mejorando mutuamente su desempeño.  
- **Aplicaciones:**
  - **Aumento de datos (data augmentation)**.  
  - **Generación de imágenes realistas (Deepfakes, arte AI, etc.)**.  
  - **Restauración de imágenes y superresolución.**  

> 🧩 GAN = “dos redes que se enfrentan para mejorar continuamente”.

---

## ⚡ **XGBoost — Extreme Gradient Boosting**

- **Tipo:** Algoritmo clásico de *ensemble learning*  
- **Función:** Clasificación, regresión y ranking.  
- **Características:**
  - Basado en la técnica de **Gradient Boosting**, que combina múltiples árboles de decisión.  
  - Mejora el rendimiento reduciendo el sesgo y el error.  
  - Muy eficiente y rápido, con soporte para paralelización y GPU.  
- **Aplicaciones:**
  - Competencias de *Machine Learning (Kaggle)*.  
  - Modelos tabulares y numéricos.  
  - Predicción de fraude, churn, o precios.

---

## 📘 Resumen General

| Acrónimo | Nombre Completo | Tipo / Enfoque | Uso Principal |
|-----------|------------------|----------------|----------------|
| **GPT** | Generative Pre-trained Transformer | Transformer / Gen-AI | Generación de texto o código |
| **BERT** | Bidirectional Encoder Representations from Transformers | Transformer | Comprensión de texto |
| **RNN** | Recurrent Neural Network | Secuencial | Texto, audio, series temporales |
| **ResNet** | Residual Network | CNN (visión) | Reconocimiento de imágenes |
| **SVM** | Support Vector Machine | Algoritmo clásico | Clasificación y regresión |
| **WaveNet** | Waveform Generative Model | Deep Audio Model | Síntesis de voz |
| **GAN** | Generative Adversarial Network | Generativo | Generación de datos sintéticos |
| **XGBoost** | Extreme Gradient Boosting | Ensemble / Árboles | Tabular, predicción, ranking |

---

## 🏁 Conclusión

Estos términos representan **las arquitecturas y algoritmos más comunes** que pueden aparecer en el examen de **AWS Certified AI Practitioner**.  
Conocer **qué tipo de datos procesan**, **qué problema resuelven** y **en qué categoría encajan** te permitirá identificar rápidamente la respuesta correcta en preguntas de opción múltiple.
