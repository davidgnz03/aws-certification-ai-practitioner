# SageMaker – ML Governance

**Amazon SageMaker ML Governance** proporciona un conjunto de herramientas que permiten **gestionar, auditar y supervisar modelos de Machine Learning** de manera segura, trazable y conforme a políticas corporativas o regulatorias.

> 🧠 *El gobierno del Machine Learning (ML Governance) garantiza que los modelos sean responsables, seguros, explicables y estén bajo control operativo continuo.*

---

## 🗂️ SageMaker Model Cards

**SageMaker Model Cards** son documentos estandarizados que resumen la información esencial de cada modelo de Machine Learning.

### 📋 Contenido de una Model Card

- **Información general del modelo**
  - Nombre, propietario, fecha de creación, versión, responsable técnico.  
- **Propósito e intención de uso**
  - Casos de uso esperados y limitaciones conocidas.
- **Riesgos y mitigaciones**
  - Nivel de riesgo, impacto potencial, y medidas preventivas.  
- **Detalles de entrenamiento**
  - Dataset, algoritmos, hiperparámetros, y métricas de rendimiento.
- **Evaluaciones adicionales**
  - Sesgos detectados, explicabilidad, cumplimiento normativo, etc.

> 💡 *Una Model Card es como el “manual técnico y ético” de un modelo.*

---

## 🧭 SageMaker Model Dashboard

El **Model Dashboard** es un **portal centralizado** que permite **visualizar, buscar y explorar todos los modelos** dentro de SageMaker.

### 📊 Funcionalidades Principales

- **Vista unificada de todos los modelos.**  
  Permite monitorear modelos desplegados, archivados o en prueba.

- **Seguimiento de estado y rendimiento.**  
  Consulta métricas de precisión, latencia, deriva, y uso en producción.

- **Detección de incumplimientos.**  
  Identifica modelos que violan los **umbrales definidos** en:
  - Calidad de datos  
  - Calidad de modelo  
  - Sesgo o falta de explicabilidad  

- **Acceso directo desde la consola de SageMaker.**

> 📈 *Facilita el gobierno centralizado y la observabilidad total del portafolio de modelos.*

---

## 🔍 SageMaker Model Monitor

**SageMaker Model Monitor** supervisa continuamente la calidad y el rendimiento de los modelos en producción.

### ⚙️ Capacidades Clave

- **Monitoreo continuo o programado.**  
  Puede ejecutarse en tiempo real o bajo un cronograma definido.

- **Alertas automáticas.**  
  Detecta desviaciones en datos, rendimiento o comportamiento del modelo.

- **Detección de drift.**  
  Identifica cambios en los patrones de los datos o en las predicciones (concept drift / data drift).

- **Corrección proactiva.**  
  Permite iniciar flujos de retraining cuando se detecta degradación.

### 💬 Ejemplo

> 📉 *Un modelo de préstamos comienza a aprobar solicitudes con bajo puntaje crediticio debido a cambios en los datos de entrada.  
Model Monitor detecta la desviación, genera una alerta y activa un flujo de retraining.*

> 🧠 *Model Monitor asegura que los modelos sigan siendo precisos y confiables a lo largo del tiempo.*

---

## 🏷️ SageMaker Model Registry

El **Model Registry** es un repositorio centralizado donde puedes **registrar, versionar, y gestionar modelos de Machine Learning** a lo largo de su ciclo de vida.

### 📘 Funciones Principales

- **Catalogación y versionado.**  
  Cada modelo y versión se almacena con su historial, métricas y metadatos.

- **Gestión de metadatos.**  
  Agrega información adicional: datasets usados, métricas, parámetros, propietario, etc.

- **Aprobación y control de versiones.**  
  Define estados como:  
  - *Pending approval*  
  - *Approved for deployment*  
  - *Rejected / Archived*

- **Automatización del despliegue.**  
  Permite desplegar modelos aprobados automáticamente mediante pipelines.

- **Colaboración entre equipos.**  
  Facilita compartir modelos dentro de una organización con control de acceso seguro.

> 📦 *El Model Registry es el “sistema de gestión de versiones” de tus modelos de ML.*

---

## 👥 SageMaker Role Manager

**SageMaker Role Manager** simplifica la creación y administración de **roles y permisos personalizados** según el tipo de usuario o función dentro de un equipo de ML.

### 🔧 Ejemplos de Roles

| Rol | Descripción |
|------|--------------|
| **Data Scientist** | Crea, entrena y evalúa modelos de ML. |
| **MLOps Engineer** | Automatiza despliegues y mantenimiento del pipeline. |
| **Reviewer / Auditor** | Revisa métricas, sesgos y cumplimiento normativo. |
| **Admin** | Gestiona políticas y permisos globales. |

> 🔐 *Centraliza la seguridad y reduce errores de configuración manual de IAM.*

---

## 🔄 SageMaker Pipelines

**SageMaker Pipelines** es un servicio de **automatización (CI/CD)** que gestiona el flujo completo del Machine Learning — desde la preparación de datos hasta el despliegue del modelo.

### ⚙️ Características Principales

- **Automatización total del ciclo de vida ML.**  
  Crea workflows que construyen, entrenan, evalúan y despliegan modelos.

- **Integración CI/CD nativa.**  
  Acelera el desarrollo de modelos y asegura entregas repetibles.

- **Escalabilidad.**  
  Permite manejar cientos de modelos en paralelo.

- **Iteración rápida y reproducible.**  
  Facilita la experimentación controlada y reduce errores humanos.

### 🔩 Tipos de Steps Soportados

| Step | Propósito |
|------|------------|
| **Processing** | Limpieza y transformación de datos (Feature Engineering). |
| **Training** | Entrenamiento del modelo. |
| **Tuning** | Optimización de hiperparámetros. |
| **AutoML** | Entrenamiento automático de modelos sin código. |
| **Model** | Registro o creación de un nuevo modelo en SageMaker. |
| **ClarifyCheck** | Detección de sesgo, deriva o falta de explicabilidad. |
| **QualityCheck** | Validación de calidad de datos y modelos. |

📚 **Referencia completa:**  
👉 [AWS Documentation – SageMaker Step Types](https://docs.aws.amazon.com/sagemaker/latest/dg/build-and-manage-steps.html#build-and-manage-steps-types)

---

## ⚙️ Feature and Capabilities (en la consola AWS)

Desde la consola de **Amazon SageMaker**, puedes acceder a:

| Herramienta | Función |
|--------------|----------|
| **Model Cards** | Documentar uso, riesgo, y detalles del modelo. |
| **Model Dashboard** | Vista centralizada y buscable de todos los modelos. |
| **Model Monitor** | Supervisión continua y alertas de calidad. |
| **Model Registry** | Versionado y aprobación de modelos. |
| **Role Manager** | Asignación y control de permisos personalizados. |
| **Pipelines** | Automatización CI/CD para flujos de ML. |

---

## 💡 Beneficios Clave

- 📋 **Trazabilidad completa del ciclo de vida de los modelos.**  
- ⚖️ **Cumplimiento y auditoría integrada.**  
- 🚀 **Automatización del desarrollo y despliegue (MLOps).**  
- 🧠 **Mayor control, seguridad y transparencia.**  
- 🔄 **Iteraciones rápidas y reproducibles.**

---

## 🧠 En Resumen

**SageMaker ML Governance** ofrece un ecosistema completo para administrar modelos de manera segura, ética y escalable.

| Componente | Propósito | Clave |
|-------------|------------|-------|
| **Model Cards** | Documentar propósito y riesgos del modelo. | Transparencia y cumplimiento. |
| **Model Dashboard** | Portal centralizado de monitoreo. | Observabilidad total. |
| **Model Monitor** | Supervisión continua. | Calidad y precisión constante. |
| **Model Registry** | Versionado y control de modelos. | Gobernanza centralizada. |
| **Role Manager** | Gestión de roles y permisos. | Seguridad y control de acceso. |
| **Pipelines** | Automatización CI/CD. | Eficiencia y escalabilidad. |

> 🧩 *Con SageMaker ML Governance, AWS ofrece un marco completo para garantizar que tus modelos sean rastreables, seguros, éticos y gobernados de principio a fin.*
