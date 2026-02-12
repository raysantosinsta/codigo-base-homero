<!DOCTYPE html>
<html>
<head>
  <title>AR Med - Monitoramento Realtime</title>
  <meta charset="utf-8">
  <script src="https://aframe.io/releases/1.3.0/aframe.min.js"></script>
  <script src="https://raw.githack.com/AR-js-org/AR.js/master/aframe/build/aframe-ar.js"></script>
  <script src="https://unpkg.com/aframe-event-set-component@5.0.0/dist/aframe-event-set-component.min.js"></script>
  
  <style>
    body { margin: 0; overflow: hidden; font-family: 'Segoe UI', sans-serif; }
    #dashboard {
      position: fixed; top: 20px; left: 20px;
      background: rgba(0, 0, 0, 0.85); color: #00e5ff;
      padding: 15px; border-radius: 10px; z-index: 1000;
      border: 1px solid #00e5ff; min-width: 150px;
    }
    .label { font-size: 10px; color: #888; margin-bottom: 5px; }
    .value { font-size: 24px; font-weight: bold; }
    #status { font-size: 12px; margin-top: 5px; }
  </style>
</head>

<body>
  <div id="dashboard">
    <div class="label">BATIMENTOS</div>
    <div id="bpm-display" class="value">-- BPM</div>
    <div id="status" style="color: #ff0000;">Conectando API...</div>
  </div>

  <a-scene embedded arjs="sourceType: webcam; debugUIEnabled: false;">
    <a-entity camera>
      <a-entity cursor="rayOrigin: mouse" raycaster="objects: .clickable"></a-entity>
    </a-entity>

    <a-marker preset="hiro">
      <a-entity 
        id="coracao"
        class="clickable"
        gltf-model="url(realistic_human_heart.glb)"
        scale="1 1 1" 
        position="0 0.5 0"
        material="emissiveIntensity: 0.6">
      </a-entity>

      <a-text id="ar-text" value="Lendo dados..." position="0 1.5 0" align="center" scale="0.7 0.7 0.7"></a-text>
    </a-marker>
  </a-scene>

  <script>
    const heartEl = document.querySelector('#coracao');
    const bpmDisplay = document.querySelector('#bpm-display');
    const statusDisplay = document.querySelector('#status');
    const arText = document.querySelector('#ar-text');

    // Mude para o link atual do seu Localtunnel
    const API_URL = "https://new-paths-begin.loca.lt/paciente/1";

    async function getMedicalData() {
      try {
        const response = await fetch(API_URL, {
          method: 'GET',
          headers: {
            // Pula a tela de "Tunnel Password" do localtunnel
            "bypass-tunnel-reminder": "true",
            "Accept": "application/json"
          }
        });

        if (!response.ok) throw new Error('Offline');

        const data = await response.json();

        // 1. Atualiza interface 2D
        bpmDisplay.innerText = `${data.bpm} BPM`;
        statusDisplay.innerText = data.status;
        statusDisplay.style.color = data.cor;

        // 2. Atualiza Coração (Cor e Pulsação leve)
        heartEl.setAttribute('material', `color: ${data.cor}; emissive: ${data.cor}`);
        const pulse = 1 + (data.bpm / 500);
        heartEl.setAttribute('scale', `${pulse} ${pulse} ${pulse}`);

        // 3. Atualiza Texto no AR
        arText.setAttribute('value', `${data.bpm} BPM\n${data.status}`);
        arText.setAttribute('color', data.cor);

      } catch (error) {
        console.error("Erro na API:", error);
        statusDisplay.innerText = "API OFFLINE";
        statusDisplay.style.color = "#ff0000";
      }
    }

    // Busca dados a cada 2 segundos
    setInterval(getMedicalData, 2000);
  </script>
</body>
</html>