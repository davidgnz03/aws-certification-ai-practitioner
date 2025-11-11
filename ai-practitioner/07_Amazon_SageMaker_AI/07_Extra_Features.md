# ⚙️ SageMaker Extra Features

Además de sus potentes capacidades principales, **Amazon SageMaker** incluye funciones avanzadas diseñadas para **reforzar la seguridad, el aislamiento de red y la precisión predictiva** en escenarios especializados como el pronóstico de series temporales.

---

## 🔒 Network Isolation Mode

El **Network Isolation Mode** permite ejecutar **contenedores de SageMaker sin acceso a Internet**, garantizando un entorno completamente aislado y seguro.

### 🧠 Características Principales

- **Sin salida a Internet (outbound access)**  
  Los trabajos (jobs) que se ejecutan en este modo no pueden comunicarse con recursos externos a la VPC ni acceder a Internet.

- **Aislamiento total de red**  
  El contenedor del entrenamiento o inferencia se ejecuta en un entorno controlado sin conexión externa.

- **Seguridad reforzada**  
  Este modo evita fugas de datos o dependencias no verificadas, garantizando cumplimiento en entornos regulados (por ejemplo, *banca o sector salud*).

- **Sin acceso incluso a Amazon S3**  
  Si el acceso a datos es necesario, debe realizarse mediante **VPC Endpoints** o **S3 PrivateLink**, no de forma directa.

### 💡 Ejemplo de Uso

> 🔐 *Ideal para entrenar modelos con datos confidenciales o en entornos donde las políticas de seguridad prohíben cualquier conexión saliente.*

---

## 📈 SageMaker DeepAR Forecasting Algorithm

**SageMaker DeepAR** es un algoritmo de **pronóstico de series temporales (time series forecasting)** basado en **Recurrent Neural Networks (RNN)**, desarrollado por Amazon para realizar predicciones precisas en datos secuenciales.

### 🧩 Características Clave

- **Basado en RNNs (Recurrent Neural Networks)**  
  Aprovecha redes neuronales recurrentes para capturar dependencias temporales complejas.

- **Aprendizaje de patrones globales**  
  Entrena simultáneamente en múltiples series temporales para mejorar la precisión en pronósticos individuales.

- **Escalable y eficiente**  
  Diseñado para manejar **millones de series temporales** en paralelo.

- **Predicciones probabilísticas**  
  Genera intervalos de confianza y distribuciones completas, no solo un valor puntual.

- **Compatibilidad con SageMaker Inference**  
  Una vez entrenado, el modelo puede desplegarse para inferencia en tiempo real o por lotes (batch).

### 📊 Casos de Uso

- Predicción de demanda de productos o inventario.  
- Pronóstico de tráfico web o actividad de usuarios.  
- Proyecciones financieras o de ventas.  
- Carga energética o consumo de recursos.

> 📈 *DeepAR es el motor detrás de muchos modelos de forecasting de Amazon, diseñado para capturar patrones temporales con mayor precisión que los métodos estadísticos tradicionales.*

---

## 💡 En Resumen

| **Función** | **Descripción** | **Beneficio Principal** |
|--------------|------------------|--------------------------|
| **Network Isolation Mode** | Ejecuta contenedores sin acceso a Internet ni S3. | Máxima seguridad y cumplimiento regulatorio. |
| **DeepAR Forecasting** | Algoritmo RNN para pronóstico de series temporales. | Predicciones precisas, escalables y probabilísticas. |

> 🔒 *Con estas características, SageMaker refuerza tanto la **seguridad** del entorno como la **potencia predictiva** de los modelos.*
