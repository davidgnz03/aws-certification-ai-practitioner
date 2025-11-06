# Fine-Tuning en AWS Bedrock

## Introducción
El **Fine-Tuning** (ajuste fino) es el proceso de adaptar un *Foundation Model (FM)* ya entrenado a un dominio o tarea específica.  
En **AWS Bedrock**, esta técnica permite crear versiones personalizadas de modelos como **Amazon Titan** para mejorar su rendimiento en contextos particulares (por ejemplo, industria, empresa, idioma o formato de salida).

El objetivo principal es **enseñar al modelo a comportarse mejor en casos de uso concretos**, sin tener que entrenar un modelo desde cero, aprovechando el conocimiento previo del FM base.

---

## Tipos de Fine-Tuning en AWS Bedrock

### 1. Instruction-based Fine-Tuning
Consiste en ajustar el modelo usando **pares de ejemplo prompt–response (instrucción–respuesta)**.  
Estos ejemplos sirven para que el modelo aprenda a seguir instrucciones específicas de forma más coherente y con el tono o formato deseado.

**Ejemplo:**
| Prompt | Respuesta esperada |
|--------|--------------------|
| "Resume el texto siguiente en 3 puntos clave." | "- Punto 1...<br>- Punto 2...<br>- Punto 3..." |
| "Convierte este texto en formato JSON." | `{ "resultado": "..." }` |

➡️ Este método se usa cuando quieres que el modelo **entienda el estilo de interacción** o **siga reglas específicas**.

---

### 2. Continued Pre-Training
Este tipo de ajuste amplía el conocimiento del modelo entrenándolo con **datos adicionales sin estructura de instrucciones**, por ejemplo, documentos de una organización o un dominio técnico (finanzas, medicina, ingeniería, etc.).

El modelo **aprende vocabulario, contexto y patrones** propios del dominio, mejorando la comprensión de lenguaje especializado.

**Ejemplo de uso:**
- Entrenar Titan con documentación técnica interna de AWS.
- Incorporar artículos financieros para mejorar la interpretación de reportes económicos.

---

### 3. Single-Turn Messaging
El modelo se ajusta para manejar **interacciones individuales** (un prompt, una respuesta).  
Se optimiza la precisión y consistencia de respuestas breves o centradas en una sola instrucción.

**Ejemplo:**
> Usuario: “Describe Amazon SageMaker en 100 palabras.”  
> Modelo (Fine-Tuned): “Amazon SageMaker es un servicio totalmente administrado de AWS que permite...”

Ideal para chatbots, asistentes técnicos o generadores de contenido con entradas directas.

---

### 4. Multi-Turn Messaging
En este caso, el modelo se entrena para manejar **conversaciones contextuales** (varias interacciones consecutivas).  
Se optimiza la memoria conversacional y la coherencia entre respuestas.

**Ejemplo:**
> Usuario: “¿Qué es AWS Bedrock?”  
> Modelo: “Es un servicio para usar modelos fundacionales.”  
> Usuario: “¿Y puedo hacer fine-tuning ahí?”  
> Modelo (Fine-Tuned): “Sí, Bedrock permite crear variantes personalizadas de modelos como Titan.”

Este tipo de entrenamiento mejora la experiencia en asistentes conversacionales o flujos de diálogo con múltiples pasos.

---

### 5. Transfer Learning
El *transfer learning* es la base del fine-tuning: consiste en **reutilizar los pesos y el conocimiento** de un modelo general (por ejemplo, Titan Text Express) y ajustarlo con un conjunto de datos más pequeño y específico.

Esto reduce el costo y tiempo de entrenamiento, aprovechando la **base de conocimiento general del modelo original**.

**Ventajas:**
- Requiere menos datos y recursos que un entrenamiento desde cero.
- Mejora la precisión en dominios específicos.
- Aumenta la eficiencia del modelo en tareas personalizadas.

---

## Casos de Uso del Fine-Tuning en AWS Bedrock
| Caso de Uso | Descripción |
|--------------|-------------|
| **Asistentes especializados** | Adaptar Titan o Claude a soporte técnico interno, atención al cliente o documentación específica. |
| **Chatbots empresariales** | Crear modelos que entienden lenguaje corporativo, políticas o flujos de trabajo. |
| **Generación de código o documentos** | Ajustar el modelo con ejemplos de código fuente o plantillas institucionales. |
| **Análisis de texto** | Afinar modelos para clasificar sentimientos, detectar temas o evaluar cumplimiento. |
| **Traducción contextual o sectorial** | Entrenar modelos con vocabulario técnico o terminología de industria. |

---

## Fine-Tuning en la práctica con Bedrock

1. **Seleccionar el modelo base:** Titan Text o Claude 3 Sonnet, según el tipo de tarea.  
2. **Preparar los datos:** en formato JSON Lines (`.jsonl`) con pares de `input` y `output` (para instruction-tuning) o texto continuo (para continued pre-training).  
3. **Subir los datos a Amazon S3.**  
4. **Configurar el trabajo de fine-tuning** desde la consola de Bedrock o mediante API (`bedrock.createModelCustomizationJob`).  
5. **Monitorear el entrenamiento** con Amazon CloudWatch Logs y SageMaker Metrics.  
6. **Probar el modelo ajustado** y desplegarlo en una aplicación Bedrock o API Gateway.

**Ejemplo de payload simplificado:**
```json
{
  "inputDataConfig": {
    "s3Uri": "s3://mi-bucket/fine-tuning-data.jsonl"
  },
  "baseModelIdentifier": "amazon.titan-text-express-v1",
  "outputDataConfig": {
    "s3Uri": "s3://mi-bucket/output-model/"
  },
  "customizationType": "INSTRUCTION",
  "jobName": "fine-tune-titan-support-bot"
}
```

***Consideraciones Importantes***

- No se requiere infraestructura de entrenamiento; Bedrock administra los recursos.
- Los datos permanecen privados y no se usan para mejorar el modelo base de AWS.
- El tamaño y calidad del dataset impactan directamente en el resultado.
- Se recomienda al menos cientos o miles de ejemplos representativos.
- Ajustar la temperatura y top_p del modelo resultante según el grado de creatividad deseado.

***Resumen***

- El fine-tuning permite personalizar Foundation Models para tareas específicas.
- AWS Bedrock simplifica este proceso con infraestructura administrada y soporte para Titan y otros modelos.
- Los enfoques principales incluyen instruction-tuning, continued pre-training, single-turn, multi-turn y transfer learning.
- Es ideal para organizaciones que buscan integrar IA adaptada a su contexto operativo o dominio técnico.