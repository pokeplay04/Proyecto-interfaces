![image](https://github.com/user-attachments/assets/2c51d25a-3e42-478b-9303-2d69abd80bfa)

# PORTADA

![portada](https://github.com/user-attachments/assets/df49678e-eddf-4715-bc9d-a42243cfd150)

# Documentación Detallada del Sitio Web del Real Madrid

## Estructura HTML Detallada

### 1. Componentes Comunes

#### 1.1 Barra de Navegación
```html
<nav class="navbar navbar-expand-lg navbar-dark bg-dark fixed-top">
    <div class="container">
        <a class="navbar-brand" href="#">Real Madrid</a>
        <button class="navbar-toggler" type="button" data-bs-toggle="collapse" data-bs-target="#navbarNav">
            <span class="navbar-toggler-icon"></span>
        </button>
    </div>
</nav>
```

**Explicación detallada:**
- `navbar-expand-lg`: Expande la barra de navegación en pantallas grandes (≥992px)
- `navbar-dark bg-dark`: Tema oscuro para mejor contraste
- `fixed-top`: Mantiene la barra de navegación fija en la parte superior
- `navbar-toggler`: Botón hamburguesa que aparece en dispositivos móviles

#### 1.2 Pie de Página
```html
<footer class="footer bg-dark text-white py-4">
    <div class="container">
        <div class="row">
            <div class="col-md-4">
                <h5>Real Madrid CF</h5>
                <p>© 2024 Todos los derechos reservados</p>
            </div>
            <div class="col-md-4">
                <h5>Redes Sociales</h5>
                <div class="social-links">
                    <a href="#" class="text-white me-3"><i class="fab fa-facebook"></i></a>
                    <a href="#" class="text-white me-3"><i class="fab fa-twitter"></i></a>
                    <a href="#" class="text-white"><i class="fab fa-instagram"></i></a>
                </div>
            </div>
        </div>
    </div>
</footer>
```

**Características:**
- Diseño responsive con sistema de rejilla Bootstrap
- Integración de iconos de Font Awesome para redes sociales
- Espaciado consistente con clases utilitarias de Bootstrap

### 2. Página Principal (index.html)

#### 2.1 Sección Hero
```html
<section class="hero-section">
    <div class="hero-content">
        <h1>Bienvenidos al Real Madrid</h1>
        <p class="lead">El club más laureado de la historia del fútbol</p>
    </div>
</section>
```

**Características técnicas:**
- Imagen de fondo a pantalla completa con overlay oscuro
- Texto centrado con alto contraste
- Animación de entrada suave para el contenido

#### 2.2 Sección Multimedia
```html
<section class="multimedia-section container my-5">
    <div class="row">
        <div class="col-md-6">
            <div class="map-container">
                <iframe src="https://www.google.com/maps/embed?pb=!1m18!1m12!1m3!1d3036.." 
                        width="100%" height="450" allowfullscreen></iframe>
            </div>
        </div>
        <div class="col-md-6">
            <div class="video-container">
                <iframe src="https://www.youtube.com/embed/..."
                        width="100%" height="450" allowfullscreen></iframe>
            </div>
        </div>
    </div>
</section>
```
**Implementación:**
- Contenedores responsive para iframes
- Proporción de aspecto 16:9 mantenida en todos los dispositivos
- Lazy loading para optimización de rendimiento

#### 2.3 Sección de Últimas Noticias
```html
<section class="news-section container my-5">
    <h2 class="section-title text-center mb-4">Últimas Noticias</h2>
    <div class="row">
        <div class="col-lg-4 col-md-6 mb-4">
            <div class="news-card">
                <div class="news-image">
                    <img src="assets/news/latest1.webp" alt="Última Noticia 1" class="img-fluid">
                    <div class="news-date">22 Feb 2024</div>
                </div>
                <div class="news-content p-3">
                    <h3 class="news-title">Victoria en Champions League</h3>
                    <p class="news-excerpt">El Real Madrid consigue una importante victoria en octavos de final...</p>
                    <a href="#" class="btn btn-outline-primary">Leer más</a>
                </div>
            </div>
        </div>
    </div>
</section>
```



### 3. Página de Plantilla (plantilla.html)

#### 3.1 Tarjetas de Jugadores
```html
<section class="players-section container my-5">
    <div class="row">
        <div class="col-lg-3 col-md-4 col-sm-6 mb-4">
            <div class="player-card" data-stats="Goles: 15, Asistencias: 10">
                <div class="player-image">
                    <img src="assets/players/player1.webp" alt="Nombre Jugador">
                </div>
                <div class="player-info">
                    <h3>Nombre Jugador</h3>
                    <p class="position">Posición</p>
                    <div class="stats">
                        <span class="number">7</span>
                    </div>
                </div>
            </div>
        </div>
    </div>
</section>
```

#### 3.2 Sistema de Estadísticas de Jugadores
```html
<div class="player-stats-modal" id="playerStatsModal">
    <div class="modal-content">
        <div class="stats-header">
            <h4 class="player-name">Estadísticas Detalladas</h4>
            <button class="close-btn">&times;</button>
        </div>
        <div class="stats-body">
            <div class="stat-row">
                <div class="stat-category">Partidos Jugados</div>
                <div class="stat-value">25</div>
            </div>
            <div class="stat-row">
                <div class="stat-category">Minutos Jugados</div>
                <div class="stat-value">2250</div>
            </div>
            <div class="stat-chart">
                <canvas id="playerPerformanceChart"></canvas>
            </div>
        </div>
    </div>
</div>
```

**Características avanzadas:**
- Modal interactivo con estadísticas detalladas
- Gráficos dinámicos con Chart.js
- Animaciones de transición suaves
- Sistema de filtrado por posición

#### 3.3 Filtros y Ordenación
```html
<div class="filters-section mb-4">
    <div class="container">
        <div class="row align-items-center">
            <div class="col-md-4">
                <select class="form-select position-filter">
                    <option value="all">Todas las posiciones</option>
                    <option value="portero">Porteros</option>
                    <option value="defensa">Defensas</option>
                    <option value="centrocampista">Centrocampistas</option>
                    <option value="delantero">Delanteros</option>
                </select>
            </div>
            <div class="col-md-4">
                <div class="sort-buttons">
                    <button class="btn btn-outline-primary" data-sort="number">Por Número</button>
                    <button class="btn btn-outline-primary" data-sort="name">Por Nombre</button>
                </div>
            </div>
        </div>
    </div>
</div>
```

**Funcionalidades:**
- Filtrado dinámico por posición
- Ordenación múltiple de jugadores
- Actualización en tiempo real
- Persistencia de filtros seleccionados

**Características avanzadas:**
- Efecto hover con transformación 3D
- Popup de estadísticas al pasar el ratón
- Animación secuencial de entrada
- Optimización de imágenes con formato WebP

### 4. Página de Historia (historia.html)

#### 4.1 Línea Temporal
```html
<section class="timeline-section container my-5">
    <div class="timeline">
        <div class="timeline-item">
            <div class="timeline-content">
                <h3>1902</h3>
                <p>Fundación del Real Madrid Club de Fútbol</p>
                <img src="assets/historia/fundacion.jpg" alt="Fundación">
            </div>
        </div>
    </div>
</section>
```

**Implementación técnica:**
- Línea temporal vertical con conectores CSS
- Animaciones de aparición al hacer scroll
- Diseño alternado izquierda-derecha
- Imágenes con lazy loading

### 5. Página de Palmarés (palmares.html)

#### 5.1 Galería de Trofeos
```html
<section class="trophies-section container my-5">
    <div class="row">
        <div class="col-lg-4 col-md-6 mb-4">
            <div class="trophy-card" onclick="showImage('assets/trophies/champions.jpg')">
                <div class="trophy-image">
                    <img src="assets/trophies/champions-thumb.jpg" alt="Champions League">
                </div>
                <div class="trophy-info">
                    <h3>UEFA Champions League</h3>
                    <p>14 Títulos</p>
                </div>
            </div>
        </div>
    </div>
</section>
```

**Características:**
- Modal de imagen a pantalla completa
- Efecto de zoom suave al hover
- Animación de entrada con fade

#### 5.2 Sección de Estadísticas
```html
<section class="stats-section bg-light py-5">
    <div class="container">
        <div class="row text-center">
            <div class="col-md-3 col-6 mb-4">
                <div class="stat-item">
                    <div class="stat-number">14</div>
                    <div class="stat-label">Champions League</div>
                </div>
            </div>
            <div class="col-md-3 col-6 mb-4">
                <div class="stat-item">
                    <div class="stat-number">35</div>
                    <div class="stat-label">Ligas</div>
                </div>
            </div>
        </div>
    </div>
</section>
```

**Implementación:**
- Animación de contador para números
- Diseño responsive en grid de 2x2 en móvil
- Efectos hover interactivos
- Transiciones suaves

## Optimización y Rendimiento

### 1. Optimización de Imágenes
- Uso de formato WebP para mejor compresión
- Múltiples tamaños para diferentes dispositivos
- Lazy loading para mejorar el tiempo de carga

### 2. Rendimiento JavaScript
- Event delegation para mejor manejo de eventos
- Debouncing en funciones de scroll
- Código modular y reutilizable

### 3. Optimización CSS
- Uso de CSS Grid y Flexbox
- Variables CSS para consistencia
- Media queries optimizadas

## Accesibilidad

### 1. Características Implementadas
- Atributos ARIA apropiados
- Alto contraste en textos
- Navegación por teclado
- Textos alternativos en imágenes

### 2. Compatibilidad con Lectores de Pantalla
- Estructura HTML semántica
- Jerarquía de encabezados clara
- Descripciones para contenido interactivo


# EVIDENCIAS
- Tablero Trello
Esta captura es de cuando comencé con la creación del proyecto

![image](https://github.com/user-attachments/assets/280751ba-9f9e-445a-81c6-f0d9e99ec2db)

Y esta de cuando terminé

![image](https://github.com/user-attachments/assets/97a680d9-5f4b-4400-901c-f05e34e805c6)

- Control de versiones en GitHub

![Sin título](https://github.com/user-attachments/assets/9b9bc89a-fae4-4257-a9be-78c462db0c59)
![image](https://github.com/user-attachments/assets/d85049c4-4011-44a1-bcea-5ebb47fcce22)

- Y su guía de estilo

![image](https://github.com/user-attachments/assets/fbf1477f-40b9-4dc7-9e20-a56cd75ef091)


# BIBLIOGRAFÍA

[Enlace accesibilidad](https://www.eniun.com/tutorial-accesibilidad-web/) 

[Enlace usabilidad](https://www.eniun.com/tutorial-usabilidad-web/)

[Video personalización Bootstrap](https://www.youtube.com/watch?v=1kNwZbRiVcQ)

[Idea de las transiciones de las cards](https://www.w3schools.com/css/css3_transitions.asp)

