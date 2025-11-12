# 🕵️ Amazon Inspector  
## Automated Security Assessments for AWS Workloads

---

### 🧱 Overview

**Amazon Inspector** es un servicio automatizado de **evaluación de seguridad (Automated Security Assessments)** que analiza continuamente tus recursos de AWS para identificar **vulnerabilidades de software, configuraciones inseguras y riesgos de red**.

> 🛡️ *Inspector ayuda a fortalecer la postura de seguridad al detectar amenazas antes de que sean explotadas.*

---

## ⚙️ Supported Resources

Amazon Inspector ejecuta evaluaciones de seguridad sobre tres tipos principales de recursos:

| **Recurso** | **Evaluaciones Realizadas** |
|--------------|-----------------------------|
| **Amazon EC2 Instances** | Analiza vulnerabilidades en el sistema operativo y accesibilidad de red no intencionada. |
| **Container Images (Amazon ECR)** | Evalúa las imágenes al ser enviadas a ECR, buscando paquetes vulnerables o desactualizados. |
| **AWS Lambda Functions** | Detecta vulnerabilidades en el código de las funciones y en las dependencias de paquetes. |

---

## 🧩 EC2 Instance Assessments

Para **EC2 Instances**, Amazon Inspector utiliza el **AWS Systems Manager (SSM) Agent** para recopilar información y ejecutar escaneos sin necesidad de intervención manual.

### 🔍 Qué analiza
- **Network Reachability**: identifica exposición no intencionada a Internet o redes no seguras.  
- **Operating System Vulnerabilities**: compara el sistema operativo y sus componentes con bases de datos de vulnerabilidades conocidas (**CVE Database**).  
- **Continuous Scanning**: análisis continuo solo cuando hay cambios relevantes en paquetes o configuraciones.

> 🧠 *No requiere detener ni reiniciar las instancias.*

---

## 🧱 Container Image Assessments (Amazon ECR)

Amazon Inspector se integra directamente con **Amazon Elastic Container Registry (ECR)**.

### 🚀 Evaluaciones automáticas
- Escanea automáticamente las **imágenes de contenedor** cuando son **empujadas (push)** a ECR.  
- Evalúa **librerías y dependencias** en busca de vulnerabilidades conocidas (CVE).  
- Actualiza continuamente los resultados cuando nuevas vulnerabilidades se descubren.

> ⚙️ *Los escaneos son continuos y se mantienen actualizados sin intervención manual.*

---

## 🧠 Lambda Function Assessments

Inspector también analiza las **funciones AWS Lambda**, incluyendo:

- **Código fuente** y **paquetes de dependencias**.  
- **Vulnerabilidades en bibliotecas** (por ejemplo, `requests`, `numpy`, `boto3`).  
- Escaneos automáticos **cada vez que una función es desplegada o actualizada**.

> ⚡ *Ideal para entornos Serverless donde las dependencias cambian rápidamente.*

---

## 🧩 What Amazon Inspector Evaluates

Amazon Inspector realiza **escaneos continuos y automáticos** para detectar vulnerabilidades críticas:

| **Evaluación** | **Tipo de Recurso** | **Descripción** |
|----------------|--------------------|-----------------|
| **Package Vulnerabilities** | EC2, ECR, Lambda | Basado en la base de datos CVE (*Common Vulnerabilities and Exposures*). |
| **Network Reachability** | EC2 | Detecta accesos de red abiertos o no intencionados. |
| **Software Dependencies** | Lambda, Containers | Evalúa librerías y paquetes de terceros. |

> 🧾 *Cada hallazgo tiene un **Risk Score** que indica su severidad y prioridad de corrección.*

---

## 📊 Risk Scoring and Prioritization

Cada vulnerabilidad identificada recibe un **puntaje de riesgo (Risk Score)** basado en:

- Severidad (de *Low* a *Critical*).  
- Contexto de exposición (por ejemplo, accesibilidad desde Internet).  
- Impacto potencial sobre el sistema.  
- Disponibilidad de parches o mitigaciones.

> 🔥 *Esto ayuda a priorizar rápidamente las vulnerabilidades más críticas para resolver primero.*

---

## 🔔 Reporting & Integrations

Amazon Inspector se integra de forma nativa con otros servicios de seguridad de AWS:

| **Servicio AWS** | **Función de Integración** |
|------------------|----------------------------|
| **AWS Security Hub** | Consolida y correlaciona los hallazgos de Inspector con otros servicios de seguridad. |
| **Amazon EventBridge** | Permite automatizar respuestas y flujos de trabajo ante vulnerabilidades detectadas. |
| **AWS CloudWatch** | Supervisión continua de métricas y alertas de evaluación. |
| **AWS Systems Manager (SSM)** | Despliegue del agente requerido para EC2, y automatización de remediaciones. |

> 📡 *Puedes enviar findings a Security Hub y EventBridge para crear reglas o automatizar parches.*

---

## ⚙️ How It Works

1. **Enable Inspector** → Se activa con un clic desde la consola o CLI.  
2. **Automatic Discovery** → Identifica EC2, ECR y Lambda activos.  
3. **Continuous Scanning** → Evalúa automáticamente vulnerabilidades relevantes.  
4. **Findings Generation** → Crea reportes detallados con risk score y recomendaciones.  
5. **Integration** → Envía los hallazgos a Security Hub o EventBridge.  
6. **Remediation** → Automatiza la reparación mediante SSM Automation o flujos personalizados.

---

## 🧠 Example Use Cases

| **Caso de Uso** | **Descripción** |
|------------------|-----------------|
| **Continuous Vulnerability Management** | Detección automática de vulnerabilidades en EC2, contenedores y Lambda. |
| **Regulatory Compliance** | Soporte para auditorías de seguridad y cumplimiento (ISO, SOC, PCI DSS). |
| **DevSecOps Pipeline** | Integración en CI/CD para validar la seguridad antes del despliegue. |
| **Incident Response** | Envío de findings críticos a EventBridge para ejecución automática de parches o aislamiento. |

---

## 💰 Pricing Overview

- Pago basado en:
  - Número de **recursos evaluados** (instancias, imágenes, funciones).
  - **Frecuencia de escaneo** y cantidad de findings generados.
- Escaneo continuo y escalable, sin administración manual de servidores.

> 💡 *El modelo de precios es “pay-as-you-go” y puede integrarse fácilmente en presupuestos de seguridad.*

---

## 🧱 Key Takeaways

- **Amazon Inspector = Evaluaciones automáticas de seguridad.**  
- Cobertura para **EC2, ECR y Lambda**.  
- **Detección continua** de vulnerabilidades y exposición de red.  
- **Integración nativa** con Security Hub, EventBridge y CloudWatch.  
- Ideal para **DevSecOps y cumplimiento continuo**.

> 🔐 *Inspector te da visibilidad, priorización y acción automatizada sobre vulnerabilidades críticas.*
