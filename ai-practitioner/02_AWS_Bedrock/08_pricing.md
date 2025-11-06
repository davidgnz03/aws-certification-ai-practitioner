# AWS Bedrock — Pricing

## Introducción
El modelo de precios de **AWS Bedrock** está diseñado para ofrecer **flexibilidad y eficiencia de costos**, adaptándose a distintos niveles de uso, carga de trabajo y necesidades empresariales.  
El costo total depende principalmente de:
- El tipo de **modelo fundacional (FM)** utilizado.  
- La modalidad de **ejecución** (On-demand, Batch o Provisioned Throughput).  
- La cantidad de **tokens procesados** (entrada y salida).  
- Los parámetros de generación y el tamaño del modelo.

---

## Modelos de Consumo en AWS Bedrock

### 🔹 On-Demand
La modalidad **On-Demand** cobra por cada solicitud realizada al modelo.  
Ideal para cargas **interactivas, experimentales o impredecibles**.

**Características:**
- Pago por uso, sin compromiso ni capacidad reservada.  
- Escalado automático según demanda.  
- Adecuado para desarrollo, pruebas o baja concurrencia.

**Ejemplo de costo:**  
`Costo = (Tokens de entrada + Tokens de salida) × Precio por token del modelo seleccionado`

---

### 🔹 Batch Mode
La modalidad **Batch** permite procesar grandes volúmenes de texto o datos **de manera asíncrona**.  
Se usa para inferencias no interactivas, como análisis de documentos o generación de resúmenes masivos.

**Características:**
- Optimizada para **procesamiento en lote**.  
- Puede ofrecer descuentos frente al modo on-demand.  
- Ideal para tareas programadas o análisis fuera de línea.

---

### 🔹 Provisioned Throughput
El modo **Provisioned Throughput** garantiza capacidad dedicada para inferencias de alta demanda o aplicaciones de misión crítica.  
Se paga por una capacidad **reservada y predecible**, en lugar de por token.

**Características:**
- Garantiza latencia consistente y disponibilidad.  
- Ideal para cargas **constantes y de alta concurrencia**.  
- Permite **ahorros significativos** en escenarios de uso continuo.  

**Ejemplo:**
- Reservar 100 *invocations per second (IPS)* por mes para un modelo Titan o Claude.

---

## Cost Hierarchy — Model Improvement Techniques
Cada técnica para mejorar el rendimiento de los modelos tiene un costo distinto en términos de **tiempo, datos y procesamiento**.  
La siguiente escala resume su complejidad y costo relativo:

| Nivel | Técnica | Descripción | Costo relativo |
|-------|----------|--------------|----------------|
| 💲 | **Prompt Engineering** | Ajustar instrucciones, formato y ejemplos en el prompt. | Bajo |
| 💲💲 | **RAG (Retrieval-Augmented Generation)** | Combinar el modelo con una base de conocimiento externa. | Medio |
| 💲💲💲 | **Instruction-based Fine-Tuning** | Entrenar el modelo con pares prompt–respuesta específicos. | Alto |
| 💲💲💲💲 | **Domain Adaptation Fine-Tuning** | Reentrenar con datos especializados de un dominio técnico. | Muy alto |

> 💡 **Recomendación:** comenzar siempre con *Prompt Engineering* y *RAG* antes de considerar *Fine-Tuning*, ya que estas opciones son más económicas y flexibles.

---

## Estrategias de Ahorro de Costos

AWS ofrece múltiples opciones para optimizar costos al usar Bedrock:

### 🔸 On-Demand Optimization
- Ajustar la frecuencia de llamadas.  
- Cachear resultados de prompts repetidos.  
- Reducir longitud de respuestas limitando `maxTokenCount`.  

---

### 🔸 Batch Processing
- Agrupar solicitudes similares para reducir el número total de invocaciones.  
- Procesar tareas fuera del horario pico (por ejemplo, por la noche).  
- Usar S3 como entrada/salida para inferencias masivas.  

---

### 🔸 Provisioned Throughput
- Reservar capacidad cuando la demanda es **constante y predecible**.  
- Evita costos variables del modo on-demand.  
- Puede reducir el costo por token hasta en **30–50%** según la carga.

---

## Parámetros que Afectan el Costo

### 🔹 Temperature
Controla la **aleatoriedad o creatividad** de las respuestas del modelo.  
Valores más altos (por ejemplo, 0.9) generan más variabilidad, pero también pueden requerir más tokens y procesamiento.

- **Top-K:** limita cuántos tokens posibles considera el modelo en cada paso.  
- **Top-P (nucleus sampling):** selecciona tokens dentro de una probabilidad acumulada P (por ejemplo, 0.9).  

**Recomendación:** usar valores moderados (`temperature = 0.3–0.5`) para obtener resultados más consistentes y económicos.

---

### 🔹 Model Size
Los modelos más grandes (como **Claude 3 Opus** o **Titan Text Express**) ofrecen mayor capacidad de razonamiento, pero también tienen un **costo por token más alto**.  
Seleccionar el modelo adecuado según la complejidad de la tarea puede reducir costos significativamente.

**Ejemplo:**
| Modelo | Tamaño | Costo relativo | Uso recomendado |
|--------|---------|----------------|-----------------|
| Titan Text Lite | Pequeño | 💲 | Clasificación, resúmenes cortos |
| Titan Text Express | Mediano | 💲💲 | Generación general de texto |
| Claude 3 Opus | Grande | 💲💲💲 | Tareas complejas o de razonamiento avanzado |

---

### 🔹 Número de Input y Output Tokens
El costo de cada inferencia depende directamente del **número de tokens** enviados y generados.

**Ecuación general:**
```text 
Costo total = (Tokens de entrada × precio_input) + (Tokens de salida × precio_output)
```

---

**Consejos para optimizar:**
- Reducir el tamaño del contexto o prompt.  
- Evitar información redundante en cada solicitud.  
- Limitar la longitud de salida con `maxTokenCount`.  
- Reutilizar contexto mediante **session memory** o **RAG**.

---

## Comparación General de Modos de Ejecución

| Modo | Pago | Ideal para | Escalabilidad | Costo |
|------|------|-------------|----------------|--------|
| **On-Demand** | Por token | Pruebas, desarrollo, uso esporádico | Alta | 💲 |
| **Batch** | Por tarea o job | Procesamiento en lote | Alta | 💲💲 |
| **Provisioned Throughput** | Por capacidad reservada | Producción, alto tráfico | Fija y garantizada | 💲💲💲 |

---

## Conclusión
El **modelo de precios de AWS Bedrock** ofrece múltiples formas de equilibrar costo, rendimiento y disponibilidad.  
Comenzar con **On-Demand** o **Batch**, optimizar con *Prompt Engineering* y *RAG*, y escalar con **Provisioned Throughput** son las mejores prácticas para maximizar valor y minimizar gasto.  
El control sobre **tokens, parámetros de inferencia y tamaño de modelo** permite ajustar de manera precisa el costo operativo de las soluciones de IA generativa en producción.
