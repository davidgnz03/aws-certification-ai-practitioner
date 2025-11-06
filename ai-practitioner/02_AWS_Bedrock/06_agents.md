# AWS Bedrock — Agents

## Introducción
Los **Agents** en **AWS Bedrock** son componentes que permiten construir aplicaciones de **IA generativa autónoma y dirigida por objetivos**.  
A diferencia de un modelo fundacional tradicional que responde solo a un *prompt*, un **Agent** puede **razonar, planificar y ejecutar acciones** utilizando modelos de lenguaje junto con servicios y datos empresariales.  

En otras palabras, los *Agents* convierten un modelo de lenguaje en un **sistema inteligente capaz de tomar decisiones y actuar**, no solo generar texto.

---

## ¿Qué es un Agent en AWS Bedrock?
Un **Agent** es una entidad configurada dentro de AWS Bedrock que:
- Utiliza un **Foundation Model (FM)** (por ejemplo, Titan, Claude o Llama).  
- Sigue un **instructivo o definición de tarea** (*instruction set*).  
- Se conecta a **fuentes de datos, APIs o funciones AWS** mediante integraciones seguras.  
- Toma decisiones y ejecuta **acciones automáticas** con base en la intención del usuario.

**Ejemplo conceptual:**
```text
Usuario: "Actualiza el inventario con los nuevos precios del archivo S3."
↓
Agent:
Interpreta la instrucción (comprensión del lenguaje natural).
Llama a una función Lambda para obtener los datos.
Procesa la información.
Actualiza los registros en DynamoDB.
Devuelve la confirmación al usuario.
```


---

## ¿Cómo funcionan los Agents en AWS Bedrock?

El flujo de trabajo de un Agent en Bedrock se puede dividir en **cuatro etapas principales**:

### 1. User Query (Entrada del usuario)
El usuario realiza una solicitud en lenguaje natural, como:  
> “Muéstrame las ventas del último trimestre por región.”

El Agent interpreta la intención detrás del texto y determina qué acciones debe ejecutar.

---

### 2. Reasoning (Razonamiento y planificación)
El Agent utiliza un modelo fundacional (por ejemplo, **Claude 3 Sonnet**) para **razonar sobre la solicitud**.  
Genera un plan que describe los pasos necesarios para cumplir la tarea.

**Ejemplo de plan interno:**
1. Consultar la base de datos de ventas.  
2. Filtrar resultados por trimestre.  
3. Agrupar por región.  
4. Generar resumen de resultados.  

---

### 3. Action Execution (Ejecución de acciones)
El Agent puede interactuar con componentes externos a través de **funciones definidas** (*Action Groups*).  
Estas funciones pueden incluir:
- **AWS Lambda** — ejecutar lógica personalizada.  
- **Amazon S3** — leer o escribir archivos.  
- **Amazon DynamoDB** — consultar datos.  
- **APIs HTTP externas** — integraciones con aplicaciones de terceros.

El Agent selecciona las funciones adecuadas, las invoca con los parámetros correctos y recopila las respuestas.

**Ejemplo:**
```json
{
  "actionGroup": "GetSalesData",
  "function": "GetQuarterlySalesByRegion",
  "parameters": { "quarter": "Q3" }
}
```

### 4. Response Generation (Generación de respuesta)

Después de ejecutar las acciones necesarias, el Agent:
- Procesa los resultados obtenidos.  
- Construye una respuesta en lenguaje natural.  
- La envía de vuelta al usuario.  

Esto permite respuestas conversacionales dinámicas y contextualizadas.

---

## Componentes Clave de un Agent
| Componente                     | Descripción                                                         |
| ------------------------------ | ------------------------------------------------------------------- |
| **Foundation Model (FM)**      | Modelo que impulsa el razonamiento y generación de texto.           |
| **Instruction Set**            | Define las reglas, estilo y objetivos del Agent.                    |
| **Action Groups**              | Conjuntos de funciones (Lambda o APIs) que el Agent puede ejecutar. |
| **Knowledge Bases (opcional)** | Fuentes de conocimiento que el Agent puede consultar mediante RAG.  |
| **Session Memory**             | Permite mantener el contexto entre turnos de conversación.          |
| **Guardrails (opcional)**      | Controlan el tipo de interacciones y respuestas permitidas.         |

---

## Ejemplo de Arquitectura de un Agent en AWS Bedrock

```text
┌───────────────────────────────┐
│          Usuario              │
└──────────────┬────────────────┘
               │
               ▼
     ┌────────────────────┐
     │  AWS Bedrock Agent │
     └────────────────────┘
        │  ▲       │  ▲
        │  │       │  │
        ▼  │       ▼  │
  [Foundation Model]  │
        │             │
        ▼             ▼
[Knowledge Base]   [Action Groups]
   (RAG Search)     (Lambda / APIs)
```

## Beneficios de usar Agents en AWS Bedrock

| Beneficio                      | Descripción                                                 |
| ------------------------------ | ----------------------------------------------------------- |
| **Automatización inteligente** | Ejecutan tareas complejas a partir de lenguaje natural.     |
| **Integración nativa con AWS** | Acceden directamente a servicios como Lambda, S3, DynamoDB. |
| **Escalabilidad y seguridad**  | Basados en infraestructura administrada por AWS.            |
| **Contexto y memoria**         | Mantienen información de conversaciones anteriores.         |
| **Razonamiento multi-paso**    | Dividen tareas complejas en acciones secuenciales.          |


---

## Casos de Uso Comunes
| Caso de Uso                   | Descripción                                                                  |
| ----------------------------- | ---------------------------------------------------------------------------- |
| **Asistentes empresariales**  | Automatizan flujos de trabajo internos o consultas administrativas.          |
| **Soporte técnico**           | Consultan bases de datos, generan tickets o ejecutan scripts de diagnóstico. |
| **Análisis de datos**         | Obtienen, transforman y resumen información desde servicios AWS.             |
| **Orquestación de procesos**  | Ejecutan múltiples pasos automatizados en diferentes servicios.              |
| **Integración con RAG y KBs** | Combinan conocimiento estructurado con generación de texto contextual.       |

---

## Conclusión

Los **Agents en AWS Bedrock** representan un salto evolutivo en la forma en que los modelos fundacionales interactúan con sistemas reales.  


Permiten que un modelo **no solo genere texto**, sino que también **razone, actúe y resuelva** tareas de forma automatizada, segura y escalable dentro del ecosistema de AWS.  


Son la base para construir **asistentes inteligentes y aplicaciones empresariales autónomas** impulsadas por IA generativa.

---