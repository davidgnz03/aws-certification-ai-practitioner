# ✅ Compliance for AI  
## Cumplimiento Normativo en la Inteligencia Artificial

El cumplimiento (*compliance*) en la AI busca garantizar que los sistemas cumplan con **leyes, regulaciones, estándares de seguridad y principios éticos**.  
Es esencial para organizaciones que operan en sectores **altamente regulados**, como la banca, la salud o la industria aeroespacial.

---

## 🏛️ Regulated Workloads  
*(Cargas de trabajo reguladas)*

Algunos sectores requieren **niveles adicionales de cumplimiento normativo** debido a la sensibilidad de los datos y las consecuencias de los errores.

### Industrias Típicamente Reguladas
- 🏦 **Servicios Financieros** — préstamos, hipotecas, inversiones.  
- 🏥 **Salud (Healthcare)** — registros médicos, diagnósticos, seguros.  
- ✈️ **Aeroespacial y Defensa** — seguridad y datos críticos de misión.  

### Ejemplos de Regulated Workloads
- **Reportes regulatorios** enviados a agencias gubernamentales (como la SEC o FDA).  
- **Aplicaciones reguladas**, por ejemplo:
  - Procesos de **hipotecas** y **evaluaciones de crédito**.  
  - Decisiones automatizadas que impactan a personas (como aprobaciones o rechazos).  

> 📋 *Si tu sistema AI debe cumplir con auditorías, archivado de datos o requisitos especiales de seguridad, estás operando un **workload regulado***.

---

## ⚖️ AI Standard Compliance Challenges  
*(Desafíos del cumplimiento normativo en AI)*

El cumplimiento normativo en inteligencia artificial presenta retos únicos debido a la **naturaleza dinámica y opaca** de los modelos de aprendizaje automático.

### 1. 🧩 **Complexity and Opacity**
- Los sistemas AI suelen ser **cajas negras** difíciles de auditar.  
- Los auditores y reguladores necesitan entender **cómo se toman las decisiones**.  

### 2. 🔄 **Dynamism and Adaptability**
- Los modelos **evolucionan con el tiempo**: cambian según nuevos datos, ajustes o entrenamiento continuo.  
- Esto dificulta mantener registros coherentes de decisiones previas.

### 3. ⚗️ **Emergent Capabilities**
- Los modelos grandes pueden desarrollar **capacidades no previstas** durante su entrenamiento (comportamientos inesperados o no intencionados).  

### 4. ⚠️ **Unique Risks**
Incluye sesgos, violaciones de privacidad o propagación de desinformación.

#### 🔹 Algorithmic Bias
- Ocurre cuando los **datos de entrenamiento no son representativos**, reflejando prejuicios sociales o estructurales.  
- El modelo puede **perpetuar o amplificar** esas desigualdades.  

#### 🔹 Human Bias
- Los **humanos que diseñan** o etiquetan los datos pueden introducir sus propios sesgos cognitivos.  

### 5. 📘 **Algorithm Accountability**
- Los algoritmos deben ser **transparentes, explicables y auditables**.  
- Regulaciones emergentes en:
  - 🇪🇺 **Artificial Intelligence Act (UE)** — exige transparencia, clasificación por niveles de riesgo y documentación exhaustiva.  
  - 🇺🇸 **Estados Unidos** — varias leyes estatales y locales sobre explicabilidad y no discriminación algorítmica.

> 🧠 *El cumplimiento en AI no es solo un requisito legal: es un requisito de confianza.*

---

## ☁️ AWS Compliance  
*(Cumplimiento normativo en Amazon Web Services)*

AWS ofrece una de las infraestructuras **más auditadas y certificadas del mundo**, con más de **140 certificaciones y estándares** de seguridad y cumplimiento.

### 🔒 Principales Estándares y Certificaciones

| **Organismo / Norma** | **Descripción / Enfoque** |
|------------------------|---------------------------|
| **NIST (National Institute of Standards and Technology)** | Estándares federales de seguridad y control en EE. UU. |
| **ENISA (European Union Agency for Cybersecurity)** | Normas europeas para la protección de sistemas y datos. |
| **ISO (International Organization for Standardization)** | Certificaciones ISO/IEC 27001, 27017, 27018 — seguridad, privacidad y cloud compliance. |
| **SOC (System and Organization Controls)** | Auditorías independientes sobre controles internos de seguridad y confidencialidad. |
| **HIPAA (Health Insurance Portability and Accountability Act)** | Protección de datos médicos y cumplimiento en sistemas de salud. |
| **GDPR (General Data Protection Regulation)** | Protección de datos personales en la Unión Europea. |
| **PCI DSS (Payment Card Industry Data Security Standard)** | Cumplimiento para manejo de datos de tarjetas de crédito. |

> ✅ *AWS proporciona documentación, controles y auditorías para ayudarte a mantener tus soluciones de AI dentro del marco regulatorio apropiado.*

---

## 🧾 Model Cards  
*(Tarjetas de modelo para la trazabilidad y auditoría de AI)*

Las **Model Cards** son documentos estandarizados para **registrar información crítica** sobre un modelo de Machine Learning.

### 📋 Contenido Típico

| **Sección** | **Descripción** |
|--------------|-----------------|
| **Model Overview** | Descripción general del modelo, su propósito e identificación. |
| **Intended Use** | Casos de uso previstos y restricciones. |
| **Training Data** | Origen, licencias y sesgos conocidos de los datos usados para entrenar. |
| **Performance Metrics** | Precisión, robustez, y resultados de evaluación. |
| **Risk Rating** | Nivel de riesgo y limitaciones identificadas. |
| **Ethical Considerations** | Consideraciones sobre impacto social o sesgos. |
| **Source Citations** | Referencias de datasets, documentación o fuentes. |

### 📘 Beneficios
- Facilitan **auditorías** y procesos regulatorios.  
- Mejoran la **transparencia y confianza** entre equipos y clientes.  
- Documentan el **ciclo de vida completo** del modelo.  

### 🔹 En el Ecosistema AWS

- **SageMaker Model Cards:** permiten documentar modelos directamente desde la consola AWS.  
- Se integran con **Model Registry** y **Model Dashboard** para mantener trazabilidad completa.  
- **AI Service Cards (AWS):** ejemplo de *responsible AI documentation* aplicada a servicios de inteligencia artificial gestionados.

> 🧩 *Las Model Cards son la base documental de una AI responsable, auditable y conforme a la regulación.*

---

## 🧭 En Resumen

| **Área** | **Desafío / Requisito** | **Solución o Herramienta AWS** |
|-----------|--------------------------|-------------------------------|
| **Regulated Workloads** | Cumplimiento en sectores sensibles. | AWS Compliance Programs, auditorías SOC, HIPAA, PCI DSS. |
| **Algorithmic Bias** | Riesgo de sesgo en datos o decisiones. | SageMaker Clarify, Data Wrangler. |
| **Transparency** | Falta de trazabilidad de decisiones. | Model Cards, Service Cards, Model Dashboard. |
| **Auditability** | Dificultad para revisión externa. | SageMaker Model Registry + AWS Audit Manager. |
| **Legal Compliance** | Requisitos regionales (GDPR, AI Act, etc.). | AWS Artifact, AWS Compliance Hub. |

---

> 🧠 *El cumplimiento normativo no solo protege a las organizaciones, sino que garantiza que la Inteligencia Artificial actúe de forma ética, segura y responsable.*
