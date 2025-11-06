# Prompt Performance Optimization

## Introducción
La **optimización del rendimiento de los prompts** (*Prompt Performance Optimization*) se refiere a los ajustes finos que pueden realizarse para **controlar el comportamiento y la calidad de las respuestas** de un modelo fundacional (FM) en **AWS Bedrock**.  

Aunque el contenido del *prompt* es esencial, los **parámetros de inferencia** determinan cómo el modelo genera sus respuestas — influenciando el grado de creatividad, coherencia, diversidad y longitud del texto producido.

---

## 1. System Prompts

Los **System Prompts** son instrucciones ocultas o predefinidas que **establecen el comportamiento general del modelo** antes de procesar los prompts del usuario.  

Estos sirven para:
- Definir el **rol o personalidad base** del modelo (por ejemplo, “Eres un asistente técnico formal y preciso”).  
- Controlar el **tono, estilo o nivel de detalle** de las respuestas.  
- Garantizar que el modelo siga ciertas **políticas o guías de comportamiento**.  

> En AWS Bedrock, los *system prompts* suelen usarse en combinación con **Guardrails** para mantener consistencia y control en entornos empresariales.

---

## 2. Randomness and Diversity

Los modelos generativos no producen siempre las mismas respuestas.  
La **aleatoriedad y diversidad** de las salidas se controla principalmente mediante tres parámetros clave:

### 🔹 Temperature (0 a 1)

La **temperature** controla el **grado de creatividad y variación** en la generación de texto.

| Valor | Descripción | Comportamiento |
|--------|--------------|----------------|
| **Bajo (ej. 0.2)** | Conservador | Respuestas más predecibles, centradas en las palabras más probables. Ideal para tareas analíticas, resúmenes o documentación técnica. |
| **Medio (ej. 0.5–0.7)** | Balanceado | Buen equilibrio entre creatividad y coherencia. Recomendado para chatbots o explicaciones narrativas. |
| **Alto (ej. 1.0)** | Creativo | Respuestas más diversas, originales e impredecibles, aunque pueden ser menos coherentes. Útil en brainstorming o generación de contenido creativo. |

**Ejemplo práctico:**

**Prompt:**
>"Describe AWS Bedrock en una frase."  
Temperature = 0.2 → “AWS Bedrock es un servicio de AWS para usar modelos de IA generativa.”  
Temperature = 1.0 → “AWS Bedrock es el puente entre la imaginación humana y el poder de la IA en la nube.”  


---

### 🔹 Top P (Nucleus Sampling)

El parámetro **Top-P** (de 0 a 1) define la **probabilidad acumulativa** de las palabras que el modelo considerará al generar texto.  
En lugar de fijarse solo en las palabras más probables, el modelo selecciona entre las que suman una probabilidad total igual a *P*.

| Valor | Descripción | Resultado |
|--------|--------------|-----------|
| **Bajo (ej. 0.25)** | Considera solo el 25% de las palabras más probables. | Respuestas más coherentes y controladas. |
| **Alto (ej. 0.95–0.99)** | Considera una gama amplia de palabras posibles. | Respuestas más variadas y creativas. |

**Consejo:** *Top-P* puede combinarse con *temperature* para equilibrar creatividad y coherencia.  

---

### 🔹 Top K

**Top-K** limita el número máximo de palabras candidatas que el modelo considera en cada paso de generación.

| Valor | Descripción | Resultado |
|--------|--------------|-----------|
| **Bajo (ej. 10)** | El modelo elige entre las 10 palabras más probables. | Respuestas más consistentes y coherentes. |
| **Alto (ej. 500)** | El modelo puede elegir entre muchas palabras posibles. | Respuestas más creativas, diversas y menos predecibles. |

**Ejemplo:**
> Top-K = 10 → Texto más técnico, directo y preciso.  
Top-K = 500 → Texto más libre, narrativo y expresivo.


---

## 3. Length — Maximum Length of the Answer

El parámetro **length** o **maxTokens** define el número máximo de tokens que el modelo puede generar en la respuesta.

- **Tokens = palabras + fragmentos de palabras + espacios.**
- Un límite muy bajo puede cortar respuestas importantes.  
- Un límite demasiado alto puede aumentar costos y tiempos de inferencia.

**Recomendación:**
- Establece longitudes máximas adaptadas al caso de uso:  
  - 200–300 tokens → Respuestas cortas o sumarios.  
  - 800–1,500 tokens → Explicaciones detalladas o generación de contenido.  
  - >2,000 tokens → Documentos extensos o reportes.

---

## 4. Stop Sequences

Las **Stop Sequences** son tokens o frases que indican al modelo **cuándo debe detener la generación de texto**.  
Son útiles para evitar que el modelo produzca texto innecesario o divague más allá del formato deseado.

**Ejemplo:**
> Stop sequence: ["###"]  
Prompt: "Describe AWS Bedrock. ###"  
→ El modelo se detendrá al generar el token “###”.  


**Usos comunes:**
- Controlar límites en respuestas conversacionales.  
- Evitar loops o continuaciones no deseadas.  
- Delimitar múltiples salidas en una misma sesión.

---

## Resumen de Parámetros Clave

| Parámetro | Rango | Controla | Bajo Valor | Alto Valor |
|------------|--------|-----------|-------------|-------------|
| **Temperature** | 0–1 | Creatividad y variación | Coherencia y repetición | Diversidad y creatividad |
| **Top-P** | 0–1 | Probabilidad acumulada de selección de palabras | Respuestas centradas | Respuestas amplias y variadas |
| **Top-K** | 1–∞ | Número de palabras candidatas | Controlado, técnico | Creativo, menos predecible |
| **Max Length** | >0 | Tamaño máximo de respuesta | Texto corto | Texto largo |
| **Stop Sequences** | Tokens definidos | Límite de generación | Control de fin | Sin límite explícito |

---

## Conclusión
La **optimización del rendimiento de los prompts** en **AWS Bedrock** implica ajustar cuidadosamente los parámetros de inferencia para lograr el equilibrio deseado entre **creatividad, coherencia, costo y longitud**.  
Controlar variables como **temperature**, **top-p**, **top-k** y **stop sequences** permite crear experiencias conversacionales más naturales y alineadas con el propósito de cada aplicación de **IA generativa**.
