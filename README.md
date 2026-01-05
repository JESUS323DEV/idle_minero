# ⛏️ Lady Hungry — Idle Game en React

**Lady Hungry** es un idle game desarrollado en **React** centrado en economía, gestión de recursos y decisiones incómodas.  
No es un clicker feliz: cada sistema presiona a los demás y obliga al jugador a equilibrar progreso, mantenimiento y riesgo.

El proyecto nace como práctica de React, pero ha evolucionado rápidamente hacia un sistema jugable completo con múltiples mecánicas interconectadas.

---

## 🎮 Mecánicas principales

### ⛏️ Minería
- Minado activo y producción pasiva de oro.
- Consumo de stamina por segundo.
- El minero se detiene automáticamente si la stamina llega a 0 o el pico se rompe.

### 🔧 Sistema de Pico
- Materiales: **Piedra → Bronze → Hierro**.
- Cada material tiene **tiers (0–3)**.
- Solo al llegar a **tier 3** se puede mejorar el material.
- Cada tier:
  - Aumenta la durabilidad.
  - Incrementa costes de reparación.
- El pico tiene:
  - Durabilidad actual y máxima.
  - Coste de reparación creciente.
  - Oro extra por picada según material.
- Reparar el pico **puede dejar el oro en negativo** (decisión de diseño).

### ⚡ Stamina
- Stamina máxima mejorable.
- Recarga instantánea con coste escalable.
- Influye directamente en la eficiencia del minado.

### 🪙 Oro pasivo
- Producción pasiva escalable mediante upgrades.
- Afectada por el estado de Lady.
- Buffs temporales que modifican la producción.

---

## 🐶 Lady (Sistema de presión)

Lady no es decorativa. Es un sistema activo que **presiona la economía**.

- Tiene nivel de hambre (0–100%).
- Si baja de cierto umbral:
  - Se reduce o corta el oro pasivo.
- Alimentarla cuesta oro y el coste escala.
- Incluye RNG (puede devolver stamina al minero).

### 🍪 Snacks
- **Snack Productivo**
  - Buff temporal de oro pasivo.
  - Puede mejorar su nivel **una sola vez**.
  - El upgrade queda bloqueado visual y lógicamente tras usarse.
- **Snack Calma**
  - Recupera el hambre al máximo.
  - Congela la pérdida de hambre durante un tiempo.

---

## 🧠 Diseño del sistema
- No existe una estrategia perfecta.
- Todos los sistemas interactúan entre sí:
  - Oro ↔ Stamina ↔ Pico ↔ Lady.
- El jugador siempre tiene algo que mejorar, pero nunca todo a la vez.
- El balance se basa en presión constante, no en castigar al jugador.

---

## 🧩 UI / UX
- Todos los modales siguen el mismo patrón:
  - Botón `+` cuando está cerrado.
  - Botón `✕` dentro del modal.
- Layout construido principalmente con **Flexbox**, escalable y estable.
- Formateo de números grandes (`K`, `M`, `B`) para evitar romper el layout.
- Sistema preparado para escalar sin romper render ni lógica.

---

## 🛠️ Tecnologías
- **React**
  - `useState`
  - `useEffect`
  - Render condicional
- JavaScript
- CSS
- LocalStorage para persistencia de partida

---

## 🚧 Estado del proyecto
Proyecto en desarrollo activo.  
La lógica base está consolidada; el foco actual está en:
- Ajuste fino de balance.
- Pulido visual.
- Mejorar feedback visual y game feel.

---

## ⚠️ Nota
Este proyecto se ha desarrollado con fines de aprendizaje, pero con mentalidad de sistema real:  
cada mecánica existe por una razón y no como simple demostración técnica.

