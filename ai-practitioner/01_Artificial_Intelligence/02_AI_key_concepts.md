# 🧠 Conceptos Fundamentales de la Inteligencia Artificial Moderna

## 🚀 Introducción

La **AI moderna** se ha potenciado gracias al desarrollo de **modelos fundacionales (Foundation Models)**, **LLMs (Large Language Models)** y las técnicas de **Generative AI (Gen-AI)**.  
Estos avances permiten que las máquinas comprendan, generen y razonen sobre texto, imágenes, audio y más.

A continuación se explican los principales conceptos que todo ingeniero debe dominar en esta nueva era de la AI.

---

## 🏗️ Foundation Model

Un **Foundation Model** es un modelo de inteligencia artificial **entrenado a gran escala** con enormes volúmenes de datos y que puede **adaptarse a múltiples tareas** mediante técnicas como el *fine-tuning* o *prompt engineering*.

Estos modelos sirven como **base o cimiento** sobre el cual se construyen aplicaciones más específicas (por ejemplo: chatbots, análisis de documentos, generación de código, etc.).

🔹 **Ejemplos:**
- GPT (de OpenAI)
- Claude (Anthropic)
- Gemini (Google)
- Titan (AWS)
- LLaMA (Meta)

---

## 💬 LLM (Large Language Model)

Un **LLM** es un tipo de *Foundation Model* especializado en **lenguaje natural (NLP)**.  
Estos modelos aprenden patrones del lenguaje al procesar miles de millones de palabras y pueden **comprender, generar y razonar sobre texto**.

🔹 **Ejemplo de tareas:**
- Resumir documentos
- Traducir texto
- Contestar preguntas
- Generar código o contenido

🔹 **Ejemplo técnico:**  
Un modelo como GPT-4 o Claude 3 usa **transformers** (arquitectura basada en *attention*) para procesar texto y generar respuestas coherentes.

---

## 📚 RAG (Retrieval-Augmented Generation) / Knowledge Base

**RAG** significa *Retrieval-Augmented Generation*.  
Es una técnica que **combina modelos generativos con búsqueda de información** en bases de conocimiento externas (por ejemplo, documentos, bases de datos, APIs o vectores).

El proceso se compone de dos partes:
1. **Retrieval (Recuperación):** Busca información relevante en una *Knowledge Base* (base de conocimiento vectorizada).  
2. **Generation (Generación):** Usa esa información como contexto para generar una respuesta más precisa y actualizada.

🔹 **Ventajas:**
- Mejora la precisión (usa datos reales).  
- Evita alucinaciones del modelo.  
- Permite actualizaciones dinámicas sin volver a entrenar el modelo.

🔹 **Ejemplo:**  
ChatGPT con acceso a documentos de empresa o conocimiento interno usando *embeddings + vector database*.

---

## 🧬 Gen-AI (Generative AI)

La **Generative AI** es una rama de la AI que permite **crear contenido nuevo** (texto, imágenes, música, código, etc.) a partir de datos aprendidos por un modelo.

Los modelos generativos **no solo analizan**, sino que **producen resultados originales** basados en patrones previos.

🔹 **Ejemplos:**
- ChatGPT (texto)
- DALL·E o Midjourney (imágenes)
- Codex / GitHub Copilot (código)
- MusicLM (audio)

---

## 💡 Prompt

Un **Prompt** es la **instrucción o entrada textual** que proporcionamos a un modelo generativo para obtener una respuesta.  
Es el “lenguaje de comunicación” entre el humano y la AI.

Existen diferentes tipos de *prompts*:

| Tipo | Descripción | Ejemplo |
|------|--------------|---------|
| **Instruction Prompt** | Indica una acción concreta. | “Resume este texto en tres puntos clave.” |
| **Context Prompt** | Incluye contexto adicional. | “Eres un ingeniero de datos, explica este código SQL.” |
| **Chain-of-Thought Prompting** | Pide al modelo que razone paso a paso. | “Explícame paso a paso cómo calcular la media ponderada.” |
| **Few-shot Prompting** | Muestra ejemplos para guiar al modelo. | “Entrada: 2+2 → 4; Entrada: 3+3 → 6; Entrada: 4+4 → ?” |

El diseño de prompts se conoce como **Prompt Engineering**, una habilidad clave en el uso de modelos generativos.

---

## 🧩 Model

Un **Model** (modelo) en AI es una **representación matemática entrenada** para aprender patrones de los datos.  
Su función es **mapear una entrada (input)** a una **salida (output)** según el conocimiento adquirido.

🔹 **Ejemplo:**
- En ML clásico: modelo de regresión → predice valores.  
- En LLMs: modelo de lenguaje → predice la siguiente palabra más probable.

Cada modelo tiene:
- **Parámetros:** valores internos que ajustan el comportamiento.  
- **Pesos (weights):** números aprendidos durante el entrenamiento.  
- **Arquitectura:** define cómo fluyen los datos (por ejemplo, *Transformers* en LLMs).

---

## 🔤 Token

Un **Token** es la **unidad mínima de texto** que un modelo procesa.  
Puede ser una palabra, parte de una palabra o incluso un signo de puntuación, dependiendo del *tokenizer* utilizado.

🔹 **Ejemplo:**
El texto `"Machine Learning is awesome!"` podría dividirse en:
`["Machine", "Learn", "ing", "is", "awesome", "!"]`

Los LLMs trabajan **contando tokens**, no palabras.  
Esto influye en:
- El **costo** (en APIs de AI como OpenAI o AWS Bedrock).  
- El **límite de contexto** (cuántos tokens puede “recordar” el modelo).  

---

## 🧠 Fine-Tuning Model

El **Fine-Tuning** es el proceso de **ajustar un modelo preentrenado** (como un Foundation Model) con **datos específicos de un dominio** para mejorar su desempeño en tareas concretas.

🔹 **Ventajas:**
- Mejora la precisión en contextos especializados.  
- Permite personalizar el modelo a un negocio o lenguaje técnico.  

🔹 **Ejemplo:**
Tomar GPT-3 y entrenarlo adicionalmente con documentación médica para obtener un “MedGPT”.

---

## 🧮 Embedding (Concepto Clave)

Un **Embedding** es una **representación numérica de datos (texto, imagen, etc.) en un espacio vectorial**.  
Sirve para medir **similitud semántica**: textos con significados parecidos tienen vectores cercanos.

🔹 **Uso en RAG:**
Los documentos se convierten en *embeddings* y se almacenan en una **Vector Database** (como Pinecone, FAISS o OpenSearch).  
Cuando un usuario pregunta algo, el sistema busca los vectores más similares y devuelve los fragmentos relevantes al modelo.

---

## ⚡ Inference (Inferencia)

La **Inferencia** es el proceso de **usar un modelo entrenado para generar resultados** (por ejemplo, una predicción o una respuesta).  
No es entrenamiento, sino **ejecución del modelo ya aprendido**.

🔹 **Ejemplo:**
- Entrenamiento: el modelo aprende a traducir idiomas.  
- Inferencia: traduce “Hello” → “Hola”.

En AWS, la inferencia puede realizarse mediante servicios como:
- **SageMaker Endpoints**  
- **Bedrock** (para modelos fundacionales como Claude, Titan, LLaMA, etc.)

---

## 🧭 En resumen

| Concepto | Descripción Corta |
|-----------|------------------|
| **Foundation Model** | Modelo base de gran escala adaptable a múltiples tareas. |
| **LLM** | Modelo fundacional enfocado en lenguaje natural. |
| **RAG** | Combina búsqueda en conocimiento con generación de texto. |
| **Gen-AI** | Modelos capaces de generar contenido nuevo (texto, imágenes, código, etc.). |
| **Prompt** | Instrucción textual para guiar al modelo. |
| **Model** | Representación matemática entrenada para aprender patrones. |
| **Token** | Unidad mínima de texto que procesa el modelo. |
| **Fine-Tuning** | Ajuste de un modelo base con datos específicos. |
| **Embedding** | Representación numérica que mide similitud semántica. |
| **Inference** | Uso del modelo para generar resultados o predicciones. |

---

## 🧩 Diagrama Conceptual (AI → ML → DL → LLM → RAG)
# AI (Inteligencia Artificial)

- **ML (Machine Learning)**
  - **DL (Deep Learning)**
  - **Foundation Models**
    - **LLM (Modelos de Lenguaje)**
      - Prompts
      - Tokens
      - Fine-Tuning
      - Inference
    - **Gen-AI**
    - **RAG (con Knowledge Base)**
- **Embeddings** (para búsqueda semántica)

