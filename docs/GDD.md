# Documento de Diseño de Juego (GDD) - Pitwall Manager

## 1. Visión General
* **Título Definitivo:** Pitwall Manager
* **Género:** Estrategia / Gestión Deportiva en Tiempo Real.
* **Rol del Jugador:** Director de Equipo (Team Principal / Jefe de Estrategia).
* **Plataforma:** Navegadores Web (Escritorio).
* **Tecnologías:** HTML5, CSS3, JavaScript Vanilla (ES6 Modules).

## 2. Pilares de Diseño
* **Presión en el Muro de Boxes:** Decisiones estratégicas basadas en telemetría en tiempo real.
* **Gestión de Recursos Críticos:** Controlar el ritmo para equilibrar la velocidad con la degradación de neumáticos.
* **Estética de Ingeniería:** Interfaz de alto contraste y modo oscuro que emula las pantallas de datos reales de la Fórmula 1.

---

## 3. Estructura y Arquitectura del Proyecto
El código se organiza de forma modular para garantizar la escalabilidad del juego:

*   `docs/GDD.md`: Este documento conceptual de diseño.
*   `src/index.html`: Estructura semántica de la pantalla de boxes y contenedores de datos.
*   `src/css/style.css`: Maquetación responsiva con CSS Grid, fuentes monoespaciadas y variables de color para banderas de carrera.
*   `src/js/app.js`: Inicializador del juego, gestión del estado global (`gameState`) y bucle principal.
*   `src/js/track.js`: Control del elemento HTML5 Canvas, dibujo del circuito en 2D y renderizado de la posición de los coches.
*   `src/js/physics.js`: Fórmulas matemáticas para el cálculo de tiempos por vuelta, desgaste de neumáticos y consumo.

---

## 4. Mecánicas y Lógica de Juego (Gameplay)

### 4.1. El Motor de Simulación (Game Loop)
* El bucle se gestiona en `app.js` mediante un temporizador asíncrono.
* Cada monoplaza posee un porcentaje de progreso de vuelta (0% a 100%).
* Al llegar al 100%, completa una vuelta, se suma al contador global y se recalculan los tiempos del *Live Timing*.

### 4.2. Variables de los Pilotos del Jugador
El usuario gestiona dos monoplazas independientes con las siguientes métricas:
* **Modo de Conducción:**
  * `Atacar (Push)`: Mayor velocidad, pero incrementa drásticamente el desgaste de neumáticos.
  * `Balanceado (Neutral)`: Ritmo de carrera óptimo y desgaste estándar.
  * `Conservar (Save)`: Reduce la velocidad para estirar la vida útil de la goma.
* **Degradación de Neumáticos (Tyre Wear):** Comienza en 100%. Al caer por debajo del 30%, el monoplaza pierde adherencia y sus tiempos por vuelta empeoran severamente.
* **Combustible:** Nivel de gasolina (0–100 kg). Mayor carga = más peso = vueltas más lentas. Menos combustible = coche más ligero. El consumo varía según el modo motor seleccionado.
* **Modo Motor:** Mapeado electrónico del propulsor.
  * `Alto rendimiento`: Máxima velocidad, máximo consumo de combustible.
  * `Mixto`: Equilibrio entre velocidad y consumo.
  * `Ahorro`: Menor velocidad, menor consumo.
* **DRS/ERS:** Opciones básicas por piloto.
  * `Exprimir`: Uso agresivo para adelantar o defender posición.
  * `Reservar`: Conservar energía para momentos clave.

### 4.3. Ventana de Pit Stop
* El jugador puede pulsar "Llamar a Boxes" en cualquier momento de la vuelta.
* El coche entrará al Pit Lane de forma automática al alcanzar el 100% de su progreso actual.
* **Menú de Selección:** Permite escoger el siguiente compuesto para el relevo: Blandos (🟥 Rápidos/Cortos), Medios (🟨 Equilibrados), Duros (⬜ Lentos/Duraderos).

### 4.4. Inteligencia Artificial y Eventos
* **Rivales de la IA:** Hasta 18 pilotos compiten autónomamente. La IA gestiona las mismas variables que el jugador (ritmo, modo motor, combustible, neumáticos, paradas en boxes). Existen varias personalidades de IA con comportamientos distintos (agresiva, conservadora, equilibrada, etc.). La IA responde al ritmo global de la carrera, no directamente a las acciones del jugador.
* **Incidentes Aleatorios:** Posibilidad de banderas amarillas o despliegue del *Safety Car*, lo que ralentiza el ritmo global y abre ventanas estratégicas para detenerse en boxes.

### 4.5. Clima Dinámico
* El clima puede cambiar durante la carrera (seco → lluvia → variable).
* Las condiciones climáticas afectan al agarre y los tiempos por vuelta.
* Influye directamente en la elección de neumáticos (slicks en seco / intermedios / lluvia).
* Los cambios de clima abren ventanas estratégicas de pit stop.

---

## 5. Criterios de Victoria y Progresión

### 5.1. Condiciones de Fin de Carrera
* **Derrota:** Si ambos coches abandonan (Doble DNF), se muestra una pantalla de derrota.
* **Victoria:** Si al menos uno de los dos coches finaliza en 1ª posición, se muestra una pantalla de victoria.
* **Resultado intermedio:** En cualquier otra situación, se muestra una pantalla de resumen con el puesto final de cada piloto.

### 5.2. Progresión
* Actualmente el juego se compone de carreras individuales independientes.
* **Futura feature:** Campaña con múltiples circuitos, tabla de posiciones global y mejoras progresivas del equipo entre carreras.

## 6. Notas adicionales
* **Audio:** Descartado explícitamente. El juego es de estrategia, no un simulador, por lo que no incluirá efectos de sonido ni música.
