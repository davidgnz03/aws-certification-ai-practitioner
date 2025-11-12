# 🛡️ AWS Security Services – Section Summary  

---

## 👤 Identity and Access Management (IAM)

| **Servicio / Concepto** | **Descripción** |
|---------------------------|-----------------|
| **IAM Users** | Representan usuarios individuales dentro de la organización. Cada usuario tiene credenciales únicas (contraseña o claves de acceso). |
| **IAM Groups** | Agrupan varios usuarios para asignar permisos comunes. Solo contienen usuarios, no otros grupos. |
| **IAM Policies** | Documentos JSON que **definen permisos**. Se asocian a usuarios, grupos o roles para controlar qué acciones pueden realizar y sobre qué recursos. |
| **IAM Roles** | Entidades que definen permisos temporales para **servicios de AWS o EC2 instances**, permitiendo que actúen en nombre del usuario sin credenciales permanentes. |

> 💡 *Aplica siempre el principio de **mínimo privilegio** para mantener un entorno seguro.*

---

## 💻 Compute Security

| **Servicio / Concepto** | **Descripción** |
|---------------------------|-----------------|
| **EC2 Instance** | Máquinas virtuales configurables con: **AMI (sistema operativo)**, **tamaño de instancia (CPU/RAM)**, **almacenamiento (EBS)**, **Security Groups** y **EC2 User Data** (scripts de inicialización). |
| **AWS Lambda** | Servicio **serverless** (Function-as-a-Service) que ejecuta funciones sin gestionar servidores. Escala automáticamente y cobra por ejecución. |

> 🧠 *Lambda es ideal para tareas automáticas y microservicios seguros sin exposición de infraestructura.*

---

## 🌐 Network Security

| **Servicio / Concepto** | **Descripción** |
|---------------------------|-----------------|
| **VPC Endpoint (PrivateLink)** | Permite **acceso privado** desde tu **VPC a servicios AWS**, sin pasar por Internet, mejorando seguridad y cumplimiento. |
| **S3 Gateway Endpoint** | Conecta la VPC directamente con **Amazon S3** de manera privada (sin usar Internet Gateway). |

> 🔒 *PrivateLink y Endpoints refuerzan la seguridad eliminando la necesidad de IPs públicas.*

---

## 🔍 Data Protection & Security Analysis

| **Servicio / Concepto** | **Descripción** |
|---------------------------|-----------------|
| **Amazon Macie** | Servicio administrado que usa **machine learning** para identificar y proteger datos sensibles (PII, PHI, etc.) almacenados en **Amazon S3**. |
| **AWS Config** | Supervisa configuraciones de recursos AWS, detecta cambios y evalúa **cumplimiento de reglas de seguridad** o políticas internas. |
| **Amazon Inspector** | Analiza **vulnerabilidades de seguridad** en instancias **EC2**, **imágenes de contenedores (ECR)** y **funciones Lambda**. |
| **AWS CloudTrail** | Registra todas las **llamadas API y eventos** realizados en tu cuenta (CLI, SDK, consola). Útil para auditorías y análisis forense. |
| **AWS Artifact** | Portal centralizado que ofrece **reportes de cumplimiento y certificaciones** (PCI, ISO, SOC, HIPAA, etc.) bajo demanda. |
| **AWS Trusted Advisor** | Evalúa tu cuenta y recomienda **mejoras en costo, rendimiento, seguridad, tolerancia a fallos y límites de servicio.** |

---

## 🧩 AWS Security Overview – Quick Reference

| **Categoría** | **Servicios Clave** | **Propósito Principal** |
|----------------|---------------------|--------------------------|
| **Identity & Access** | IAM Users, Groups, Roles, Policies | Controlar quién puede hacer qué dentro de AWS. |
| **Compute Protection** | EC2, Lambda | Asegurar workloads y funciones serverless. |
| **Network Security** | VPC Endpoints, PrivateLink, S3 Gateway | Comunicación privada y segura sin Internet. |
| **Data Protection** | Macie, Config, Inspector | Detectar datos sensibles, evaluar vulnerabilidades y monitorear compliance. |
| **Governance & Audit** | CloudTrail, Artifact, Trusted Advisor | Auditoría, cumplimiento y optimización operativa. |

---

## 🧱 Key Takeaways

- 🧍 **IAM:** Control de acceso granular y seguro.  
- 💻 **EC2 / Lambda:** Computo flexible con control de seguridad.  
- 🌐 **PrivateLink / Endpoints:** Conexión privada y sin exposición a Internet.  
- 🔍 **Macie / Config / Inspector:** Análisis, cumplimiento y protección de datos.  
- 🧾 **CloudTrail / Artifact / Trusted Advisor:** Auditoría, certificación y mejora continua.  

> 🔐 *Con estos servicios, AWS proporciona un ecosistema integral de seguridad, desde identidad hasta cumplimiento y monitoreo continuo.*
