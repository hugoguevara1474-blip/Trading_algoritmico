<!DOCTYPE html>
<html lang="es">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Alpha Centinela - Portal de Acceso</title>
    <link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.4.0/css/all.min.css">
    <style>
        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
            font-family: 'Segoe UI', Tahoma, Geneva, Verdana, sans-serif;
        }
        
        body {
            background: linear-gradient(135deg, #0f0c29, #302b63, #24243e);
            color: #fff;
            min-height: 100vh;
            display: flex;
            flex-direction: column;
            justify-content: center;
            align-items: center;
            padding: 20px;
            text-align: center;
            position: relative;
            overflow-x: hidden;
        }
        
        /* Estrellas de fondo */
        .stars {
            position: absolute;
            top: 0;
            left: 0;
            width: 100%;
            height: 100%;
            pointer-events: none;
            z-index: -1;
        }
        
        .star {
            position: absolute;
            background-color: white;
            border-radius: 50%;
            animation: twinkle 5s infinite;
        }
        
        @keyframes twinkle {
            0%, 100% { opacity: 0.3; }
            50% { opacity: 1; }
        }
        
        .container {
            max-width: 800px;
            width: 100%;
            padding: 20px;
        }
        
        .logo-container {
            margin-bottom: 30px;
        }
        
        .logo {
            font-size: 3.5rem;
            color: #00d4ff;
            margin-bottom: 10px;
            text-shadow: 0 0 10px rgba(0, 212, 255, 0.7);
        }
        
        .logo-text {
            font-size: 2.8rem;
            font-weight: 800;
            background: linear-gradient(90deg, #00d4ff, #0088ff);
            -webkit-background-clip: text;
            background-clip: text;
            color: transparent;
            letter-spacing: 1px;
        }
        
        .subtitle {
            font-size: 1.2rem;
            margin-bottom: 40px;
            color: #b0b0ff;
            max-width: 600px;
            margin-left: auto;
            margin-right: auto;
            line-height: 1.5;
        }
        
        .link-card {
            background: rgba(16, 18, 36, 0.85);
            border-radius: 20px;
            padding: 30px;
            margin: 30px 0;
            box-shadow: 0 10px 30px rgba(0, 0, 0, 0.5);
            border: 1px solid rgba(0, 212, 255, 0.3);
            backdrop-filter: blur(10px);
            transition: transform 0.3s ease, box-shadow 0.3s ease;
            position: relative;
            overflow: hidden;
        }
        
        .link-card:hover {
            transform: translateY(-5px);
            box-shadow: 0 15px 40px rgba(0, 132, 255, 0.4);
            border-color: rgba(0, 212, 255, 0.6);
        }
        
        .link-card::before {
            content: '';
            position: absolute;
            top: 0;
            left: -100%;
            width: 100%;
            height: 100%;
            background: linear-gradient(90deg, transparent, rgba(0, 212, 255, 0.1), transparent);
            transition: left 0.7s;
        }
        
        .link-card:hover::before {
            left: 100%;
        }
        
        .card-title {
            font-size: 1.8rem;
            margin-bottom: 15px;
            color: #00d4ff;
        }
        
        .card-description {
            font-size: 1.1rem;
            line-height: 1.6;
            margin-bottom: 25px;
            color: #d0d0ff;
        }
        
        .link-button {
            display: inline-flex;
            align-items: center;
            justify-content: center;
            gap: 12px;
            background: linear-gradient(90deg, #0066ff, #00ccff);
            color: white;
            text-decoration: none;
            padding: 16px 35px;
            border-radius: 50px;
            font-size: 1.3rem;
            font-weight: 600;
            letter-spacing: 0.5px;
            transition: all 0.3s ease;
            box-shadow: 0 5px 15px rgba(0, 102, 255, 0.4);
            position: relative;
            overflow: hidden;
            z-index: 1;
        }
        
        .link-button:hover {
            transform: scale(1.05);
            box-shadow: 0 8px 20px rgba(0, 102, 255, 0.6);
            letter-spacing: 1px;
        }
        
        .link-button::before {
            content: '';
            position: absolute;
            top: 0;
            left: -100%;
            width: 100%;
            height: 100%;
            background: linear-gradient(90deg, #00ccff, #0066ff);
            transition: left 0.5s;
            z-index: -1;
        }
        
        .link-button:hover::before {
            left: 0;
        }
        
        .button-icon {
            font-size: 1.5rem;
        }
        
        .features {
            display: flex;
            flex-wrap: wrap;
            justify-content: center;
            gap: 25px;
            margin-top: 50px;
        }
        
        .feature {
            flex: 1;
            min-width: 200px;
            max-width: 250px;
            background: rgba(255, 255, 255, 0.05);
            border-radius: 15px;
            padding: 20px;
            border: 1px solid rgba(0, 212, 255, 0.1);
            transition: transform 0.3s ease;
        }
        
        .feature:hover {
            transform: translateY(-5px);
            border-color: rgba(0, 212, 255, 0.3);
        }
        
        .feature-icon {
            font-size: 2.5rem;
            color: #00d4ff;
            margin-bottom: 15px;
        }
        
        .feature-title {
            font-size: 1.3rem;
            margin-bottom: 10px;
            color: #ffffff;
        }
        
        .feature-text {
            color: #b0b0ff;
            font-size: 0.95rem;
            line-height: 1.5;
        }
        
        .url-display {
            margin-top: 20px;
            font-size: 0.9rem;
            color: #8888cc;
            word-break: break-all;
        }
        
        footer {
            margin-top: 50px;
            color: #8888cc;
            font-size: 0.9rem;
            padding: 20px;
            border-top: 1px solid rgba(255, 255, 255, 0.1);
            width: 100%;
        }
        
        @media (max-width: 768px) {
            .logo-text {
                font-size: 2.2rem;
            }
            
            .subtitle {
                font-size: 1rem;
            }
            
            .link-button {
                padding: 14px 25px;
                font-size: 1.1rem;
            }
            
            .feature {
                min-width: 100%;
            }
        }
    </style>
</head>
<body>
    <div class="stars" id="stars-container"></div>
    
    <div class="container">
        <div class="logo-container">
            <div class="logo"><i class="fas fa-satellite"></i></div>
            <h1 class="logo-text">ALPHA CENTINELA</h1>
            <p class="subtitle">Explora el portal oficial de Alpha Centinela. Accede a contenido exclusivo, herramientas interactivas y la última información sobre vigilancia estelar.</p>
        </div>
        
        <div class="link-card">
            <h2 class="card-title">Portal de Acceso Principal</h2>
            <p class="card-description">Haz clic en el botón a continuación para acceder al sitio oficial de Alpha Centinela. Descubre contenido exclusivo, herramientas interactivas y las últimas actualizaciones sobre vigilancia estelar y tecnología avanzada.</p>
            
            <a href="https://hugoguevara1474-blip.github.io/alfha_centinel/" class="link-button" target="_blank" id="main-link">
                <i class="fas fa-rocket button-icon"></i>
                <span>Ingresar al Portal</span>
            </a>
            
            <div class="url-display">
                URL: https://hugoguevara1474-blip.github.io/alfha_centinel/
            </div>
        </div>
        
        <div class="features">
            <div class="feature">
                <div class="feature-icon"><i class="fas fa-globe-americas"></i></div>
                <h3 class="feature-title">Cobertura Global</h3>
                <p class="feature-text">Monitoreo en tiempo real de actividades estelares y fenómenos cósmicos desde cualquier ubicación.</p>
            </div>
            
            <div class="feature">
                <div class="feature-icon"><i class="fas fa-chart-line"></i></div>
                <h3 class="feature-title">Análisis Avanzado</h3>
                <p class="feature-text">Datos procesados con algoritmos de última generación para predicciones precisas.</p>
            </div>
            
            <div class="feature">
                <div class="feature-icon"><i class="fas fa-user-astronaut"></i></div>
                <h3 class="feature-title">Interfaz Intuitiva</h3>
                <p class="feature-text">Diseñada para una experiencia de usuario óptima tanto para expertos como para principiantes.</p>
            </div>
        </div>
    </div>
    
    <footer>
        <p>Alpha Centinela &copy; 2023 - Todos los derechos reservados</p>
        <p>Sistema de Vigilancia Estelar Avanzada</p>
    </footer>
    
    <script>
        // Crear estrellas de fondo
        function createStars() {
            const starsContainer = document.getElementById('stars-container');
            const starCount = 150;
            
            for (let i = 0; i < starCount; i++) {
                const star = document.createElement('div');
                star.classList.add('star');
                
                // Tamaño aleatorio
                const size = Math.random() * 3 + 1;
                star.style.width = `${size}px`;
                star.style.height = `${size}px`;
                
                // Posición aleatoria
                star.style.left = `${Math.random() * 100}%`;
                star.style.top = `${Math.random() * 100}%`;
                
                // Retraso de animación aleatorio
                star.style.animationDelay = `${Math.random() * 5}s`;
                
                starsContainer.appendChild(star);
            }
        }
        
        // Efecto de escritura para el título
        function typeWriterEffect() {
            const title = document.querySelector('.logo-text');
            const originalText = title.textContent;
            title.textContent = '';
            
            let i = 0;
            const typeWriter = () => {
                if (i < originalText.length) {
                    title.textContent += originalText.charAt(i);
                    i++;
                    setTimeout(typeWriter, 80);
                }
            };
            
            // Iniciar después de un breve retraso
            setTimeout(typeWriter, 500);
        }
        
        // Contador de clics (simulación)
        let clickCount = Math.floor(Math.random() * 100) + 50;
        
        function updateClickCount() {
            clickCount++;
            // En una implementación real, aquí enviarías los datos a un servidor
            console.log(`Clic registrado. Total: ${clickCount}`);
            
            // Animación de confeti al hacer clic
            createConfetti();
        }
        
        // Efecto de confeti al hacer clic
        function createConfetti() {
            const confettiCount = 30;
            const colors = ['#00d4ff', '#0066ff', '#ffffff', '#00ffaa'];
            
            for (let i = 0; i < confettiCount; i++) {
                const confetti = document.createElement('div');
                confetti.style.position = 'fixed';
                confetti.style.width = '10px';
                confetti.style.height = '10px';
                confetti.style.backgroundColor = colors[Math.floor(Math.random() * colors.length)];
                confetti.style.borderRadius = '50%';
                confetti.style.left = `${Math.random() * 100}vw`;
                confetti.style.top = '-20px';
                confetti.style.zIndex = '9999';
                confetti.style.pointerEvents = 'none';
                
                document.body.appendChild(confetti);
                
                // Animación
                const animation = confetti.animate([
                    { transform: 'translateY(0) rotate(0deg)', opacity: 1 },
                    { transform: `translateY(${window.innerHeight + 20}px) rotate(${Math.random() * 360}deg)`, opacity: 0 }
                ], {
                    duration: 1000 + Math.random() * 2000,
                    easing: 'cubic-bezier(0.215, 0.610, 0.355, 1)'
                });
                
                animation.onfinish = () => {
                    document.body.removeChild(confetti);
                };
            }
        }
        
        // Inicialización
        document.addEventListener('DOMContentLoaded', function() {
            createStars();
            typeWriterEffect();
            
            // Agregar evento al botón principal
            const mainButton = document.getElementById('main-link');
            mainButton.addEventListener('click', updateClickCount);
            
            // Agregar efecto de sonido (simulado) al pasar el cursor sobre el botón
            mainButton.addEventListener('mouseenter', function() {
                // En una implementación real, aquí podrías reproducir un sonido sutil
                console.log('Sonido de hover reproducido (simulado)');
            });
        });
    </script>
</body>
</html>
