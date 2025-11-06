# AWS Bedrock — Foundation Models (FM)

## Introducción
Los **Foundation Models (FM)** son modelos de inteligencia artificial a gran escala, entrenados con enormes volúmenes de datos y capaces de realizar una amplia variedad de tareas.  
En **AWS Bedrock**, estos modelos están disponibles como un servicio totalmente administrado, lo que permite utilizarlos sin tener que construir ni mantener infraestructura de entrenamiento o despliegue.

AWS Bedrock ofrece acceso a modelos de distintos proveedores (como **Amazon**, **Anthropic**, **Meta**, **Cohere**, **Mistral**, entre otros), lo que facilita elegir el modelo más adecuado para cada caso de uso.

---

## ¿Qué es un Foundation Model?
Un **Foundation Model** es un modelo de Machine Learning de propósito general que sirve como base (“foundation”) para múltiples aplicaciones de inteligencia artificial.

Estos modelos:
- Se entrenan con **grandes volúmenes de datos multilingües y multimodales** (texto, imágenes, código, etc.).
- Son **preentrenados** y luego pueden **ajustarse (fine-tuning)** o **especializarse (prompt tuning)** para tareas específicas.
- Tienen la capacidad de **razonar, generar, resumir, traducir y responder preguntas**, entre otras tareas.

Ejemplos:
- Modelos de lenguaje como **Titan Text Express** o **Claude 3 Sonnet**.  
- Modelos de embeddings como **Titan Embeddings**.  
- Modelos generativos de imágenes como **Titan Image Generator**.

---

## AWS Bedrock y los Foundation Models

**Amazon Bedrock** es el servicio que centraliza y simplifica el acceso a Foundation Models mediante una **API unificada** y sin necesidad de configurar infraestructura de Machine Learning.  

### Características clave
- 🔹 **API unificada:** invoca cualquier modelo compatible (Titan, Claude, Llama, Mistral, etc.) con una sola API.  
- 🔹 **Sin infraestructura:** AWS se encarga de la administración, escalabilidad y seguridad.  
- 🔹 **Integración nativa con servicios AWS:** Lambda, SageMaker, API Gateway, Step Functions, S3, CloudWatch, etc.  
- 🔹 **Personalización:** admite *fine-tuning*, *RAG* (Retrieval-Augmented Generation) y *embedding search*.  
- 🔹 **Seguridad empresarial:** los datos no se usan para reentrenar los modelos y se alojan dentro de la cuenta del cliente.  

---

## Proveedores y Modelos Disponibles
AWS Bedrock proporciona acceso a un ecosistema de modelos líderes:

| Proveedor | Modelo | Tipo | Descripción |
|------------|---------|------|--------------|
| **Amazon** | Titan Text Express / Lite | Texto | Generación, resumen y clasificación de texto. |
| **Amazon** | Titan Embeddings | Embeddings | Convierte texto en vectores para búsquedas semánticas. |
| **Amazon** | Titan Image Generator | Imagen | Genera imágenes a partir de texto. |
| **Anthropic** | Claude 3 Family (Haiku, Sonnet, Opus) | Texto | Modelos conversacionales avanzados, razonamiento contextual. |
| **Meta** | Llama 3 | Texto | Modelo open-source optimizado para rendimiento y personalización. |
| **Cohere** | Command R / R+ | Texto | Modelos especializados en RAG y recuperación de información. |
| **Mistral AI** | Mistral / Mixtral | Texto | Modelos livianos y de alto rendimiento para generación y análisis. |

> 💡 Cada modelo tiene diferentes **fortalezas, costos y latencias**, por lo que AWS permite probar y comparar dentro de la misma consola.

---

## Arquitectura General de Bedrock con FMs


```text

# 🧱 AWS Bedrock Architecture

                        │
├───────────────────────────────────────────────┐
│                                               │
│               **AWS Bedrock**                 │
│                                               │
│   ┌───────────────────────────────────────┐   │
│   │         Foundation Models Hub         │   │
│   │  ──────────────────────────────────   │   │
│   │   (Titan, Claude, Llama...)           │   │
│   └───────────────────────────────────────┘   │
│                                               │
│                 ↑ API unificada ↓             │
│                                               │
│   ┌───────────────────────────────────────┐   │
│   │       Aplicaciones del Cliente        │   │
│   │  ──────────────────────────────────   │   │
│   │   (Chatbot, Analítica, Código, …)     │   │
│   └───────────────────────────────────────┘   │
│                                               │
└───────────────────────────────────────────────┘
                        │
                        ▼
            **AWS Services Integrados**  
            (S3, Lambda, SageMaker, etc.)
```

Esta arquitectura permite construir soluciones escalables de IA generativa sin administrar GPUs ni clústeres de entrenamiento.

---

## Ciclo de Vida de Uso de un FM en Bedrock
1. **Seleccionar el modelo adecuado:** según la tarea (texto, imagen, embeddings).  
2. **Diseñar el prompt:** instrucción o contexto que define la tarea.  
3. **Ajustar parámetros de generación:** `temperature`, `top_p`, `maxTokenCount`, etc.  
4. **(Opcional) Aplicar Fine-Tuning:** para tareas o dominios específicos.  
5. **(Opcional) Implementar RAG:** para enriquecer respuestas con conocimiento externo.  
6. **Integrar en la aplicación:** usando SDKs, API Gateway o AWS Lambda.  
7. **Monitorear desempeño:** con CloudWatch y métricas de respuesta.

---

## Ejemplo de invocación con Boto3
```python
import boto3
import json

bedrock = boto3.client("bedrock-runtime")

prompt = "Resume en tres puntos las ventajas de Amazon Bedrock."

body = {
    "inputText": prompt,
    "textGenerationConfig": {
        "temperature": 0.3,
        "topP": 0.9,
        "maxTokenCount": 200
    }
}

response = bedrock.invoke_model(
    modelId="amazon.titan-text-express-v1",
    contentType="application/json",
    accept="application/json",
    body=json.dumps(body)
)

result = json.loads(response["body"].read())
print(result["results"][0]["outputText"])
```

---

## Beneficios de usar Foundation Models en Bedrock

| Beneficio                   | Descripción                                                 |
| --------------------------- | ----------------------------------------------------------- |
| **Velocidad de desarrollo** | No es necesario entrenar modelos desde cero.                |
| **Escalabilidad**           | AWS maneja el cómputo y ajuste dinámico de recursos.        |
| **Seguridad y privacidad**  | Los datos permanecen dentro de la cuenta del cliente.       |
| **Interoperabilidad**       | Diferentes modelos pueden coexistir en la misma aplicación. |
| **Costo eficiente**         | Pago por uso, sin necesidad de hardware dedicado.           |

---

## Conclusión

Los Foundation Models en AWS Bedrock representan la capa base de la inteligencia artificial moderna en AWS.  
Permiten construir soluciones de IA generativa, analítica o conversacional ***de forma rápida, segura y escalable***, aprovechando modelos líderes del mercado sin la complejidad de gestionarlos manualmente.