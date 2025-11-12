# 🧾 AWS Config  
## Auditing, Compliance & Resource Configuration Tracking

---

### 🧱 Overview

**AWS Config** es un servicio totalmente administrado que permite **auditar, monitorear y evaluar la configuración de los recursos de AWS**.  
Registra continuamente los cambios y configuraciones para ayudarte a mantener el cumplimiento normativo y de seguridad.

> 🔍 *AWS Config responde la pregunta: “¿Qué cambió, cuándo, y quién lo cambió?”*

---

## 🎯 Core Capabilities

| **Funcionalidad** | **Descripción** |
|--------------------|-----------------|
| **Auditing** | Supervisa si tus recursos cumplen con las políticas internas, normativas o estándares (como PCI-DSS, HIPAA, GDPR). |
| **Compliance Recording** | Detecta configuraciones no conformes y genera reportes de cumplimiento en tiempo real. |
| **Configuration Recording** | Registra automáticamente los cambios de configuración de los recursos AWS. |
| **Historical Tracking** | Mantiene un historial completo de cómo han evolucionado los recursos a lo largo del tiempo. |
| **Change Notifications** | Envía notificaciones a **Amazon SNS** cada vez que ocurre un cambio en un recurso. |

> 🧩 *AWS Config te permite visualizar y entender el estado y evolución de tus recursos en un solo lugar.*

---

## 📦 Example Questions AWS Config Can Answer

AWS Config ayuda a responder preguntas críticas de seguridad y cumplimiento:

- ❓ ¿Hay **acceso SSH no restringido** en mis *Security Groups*?  
- ❓ ¿Alguno de mis **buckets S3** tiene acceso público?  
- ❓ ¿Cómo ha cambiado la **configuración de mi Application Load Balancer (ALB)** con el tiempo?  
- ❓ ¿Mis recursos cumplen con las políticas definidas por mi organización?  
- ❓ ¿Qué usuarios o roles realizaron cambios específicos? *(vía integración con CloudTrail)*  

> 📊 *Puedes visualizar la evolución de configuraciones o exportar los datos para análisis con Amazon Athena.*

---

## ☁️ Key Integrations

| **Servicio AWS** | **Integración con Config** |
|------------------|----------------------------|
| **Amazon S3** | Guarda los registros de configuración y compliance. |
| **AWS CloudTrail** | Asocia los cambios detectados con eventos de API y usuarios responsables. |
| **Amazon SNS** | Envía alertas automáticas sobre cambios o violaciones de cumplimiento. |
| **Amazon Athena** | Analiza los datos de configuración almacenados en S3 mediante consultas SQL. |
| **AWS Organizations** | Permite agrupar y consolidar datos de Config entre **múltiples cuentas y regiones**. |

---

## 🌍 Regional Scope

- **AWS Config es un servicio por región**, pero:
  - Puede **agregarse** a través de múltiples regiones y cuentas.
  - Permite una **vista centralizada de cumplimiento** mediante **Config Aggregators**.
  - Ideal para grandes organizaciones o entornos multi-cuenta (AWS Organizations).

---

## 🧩 AWS Config Resource View

Cada recurso monitoreado tiene una **vista de historial detallada**:

| **Vista** | **Descripción** |
|------------|-----------------|
| **Compliance Timeline** | Muestra el estado de cumplimiento del recurso a lo largo del tiempo. |
| **Configuration Timeline** | Permite revisar cómo ha cambiado la configuración (por ejemplo, nuevas reglas, etiquetas, permisos). |
| **CloudTrail Integration** | Si está habilitado, muestra las llamadas API asociadas a cada cambio detectado. |

> 📅 *Esto permite realizar auditorías forenses o reconstruir el estado exacto de tu infraestructura en un punto del tiempo.*

---

## 🧠 How It Works

1. **Enable AWS Config** → selecciona los recursos que deseas monitorear.  
2. **Record Configurations** → AWS Config toma “snapshots” periódicos de las configuraciones.  
3. **Evaluate Compliance** → las compara con **Config Rules** (reglas predefinidas o personalizadas).  
4. **Alert & Store** → envía alertas a SNS y almacena los datos en **Amazon S3**.  
5. **Analyze & Audit** → usa **AWS Config Console** o **Athena** para análisis detallados.

---

## ⚙️ Example Use Cases

| **Caso de Uso** | **Descripción** |
|------------------|-----------------|
| **Security Auditing** | Detectar configuraciones inseguras (por ejemplo, puertos abiertos en SG). |
| **Compliance Monitoring** | Verificar que los recursos cumplan con políticas internas o regulatorias. |
| **Change Management** | Rastrear quién cambió qué configuración y cuándo. |
| **Operational Troubleshooting** | Comparar configuraciones históricas para diagnosticar problemas. |

---

## 💰 Pricing Overview

- **Pago por recurso grabado y evaluado.**
- Costos adicionales por almacenamiento en **S3** o consultas con **Athena**.
- Escalabilidad automática según el número de recursos monitoreados.

> 💡 *AWS Config incluye una capa gratuita de hasta 10,000 configuraciones grabadas por mes.*

---

## 🧱 Key Takeaways

- **AWS Config** = Auditoría + Cumplimiento + Historial de configuración.  
- Responde *quién, cuándo y cómo* cambió la infraestructura.  
- Permite **automatizar alertas y reportes** de cumplimiento.  
- **Integración profunda con CloudTrail, SNS, S3 y Athena.**  
- Ideal para **seguridad, gobernanza y auditorías multi-cuenta.**

> 🛡️ *AWS Config convierte la visibilidad en control y el control en cumplimiento continuo.*
