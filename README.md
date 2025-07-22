<!DOCTYPE html>
<html lang="es">
<head>
  <meta charset="UTF-8" />
  <meta name="viewport" content="width=device-width, initial-scale=1" />
  <title>🕷 Araña de Seda Dorada | El mundo de las Arañas</title> 
  <link rel="preconnect" href="https://fonts.googleapis.com">
  <link rel="preconnect" href="https://fonts.gstatic.com" crossorigin>
  <link href="https://fonts.googleapis.com/css2?family=Poppins:wght@300;400;600;700&family=Roboto+Condensed:wght@400;700&display=swap" rel="stylesheet">
  <link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.4.0/css/all.min.css">
  <!-- Leaflet CSS -->
  <link rel="stylesheet" href="https://unpkg.com/leaflet@1.9.4/dist/leaflet.css" />
  <style>
    :root {
      --primary: #D4AF37; /* Dorado */
      --primary-dark: #B8860B;
      --primary-light: #FFD700;
      --secondary: #F1C40F;
      --dark: #0F0F0F;
      --darker: #080808;
      --light: #F8F9FA;
      --gray: #495057;
    }

    /* ... (mantener todos los estilos igual que antes) ... */
  </style>
</head>
<body>
  <!-- Fondo de telaraña -->
  <div class="web-background"></div>

  <header>
    <h1>Araña de Seda Dorada</h1>
    <div class="scientific-name">Nephila clavipes</div>
    <div class="danger-label">Peligrosidad: Moderada</div>
  </header>

  <div class="main-container">
    <div class="info-section">
      <h2 class="section-title">Descripción</h2>
      <p>La araña de seda dorada (<em>Nephila clavipes</em>) es conocida por su impresionante telaraña de color dorado y su gran tamaño. Estas arañas son famosas por producir una de las sedas más fuertes y resistentes del mundo animal, con propiedades mecánicas superiores al acero en relación a su peso.</p>
      
      <p>Las hembras son significativamente más grandes que los machos (hasta 5 veces más), con cuerpos que pueden alcanzar los 5 cm de longitud y patas que se extienden hasta 15 cm. Su coloración es predominantemente amarillo dorado con marcas blancas y negras en el abdomen.</p>
      
      <h3 class="section-title" style="margin-top: 2rem;">Características clave</h3>
      <ul>
        <li>Tamaño: Hembras 3-5 cm, machos 0.5-1 cm</li>
        <li>Coloración: Amarillo dorado con marcas blancas y negras</li>
        <li>Hábitat: Bosques tropicales y subtropicales</li>
        <li>Dieta: Insectos voladores (moscas, mosquitos, mariposas)</li>
        <li>Comportamiento: Constructoras de grandes telarañas orbiculares</li>
        <li>Esperanza de vida: Hembras 1 año, machos 3-4 meses</li>
      </ul>
    </div>

    <div class="info-section">
      <h2 class="section-title">Galería</h2>
      <div class="gallery">
        <div class="gallery-item">
          <img src="https://upload.wikimedia.org/wikipedia/commons/thumb/8/8d/Nephila_clavipes_by_Line1.jpg/800px-Nephila_clavipes_by_Line1.jpg" alt="Araña de seda dorada en su telaraña">
          <div class="gallery-caption">Ejemplar adulto en su característica telaraña</div>
        </div>
        <div class="gallery-item">
          <img src="https://www.researchgate.net/publication/335575642/figure/fig1/AS:798434735656960@1567358738925/Golden-silk-orb-weaver-Nephila-clavipes-spider-with-prey-in-its-web-The-spider-is.jpg" alt="Detalle de la seda dorada">
          <div class="gallery-caption">Detalle de la seda dorada al sol</div>
        </div>
        <div class="gallery-item">
          <img src="https://bugguide.net/images/raw/L0Q/HRQ/L0QHRQ0L0RZR7RZR1RZR5R0RZR7RZR1R0RZR5R0RZR7RZR1R0RZR5R0RZR7RZR1R0RZR5R0RZR7RZR1R0RZR5R0RZR7RZR1R0RZR5R0RZR7RZR1R0RZ5R.jpg" alt="Comparación hembra y macho">
          <div class="gallery-caption">Diferencia de tamaño entre hembra (grande) y macho (pequeño)</div>
        </div>
        <div class="gallery-item">
          <img src="https://live.staticflickr.com/65535/51116590297_0c1c3a3f8b_b.jpg" alt="Araña con presa">
          <div class="gallery-caption">Capturando una mariposa en su telaraña</div>
        </div>
      </div>
    </div>

    <div class="info-section">
      <h2 class="section-title">Datos Científicos</h2>
      <div class="data-grid">
        <div class="data-card">
          <h3>Reino</h3>
          <p>Animalia</p>
        </div>
        <div class="data-card">
          <h3>Filo</h3>
          <p>Arthropoda</p>
        </div>
        <div class="data-card">
          <h3>Clase</h3>
          <p>Arachnida</p>
        </div>
        <div class="data-card">
          <h3>Orden</h3>
          <p>Araneae</p>
        </div>
        <div class="data-card">
          <h3>Familia</h3>
          <p>Araneidae</p>
        </div>
        <div class="data-card">
          <h3>Género</h3>
          <p>Nephila</p>
        </div>
      </div>
    </div>

    <div class="info-section">
      <h2 class="section-title">Distribución Geográfica</h2>
      <p>La araña de seda dorada se encuentra en regiones tropicales y subtropicales del continente americano, desde el sureste de Estados Unidos hasta Argentina. Prefiere hábitats húmedos como bosques, manglares y áreas cercanas a cuerpos de agua donde abundan los insectos voladores.</p>
      
      <div class="map-container">
        <div id="distribution-map"></div>
        <div class="map-legend">
          <span class="legend-color"></span> Distribución en América
        </div>
      </div>
    </div>

    <!-- ... (resto de las secciones se mantienen igual) ... -->
  </div>

  <footer>
    <a href="spider-world.html" class="back-button">
      <i class="fas fa-arrow-left"></i> Volver al Mundo de las Arañas
    </a>
    <div class="footer-bottom">
      &copy; 2025 El mundo de las Arañas. Todos los derechos reservados. | Especial Arañas de Seda Dorada
    </div>
  </footer>

  <!-- Leaflet JS -->
  <script src="https://unpkg.com/leaflet@1.9.4/dist/leaflet.js"></script>
  <script>
    // Efecto de movimiento para el fondo de telaraña
    document.addEventListener('mousemove', (e) => {
      const web = document.querySelector('.web-background');
      const x = e.clientX / window.innerWidth;
      const y = e.clientY / window.innerHeight;
      web.style.transform = `translate(${x * 20}px, ${y * 20}px)`;
    });

    // Efecto de revelado al hacer scroll
    const observer = new IntersectionObserver((entries) => {
      entries.forEach(entry => {
        if (entry.isIntersecting) {
          entry.target.style.opacity = 1;
          entry.target.style.transform = 'translateY(0)';
        }
      });
    }, { threshold: 0.1 });

    document.querySelectorAll('.info-section, .venom-section').forEach(section => {
      section.style.opacity = 0;
      section.style.transform = 'translateY(30px)';
      section.style.transition = 'all 0.6s ease';
      observer.observe(section);
    });

    // Mapa de distribución corregido
    document.addEventListener('DOMContentLoaded', () => {
      const map = L.map('distribution-map').setView([10, -80], 3);
      
      // Capa base oscura
      L.tileLayer('https://{s}.basemaps.cartocdn.com/dark_all/{z}/{x}/{y}{r}.png', {
        attribution: '&copy; <a href="https://www.openstreetmap.org/copyright">OpenStreetMap</a> contributors'
      }).addTo(map);

      // Área de distribución aproximada (coordenadas simplificadas)
      const distributionCoords = [
        [30, -100], [30, -75], [15, -60], [5, -50], 
        [-5, -35], [-15, -30], [-30, -40], [-40, -60], 
        [-40, -80], [-30, -70], [-20, -60], [-10, -50],
        [5, -60], [15, -75], [30, -100]
      ];
      
      L.polygon([distributionCoords], {
        color: '#D4AF37',
        fillColor: '#FFD700',
        fillOpacity: 0.2,
        weight: 1
      }).addTo(map).bindPopup('<b>Área de distribución</b><br>Nephila clavipes');

      // Puntos de mayor densidad (coordenadas válidas)
      const densityPoints = [
        { lat: 25.5, lng: -80.2, name: 'Florida, USA', density: 'Alta' },
        { lat: 18.1, lng: -77.3, name: 'Jamaica', density: 'Muy alta' },
        { lat: 9.9, lng: -83.9, name: 'Costa Rica', density: 'Muy alta' },
        { lat: 8.6, lng: -71.2, name: 'Venezuela', density: 'Alta' },
        { lat: -3.5, lng: -62.5, name: 'Amazonas', density: 'Alta' },
        { lat: -15.8, lng: -47.9, name: 'Brasil Central', density: 'Media' },
        { lat: -25.3, lng: -57.6, name: 'Paraguay', density: 'Baja' },
        { lat: -34.6, lng: -58.4, name: 'Argentina Norte', density: 'Baja' }
      ];

      densityPoints.forEach(point => {
        L.circleMarker([point.lat, point.lng], {
          radius: 8,
          color: '#B8860B',
          fillColor: '#FFD700',
          fillOpacity: 0.7,
          weight: 1
        }).addTo(map).bindPopup(`<b>${point.name}</b><br>Densidad: ${point.density}`);
      });

      // Nota de distribución
      L.control({position: 'bottomleft'}).addTo(map).getContainer().innerHTML = 
        '<div style="background: rgba(0,0,0,0.7); padding: 5px; color: white; border-radius: 5px; font-size: 12px;">Distribución desde el sureste de EE.UU. hasta el norte de Argentina</div>';
    });
  </script>
</body>
</html>
