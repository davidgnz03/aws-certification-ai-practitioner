# RAG and Knowledge Base

## Introducción
**RAG (Retrieval-Augmented Generation)** es una técnica que combina la generación de texto mediante modelos de lenguaje con la recuperación de información desde fuentes externas.  
Su objetivo es mejorar la **precisión, actualidad y contexto** de las respuestas de un modelo sin necesidad de volver a entrenarlo.

En lugar de depender únicamente del conocimiento interno del modelo, RAG **inyecta información relevante en tiempo de ejecución** desde una base de conocimiento (*Knowledge Base*), normalmente almacenada en una **base de datos vectorial (Vector DB)**.

---

## ¿Qué es Retrieval-Augmented Generation (RAG)?
**RAG** se compone de dos fases principales:

1. **Retrieval (Recuperación):**  
   El sistema busca y recupera documentos, párrafos o fragmentos de texto relevantes desde una base de conocimiento indexada por vectores (*embeddings*).

2. **Augmented Generation (Generación aumentada):**  
   Los resultados recuperados se integran dentro del *prompt* del modelo de lenguaje, para que la respuesta final esté respaldada por información actualizada y verificada.

**Objetivo:** Reducir *alucinaciones* (respuestas incorrectas o inventadas) y ofrecer respuestas basadas en datos reales.

---

## Vector Database

Una **Vector Database** almacena representaciones numéricas (*embeddings*) de texto, imágenes o cualquier dato semántico.  
Esto permite realizar **búsquedas por similitud** en lugar de coincidencias exactas de palabras.

**Proceso básico:**
1. El texto (por ejemplo, un documento o párrafo) se convierte en un vector de alta dimensión mediante un *embedding model*.  
2. Estos vectores se almacenan en una base de datos vectorial.  
3. Cuando el usuario hace una pregunta, el sistema convierte la consulta en un vector y busca los más similares (top-k matches).  
4. Los fragmentos correspondientes se pasan al modelo generativo como contexto adicional.

---

## Servicios comunes usados con RAG

En el contexto general de IA (y no específico aún de AWS Bedrock), se pueden usar varios servicios o herramientas para implementar RAG:

| Tipo | Ejemplo de Servicio | Descripción |
|------|---------------------|--------------|
| **Vector Database** | Pinecone, Weaviate, Qdrant, FAISS, Milvus, Chroma | Almacenan los embeddings y permiten búsquedas por similitud. |
| **Embedding Models** | OpenAI Embeddings, Sentence-BERT, Titan Embeddings | Transforman texto en vectores. |
| **Document Loaders / Chunkers** | LangChain, LlamaIndex, Haystack | Dividen los documentos en fragmentos y los preparan para indexar. |
| **Orchestrators / Frameworks** | LangChain, Semantic Kernel, Haystack | Integran las fases de recuperación y generación. |

---

## ¿Cómo funciona el proceso RAG?
El flujo típico de RAG sigue estas etapas:

1. **Ingesta de datos**
   - Se recopilan documentos de diferentes fuentes (PDFs, bases de datos, APIs, sitios web, etc.).
   - Se fragmentan (*chunking*) para mejorar la granularidad de búsqueda.

2. **Generación de embeddings**
   - Cada fragmento se convierte en un vector mediante un modelo de *embeddings*.

3. **Indexación**
   - Los vectores y metadatos se almacenan en una **vector database**.

4. **Consulta del usuario**
   - La pregunta se convierte también en un embedding.

5. **Búsqueda por similitud**
   - El sistema recupera los fragmentos más parecidos semánticamente (*top-k retrieval*).

6. **Generación aumentada**
   - Los fragmentos relevantes se incorporan al *prompt* del modelo (como contexto).
   - El modelo genera una respuesta fundamentada en esa información.

**Visualmente:**

```text
[Usuario] → [Consulta]
↓
[Embedding Query]
↓
[Vector Search en Base de Conocimiento]
↓
[Documentos relevantes]
↓
[Prompt + Contexto]
↓
[Modelo Generativo → Respuesta]
```

---

## Augmented Prompt → Response
En un escenario RAG, el *prompt* no solo contiene la instrucción del usuario, sino también **información adicional recuperada**.

**Ejemplo:**

```
Contexto:
"Amazon Bedrock es un servicio totalmente administrado que permite usar Foundation Models a través de una API."  

Pregunta:
"¿Qué es AWS Bedrock y para qué se utiliza?"

Prompt aumentado:
Usa exclusivamente la información del contexto para responder de forma clara y concisa.

Contexto:
Amazon Bedrock es un servicio totalmente administrado que permite usar Foundation Models a través de una API.

Respuesta esperada:
AWS Bedrock es un servicio que facilita el uso de modelos fundacionales mediante una API administrada por AWS.
```


---

## RAG Data Sources

Las fuentes de datos utilizadas para construir una *Knowledge Base* pueden variar según la organización o el caso de uso:

| Tipo de Fuente | Ejemplo | Descripción |
|----------------|----------|--------------|
| **Documentos corporativos** | Políticas, manuales, PDFs internos | Información institucional. |
| **Bases de datos estructuradas** | SQL, DynamoDB, MongoDB | Datos tabulares o metadatos. |
| **Repositorios de conocimiento** | Confluence, Notion, SharePoint | Información documental colaborativa. |
| **Fuentes públicas** | Wikipedia, sitios web, APIs | Información general o contextual. |
| **Logs o tickets** | Zendesk, Salesforce, Jira | Casos de soporte o consultas frecuentes. |

---

## RAG Use Cases

| Caso de Uso | Descripción |
|--------------|-------------|
| **Chatbots empresariales** | Proporcionar respuestas basadas en documentación interna actualizada. |
| **Asistentes técnicos** | Recuperar información de manuales o guías específicas. |
| **Análisis documental** | Buscar y resumir información en grandes volúmenes de texto. |
| **Compliance y auditoría** | Validar decisiones o respuestas con documentos oficiales. |
| **Soporte al cliente** | Acelerar respuestas usando datos de tickets anteriores o FAQs. |
| **Educación / entrenamiento** | Integrar información verificada en materiales de aprendizaje generados automáticamente. |

---

## Beneficios del enfoque RAG
- 🔹 Reduce *alucinaciones* del modelo.  
- 🔹 Aumenta la precisión y la confianza de las respuestas.  
- 🔹 Evita costosos procesos de *fine-tuning*.  
- 🔹 Permite actualizaciones inmediatas al conocimiento sin reentrenar el modelo.  
- 🔹 Facilita trazabilidad: las respuestas se basan en documentos verificables.

---

## Conclusión
RAG combina lo mejor de dos mundos:  
- La **potencia generativa** de los modelos fundacionales (como Titan o Claude).  
- La **precisión documental** de bases de conocimiento externas.  

Es una técnica esencial para crear aplicaciones de IA confiables, actualizadas y contextualmente relevantes en entornos corporativos y productivos.
