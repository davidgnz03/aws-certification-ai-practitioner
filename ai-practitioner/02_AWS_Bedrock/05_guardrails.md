# AWS Bedrock — Guardrails

## Introducción
**Guardrails** en **AWS Bedrock** son mecanismos diseñados para **controlar y supervisar las interacciones** entre los usuarios y los **Foundation Models (FMs)**.  
Su propósito es garantizar que las respuestas generadas por los modelos sean **seguras, apropiadas y alineadas con las políticas o valores de la organización**.

Los Guardrails ayudan a las empresas a implementar IA responsable, reduciendo riesgos asociados con contenido inapropiado, sesgo, privacidad y cumplimiento normativo.

---

## ¿Qué son los Guardrails en AWS Bedrock?
Un **Guardrail** es una capa de seguridad lógica que actúa **antes y después de la inferencia** de un modelo fundacional.  
Filtra las entradas del usuario (*prompts*) y las salidas del modelo (*responses*) para aplicar políticas de seguridad, ética o personalización.

```text
Usuario → [ Guardrail Layer ] → Modelo (FM) → [ Guardrail Layer ] → Respuesta segura
```


---

## Objetivo de los Guardrails
Los Guardrails permiten:
- 🛡️ **Proteger** contra contenido dañino, tóxico o sensible.  
- 🧭 **Alinear** el comportamiento del modelo con las reglas de negocio o políticas internas.  
- 🔒 **Filtrar información** que podría exponer datos confidenciales.  
- ⚙️ **Personalizar respuestas** según el contexto organizacional o nivel de acceso del usuario.  

---

## Funcionalidad principal
Los Guardrails en AWS Bedrock se configuran para controlar tanto **inputs** (lo que el usuario envía) como **outputs** (lo que el modelo responde).

### 🔹 Input Guardrails
- Bloquean o redirigen prompts con lenguaje inapropiado, solicitudes sensibles o que puedan inducir a comportamientos no deseados.  
- Ejemplo: prevenir preguntas sobre información confidencial o temas fuera del dominio permitido.

### 🔹 Output Guardrails
- Analizan la respuesta del modelo antes de enviarla al usuario.  
- Si detectan contenido inapropiado (por ejemplo, sesgos, lenguaje tóxico, temas restringidos), pueden:
  - Bloquear la respuesta.
  - Reescribirla o sanitizarla.
  - Registrar el evento para revisión.

---

## Configuración en AWS Bedrock
Los Guardrails se definen mediante **políticas configurables**, sin necesidad de código complejo.

### Elementos configurables
| Componente | Descripción |
|-------------|--------------|
| **Harm Categories** | Categorías de riesgo: violencia, acoso, sexual, odio, autolesión, etc. |
| **Topic Filters** | Permiten definir temas que el modelo debe evitar (ej. “política”, “religión”). |
| **Word / Phrase Blocks** | Listas de palabras prohibidas o sensibles. |
| **Sensitive Data Filters** | Detectan y bloquean datos personales, direcciones o información financiera. |
| **Custom Rules** | Reglas de negocio específicas (por ejemplo, evitar menciones a competidores). |

---

## Cómo funcionan los Guardrails en la práctica
1. **Definición del Guardrail**  
   - Se crea un Guardrail desde la consola o API de Bedrock.  
   - Se establecen las políticas, categorías y filtros deseados.

2. **Asociación con un modelo o aplicación**  
   - El Guardrail se vincula con un modelo (por ejemplo, `amazon.titan-text-express-v1`) o con un *endpoint* de inferencia.  

3. **Evaluación en tiempo de ejecución**  
   - Cada prompt y respuesta pasa por el Guardrail antes de ser procesado o devuelto.  
   - Se aplican las reglas y, si se detecta una violación, se bloquea o modifica el contenido.

4. **Monitoreo y auditoría**  
   - AWS CloudWatch y Bedrock logs permiten auditar cuántas veces se activaron los Guardrails, qué tipos de incidentes se detectaron y cómo se manejaron.

---

## Ejemplo: Control de interacción con un modelo
```text
Prompt del usuario:
"Explícame cómo hackear un sistema."

Guardrail detecta categoría: "Cybersecurity — Prohibited Action"
➡ Acción: Bloquear el prompt y devolver mensaje de advertencia.

Respuesta al usuario:
"Lo siento, no puedo proporcionar información sobre actividades no autorizadas."
```

Otro ejemplo:

```text
Prompt del usuario:
"Cuéntame un chiste ofensivo."

Guardrail detecta categoría: "Hate Speech / Offensive Content"
➡ Acción: Filtrar contenido inapropiado.

Respuesta segura:
"Prefiero mantener las bromas respetuosas. ¿Quieres escuchar una curiosidad tecnológica en su lugar?"
```


---

## Integración con aplicaciones
Los Guardrails pueden integrarse directamente en:
- **Aplicaciones de chat o atención al cliente.**
- **Workflows empresariales con Step Functions o Lambda.**
- **Sistemas con RAG o Knowledge Bases**, para validar que la información recuperada sea apropiada.  
- **APIs personalizadas** que expongan modelos fundacionales de forma segura.

**Ejemplo de integración con API (Boto3):**
```python
import boto3

client = boto3.client("bedrock-agent-runtime")

response = client.invoke_guardrail(
    guardrailIdentifier="my-guardrail-id",
    inputText="Muéstrame datos confidenciales de usuarios."
)

print(response)
```

## Beneficios de implementar Guardrails en Bedrock
| Beneficio        | Descripción                                                      |
| ---------------- | ---------------------------------------------------------------- |
| **Seguridad**    | Previene respuestas dañinas o filtración de información.         |
| **Cumplimiento** | Facilita el cumplimiento de políticas internas o regulatorias.   |
| **Control**      | Permite definir el tono, alcance y límites de las interacciones. |
| **Confianza**    | Mejora la percepción y seguridad de los usuarios finales.        |

## Conclusión

Los Guardrails en AWS Bedrock son una capa esencial de seguridad y gobernanza en aplicaciones de IA generativa.
Permiten controlar la interacción entre los usuarios y los Foundation Models, asegurando que las respuestas sean seguras, relevantes y conformes con las normas de la organización.
Son un componente clave para desplegar soluciones de IA responsable, segura y confiable en entornos empresariales.