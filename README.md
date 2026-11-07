# LISTEN-TO-CAPI
primera vez
<html lang="es">
<head>
  <meta charset="UTF-8" />
  <meta name="viewport" content="width=device-width, initial-scale=1.0" />
  <title>Listen to Capi</title>
  <link rel="stylesheet" href="style.css" />
  <!-- Iconos de FontAwesome -->
  <link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.4.0/css/all.min.css" />
</head>
<body>

  <!-- Barra lateral (Navegación) -->
  <aside class="sidebar">
    <div class="logo">
      <i class="fa-solid fa-headphones"></i>
      <span>Listen to Capi</span>
    </div>
    <nav class="menu">
      <button class="nav-btn active" data-tab="home"><i class="fa-solid fa-house"></i> Inicio</button>
      <button class="nav-btn" data-tab="liked"><i class="fa-solid fa-heart"></i> Me Gusta</button>
      <button class="nav-btn" data-tab="history"><i class="fa-solid fa-clock-rotate-left"></i> Historial</button>
      <button class="nav-btn" data-tab="downloads"><i class="fa-solid fa-download"></i> Descargas (Sin Internet)</button>
    </nav>
    <div class="offline-toggle">
      <label for="connection-mode">Modo Sin Internet</label>
      <input type="checkbox" id="connection-mode" />
    </div>
  </aside>

  <!-- Contenido principal -->
  <main class="main-content">
    <!-- Header con buscador -->
    <header class="top-bar">
      <div class="search-box">
        <i class="fa-solid fa-magnifying-glass"></i>
        <input type="text" id="search-input" placeholder="Buscar cualquier artista, canción o álbum..." />
      </div>
    </header>

    <!-- Contenedor dinámico -->
    <section class="content-section">
      <h2 id="section-title">Canciones Tendencia</h2>
      <div id="music-grid" class="music-grid">
        <!-- Las tarjetas se generan dinámicamente -->
      </div>
    </section>
  </main>

  <!-- Reproductor Inferior Fijo -->
  <footer class="player-bar">
    <div class="now-playing">
      <img id="player-cover" src="https://picsum.photos/seed/capi/80/80" alt="Carátula" />
      <div class="track-details">
        <h4 id="player-title">Selecciona una canción</h4>
        <p id="player-artist">Listen to Capi</p>
      </div>
      <button id="player-like-btn" class="icon-btn"><i class="fa-regular fa-heart"></i></button>
    </div>

    <div class="player-controls">
      <div class="control-buttons">
        <button id="prev-btn" class="ctrl-btn"><i class="fa-solid fa-backward-step"></i></button>
        <button id="play-btn" class="ctrl-btn main-play"><i class="fa-solid fa-play"></i></button>
        <button id="next-btn" class="ctrl-btn"><i class="fa-solid fa-forward-step"></i></button>
      </div>
      <div class="progress-container">
        <span id="current-time">0:00</span>
        <input type="range" id="progress-bar" value="0" min="0" max="100" />
        <span id="total-duration">0:00</span>
      </div>
    </div>

    <div class="right-controls">
      <button id="lyrics-btn" class="icon-btn-text" title="Ver Letra"><i class="fa-solid fa-align-left"></i> Letra</button>
      <div class="volume-container">
        <i class="fa-solid fa-volume-high"></i>
        <input type="range" id="volume-bar" value="100" min="0" max="100" />
      </div>
    </div>
  </footer>

  <!-- Modal para ver el Videoclip -->
  <div id="video-modal" class="modal">
    <div class="modal-content">
      <span class="close-modal" id="close-video">&times;</span>
      <h3 id="video-title">Videoclip</h3>
      <div class="video-container">
        <iframe id="video-frame" src="" frameborder="0" allowfullscreen></iframe>
      </div>
    </div>
  </div>

  <!-- Modal / Ventana Emergente para Letras -->
  <div id="lyrics-modal" class="modal">
    <div class="modal-content lyrics-content">
      <span class="close-modal" id="close-lyrics">&times;</span>
      <h3 id="lyrics-title">Letra de la canción</h3>
      <h4 id="lyrics-artist" class="sub-text">Artista</h4>
      <div id="lyrics-body" class="lyrics-body">
        Cargando letra...
      </div>
    </div>
  </div>

  <audio id="audio-element"></audio>

  <script src="script.js"></script>
</body>
</html>
