# Tamagotchi Online

Hi👋.

I built this project to get a feel to get a sense of what a complete project looks like — one that people can use as an actual product. With a few tecnologies of React ecosystem.

I've been using core React features like useReducer and Context API, React Router for routing, localStorage for data persistence, also cool CSS for the cat desings and customizations.

---

# Guía para crear un Tamagotchi en React

¡Buena idea para el portfolio! Te ayudo a desglosar las funcionalidades típicas de un Tamagotchi, desde lo básico hasta extras que pueden lucir muy bien.

## 🎮 Funcionalidades core (lo mínimo viable)

### 1. **Sistema de estadísticas** (las clásicas barras)

- **Hambre** 🍖 - baja con el tiempo
- **Felicidad** 😊 - baja con el tiempo o si está hambriento
- **Energía/Sueño** 😴 - baja despierto, sube durmiendo
- **Higiene** 🧼 - baja con el tiempo
- **Salud** ❤️ - se degrada si las demás están mal

Cada una suele ir de 0 a 100.

### 2. **Acciones del jugador**

- **Alimentar** (comida 🍕 o snack 🍬, con efectos distintos)
- **Jugar** (minijuego simple o solo subir felicidad)
- **Dormir** (sube energía, pausa otras stats)
- **Limpiar** (baño/ducha)
- **Curar** (si se enferma)

### 3. **Ciclo de vida**

- **Huevo → Bebé → Niño → Adolescente → Adulto**
- Evoluciona según cómo lo cuides (ej: si lo descuidas, evoluciona a algo "feo")
- **Muerte** si las stats llegan a 0 mucho tiempo

### 4. **Ciclo temporal**

- Un `setInterval` o `requestAnimationFrame` que decremente stats cada X segundos
- Estados de ánimo (feliz, neutral, triste, enfermo) según stats

## ✨ Funcionalidades extra que lucen bien en portfolio

- **Persistencia con `localStorage`** → si cierras la pestaña, sigue vivo (o calcula tiempo transcurrido al volver)
- **Animaciones** con Framer Motion o CSS (rebotar, parpadear, dormir)
- **Sonidos** con la Web Audio API o audios pequeños
- **Minijuego** al pulsar "jugar" (piedra-papel-tijera, memory, etc.)
- **Estados de ánimo visuales** (sprites o emojis que cambian)
- **Notificaciones** si está triste o hambriento
- **Modo "pausa"** cuando la pestaña no está visible
- **Estadísticas históricas** (cuántos días vivió, récords)

## 🛠️ Stack sugerido para GitHub Pages

```
- Vite + React (más rápido que CRA)
- Zustand o useReducer para el estado del bicho
- Framer Motion para animaciones
- localStorage o IndexedDB para persistencia
- gh-pages o GitHub Actions para deploy
```

## 📐 Arquitectura sugerida

```
src/
├── components/
│   ├── Pet.jsx           # el bicho con sus animaciones
│   ├── StatsBar.jsx      # barras de hambre, felicidad...
│   ├── ActionButtons.jsx # botones de acciones
│   └── Minigame.jsx      # opcional
├── hooks/
│   ├── usePetStats.js    # lógica del tick temporal
│   └── useLocalStorage.js
├── store/
│   └── petStore.js       # estado global
└── utils/
    └── evolution.js      # lógica de evolución/muerte
```

## 💡 Consejo para el portfolio

Lo que más impresiona no es que sea complejo, sino que **se sienta vivo**:

- Animaciones suaves
- Que reaccione a tus acciones (cambie la cara, salte, se queje)
- Que recuerde el estado entre visitas
- Un diseño visual cuidado (pixel art o estilo cute minimalista)

## 🚀 Sobre el deploy en GitHub Pages

Con Vite es muy simple:

```bash
npm run build
# subir /dist a la rama gh-pages
```

O usa la action oficial `actions/deploy-pages`. Recuerda configurar `base: '/nombre-repo/'` en `vite.config.js`.

---

¿Quieres que te ayude con alguna parte concreta? Por ejemplo:

- Diseñar el **hook del ciclo temporal** (que es lo más tricky)
- La **lógica de evolución** del bicho
- El **setup de Vite + GitHub Pages** paso a paso
- Un **esqueleto inicial** del proyecto
