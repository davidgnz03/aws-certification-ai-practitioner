# ML Algorithms — Unsupervised Learning

## Introducción

**Unsupervised Learning (Aprendizaje No Supervisado)** es una técnica de Machine Learning en la que el modelo **no dispone de etiquetas de salida (labels)**.  
El objetivo es **descubrir patrones ocultos, estructuras o relaciones** dentro del conjunto de datos sin una guía explícita.

> 💡 *El modelo “aprende por sí mismo” a encontrar organización y similitudes dentro de los datos.*

A diferencia del aprendizaje supervisado, aquí **no se le dice al modelo qué buscar**, solo se le proporcionan los datos, y el modelo identifica **grupos, asociaciones o anomalías** basándose en similitudes o dependencias.

---

## Objetivo Principal

- Identificar **patrones inherentes** en los datos.  
- Descubrir **relaciones y dependencias ocultas**.  
- Dividir los datos en **grupos o categorías** que compartan características similares.  

Aunque el modelo crea las agrupaciones automáticamente, **los humanos interpretan y asignan significado a los grupos resultantes** (por ejemplo, “clientes frecuentes”, “usuarios de alto riesgo”, etc.).

---

## Técnicas Comunes en Unsupervised Learning

Las tres técnicas más utilizadas son:

1. **Clustering (Agrupamiento)**  
2. **Association Rule Learning (Aprendizaje de Reglas de Asociación)**  
3. **Anomaly Detection (Detección de Anomalías)**  

---

### 🧩 **1. Clustering (Agrupamiento)**

**Definición:**  
Técnica utilizada para **agrupar puntos de datos similares** en clústeres basándose en sus características o distancia en el espacio de atributos.  

El objetivo es que **los datos dentro de un mismo grupo sean muy similares entre sí** y **diferentes de los de otros grupos**.

#### Ejemplos de uso:
- Segmentación de clientes (por comportamiento o gasto).  
- Marketing dirigido (identificación de audiencias específicas).  
- Sistemas de recomendación (agrupando usuarios o productos).  

#### Algoritmos populares:
- **K-Means Clustering:** particiona los datos en *k* grupos según distancia media.  
- **Hierarchical Clustering:** construye jerarquías de grupos (dendrogramas).  
- **DBSCAN:** agrupa puntos cercanos basándose en densidad, detectando además anomalías.

#### Ejemplo:
Un supermercado podría usar clustering para identificar distintos tipos de compradores:
- Grupo 1: compradores frecuentes de bajo gasto.  
- Grupo 2: compradores ocasionales de alto gasto.  
- Grupo 3: compradores por temporada.

> 🧠 *El modelo forma los grupos, pero los humanos interpretan qué significa cada grupo.*

---

### 🔗 **2. Association Rule Learning (Reglas de Asociación)**

**Definición:**  
Método que encuentra **relaciones y dependencias entre ítems o atributos** dentro de grandes conjuntos de datos.  
Identifica patrones del tipo **“si X ocurre, entonces Y también ocurre”** (reglas *if-then*), sin requerir datos etiquetados.

#### Ejemplo:
- “Si un cliente compra pan 🍞 y mantequilla 🧈, probablemente también compre leche 🥛.”  
- Muy usado en **análisis de cestas de compra (Market Basket Analysis)**.

#### Algoritmos comunes:
- **Apriori Algorithm**  
- **Eclat Algorithm**  

#### Métricas importantes:
- **Support:** frecuencia del conjunto de ítems en el dataset.  
- **Confidence:** probabilidad de que Y ocurra dado que X ocurre.  
- **Lift:** qué tanto la ocurrencia de X incrementa la probabilidad de Y.

#### Casos de uso:
- Recomendaciones de productos.  
- Optimización de inventarios.  
- Análisis de comportamiento del consumidor.

---

### ⚠️ **3. Anomaly Detection (Detección de Anomalías)**

**Definición:**  
Identificación de **puntos de datos inusuales o comportamientos atípicos** dentro de un dataset, sin requerir ejemplos previos de qué es “normal” o “anómalo”.

#### Ejemplo:
- Detectar transacciones bancarias fraudulentas.  
- Identificar fallos en sensores IoT.  
- Monitorizar ciberataques o accesos sospechosos.

#### Características:
- No requiere etiquetas predefinidas.  
- Usa **métricas de distancia o densidad** para encontrar outliers.  
- Se enfoca en detectar observaciones que **no encajan** con el patrón general.

#### Algoritmos comunes:
- **Isolation Forest**  
- **Local Outlier Factor (LOF)**  
- **One-Class SVM**

---

## 🧠 Feature Engineering en Unsupervised Learning

Aunque el modelo aprende sin etiquetas, una **buena ingeniería de características** puede **mejorar significativamente la calidad del agrupamiento o detección**.

Ejemplos:
- Escalamiento de variables (normalización, estandarización).  
- Reducción de dimensionalidad con **PCA (Principal Component Analysis)**.  
- Creación de variables derivadas relevantes para el contexto del negocio.

> 🧩 Cuanto mejores sean las características, más “coherentes” serán las agrupaciones que encuentre el modelo.

---

## 🧬 Semi-Supervised Learning (Aprendizaje Semi-Supervisado)

### Concepto

El **aprendizaje semi-supervisado** combina lo mejor de ambos mundos:  
usa **una pequeña cantidad de datos etiquetados** junto con **una gran cantidad de datos sin etiquetar** para entrenar el modelo.

### Proceso:
1. Se entrena un modelo inicial con los pocos datos etiquetados disponibles.  
2. El modelo genera **pseudo-etiquetas** para los datos no etiquetados.  
3. Se reentrena el modelo con la combinación de ambos conjuntos.  

Este proceso se llama **pseudo-labeling** y permite aprovechar grandes volúmenes de datos sin etiquetar.

### Beneficios:
- Reduce el costo y esfuerzo de etiquetar grandes datasets.  
- Mejora la precisión del modelo en comparación con el aprendizaje no supervisado puro.  
- Ideal cuando el etiquetado manual es costoso (por ejemplo, imágenes médicas).

### Ejemplo:
Un sistema de reconocimiento facial puede entrenarse con unas pocas imágenes etiquetadas de personas conocidas, y luego usar autoetiquetado para mejorar su capacidad con miles de imágenes sin etiquetas.

---

## Resumen General

| Técnica | Descripción | Ejemplo de Uso | Tipo de Datos |
|----------|--------------|----------------|----------------|
| **Clustering** | Agrupa datos similares basándose en características compartidas. | Segmentación de clientes, marketing dirigido. | Numéricos, categóricos |
| **Association Rule Learning** | Encuentra relaciones tipo “si X, entonces Y”. | Análisis de compras, recomendaciones. | Transaccionales |
| **Anomaly Detection** | Identifica comportamientos o puntos fuera de lo normal. | Detección de fraude, mantenimiento predictivo. | Numéricos, temporales |
| **Semi-Supervised Learning** | Usa pocos datos etiquetados + muchos sin etiquetar para mejorar resultados. | Clasificación de imágenes, NLP, visión por computadora. | Mixto |

---

## Conclusión

El **aprendizaje no supervisado** permite descubrir patrones ocultos y relaciones sin necesidad de etiquetas.  
Es esencial en tareas exploratorias y de descubrimiento de conocimiento.

> 🔍 “El modelo aprende sin que le digas qué buscar, pero tú debes interpretar lo que encuentra.”

Y cuando combinamos un poco de supervisión con grandes volúmenes de datos no etiquetados (semi-supervised learning),  
> 💡 *podemos alcanzar resultados potentes con menor esfuerzo de etiquetado.*
