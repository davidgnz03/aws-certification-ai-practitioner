# Prompt Engineering en Amazon Bedrock con Foundation Models (FM) — Titan

## Introducción
El *Prompt Engineering* es la técnica de diseñar instrucciones efectivas para guiar el comportamiento de un modelo generativo.  
En **Amazon Bedrock**, esto implica crear prompts claros para **Foundation Models** como **Titan**, controlar parámetros de generación y, cuando aplique, enriquecer con contexto (*RAG*).

---

## ¿Qué es Amazon Bedrock?
**Amazon Bedrock** es un servicio administrado para construir aplicaciones de IA generativa con modelos fundacionales de múltiples proveedores, sin gestionar infraestructura.

**Características clave**
- Acceso a múltiples FMs (Titan, Claude, Llama, Mistral, etc.) desde una API unificada.  
- Integración con servicios AWS (SageMaker, Lambda, API Gateway, Step Functions).  
- Soporte para **RAG**, **fine-tuning** y **embeddings**.  
- Seguridad y privacidad: los datos del cliente no reentrenan los modelos.

---

## Familia Titan en Bedrock
| Modelo | Descripción | Casos de uso típicos |
|---|---|---|
| **Titan Text Express** | LLM general para comprensión y generación de texto. | Q&A, resúmenes, asistentes. |
| **Titan Text Lite** | Variante ligera, más barata y rápida. | Clasificación, respuestas cortas. |
| **Titan Embeddings** | Convierte texto a vectores (embeddings). | Búsqueda semántica, RAG, clustering. |
| **Titan Image Generator** | Generación de imágenes desde texto. | Marketing, ideación visual. |

---

## ¿Qué es Prompt Engineering?
Diseñar prompts para:
- Definir **rol/contexto** del modelo.  
- Especificar **tarea/acción**.  
- Controlar **formato/tono** de salida.  
- Incluir **reglas y ejemplos**.

**Plantilla sugerida**
```
[Rol/Contexto]
[Instrucción principal (tarea)]
[Reglas/criterios de calidad]
[Ejemplos (opcional, few-shot)]
[Restricciones de seguridad/alcance]
[Formato de salida esperado]
```

**Ejemplo**
```
Rol: Eres un ingeniero de datos en AWS.
Tarea: Explica Amazon SageMaker y su relación con ML en 120-150 palabras.
Reglas: precisión técnica, lenguaje claro, sin marketing.
Formato: Markdown con subtítulos y listas.
```

---

## Tipos de prompts útiles en Bedrock
| Tipo | Descripción | Ejemplo breve |
|---|---|---|
| **Instruction** | Orden directa. | “Resume este texto en 3 puntos.” |
| **Contextual/Rol** | Añade rol o escenario. | “Eres analista financiero. Evalúa riesgos.” |
| **Zero-shot** | Solo instrucción. | “Clasifica positivo/negativo.” |
| **Few-shot** | Con ejemplos guía. | “Entrada: 2+2→4; 3+3→6; 5+5→?” |
| **Output-constrained** | Fija formato de salida. | “Devuelve JSON válido con `resumen`, `riesgos`.” |
| **Delimiters** | Aísla contexto con separadores. | “Usa solo lo entre [CONTEXT] ... [/CONTEXT].” |

> Nota: Evita pedir “razona paso a paso” si no necesitas ver el razonamiento. Mejor solicita “muestra tu respuesta final y los supuestos clave”.

---

## Parámetros de generación (Titan Text)
| Parámetro | Efecto | Guía rápida |
|---|---|---|
| `temperature` | Creatividad / diversidad. | 0.0–0.3 factual; 0.4–0.7 balance; >0.7 creativo. |
| `top_p` | Núcleo de probabilidad. | 0.8–0.95 suele funcionar bien. |
| `maxTokenCount` | Tope de tokens de salida. | Ajusta según longitud esperada. |
| `stopSequences` | Secuencias de parada. | Ej.: `["\n###", "END"]`. |
| `presencePenalty` / `frequencyPenalty` | Control de repeticiones. | 0.2–0.8 para reducir redundancia. |

---

## Ejemplo con AWS SDK (Boto3) — Titan Text Express
```python
import json
import boto3

bedrock = boto3.client("bedrock-runtime")

prompt = """\
Rol: Eres un experto en ML.
Tarea: Explica qué es Fine-Tuning y da un ejemplo breve.
Reglas: 100-130 palabras, sin jerga innecesaria.
Formato: Markdown con subtítulo y lista.
"""

body = {
    "inputText": prompt,
    "textGenerationConfig": {
        "temperature": 0.3,
        "topP": 0.9,
        "maxTokenCount": 300,
        "stopSequences": ["\n###"]
    }
}

resp = bedrock.invoke_model(
    modelId="amazon.titan-text-express-v1",
    contentType="application/json",
    accept="application/json",
    body=json.dumps(body)
)

payload = json.loads(resp["body"].read())
print(payload["results"][0]["outputText"])
```

---

## Prompt Engineering + RAG (con Embeddings de Titan)
**Objetivo:** inyectar contexto **verídico y actual** desde tu *knowledge base* para reducir alucinaciones.

**Flujo**
1. Generar embeddings (Titan Embeddings) de documentos.  
2. Indexar en una **vector DB** (OpenSearch, Pinecone, etc.).  
3. Recuperar *top-k* pasajes similares a la consulta.  
4. Construir *prompt* con esos pasajes como **contexto delimitado**.  
5. Invocar Titan Text (u otro FM) con el *prompt* enriquecido.

**Plantilla de prompt para RAG**
```
Usa EXCLUSIVAMENTE el contexto provisto para responder.
Si la respuesta no está en el contexto, responde: "No encontrado en el contexto."

[FORMATO DE SALIDA]
- Markdown
- Sección "Respuesta"
- Sección "Fuentes" con títulos de los pasajes usados

[CONTEXTO]
<<<DOC_1>>>
{fragmento_1}
<<<DOC_2>>>
{fragmento_2}

[PREGUNTA DEL USUARIO]
{consulta}
```

---

## Buenas prácticas
- **Especificidad**: pide exactamente lo que necesitas (longitud, formato, tono).  
- **Delimitadores**: aísla contexto `<<< >>>` o etiquetas como `[CONTEXT]`.  
- **Validación**: solicita *“si falta contexto, declara limitaciones”*.  
- **Idempotencia**: conserva prompts exitosos; versiona y etiqueta.  
- **Evaluación**: crea *golden prompts* y pruebas automatizadas (exact match, ROUGE/BLEU, checks de políticas).  
- **Costo/latencia**: usa Titan Lite para tareas cortas y experimentación.

---

## Errores comunes y cómo evitarlos
| Antipatrón | Síntoma | Corrección |
|---|---|---|
| Instrucciones vagas | Respuestas inconsistentes. | Añade rol, reglas y formato. |
| Prompt sin límites | Salidas demasiado largas. | Define `maxTokenCount` y secciones. |
| Contexto mezclado | Alucinaciones. | Delimita y declara “usar solo el contexto”. |
| Parámetros por defecto | Variabilidad alta. | Fija `temperature` y `top_p`. |
| Sin tests | Derivas de calidad con el tiempo. | Conjuntos de evaluación + CI para prompts. |

---

## Checklist rápido
- [ ] Rol/contexto definidos  
- [ ] Tarea concreta y medible  
- [ ] Reglas de estilo/tono/longitud  
- [ ] Formato de salida (Markdown/JSON/tabla)  
- [ ] Delimitadores de contexto (si RAG)  
- [ ] Límites: `maxTokenCount`, `stopSequences`  
- [ ] Parámetros: `temperature`, `top_p`  
- [ ] *Golden prompts* y tests de regresión  

---

## Recursos de referencia
- AWS Bedrock — User Guide  
- Titan Text Models — Overview  
- Titan Embeddings — Overview  
- Boto3 `bedrock-runtime` Reference  
