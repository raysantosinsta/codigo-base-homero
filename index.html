<!DOCTYPE html>
<html lang="pt-br">
<head>
    <meta charset="UTF-8">
    <title>Projeto AR - Interatividade Avançada</title>
    <script src="https://aframe.io/releases/1.3.0/aframe.min.js"></script>
    <script src="https://raw.githack.com/AR-js-org/AR.js/master/aframe/build/aframe-ar.js"></script>
    <script src="https://raw.githack.com/fcor/aframe-gesture-handler/master/dist/aframe-gesture-handler.js"></script>

    <style>
        body { margin: 0; overflow: hidden; font-family: sans-serif; }
        .ui-feedback {
            position: fixed; bottom: 20px; left: 50%; transform: translateX(-50%);
            background: rgba(0, 0, 0, 0.7); color: #00ff00;
            padding: 12px 25px; border-radius: 30px; z-index: 100;
            border: 1px solid #00ff00; pointer-events: none;
            text-align: center; font-size: 14px;
        }
    </style>
</head>

<body>
    <div class="ui-feedback">
        [Hiro Detectado] <br> 
        Use 1 dedo para girar • 2 dedos para zoom
    </div>

    <a-scene 
        embedded 
        arjs="sourceType: webcam; debugUIEnabled: false; detectionMode: mono_and_matrix; matrixCodeType: 3x3;"
        gesture-detector
        renderer="logarithmicDepthBuffer: true; colorManagement: true;">

        <a-assets>
            <a-asset-item id="modelo-opt" src="https://arjs-cors-proxy.herokuapp.com/https://raw.gstreamer.net/A-Frame/assets/master/test-models/models/glTF-2.0/duck/Scene.gltf"></a-asset-item>
        </a-assets>

        <a-marker preset="hiro" raycaster="objects: .clickable" emitevents="true" cursor="fuse: false; rayOrigin: mouse;">
            
            <a-entity
                id="objeto-interativo"
                class="clickable"
                gltf-model="url(https://raw.githubusercontent.com/KhronosGroup/glTF-Sample-Models/master/2.0/DamagedHelmet/glTF/DamagedHelmet.gltf)"
                scale="1.5 1.5 1.5"
                position="0 0.5 0"
                rotation="0 0 0"
                gesture-handler="minScale: 0.25; maxScale: 5"
                animation__pulse="property: scale; to: 1.6 1.6 1.6; dir: alternate; dur: 2000; loop: true; easing: easeInOutQuad">
                
                <a-light id="feedback-luz" type="point" intensity="0" color="#00ff00" position="0 1 1"></a-light>
            </a-entity>

        </a-marker>

        <a-entity camera></a-entity>
    </a-scene>

    <script>
        // Interação 2: Feedback visual via clique/toque (Aumenta brilho)
        const el = document.querySelector('#objeto-interativo');
        const luz = document.querySelector('#feedback-luz');

        el.addEventListener('click', function () {
            luz.setAttribute('animation', 'property: intensity; from: 5; to: 0; dur: 500');
            console.log("Interação capturada: Feedback visual ativado.");
        });
    </script>
</body>
</html>