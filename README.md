<!DOCTYPE html>
<html lang="es">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Álvaro Rivera - Estudiante TI</title>
    <style>
        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
        }

        body {
            font-family: 'Arial', sans-serif;
            background: linear-gradient(135deg, #0a0a0a 0%, #1a1a2e 50%, #16213e 100%);
            color: #ffffff;
            min-height: 100vh;
            overflow-x: hidden;
        }

        .container {
            max-width: 1200px;
            margin: 0 auto;
            padding: 20px;
        }

        .header {
            text-align: center;
            margin-bottom: 40px;
            background: rgba(255, 255, 255, 0.05);
            backdrop-filter: blur(10px);
            border: 1px solid rgba(59, 130, 246, 0.3);
            border-radius: 20px;
            padding: 40px;
            box-shadow: 0 20px 40px rgba(0, 0, 0, 0.3);
            position: relative;
            overflow: hidden;
        }

        .header::before {
            content: '';
            position: absolute;
            top: -50%;
            left: -50%;
            width: 200%;
            height: 200%;
            background: conic-gradient(from 0deg, transparent, rgba(59, 130, 246, 0.1), transparent);
            animation: rotate 10s linear infinite;
        }

        .header-content {
            position: relative;
            z-index: 1;
        }

        @keyframes rotate {
            0% { transform: rotate(0deg); }
            100% { transform: rotate(360deg); }
        }

        .profile-img {
            width: 150px;
            height: 150px;
            border-radius: 50%;
            background: linear-gradient(45deg, #3b82f6, #1e40af);
            margin: 0 auto 20px;
            display: flex;
            align-items: center;
            justify-content: center;
            font-size: 60px;
            border: 4px solid rgba(59, 130, 246, 0.5);
            box-shadow: 0 10px 30px rgba(59, 130, 246, 0.3);
        }

        .main-title {
            font-size: 3em;
            font-weight: bold;
            margin-bottom: 10px;
            background: linear-gradient(45deg, #3b82f6, #60a5fa);
            -webkit-background-clip: text;
            -webkit-text-fill-color: transparent;
            background-clip: text;
        }

        .subtitle {
            font-size: 1.2em;
            color: #94a3b8;
            margin-bottom: 20px;
        }

        .age-badge {
            display: inline-block;
            background: linear-gradient(45deg, #3b82f6, #1e40af);
            padding: 8px 20px;
            border-radius: 25px;
            font-weight: bold;
            font-size: 1.1em;
        }

        .grid {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(350px, 1fr));
            gap: 30px;
            margin-top: 40px;
        }

        .card {
            background: rgba(255, 255, 255, 0.05);
            backdrop-filter: blur(10px);
            border: 1px solid rgba(59, 130, 246, 0.3);
            border-radius: 20px;
            padding: 30px;
            box-shadow: 0 15px 35px rgba(0, 0, 0, 0.2);
            transition: all 0.3s ease;
            position: relative;
            overflow: hidden;
        }

        .card::before {
            content: '';
            position: absolute;
            top: 0;
            left: -100%;
            width: 100%;
            height: 100%;
            background: linear-gradient(90deg, transparent, rgba(59, 130, 246, 0.1), transparent);
            transition: left 0.5s ease;
        }

        .card:hover::before {
            left: 100%;
        }

        .card:hover {
            transform: translateY(-10px);
            border-color: rgba(59, 130, 246, 0.6);
            box-shadow: 0 25px 50px rgba(59, 130, 246, 0.2);
        }

        .card-icon {
            font-size: 2.5em;
            margin-bottom: 20px;
            color: #3b82f6;
        }

        .card-title {
            font-size: 1.5em;
            font-weight: bold;
            margin-bottom: 15px;
            color: #60a5fa;
        }

        .card-content {
            line-height: 1.6;
            color: #cbd5e1;
        }

        .skills-list {
            display: flex;
            flex-wrap: wrap;
            gap: 10px;
            margin-top: 15px;
        }

        .skill-tag {
            background: linear-gradient(45deg, #1e40af, #3730a3);
            padding: 8px 16px;
            border-radius: 20px;
            font-size: 0.9em;
            border: 1px solid rgba(59, 130, 246, 0.3);
            transition: all 0.3s ease;
        }

        .skill-tag:hover {
            transform: scale(1.05);
            box-shadow: 0 5px 15px rgba(59, 130, 246, 0.3);
        }

        .contact-links {
            display: flex;
            justify-content: center;
            gap: 20px;
            margin-top: 30px;
        }

        .contact-btn {
            background: linear-gradient(45deg, #3b82f6, #1e40af);
            color: white;
            text-decoration: none;
            padding: 15px 30px;
            border-radius: 30px;
            font-weight: bold;
            transition: all 0.3s ease;
            border: 2px solid transparent;
        }

        .contact-btn:hover {
            transform: translateY(-3px);
            box-shadow: 0 10px 25px rgba(59, 130, 246, 0.4);
            border-color: rgba(59, 130, 246, 0.5);
        }

        .floating-elements {
            position: fixed;
            top: 0;
            left: 0;
            width: 100%;
            height: 100%;
            pointer-events: none;
            z-index: -1;
        }

        .floating-circle {
            position: absolute;
            border-radius: 50%;
            background: rgba(59, 130, 246, 0.1);
            animation: float 6s ease-in-out infinite;
        }

        .floating-circle:nth-child(1) {
            width: 80px;
            height: 80px;
            top: 20%;
            left: 10%;
            animation-delay: 0s;
        }

        .floating-circle:nth-child(2) {
            width: 120px;
            height: 120px;
            top: 60%;
            right: 10%;
            animation-delay: 2s;
        }

        .floating-circle:nth-child(3) {
            width: 60px;
            height: 60px;
            bottom: 20%;
            left: 20%;
            animation-delay: 4s;
        }

        @keyframes float {
            0%, 100% { transform: translateY(0px) rotate(0deg); }
            50% { transform: translateY(-20px) rotate(180deg); }
        }

        @media (max-width: 768px) {
            .grid {
                grid-template-columns: 1fr;
            }
            
            .main-title {
                font-size: 2em;
            }
            
            .contact-links {
                flex-direction: column;
                align-items: center;
            }
        }
    </style>
</head>
<body>
    <div class="floating-elements">
        <div class="floating-circle"></div>
        <div class="floating-circle"></div>
        <div class="floating-circle"></div>
    </div>

    <div class="container">
        <div class="header">
            <div class="header-content">
                <div class="profile-img">👨‍💻</div>
                <h1 class="main-title">Álvaro Nicolás Rivera Tarque</h1>
                <p class="subtitle">Estudiante de Ingeniería en Tecnología de Información y Sistemas</p>
                <div class="age-badge">19 años</div>
            </div>
        </div>

        <div class="grid">
            <div class="card">
                <div class="card-icon">🎓</div>
                <h3 class="card-title">Educación</h3>
                <div class="card-content">
                    <strong>Universidad ESAN</strong><br>
                    Ingeniería en Tecnología de Información y Sistemas<br>
                    Una de las universidades más prestigiosas del Perú, reconocida por su excelencia académica y enfoque en la innovación tecnológica.
                </div>
            </div>

            <div class="card">
                <div class="card-icon">💡</div>
                <h3 class="card-title">Sobre Mí</h3>
                <div class="card-content">
                    Apasionado por la tecnología y la innovación. Me especializo en el desarrollo de soluciones digitales que impacten positivamente en la sociedad. Siempre en búsqueda de nuevos retos que me permitan crecer profesionalmente.
                </div>
            </div>

            <div class="card">
                <div class="card-icon">🚀</div>
                <h3 class="card-title">Áreas de Interés</h3>
                <div class="card-content">
                    <div class="skills-list">
                        <span class="skill-tag">Desarrollo Web</span>
                        <span class="skill-tag">Inteligencia Artificial</span>
                        <span class="skill-tag">Ciberseguridad</span>
                        <span class="skill-tag">Base de Datos</span>
                        <span class="skill-tag">Cloud Computing</span>
                        <span class="skill-tag">DevOps</span>
                    </div>
                </div>
            </div>

            <div class="card">
                <div class="card-icon">🎯</div>
                <h3 class="card-title">Objetivos</h3>
                <div class="card-content">
                    Mi meta es convertirme en un profesional integral en tecnología, capaz de liderar proyectos innovadores y contribuir al desarrollo tecnológico del país. Busco especializarme en áreas emergentes como IA y blockchain.
                </div>
            </div>

            <div class="card">
                <div class="card-icon">⚡</div>
                <h3 class="card-title">Habilidades Técnicas</h3>
                <div class="card-content">
                    <div class="skills-list">
                        <span class="skill-tag">Python</span>
                        <span class="skill-tag">JavaScript</span>
                        <span class="skill-tag">HTML/CSS</span>
                        <span class="skill-tag">SQL</span>
                        <span class="skill-tag">Git</span>
                        <span class="skill-tag">Linux</span>
                    </div>
                </div>
            </div>

            <div class="card">
                <div class="card-icon">🌟</div>
                <h3 class="card-title">Valores</h3>
                <div class="card-content">
                    Creo firmemente en la importancia de la innovación responsable, el aprendizaje continuo y el trabajo en equipo. La tecnología debe ser una herramienta para mejorar la calidad de vida de las personas.
                </div>
            </div>
        </div>

        <div class="contact-links">
            <a href="mailto:alvaro.rivera@esan.edu.pe" class="contact-btn">📧 Contacto</a>
            <a href="#" class="contact-btn">💼 LinkedIn</a>
            <a href="#" class="contact-btn">🔗 Portfolio</a>
        </div>
    </div>

    <script>
        // Efecto de partículas interactivas
        document.addEventListener('mousemove', (e) => {
            const cards = document.querySelectorAll('.card');
            cards.forEach(card => {
                const rect = card.getBoundingClientRect();
                const x = e.clientX - rect.left;
                const y = e.clientY - rect.top;
                
                if (x >= 0 && x <= rect.width && y >= 0 && y <= rect.height) {
                    const centerX = rect.width / 2;
                    const centerY = rect.height / 2;
                    const rotateX = (y - centerY) / 10;
                    const rotateY = (centerX - x) / 10;
                    
                    card.style.transform = `perspective(1000px) rotateX(${rotateX}deg) rotateY(${rotateY}deg) translateZ(10px)`;
                } else {
                    card.style.transform = '';
                }
            });
        });

        // Animación de entrada para las tarjetas
        const observer = new IntersectionObserver((entries) => {
            entries.forEach(entry => {
                if (entry.isIntersecting) {
                    entry.target.style.opacity = '1';
                    entry.target.style.transform = 'translateY(0)';
                }
            });
        });

        document.querySelectorAll('.card').forEach(card => {
            card.style.opacity = '0';
            card.style.transform = 'translateY(50px)';
            card.style.transition = 'all 0.6s ease';
            observer.observe(card);
        });
    </script>
</body>
</html>
