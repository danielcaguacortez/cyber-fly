<!DOCTYPE html>
<html lang="es">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>CYBER-FLY: NEON OVERDRIVE 3D</title>
    <!-- Tailwind CSS para la interfaz -->
    <script src="https://cdn.tailwindcss.com"></script>
    <!-- Three.js Library -->
    <script src="https://cdnjs.cloudflare.com/ajax/libs/three.js/r128/three.min.js"></script>
    <!-- Google Font Google Orbitron -->
    <link href="https://fonts.googleapis.com/css2?family=Orbitron:wght@400;700;900&display=swap" rel="stylesheet">
    <style>
        * {
            user-select: none;
            -webkit-user-select: none;
        }
        body {
            margin: 0;
            overflow: hidden;
            background-color: #030308;
            font-family: 'Orbitron', sans-serif;
            color: #fff;
        }
        #canvas-container {
            width: 100vw;
            height: 100vh;
            position: absolute;
            top: 0;
            left: 0;
            z-index: 1;
        }
        /* Neon Glow Effects */
        .neon-text-cyan {
            text-shadow: 0 0 5px #00f3ff, 0 0 10px #00f3ff, 0 0 20px #00f3ff;
        }
        .neon-text-pink {
            text-shadow: 0 0 5px #ff0055, 0 0 10px #ff0055, 0 0 20px #ff0055;
        }
        .neon-border-pink {
            box-shadow: 0 0 10px #ff0055, inset 0 0 10px #ff0055;
            border-color: #ff0055;
        }
        .neon-border-cyan {
            box-shadow: 0 0 10px #00f3ff, inset 0 0 10px #00f3ff;
            border-color: #00f3ff;
        }
        .glass-panel {
            background: rgba(10, 10, 25, 0.75);
            backdrop-filter: blur(12px);
            border: 1px solid rgba(255, 255, 255, 0.1);
        }
    </style>
</head>
<body class="w-full h-full overflow-hidden bg-black text-white">

    <!-- Canvas para renderizar Three.js -->
    <div id="canvas-container"></div>

    <!-- HUD Overlay durante el juego -->
    <div id="hud" class="absolute inset-0 pointer-events-none z-10 hidden flex-col justify-between p-6">
        <!-- Barra Superior: Stats -->
        <div class="flex justify-between items-start">
            <div class="glass-panel p-4 rounded-xl border border-cyan-500/30 flex flex-col gap-1">
                <div class="text-xs text-cyan-400 font-bold tracking-widest">PUNTUACIÓN</div>
                <div id="score-val" class="text-3xl font-black text-white neon-text-cyan">000000</div>
                <div class="text-xs text-pink-400 font-semibold mt-1">MULTIPLIADOR: <span id="multiplier-val">x1</span></div>
            </div>

            <div class="glass-panel p-4 rounded-xl border border-pink-500/30 text-center">
                <div class="text-xs text-pink-400 font-bold tracking-widest">OLEADA</div>
                <div id="wave-val" class="text-4xl font-black text-white neon-text-pink">1</div>
            </div>

            <div class="glass-panel p-4 rounded-xl border border-cyan-500/30 flex flex-col gap-2 min-w-[200px]">
                <div>
                    <div class="flex justify-between text-xs text-cyan-300 font-bold mb-1">
                        <span>ESCUDO</span>
                        <span id="shield-val">100%</span>
                    </div>
                    <div class="w-full bg-gray-900 rounded-full h-3 p-0.5 border border-cyan-500/50">
                        <div id="shield-bar" class="bg-gradient-to-r from-cyan-500 to-blue-500 h-full rounded-full transition-all duration-200" style="width: 100%;"></div>
                    </div>
                </div>
                <div>
                    <div class="flex justify-between text-xs text-pink-300 font-bold mb-1">
                        <span>TURBO OVERDRIVE</span>
                        <span id="boost-val">READY</span>
                    </div>
                    <div class="w-full bg-gray-900 rounded-full h-2 p-0.5 border border-pink-500/50">
                        <div id="boost-bar" class="bg-gradient-to-r from-pink-500 to-yellow-400 h-full rounded-full transition-all duration-100" style="width: 100%;"></div>
                    </div>
                </div>
            </div>
        </div>

        <!-- Indicador de Powerups / Alertas centrales -->
        <div id="alert-banner" class="text-center transition-all duration-300 opacity-0 transform translate-y-4">
            <h2 id="alert-text" class="text-3xl md:text-5xl font-black tracking-widest text-yellow-400 neon-text-pink">¡ALERTA ENEMIGA!</h2>
        </div>

        <!-- Controles Móviles Visibles en Touch -->
        <div class="flex justify-between items-end md:hidden pointer-events-auto">
            <div id="touch-joystick" class="w-32 h-32 rounded-full glass-panel border-2 border-cyan-500/40 relative flex items-center justify-center">
                <div id="joystick-knob" class="w-12 h-12 rounded-full bg-cyan-400/80 shadow-lg shadow-cyan-500/50"></div>
            </div>
            <div class="flex gap-4">
                <button id="btn-fire" class="w-16 h-16 rounded-full bg-pink-600/80 border-2 border-pink-300 text-white font-bold text-xs shadow-lg active:scale-95">FUEGO</button>
                <button id="btn-boost" class="w-16 h-16 rounded-full bg-cyan-600/80 border-2 border-cyan-300 text-white font-bold text-xs shadow-lg active:scale-95">TURBO</button>
            </div>
        </div>
    </div>

    <!-- Menú Principal -->
    <div id="menu-screen" class="absolute inset-0 z-20 flex items-center justify-center p-4 bg-black/80 backdrop-blur-md">
        <div class="max-w-xl w-full glass-panel p-8 rounded-2xl border-2 border-cyan-500/50 text-center flex flex-col items-center gap-6 shadow-2xl">
            <div class="space-y-2">
                <h1 class="text-4xl md:text-6xl font-black italic tracking-wider bg-clip-text text-transparent bg-gradient-to-r from-cyan-400 via-pink-500 to-purple-500 neon-text-cyan">
                    CYBER-FLY
                </h1>
                <p class="text-xs md:text-sm text-cyan-300 tracking-widest uppercase">OVERDRIVE SYNTH COMBAT 3D</p>
            </div>

            <div class="w-full bg-black/40 rounded-xl p-4 border border-white/10 text-xs md:text-sm text-gray-300 text-left space-y-2">
                <div class="text-pink-400 font-bold mb-1 text-center">CONTROLES DE VUELO:</div>
                <div class="flex justify-between"><span>Mover Nave:</span> <span class="text-cyan-300 font-bold">W, A, S, D / Flechas</span></div>
                <div class="flex justify-between"><span>Disparar Lasers:</span> <span class="text-cyan-300 font-bold">ESPACIO / Clic Izquierdo</span></div>
                <div class="flex justify-between"><span>Propulsor Turbo:</span> <span class="text-cyan-300 font-bold">SHIFT Izquierdo</span></div>
                <div class="flex justify-between"><span>Pausa:</span> <span class="text-cyan-300 font-bold">Tecla P</span></div>
            </div>

            <button id="start-btn" class="w-full py-4 rounded-xl bg-gradient-to-r from-cyan-500 via-purple-600 to-pink-500 text-white font-black text-xl tracking-widest hover:opacity-90 transition-all duration-300 shadow-lg shadow-pink-500/30 transform hover:-translate-y-0.5 active:translate-y-0 pointer-events-auto">
                INICIAR MISIÓN
            </button>
        </div>
    </div>

    <!-- Pantalla de Game Over -->
    <div id="gameover-screen" class="absolute inset-0 z-20 flex items-center justify-center p-4 bg-black/90 backdrop-blur-md hidden">
        <div class="max-w-md w-full glass-panel p-8 rounded-2xl border-2 border-pink-500/60 text-center flex flex-col items-center gap-6 shadow-2xl">
            <h2 class="text-4xl font-black text-pink-500 neon-text-pink">SISTEMA CAÍDO</h2>
            
            <div class="space-y-3 w-full">
                <div class="text-gray-400 text-xs tracking-widest">PUNTUACIÓN FINAL</div>
                <div id="final-score" class="text-5xl font-black text-cyan-400 neon-text-cyan">000000</div>
                <div class="text-sm text-gray-300">Oleadas Sobrevividas: <span id="final-wave" class="text-pink-400 font-bold">0</span></div>
            </div>

            <button id="restart-btn" class="w-full py-4 rounded-xl bg-gradient-to-r from-pink-500 to-purple-600 text-white font-black text-lg tracking-widest hover:opacity-90 transition-all shadow-lg shadow-pink-500/40 pointer-events-auto">
                REINICIAR SISTEMA
            </button>
        </div>
    </div>

    <!-- Código del Juego en JS -->
    <script>
        /* --- SINTETIZADOR DE AUDIO (Web Audio API) --- */
        class AudioController {
            constructor() {
                this.ctx = null;
                this.isMuted = false;
                this.musicInterval = null;
            }

            init() {
                if (!this.ctx) {
                    const AudioContext = window.AudioContext || window.webkitAudioContext;
                    this.ctx = new AudioContext();
                    this.startSynthwaveMusic();
                }
            }

            // Reproduce sonidos sintetizados procedurales
            playShoot() {
                if (!this.ctx || this.isMuted) return;
                const osc = this.ctx.createOscillator();
                const gain = this.ctx.createGain();
                osc.type = 'sawtooth';
                osc.frequency.setValueAtTime(800, this.ctx.currentTime);
                osc.frequency.exponentialRampToValueAtTime(100, this.ctx.currentTime + 0.15);
                
                gain.gain.setValueAtTime(0.2, this.ctx.currentTime);
                gain.gain.exponentialRampToValueAtTime(0.01, this.ctx.currentTime + 0.15);

                osc.connect(gain);
                gain.connect(this.ctx.destination);
                osc.start();
                osc.stop(this.ctx.currentTime + 0.15);
            }

            playExplosion() {
                if (!this.ctx || this.isMuted) return;
                // Ruido blanco sintetizado para explosiones
                const bufferSize = this.ctx.sampleRate * 0.4;
                const buffer = this.ctx.createBuffer(1, bufferSize, this.ctx.sampleRate);
                const data = buffer.getChannelData(0);
                for (let i = 0; i < bufferSize; i++) {
                    data[i] = Math.random() * 2 - 1;
                }

                const noise = this.ctx.createBufferSource();
                noise.buffer = buffer;

                const filter = this.ctx.createBiquadFilter();
                filter.type = 'lowpass';
                filter.frequency.setValueAtTime(800, this.ctx.currentTime);
                filter.frequency.exponentialRampToValueAtTime(30, this.ctx.currentTime + 0.4);

                const gain = this.ctx.createGain();
                gain.gain.setValueAtTime(0.5, this.ctx.currentTime);
                gain.gain.exponentialRampToValueAtTime(0.01, this.ctx.currentTime + 0.4);

                noise.connect(filter);
                filter.connect(gain);
                gain.connect(this.ctx.destination);

                noise.start();
                noise.stop(this.ctx.currentTime + 0.4);
            }

            playPowerup() {
                if (!this.ctx || this.isMuted) return;
                const osc = this.ctx.createOscillator();
                const gain = this.ctx.createGain();
                osc.type = 'sine';
                osc.frequency.setValueAtTime(300, this.ctx.currentTime);
                osc.frequency.exponentialRampToValueAtTime(1200, this.ctx.currentTime + 0.25);

                gain.gain.setValueAtTime(0.2, this.ctx.currentTime);
                gain.gain.linearRampToValueAtTime(0.01, this.ctx.currentTime + 0.25);

                osc.connect(gain);
                gain.connect(this.ctx.destination);
                osc.start();
                osc.stop(this.ctx.currentTime + 0.25);
            }

            playHit() {
                if (!this.ctx || this.isMuted) return;
                const osc = this.ctx.createOscillator();
                const gain = this.ctx.createGain();
                osc.type = 'square';
                osc.frequency.setValueAtTime(150, this.ctx.currentTime);
                osc.frequency.exponentialRampToValueAtTime(40, this.ctx.currentTime + 0.1);

                gain.gain.setValueAtTime(0.3, this.ctx.currentTime);
                gain.gain.linearRampToValueAtTime(0.01, this.ctx.currentTime + 0.1);

                osc.connect(gain);
                gain.connect(this.ctx.destination);
                osc.start();
                osc.stop(this.ctx.currentTime + 0.1);
            }

            startSynthwaveMusic() {
                // Línea de bajo retrofuturista programada de forma procedural
                const bassNotes = [55, 55, 110, 55, 82.4, 55, 73.4, 65.4];
                let noteIdx = 0;

                this.musicInterval = setInterval(() => {
                    if (this.isMuted || !this.ctx) return;
                    const freq = bassNotes[noteIdx % bassNotes.length];
                    noteIdx++;

                    const osc = this.ctx.createOscillator();
                    const gain = this.ctx.createGain();
                    const filter = this.ctx.createBiquadFilter();

                    osc.type = 'sawtooth';
                    osc.frequency.setValueAtTime(freq, this.ctx.currentTime);

                    filter.type = 'lowpass';
                    filter.frequency.setValueAtTime(400, this.ctx.currentTime);

                    gain.gain.setValueAtTime(0.12, this.ctx.currentTime);
                    gain.gain.exponentialRampToValueAtTime(0.001, this.ctx.currentTime + 0.2);

                    osc.connect(filter);
                    filter.connect(gain);
                    gain.connect(this.ctx.destination);

                    osc.start();
                    osc.stop(this.ctx.currentTime + 0.2);
                }, 180);
            }
        }

        const audio = new AudioController();

        /* --- MOTOR PRINCIPAL DEL JUEGO THREE.JS --- */
        let scene, camera, renderer;
        let playerShip, playerGroup;
        let gridMesh1, gridMesh2;
        let starsField;

        // Estado del Juego
        let gameState = 'MENU'; // MENU, PLAYING, GAMEOVER
        let score = 0;
        let multiplier = 1;
        let wave = 1;
        let shield = 100;
        let boostAmount = 100;
        let isBoosting = false;
        let lastShootTime = 0;
        let shootDelay = 150; // ms
        let tripleShotActive = false;
        let tripleShotTimer = 0;

        // Arrays de Objetos Activos
        let lasers = [];
        let enemies = [];
        let enemyLasers = [];
        let powerups = [];
        let particles = [];
        let floatingTexts = [];

        // Teclado
        const keys = {
            w: false, a: false, s: false, d: false,
            ArrowUp: false, ArrowDown: false, ArrowLeft: false, ArrowRight: false,
            Space: false, ShiftLeft: false
        };

        // Configuración de Límites de Movimiento
        const BOUNDS = { x: 22, y: 12 };
        const GAME_SPEED = 1.2;

        // Inicialización al cargar ventana
        window.onload = function () {
            initEngine();
            setupEventListeners();
            animate();
        };

        function initEngine() {
            const container = document.getElementById('canvas-container');

            // Escena
            scene = new THREE.Scene();
            scene.fog = new THREE.FogExp2(0x03030d, 0.015);

            // Cámara
            camera = new THREE.PerspectiveCamera(60, window.innerWidth / window.innerHeight, 0.1, 1000);
            camera.position.set(0, 3, 12);

            // Renderizador
            renderer = new THREE.WebGLRenderer({ antialias: true, alpha: false });
            renderer.setSize(window.innerWidth, window.innerHeight);
            renderer.setPixelRatio(Math.min(window.devicePixelRatio, 2));
            renderer.toneMapping = THREE.ACESFilmicToneMapping;
            container.appendChild(renderer.domElement);

            // Iluminación
            const ambientLight = new THREE.AmbientLight(0xffffff, 0.6);
            scene.add(ambientLight);

            const dirLight = new THREE.DirectionalLight(0x00f3ff, 1.2);
            dirLight.position.set(0, 20, 10);
            scene.add(dirLight);

            const pinkPointLight = new THREE.PointLight(0xff0055, 3, 30);
            pinkPointLight.position.set(0, 0, 5);
            scene.add(pinkPointLight);

            // Crear Escenario Synthwave (Grid Infinito + Estrellas)
            createEnvironment();

            // Crear Nave del Jugador
            createPlayerShip();
        }

        /* --- CONSTRUCCIÓN DE ESCENARIO 3D --- */
        function createEnvironment() {
            // Fondo Estelar de Partículas
            const starCount = 1000;
            const starGeo = new THREE.BufferGeometry();
            const starCoords = new Float32Array(starCount * 3);

            for (let i = 0; i < starCount * 3; i += 3) {
                starCoords[i] = (Math.random() - 0.5) * 300;
                starCoords[i + 1] = (Math.random() - 0.5) * 300;
                starCoords[i + 2] = -Math.random() * 200;
            }

            starGeo.setAttribute('position', new THREE.BufferAttribute(starCoords, 3));
            const starMat = new THREE.PointsMaterial({ color: 0x00f3ff, size: 0.8, transparent: true, opacity: 0.8 });
            starsField = new THREE.Points(starGeo, starMat);
            scene.add(starsField);

            // Retícula de Piso Neón (Infinite Grid Effect)
            const gridHelper1 = new THREE.GridHelper(200, 40, 0xff0055, 0x00f3ff);
            gridHelper1.position.y = -10;
            gridHelper1.position.z = -50;
            gridMesh1 = gridHelper1;
            scene.add(gridMesh1);

            const gridHelper2 = new THREE.GridHelper(200, 40, 0xff0055, 0x00f3ff);
            gridHelper2.position.y = -10;
            gridHelper2.position.z = -250;
            gridMesh2 = gridHelper2;
            scene.add(gridMesh2);

            // Sol / Disco Neón de fondo
            const sunGeo = new THREE.CircleGeometry(30, 32);
            const sunMat = new THREE.MeshBasicMaterial({ color: 0xff0055, wireframe: true });
            const sun = new THREE.Mesh(sunGeo, sunMat);
            sun.position.set(0, 10, -180);
            scene.add(sun);
        }

        /* --- CONSTRUCCIÓN DE LA NAVE JUGADOR --- */
        function createPlayerShip() {
            playerGroup = new THREE.Group();

            // Cuerpo Central (Fuselaje Estilizado)
            const bodyGeo = new THREE.ConeGeometry(1, 4, 5);
            bodyGeo.rotateX(Math.PI / 2);
            const bodyMat = new THREE.MeshStandardMaterial({
                color: 0x0a0a1a,
                roughness: 0.2,
                metalness: 0.8,
                emissive: 0x00f3ff,
                emissiveIntensity: 0.2
            });
            const body = new THREE.Mesh(bodyGeo, bodyMat);
            playerGroup.add(body);

            // Alas
            const wingGeo = new THREE.BufferGeometry();
            const vertices = new Float32Array([
                0, 0, 0,
                3.5, -0.2, 1.5,
                0, 0, -2,

                0, 0, 0,
                -3.5, -0.2, 1.5,
                0, 0, -2
            ]);
            wingGeo.setAttribute('position', new THREE.BufferAttribute(vertices, 3));
            wingGeo.computeVertexNormals();
            const wingMat = new THREE.MeshStandardMaterial({ color: 0x111122, side: THREE.DoubleSide, metalness: 0.9 });
            const wings = new THREE.Mesh(wingGeo, wingMat);
            playerGroup.add(wings);

            // Luces y Tubos Neón en Alas
            const edgeMat = new THREE.LineBasicMaterial({ color: 0x00f3ff, linewidth: 2 });
            const edgeGeo = new THREE.BufferGeometry().setFromPoints([
                new THREE.Vector3(0, 0, -2), new THREE.Vector3(3.5, -0.2, 1.5),
                new THREE.Vector3(0, 0, -2), new THREE.Vector3(-3.5, -0.2, 1.5)
            ]);
            const wingEdges = new THREE.LineSegments(edgeGeo, edgeMat);
            playerGroup.add(wingEdges);

            // Propulsor Trasero (Luz Neón)
            const engineGeo = new THREE.CylinderGeometry(0.4, 0.1, 1, 16);
            engineGeo.rotateX(Math.PI / 2);
            const engineMat = new THREE.MeshBasicMaterial({ color: 0xff0055 });
            const engine = new THREE.Mesh(engineGeo, engineMat);
            engine.position.set(0, 0, 1.8);
            playerGroup.add(engine);

            playerGroup.position.set(0, 0, 0);
            scene.add(playerGroup);
        }

        /* --- MANEJO DE EVENTOS Y TECLAS --- */
        function setupEventListeners() {
            window.addEventListener('resize', onWindowResize);

            // Teclado
            window.addEventListener('keydown', (e) => {
                if (e.code === 'KeyP') togglePause();
                if (keys.hasOwnProperty(e.code) || keys.hasOwnProperty(e.key.toLowerCase())) {
                    keys[e.code] = true;
                    keys[e.key.toLowerCase()] = true;
                }
                if (e.code === 'Space') keys.Space = true;
                if (e.code === 'ShiftLeft') keys.ShiftLeft = true;
            });

            window.addEventListener('keyup', (e) => {
                if (keys.hasOwnProperty(e.code) || keys.hasOwnProperty(e.key.toLowerCase())) {
                    keys[e.code] = false;
                    keys[e.key.toLowerCase()] = false;
                }
                if (e.code === 'Space') keys.Space = false;
                if (e.code === 'ShiftLeft') keys.ShiftLeft = false;
            });

            // Ratón para Disparar
            window.addEventListener('mousedown', (e) => {
                if (gameState === 'PLAYING' && e.button === 0) {
                    keys.Space = true;
                }
            });
            window.addEventListener('mouseup', (e) => {
                if (e.button === 0) keys.Space = false;
            });

            // Botones UI
            document.getElementById('start-btn').addEventListener('click', startGame);
            document.getElementById('restart-btn').addEventListener('click', startGame);

            // Soporte Controles Táctiles Básicos
            setupTouchControls();
        }

        function setupTouchControls() {
            const btnFire = document.getElementById('btn-fire');
            const btnBoost = document.getElementById('btn-boost');

            btnFire.addEventListener('touchstart', (e) => { e.preventDefault(); keys.Space = true; });
            btnFire.addEventListener('touchend', (e) => { e.preventDefault(); keys.Space = false; });

            btnBoost.addEventListener('touchstart', (e) => { e.preventDefault(); keys.ShiftLeft = true; });
            btnBoost.addEventListener('touchend', (e) => { e.preventDefault(); keys.ShiftLeft = false; });

            // Virtual Joystick
            const joystick = document.getElementById('touch-joystick');
            const knob = document.getElementById('joystick-knob');
            let joyActive = false;

            joystick.addEventListener('touchstart', (e) => { joyActive = true; });
            window.addEventListener('touchend', () => {
                joyActive = false;
                knob.style.transform = `translate(0px, 0px)`;
                keys.w = keys.s = keys.a = keys.d = false;
            });

            joystick.addEventListener('touchmove', (e) => {
                if (!joyActive) return;
                const rect = joystick.getBoundingClientRect();
                const touch = e.touches[0];
                const x = touch.clientX - (rect.left + rect.width / 2);
                const y = touch.clientY - (rect.top + rect.height / 2);
                
                const dist = Math.min(Math.hypot(x, y), 40);
                const angle = Math.atan2(y, x);
                const knX = Math.cos(angle) * dist;
                const knY = Math.sin(angle) * dist;

                knob.style.transform = `translate(${knX}px, ${knY}px)`;

                keys.d = knX > 10;
                keys.a = knX < -10;
                keys.s = knY > 10;
                keys.w = knY < -10;
            });
        }

        function onWindowResize() {
            camera.aspect = window.innerWidth / window.innerHeight;
            camera.updateProjectionMatrix();
            renderer.setSize(window.innerWidth, window.innerHeight);
        }

        /* --- INICIO Y LÓGICA DEL JUEGO --- */
        function startGame() {
            audio.init();

            // Ocultar menús
            document.getElementById('menu-screen').classList.add('hidden');
            document.getElementById('gameover-screen').classList.add('hidden');
            document.getElementById('hud').classList.remove('hidden');
            document.getElementById('hud').classList.add('flex');

            // Reset de Variables
            score = 0;
            multiplier = 1;
            wave = 1;
            shield = 100;
            boostAmount = 100;
            tripleShotActive = false;

            // Limpiar Entidades Antiguas
            enemies.forEach(e => scene.remove(e.mesh));
            lasers.forEach(l => scene.remove(l.mesh));
            enemyLasers.forEach(l => scene.remove(l.mesh));
            powerups.forEach(p => scene.remove(p.mesh));
            particles.forEach(p => scene.remove(p.mesh));

            enemies = [];
            lasers = [];
            enemyLasers = [];
            powerups = [];
            particles = [];

            playerGroup.position.set(0, 0, 0);
            gameState = 'PLAYING';

            updateHUD();
            showAlert("¡MISIÓN INICIADA!");
        }

        function togglePause() {
            if (gameState === 'PLAYING') gameState = 'PAUSED';
            else if (gameState === 'PAUSED') gameState = 'PLAYING';
        }

        function gameOver() {
            gameState = 'GAMEOVER';
            audio.playExplosion();

            document.getElementById('final-score').innerText = String(score).padStart(6, '0');
            document.getElementById('final-wave').innerText = wave;

            document.getElementById('hud').classList.add('hidden');
            document.getElementById('gameover-screen').classList.remove('hidden');
        }

        /* --- LOOP PRINCIPAL DE RENDER --- */
        function animate() {
            requestAnimationFrame(animate);

            if (gameState === 'PLAYING') {
                updatePlayer();
                updateLasers();
                updateEnemies();
                updatePowerups();
                updateParticles();
                updateEnvironment();
                checkCollisions();
                checkWaveProgress();
            }

            // Mover retícula para dar sensación de velocidad infinita
            const speedFactor = isBoosting ? 2.5 : 1.0;
            gridMesh1.position.z += GAME_SPEED * speedFactor;
            gridMesh2.position.z += GAME_SPEED * speedFactor;

            if (gridMesh1.position.z >= 150) gridMesh1.position.z = -250;
            if (gridMesh2.position.z >= 150) gridMesh2.position.z = -250;

            renderer.render(scene, camera);
        }

        /* --- ACTUALIZACIÓN DEL JUEGO Y MOVIMIENTO --- */
        function updatePlayer() {
            const speed = isBoosting ? 0.45 : 0.28;

            // Movimiento Horizontal/Vertical con teclas
            if ((keys.a || keys.ArrowLeft) && playerGroup.position.x > -BOUNDS.x) {
                playerGroup.position.x -= speed;
                playerGroup.rotation.z = Math.min(playerGroup.rotation.z + 0.08, 0.6);
            } else if ((keys.d || keys.ArrowRight) && playerGroup.position.x < BOUNDS.x) {
                playerGroup.position.x += speed;
                playerGroup.rotation.z = Math.max(playerGroup.rotation.z - 0.08, -0.6);
            } else {
                playerGroup.rotation.z *= 0.88; // Regreso suave al centro
            }

            if ((keys.w || keys.ArrowUp) && playerGroup.position.y < BOUNDS.y) {
                playerGroup.position.y += speed;
                playerGroup.rotation.x = Math.max(playerGroup.rotation.x - 0.05, -0.3);
            } else if ((keys.s || keys.ArrowDown) && playerGroup.position.y > -BOUNDS.y + 2) {
                playerGroup.position.y -= speed;
                playerGroup.rotation.x = Math.min(playerGroup.rotation.x + 0.05, 0.3);
            } else {
                playerGroup.rotation.x *= 0.88;
            }

            // Manejo de Turbo (Boost)
            if (keys.ShiftLeft && boostAmount > 0) {
                isBoosting = true;
                boostAmount = Math.max(0, boostAmount - 0.8);
                camera.fov = THREE.MathUtils.lerp(camera.fov, 72, 0.1); // Efecto FOV de velocidad
                camera.updateProjectionMatrix();
                createEngineParticle();
            } else {
                isBoosting = false;
                boostAmount = Math.min(100, boostAmount + 0.25); // Recarga progresiva
                camera.fov = THREE.MathUtils.lerp(camera.fov, 60, 0.1);
                camera.updateProjectionMatrix();
            }

            // Disparo de Lasers
            if (keys.Space && Date.now() - lastShootTime > shootDelay) {
                shootLaser();
                lastShootTime = Date.now();
            }

            // Temporizador Powerup Triple Disparo
            if (tripleShotActive) {
                tripleShotTimer -= 16;
                if (tripleShotTimer <= 0) tripleShotActive = false;
            }

            updateHUD();
        }

        /* --- SISTEMA DE DISPARO --- */
        function shootLaser() {
            audio.playShoot();

            const createLaserMesh = (offsetX = 0) => {
                const geo = new THREE.CylinderGeometry(0.1, 0.1, 2, 8);
                geo.rotateX(Math.PI / 2);
                const mat = new THREE.MeshBasicMaterial({ color: tripleShotActive ? 0xffff00 : 0x00f3ff });
                const mesh = new THREE.Mesh(geo, mat);
                mesh.position.set(
                    playerGroup.position.x + offsetX,
                    playerGroup.position.y,
                    playerGroup.position.z - 1.5
                );
                scene.add(mesh);
                lasers.push({ mesh, speed: 2.2 });
            };

            if (tripleShotActive) {
                createLaserMesh(0);
                createLaserMesh(-1.2);
                createLaserMesh(1.2);
            } else {
                createLaserMesh(-0.6);
                createLaserMesh(0.6);
            }
        }

        function updateLasers() {
            // Lasers del Jugador
            for (let i = lasers.length - 1; i >= 0; i--) {
                const l = lasers[i];
                l.mesh.position.z -= l.speed;
                if (l.mesh.position.z < -120) {
                    scene.remove(l.mesh);
                    lasers.splice(i, 1);
                }
            }

            // Lasers Enemigos
            for (let i = enemyLasers.length - 1; i >= 0; i--) {
                const el = enemyLasers[i];
                el.mesh.position.z += el.speed;
                if (el.mesh.position.z > 20) {
                    scene.remove(el.mesh);
                    enemyLasers.splice(i, 1);
                }
            }
        }

        /* --- GENERACIÓN Y COMPORTAMIENTO DE ENEMIGOS --- */
        function updateEnemies() {
            // Aparecer enemigos según la oleada
            if (enemies.length < 3 + wave * 2 && Math.random() < 0.03) {
                spawnEnemy();
            }

            for (let i = enemies.length - 1; i >= 0; i--) {
                const enemy = enemies[i];
                enemy.mesh.position.z += enemy.speed;

                // Patrón de movimiento sinusoidal
                if (enemy.type === 'ZIGZAG') {
                    enemy.mesh.position.x += Math.sin(Date.now() * 0.005 + enemy.id) * 0.15;
                }

                // Disparo enemigo ocasional
                if (Math.random() < 0.005 && enemy.mesh.position.z < -10) {
                    spawnEnemyLaser(enemy.mesh.position);
                }

                // Eliminar enemigos fuera de pantalla
                if (enemy.mesh.position.z > 15) {
                    scene.remove(enemy.mesh);
                    enemies.splice(i, 1);
                    multiplier = 1; // Reiniciar multiplicador al dejar pasar enemigos
                }
            }
        }

        function spawnEnemy() {
            const types = ['STANDARD', 'ZIGZAG', 'HEAVY'];
            const type = types[Math.floor(Math.random() * types.length)];

            const group = new THREE.Group();
            let geo, mat, hp = 1, speed = 0.6 + Math.random() * 0.3;

            if (type === 'STANDARD') {
                geo = new THREE.OctahedronGeometry(1.2);
                mat = new THREE.MeshStandardMaterial({ color: 0xff0055, emissive: 0xff0055, emissiveIntensity: 0.5 });
            } else if (type === 'ZIGZAG') {
                geo = new THREE.TetrahedronGeometry(1.4);
                mat = new THREE.MeshStandardMaterial({ color: 0xaa00ff, emissive: 0xaa00ff, emissiveIntensity: 0.6 });
                speed += 0.2;
            } else if (type === 'HEAVY') {
                geo = new THREE.DodecahedronGeometry(2.0);
                mat = new THREE.MeshStandardMaterial({ color: 0xffaa00, emissive: 0xffaa00, emissiveIntensity: 0.4 });
                hp = 3;
                speed *= 0.7;
            }

            const mesh = new THREE.Mesh(geo, mat);
            group.add(mesh);

            // Borde luminoso
            const wireGeo = new THREE.WireframeGeometry(geo);
            const wireMat = new THREE.LineBasicMaterial({ color: 0xffffff });
            const wireframe = new THREE.LineSegments(wireGeo, wireMat);
            group.add(wireframe);

            group.position.set(
                (Math.random() - 0.5) * (BOUNDS.x * 1.8),
                (Math.random() - 0.5) * (BOUNDS.y * 1.5),
                -120 - Math.random() * 40
            );

            scene.add(group);
            enemies.push({ mesh: group, type, hp, speed, id: Math.random() });
        }

        function spawnEnemyLaser(pos) {
            const geo = new THREE.SphereGeometry(0.3, 8, 8);
            const mat = new THREE.MeshBasicMaterial({ color: 0xff0000 });
            const mesh = new THREE.Mesh(geo, mat);
            mesh.position.copy(pos);
            scene.add(mesh);
            enemyLasers.push({ mesh, speed: 0.9 });
        }

        /* --- POWER-UPS --- */
        function spawnPowerup(pos) {
            if (Math.random() > 0.4) return; // 40% probabilidad al destruir enemigo

            const types = ['SHIELD', 'TRIPLE', 'BOOST'];
            const type = types[Math.floor(Math.random() * types.length)];

            const geo = new THREE.IcosahedronGeometry(0.8);
            let color = 0x00f3ff;
            if (type === 'TRIPLE') color = 0xffff00;
            if (type === 'BOOST') color = 0xff00ff;

            const mat = new THREE.MeshBasicMaterial({ color, wireframe: true });
            const mesh = new THREE.Mesh(geo, mat);
            mesh.position.copy(pos);

            scene.add(mesh);
            powerups.push({ mesh, type, speed: 0.4 });
        }

        function updatePowerups() {
            for (let i = powerups.length - 1; i >= 0; i--) {
                const p = powerups[i];
                p.mesh.position.z += p.speed;
                p.mesh.rotation.x += 0.03;
                p.mesh.rotation.y += 0.03;

                if (p.mesh.position.z > 15) {
                    scene.remove(p.mesh);
                    powerups.splice(i, 1);
                }
            }
        }

        /* --- DETECCIÓN DE COLISIONES --- */
        function checkCollisions() {
            // 1. Lasers Jugador vs Enemigos
            for (let i = lasers.length - 1; i >= 0; i--) {
                for (let j = enemies.length - 1; j >= 0; j--) {
                    if (lasers[i] && enemies[j]) {
                        const dist = lasers[i].mesh.position.distanceTo(enemies[j].mesh.position);
                        if (dist < 2.0) {
                            // Impacto exitoso
                            createExplosion(enemies[j].mesh.position, 0xff0055);
                            scene.remove(lasers[i].mesh);
                            lasers.splice(i, 1);

                            enemies[j].hp -= 1;
                            if (enemies[j].hp <= 0) {
                                audio.playExplosion();
                                spawnPowerup(enemies[j].mesh.position);
                                scene.remove(enemies[j].mesh);
                                enemies.splice(j, 1);

                                score += 100 * multiplier;
                                multiplier = Math.min(multiplier + 1, 10);
                            } else {
                                audio.playHit();
                            }
                            break;
                        }
                    }
                }
            }

            // 2. Nave vs Enemigos
            for (let i = enemies.length - 1; i >= 0; i--) {
                const dist = playerGroup.position.distanceTo(enemies[i].mesh.position);
                if (dist < 2.5) {
                    createExplosion(enemies[i].mesh.position, 0xff0055);
                    scene.remove(enemies[i].mesh);
                    enemies.splice(i, 1);
                    takeDamage(30);
                }
            }

            // 3. Nave vs Lasers Enemigos
            for (let i = enemyLasers.length - 1; i >= 0; i--) {
                const dist = playerGroup.position.distanceTo(enemyLasers[i].mesh.position);
                if (dist < 1.8) {
                    scene.remove(enemyLasers[i].mesh);
                    enemyLasers.splice(i, 1);
                    takeDamage(15);
                }
            }

            // 4. Nave vs Powerups
            for (let i = powerups.length - 1; i >= 0; i--) {
                const dist = playerGroup.position.distanceTo(powerups[i].mesh.position);
                if (dist < 2.2) {
                    audio.playPowerup();
                    applyPowerup(powerups[i].type);
                    scene.remove(powerups[i].mesh);
                    powerups.splice(i, 1);
                }
            }
        }

        function takeDamage(amount) {
            audio.playHit();
            shield = Math.max(0, shield - amount);
            multiplier = 1; // Reiniciar combo

            // Flash visual
            renderer.setClearColor(0xff0033, 0.3);
            setTimeout(() => renderer.setClearColor(0x000000, 1), 100);

            if (shield <= 0) {
                createExplosion(playerGroup.position, 0x00f3ff, 40);
                gameOver();
            }
        }

        function applyPowerup(type) {
            if (type === 'SHIELD') {
                shield = Math.min(100, shield + 35);
                showAlert("¡ESCUDOS REPARADOS!");
            } else if (type === 'TRIPLE') {
                tripleShotActive = true;
                tripleShotTimer = 8000; // 8 segundos
                showAlert("¡TRIPLE LÁSER ACTIVO!");
            } else if (type === 'BOOST') {
                boostAmount = 100;
                showAlert("¡TURBO RECARGADO!");
            }
        }

        /* --- PROGRESIÓN DE OLEADAS --- */
        function checkWaveProgress() {
            if (score >= wave * 1500) {
                wave++;
                showAlert(`¡OLEADA ${wave} INICIADA!`);
            }
        }

        /* --- SISTEMA DE PARTÍCULAS Y EFECTOS --- */
        function createExplosion(pos, colorHex, count = 20) {
            for (let i = 0; i < count; i++) {
                const geo = new THREE.BoxGeometry(0.2, 0.2, 0.2);
                const mat = new THREE.MeshBasicMaterial({ color: colorHex });
                const p = new THREE.Mesh(geo, mat);
                p.position.copy(pos);

                const velocity = new THREE.Vector3(
                    (Math.random() - 0.5) * 1.2,
                    (Math.random() - 0.5) * 1.2,
                    (Math.random() - 0.5) * 1.2
                );

                scene.add(p);
                particles.push({ mesh: p, vel: velocity, life: 1.0 });
            }
        }

        function createEngineParticle() {
            const geo = new THREE.SphereGeometry(0.15, 4, 4);
            const mat = new THREE.MeshBasicMaterial({ color: 0x00f3ff, transparent: true, opacity: 0.8 });
            const p = new THREE.Mesh(geo, mat);
            p.position.set(
                playerGroup.position.x + (Math.random() - 0.5) * 0.4,
                playerGroup.position.y,
                playerGroup.position.z + 2.0
            );
            scene.add(p);
            particles.push({ mesh: p, vel: new THREE.Vector3(0, 0, 0.8), life: 0.5 });
        }

        function updateParticles() {
            for (let i = particles.length - 1; i >= 0; i--) {
                const p = particles[i];
                p.mesh.position.add(p.vel);
                p.life -= 0.04;
                p.mesh.scale.multiplyScalar(0.95);

                if (p.life <= 0) {
                    scene.remove(p.mesh);
                    particles.splice(i, 1);
                }
            }
        }

        function updateEnvironment() {
            if (starsField) {
                starsField.rotation.z += 0.0005;
            }
        }

        /* --- ACTUALIZACIÓN DE INTERFAZ (HUD) --- */
        function updateHUD() {
            document.getElementById('score-val').innerText = String(score).padStart(6, '0');
            document.getElementById('multiplier-val').innerText = `x${multiplier}`;
            document.getElementById('wave-val').innerText = wave;
            document.getElementById('shield-val').innerText = `${Math.round(shield)}%`;
            document.getElementById('shield-bar').style.width = `${shield}%`;
            document.getElementById('boost-bar').style.width = `${boostAmount}%`;
        }

        function showAlert(text) {
            const banner = document.getElementById('alert-banner');
            const alertText = document.getElementById('alert-text');
            alertText.innerText = text;
            banner.classList.remove('opacity-0', 'translate-y-4');
            banner.classList.add('opacity-100', 'translate-y-0');

            setTimeout(() => {
                banner.classList.remove('opacity-100', 'translate-y-0');
                banner.classList.add('opacity-0', 'translate-y-4');
            }, 2000);
        }
    </script>
</body>
</html>