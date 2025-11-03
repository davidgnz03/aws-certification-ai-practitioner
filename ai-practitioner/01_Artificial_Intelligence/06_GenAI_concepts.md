# GenAI Concepts

## Introducción
La **Generative AI (GenAI)** se basa en modelos capaces de crear contenido nuevo — texto, imágenes, audio o código — a partir de instrucciones humanas (*prompts*).  
Para comprender cómo funcionan internamente estos modelos (como **Titan**, **Claude**, o **GPT**), es importante entender conceptos fundamentales como **tokens**, **tokenización**, **ventanas de contexto (context windows)** y **embeddings**.  
Estos conceptos determinan cómo el modelo interpreta el lenguaje, procesa la información y genera las respuestas.

---

## ¿Qué es un Token en GenAI?
Un **token** es la unidad básica de texto que un modelo de lenguaje utiliza para procesar información.  
Los modelos no leen texto carácter por carácter ni palabra por palabra, sino en forma de tokens.

Dependiendo del idioma y del modelo, un token puede representar:
- Una palabra completa (`house`)
- Parte de una palabra (`hous` + `e`)
- Un símbolo (`$`, `!`, `?`)
- Un espacio o salto de línea

**Ejemplo:**
```text
Texto original: "AWS Bedrock simplifies GenAI." 
Tokens (ejemplo): ["AWS", " Bed", "rock", " simplifies", " Gen", "AI", "."]
```
➡️ En este ejemplo, la frase tiene **7 tokens**.

El número de tokens determina:
- Cuánto texto puede procesar el modelo.
- Cuánto cuesta una solicitud (ya que los costos en GenAI suelen medirse por token).
- Cuánto contexto tiene disponible para responder.

---

## Tokenization (Tokenización)
La **tokenización** es el proceso de dividir el texto en tokens que el modelo puede entender.  
Este paso convierte texto natural en una secuencia numérica que representa unidades semánticas más pequeñas.

Existen diferentes enfoques de tokenización:

### 🔹 Word-Based Tokenization
Divide el texto por palabras completas.
```text
Texto: "Machine learning is powerful."
Tokens: ["Machine", "learning", "is", "powerful"]
```
**Ventaja:** Simple y directa.  
**Desventaja:** Ineficiente para idiomas con muchas variaciones o palabras compuestas.

---

### 🔹 Subword Tokenization
Divide el texto en fragmentos más pequeños (*subwords*) que pueden recombinarse para formar palabras.  
Es el enfoque usado por la mayoría de los modelos modernos (**BPE**, **SentencePiece**, **WordPiece**, etc.).

```text
Texto: "Powerfulness"
Tokens: ["Power", "ful", "ness"]
```


**Ventajas:**
- Reduce el tamaño del vocabulario.
- Maneja mejor palabras nuevas o raras.
- Aumenta la eficiencia del modelo.

**Herramienta práctica:**  
👉 [OpenAI Tokenizer](https://platform.openai.com/tokenizer)  
Permite visualizar cómo un modelo divide el texto en tokens.

---

## Context Windows (Ventanas de Contexto)
La **ventana de contexto** es la cantidad máxima de tokens que un modelo puede procesar en una sola interacción (prompt + respuesta).  
Determina el “límite de memoria” del modelo.

**Ejemplo:**
- Si un modelo tiene un *context window* de **8,000 tokens**, y el prompt ocupa 7,000, entonces solo quedan 1,000 para la respuesta.
- Modelos más avanzados (como Claude 3 o GPT-4 Turbo) pueden manejar hasta **200,000 tokens o más**, equivalentes a cientos de páginas de texto.

**Importancia:**
- Define cuánta información puede tener en cuenta el modelo a la vez.
- Impacta en el rendimiento y costo de las llamadas al modelo.
- En arquitecturas de RAG, la ventana de contexto limita cuántos fragmentos de información recuperada pueden inyectarse.

---

## Embeddings
Los **embeddings** son representaciones numéricas (vectores) de palabras, frases o documentos que capturan su **significado semántico**.  
En lugar de comparar texto directamente, los embeddings permiten medir similitud entre ideas mediante distancias en un espacio vectorial.

**Ejemplo conceptual:**

```text
Palabra: Vector (simplificado)
"cloud" → [0.91, 0.02, 0.77, 0.10]
"server" → [0.89, 0.05, 0.74, 0.11]
"banana" → [0.11, 0.92, 0.03, 0.88]
```

➡️ “Cloud” y “Server” están más cerca entre sí que de “Banana”.

**Usos comunes de embeddings:**
- **Búsqueda semántica:** encontrar documentos similares por significado, no por palabra exacta.  
- **Clustering y clasificación:** agrupar textos por tema o contexto.  
- **RAG (Retrieval-Augmented Generation):** convertir consultas y documentos a vectores para buscar coincidencias semánticas.  
- **Análisis de sentimiento o similitud textual.**

En **AWS Bedrock**, el modelo **Titan Embeddings** se usa para generar estos vectores y es un componente clave en implementaciones de RAG y sistemas de recomendación.

---

## Resumen
| Concepto | Descripción | Ejemplo / Relevancia |
|-----------|-------------|----------------------|
| **Token** | Unidad mínima de texto que el modelo procesa. | “Bedrock” → 2 tokens |
| **Tokenization** | Proceso de dividir texto en tokens. | Subword Tokenization (BPE, WordPiece) |
| **Context Window** | Límite de tokens por prompt. | Titan: 8K–32K; Claude 3: hasta 200K |
| **Embeddings** | Representaciones numéricas del significado del texto. | Usado en RAG y búsquedas semánticas |

---

## Conclusión
Comprender los conceptos de **tokens**, **tokenización**, **ventanas de contexto** y **embeddings** es esencial para optimizar el diseño de prompts, el rendimiento de modelos fundacionales y las soluciones de IA generativa en AWS Bedrock y otros entornos GenAI.
