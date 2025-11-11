# Amazon Rekognition

**Amazon Rekognition** es un servicio de **Machine Learning (ML)** completamente administrado que permite **analizar imágenes y videos** para detectar **objetos, personas, texto, escenas, y actividades** de forma automática.  

Además, ofrece capacidades avanzadas de **análisis y búsqueda facial**, **moderación de contenido**, y **detección de texto o logotipos**, todo sin necesidad de construir o entrenar modelos desde cero.

---

## 🧠 Características Principales

- **Detección de objetos, personas, texto, y escenas** en imágenes o videos.  
- **Análisis facial y búsqueda de rostros** para verificación de usuarios o conteo de personas.  
- **Comparación de rostros** con bases de datos o reconocimiento de celebridades.  
- **Etiquetado automático (Labeling)** con categorías predefinidas por AWS.  
- **Moderación de contenido** visual para detectar material inapropiado u ofensivo.  
- **Análisis de trayectorias (Pathing)** para analizar movimientos, por ejemplo, en eventos deportivos.  

> 💡 *Amazon Rekognition analiza imágenes o secuencias de video con precisión a nivel humano, pero a escala de máquina.*

---

## 🎯 Casos de Uso

- **Etiquetado automático de imágenes y videos (Labeling).**  
  Clasifica automáticamente los elementos visibles (animales, vehículos, logos, escenas, etc.).

- **Moderación de contenido.**  
  Detecta material sensible o inapropiado en redes sociales, medios o publicidad.

- **Detección y análisis facial.**  
  Determina atributos como **género, rango de edad, emociones o presencia de accesorios**.

- **Búsqueda y verificación facial.**  
  Compara rostros con una base de datos de “rostros conocidos” para verificación o identificación.

- **Reconocimiento de celebridades.**  
  Identifica celebridades en contenido multimedia (útil en medios y entretenimiento).

- **Pathing (seguimiento de movimiento).**  
  Analiza el movimiento de objetos o personas, como jugadores en un evento deportivo.

> ⚙️ *Por ejemplo, la NFL usa Rekognition para identificar logotipos en fotografías deportivas.*

---

## 🧩 Custom Labels (Etiquetas Personalizadas)

**Amazon Rekognition Custom Labels** te permite **entrenar tus propios modelos personalizados** sin requerir experiencia en ML.  
Puedes detectar **objetos o escenas específicas** para tu negocio, como **tu logo, productos o maquinaria.**

### Cómo Funciona:

1. **Etiqueta tus imágenes de entrenamiento.**  
   Identifica manualmente los objetos o categorías que te interesan.

2. **Almacena las imágenes en Amazon S3.**

3. **Entrena un modelo personalizado en Rekognition Custom Labels.**  
   Solo se necesitan unas **pocas centenas de imágenes**.

4. **Analiza nuevas imágenes**: el modelo reconocerá tus categorías personalizadas.

**Ejemplo de flujo:**

```plaintext
Amazon S3 (Training Images)
            ↓
Amazon Rekognition - Custom Labels
            ↓
Modelo personalizado
            ↓
Nuevas imágenes → Clasificación personalizada
```

> 🧠 *Ideal para detectar logotipos, productos, uniformes o maquinaria industrial.*

---

## 🧱 Content Moderation (Moderación de Contenido)

Amazon Rekognition puede **detectar automáticamente contenido inapropiado u ofensivo**, reduciendo la necesidad de revisión manual.

### Capacidades:

- Detección de **violencia, desnudos, lenguaje gráfico, o material explícito**.  
- **Filtrado automático** de imágenes o videos en redes sociales o transmisiones en vivo.  
- **Reducción de revisión humana** a solo un **1–5% del contenido total**.  
- Integración con **Amazon Augmented AI (A2I)** para revisión humana opcional.  

**Ejemplo de flujo:**
```
Usuario → Sube imagen
                ↓
Amazon Rekognition → DetectModerationLabels API
                ↓
Etiquetas (labels) de contenido → “Pass” o “Fail”
                ↓
(A2I) Revisión humana opcional 1–5%
```


---

### 🧩 Custom Moderation Adaptors

Los **Custom Moderation Adaptors** extienden las capacidades de moderación al permitirte **entrenar Rekognition con tus propios conjuntos de datos etiquetados**.

- Aumentan la precisión de la moderación.  
- Permiten crear **casos específicos de revisión visual** (por ejemplo, contenido inapropiado solo para ciertas culturas o marcas).  
- Se integran con **Amazon Augmented AI (A2I)** para validación humana opcional.

**Flujo resumido:**

```
Labeled Images → Rekognition Custom Moderation Adaptor
            ↓
Moderation Input → Pass/Fail
            ↓
Amazon Augmented AI (A2I) → 1–5% revisión humana
```


> ⚖️ *Equilibra la automatización del ML con la precisión del juicio humano.*

---

## ⚙️ Funcionalidades en la Consola de AWS

| Funcionalidad | Descripción |
|----------------|-------------|
| **Detect Labels** | Detecta objetos, personas y escenas automáticamente. |
| **Detect Faces** | Analiza atributos faciales (edad, género, emociones). |
| **Search Faces by Image** | Compara rostros con una colección existente. |
| **Content Moderation** | Identifica contenido sensible u ofensivo. |
| **Text in Image/Video** | Extrae texto de imágenes o marcos de video. |
| **Custom Labels** | Entrena modelos personalizados sin código. |
| **Pathing Analysis** | Rastrea movimiento de objetos o personas en video. |

---

## 🔗 Integraciones Comunes

- **Amazon S3** → Almacenamiento de imágenes y videos.  
- **AWS Lambda** → Procesamiento automático al cargar contenido.  
- **Amazon A2I** → Revisión humana de moderación o clasificación.  
- **Amazon SageMaker** → Entrenamiento adicional o validación de resultados.  
- **Amazon Kinesis Video Streams** → Análisis de video en tiempo real.  

---

## 🧠 En Resumen

**Amazon Rekognition** es una solución integral de visión por computadora que permite analizar imágenes y videos para identificar objetos, personas, texto, emociones y más, todo impulsado por ML.  

**Beneficios clave:**
- Detección y etiquetado automático de contenido visual.  
- Moderación inteligente de imágenes y videos.  
- Entrenamiento de modelos personalizados sin experiencia en ML.  
- Escalabilidad y precisión impulsadas por Deep Learning.  
- Integración perfecta con el ecosistema AWS.

> 🖼️ *Con Amazon Rekognition, tus imágenes “hablan” — detecta, clasifica y entiende lo que ves.*
