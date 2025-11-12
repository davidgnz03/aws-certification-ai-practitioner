# 🧾 AWS CloudTrail  
## Governance, Compliance & Auditing for Your AWS Account

---

### 🧱 Overview

**AWS CloudTrail** es un servicio que proporciona **gobernanza, cumplimiento y auditoría** para las actividades realizadas dentro de tu cuenta de AWS.  
Registra todos los **eventos y llamadas a la API (API calls)** que ocurren, permitiéndote rastrear quién hizo qué, desde dónde y cuándo.

> 🕵️ *CloudTrail es la “caja negra” de tu cuenta AWS: todo lo que sucede, queda registrado.*

---

## ⚙️ Core Capabilities

| **Funcionalidad** | **Descripción** |
|--------------------|-----------------|
| **Activity Tracking** | Registra todas las acciones realizadas por usuarios, roles o servicios de AWS. |
| **Audit Trail** | Proporciona un historial detallado de los eventos que se ejecutan en tu cuenta. |
| **Compliance** | Facilita la auditoría y el cumplimiento con normativas como ISO, SOC, PCI DSS y GDPR. |
| **Governance** | Permite supervisar cambios en los recursos, detectar accesos indebidos y mantener control. |
| **Security Forensics** | Ayuda a investigar incidentes de seguridad o eliminación de recursos sospechosos. |

> 🧩 *CloudTrail está habilitado por defecto en todas las cuentas AWS.*

---

## 🧠 What CloudTrail Records

CloudTrail registra **eventos y llamadas API** generados por:

- 🖥️ **AWS Management Console**  
- 🧑‍💻 **AWS SDKs**  
- ⚙️ **AWS Command Line Interface (CLI)**  
- 🧩 **Servicios AWS internos** (por ejemplo, acciones automáticas de Lambda, EC2, IAM, etc.)

Cada evento incluye información como:

- **Quién** realizó la acción (usuario, rol, servicio).  
- **Qué** acción se realizó (por ejemplo, `DeleteBucket`, `RunInstances`).  
- **Cuándo** ocurrió el evento (timestamp).  
- **Dónde** se originó (dirección IP, región).  
- **Resultado** de la operación (éxito o error).

> 📜 *Estos logs son esenciales para auditorías, análisis forense y monitoreo continuo.*

---

## ☁️ Integration and Storage

| **Destino** | **Uso Principal** |
|--------------|------------------|
| **Amazon S3** | Almacenamiento duradero y centralizado de logs históricos. |
| **Amazon CloudWatch Logs** | Monitoreo y alertas en tiempo real sobre eventos específicos. |
| **AWS Athena** | Consulta de logs mediante SQL para análisis avanzados. |
| **AWS EventBridge** | Automatización de respuestas ante eventos (por ejemplo, alertas de seguridad). |

> 💾 *Puedes almacenar los logs en S3 para conservarlos indefinidamente y analizarlos con otras herramientas.*

---

## 🌍 Regional and Multi-Region Trails

- Por defecto, CloudTrail **registra eventos en todas las regiones** de AWS.  
- Puedes configurar un *trail* para una **región específica** si deseas separar entornos (por ejemplo, dev vs prod).  
- Recomendado: habilitar **All-Region Trail** para garantizar visibilidad completa.

> 🌐 *Esto asegura que los eventos en nuevas regiones se registren automáticamente.*

---

## 🔔 Alerts and Automation

- CloudTrail puede **enviar notificaciones** de eventos importantes a través de:
  - **Amazon SNS (Simple Notification Service)**
  - **Amazon EventBridge**
- Ejemplo: alerta cuando se elimina una instancia EC2 o se modifica una política IAM crítica.

> ⚠️ *Si un recurso desaparece, CloudTrail es el primer lugar donde debes investigar.*

---

## 🧩 Example Use Cases

| **Caso de Uso** | **Descripción** |
|------------------|-----------------|
| **Security Investigation** | Detectar quién eliminó un recurso, cambió permisos o accedió a datos sensibles. |
| **Operational Troubleshooting** | Rastrear fallos de configuración o cambios accidentales. |
| **Compliance Auditing** | Proporcionar evidencia de auditoría para normativas de seguridad y cumplimiento. |
| **Access Monitoring** | Identificar usuarios y roles que interactúan con servicios críticos. |

---

## 🧠 How It Works

1. **CloudTrail Enabled by Default** → Comienza a registrar eventos automáticamente.  
2. **Trails Configuration** → Puedes definir uno o varios trails para guardar logs en S3 o CloudWatch.  
3. **Continuous Logging** → Captura llamadas API en tiempo real.  
4. **Event Delivery** → Los logs se entregan a S3 (almacenamiento) o CloudWatch (monitoreo).  
5. **Analysis & Alerting** → Usa Athena o EventBridge para detectar patrones o anomalías.

---

## 💰 Pricing Overview

- **Eventos de gestión (Management Events):**  
  - Primer trail (por defecto) sin costo adicional.  
  - Trails adicionales con costo por cada 100,000 eventos.  
- **Eventos de datos (Data Events):**  
  - Cobro por cada 100,000 eventos registrados (más granular).  
- **Almacenamiento:**  
  - Costos asociados a S3 y CloudWatch Logs.

> 💡 *El trail por defecto ofrece visibilidad básica sin costo; se paga por almacenamiento o análisis avanzados.*

---

## 🧱 Key Takeaways

- **AWS CloudTrail = Auditoría y visibilidad total de tu cuenta AWS.**  
- Registra **todas las llamadas API y cambios** realizados por usuarios o servicios.  
- Integración con **S3, CloudWatch, Athena y EventBridge**.  
- **Habilitado por defecto** en todas las cuentas.  
- Esencial para **cumplimiento, gobernanza y respuesta a incidentes.**

> 🕵️ *“Si algo cambió en AWS y no sabes por qué, CloudTrail tiene la respuesta.”*
