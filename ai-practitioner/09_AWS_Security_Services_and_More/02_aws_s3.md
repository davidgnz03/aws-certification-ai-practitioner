# 🪣 Amazon S3  
## Simple Storage Service

---

### 🧱 Overview

**Amazon S3 (Simple Storage Service)** es uno de los **principales pilares de AWS**.  
Permite almacenar y recuperar **objetos (archivos)** desde cualquier lugar del mundo, ofreciendo **escalabilidad, durabilidad (99.999999999%) y disponibilidad**.  

Muchos servicios de AWS integran Amazon S3 como almacenamiento base, incluyendo **CloudFront, Athena, Glue, Redshift, Lambda**, entre otros.

> 💡 *S3 es el almacenamiento central para datos, copias de seguridad, análisis y contenido estático.*

---

## 🧩 Common Use Cases

| **Use Case** | **Descripción** |
|---------------|-----------------|
| **Backup & Storage** | Almacenamiento seguro y escalable para copias de seguridad y archivos críticos. |
| **Disaster Recovery** | Punto de recuperación para entornos críticos con replicación entre regiones. |
| **Archive** | Retención a largo plazo de datos con bajo costo (usando S3 Glacier). |
| **Hybrid Cloud Storage** | Integración con sistemas locales mediante AWS Storage Gateway. |
| **Application Hosting** | Almacenamiento de recursos para aplicaciones web o móviles. |
| **Media Hosting** | Distribución de contenido multimedia (videos, imágenes, documentos). |
| **Data Lakes & Analytics** | Base de datos central para análisis con Athena, Glue, EMR, Redshift. |
| **Software Delivery** | Distribución de binarios, instaladores o actualizaciones. |
| **Static Website Hosting** | Hospedaje de sitios web estáticos (HTML, CSS, JS) directamente desde S3. |

---

## 🪣 AWS S3 – Buckets

### 📦 Buckets Overview
- Los **Buckets** son **contenedores lógicos** que almacenan objetos (archivos).  
- Cada bucket debe tener un **nombre globalmente único** (a nivel mundial).  
- Aunque S3 parece un servicio global, los **buckets se crean en una región específica**.

### 🏷️ Naming Convention
- Letras minúsculas, números y guiones (`-`) son permitidos.  
- Ejemplo: `my-company-backups-eu-west-1`  
- No pueden contener espacios, mayúsculas ni caracteres especiales.

### 🌍 Regionality
- Los buckets se asocian a una **región** (p. ej., `us-east-1`, `eu-west-1`), lo cual:
  - Permite optimizar latencia y cumplimiento regulatorio.
  - Evita costos innecesarios de transferencia entre regiones.

> 📌 *“S3 looks global, but buckets live in specific regions.”*

---

## 📁 AWS S3 – Objects

### 🧱 Object Structure

| **Componente** | **Descripción** |
|-----------------|-----------------|
| **Key** | Es la **ruta completa (FULL PATH)** del objeto dentro del bucket. Ejemplo: `photos/2025/january/image.png`. |
| **Prefix** | Parte del nombre de la clave antes del último `/`. Ejemplo: `photos/2025/january/`. |
| **Object Name** | Nombre final del archivo (`image.png`). |
| **Value (Body)** | Contenido binario o de texto del archivo. Tamaño máximo: **5 TB** (usa *multipart upload* para > 5 GB). |
| **Metadata** | Pares clave-valor que describen el objeto (tipo MIME, fecha, etc.). |
| **Tags** | Etiquetas personalizadas para clasificar y administrar objetos. |
| **Version ID** | Identificador único cuando la versión está habilitada en el bucket. |

### 🧭 Directory Structure
- S3 **no tiene directorios reales**, solo **claves largas con slashes** que simulan jerarquías.  
- Ejemplo:

```plaintext
bucket-name/
├── logs/2025/01/access.log
├── media/videos/movie.mp4
└── media/images/photo.png
```


> 🧩 *Las “carpetas” en S3 son una convención visual del prefijo de las claves.*

---

## 🧊 Amazon S3 Storage Classes

Cada **Storage Class** ofrece distintos niveles de **costo, durabilidad, y disponibilidad**, adaptándose al patrón de acceso a los datos.

| **Storage Class** | **Uso Principal** | **Durabilidad** | **Disponibilidad** | **Costo** | **Notas** |
|--------------------|------------------|-----------------|-------------------|------------|------------|
| **S3 Standard (General Purpose)** | Acceso frecuente | 99.999999999% | 99.99% | 💲💲 | Ideal para datos de uso activo (apps, sitios web). |
| **S3 Standard-IA (Infrequent Access)** | Acceso infrecuente | 99.999999999% | 99.9% | 💲 | Menor costo de almacenamiento; costo por recuperación. |
| **S3 One Zone-IA** | Acceso infrecuente en una sola zona AZ | 99.999999999% | 99.5% | 💲 | No replicado entre zonas; útil para backups no críticos. |
| **S3 Glacier Instant Retrieval** | Archivos archivados que requieren acceso rápido | 99.999999999% | 99.9% | 💲 | Recuperación en milisegundos. |
| **S3 Glacier Flexible Retrieval** | Archivos de largo plazo | 99.999999999% | 99.9% | 💲 | Recuperación en minutos u horas (antes “S3 Glacier”). |
| **S3 Glacier Deep Archive** | Archivos históricos, respaldo a largo plazo | 99.999999999% | 99.9% | 💵 | Recuperación en horas (12–48h). |
| **S3 Intelligent-Tiering** | Automático según el patrón de acceso | 99.999999999% | 99.9% | Variable | Mueve objetos entre clases según uso, sin impacto de latencia. |

> ⚙️ *Puedes mover objetos manualmente o mediante políticas de **S3 Lifecycle Configuration**.*

---

### 🔄 Lifecycle Management

- **S3 Lifecycle Rules** permiten **automatizar la transición** de objetos entre clases o su **eliminación programada**.
- Ejemplo:
- Día 0: S3 Standard  
- Día 30: Mover a Standard-IA  
- Día 180: Mover a Glacier Deep Archive  
- Día 365: Eliminar

---

> 🪣 *Amazon S3 combina simplicidad, durabilidad y flexibilidad — una base esencial para cualquier arquitectura en AWS.*
