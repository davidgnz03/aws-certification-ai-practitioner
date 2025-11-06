# What is Prompt Engineering?

## Introducción
**Prompt Engineering** es la práctica de **diseñar, desarrollar y optimizar prompts** (instrucciones en lenguaje natural o estructurado) para obtener **respuestas precisas, útiles y alineadas** a las necesidades del usuario o de la aplicación.  
En el contexto de **Foundation Models (FMs)** como los disponibles en **AWS Bedrock**, el prompt actúa como la **interfaz directa de comunicación** entre el humano y el modelo de IA generativa.

---

## Definición
> **Prompt Engineering** consiste en desarrollar, diseñar y optimizar prompts para mejorar la salida de los Foundation Models (FMs) de acuerdo con los objetivos del usuario.

El enfoque busca **maximizar la calidad y relevancia de las respuestas** controlando cuidadosamente:
- El contenido del prompt.  
- Su estructura y formato.  
- El contexto o información adicional que se incluye.  
- Los parámetros de generación (como `temperature`, `top-k`, `maxTokens`, etc.).

---

## Importancia del Prompt Engineering
Los modelos de lenguaje no “entienden” en el sentido humano, sino que **predicen patrones** basados en los datos de entrenamiento.  
Por ello, la forma en que se formula el prompt puede cambiar radicalmente la calidad del resultado.

**Ejemplo simple:**
```text
Prompt 1: "Describe AWS Bedrock."
    → Respuesta genérica y breve.

Prompt 2: "Describe AWS Bedrock en detalle, incluyendo sus principales componentes, modelos fundacionales y casos de uso empresariales."
    → Respuesta más completa, estructurada y relevante.
```

---


---

## Objetivos del Prompt Engineering
| Objetivo | Descripción |
|-----------|--------------|
| **Claridad** | Asegurar que el modelo entienda exactamente qué se solicita. |
| **Consistencia** | Obtener resultados estables ante prompts similares. |
| **Eficiencia** | Reducir el número de tokens o iteraciones necesarias. |
| **Control** | Guiar el estilo, tono o formato de las respuestas. |
| **Optimización de costo** | Ajustar prompts para usar menos tokens sin perder calidad. |

---

## Técnicas Comunes de Prompt Engineering

### 🔹 Instrucciones explícitas
Decirle claramente al modelo qué hacer.  
```text
"Resume este texto en formato de lista con los 3 puntos principales."
```


### 🔹 Ejemplos (Few-shot prompting)
Proporcionar ejemplos en el prompt para mostrar el formato o estilo deseado.  


**Ejemplo:**
```text
Entrada: "Sol"
Salida: "Una estrella que proporciona energía al sistema solar."

Entrada: "Luna"
Salida:
```
**Resultado esperado:**
> “Un satélite natural que orbita alrededor de la Tierra.”
---

### 🔹 Chain-of-Thought (CoT)
Pedir al modelo que **razone paso a paso** antes de ofrecer una respuesta final.

```text
"Piensa paso a paso antes de responder para llegar a la mejor conclusión."
```


---

### 🔹 Role-Based Prompting
Asignar un rol o contexto al modelo para influir en su estilo y tono de respuesta.

```text
"Eres un arquitecto de soluciones AWS. Explica cómo implementar una arquitectura de IA generativa escalable en AWS Bedrock."
```


---

### 🔹 Contextual Prompting
Agregar información de referencia (por ejemplo, resultados de RAG o datos empresariales) para que el modelo genere respuestas más informadas.


```text
"Usando la información del documento siguiente, explica los beneficios de AWS Bedrock para empresas del sector financiero."
```


---

## Mejores Prácticas
- ✍️ Escribe prompts claros, directos y sin ambigüedades.  
- 🧩 Incluye contexto cuando sea necesario.  
- ⚙️ Ajusta parámetros de generación (`temperature`, `topP`, `maxTokens`) según la tarea.  
- 📋 Define un formato de salida (lista, tabla, resumen, etc.).  
- 🔁 Itera y evalúa distintos enfoques para mejorar resultados.  
- 📚 Crea una **librería de prompts efectivos** para uso recurrente.  

---

## Ejemplo en AWS Bedrock

**Prompt:**
```text
Eres un experto en AWS. Explica qué es Amazon Bedrock y menciona sus principales beneficios para la creación de aplicaciones de IA generativa empresariales.

Responde en formato de lista numerada.
```


**Posible Respuesta:**
```
1. Amazon Bedrock es un servicio totalmente gestionado que facilita el acceso a modelos fundacionales mediante una API.  
2. Permite integrar modelos de Titan, Claude, Llama, entre otros.  
3. Simplifica el desarrollo de aplicaciones GenAI seguras y escalables.  
4. Se integra con servicios como CloudWatch, Guardrails y Knowledge Bases para control y monitoreo.
```

---

## Conclusión
El **Prompt Engineering** es una habilidad esencial en el uso de modelos de IA generativa.  
Dominar la redacción, estructura y optimización de prompts permite **obtener resultados más precisos, controlados y rentables**.  
En el ecosistema de **AWS Bedrock**, un buen prompt es la clave para aprovechar el máximo potencial de los **Foundation Models**, garantizando eficiencia y calidad en las aplicaciones de IA empresarial.
