# Improved Prompting Techniques

## Introducción
Las **Improved Prompting Techniques** se enfocan en estructurar de manera más inteligente los prompts para guiar al modelo hacia respuestas **más precisas, controladas y útiles**.  
En lugar de depender únicamente de una instrucción general, estas técnicas incorporan **contexto, datos y formato esperado**, lo que mejora significativamente la calidad de las respuestas en aplicaciones basadas en **AWS Bedrock**.

---

## Componentes de un Prompt Mejorado

Un **prompt bien diseñado** combina cuatro elementos clave:

| Elemento | Descripción | Ejemplo |
|-----------|--------------|----------|
| **Instructions** | Indican claramente lo que el modelo debe hacer. | “Resume el siguiente texto en tres puntos principales.” |
| **Context** | Proporciona información adicional o antecedentes relevantes. | “Eres un especialista en AWS.” |
| **Input Data** | Contiene los datos o texto sobre el que el modelo debe trabajar. | “Texto: AWS Bedrock permite acceder a modelos fundacionales...” |
| **Output Indicator** | Define el formato o estilo de la salida esperada. | “Responde en formato de lista numerada.” |

**Ejemplo completo:**

```text
Context: Eres un consultor de AWS especializado en IA generativa.

Instruction: Explica brevemente qué es Amazon Bedrock y sus principales ventajas.

Input Data: “Amazon Bedrock es un servicio totalmente gestionado que permite acceder a Foundation Models a través de API.”

Output Indicator: Responde en formato de lista.
```

**Resultado esperado:**
```
1. Servicio administrado por AWS para IA generativa.  
2. Permite acceder a múltiples modelos fundacionales.  
3. Facilita el desarrollo de soluciones seguras y escalables.
```

---

## Beneficios de las Improved Prompting Techniques
- 🧭 **Dirección clara:** guían al modelo paso a paso hacia el resultado deseado.  
- 🧩 **Consistencia:** permiten obtener salidas predecibles y bien estructuradas.  
- 💬 **Menos ambigüedad:** reducen respuestas irrelevantes o fuera de contexto.  
- ⚙️ **Mayor control:** permiten definir explícitamente cómo, cuándo y en qué formato debe responder el modelo.  

---

# Negative Prompting

## Definición
**Negative Prompting** es una técnica en la que se le indica explícitamente al modelo **qué no debe hacer o incluir** en su respuesta.  
Es una forma de restricción semántica que ayuda a **evitar desviaciones** y **mantener la respuesta enfocada** en lo realmente importante.

> En otras palabras: mientras el *prompt positivo* indica *qué hacer*, el *negative prompt* indica *qué evitar*.

---

## ¿Por qué usar Negative Prompting?
El objetivo del *negative prompting* es **reducir el ruido o la ambigüedad** en la generación de texto, asegurando que las respuestas sean relevantes y apropiadas para el contexto de negocio.

### Beneficios principales
| Beneficio | Descripción |
|------------|--------------|
| **Avoid Unwanted Content** | Elimina información fuera del tema o respuestas inapropiadas. |
| **Maintain Focus** | Centra la atención del modelo en el tema principal. |
| **Enhance Clarity** | Mejora la coherencia y precisión de la respuesta final. |

---

## Ejemplos Prácticos

### 🔹 Ejemplo 1 — Control de tono



> Prompt:
Eres un asistente empresarial. Explica qué es AWS Bedrock.  
No incluyas lenguaje informal ni ejemplos humorísticos.

**Resultado:**
> AWS Bedrock es un servicio administrado que facilita el uso de modelos fundacionales para crear aplicaciones de IA generativa empresariales.

---

### 🔹 Ejemplo 2 — Control de contenido
**Prompt:**
>Describe las ventajas de la IA generativa.  
No hables de desventajas ni de preocupaciones éticas.  

**Resultado:**
> La IA generativa permite automatizar tareas creativas, generar contenido personalizado y mejorar la productividad empresarial.

---

### 🔹 Ejemplo 3 — Control de formato
**Prompt:**
>Resume este texto en tres puntos.  
No incluyas conclusiones ni comentarios personales.  

**Resultado:**
```
1. AWS Bedrock proporciona acceso a Foundation Models.  
2. Permite integrar IA generativa en aplicaciones empresariales.  
3. Ofrece herramientas para personalización y seguridad.
```

---

## Buenas Prácticas
- 🧱 Combina prompts positivos y negativos para mayor control.  
- ⚖️ Usa lenguaje claro y objetivo en las restricciones (“no incluyas...”, “evita mencionar...”).  
- 🚫 Evita restricciones excesivas, ya que pueden limitar demasiado la creatividad del modelo.  
- 🧠 Valida los resultados iterativamente para ajustar el equilibrio entre libertad y control.  

---

## Conclusión
Las **Improved Prompting Techniques** permiten construir prompts más completos y efectivos al combinar instrucciones, contexto, datos y formato de salida.  
Complementariamente, el **Negative Prompting** añade una capa de control semántico, ayudando a **evitar contenido no deseado, mantener el enfoque y mejorar la claridad**.  

Juntas, estas técnicas son fundamentales para diseñar **prompts profesionales, consistentes y alineados con las necesidades empresariales** dentro del ecosistema de **AWS Bedrock**.
