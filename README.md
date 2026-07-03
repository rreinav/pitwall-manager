# 🏁 Pitwall Manager

[![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg)](LICENSE)
[![PRs Welcome](https://img.shields.io/badge/PRs-welcome-brightgreen.svg)](http://makeapullrequest.com)
[![Vanilla JS](https://img.shields.io/badge/vanilla-js-f7df1e?logo=javascript&logoColor=black)](https://developer.mozilla.org/en-US/docs/Web/JavaScript)
[![HTML5](https://img.shields.io/badge/HTML5-E34F26?logo=html5&logoColor=white)](https://developer.mozilla.org/en-US/docs/Web/HTML)
[![CSS3](https://img.shields.io/badge/CSS3-1572B6?logo=css3&logoColor=white)](https://developer.mozilla.org/en-US/docs/Web/CSS)

¡Bienvenido a **Pitwall Manager**! Un simulador web de estrategia y gestión de Fórmula 1 en tiempo real desarrollado de forma nativa. Asume el rol de *Team Principal*, toma las decisiones del muro de boxes, analiza la telemetría en vivo y gestiona los neumáticos para llevar a tu equipo a la victoria.

El proyecto está diseñado bajo una arquitectura limpia, modular y sin librerías externas de JavaScript.

## 📁 Estructura del Repositorio

Para mantener el código organizado, el proyecto se divide en las siguientes carpetas:

```text
├── docs/
│   └── GDD.md          # Documento de Diseño de Juego (Game Design Document)
├── src/
│   ├── css/
│   │   └── style.css   # Estilos, maquetación adaptativa y modo oscuro
│   ├── js/
│   │   ├── app.js      # Inicializador y núcleo del bucle de juego
│   │   ├── track.js    # Renderizado y lógicas del circuito en HTML5 Canvas
│   │   └── physics.js  # Fórmulas de degradación y matemáticas de carrera
│   └── index.html      # Estructura principal de la interfaz de boxes
└── README.md           # Presentación del proyecto
```

## 🚀 Características Principales

*   **Mapa en Tiempo Real:** Circuito interactivo 2D renderizado mediante HTML5 Canvas que muestra el movimiento constante de los monoplazas.
*   **Gestión de Pilotos:** Panel de control individual para ordenar a tus dos pilotos cambiar de ritmo (`Push`, `Balanced`, `Save`).
*   **Estrategia de Pit Stop:** Planifica paradas dinámicas eligiendo entre compuestos Blandos (🟥), Medios (🟨) o Duros (⬜).
*   **Live Timing Dinámico:** Tabla de posiciones interactiva que se actualiza en tiempo real calculando los intervalos con la IA rival.

## 🛠️ Tecnologías

*   **HTML5:** Estructura modular del muro de decisiones.
*   **CSS3:** Diseño futurista de telemetría basado en CSS Grid y Flexbox.
*   **JavaScript (ES6 Modules):** Lógica orientada a eventos, físicas del desgaste y manipulación dinámica del DOM.

## 📄 Licencia

Este proyecto se distribuye bajo la **Licencia MIT**. Siéntete libre de explorar el código, proponer mejoras o usarlo en tus propios desarrollos de aprendizaje.
