<!doctype html>
<html>
  <head>
    <title>Projeto AR - Coração Humano Interativo</title>
    <meta
      name="viewport"
      content="width=device-width, initial-scale=1.0, maximum-scale=1.0, user-scalable=no"
    />

    <script src="https://aframe.io/releases/1.6.0/aframe.min.js"></script>
    <script src="https://raw.githack.com/AR-js-org/AR.js/3.4.7/aframe/build/aframe-ar.js"></script>
    <script src="https://raw.githack.com/fcor/arjs-gestures/master/gesture-detector.js"></script>
    <script src="https://raw.githack.com/fcor/arjs-gestures/master/gesture-handler.js"></script>

    <style>
      body {
        margin: 0;
        overflow: hidden;
      }
      #ar-overlay {
        position: absolute;
        top: 10px;
        left: 10px;
        color: white;
        font-family: Arial, sans-serif;
        background: rgba(0, 0, 0, 0.4);
        padding: 8px 12px;
        border-radius: 6px;
        pointer-events: none;
        font-size: 14px;
        z-index: 10;
      }
    </style>
  </head>
  <body>
    <div id="ar-overlay">
      • Use 2 dedos para Zoom<br />
      • Use 1 dedo para Rotação<br />
      • O coração pulsa e audio toca
    </div>

    <a-scene
      embedded
      arjs="sourceType: webcam; debugUIEnabled: false;"
      gesture-detector
      renderer="antialias: true; logarithmicDepthBuffer: true;"
    >
      <a-assets>
        <audio id="batida" src="coracao-som.mp3" preload="auto"></audio>
      </a-assets>

      <a-marker
        preset="hiro"
        raycaster="objects: .clickable"
        emitevents="true"
        cursor="fuse: false; rayOrigin: mouse;"
      >
        <a-entity
          id="heart-container"
          class="clickable"
          gesture-handler
          position="0 0.3 0"
          scale="1 1 1"
        >
          <a-entity
            gltf-model="url(realistic_human_heart.glb)"
            scale="1 1 1"
            sound="src: #batida; autoplay: true; loop: true; volume: 10; positional: false"
            animation="property: scale; 
                       from: 0.8 0.8 0.8;
                       to: 1.1 1.1 1.1; 
                       dir: alternate; 
                       dur: 600; 
                       easing: easeInOutQuad; 
                       loop: true"
          >
          </a-entity>
        </a-entity>
      </a-marker>

      <a-entity camera></a-entity>
    </a-scene>
  </body>
</html>
