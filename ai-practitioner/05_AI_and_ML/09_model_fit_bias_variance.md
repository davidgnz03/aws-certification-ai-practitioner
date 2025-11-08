# Model Fit, Bias and Variance

## Introducción

En el desarrollo de modelos de Machine Learning, entender cómo se **ajusta el modelo a los datos** (model fit) y cómo se comportan los **errores de sesgo (bias)** y **varianza (variance)** es fundamental para lograr un rendimiento óptimo.  

> 🎯 El objetivo principal es encontrar un equilibrio entre un modelo que **aprenda lo suficiente** para generalizar correctamente, pero **sin memorizar** los datos de entrenamiento.

---

## ⚙️ Model Fit (Ajuste del Modelo)

El **ajuste del modelo** describe qué tan bien el modelo **aprende las relaciones subyacentes** entre las variables de entrada y salida de un conjunto de datos.

Existen tres posibles escenarios:

### 🧩 **1. Overfitting (Sobreajuste)**

- El modelo **aprende demasiado bien los datos de entrenamiento**, incluso los ruidos y patrones irrelevantes.  
- Aunque tiene excelente desempeño en el conjunto de entrenamiento, **falla al generalizar** a datos nuevos.  

**Síntomas:**
- Alta precisión en entrenamiento pero baja en validación.  
- El modelo memoriza en lugar de aprender.  

**Ejemplo:**
Un árbol de decisión muy profundo que clasifica perfectamente los datos conocidos, pero falla con nuevos ejemplos.

**Soluciones:**
- Simplificar el modelo (reducir complejidad).  
- Aplicar regularización (L1/L2, dropout).  
- Aumentar los datos de entrenamiento o usar *data augmentation*.

---

### ⚖️ **2. Balanced Fit (Ajuste Equilibrado)**

- El modelo **aprende las relaciones reales** entre las variables sin sobreajustarse.  
- Tiene un **rendimiento sólido tanto en entrenamiento como en prueba**.  
- Este es el escenario ideal.

> ✅ Un modelo balanceado logra **generalización**, es decir, buen desempeño en datos nunca vistos.

---

### 🪫 **3. Underfitting (Subajuste)**

- El modelo es **demasiado simple** para capturar los patrones de los datos.  
- No aprende adecuadamente ni siquiera en el conjunto de entrenamiento.  
- Usualmente ocurre por falta de complejidad o de características relevantes.

**Síntomas:**
- Baja precisión en entrenamiento y en validación.  
- Errores altos en ambos conjuntos.  

**Ejemplo:**
Usar una regresión lineal para un problema que tiene una relación no lineal.

**Soluciones:**
- Usar un modelo más complejo (ej. redes neuronales, ensembles).  
- Añadir más características o transformar las existentes.  
- Mejorar la calidad del dataset (limpieza, feature engineering).

---

## 🎯 Bias and Variance (Sesgo y Varianza)

El rendimiento de un modelo se ve afectado por dos fuentes principales de error:

- **Bias (Sesgo):** error sistemático que surge cuando el modelo no captura la verdadera relación entre las variables.  
- **Variance (Varianza):** error que refleja la sensibilidad del modelo a las variaciones del dataset de entrenamiento.

> ⚖️ La clave está en lograr un equilibrio entre ambos: **Bias-Variance Tradeoff**.

---

### 🧠 **Bias (Sesgo)**

**Definición:**
La diferencia entre las predicciones del modelo y los valores reales.  
Un sesgo alto implica que el modelo **simplifica demasiado** el problema y no logra aprender patrones relevantes.

**Causas:**
- Modelo demasiado simple (ej. usar una regresión lineal en datos no lineales).  
- Suposiciones incorrectas sobre la estructura del problema.  
- Falta de características relevantes.

**Ejemplo:**
```plaintext
Predicción del modelo: 50
Valor real: 80
Error por sesgo: 30
```


**Consecuencias:**
- El modelo **no se ajusta a los datos de entrenamiento**.
- **Presenta underfitting** (subajuste).

**Cómo reducir el sesgo:**
- Usar un modelo más complejo (deep learning, árboles, ensembles).
- Añadir más características relevantes.
- Mejorar la representación de los datos (feature engineering).

---

## 📈 Variance (Varianza)

**Definición:**
La varianza mide **cuánto cambia el rendimiento del modelo** si se entrena con diferentes subconjuntos de datos con una distribución similar.  
Un modelo con alta varianza **aprende demasiado los detalles del entrenamiento**, lo que lo hace inestable ante nuevos datos.

**Síntomas:**
- Excelente desempeño en entrenamiento, pero bajo en validación o prueba.
- Comportamiento inconsistente entre diferentes ejecuciones.

**Ejemplo:**
```plaintext
Una red neuronal con demasiadas capas y pocos datos puede memorizar ejemplos individuales, fallando al generalizar.
```

**Consecuencias:**
- El modelo sobreajusta (overfitting).
- Tiene baja capacidad de generalización.

**Cómo reducir la varianza:**
- Simplificar el modelo (menos capas, menor profundidad).
- Seleccionar solo características relevantes (feature selection).
- Dividir el dataset múltiples veces y promediar resultados (cross-validation).
- Usar técnicas de regularización (Dropout, L1, L2).

---

## ⚖️ Bias-Variance Tradeoff

Existe una relación inversa entre **Bias** y **Variance**:

| Tipo de Modelo | Bias  | Variance | Ejemplo                                  |
| -------------- | ----- | -------- | ---------------------------------------- |
| Muy Simple     | Alto  | Bajo     | Regresión lineal sobre datos no lineales |
| Balanceado     | Medio | Medio    | Modelo óptimo generalizado               |
| Muy Complejo   | Bajo  | Alto     | Red neuronal profunda con pocos datos    |

### Representación visual

```
Error Total = Bias² + Variance + Irreducible Error
```

📊 **Interpretación:**
- Reducir el sesgo puede aumentar la varianza.
- Reducir la varianza puede aumentar el sesgo.
- El punto óptimo se alcanza cuando el error total es mínimo.

---

## 🔍 Ejemplo Práctico

Supongamos que entrenas un modelo para predecir el precio de viviendas:

| Escenario                       | Descripción                                 | Resultado                                                |
| ------------------------------- | ------------------------------------------- | -------------------------------------------------------- |
| **Underfitting (High Bias)**    | Usas una regresión lineal simple.           | No captura relaciones no lineales → predicciones pobres. |
| **Overfitting (High Variance)** | Usas una red neuronal con demasiadas capas. | Memoriza los datos → falla con nuevos ejemplos.          |
| **Balanced Fit**                | Usas un modelo con la complejidad justa.    | Generaliza correctamente → mejor rendimiento global.     |


## 🧠 Conclusión

El éxito en Machine Learning depende de **lograr el equilibrio correcto entre Bias y Variance**.  
Comprender cómo tu modelo se ajusta a los datos te **permite diagnosticar** problemas de subajuste o sobreajuste, y tomar acciones para mejorar la **generalización**.

> ⚙️ Un buen modelo no es el que memoriza todo, sino el que entiende lo suficiente para predecir lo nuevo con precisión.