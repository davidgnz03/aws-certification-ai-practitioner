# Prompt Engineering Techniques

## Introducción
Las **Prompt Engineering Techniques** son estrategias utilizadas para **mejorar la interacción entre el usuario y los Foundation Models (FMs)**, orientando al modelo hacia respuestas más precisas, relevantes y estructuradas.  
Cada técnica tiene diferentes niveles de complejidad y control, y puede combinarse para obtener mejores resultados dentro de **AWS Bedrock**.

A continuación se detallan las principales técnicas: **Zero-Shot**, **Few-Shot**, **Chain-of-Thought** y **Retrieval-Augmented Generation (RAG)**.

---

## 🟦 Zero-Shot Prompting

### Descripción
En el **Zero-Shot Prompting**, se presenta una tarea al modelo **sin proporcionar ejemplos previos o entrenamiento específico**.  
El modelo se basa completamente en su **conocimiento general preentrenado** para generar la respuesta.

### Características
- No se ofrecen ejemplos ni contexto adicional.  
- El modelo interpreta la tarea basándose en lo que ya sabe.  
- Ideal para tareas simples o bien conocidas por el modelo.

### Ejemplo
> Prompt: “Traducir al francés: The weather is nice today.”  
→ “Le temps est agréable aujourd'hui.”  


### Cuándo usarlo
- Cuando se busca una respuesta rápida o general.  
- Cuando el modelo ya domina el tipo de tarea.  
- En casos donde la precisión no es crítica.  

> 💡 *Cuanto más grande y capaz sea el Foundation Model (FM), mejores serán los resultados en modo Zero-Shot.*

---

## 🟨 Few-Shot Prompting

### Descripción
El **Few-Shot Prompting** consiste en **proporcionar algunos ejemplos de entrada y salida** dentro del mismo prompt para guiar al modelo.  
De esta forma, el modelo aprende el **patrón de la tarea** durante la inferencia sin necesidad de un *fine-tuning* formal.

### Características
- Se ofrecen **pocos ejemplos** (“shots”) como referencia.  
- El modelo generaliza a partir de esos ejemplos.  
- Si se usa **solo un ejemplo**, se denomina *One-Shot* o *Single-Shot Prompting*.

### Ejemplo

**Prompt:**
```text
Ejemplo 1:  
    Entrada: “Sol”  
    Salida: “Una estrella que proporciona luz y calor al    sistema solar.”    
Ejemplo 2:  
    Entrada: “Luna”  
    Salida: 
```
**Resultado esperado:**
> “Un satélite natural que orbita alrededor de la Tierra.”

### Cuándo usarlo
- Cuando se desea controlar el **estilo o formato** de la respuesta.  
- En tareas donde el modelo necesita **aprender un patrón específico**.  
- En casos donde no se dispone de suficiente información para un *fine-tuning*.

---

## 🟧 Chain-of-Thought Prompting

### Descripción
El **Chain-of-Thought Prompting (CoT)** divide una tarea compleja en una **secuencia de pasos de razonamiento**, ayudando al modelo a **estructurar su pensamiento y mantener coherencia lógica**.  
Al incluir frases como *“piensa paso a paso”*, el modelo produce respuestas más explicativas y fundamentadas.

### Características
- Fomenta razonamiento lógico y estructurado.  
- Mejora la exactitud en tareas que requieren múltiples pasos.  
- Puede combinarse con **Zero-Shot** o **Few-Shot**.

### Ejemplo
**Prompt:**
>Pregunta: Si un tren viaja a 80 km/h y tarda 2 horas en llegar, ¿cuál es la distancia recorrida?  Piensa paso a paso.  


**Razonamiento del modelo:**
1. La velocidad es 80 km/h.  
2. El tiempo es 2 horas.  
3. Distancia = velocidad × tiempo = 80 × 2 = 160.  

**Respuesta final:**
> “El tren recorrió 160 km.”

### Cuándo usarlo
- Para problemas matemáticos o de lógica.  
- En escenarios de análisis o toma de decisiones.  
- En tareas que requieren una explicación intermedia antes de la respuesta final.

---

## 🟥 Retrieval-Augmented Generation (RAG)

### Descripción
El **Retrieval-Augmented Generation (RAG)** combina la capacidad generativa del modelo con **fuentes de información externas** (bases de conocimiento, documentos, bases vectoriales, etc.).  
Esto permite generar **respuestas más precisas, actualizadas y contextualizadas**.

### Características
- El prompt se **amplía dinámicamente** con información relevante recuperada desde una **knowledge base** o **vector database**.  
- Mejora la exactitud en temas especializados o recientes.  
- Reduce las “alucinaciones” del modelo al proveer evidencia factual.

### Ejemplo

**Prompt:**
```text
Usa los siguientes documentos sobre AWS Bedrock para explicar sus beneficios principales.  

[Documentos recuperados automáticamente]  

Pregunta: ¿Por qué AWS Bedrock es útil para construir aplicaciones de IA generativa?  
```

**Resultado esperado:**
> “AWS Bedrock permite acceder a múltiples modelos fundacionales, facilita la integración de GenAI con otros servicios AWS y ofrece seguridad empresarial mediante controles de acceso y monitoreo integrados.”

### Cuándo usarlo
- En tareas que requieren información actualizada.  
- Para responder preguntas específicas sobre datos privados o empresariales.  
- En aplicaciones de IA empresarial que combinan GenAI con bases de conocimiento internas.

---

## Comparación de Técnicas

| Técnica | Ejemplos incluidos | Nivel de control | Requiere datos externos | Ideal para |
|----------|-------------------|------------------|--------------------------|-------------|
| **Zero-Shot** | ❌ No | Bajo | ❌ No | Tareas simples y conocidas |
| **Few-Shot** | ✅ Algunos | Medio | ❌ No | Estandarizar formato de salida |
| **Chain-of-Thought** | ✅ Opcional | Alto | ❌ No | Razonamiento lógico paso a paso |
| **RAG** | ✅ Dinámicos | Muy alto | ✅ Sí | Respuestas basadas en conocimiento actualizado |

---

## Conclusión
El dominio de las **Prompt Engineering Techniques** permite adaptar el comportamiento del modelo según la necesidad:  
- **Zero-Shot** para rapidez,  
- **Few-Shot** para consistencia,  
- **Chain-of-Thought** para razonamiento, y  
- **RAG** para conocimiento enriquecido.  

En **AWS Bedrock**, combinar estas técnicas con parámetros de rendimiento (temperature, top-p, top-k) y *fine-tuning* adecuado ofrece una base sólida para **construir soluciones de IA generativa precisas, confiables y escalables**.
