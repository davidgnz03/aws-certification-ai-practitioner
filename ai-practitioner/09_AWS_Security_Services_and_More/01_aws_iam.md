# 🔐 IAM Section  
## AWS Identity and Access Management (IAM)

---

### 🧭 Overview

**AWS IAM (Identity and Access Management)** es un **servicio global** que permite **gestionar identidades y permisos** dentro de una cuenta de AWS.  
Su objetivo principal es garantizar que solo las **personas o servicios autorizados** puedan acceder a los recursos necesarios, aplicando siempre el **principio de privilegio mínimo** (*Least Privilege Principle*).

> 💡 *IAM no es un servicio regional. Las políticas y configuraciones aplican globalmente en toda la cuenta AWS.*

---

## 👤 IAM Users and Groups

### 🔸 Users (Usuarios)
- Representan **identidades individuales** dentro de la organización.  
- Cada usuario puede tener **credenciales propias**:
  - Usuario/contraseña para la consola de AWS.
  - Claves de acceso (Access Key ID y Secret Access Key) para uso mediante CLI o SDK.  
- Los usuarios deben crearse **bajo la cuenta raíz**, pero **no deben usar la cuenta raíz para operaciones diarias**.

> 🚫 *La cuenta root solo se usa para configuraciones iniciales o tareas críticas de administración.*

---

### 🔸 Groups (Grupos)
- Permiten **organizar usuarios** que comparten funciones o responsabilidades.  
- Las políticas se pueden asignar a grupos para otorgar permisos colectivos.  
- Un grupo **solo puede contener usuarios**, no otros grupos.

> 🧩 *Ejemplo:* Un grupo “Developers” puede tener permisos para usar EC2 y S3, aplicando la misma política a todos los desarrolladores.

---

## 🔐 IAM Permissions

### 🧱 Políticas de Permisos (Policies)
- Las **políticas (policies)** son **documentos JSON** que definen permisos.  
- Se aplican a **usuarios, grupos o roles** para controlar el acceso a recursos.  
- AWS recomienda el **principio de menor privilegio**, es decir:
  > Conceder solo los permisos estrictamente necesarios para realizar una tarea.

---

## 🧩 IAM Policies – Estructura

Una política IAM se compone de **bloques JSON** con los siguientes campos:

```json
{
  "Version": "2012-10-17",
  "Id": "PolicyExample",
  "Statement": [
    {
      "Sid": "Stmt1",
      "Effect": "Allow",
      "Principal": "*",
      "Action": "s3:ListBucket",
      "Resource": "arn:aws:s3:::example-bucket",
      "Condition": {
        "StringEquals": { "aws:username": "alice" }
      }
    }
  ]
}
```

| **Campo**                | **Descripción**                                                           |
| ------------------------ | ------------------------------------------------------------------------- |
| **Version**              | Fecha de versión del lenguaje de políticas (recomendado: `"2012-10-17"`). |
| **Id**                   | Identificador opcional para la política.                                  |
| **Statement**            | Lista de reglas individuales (una o más).                                 |
| **Sid**                  | Identificador de la declaración.                                          |
| **Effect**               | Define si la acción se **permite (Allow)** o se **deniega (Deny)**.       |
| **Principal**            | Entidad a la que se aplica la política (usuarios, roles, cuentas).        |
| **Action**               | Operaciones de AWS permitidas o denegadas (ej: `s3:GetObject`).           |
| **Resource**             | ARN de los recursos afectados.                                            |
| **Condition (opcional)** | Define cuándo se aplica la política (por ejemplo, por IP o región).       |

---

## 📚 Tipos de Políticas

| **Tipo**                             | **Descripción**                                                                                                       |
| ------------------------------------ | --------------------------------------------------------------------------------------------------------------------- |
| **Managed Policies (Administradas)** | Políticas creadas y mantenidas por AWS o el cliente. Reutilizables entre múltiples identidades.                       |
| **Inline Policies (Integradas)**     | Políticas que están directamente incrustadas dentro de un usuario, grupo o rol. Se eliminan si se elimina la entidad. |

> ⚙️ *AWS recomienda usar Managed Policies para consistencia y escalabilidad.*

---

## 🔄 IAM Roles

### 🧠 ¿Qué es un Rol?

Un **IAM Role** es una **identidad con permisos que no está asociada a una persona específica.**  
Se utiliza cuando un servicio de AWS, aplicación o usuario necesita **asumir temporalmente ciertos permisos.**

### 🧩 Casos de Uso Comunes

- Un servicio de AWS (por ejemplo, EC2) necesita acceder a S3.
- Una aplicación externa necesita ejecutar acciones dentro de AWS.
- Acceso temporal mediante IAM Role + STS (Security Token Service).

> 🧱 *Los roles permiten delegar permisos de forma segura sin compartir credenciales permanentes.*

**🔑 Ejemplo: Rol para EC2 acceder a S3**
```json
{
  "Version": "2012-10-17",
  "Statement": [
    {
      "Effect": "Allow",
      "Action": ["s3:GetObject"],
      "Resource": ["arn:aws:s3:::example-bucket/*"]
    }
  ]
}
```

- El rol se asigna a la instancia EC2.
- La instancia puede leer objetos de S3 sin almacenar claves de acceso.

---

## 🌐 AWS Console Simultaneous Sign-In

Desde 2024, AWS permite **iniciar sesión con hasta cinco identidades diferentes simultáneamente en la consola web del AWS Management Console.**

> 🔁 *Esto facilita cambiar entre cuentas o roles sin cerrar sesión.*

---

## 🧱 Buenas Prácticas IAM

| **Práctica**                          | **Descripción**                                                    |
| ------------------------------------- | ------------------------------------------------------------------ |
| **Evitar uso de la cuenta root**      | Utilizar solo para configuración inicial o recuperación de cuenta. |
| **MFA (Multi-Factor Authentication)** | Habilitar MFA para todas las cuentas, especialmente root.          |
| **Least Privilege Principle**         | Otorgar permisos mínimos necesarios.                               |
| **Rotación de credenciales**          | Rotar claves de acceso regularmente.                               |
| **Uso de roles en lugar de claves**   | Reemplazar credenciales estáticas por roles temporales.            |
| **Auditorías periódicas**             | Revisar políticas y accesos mediante AWS IAM Access Analyzer.      |

> 🔒 *IAM es el cimiento de la seguridad en AWS. Su correcta implementación garantiza un control granular, auditabilidad y protección efectiva contra accesos no autorizados.*
