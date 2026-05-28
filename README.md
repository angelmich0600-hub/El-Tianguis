
<html lang="es">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>El Tianguis - Audio Tienda Pro</title>
    <style>
        body {
            font-family: 'Segoe UI', Roboto, Helvetica, Arial, sans-serif;
            background-color: #f1f5f9;
            color: #1e293b;
            display: flex;
            justify-content: center;
            align-items: center;
            min-height: 100vh;
            margin: 0;
            padding: 12px;
            box-sizing: border-box;
        }
        .container {
            text-align: center;
            background-color: #ffffff;
            padding: 20px 16px;
            border-radius: 16px;
            box-shadow: 0 4px 20px rgba(0,0,0,0.08);
            max-width: 360px;
            width: 100%;
            box-sizing: border-box;
        }
        
        /* --- DISEÑO DE LOGO AJUSTADO --- */
        .logo-container {
            width: 75px;
            height: 75px;
            margin: 0 auto 8px auto;
            display: flex;
            justify-content: center;
            align-items: center;
        }
        .logo-svg {
            width: 100%;
            height: 100%;
        }

        /* --- TEXTOS PRINCIPALES PROPORCIONALES --- */
        .brand-title {
            font-family: 'Arial Black', Impact, sans-serif;
            font-size: 26px;
            color: #0f172a;
            margin: 0;
            text-transform: uppercase;
            letter-spacing: -0.5px;
            line-height: 1.1;
        }
        .brand-subtitle {
            font-size: 14px;
            font-weight: 700;
            color: #16a34a;
            margin: 2px 0 10px 0;
            text-transform: uppercase;
            letter-spacing: 1px;
        }
        .description {
            color: #64748b;
            font-size: 13px;
            line-height: 1.4;
            margin: 0 0 16px 0;
            padding: 0 8px;
        }

        /* --- SECCIONES Y CONTROLES ESTILIZADOS --- */
        .seccion {
            background-color: #f8fafc;
            border: 1px solid #e2e8f0;
            padding: 12px;
            border-radius: 12px;
            margin-bottom: 12px;
            text-align: left;
            box-sizing: border-box;
        }
        .seccion-titulo {
            font-size: 12px;
            color: #64748b;
            margin-bottom: 8px;
            font-weight: 700;
            text-transform: uppercase;
            letter-spacing: 0.5px;
        }

        /* --- SELECTOR DE TIEMPO MANUAL --- */
        .input-tiempo-container {
            display: flex;
            align-items: center;
            justify-content: space-between;
            background-color: #ffffff;
            border: 1px solid #cbd5e1;
            padding: 8px 12px;
            border-radius: 8px;
            margin-bottom: 10px;
        }
        .input-tiempo-container label {
            font-size: 13px;
            color: #334155;
            font-weight: 600;
        }
        .input-tiempo-container input {
            width: 60px;
            padding: 6px;
            font-size: 15px;
            font-weight: 700;
            text-align: center;
            border: 1.5px solid #0f172a;
            border-radius: 6px;
            color: #0f172a;
            outline: none;
        }

        /* --- BOTONES ADAPTADOS PARA MÓVIL --- */
        button {
            color: white;
            border: none;
            padding: 12px 14px;
            font-size: 14px;
            font-weight: 700;
            border-radius: 8px;
            cursor: pointer;
            transition: all 0.2s ease;
            width: 100%;
            margin: 2px 0;
            box-sizing: border-box;
            display: flex;
            justify-content: center;
            align-items: center;
            gap: 6px;
        }
        button:active { transform: scale(0.98); }
        
        .btn-grabar { background-color: #2563eb; }
        .btn-grabar.grabando { background-color: #dc2626; animation: parpadeo 1s infinite; }
        .btn-play { background-color: #0f172a; }
        .btn-play.stop { background-color: #dc2626; }
        button:disabled { background-color: #cbd5e1; color: #94a3b8; cursor: not-allowed; }

        /* --- DISPLAY DE ESTADO Y TIEMPO COMPACTO --- */
        .display-box {
            display: flex;
            border: 1px solid #cbd5e1;
            border-radius: 8px;
            overflow: hidden;
            margin-top: 10px;
            background: #ffffff;
        }
        .display-left, .display-right {
            flex: 1;
            padding: 8px;
            display: flex;
            flex-direction: column;
            justify-content: center;
            align-items: center;
        }
        .display-left {
            border-right: 1px solid #cbd5e1;
            background-color: #f8fafc;
        }
        .display-label {
            font-size: 10px;
            color: #64748b;
            font-weight: 700;
            text-transform: uppercase;
            margin-bottom: 2px;
        }
        .status-text {
            font-size: 13px;
            color: #0f172a;
            font-weight: 700;
        }
        .timer {
            font-size: 24px;
            font-weight: 800;
            color: #16a34a;
            font-variant-numeric: tabular-nums;
            line-height: 1;
        }

        /* --- CINTILLO MARCAS INFERIOR --- */
        .cintillo-saldos {
            background-color: #f97316;
            color: #ffffff;
            font-size: 14px;
            font-weight: 700;
            padding: 6px;
            border-radius: 6px;
            margin-top: 18px;
            text-transform: uppercase;
            letter-spacing: 0.5px;
        }
        .marcas-grid {
            display: flex;
            justify-content: space-around;
            align-items: center;
            margin-top: 10px;
            padding: 0 4px;
        }
        .marca {
            font-size: 11px;
            font-weight: 800;
            color: #475569;
        }
        .marca-cvs { color: #dc2626; display: flex; align-items: center; gap: 2px;}
        .marca-amazon { color: #0f172a; font-style: italic; }
        .marca-target { color: #dc2626; font-weight: 900; }
        .marca-walmart { color: #0284c7; }

        @keyframes parpadeo {
            0% { opacity: 1; }
            50% { opacity: 0.7; }
            100% { opacity: 1; }
        }
    </style>
</head>
<body>

<div class="container">
    <div class="logo-container">
        <svg class="logo-svg" viewBox="0 0 512 512" fill="none" xmlns="http://www.w3.org/2000/svg">
            <path d="M166 210V140C166 90.3 206.3 50 256 50C305.7 50 346 90.3 346 140V210" stroke="#f97316" stroke-width="32" stroke-linecap="round"/>
            <path d="M166 210H380C410 210 426 235 422 265L392 435C388 455 370 470 350 470H256C254 415 210 370 155 370C155 340 140 290 150 265C155 240 146 210 166 210Z" fill="#f97316"/>
            <path d="M155 370C210 370 254 415 256 470H115C95 470 80 452 83 432L93 376C98 346 125 370 155 370Z" fill="#ffffff"/>
            <path d="M165 345L70 425C62 432 50 424 54 414L102 300C107 288 123 286 130 297L164 328C171 334 171 340 165 345Z" fill="#0f172a"/>
        </svg>
    </div>
    
    <div class="brand-title">El Tianguis</div>
    <div class="brand-subtitle">Audio Tienda Pro</div>
    
    <p class="description">
        Graba tus anuncios de ofertas. Define los minutos de espera y sonarán interrumpiendo sutilmente la música.
    </p>
    
    <div class="seccion">
        <div class="seccion-titulo">1. Grabar Anuncio</div>
        <button id="btnGrabar" class="btn-grabar" onclick="toglearGrabacion()">🎙️ Grabar Micrófono</button>
        <div id="estadoGrabacion" style="font-size: 11px; color: #64748b; margin-top: 6px; font-weight: 500; text-align: center;">Sin audio grabado</div>
    </div>

    <div class="seccion">
        <div class="seccion-titulo">2. Ajuste de Tiempo y Control</div>
        
        <div class="input-tiempo-container">
            <label for="inputMinutos">Repetir cada (minutos):</label>
            <input type="number" id="inputMinutos" value="30" min="1" max="120">
        </div>

        <button id="btnSistema" class="btn-play" onclick="toglearSistema()" disabled>▶️ Iniciar Sistema</button>
        
        <div class="display-box">
            <div class="display-left">
                <span class="display-label">Estado</span>
                <span id="estadoSistema" class="status-text">Apagado</span>
            </div>
            <div class="display-right">
                <span class="display-label">Próximo Audio</span>
                <div class="timer" id="cuentaRegresiva">00:00</div>
            </div>
        </div>
    </div>

    <div class="cintillo-saldos">Saldos Americanos</div>
    <div class="marcas-grid">
        <span class="marca marca-cvs">❤️ CVS</span>
        <span class="marca marca-amazon">amazon</span>
        <span class="marca marca-target">🎯 TARGET</span>
        <span class="marca marca-walmart">Walmart ☀️</span>
    </div>
</div>

<script>
    let mediaRecorder;
    let audioBlobs = [];
    let audioUrl = null;
    let audioAnuncio = new Audio();
    
    let sistemaActivo = false;
    let intervalo;
    let tiempoRestante = 0;
    let wakeLock = null;

    const btnGrabar = document.getElementById('btnGrabar');
    const estadoGrabacion = document.getElementById('estadoGrabacion');
    const btnSistema = document.getElementById('btnSistema');
    const estadoSistema = document.getElementById('estadoSistema');
    const cuentaRegresivaTxt = document.getElementById('cuentaRegresiva');
    const inputMinutos = document.getElementById('inputMinutos');

    actualizarRelojVisual(inputMinutos.value * 60);

    inputMinutos.addEventListener('input', () => {
        if (!sistemaActivo) {
            let mins = parseInt(inputMinutos.value) || 0;
            actualizarRelojVisual(mins * 60);
        }
    });

    async function toglearGrabacion() {
        if (!mediaRecorder || mediaRecorder.state === "inactive") {
            try {
                const stream = await navigator.mediaDevices.getUserMedia({ audio: true });
                mediaRecorder = new MediaRecorder(stream);
                audioBlobs = [];

                mediaRecorder.ondataavailable = event => { audioBlobs.push(event.data); };

                mediaRecorder.onstop = () => {
                    const audioBlob = new Blob(audioBlobs, { type: 'audio/mp3' });
                    audioUrl = URL.createObjectURL(audioBlob);
                    audioAnuncio.src = audioUrl;
                    
                    estadoGrabacion.textContent = "¡Audio guardado correctamente!";
                    btnSistema.disabled = false;
                };

                mediaRecorder.start();
                btnGrabar.textContent = "🛑 Detener Grabación";
                btnGrabar.className = "btn-grabar grabando";
                estadoGrabacion.textContent = "Grabando desde el micrófono...";
                
                if(sistemaActivo) toglearSistema();
                
            } catch (err) {
                alert("Por favor concede permisos para usar el micrófono.");
                console.error(err);
            }
        } else {
            mediaRecorder.stop();
            mediaRecorder.stream.getTracks().forEach(track => track.stop());
            btnGrabar.textContent = "🎙️ Grabar Nuevo Audio";
            btnGrabar.className = "btn-grabar";
        }
    }

    async function activarMantenerPantalla() {
        try { if ('wakeLock' in navigator) { wakeLock = await navigator.wakeLock.request('screen'); } } catch (err) {}
    }
    function desactivarMantenerPantalla() { if (wakeLock !== null) { wakeLock.release(); wakeLock = null; } }

    function toglearSistema() {
        if (!sistemaActivo) {
            if (!audioUrl) return;
            
            sistemaActivo = true;
            btnSistema.textContent = "🛑 Detener Sistema";
            btnSistema.className = "btn-play stop";
            estadoSistema.textContent = "Activo";
            btnGrabar.disabled = true;
            inputMinutos.disabled = true; 
            
            activarMantenerPantalla();
            reproducirAnuncio(); 
        } else {
            sistemaActivo = false;
            clearInterval(intervalo);
            audioAnuncio.pause();
            audioAnuncio.currentTime = 0;
            btnSistema.textContent = "▶️ Iniciar Sistema";
            btnSistema.className = "btn-play";
            estadoSistema.textContent = "Apagado";
            btnGrabar.disabled = false;
            inputMinutos.disabled = false;
            
            let mins = parseInt(inputMinutos.value) || 30;
            actualizarRelojVisual(mins * 60);
            
            desactivaMantenerPantalla();
        }
    }

    function reproducirAnuncio() {
        estadoSistema.textContent = "Sonando...";
        
        audioAnuncio.play().catch(error => {
            console.log("Error de reproducción: ", error);
        });

        audioAnuncio.onended = function() {
            estadoSistema.textContent = "Esperando";
            reiniciarTemporizador();
        };
    }

    function reiniciarTemporizador() {
        clearInterval(intervalo);
        
        let minutosManuales = parseInt(inputMinutos.value) || 30;
        tiempoRestante = minutosManuales * 60; 
        
        actualizarRelojVisual(tiempoRestante);
        
        intervalo = setInterval(() => {
            tiempoRestante--;
            actualizarRelojVisual(tiempoRestante);
            if (tiempoRestante <= 0) {
                clearInterval(intervalo);
                reproducirAnuncio();
            }
        }, 1000);
    }

    function actualizarRelojVisual(segundosTotales) {
        let minutos = Math.floor(segundosTotales / 60);
        let segundos = segundosTotales % 60;
        minutos = minutos < 10 ? "0" + minutos : minutos;
        segundos = segundos < 10 ? "0" + segundos : segundos;
        cuentaRegresivaTxt.textContent = `${minutos}:${segundos}`;
    }
</script>

</body>
</html>
