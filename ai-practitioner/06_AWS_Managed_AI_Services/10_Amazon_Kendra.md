# Amazon Kendra

**Amazon Kendra** es un servicio completamente administrado de **búsqueda inteligente de documentos** impulsado por **Machine Learning (ML)**.  
Permite realizar búsquedas en lenguaje natural y obtener **respuestas precisas directamente desde el contenido de los documentos**, no solo coincidencias de palabras clave.

> 🔍 *Kendra convierte tus documentos en una base de conocimiento inteligente.*

---

## 🧠 Características Principales

- **Servicio totalmente administrado:** sin necesidad de construir ni mantener una infraestructura de búsqueda.  
- **Natural Language Search (búsqueda en lenguaje natural):** los usuarios pueden escribir preguntas como lo harían con una persona (“¿Dónde está el departamento de TI?”).  
- **Extracción contextual:** devuelve respuestas exactas desde dentro de los documentos (no solo enlaces).  
- **Aprendizaje incremental:** mejora automáticamente sus resultados basándose en interacciones y retroalimentación de los usuarios.  
- **Ajuste manual de relevancia:** puedes modificar la importancia de fuentes, fechas, frescura o categorías para personalizar los resultados.  
- **Seguridad integrada:** hereda los permisos de acceso de tus fuentes de datos, garantizando resultados seguros y personalizados.

> 💡 *Kendra entiende el significado detrás de las palabras, no solo las palabras mismas.*

---

## 🧩 Ejemplo de Flujo de Búsqueda

**Consulta del usuario:**
> “¿Dónde está la mesa de soporte técnico?”

**Flujo de procesamiento:**
```
Amazon S3 / RDS / Google Drive / SharePoint → Indexación en Amazon Kendra → Knowledge Index (ML) → Usuario
```


**Respuesta:**
> 🗨️ *“El soporte técnico se encuentra en el primer piso.”*

> 🧠 *Kendra encuentra la respuesta exacta dentro del documento relevante.*

---

## 📚 Fuentes de Datos Compatibles

Kendra puede conectarse a múltiples **repositorios de información** para crear un índice de conocimiento centralizado:

| Fuente de Datos | Ejemplos |
|------------------|----------|
| **Amazon S3** | Documentos, manuales, PDFs, reportes. |
| **Amazon RDS / Aurora** | Bases de datos estructuradas. |
| **Microsoft SharePoint / OneDrive** | Documentos empresariales y colaborativos. |
| **Google Drive** | Archivos, hojas, presentaciones. |
| **Salesforce** | Artículos de conocimiento, FAQs, registros de clientes. |
| **ServiceNow** | Tickets, incidentes, documentación de soporte. |
| **Confluence / Jira** | Documentación técnica o de proyectos. |
| **Web Crawlers** | Indexación de sitios web internos o externos. |

> ⚙️ *Puedes combinar múltiples fuentes para crear un “conocimiento unificado” en una sola búsqueda.*

---

## 🧱 Proceso de Indexación

1. **Conectores de datos:** Kendra se conecta a tus fuentes (S3, Drive, SharePoint…).  
2. **Ingesta e indexación:** analiza los documentos y crea un **índice de conocimiento** optimizado.  
3. **Procesamiento con ML:** aplica modelos de lenguaje natural para comprender contexto, sinónimos y relevancia.  
4. **Búsqueda inteligente:** los usuarios formulan preguntas o palabras clave.  
5. **Respuestas contextuales:** Kendra entrega la información precisa directamente del contenido.  

**Ejemplo de flujo:**
```
Amazon S3 → Amazon Kendra (Indexación) → Knowledge Index (ML) → Usuario
```


---

## 🧠 Incremental Learning (Aprendizaje Incremental)

- Aprende de las **interacciones de los usuarios** (qué resultados seleccionan o descartan).  
- Promueve resultados más relevantes con el tiempo.  
- Puede **ajustarse manualmente** para dar prioridad a documentos más recientes o fuentes más confiables.  

> 🔁 *Kendra se vuelve más precisa mientras más se usa.*

---

## ⚙️ Capacidades Clave

| Capacidad | Descripción |
|------------|-------------|
| **Natural Language Query** | Interpreta preguntas humanas y busca respuestas contextuales. |
| **FAQ Matching** | Identifica y devuelve respuestas a preguntas frecuentes. |
| **Document Ranking** | Clasifica documentos según relevancia, fecha o popularidad. |
| **Incremental Learning** | Aprende de la interacción del usuario. |
| **Custom Relevance Tuning** | Ajusta la importancia de atributos (por ejemplo, autor, fecha, categoría). |
| **Access Control Integration** | Aplica permisos y políticas de acceso desde las fuentes de datos. |
| **Multi-language Support** | Compatible con múltiples idiomas (inglés, español, francés, alemán, etc.). |

---

## 💬 Ejemplo Práctico

Un empleado escribe en el portal interno:
> “¿Dónde puedo encontrar la política de vacaciones actualizada?”

**Amazon Kendra:**
- Busca en SharePoint, Google Drive y ServiceNow.  
- Encuentra el documento relevante.  
- Devuelve directamente la respuesta:
  > “La política de vacaciones se encuentra en la intranet, documento HR_Policy_V3.pdf, sección 4.”

> 🧩 *Reduce el tiempo de búsqueda de minutos a segundos.*

---

## ⚙️ Funcionalidades en la Consola de AWS

Desde la consola de **Amazon Kendra**, puedes:

| Funcionalidad | Descripción |
|----------------|-------------|
| **Create Index** | Crea un índice de conocimiento basado en ML. |
| **Add Data Sources** | Conecta tus repositorios (S3, SharePoint, Salesforce, etc.). |
| **Query Testing** | Prueba consultas y ajusta resultados. |
| **Synonym Management** | Agrega sinónimos o términos equivalentes. |
| **Relevance Tuning** | Ajusta manualmente los pesos de atributos y frescura. |
| **Access Control** | Configura políticas de seguridad y permisos por usuario. |
| **Analytics Dashboard** | Monitorea métricas de uso, consultas y rendimiento. |

---

## 💡 Beneficios Clave

- 🔍 **Búsqueda semántica precisa**: entiende el contexto de las preguntas.  
- ⚙️ **Integración flexible** con múltiples fuentes.  
- 📈 **Aprendizaje continuo** a través de feedback.  
- 🧠 **Respuestas exactas, no solo documentos.**  
- 🔐 **Seguridad empresarial** integrada con IAM y fuentes autenticadas.  
- 🌍 **Multilingüe y escalable.**

---

## 🧠 En Resumen

**Amazon Kendra** transforma la forma en que los empleados o clientes encuentran información.  
Usa Machine Learning para ofrecer **respuestas precisas, rápidas y seguras** desde documentos estructurados o no estructurados.

**Beneficios clave:**
- Búsqueda semántica en lenguaje natural.  
- Respuestas contextuales desde texto, PDF, Word, HTML, etc.  
- Aprendizaje incremental y relevancia ajustable.  
- Integración con más de 30 fuentes empresariales.  
- Despliegue rápido y mantenimiento mínimo.

> 🧩 *Amazon Kendra: del caos documental al conocimiento accesible.*
