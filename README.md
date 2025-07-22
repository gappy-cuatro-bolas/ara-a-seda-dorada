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

    * {
      margin: 0;
      padding: 0;
      box-sizing: border-box;
    }

    body {
      margin: 0;
      background-color: var(--darker);
      color: var(--light);
      font-family: 'Poppins', sans-serif;
      min-height: 100vh;
      overflow-x: hidden;
    }

    .web-background {
      position: fixed;
      top: 0;
      left: 0;
      width: 100%;
      height: 100%;
      background-image: url('https://www.transparenttextures.com/patterns/silver-scales.png');
      opacity: 0.05;
      z-index: -1;
      pointer-events: none;
    }

    header {
      background: linear-gradient(135deg, rgba(15, 15, 15, 0.9), rgba(30, 30, 30, 0.9));
      padding: 3rem 1rem 2rem;
      text-align: center;
      position: relative;
      overflow: hidden;
      backdrop-filter: blur(5px);
      border-bottom: 1px solid rgba(212, 175, 55, 0.3);
    }

    header h1 {
      font-size: 2.5rem;
      font-family: 'Roboto Condensed', sans-serif;
      color: var(--primary-light);
      margin: 0;
      text-shadow: 0 0 10px var(--primary), 0 0 20px rgba(212, 175, 55, 0.5);
      letter-spacing: 1px;
    }

    .scientific-name {
      font-style: italic;
      font-size: 1.2rem;
      color: var(--primary);
      margin: 0.5rem 0;
    }

    .danger-label {
      display: inline-block;
      background: rgba(244, 164, 96, 0.2);
      color: var(--warning);
      padding: 0.3rem 1rem;
      border-radius: 50px;
      font-size: 0.9rem;
      margin-top: 0.5rem;
      border: 1px solid rgba(244, 164, 96, 0.3);
    }

    .main-container {
      max-width: 1200px;
      margin: 2rem auto;
      padding: 0 1.5rem;
    }

    .info-section {
      background: rgba(20, 20, 20, 0.7);
      border-radius: 15px;
      padding: 2rem;
      margin-bottom: 2rem;
      backdrop-filter: blur(10px);
      border: 1px solid rgba(212, 175, 55, 0.1);
      box-shadow: 0 5px 20px rgba(0, 0, 0, 0.3);
    }

    .section-title {
      color: var(--primary);
      font-size: 1.8rem;
      margin-bottom: 1.5rem;
      position: relative;
      padding-bottom: 0.5rem;
    }

    .section-title::after {
      content: '';
      position: absolute;
      bottom: 0;
      left: 0;
      width: 60px;
      height: 2px;
      background: var(--primary);
    }

    p {
      line-height: 1.7;
      margin-bottom: 1rem;
    }

    ul {
      margin: 1rem 0;
      padding-left: 1.5rem;
    }

    li {
      margin-bottom: 0.5rem;
      line-height: 1.5;
    }

    .gallery {
      display: grid;
      grid-template-columns: repeat(auto-fill, minmax(250px, 1fr));
      gap: 1.5rem;
      margin-top: 1.5rem;
    }

    .gallery-item {
      background: rgba(30, 30, 30, 0.7);
      border-radius: 10px;
      overflow: hidden;
      box-shadow: 0 5px 15px rgba(0, 0, 0, 0.2);
      transition: transform 0.3s ease;
    }

    .gallery-item:hover {
      transform: translateY(-5px);
    }

    .gallery-item img {
      width: 100%;
      height: 200px;
      object-fit: cover;
      border-bottom: 1px solid rgba(212, 175, 55, 0.1);
    }

    .gallery-caption {
      padding: 1rem;
      font-size: 0.9rem;
      color: rgba(255, 255, 255, 0.8);
      text-align: center;
    }

    .data-grid {
      display: grid;
      grid-template-columns: repeat(auto-fill, minmax(150px, 1fr));
      gap: 1rem;
      margin-top: 1.5rem;
    }

    .data-card {
      background: rgba(30, 30, 30, 0.7);
      border-radius: 8px;
      padding: 1rem;
      text-align: center;
      border: 1px solid rgba(212, 175, 55, 0.1);
    }

    .data-card h3 {
      color: var(--primary);
      font-size: 1rem;
      margin-bottom: 0.5rem;
    }

    .data-card p {
      font-size: 0.9rem;
      color: rgba(255, 255, 255, 0.8);
    }

    .map-container {
      margin-top: 2rem;
      border-radius: 10px;
      overflow: hidden;
      box-shadow: 0 5px 15px rgba(0, 0, 0, 0.3);
    }

    #distribution-map {
      height: 400px;
      width: 100%;
    }

    .map-legend {
      background: rgba(20, 20, 20, 0.8);
      padding: 0.5rem 1rem;
      font-size: 0.9rem;
      display: flex;
      align-items: center;
      gap: 0.5rem;
    }

    .legend-color {
      display: inline-block;
      width: 15px;
      height: 15px;
      background: var(--primary-light);
      border-radius: 3px;
    }

    footer {
      background: linear-gradient(to top, rgba(15, 15, 15, 0.9), rgba(8, 8, 8, 0.95));
      color: var(--light);
      padding: 3rem 1rem 2rem;
      text-align: center;
      position: relative;
      margin-top: 3rem;
    }

    .back-button {
      display: inline-flex;
      align-items: center;
      justify-content: center;
      padding: 0.8rem 1.5rem;
      background: rgba(212, 175, 55, 0.1);
      color: var(--primary-light);
      border-radius: 50px;
      text-decoration: none;
      transition: all 0.3s ease;
      margin-bottom: 1.5rem;
      border: 1px solid rgba(212, 175, 55, 0.3);
    }

    .back-button:hover {
      background: rgba(212, 175, 55, 0.2);
      transform: translateY(-2px);
    }

    .back-button i {
      margin-right: 8px;
    }

    .footer-bottom {
      margin-top: 1.5rem;
      font-size: 0.9rem;
      color: rgba(255, 255, 255, 0.6);
      padding-top: 1.5rem;
      border-top: 1px solid rgba(212, 175, 55, 0.1);
    }

    /* Responsive design */
    @media (max-width: 768px) {
      header h1 {
        font-size: 2rem;
      }
      
      .scientific-name {
        font-size: 1rem;
      }
      
      .main-container {
        padding: 0 1rem;
      }
      
      .info-section {
        padding: 1.5rem;
      }
      
      .section-title {
        font-size: 1.5rem;
      }
      
      .gallery {
        grid-template-columns: 1fr;
      }
      
      #distribution-map {
        height: 300px;
      }
    }

    @media (max-width: 480px) {
      header {
        padding: 2rem 1rem 1.5rem;
      }
      
      header h1 {
        font-size: 1.8rem;
      }
      
      .data-grid {
        grid-template-columns: 1fr 1fr;
      }
    }
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
          <img src="https://live.staticflickr.com/65535/34031771221_7fb3341952_z.jpg" alt="Araña de seda dorada en su telaraña">
          <div class="gallery-caption">Ejemplar adulto en su característica telaraña</div>
        </div>
        <div class="gallery-item">
          <img src="https://static.wikia.nocookie.net/reinoanimalia/images/9/9b/800px-Golden_silk_spider_-_Nephila_clavipes.jpg/revision/latest?cb=20181129173654&path-prefix=es" alt="Detalle de la seda dorada">
          <div class="gallery-caption">Detalle de la seda dorada al sol</div>
        </div>
        <div class="gallery-item">
          <img src="https://ecuador.inaturalist.org/photos/159133368" alt="Comparación hembra y macho">
          <div class="gallery-caption">Diferencia de tamaño entre hembra (grande) y macho (pequeño)</div>
        </div>
        <div class="gallery-item">
          <img src="https://inaturalist-open-data.s3.amazonaws.com/photos/202183994/original.jpeg" alt="Araña con presa">
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

    <div class="info-section">
      <h2 class="section-title">Seda Dorada</h2>
      <p>La seda producida por <em>Nephila clavipes</em> es notable por su color dorado y sus excepcionales propiedades mecánicas. Es una de las sedas naturales más fuertes conocidas, con una resistencia a la tracción comparable al acero de alto grado, pero mucho más ligera y flexible.</p>
      
      <p>La seda dorada tiene múltiples usos potenciales en aplicaciones biomédicas (como suturas quirúrgicas) y en la industria de materiales. Investigadores están estudiando cómo replicar sus propiedades para crear nuevos materiales avanzados.</p>
      
      <h3 class="section-title" style="margin-top: 2rem;">Propiedades de la seda</h3>
      <ul>
        <li>Resistencia a la tracción: ~1.1 GPa (similar al acero)</li>
        <li>Elasticidad: Puede estirarse hasta un 40% de su longitud original</li>
        <li>Color: Amarillo dorado debido a pigmentos carotenoides</li>
        <li>Producción: Una araña puede producir hasta 150 metros de seda en un día</li>
      </ul>
    </div>

    <div class="info-section">
      <h2 class="section-title">Comportamiento</h2>
      <p>Estas arañas son diurnas y pasan la mayor parte de su tiempo en el centro de sus grandes telarañas orbiculares, que pueden alcanzar más de 1 metro de diámetro. Las hembras son territoriales y pueden permanecer en la misma telaraña durante semanas, reparándola diariamente.</p>
      
      <p>Los machos, mucho más pequeños, a menudo comparten la telaraña de una hembra y compiten por la oportunidad de aparearse. Después del apareamiento, la hembra produce un saco de huevos que puede contener cientos de huevos, protegido por una densa capa de seda dorada.</p>
    </div>
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

    document.querySelectorAll('.info-section').forEach(section => {
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
