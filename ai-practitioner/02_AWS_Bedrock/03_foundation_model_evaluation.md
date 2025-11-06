# AWS Bedrock — Foundation Model (FM) Evaluation

## Introducción
La **evaluación de Foundation Models (FMs)** en **AWS Bedrock** es un proceso crítico para medir el rendimiento, la calidad y la utilidad práctica de un modelo, ya sea antes o después del *fine-tuning*.  
AWS permite realizar evaluaciones **automáticas y humanas**, apoyadas en métricas objetivas y datos curados, con el objetivo de garantizar que los modelos sean **precisos, éticos y alineados con los objetivos del negocio**.

---

## Tipos de Evaluación en AWS Bedrock

### 1. Automatic Evaluation
La **evaluación automática** utiliza métricas cuantitativas para comparar las respuestas del modelo con resultados de referencia (*ground truth*).  
Estas métricas se calculan mediante scripts, pipelines o servicios automáticos.

**Ventajas:**
- Escalable y reproducible.  
- Permite comparar modelos de forma objetiva.  
- Ideal para pruebas iniciales o regresiones.

---

### 2. Human Evaluation
La **evaluación humana** consiste en que expertos o evaluadores revisen las salidas del modelo según criterios como:
- Claridad, coherencia y precisión.  
- Relevancia con la consulta.  
- Tono y adecuación al contexto.  
- Ausencia de sesgos o contenido tóxico.

**Ventajas:**
- Mide la calidad subjetiva (fluidez, contexto, intención).  
- Es más representativa de la experiencia real del usuario.

**Desventajas:**
- Costosa y lenta comparada con la automática.  
- Puede tener variabilidad entre evaluadores.

---

## Componentes de una Evaluación de Modelo

| Componente | Descripción |
|-------------|-------------|
| **Curated Prompt Datasets** | Conjunto de prompts cuidadosamente seleccionados que representan tareas reales. |
| **Model to Evaluate** | El FM o modelo ajustado (*fine-tuned*) que se va a medir. |
| **Generated Answers** | Las respuestas producidas por el modelo ante los prompts. |
| **Judge Model** | Un modelo o humano evaluador que puntúa las respuestas según criterios definidos. |
| **Grading Score** | Puntuación numérica o categórica asignada a cada respuesta. |
| **Benchmark Datasets** | Conjuntos de datos estándar usados para comparar desempeño entre modelos (por ejemplo, MMLU, GLUE, etc.). |
| **Bias Score** | Indicador de posibles sesgos o comportamientos discriminatorios en las respuestas. |

---

## Métricas Automáticas de Evaluación

AWS Bedrock permite integrar diversas métricas estándar del NLP para cuantificar el rendimiento de los modelos de texto.

### 🔹 ROUGE (Recall-Oriented Understudy for Gisting Evaluation)
Evalúa la **superposición de palabras o frases** entre la respuesta generada y la respuesta esperada (*ground truth*).

- **ROUGE-N:** mide coincidencias de *n-gramas* (ROUGE-1 para unigramas, ROUGE-2 para bigramas).  
- **ROUGE-L:** mide la longitud de la *Longest Common Subsequence* (LCS), es decir, la secuencia de palabras más larga compartida entre ambas respuestas.

**Interpretación:**  
Cuanto mayor el valor de ROUGE, más similar es la respuesta del modelo a la referencia.

---

### 🔹 BLEU (Bilingual Evaluation Understudy)
Calcula la precisión de coincidencias de *n-gramas* entre la salida del modelo y la referencia.  
Es muy usada en traducción automática y generación de texto.

**Rango:** 0 a 1 (o 0–100%).  
- 1 → coincidencia perfecta.  
- 0 → sin coincidencia.  

**Limitación:** No evalúa semántica, solo coincidencia textual.

---

### 🔹 BERTScore
Compara la similitud semántica entre la respuesta generada y la de referencia, usando *embeddings* producidos por un modelo BERT o similar.

**Ventajas:**
- Mide significado, no solo palabras exactas.  
- Más robusto para respuestas equivalentes con diferente redacción.

---

### 🔹 Perplexity
Mide qué tan “sorprendido” está el modelo al generar una secuencia de texto.  
Cuanto menor sea la **perplexidad**, más seguro y coherente es el modelo en sus predicciones.  
> En inteligencia artificial y procesamiento del lenguaje natural (PLN), la perplejidad mide la precisión con la que un modelo de lenguaje predice una muestra de texto. En términos sencillos, cuantifica la "sorpresa" o incertidumbre del modelo al enfrentarse a nuevos datos.

**Interpretación:**
- Perplexity baja = modelo confiado y consistente.  
- Perplexity alta = modelo inseguro o errático.

---

## Métricas de Negocio para Evaluar un Modelo

Además de las métricas técnicas, en AWS Bedrock se recomienda evaluar el impacto **en métricas de negocio**, ya que un modelo puede ser técnicamente preciso, pero ineficiente comercialmente.

| Métrica de Negocio | Descripción |
|---------------------|-------------|
| **User Satisfaction** | Nivel de satisfacción o utilidad percibida por los usuarios. |
| **Average Revenue Per User (ARPU)** | Ingreso promedio generado por usuario que interactúa con el modelo. |
| **Cross-Domain Performance** | Capacidad del modelo de mantener calidad en múltiples dominios o temas. |
| **Conversion Rate** | Porcentaje de interacciones que llevan a una acción deseada (compra, registro, clic, etc.). |
| **Efficiency** | Medición del costo, latencia y uso de recursos frente a los beneficios obtenidos. |

---

## Métricas y Datasets de Evaluación Complementaria

AWS también permite evaluar modelos desde una perspectiva ética y de calidad contextual.

| Métrica | Descripción |
|----------|--------------|
| **Toxicity** | Evalúa si el modelo genera contenido ofensivo, sesgado o dañino. |
| **Accuracy** | Mide la exactitud objetiva de las respuestas frente a la verdad conocida. |
| **Robustness** | Evalúa cómo responde el modelo a datos ruidosos, entradas adversarias o variaciones de formato. |

**Ejemplo de dataset para estas métricas:**
- **RealToxicityPrompts** → Para evaluar toxicidad.  
- **TruthfulQA** → Para medir precisión y veracidad.  
- **AdversarialQA** → Para robustez y resistencia a prompts engañosos.

---

## Proceso General de Evaluación en AWS Bedrock
1. **Definir el objetivo de evaluación** (calidad, sesgo, negocio, etc.).  
2. **Seleccionar dataset de prompts representativo.**  
3. **Ejecutar inferencias** en el modelo evaluado.  
4. **Recolectar respuestas generadas.**  
5. **Aplicar métricas automáticas o evaluación humana.**  
6. **Analizar resultados y comparar entre modelos.**  
7. **Ajustar (fine-tune o prompt-tune)** según los hallazgos.  

---

## Resumen
- AWS Bedrock permite evaluar Foundation Models tanto de forma **automática** como **manual**.  
- Las métricas técnicas (ROUGE, BLEU, BERTScore, Perplexity) miden calidad de texto.  
- Las métricas de negocio (Satisfacción, Conversión, ARPU) miden impacto real.  
- Los **datasets de referencia** y el **bias score** ayudan a garantizar modelos éticos y robustos.  
- Una evaluación completa debe combinar **métricas cuantitativas**, **cualitativas** y **de negocio** para obtener una visión integral del rendimiento del modelo.
