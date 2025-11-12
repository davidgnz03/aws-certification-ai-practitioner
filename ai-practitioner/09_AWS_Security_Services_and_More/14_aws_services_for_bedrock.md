# 🧠 AWS Services for Bedrock  
## Seguridad, Gobernanza y Cumplimiento en Amazon Bedrock

---

### 🔐 IAM with Bedrock  
**Amazon Bedrock** se integra con **AWS Identity and Access Management (IAM)** para proporcionar un control detallado de acceso y autenticación.

| **Componente** | **Descripción** |
|----------------|-----------------|
| **Identity Verification** | IAM garantiza que solo usuarios, servicios o aplicaciones autenticadas puedan acceder a recursos de Bedrock. |
| **Resource-Level Access Control** | Puedes definir políticas IAM que limiten el acceso a recursos específicos de Bedrock (por ejemplo, modelos, endpoints o configuraciones). |
| **Roles and Permissions** | Define **roles IAM** para usuarios como **científicos de datos, desarrolladores o analistas** con permisos ajustados según su función. |

> 🧠 *Ejemplo:* un rol IAM podría permitir acceso a la API de inferencia de Bedrock pero no a la administración de modelos o datasets.

---

### 🛡️ GuardRails for Bedrock  

Los **GuardRails for Bedrock** permiten configurar **políticas de seguridad y contenido responsable** dentro de aplicaciones generativas (GenAI).

| **Funcionalidad** | **Propósito** |
|--------------------|---------------|
| **Restrict Specific Topics** | Limita temas o dominios específicos que la aplicación GenAI no debe tratar. |
| **Filter Harmful Content** | Detecta y filtra contenido ofensivo, tóxico o inapropiado antes de su entrega. |
| **Compliance with Safety Policies** | Asegura el cumplimiento con políticas internas, regulatorias o éticas mediante el análisis de las entradas del usuario. |

> ⚙️ *Ejemplo:* restringir conversaciones relacionadas con violencia o temas médicos no aprobados en un chatbot corporativo.

---

### 📜 CloudTrail with Bedrock  

**AWS CloudTrail** registra todas las **llamadas API realizadas a Amazon Bedrock**, brindando visibilidad completa sobre el uso y acciones ejecutadas.

- Permite **auditorías de seguridad y cumplimiento**.  
- Registra quién accedió, desde dónde, cuándo y qué operación realizó.  
- Integra alertas con **CloudWatch** o **EventBridge** para detectar actividades sospechosas.  

> 🧾 *Ideal para entornos regulados o proyectos sensibles donde se requiere trazabilidad completa.*

---

### 🧩 AWS Config with Bedrock  

**AWS Config** puede monitorear las **configuraciones y cambios** relacionados con recursos de Bedrock:

- Detecta modificaciones en permisos, endpoints o configuraciones de modelos.  
- Evalúa el cumplimiento con políticas internas o normativas (ej. GDPR, HIPAA).  
- Almacena historial de configuraciones para auditorías y revisiones de seguridad.  

> 📋 *Permite demostrar compliance continuo y detectar desviaciones en configuraciones críticas.*

---

### 🔒 PrivateLink with Bedrock  

Con **AWS PrivateLink**, es posible mantener **todas las llamadas a la API de Amazon Bedrock dentro de una VPC privada**, eliminando la exposición a Internet.

| **Beneficio** | **Descripción** |
|----------------|-----------------|
| **Tráfico Interno Seguro** | Todo el tráfico entre Bedrock y otros servicios (S3, KMS, etc.) permanece en la red interna de AWS. |
| **Cumplimiento y Privacidad** | Alinea con requisitos de seguridad y privacidad corporativos. |
| **Menor Latencia** | Al no pasar por Internet, se obtiene un acceso más rápido y confiable. |

> 🔐 *Perfecto para entornos donde la protección de datos y el aislamiento de red son críticos (como banca, salud o defensa).*

---

### 🗝️ Bedrock and Encrypted S3 Buckets  

Amazon Bedrock debe poder acceder de forma segura a los datos almacenados en **buckets S3 cifrados**.  
Para ello, necesita un **rol IAM** con los permisos adecuados.

#### Requisitos de Acceso:
- **Amazon S3 Access:** Permite leer datos de los buckets necesarios.  
- **KMS Key Access:** Bedrock debe tener permiso para **usar la clave KMS (Key Management Service)** asociada al bucket, incluyendo el permiso **`kms:Decrypt`**.  

> 💡 *Esto garantiza que Bedrock pueda acceder a los datos de entrenamiento o inferencia sin comprometer el cifrado ni la seguridad.*

---

## 🧠 Key Takeaways

- **IAM:** Controla quién puede acceder a Bedrock y qué acciones puede realizar.  
- **GuardRails:** Asegura la responsabilidad y seguridad del contenido generado.  
- **CloudTrail:** Audita todas las llamadas API y actividades en Bedrock.  
- **Config:** Supervisa cambios y cumplimiento de configuraciones.  
- **PrivateLink:** Mantiene el tráfico privado y dentro de la VPC.  
- **KMS + S3:** Protege datos sensibles mediante cifrado y control de claves.  

> 🧩 *Con estos servicios, Amazon Bedrock se integra de forma segura dentro del ecosistema AWS, cumpliendo los estándares más altos de seguridad, gobernanza y privacidad.*
