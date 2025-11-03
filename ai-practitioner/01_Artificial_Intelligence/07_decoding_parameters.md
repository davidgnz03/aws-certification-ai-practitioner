# Parámetros de Generación de Texto en IA: `temperature`, `top-p` y `top-k`

Los parámetros **temperature**, **top-p** y **top-k** controlan el **nivel de aleatoriedad, creatividad y coherencia** de un modelo de lenguaje (como GPT).  
Sirven para ajustar **cómo el modelo elige las palabras** cuando genera texto.

---

## 🌡️ 1. Temperature

Controla **cuánto riesgo o aleatoriedad** toma el modelo al elegir palabras.

- **Baja temperatura (≈ 0.1–0.3):**
  - Respuestas más **deterministas y predecibles**.
  - El modelo elige casi siempre las palabras más probables.
  - Ideal para tareas **técnicas o analíticas**.

- **Alta temperatura (≈ 0.8–1.0 o más):**
  - Respuestas más **creativas y variadas**.
  - El modelo se “arriesga” a usar palabras menos probables.
  - Ideal para **textos creativos o artísticos**.

**Ejemplo:**
> Prompt: “Describe la luna.”  
> - `temperature = 0.2` → “La luna es el satélite natural de la Tierra.”  
> - `temperature = 0.9` → “La luna flota como un farol de plata en la noche.”

---

## 🎯 2. Top-p (Nucleus Sampling)

Limita la **probabilidad acumulada** de las palabras que el modelo considera al generar texto.

- El modelo **ordena las palabras posibles por probabilidad**.
- Suma esas probabilidades hasta alcanzar el valor *p*.
- Solo elige entre esas palabras.

**Ejemplo:**
- `top-p = 0.9` → Considera solo las palabras que suman el **90 %** de la probabilidad total.

**Usos comunes:**
- `top-p = 1.0` → sin filtro (máxima libertad).  
- `top-p = 0.8–0.9` → equilibrio entre coherencia y creatividad.

---

## 🔢 3. Top-k

Limita el número de **palabras candidatas** que el modelo puede elegir.

- `top-k = 1` → palabra más probable (modelo determinista).  
- `top-k = 50` → el modelo elige entre las **50 palabras más probables**.

**Diferencia con `top-p`:**
- `top-k` → número fijo de palabras.  
- `top-p` → porcentaje acumulado de probabilidad.

---

## ⚙️ Cómo interactúan

Generalmente se usan **juntos** para equilibrar coherencia y creatividad:

| Configuración | Resultado esperado |
|----------------|--------------------|
| `temperature=0.2, top-p=1` | Muy preciso y repetitivo |
| `temperature=0.7, top-p=0.9` | Natural y equilibrado |
| `temperature=1.0, top-p=0.8` | Creativo y expresivo |
| `temperature=1.2, top-p=0.5` | Muy impredecible y artístico |

---

## 🧠 Resumen

| Parámetro | Qué controla | Efecto |
|------------|---------------|--------|
| **Temperature** | Nivel general de aleatoriedad | ↑ = más creatividad |
| **Top-p** | Porcentaje de probabilidad acumulada | Filtra palabras raras |
| **Top-k** | Número máximo de opciones | Limita la amplitud de elección |

---

> 💬 **Consejo:**  
> Para la mayoría de aplicaciones prácticas (chatbots, redacción, explicación), una buena combinación suele ser:  
> `temperature = 0.7` y `top-p = 0.9`.

---
