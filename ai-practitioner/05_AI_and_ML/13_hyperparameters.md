# Hyperparameter Tuning

## 🧠 What are Hyperparameters?

**Hyperparameters** are **configuration settings** that define the **structure of a model** and **control the learning process** during training.  
Unlike model parameters (which are learned automatically), hyperparameters are **set manually before training begins**.

They influence how well the model learns, how fast it converges, and whether it overfits or underfits the data.

### 🔧 Examples of Common Hyperparameters
- **Learning Rate:** Determines how much to adjust the model’s weights during training.  
- **Batch Size:** Number of samples processed before the model updates its parameters.  
- **Number of Epochs:** How many times the model iterates through the entire dataset.  
- **Regularization:** Controls model complexity to avoid overfitting.  

> ⚙️ *Choosing the right hyperparameters can make the difference between a high-performing model and one that fails to generalize.*

---

## 🎯 What is Hyperparameter Tuning?

**Hyperparameter Tuning** is the process of finding the **best combination of hyperparameter values** that optimize the model’s performance.  
The goal is to **maximize accuracy**, **minimize error**, and **enhance generalization** to unseen data.

### ✅ Benefits
- Improves overall model accuracy.  
- Reduces overfitting.  
- Enhances stability and generalization.  
- Speeds up convergence during training.

---

## ⚙️ How to Perform Hyperparameter Tuning

Existen varias estrategias para encontrar los valores óptimos:

### 🔹 **Grid Search**
- Prueba todas las combinaciones posibles de hiperparámetros dentro de un conjunto predefinido.  
- Exhaustivo pero costoso en tiempo y recursos.  
- Ideal para conjuntos de hiperparámetros pequeños.

### 🔹 **Random Search**
- Prueba combinaciones **aleatorias** dentro de un rango definido.  
- Más eficiente cuando hay muchos hiperparámetros posibles.  
- Mayor probabilidad de encontrar una buena combinación más rápido.

### 🔹 **Automated Tuning (AWS SageMaker AMT)**
- AWS **SageMaker Automatic Model Tuning (AMT)** optimiza automáticamente los hiperparámetros.  
- Usa técnicas como **Bayesian Optimization** para encontrar configuraciones óptimas basadas en resultados anteriores.  
- Reduce el tiempo manual y mejora la eficiencia del proceso de tuning.

> ☁️ *AWS SageMaker AMT entrena múltiples modelos en paralelo con diferentes combinaciones de hiperparámetros y selecciona el mejor basado en una métrica objetivo.*

---

## 🔍 Important Hyperparameters and Their Roles

### ⚡ **Learning Rate**
Define el tamaño del paso que da el modelo al ajustar los pesos durante el entrenamiento.

- **Alta learning rate:**  
  - Convergencia más rápida.  
  - Riesgo de **“overshooting”** (no alcanzar el mínimo óptimo).  
- **Baja learning rate:**  
  - Entrenamiento más lento.  
  - Puede lograr **mayor precisión final**, pero con más iteraciones.  

> 🎯 *Busca un equilibrio: demasiado alto → inestable; demasiado bajo → lento o estancado.*

---

### 📦 **Batch Size**
Número de ejemplos utilizados para actualizar los pesos del modelo en una iteración.

- **Batch pequeño:**  
  - Entrenamiento más estable (mejor generalización).  
  - Mayor tiempo de cómputo.  
- **Batch grande:**  
  - Entrenamiento más rápido.  
  - Puede perder precisión y estabilidad.  

> 💡 *En la práctica, los tamaños comunes son potencias de 2 (32, 64, 128, 256).*

---

### 🔁 **Number of Epochs**
Número de veces que el modelo recorre **todo el dataset de entrenamiento**.

- Muy pocos epochs → **underfitting** (no aprende lo suficiente).  
- Demasiados epochs → **overfitting** (aprende ruido del dataset).  

> 🧩 *Utiliza “early stopping” para detener el entrenamiento automáticamente cuando el rendimiento ya no mejora.*

---

### 🧱 **Regularization**
Controla el equilibrio entre un modelo **simple** (que generaliza bien) y uno **complejo** (que puede sobreajustarse).

- **Alta regularización:** reduce overfitting, pero puede subajustar.  
- **Baja regularización:** aumenta precisión, pero puede memorizar datos.  

**Técnicas comunes:**
- **L1/L2 Regularization:** penalizan pesos grandes.  
- **Dropout:** apaga aleatoriamente neuronas durante el entrenamiento.  
- **Weight Decay:** reduce el valor absoluto de los pesos.

---

## ⚠️ Overfitting and How to Prevent It

### 🔍 What is Overfitting?

El **overfitting** ocurre cuando el modelo:
- Tiene **excelente rendimiento en el conjunto de entrenamiento**, pero  
- **falla con datos nuevos** o no vistos.  

### 🧩 Causes of Overfitting
- Tamaño del dataset demasiado pequeño.  
- Entrenamiento excesivo (demasiados epochs).  
- Modelo demasiado complejo (demasios parámetros).  
- Falta de regularización.  

---

### 🧠 How to Prevent Overfitting

| Estrategia | Descripción |
|-------------|-------------|
| **Increase Training Data Size** | Aumentar la cantidad de datos ayuda al modelo a generalizar mejor. |
| **Early Stopping** | Detener el entrenamiento cuando la métrica de validación deja de mejorar. |
| **Data Augmentation** | Crear nuevas muestras modificando ligeramente los datos existentes (rotación, ruido, etc.). |
| **Regularization** | Aplicar penalizaciones (L1/L2, dropout) para evitar sobreajuste. |
| **Adjust Hyperparameters** | Cambiar learning rate, batch size o epochs para optimizar el equilibrio. |

> ⚙️ *El objetivo es lograr que el modelo aprenda los patrones reales, no el ruido.*

---

## 📊 Hyperparameter Tuning Workflow

```plaintext
Set Initial Hyperparameters
       ↓
Train Model
       ↓
Evaluate Performance
       ↓
Adjust Hyperparameters (Grid, Random, AMT)
       ↓
Retrain Model
       ↓
Select Best Configuration
```

## 🧠 Conclusión

El **Hyperparameter Tuning** es una fase crítica para mejorar la calidad del modelo.  
A través de técnicas sistemáticas o automáticas, se busca **el punto óptimo entre rendimiento, estabilidad y generalización**.

> 🚀 Un modelo bien ajustado aprende rápido, predice mejor y se adapta más fácilmente a nuevos escenarios.