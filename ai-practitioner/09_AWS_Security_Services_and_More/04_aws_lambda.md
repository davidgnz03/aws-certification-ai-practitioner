# ⚡ AWS Lambda  
## Serverless Compute Service

---

### 🧱 Overview

**AWS Lambda** es un servicio **Serverless (sin servidores)** que permite ejecutar código **sin aprovisionar ni administrar servidores**.  
AWS Lambda se encarga automáticamente de la **infraestructura, el escalado y la disponibilidad**.

> ⚙️ *Tú solo subes el código; AWS Lambda se encarga de todo lo demás.*

---

## 🧩 Key Characteristics

| **Característica** | **Descripción** |
|---------------------|-----------------|
| **Virtual Functions** | Ejecuta pequeñas funciones sin necesidad de servidores dedicados. |
| **On-Demand Execution** | Las funciones se ejecutan solo cuando son invocadas. |
| **Short Executions** | Ideal para tareas de corta duración (máx. 15 minutos por ejecución). |
| **Automatic Scaling** | Escala automáticamente al número de solicitudes concurrentes necesarias. |

> 💡 *Lambda escala horizontalmente creando instancias paralelas de la función según la demanda.*

---

## 🌟 Benefits of AWS Lambda

### 💰 Easy Pricing
- **Pago por uso:** solo pagas por las **solicitudes** y **tiempo de ejecución** (en GB-segundos).  
- **Free Tier:**  
  - 1,000,000 solicitudes gratuitas al mes.  
  - 400,000 GB-segundos de cómputo mensual gratuito.  

| **Concepto** | **Unidad de Cobro** |
|---------------|---------------------|
| Requests | $0.20 por millón de solicitudes después del free tier |
| Duration | $0.00001667 por GB-segundo de ejecución (según memoria configurada) |

> ⚙️ *El costo depende de la cantidad de memoria asignada y del tiempo de ejecución.*

---

### 🔗 Full AWS Integration

AWS Lambda está totalmente **integrado con otros servicios de AWS**, permitiendo arquitecturas **event-driven** (basadas en eventos):

| **Servicio AWS** | **Evento que Invoca Lambda** |
|-------------------|-------------------------------|
| **S3** | Carga o eliminación de objetos en un bucket. |
| **DynamoDB** | Cambios en tablas (streams). |
| **API Gateway** | Llamadas HTTP o REST. |
| **SNS / SQS** | Mensajes y notificaciones. |
| **CloudWatch Events / EventBridge** | Eventos programados o del sistema. |
| **Kinesis / Firehose** | Flujos de datos en tiempo real. |
| **Cognito** | Eventos de autenticación de usuarios. |

> 🚀 *Lambda es el motor central del enfoque Event-Driven Architecture (EDA) en AWS.*

---

### 🧠 Easy Monitoring

Lambda se integra nativamente con **Amazon CloudWatch**, lo que permite:
- Monitorear métricas: invocaciones, errores, duración, tiempo de espera.
- Crear alarmas para funciones específicas.
- Visualizar logs generados por la función (`console.log`, `print`, etc.).

> 📊 *Cada ejecución genera automáticamente logs visibles en CloudWatch Logs.*

---

### ⚙️ Resource Allocation

- Puedes asignar **hasta 10 GB de RAM por función**.
- El incremento de memoria también **aumenta proporcionalmente el CPU y el ancho de banda de red**.  
- Ideal para optimizar rendimiento sin tener que ajustar servidores.

> 💡 *Más RAM = más CPU + mejor performance + mayor costo por segundo.*

---

## 💬 AWS Lambda Language Support

AWS Lambda soporta múltiples lenguajes nativamente:

| **Lenguaje** | **Runtime Compatible** |
|---------------|------------------------|
| Node.js | ✅ |
| Python | ✅ |
| Java | ✅ |
| Go | ✅ |
| Ruby | ✅ |
| .NET (C#) | ✅ |
| Custom Runtime | ✅ (mediante API personalizada) |

> 🧩 *Puedes usar runtimes personalizados para otros lenguajes no soportados oficialmente.*

---

## 🐳 Lambda Container Image Support

AWS Lambda permite **desplegar funciones como imágenes de contenedor (Docker)**.  
Esto amplía la flexibilidad para desarrolladores que ya usan contenedores en su flujo de trabajo.

### 🔸 Requisitos
- La imagen **debe implementar el Lambda Runtime API**.
- Tamaño máximo de la imagen: **10 GB**.
- Compatible con **Amazon ECR (Elastic Container Registry)**.

> ⚠️ *Si necesitas ejecutar contenedores arbitrarios o persistentes, considera usar **ECS** o **AWS Fargate**.*

---

## ⚙️ Common Use Cases

| **Use Case** | **Descripción** |
|----------------|----------------|
| **Data Processing** | Procesamiento de datos en tiempo real desde S3, DynamoDB o Kinesis. |
| **Web APIs (Serverless Backend)** | Junto con API Gateway, construye APIs REST o GraphQL sin servidores. |
| **Automation / Event Handling** | Ejecución automática ante eventos de AWS o cron jobs (CloudWatch Events). |
| **IoT & Stream Processing** | Reacción a eventos generados por dispositivos IoT o flujos Kinesis. |
| **Machine Learning Inference** | Ejecución rápida de inferencias con modelos ligeros. |
| **Image / Video Processing** | Procesamiento en segundo plano de archivos cargados en S3. |

---

## 💵 AWS Lambda Pricing Example

### Example Calculation
- Memoria: 512 MB  
- Tiempo: 1 segundo por ejecución  
- 1 millón de solicitudes mensuales  

**Costo aproximado:**  
- Solicitudes: $0.20  
- Ejecución: 1,000,000 × 0.5 GB × 1 seg × $0.00001667 = **$8.34**

> 💰 **Total mensual:** ~$8.54  
> *(después del free tier)*

---

## 🧱 Key Takeaways

- **Serverless** = sin gestión de servidores ni infraestructura.  
- **Escala automática** basado en eventos y demanda.  
- **Pago por uso** (millones de solicitudes y GB-segundos).  
- **Integrado con todo AWS**: S3, API Gateway, DynamoDB, CloudWatch, etc.  
- **Ideal para workloads event-driven, automations, APIs y microservicios.**

> ⚡ *AWS Lambda simplifica la computación moderna: código sin servidores, ejecución sin límites de escalabilidad.*
