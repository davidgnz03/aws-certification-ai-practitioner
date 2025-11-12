# 🧱 GenAI Security Scoping Matrix  
## Matriz de Alcance de Seguridad para Generative AI

---

### 🧭 ¿Qué es la *Generative AI Security Scoping Matrix*?

La **Generative AI Security Scoping Matrix** es un **marco de referencia (framework)** diseñado para **identificar, clasificar y gestionar los riesgos de seguridad** asociados con el desarrollo y despliegue de aplicaciones de **Inteligencia Artificial Generativa (GenAI)**.

Permite determinar el **nivel de responsabilidad y control** que una organización debe ejercer sobre los diferentes componentes de su solución de AI, **desde el uso de servicios completamente gestionados hasta modelos personalizados de alta propiedad**.

---

### 🎯 Objetivo Principal

- Evaluar el **riesgo de seguridad** en función del **grado de control** sobre el modelo, los datos y la infraestructura.  
- Ayudar a las organizaciones a:
  - Definir **políticas de seguridad adecuadas**.  
  - Establecer **controles de cumplimiento y gobernanza**.  
  - Aplicar **estrategias de mitigación proporcionales** al nivel de riesgo.  

> 🧠 *El principio clave es simple: cuanto mayor es el nivel de personalización o control, mayor es la responsabilidad de seguridad.*

---

### 🧩 Clasificación: Niveles de Propiedad (*Scopes*)

Las aplicaciones se clasifican en **cinco niveles (scopes)** de **propiedad o control**, que van de **bajo a alto**.

```plaintext
         ┌────────────────────────────────────────────────────────────────────────┐
         │                         Security Generative AI                         │
         │------------------------------------------------------------------------│
         │ Governance & Compliance | Legal & Privacy | Risk Management | Controls │
         │                            | Resilience                                │
         └────────────────────────────────────────────────────────────────────────┘
                                            │
                                            ▼
         ┌─────────────┬─────────────┬──────────────┬──────────────┬─────────────┐
         │  Scope 1    │  Scope 2    │  Scope 3     │  Scope 4     │  Scope 5    │
         │ Consumer    │ Enterprise  │ Pre-trained  │ Fine-tuned   │ Self-trained│
         │   App       │    App      │   Models     │   Models     │   Models    │
         ├─────────────┼─────────────┼──────────────┼──────────────┼─────────────┤
         │ Public GenAI│ SaaS with   │ Use versioned│ Fine-tune    │ Train from  │
         │ services    │ GenAI tools │ base models  │ with your    │ scratch     │
         │             │             │              │   data       │   data      │
         ├─────────────┼─────────────┼──────────────┼──────────────┼─────────────┤
         │ ChatGPT,    │ Salesforce  │ Amazon       │ Amazon       │ SageMaker   │
         │ Midjourney  │ Einstein GPT│ Bedrock base │ Bedrock cust.│             │
         │             │ Amazon Q Dev│   models     │ SageMaker JS │             │
         └─────────────┴─────────────┴──────────────┴──────────────┴─────────────┘

```

| **Scope / Nivel** | **Descripción General** | **Nivel de Propiedad** | **Responsabilidad de Seguridad Principal** |
|--------------------|--------------------------|------------------------|--------------------------------------------|
| **Scope 1 – Fully Managed AI Service** | Uso de servicios de AI completamente gestionados (ej. Amazon Bedrock, Amazon Comprehend). | Bajo | AWS gestiona la seguridad del modelo e infraestructura. El cliente gestiona el acceso y los datos. |
| **Scope 2 – Pre-trained Model with Configuration** | Se utiliza un modelo preentrenado ajustado mediante configuración mínima o *prompts*. | Bajo-Medio | AWS gestiona el modelo; el cliente es responsable de los datos y del uso adecuado de *guardrails*. |
| **Scope 3 – Fine-Tuned Model** | El cliente realiza *fine-tuning* de un modelo base con sus propios datos. | Medio | El cliente debe proteger sus datos y gestionar la seguridad del entrenamiento. |
| **Scope 4 – Custom Model on Managed Infrastructure** | Se entrena un modelo personalizado sobre infraestructura gestionada (por ejemplo, SageMaker). | Alto | El cliente controla entrenamiento, datos y despliegue; AWS asegura la infraestructura. |
| **Scope 5 – Self-managed Model and Infrastructure** | Modelo completamente desarrollado y desplegado en infraestructura propia. | Muy Alto | El cliente es responsable total de la seguridad, cumplimiento, y mantenimiento del sistema. |

> 🔒 *Mientras más “propiedad” se tenga sobre el modelo o los datos, mayor es la exposición al riesgo y la necesidad de controles personalizados.*

---

### ⚙️ Aplicación del Framework

Para cada aplicación de GenAI, evalúe:

1. **Tipo de modelo utilizado** (preentrenado, ajustado o personalizado).  
2. **Nivel de control sobre los datos y la infraestructura.**  
3. **Riesgos potenciales de privacidad, integridad y cumplimiento.**  
4. **Controles de seguridad aplicables** (cifrado, auditorías, guardrails, acceso, etc.).  

---

### 🧠 Beneficios Clave

- Estandariza la **evaluación de riesgos** para proyectos GenAI.  
- Mejora la **visibilidad de responsabilidades compartidas** entre cliente y proveedor.  
- Facilita la **toma de decisiones** sobre dónde aplicar inversiones en seguridad.  
- Alinea la gestión de AI con el **modelo de responsabilidad compartida de AWS**.

---

> 🧩 *En resumen: la “GenAI Security Scoping Matrix” permite escalar la innovación en inteligencia artificial generativa sin comprometer la seguridad, el cumplimiento ni la confianza.*
