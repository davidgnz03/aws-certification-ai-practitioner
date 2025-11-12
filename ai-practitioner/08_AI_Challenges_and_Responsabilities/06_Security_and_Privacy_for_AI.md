# 🔐 Security and Privacy for AI  
## Seguridad y Privacidad en Sistemas de Inteligencia Artificial

La seguridad y la privacidad son pilares fundamentales para el desarrollo responsable de sistemas de **Inteligencia Artificial (AI)**.  
Proteger los modelos, datos y usuarios no solo evita brechas o ataques, sino que también refuerza la **confianza** y el **cumplimiento normativo**.

---

## 🧠 Security and Privacy for AI Systems  
*(Seguridad y privacidad en sistemas AI)*

### ⚠️ Threat Detection (Detección de amenazas)

- Los sistemas AI pueden ser blanco o herramienta de **ataques automatizados**, **datos manipulados** o **contenido falso**.  
- Es esencial implementar **sistemas de detección de amenazas basados en AI** capaces de analizar:
  - Tráfico de red.
  - Comportamientos anómalos de usuarios.
  - Actividades en tiempo real de aplicaciones y datos.  

> 💡 *Ejemplo:* modelos AI que detectan *deepfakes* o intentos de inyección de *prompts* maliciosos.

---

### 🧩 Vulnerabilities Management (Gestión de vulnerabilidades)

- Identificar y mitigar **fallas de seguridad** en software, dependencias y modelos.  
- Prácticas recomendadas:
  - Auditorías de seguridad y pruebas de penetración.  
  - Revisión de código (code reviews).  
  - Gestión activa de *patches* y actualizaciones.  

> 🧠 *Una vulnerabilidad en el modelo puede comprometer toda la infraestructura.*

---

### 🖥️ Infrastructure Protection (Protección de infraestructura)

- Asegurar los entornos donde se ejecuta AI: **nube, edge devices, y repositorios de datos**.  
- Implementar:
  - Controles de acceso y segmentación de red.  
  - Cifrado extremo a extremo.  
  - Planes de resiliencia ante fallos del sistema.  

> 🧱 *AWS ofrece herramientas como VPC, IAM, Shield y GuardDuty para reforzar la seguridad.*

---

### ⚔️ Prompt Injection (Inyección de *prompts*)

- Ataque donde un usuario manipula el *input* para generar contenido no deseado o inseguro.  
- Mitigación mediante **guardrails**:
  - Filtrado y validación de *prompts*.  
  - Sanitización de entradas.  
  - Monitoreo continuo de interacciones sospechosas.  

---

### 🔒 Data Encryption (Cifrado de datos)

- **Cifrar los datos en reposo y en tránsito** usando claves gestionadas.  
- Emplear servicios como:
  - **AWS KMS (Key Management Service)** para gestión segura de llaves.  
  - **AWS Secrets Manager** para proteger credenciales y secretos.  
- Asegurar que las claves estén **protegidas y auditadas** para evitar accesos no autorizados.

---

## 📈 Monitoring AI Systems  
*(Monitoreo y métricas de sistemas AI)*

El monitoreo continuo es esencial para garantizar que los modelos se comporten conforme a lo esperado y cumplan con los requisitos de rendimiento y seguridad.

### 🔢 Performance Metrics (Métricas de rendimiento)
| **Métrica** | **Descripción** |
|--------------|----------------|
| **Accuracy (Exactitud)** | Porcentaje de predicciones correctas. |
| **Precision (Precisión)** | Proporción de verdaderos positivos entre todas las predicciones positivas. |
| **Recall (Sensibilidad)** | Proporción de verdaderos positivos detectados entre todos los positivos reales. |
| **F1-Score** | Media armónica entre precisión y *recall* (balance general). |
| **Latency (Latencia)** | Tiempo que tarda el modelo en generar una predicción. |

### 🖥️ Infrastructure Monitoring
- Supervisar recursos de cómputo (CPU/GPU), almacenamiento y red.  
- Analizar *logs* del sistema y métricas de uso.  
- Detectar **cuellos de botella** o **fallos críticos** en pipelines de inferencia o entrenamiento.  

### ⚖️ Bias, Fairness & Compliance
- Monitorear **sesgo y equidad** del modelo en producción.  
- Aplicar revisiones periódicas con herramientas como **SageMaker Clarify** o **Model Monitor**.

---

## ☁️ AWS Shared Responsibility Model  
*(Modelo de responsabilidad compartida en AWS)*

El modelo de seguridad de AWS se basa en la **división de responsabilidades** entre el proveedor de la nube (AWS) y el cliente.

| **Categoría** | **Responsabilidad** | **Ejemplos** |
|----------------|---------------------|---------------|
| **AWS Responsibility – Security *of* the Cloud** | Seguridad de la infraestructura (hardware, software, redes y centros de datos). | Protección física, red, hipervisores, servicios gestionados como S3, SageMaker, Bedrock. |
| **Customer Responsibility – Security *in* the Cloud** | Seguridad del contenido, configuraciones y accesos. | Cifrado de datos, gestión de usuarios, control de acceso, *guardrails* en Bedrock. |
| **Shared Controls** | Controles compartidos por ambas partes. | Gestión de *patches*, configuración segura, concienciación y formación. |

🔗 **Referencia oficial:**  
[AWS Shared Responsibility Model Documentation](https://aws.amazon.com/compliance/shared-responsibility-model/)

> 🧱 *AWS asegura la nube, tú aseguras lo que pones en ella.*

---

## 🧮 Secure Data Engineering – Best Practices  
*(Buenas prácticas de ingeniería de datos segura)*

### 📊 Assessing Data Quality (Evaluación de calidad de datos)

| **Criterio** | **Descripción** |
|---------------|----------------|
| **Completeness (Completitud)** | Cobertura amplia de escenarios y variables relevantes. |
| **Accuracy (Exactitud)** | Datos correctos, actualizados y representativos. |
| **Timeliness (Actualidad)** | Datos recientes y vigentes para el propósito de uso. |
| **Consistency (Consistencia)** | Coherencia a lo largo de todo el ciclo de vida de los datos. |

- Implementar **data profiling**, **monitoring** y **data lineage** para detectar problemas de calidad.  

---

### 🧰 Privacy-Enhancing Technologies (Tecnologías de mejora de privacidad)

- **Data masking / obfuscation:** ocultar información sensible en entornos de prueba o análisis.  
- **Encryption / tokenization:** cifrar o sustituir identificadores personales durante el procesamiento.  
- Reducen la exposición en caso de fuga o mal uso de datos.  

> 🛡️ *El objetivo es minimizar el riesgo de violación de datos personales.*

---

### 👥 Data Access Control (Control de acceso a datos)

- Definir un **marco de gobernanza** con políticas claras de acceso.  
- Aplicar **Role-Based Access Control (RBAC)** y **fine-grained permissions**.  
- Habilitar **Single Sign-On (SSO)**, **Multi-Factor Authentication (MFA)** y **IAM**.  
- Monitorear y registrar toda la actividad de acceso.  
- Revisar periódicamente los privilegios siguiendo el principio de **least privilege** (mínimo acceso necesario).

---

### 🧩 Data Integrity (Integridad de datos)

- Garantizar que los datos sean **completos, coherentes y libres de errores**.  
- Estrategias clave:
  - **Copias de seguridad** y **recuperación ante desastres**.  
  - Mantener **líneas de trazabilidad (data lineage)** y **registros de auditoría**.  
  - **Probar periódicamente** los controles de integridad.  

> 🧱 *La integridad y trazabilidad de los datos sustentan la confiabilidad de los modelos AI.*

---

## 🧭 En Resumen

| **Área** | **Objetivo Principal** | **Herramientas / Prácticas AWS** |
|-----------|------------------------|----------------------------------|
| **Threat Detection** | Detectar amenazas y anomalías. | Amazon GuardDuty, Detective, CloudWatch. |
| **Vulnerability Management** | Identificar y mitigar vulnerabilidades. | AWS Inspector, Security Hub. |
| **Infrastructure Protection** | Asegurar entornos de ejecución. | AWS VPC, Shield, WAF, IAM. |
| **Prompt Security** | Evitar *prompt injection* y manipulación. | Guardrails for Amazon Bedrock. |
| **Data Encryption** | Proteger datos en tránsito y en reposo. | AWS KMS, Secrets Manager, CloudHSM. |
| **Monitoring & Compliance** | Medir rendimiento y equidad. | CloudTrail, SageMaker Model Monitor. |
| **Data Governance** | Mantener calidad, privacidad e integridad. | AWS Lake Formation, Glue Data Catalog. |

---

> 🔒 *La seguridad en AI no es una opción: es una responsabilidad compartida que garantiza la privacidad, confiabilidad y sostenibilidad de las soluciones basadas en inteligencia artificial.*
