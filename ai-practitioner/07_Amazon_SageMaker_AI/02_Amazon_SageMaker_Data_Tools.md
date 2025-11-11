# SageMaker – Data Tools

**Amazon SageMaker** incluye un conjunto de herramientas diseñadas para **preparar, transformar y gestionar datos** antes del entrenamiento de modelos de Machine Learning.  
Estas herramientas permiten optimizar la calidad de los datos, automatizar la **ingeniería de características (Feature Engineering)** y mantener la consistencia de los datos usados en entrenamiento e inferencia.

> 📊 *Los datos limpios, transformados y bien gestionados son la base de cualquier modelo de Machine Learning exitoso.*

---

## 🧰 SageMaker Data Wrangler

**SageMaker Data Wrangler** simplifica y acelera el proceso de **preparación de datos tabulares e imágenes** para Machine Learning, todo desde una única interfaz visual.

### 🔩 Características Principales

- **Preparación de datos tabulares e imágenes**  
  Limpieza, transformación y enriquecimiento de datasets.
  
- **Feature Engineering**  
  Creación de nuevas variables a partir de las existentes (p. ej., edad a partir de fecha de nacimiento).

- **Interfaz unificada**  
  Permite realizar selección, limpieza, exploración, visualización y procesamiento de datos.

- **Soporte SQL nativo**  
  Posibilidad de realizar consultas SQL directamente sobre los datos.

- **Herramienta de Calidad de Datos (Data Quality Tool)**  
  Detecta valores nulos, outliers o inconsistencias automáticamente.

> 💡 *Reduce horas de trabajo manual en limpieza de datos a solo minutos.*

---

### 🔄 Flujo de Trabajo en Data Wrangler
```
Import Data → Preview Data → Visualize → Transform → Quick Model → Export Data Flow
```


| Etapa | Descripción |
|--------|--------------|
| **Import Data** | Carga de datos desde Amazon S3, Redshift, Athena, Snowflake o bases SQL. |
| **Preview Data** | Revisión de estructura y formato de los datos. |
| **Visualize** | Gráficas interactivas para entender distribución, correlaciones, outliers. |
| **Transform** | Aplicación de transformaciones o creación de nuevas características. |
| **Quick Model** | Evaluación rápida del impacto de las transformaciones en la predicción. |
| **Export Data Flow** | Exporta el flujo de preparación hacia SageMaker Pipelines o Feature Store. |

> 🧠 *Data Wrangler integra visualización, limpieza y transformación sin necesidad de código complejo.*

---

## 🧮 ¿Qué son las Features (Características) en Machine Learning?

Las **features** son los **atributos o variables de entrada** que un modelo de Machine Learning utiliza durante su entrenamiento y para realizar predicciones (inferencia).

### 🧠 Concepto Clave

- Son las **columnas relevantes del dataset** que describen el fenómeno que queremos modelar.  
- Cada feature debe ser **relevante, representativa y de alta calidad**.  
- La **ingeniería de features (Feature Engineering)** transforma los datos brutos en variables útiles para el modelo.

### 🎧 Ejemplo

**Dataset de música:**
- Features posibles: calificación de la canción, duración de escucha, edad del oyente, género musical.

> 📈 *Cuanto mejores sean las features, más preciso será el modelo.*

---

## 🧠 Ejemplo de Feature Engineering

### Antes de la Ingeniería de Características

| **Customer_ID** | **Name** | **BirthDate** | **Purchase_Amount** |
|-----------------|----------|----------------|---------------------|
| 1 | Alice | 15-05-1993 | $200 |
| 2 | Bob   | 22-08-1978 | $300 |

### Después de la Ingeniería de Características

| **Customer_ID** | **Name** | **Age** | **Purchase_Amount** |
|-----------------|----------|----------|---------------------|
| 1 | Alice | 30 | $200 |
| 2 | Bob   | 45 | $300 |

> 🧩 *La variable “BirthDate” fue transformada en “Age”, una feature más útil para el modelo.*

---

## 🗄️ SageMaker Feature Store

**SageMaker Feature Store** es un repositorio centralizado y gestionado para almacenar, versionar y compartir **features** entre equipos y modelos de Machine Learning.

### 🔩 Características Clave

- **Ingesta de datos desde múltiples fuentes**  
  Amazon S3, Redshift, Data Wrangler, bases de datos externas, etc.

- **Transformaciones internas**  
  Define cómo los datos brutos se convierten en features directamente dentro del Feature Store.

- **Integración con Data Wrangler**  
  Puedes publicar features directamente desde **Data Wrangler** hacia **Feature Store**.

- **Descubrimiento e indexación**  
  Todas las features son **buscables y reutilizables** dentro de **SageMaker Studio**.

- **Versionado y consistencia**  
  Garantiza que las mismas features usadas en entrenamiento se apliquen en inferencia.

> 🧠 *Evita la duplicación y asegura coherencia en las predicciones de tus modelos.*

---

## ⚙️ Feature and Capabilities (en la consola de AWS)

Desde la consola de **Amazon SageMaker**, puedes:

| Función | Descripción |
|----------|-------------|
| **Data Wrangler** | Cargar, limpiar y transformar datos de múltiples fuentes. |
| **Visualize Data** | Crear gráficos interactivos para análisis exploratorio. |
| **Create and Export Flows** | Guardar flujos de preparación y aplicarlos a nuevos datasets. |
| **Publish to Feature Store** | Exportar features transformadas directamente al repositorio central. |
| **Data Quality Reports** | Generar reportes automáticos de calidad y consistencia. |
| **Integration with Pipelines** | Conectar los flujos de datos a pipelines de entrenamiento en SageMaker. |

---

## 💡 Beneficios Clave

- 🧩 **Preparación y transformación de datos centralizada.**  
- 📈 **Ingeniería de características simplificada.**  
- 🔄 **Reutilización de features entre modelos.**  
- 🔍 **Detección automática de errores y datos inconsistentes.**  
- ⚙️ **Integración directa con SageMaker Studio, Pipelines y Feature Store.**

---

## 🧠 En Resumen

**SageMaker Data Tools** permite preparar y gestionar datos de forma eficiente para Machine Learning:

| Herramienta | Propósito | Clave |
|--------------|------------|--------|
| **Data Wrangler** | Limpieza y transformación visual de datos. | Simplifica la preparación de datos tabulares e imágenes. |
| **Feature Store** | Repositorio centralizado de features. | Asegura consistencia y reutilización entre modelos. |

> ⚙️ *Con Data Wrangler y Feature Store, AWS automatiza la parte más crítica y laboriosa del Machine Learning: la gestión y preparación de datos.*
