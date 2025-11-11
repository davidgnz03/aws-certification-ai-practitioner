# Amazon Comprehend

**Amazon Comprehend** es un servicio totalmente administrado y **serverless** de **AWS** para realizar **Natural Language Processing (NLP)** — procesamiento de lenguaje natural.  
Utiliza **Machine Learning (ML)** para descubrir **insights, relaciones y patrones** dentro de texto sin necesidad de entrenamiento manual ni infraestructura dedicada.

---

## 🧠 Características Generales

- **Totalmente administrado y sin servidor (serverless)** — no necesitas preocuparte por servidores ni escalabilidad.  
- Utiliza **modelos de aprendizaje automático** para analizar y comprender texto.  
- Puede procesar texto en diferentes idiomas.  
- Detecta el **idioma** automáticamente.  
- **Extrae entidades clave** como frases importantes, lugares, personas, marcas o eventos.  
- Evalúa la **polaridad del texto (positiva, negativa, neutral o mixta)** mediante análisis de sentimiento.  
- Realiza **tokenización** (división en palabras y frases) y **análisis gramatical (part-of-speech tagging)**.  
- Clasifica automáticamente grandes volúmenes de documentos en **temas** mediante modelado de tópicos.

---

## 💡 Casos de Uso Comunes

- **Análisis de interacciones con clientes:**  
  Procesar correos electrónicos o reseñas para identificar las causas de experiencias positivas o negativas.  

- **Agrupación automática de documentos o artículos:**  
  Clasificar contenido (noticias, blogs, documentos corporativos) por temas detectados automáticamente.

> 🧩 *Ideal para análisis de texto, minería de información y automatización de tareas de clasificación documental.*

---

## 🧾 Custom Classification (Clasificación Personalizada)

Permite **organizar documentos** en categorías (clases) **definidas por el usuario**.

### Ejemplo:
Clasificar correos electrónicos de clientes según el tipo de solicitud, para dirigirlos al equipo o flujo de trabajo correcto.

### Características:
- Soporta múltiples formatos: **texto, PDF, Word e imágenes** (mediante integración con Textract).  
- **Real-Time Analysis:** análisis sincrónico de un solo documento.  
- **Async Analysis:** análisis asíncrono por lotes de múltiples documentos.  

> 🧠 *Tú defines las categorías, Comprehend aprende a reconocerlas.*

---

## 🧍‍♂️ Named Entity Recognition (NER)

**NER (Reconocimiento de Entidades Nombradas)** permite extraer **entidades predefinidas y de propósito general** desde texto, como:

- Personas  
- Organizaciones  
- Lugares  
- Fechas  
- Cantidades, eventos, etc.

> 🔍 *Ejemplo:* De la frase  
> “Jeff Bezos founded Amazon in 1994 in Seattle.”  
> Comprehend extrae:
> - Persona: *Jeff Bezos*  
> - Organización: *Amazon*  
> - Fecha: *1994*  
> - Lugar: *Seattle*

---

## 🧩 Custom Entity Recognition (Reconocimiento de Entidades Personalizadas)

**Custom Entity Recognition (CER)** permite extraer entidades **específicas de tu negocio** que los modelos preentrenados no reconocen por defecto.

### Qué puede hacer:
- Identificar términos, frases y sustantivos relevantes para tu organización.  
- Extraer información como **números de póliza**, **códigos internos**, **nombres de productos**, o **indicadores de escalamiento de clientes**.  

### Cómo funciona:
1. Entrenas el modelo con tus propios datos (listas de entidades y documentos de ejemplo).  
2. Amazon Comprehend aprende a identificar esas entidades dentro de texto nuevo.  
3. Puedes usarlo en modo **sincrónico (real-time)** o **asíncrono (batch)**.

> 🧠 *Transforma texto libre en información estructurada relevante para tu negocio.*

---

## ⚙️ Funcionalidades en la Consola AWS

Desde la consola de **Amazon Comprehend**, puedes acceder y ejecutar los siguientes módulos:

| Funcionalidad | Descripción |
|----------------|-------------|
| **Detect Dominant Language** | Identifica el idioma principal del texto. |
| **Detect Sentiment** | Analiza el sentimiento general (positivo, negativo, neutral o mixto). |
| **Detect Entities** | Extrae entidades como personas, lugares y organizaciones. |
| **Detect Key Phrases** | Identifica las frases o palabras más relevantes del texto. |
| **Detect Syntax** | Analiza la estructura gramatical y el tipo de palabras (sustantivos, verbos, adjetivos, etc.). |
| **Topics Modeling** | Agrupa colecciones de texto en temas principales. |
| **Custom Classification** | Entrena modelos personalizados de clasificación. |
| **Custom Entity Recognition** | Entrena modelos para detectar entidades específicas del negocio. |

---

## 🧠 En Resumen

**Amazon Comprehend**:
- Es **serverless**, **preentrenado** y **fácil de integrar**.  
- Permite **entender, clasificar y extraer información** de texto de forma automática.  
- Escala según demanda y puede combinarse con otros servicios de AWS (Textract, Bedrock, Lambda, S3, etc.).  

> 🚀 *Una herramienta poderosa para transformar texto en conocimiento estructurado, lista para producción sin necesidad de construir modelos desde cero.*
