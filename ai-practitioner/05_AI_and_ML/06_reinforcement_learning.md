# Reinforcement Learning (Aprendizaje por Refuerzo)

## Introducción

**Reinforcement Learning (RL)** o **Aprendizaje por Refuerzo** es un tipo de aprendizaje automático donde un **agente (agent)** aprende a **tomar decisiones óptimas** a través de **interacciones con un entorno (environment)**.  

El agente recibe **recompensas (rewards)** o **castigos** según las acciones que realiza y, con el tiempo, **ajusta su estrategia (policy)** para **maximizar la recompensa acumulada**.

> 💡 *A diferencia del aprendizaje supervisado o no supervisado, en RL no existen etiquetas predefinidas; el conocimiento se obtiene mediante prueba y error.*

---

## 🧠 Concepto General

En Reinforcement Learning, el agente **aprende comportamientos óptimos** mediante un ciclo continuo de:
1. **Observar** el entorno.  
2. **Actuar** según una política.  
3. **Recibir retroalimentación** (recompensa o penalización).  
4. **Actualizar** su política con base en la experiencia obtenida.

> 🎯 El objetivo final es **maximizar la recompensa total acumulada** a lo largo del tiempo.

---

## 🔑 Componentes Clave de RL

| Concepto | Descripción | Ejemplo |
|-----------|--------------|---------|
| **Agent (Agente)** | El “actor” o entidad que aprende y toma decisiones. | Un robot, un software de trading, un modelo de IA que juega ajedrez. |
| **Environment (Entorno)** | El sistema con el que el agente interactúa. | Un tablero de ajedrez, un mercado financiero, una simulación de tráfico. |
| **State (Estado)** | Representa la situación actual del entorno. | La posición de las piezas en el tablero, el precio actual del mercado. |
| **Action (Acción)** | Decisiones que el agente puede tomar. | Mover una pieza, comprar/vender, girar a la izquierda. |
| **Reward (Recompensa)** | Retroalimentación recibida después de una acción. | +1 por ganar, -1 por perder, +0.5 por avanzar al objetivo. |
| **Policy (Política)** | Estrategia que define cómo el agente selecciona acciones. | “Si el enemigo está cerca, retrocede.” |

---

## ⚙️ ¿Cómo Funciona el Aprendizaje por Refuerzo?

El proceso de aprendizaje sigue un ciclo iterativo donde el agente mejora su comportamiento con el tiempo.

### 🔄 Ciclo de Aprendizaje

1. El **Agente** observa el **Estado actual (Sₜ)** del entorno.  
2. Basado en su **Política (π)**, selecciona una **Acción (Aₜ)**.  
3. El **Entorno (Environment)** cambia a un **nuevo Estado (Sₜ₊₁)** y otorga una **Recompensa (Rₜ)**.  
4. El **Agente** usa esa información para **ajustar su política** y tomar mejores decisiones futuras.

> 🎯 **Meta:** Maximizar la suma de recompensas acumuladas a lo largo del tiempo (Return).


---

## 📚 Tipos de Aprendizaje por Refuerzo

### 1. **Model-Free (Sin modelo del entorno)**
- El agente **aprende directamente de la experiencia**, sin conocer cómo funciona el entorno.  
- Ejemplo: **Q-Learning**, **Deep Q-Networks (DQN)**.  

### 2. **Model-Based (Con modelo del entorno)**
- El agente **intenta modelar el entorno** y predecir resultados antes de actuar.  
- Ejemplo: algoritmos **Monte Carlo Tree Search (MCTS)**.

### 3. **Policy Optimization**
- Métodos que **aprenden directamente la mejor política** sin usar tablas de valores.  
- Ejemplo: **REINFORCE**, **Proximal Policy Optimization (PPO)**.

---

## 🧩 Ejemplo Conceptual

**Situación:** Un robot en un laberinto.  
- **Estado (State):** su posición actual.  
- **Acción (Action):** moverse arriba, abajo, izquierda o derecha.  
- **Recompensa (Reward):** +10 por llegar a la salida, -1 por chocar con una pared.  
- **Política (Policy):** el conjunto de reglas que le dicen qué movimiento realizar según el entorno.

Con el tiempo, el robot aprende a **llegar a la salida más rápido y con menos errores**, maximizando sus recompensas.

---

## 🏗️ Proceso de Aprendizaje

1. **Exploración:** el agente prueba diferentes acciones para descubrir cuáles son buenas.  
2. **Explotación:** una vez que aprende qué acciones son efectivas, las repite para obtener más recompensa.  
3. **Trade-off:** equilibrar entre explorar nuevas estrategias y explotar las conocidas es clave en RL.

> 📈 Este equilibrio se conoce como **Exploration vs. Exploitation Dilemma**.

---

## 🚀 Aplicaciones Reales de Reinforcement Learning

| Dominio | Aplicación | Ejemplo |
|----------|-------------|----------|
| **Gaming** | Entrenamiento de agentes que superan a humanos en juegos. | AlphaGo, Chess, Atari, Dota 2. |
| **Robotics** | Aprendizaje de control de movimiento y navegación. | Robots autónomos, brazos robóticos industriales. |
| **Finance** | Estrategias de inversión adaptativas. | Trading algorítmico, gestión de portafolios. |
| **Healthcare** | Optimización de tratamientos médicos personalizados. | Ajuste de dosis de medicamentos. |
| **Autonomous Vehicles** | Toma de decisiones en conducción autónoma. | Frenado, aceleración, cambio de carril. |

---

## 🎯 Meta del Aprendizaje por Refuerzo

El objetivo final del agente es **maximizar la recompensa acumulada total (Cumulative Reward)** a lo largo del tiempo, ajustando su política con base en la experiencia adquirida.

Fórmula general:
\[
G_t = R_{t+1} + \gamma R_{t+2} + \gamma^2 R_{t+3} + ... = \sum_{k=0}^{\infty} \gamma^k R_{t+k+1}
\]
Donde:
- \( G_t \): recompensa acumulada esperada.  
- \( \gamma \): factor de descuento (0 < γ ≤ 1), que determina la importancia de las recompensas futuras.

---

## 🧠 Resumen General

| Concepto | Descripción | Ejemplo |
|-----------|--------------|---------|
| **Agent** | Entidad que toma decisiones y aprende. | Robot, jugador, software de trading. |
| **Environment** | Entorno donde actúa el agente. | Juego, simulación, mercado. |
| **Action** | Movimiento o decisión que ejecuta el agente. | Mover, comprar, detener. |
| **Reward** | Retroalimentación del entorno. | +1 por ganar, -1 por perder. |
| **State** | Situación actual del entorno. | Posición del jugador, valor de acción. |
| **Policy** | Estrategia para decidir acciones. | “Si lluvia, usa paraguas.” |

---

## 🧩 Conclusión

El **Reinforcement Learning** representa la frontera entre la **IA teórica y la práctica**, ya que combina **toma de decisiones**, **retroalimentación en tiempo real** y **aprendizaje continuo**.

> 🚀 *El agente no aprende de ejemplos, sino de experiencia.*
