# SageMaker – Models and Humans

**Amazon SageMaker** integra herramientas que combinan **modelos de Machine Learning** con la **participación humana**, con el fin de mejorar la **explicabilidad**, **equidad** y **alineación** de los modelos con las preferencias humanas.

> 🧠 *SageMaker une el poder de los modelos automáticos con el juicio y la supervisión humana.*

---

## 🤖 SageMaker Clarify

**SageMaker Clarify** proporciona capacidades avanzadas para **evaluar y explicar modelos de Machine Learning**, incluyendo los **Foundation Models (FMs)**.  
Ayuda a las organizaciones a entender **cómo** y **por qué** un modelo toma decisiones, detectar **sesgos** y evaluar **factores humanos**.

### 🔍 Características Principales

- **Evaluación de Foundation Models (FMs)**  
  Analiza el rendimiento y comportamiento de modelos de gran escala (LLMs, multimodales, etc.).

- **Evaluación de factores humanos**  
  Mide aspectos como **amabilidad**, **humor**, **tono**, o **empatía** en las respuestas de modelos generativos.

- **Equipos humanos o propios**  
  Usa un **equipo administrado por AWS** o tu propio personal para la evaluación.

- **Datasets personalizables**  
  Usa **datasets preconstruidos** o **sube tus propios conjuntos de datos** para las pruebas.

- **Métricas y algoritmos integrados**  
  Incluye métricas estándar para evaluación cuantitativa y cualitativa.

- **Integrado en SageMaker Studio**  
  Totalmente accesible desde la interfaz unificada de **SageMaker Studio**.

> 💡 *SageMaker Clarify evalúa tanto la precisión técnica del modelo como su alineación con la experiencia humana.*

---

## 🧩 SageMaker Clarify – Model Explainability

### 🧠 Explicabilidad del Modelo

**Model Explainability** permite entender el razonamiento detrás de las predicciones de un modelo, lo que incrementa la **confianza**, la **transparencia** y la **capacidad de auditoría**.

### 🔩 Funcionalidades

- **Explica cómo el modelo toma decisiones.**  
  Analiza la importancia relativa de cada feature (atributo) en las predicciones.

- **Evaluación antes del despliegue.**  
  Comprende el comportamiento general del modelo antes de ponerlo en producción.

- **Depuración posterior al despliegue.**  
  Identifica causas de errores o decisiones inesperadas del modelo ya entrenado.

- **Mejora la confianza y comprensión.**  
  Especialmente útil en sectores regulados (finanzas, salud, seguros, etc.).

### 💬 Ejemplos

- “¿Por qué el modelo rechazó un préstamo para este solicitante?”  
- “¿Por qué el modelo hizo una predicción incorrecta?”

> 🧠 *Clarify Explainability transforma los modelos de ‘cajas negras’ en sistemas comprensibles y auditables.*

---

## ⚖️ SageMaker Clarify – Detect Bias (Human)

### 🚨 Detección de Sesgo

**SageMaker Clarify** permite detectar y explicar sesgos en los datos de entrada o en los resultados del modelo.

### 🔍 Capacidades

- **Detección automática de sesgo**  
  Identifica posibles desigualdades en cómo el modelo trata diferentes grupos (género, edad, ubicación, etc.).

- **Explicación de sesgo**  
  Muestra qué variables contribuyen más al sesgo detectado.

- **Métricas estadísticas integradas**  
  Usa indicadores como *Disparate Impact Ratio*, *Statistical Parity Difference* o *Equal Opportunity Difference*.

- **Interfaz visual**  
  Presenta reportes claros para auditores y científicos de datos.

> ⚖️ *Garantiza que los modelos sean éticos, imparciales y confiables.*

---

## 👥 SageMaker Ground Truth

**SageMaker Ground Truth** permite **incorporar feedback humano** en el ciclo de entrenamiento y evaluación de modelos de Machine Learning.  
Es una herramienta clave para **Reinforcement Learning from Human Feedback (RLHF)**.

### 🧩 Funciones Principales

#### 🔁 RLHF – Reinforcement Learning from Human Feedback

- Permite que los **modelos aprendan de la retroalimentación humana**.  
- Los humanos califican o corrigen las salidas del modelo.  
- Esa retroalimentación se integra como parte de la **función de recompensa (reward function)**.  
- Mejora la **alineación del modelo con las preferencias humanas** (p. ej., mayor cortesía, exactitud o empatía).  

> 💬 *El modelo aprende lo que los humanos consideran una buena respuesta.*

#### 🧠 Human Feedback for ML

Los humanos también pueden participar en:

- **Creación o evaluación de modelos.**  
- **Generación o anotación de datos** (por ejemplo, etiquetado de imágenes, clasificación de texto, transcripción).  
- **Validación de predicciones del modelo.**

#### 👩‍💻 Tipos de Revisores

- **Amazon Mechanical Turk workers** — fuerza laboral global para tareas simples.  
- **Tus propios empleados.**  
- **Proveedores externos certificados** — para requisitos de confidencialidad o compliance.

---

## 🧩 SageMaker Ground Truth Plus

**Ground Truth Plus** amplía las capacidades de etiquetado humano con un **servicio gestionado de AWS**.

### 🔩 Características

- Gestión completa de proyectos de etiquetado por AWS.  
- Equipos humanos preseleccionados y capacitados.  
- Supervisión de calidad y control de flujo de trabajo.  
- Soporte para imágenes, texto, video, audio, y datos 3D.

> 🧠 *Ground Truth Plus simplifica el etiquetado de datos a gran escala sin requerir gestión manual.*

---

## ⚙️ Feature and Capabilities (en la consola AWS)

Desde la consola de **Amazon SageMaker Studio**, puedes acceder a:

| Función | Descripción |
|----------|--------------|
| **Clarify** | Detecta sesgos y explica predicciones del modelo. |
| **Model Explainability Dashboard** | Visualiza la importancia de las variables y la trazabilidad del modelo. |
| **Bias Reports** | Reportes automáticos de equidad y balance. |
| **Ground Truth** | Plataforma para etiquetado y evaluación humana. |
| **RLHF Pipelines** | Entrenamiento iterativo con retroalimentación humana. |
| **Ground Truth Plus** | Servicio gestionado de etiquetado con equipos humanos especializados. |

---

## 💡 Beneficios Clave

- 🧠 **Explicabilidad total de los modelos.**  
- ⚖️ **Detección y mitigación de sesgos humanos y algorítmicos.**  
- 🤝 **Alineación con preferencias humanas (RLHF).**  
- 👥 **Integración fluida de revisores humanos.**  
- 🔍 **Mejor trazabilidad y cumplimiento normativo.**

---

## 🧠 En Resumen

**SageMaker Clarify** y **Ground Truth** trabajan en conjunto para crear modelos **más justos, interpretables y alineados con los valores humanos**.

| Herramienta | Propósito | Clave |
|--------------|------------|--------|
| **SageMaker Clarify** | Detectar sesgo y explicar decisiones del modelo. | Aumenta transparencia y confianza. |
| **SageMaker Ground Truth** | Incluir retroalimentación humana (RLHF) y etiquetar datos. | Mejora la calidad del entrenamiento. |
| **Ground Truth Plus** | Servicio gestionado de etiquetado de datos. | Escalabilidad y control de calidad garantizados. |

> 🤖 *SageMaker combina inteligencia artificial y juicio humano para crear modelos más precisos, éticos y confiables.*
