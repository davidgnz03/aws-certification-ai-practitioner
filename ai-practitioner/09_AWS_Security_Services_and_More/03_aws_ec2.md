# 💻 Amazon EC2  
## Elastic Compute Cloud

---

### 🧱 Overview

**Amazon EC2 (Elastic Compute Cloud)** es uno de los servicios más populares y fundamentales de AWS.  
Forma parte del modelo **IaaS (Infrastructure as a Service)** y proporciona **capacidad de cómputo escalable bajo demanda** en la nube.

> ⚙️ *EC2 te permite lanzar servidores virtuales (llamados “instancias”) para ejecutar aplicaciones en AWS.*

---

## 🧩 Core Capabilities of EC2

| **Función** | **Descripción** |
|--------------|-----------------|
| **Renting Virtual Machines (EC2 Instances)** | Ejecuta sistemas operativos y aplicaciones personalizadas en máquinas virtuales en la nube. |
| **Storing Data on Virtual Drives (EBS)** | Usa **Amazon EBS (Elastic Block Store)** como almacenamiento persistente para las instancias EC2. |
| **Distributing Load Across Machines (ELB)** | Balancea el tráfico de red con **Elastic Load Balancer**, distribuyendo la carga entre múltiples instancias. |
| **Scaling Services Automatically (ASG)** | Escala automáticamente la capacidad de cómputo con **Auto Scaling Groups** según demanda o métricas. |

> 💡 *La combinación de EC2 + EBS + ELB + ASG representa la base de una infraestructura escalable y resiliente en AWS.*

---

## ⚙️ EC2 Sizing & Configuration Options

Cada instancia EC2 puede configurarse según las necesidades de rendimiento, memoria, red y almacenamiento.  
AWS ofrece **familias de instancias** adaptadas a distintos casos de uso.

### 🧩 EC2 Instance Families

| **Familia** | **Uso principal** | **Ejemplo de tipo** |
|--------------|-------------------|----------------------|
| **General Purpose** | Balance entre cómputo, memoria y red. | `t3`, `t4g`, `m6i` |
| **Compute Optimized** | Cómputo intensivo, CPU de alto rendimiento. | `c6i`, `c7g` |
| **Memory Optimized** | Procesamiento intensivo de memoria (bases de datos, caching). | `r6g`, `x2idn` |
| **Storage Optimized** | Alta capacidad de almacenamiento y throughput. | `i3`, `i4i`, `d3` |
| **Accelerated Computing (GPU)** | Machine Learning, renderizado, cálculos científicos. | `p4d`, `g5`, `inf2`, `trn1` |
| **High Performance Computing (HPC)** | Redes de baja latencia, cargas masivas. | `hpc6id`, `c7gn` |

> 🔍 *Cada tipo de instancia combina CPU, RAM, almacenamiento y red con una nomenclatura específica (ejemplo: `m6i.large`).*

---

### 🧮 EC2 Instance Attributes

| **Atributo** | **Descripción** |
|---------------|-----------------|
| **vCPU** | Número de núcleos virtuales asignados. |
| **RAM** | Memoria asignada a la instancia. |
| **EBS Storage** | Tamaño y tipo del volumen raíz y adicionales (SSD/HDD). |
| **Network Performance** | Ancho de banda y número de interfaces de red (ENIs). |
| **Tenancy** | Dedicada o compartida. |
| **AMI (Amazon Machine Image)** | Imagen base con sistema operativo preinstalado (Linux, Windows, etc.). |
| **Security Groups** | Firewall virtual que controla el tráfico entrante y saliente. |
| **Key Pair** | Par de claves SSH usado para acceder a la instancia. |

---

## 🧰 EC2 User Data

El campo **User Data** permite ejecutar **scripts automáticamente al iniciar una instancia**.  
Se usa comúnmente para:
- Instalar paquetes o dependencias.
- Configurar servicios (web servers, aplicaciones).
- Registrar la instancia en sistemas externos.

### 💻 Example: Install Apache Web Server on Launch

```bash
#!/bin/bash
yum update -y
yum install -y httpd
systemctl enable httpd
systemctl start httpd
echo "Hello from EC2 $(hostname)" > /var/www/html/index.html
```

📦 El script anterior instala Apache y crea una página de bienvenida automáticamente al iniciar la instancia.

> ⚙️ *User Data se ejecuta solo la primera vez que se lanza la instancia (a menos que se configure lo contrario).*

---

## 🧩 Integration with Other AWS Services

| **Servicio**                    | **Integración con EC2**                                     |
| ------------------------------- | ----------------------------------------------------------- |
| **Amazon S3**                   | Almacenamiento de backups, logs o datos estáticos.          |
| **Amazon CloudWatch**           | Monitoreo de métricas de CPU, red, disco y alarmas.         |
| **AWS Systems Manager (SSM)**   | Gestión remota, ejecución de comandos y parches.            |
| **AWS Lambda**                  | Automatización y eventos que inician/paran instancias.      |
| **Elastic Load Balancer (ELB)** | Distribuye el tráfico entrante entre varias instancias EC2. |
| **Auto Scaling Group (ASG)**    | Ajusta la cantidad de instancias EC2 según demanda.         |

---

## 🧱 Key Takeaways

- **EC2 = Elastic Compute Cloud** → Infraestructura bajo demanda.
- **Componentes clave:** Instancias, EBS, ELB, ASG.
- **Configuración flexible:** AMI, tipo de instancia, tamaño, seguridad.
- **User Data:** automatiza la configuración inicial.
- **Escalabilidad:** autoscaling + load balancing = resiliencia total.

> 💡 *Dominar EC2 es esencial para comprender la base de cualquier arquitectura en la nube de AWS.*
