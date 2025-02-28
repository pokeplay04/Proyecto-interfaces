# Documentación del Sitio Web del Real Madrid

## Descripción General del Proyecto
Este sitio web está dedicado al Real Madrid Club de Fútbol, proporcionando información sobre la historia del equipo, la plantilla actual y sus logros. El sitio presenta un diseño responsive utilizando Bootstrap 5 y estilos CSS personalizados.

## Estructura del Sitio

### Páginas
1. **Página Principal (index.html)**
   - Sección hero con mensaje de bienvenida
   - Sección multimedia con ubicación del estadio y himno del club
   - Sección de últimas noticias
   - Barra de navegación responsive

2. **Página de Plantilla (plantilla.html)**
   - Sección de plantilla actual con tarjetas interactivas de jugadores
   - Sección de jugadores históricos
   - Estadísticas interactivas al pasar el ratón
   - Efectos de entrada animados para las tarjetas

3. **Página de Historia (historia.html)**
   - Línea temporal de la historia del club
   - Diseño responsive para todos los dispositivos

4. **Página de Palmarés (palmares.html)**
   - Exhibición de todos los títulos y trofeos del club
   - Presentación organizada de trofeos

## Características

### Sistema de Chat
- **Interfaz de Usuario**
  - Ventana de chat flotante en la esquina inferior derecha
  - Botón de minimizar/maximizar
  - Indicador de estado de conexión
  - Campo de entrada de texto con botón de envío

- **Funcionalidades**
  - Chat en tiempo real entre usuarios
  - Historial de mensajes persistente
  - Notificaciones de nuevos mensajes
  - Emojis y formato básico de texto
  - Indicador de "escribiendo..."

- **Características Técnicas**
  - Conexión WebSocket para comunicación en tiempo real
  - Almacenamiento local para historial de chat
  - Gestión de sesiones de usuario
  - Sistema de notificaciones push

### Navegación
- Barra de navegación fija en la parte superior
- Menú hamburguesa responsive para dispositivos móviles
- Indicación de página activa
- Logo de la marca con enlace a la página principal

### Tarjetas de Jugadores (plantilla.html)
- Efectos interactivos al pasar el ratón
- Ventana emergente de estadísticas
- Información del jugador incluyendo:
  - Imagen
  - Nombre
  - Posición
  - Estadísticas (partidos, goles, asistencias)
- Efectos de entrada animados

### Integración Multimedia
- Integración de Google Maps para la ubicación del estadio
- Video de YouTube integrado para el himno del club
- Iframes responsive

## Implementación Técnica

### Estructura CSS
- **custom.css**: Estilos principales para la página de inicio
- **plantilla.css**: Estilos para tarjetas de jugadores y animaciones
- **historia.css**: Estilos para la línea temporal y página de historia
- **palmares.css**: Estilos para la visualización de trofeos
- **footer.css**: Estilos comunes del pie de página
- **chat.css**: Estilos para el sistema de chat

## Explicación Detallada del Código por Página

### 1. Página Principal (index.html)
```html
<!-- Estructura de la Barra de Navegación -->
<nav class="navbar navbar-expand-lg navbar-dark bg-dark fixed-top">
    <div class="container">
        <a class="navbar-brand" href="#">Real Madrid</a>
        <!-- Botón para móviles -->
        <button class="navbar-toggler" type="button" data-bs-toggle="collapse" data-bs-target="#navbarNav">
            <span class="navbar-toggler-icon"></span>
        </button>
    </div>
</nav>
```
La barra de navegación utiliza Bootstrap 5 con las clases `navbar-expand-lg` para expansión en pantallas grandes y `fixed-top` para mantenerla fija. El botón hamburguesa aparece en dispositivos móviles.

### 2. Página de Plantilla (plantilla.html)
```javascript
// Sistema de Tarjetas de Jugadores
document.addEventListener("DOMContentLoaded", function () {
    const players = document.querySelectorAll(".player-card");
    players.forEach((card, index) => {
        // Añade retraso en la animación para cada tarjeta
        card.style.animationDelay = `${index * 0.1}s`;
    });
});

// Ventana emergente de estadísticas
const statsPopup = document.getElementById("player-stats");
document.querySelectorAll(".player-card").forEach(card => {
    card.addEventListener("mouseover", function (event) {
        // Muestra estadísticas al pasar el ratón
        statsPopup.innerText = this.getAttribute("data-stats");
        statsPopup.style.display = "block";
        statsPopup.style.top = event.pageY + "px";
        statsPopup.style.left = event.pageX + "px";
    });
});
```
El código implementa animaciones secuenciales para las tarjetas de jugadores y una ventana emergente con estadísticas.

### 3. Página de Historia (historia.html)
```javascript
// Animaciones de la línea temporal
document.addEventListener("DOMContentLoaded", function () {
    const items = document.querySelectorAll(".timeline-item");
    function showOnScroll() {
        items.forEach(item => {
            const rect = item.getBoundingClientRect();
            // Muestra elementos cuando entran en el viewport
            if (rect.top <= window.innerHeight * 0.8) {
                item.classList.add("visible");
            }
        });
    }
    window.addEventListener("scroll", showOnScroll);
    showOnScroll();
});
```
Implementa animaciones de aparición progresiva para los elementos de la línea temporal al hacer scroll.

### 4. Página de Palmarés (palmares.html)
```javascript
// Sistema de visualización de imágenes
function showImage(src) {
    const popupImg = document.getElementById('popupImg');
    popupImg.src = src;
    popupImg.classList.add('show');
}

function hideImage() {
    document.getElementById('popupImg').classList.remove('show');
}
```
Gestiona la visualización de imágenes en modo popup al hacer clic en los trofeos.

### Sistema de Chat
```javascript
// Inicialización del chat
const chatInit = () => {
    const socket = new WebSocket('ws://servidor-chat');
    socket.onmessage = (event) => {
        mostrarMensaje(JSON.parse(event.data));
    };
};
```
Implementa la conexión WebSocket para el chat en tiempo real.
```

### Dependencias
- Bootstrap 5.3.0
- CSS/SCSS personalizado
- Iconos de Font Awesome
- Socket.IO para el chat en tiempo real

## Diseño Responsive
- Enfoque mobile-first
- Puntos de ruptura:
  - xs: < 576px
  - sm: ≥ 576px
  - md: ≥ 768px
  - lg: ≥ 992px
  - xl: ≥ 1200px

## Gestión de Recursos
- Imágenes almacenadas en el directorio `/assets`
- Formato webp optimizado para imágenes de jugadores
- Carga de imágenes responsive

## Pie de Página
- Información de copyright
- Enlaces a redes sociales
- Consistente en todas las páginas


