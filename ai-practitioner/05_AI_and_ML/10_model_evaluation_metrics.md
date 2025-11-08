# Model Evaluation Metrics

## 🧩 Binary Classification Example

En **clasificación binaria**, el objetivo del modelo es predecir entre dos categorías posibles —por ejemplo, *positivo/negativo*, *spam/no spam*, *fraudulento/no fraudulento*.  
Para evaluar qué tan bien el modelo predice estas clases, comparamos las **predicciones** con los **valores reales**.

| Tipo de Valor | Descripción |
|----------------|--------------|
| **True Values** | Son los valores reales (la verdad observada). |
| **Predictions** | Son las salidas del modelo (predicciones calculadas). |

---

## 📊 Confusion Matrix (Matriz de Confusión)

La **matriz de confusión** permite visualizar el rendimiento del modelo al comparar las predicciones con los valores reales.

|                  | **Predicho Positivo** | **Predicho Negativo** |
|------------------|----------------------|----------------------|
| **Real Positivo** | **True Positive (TP)** | **False Negative (FN)** |
| **Real Negativo** | **False Positive (FP)** | **True Negative (TN)** |

**Interpretación:**
- **TP:** el modelo predijo correctamente positivo.  
- **TN:** el modelo predijo correctamente negativo.  
- **FP:** el modelo predijo positivo cuando era negativo (*falso positivo*).  
- **FN:** el modelo predijo negativo cuando era positivo (*falso negativo*).

> 🎯 Idealmente, queremos **altos TP y TN**, y **bajos FP y FN**.

---

## ⚙️ Key Metrics for Classification

Una vez que tenemos la matriz de confusión, podemos calcular diferentes métricas para evaluar la calidad del modelo.

### 🎯 **1. Precision**

\[
Precision = \frac{TP}{TP + FP}
\]

Mide **qué proporción de predicciones positivas son realmente correctas**.

- **Alta precisión:** el modelo comete pocos falsos positivos.  
- **Ideal cuando:** los falsos positivos son costosos (por ejemplo, diagnosticar erróneamente una enfermedad).  

> 💡 Ejemplo: “De todos los correos marcados como spam, ¿cuántos realmente lo eran?”

---

### 🔎 **2. Recall (Sensibilidad o Tasa de Verdaderos Positivos)**

\[
Recall = \frac{TP}{TP + FN}
\]

Mide **qué proporción de casos positivos reales fueron correctamente identificados**.

- **Alta recall:** el modelo detecta casi todos los positivos reales.  
- **Ideal cuando:** los falsos negativos son costosos (por ejemplo, no detectar una enfermedad real).  

> 💡 Ejemplo: “De todos los correos spam, ¿cuántos fueron correctamente detectados?”

---

### ⚖️ **3. F1 Score**

\[
F1 = 2 \times \frac{Precision \times Recall}{Precision + Recall}
\]

El **F1 Score** combina **precisión y recall** en una sola métrica balanceada.

- Ideal cuando hay un **desequilibrio de clases** (una clase tiene muchos más ejemplos que otra).  
- Rango: 0 a 1 → cuanto más alto, mejor.

> 💡 Útil para medir el equilibrio entre *capturar todos los positivos* y *evitar errores falsos*.

---

### 📈 **4. Accuracy**

\[
Accuracy = \frac{TP + TN}{TP + TN + FP + FN}
\]

Mide **la proporción de predicciones correctas** sobre el total de predicciones.

- Ideal cuando el dataset está **balanceado**.  
- Puede ser **engañoso** en datasets desequilibrados (por ejemplo, si 95% de los casos son negativos, un modelo que siempre predice “negativo” tendrá 95% de accuracy, pero no sirve).

---

## 🧮 Multi-Dimensional Classification

Cuando un modelo predice **más de dos clases** (por ejemplo, tipos de frutas: manzana, naranja, plátano), hablamos de **clasificación multiclase o multidimensional**.

En estos casos:
- Se calcula una **matriz de confusión** por clase.  
- Se promedian métricas como precisión, recall y F1 (macro, micro o weighted average).  

> ✅ Es la mejor forma de evaluar el desempeño en **modelos que clasifican en múltiples categorías**.

---

## 📉 AUC-ROC (Área Bajo la Curva ROC)

**ROC (Receiver Operating Characteristic)** es una gráfica que muestra la relación entre:

- **True Positive Rate (Sensibilidad)**  
- **False Positive Rate (1 - Especificidad)**

El **AUC (Area Under the Curve)** mide el área bajo la curva ROC.

| Valor AUC | Interpretación |
|------------|----------------|
| **1.0** | Modelo perfecto |
| **0.9 - 1.0** | Excelente |
| **0.8 - 0.9** | Bueno |
| **0.7 - 0.8** | Aceptable |
| **0.5** | Aleatorio (sin valor predictivo) |

> 🎯 Cuanto más cerca de **1**, mejor distingue el modelo entre clases positivas y negativas.

---

## 📊 Model Evaluation – Regression Metrics

Para problemas donde el modelo predice un **valor continuo** (por ejemplo, precio de una casa, temperatura, ventas proyectadas), usamos métricas de **regresión**.

### 🔹 **1. MAE – Mean Absolute Error**
\[
MAE = \frac{1}{n} \sum |y_{real} - y_{pred}|
\]

Mide el **error promedio absoluto**.  
Más robusto ante valores atípicos que RMSE.

> 💡 Interpretación: en promedio, cuántas unidades se equivoca el modelo.

---

### 🔹 **2. MAPE – Mean Absolute Percentage Error**
\[
MAPE = \frac{100}{n} \sum \left| \frac{y_{real} - y_{pred}}{y_{real}} \right|
\]

Mide el error relativo en porcentaje.

> 💡 Ideal cuando el rango de los valores es amplio y se quiere expresar el error en forma porcentual.

---

### 🔹 **3. RMSE – Root Mean Square Error**
\[
RMSE = \sqrt{ \frac{1}{n} \sum (y_{real} - y_{pred})^2 }
\]

Mide el error cuadrático medio.  
Penaliza más los errores grandes que el MAE.

> 💡 Ideal cuando se desea minimizar grandes desviaciones en las predicciones.

---

### 🔹 **4. R² – Coefficient of Determination**
\[
R^2 = 1 - \frac{SS_{res}}{SS_{tot}}
\]

Mide **cuánta variabilidad de los datos reales explica el modelo**.

| Valor R² | Interpretación |
|-----------|----------------|
| **1.0** | El modelo explica el 100% de la variación |
| **0.9 - 1.0** | Excelente ajuste |
| **0.5 - 0.9** | Aceptable |
| **0.0** | No explica la variabilidad |
| **< 0.0** | Peor que una media constante |

> 🎯 Ideal para evaluar modelos de regresión y entender su capacidad explicativa.

---

## 🧠 Conclusión

Seleccionar la **métrica adecuada** depende del tipo de problema y del objetivo del modelo:

| Tipo de Problema | Métricas Recomendadas | Uso Principal |
|------------------|------------------------|----------------|
| **Clasificación Binaria** | Precision, Recall, F1, Accuracy | Diagnóstico de rendimiento y balance entre errores. |
| **Clasificación Multiclase** | F1 Macro/Micro, Confusion Matrix | Evaluación de predicciones en múltiples categorías. |
| **Regresión** | MAE, RMSE, R² | Medición de precisión en valores continuos. |

> ⚙️ *No existe una métrica universal: elegir la correcta es clave para entender la calidad real del modelo.*
