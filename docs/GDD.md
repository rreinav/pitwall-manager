# Documento de Diseño de Juego (GDD) - Pitwall Manager

## 1. Visión General
* **Título de la saga:** Pitwall Manager
* **Género:** Estrategia / Gestión Deportiva en Tiempo Real.
* **Rol del Jugador:** Director de Equipo (Team Principal / Jefe de Estrategia).
* **Plataforma:** Navegadores Web (Escritorio).
* **Tecnologías:** HTML5, CSS3, JavaScript Vanilla (ES6 Modules).

## 2. Títulos de la saga

| Título | Estado | Descripción |
|--------|--------|-------------|
| **Pitwall Manager: F1 2000** | En desarrollo | Ambientado en la temporada 2000 de Fórmula 1. Estrategia en tiempo real con gestión de neumáticos, combustible y comunicaciones con delay por cansancio del piloto. |
| **Pitwall Manager: F1 1976** | En desarrollo | Ambientado en la temporada 1976, sin comunicaciones por radio. Las órdenes se ejecutan mediante carteles al pasar por meta. |

## 3. Pilares de Diseño (Comunes)
* **Presión en el Muro de Boxes:** Decisiones estratégicas basadas en telemetría en tiempo real.
* **Gestión de Recursos Críticos:** Controlar el ritmo para equilibrar la velocidad con la degradación de neumáticos.
* **Estética de Ingeniería:** Interfaz de alto contraste y modo oscuro que emula las pantallas de datos reales de la Fórmula 1.

## 4. Estructura del Repositorio

```
pitwall-manager/              # Hub de la saga
├── docs/GDD.md               # Este documento
├── src/                      # Landing page del hub
│   ├── index.html
│   └── css/style.css
├── games/                    # Juegos individuales (gitignored)
│   └── pitwall-manager-f1-2000/  # Pitwall Manager: F1 2000
└── README.md
```

Para más información sobre cada título, consultar su GDD específico en su repositorio correspondiente.
