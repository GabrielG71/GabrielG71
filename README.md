<!DOCTYPE html>
<html lang="pt-BR">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Dev Full Stack - GitHub Profile</title>
    <style>
        @import url('https://fonts.googleapis.com/css2?family=Fira+Code:wght@300;400;500;600;700&family=Inter:wght@300;400;500;600;700;800;900&display=swap');
        
        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
        }

        body {
            font-family: 'Inter', sans-serif;
            background: linear-gradient(135deg, #667eea 0%, #764ba2 100%);
            color: #fff;
            line-height: 1.6;
            overflow-x: hidden;
        }

        .container {
            max-width: 1200px;
            margin: 0 auto;
            padding: 2rem;
        }

        /* Header Animation */
        @keyframes fadeInUp {
            from {
                opacity: 0;
                transform: translateY(30px);
            }
            to {
                opacity: 1;
                transform: translateY(0);
            }
        }

        @keyframes float {
            0%, 100% { transform: translateY(0px); }
            50% { transform: translateY(-10px); }
        }

        @keyframes glow {
            0%, 100% { box-shadow: 0 0 20px rgba(102, 126, 234, 0.5); }
            50% { box-shadow: 0 0 30px rgba(102, 126, 234, 0.8), 0 0 40px rgba(118, 75, 162, 0.6); }
        }

        .header {
            text-align: center;
            padding: 4rem 0;
            animation: fadeInUp 1s ease-out;
        }

        .profile-img {
            width: 150px;
            height: 150px;
            border-radius: 50%;
            border: 4px solid rgba(255, 255, 255, 0.3);
            margin-bottom: 2rem;
            animation: float 3s ease-in-out infinite, glow 2s ease-in-out infinite alternate;
            background: linear-gradient(45deg, #667eea, #764ba2);
            display: flex;
            align-items: center;
            justify-content: center;
            font-size: 4rem;
            margin-left: auto;
            margin-right: auto;
        }

        .name {
            font-size: 3.5rem;
            font-weight: 900;
            margin-bottom: 1rem;
            background: linear-gradient(45deg, #fff, #f0f8ff);
            -webkit-background-clip: text;
            -webkit-text-fill-color: transparent;
            background-clip: text;
        }

        .title {
            font-size: 1.5rem;
            font-weight: 300;
            margin-bottom: 2rem;
            opacity: 0.9;
        }

        .typing-animation {
            font-family: 'Fira Code', monospace;
            font-size: 1.2rem;
            color: #00ff88;
            margin-bottom: 2rem;
        }

        .typing-animation::after {
            content: '|';
            animation: blink 1s infinite;
        }

        @keyframes blink {
            0%, 50% { opacity: 1; }
            51%, 100% { opacity: 0; }
        }

        /* Stats Section */
        .stats-section {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(300px, 1fr));
            gap: 2rem;
            margin: 4rem 0;
        }

        .stat-card {
            background: rgba(255, 255, 255, 0.1);
            backdrop-filter: blur(10px);
            border-radius: 20px;
            padding: 2rem;
            text-align: center;
            transition: all 0.3s ease;
            border: 1px solid rgba(255, 255, 255, 0.2);
        }

        .stat-card:hover {
            transform: translateY(-10px);
            box-shadow: 0 20px 40px rgba(0, 0, 0, 0.3);
            background: rgba(255, 255, 255, 0.15);
        }

        .stat-number {
            font-size: 3rem;
            font-weight: 800;
            color: #00ff88;
            margin-bottom: 0.5rem;
        }

        .stat-label {
            font-size: 1.1rem;
            opacity: 0.8;
        }

        /* Tech Stack */
        .tech-section {
            margin: 4rem 0;
        }

        .section-title {
            font-size: 2.5rem;
            font-weight: 700;
            text-align: center;
            margin-bottom: 3rem;
            position: relative;
        }

        .section-title::after {
            content: '';
            position: absolute;
            bottom: -10px;
            left: 50%;
            transform: translateX(-50%);
            width: 100px;
            height: 4px;
            background: linear-gradient(45deg, #00ff88, #00d4ff);
            border-radius: 2px;
        }

        .tech-grid {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(120px, 1fr));
            gap: 1.5rem;
            margin-top: 2rem;
        }

        .tech-item {
            background: rgba(255, 255, 255, 0.1);
            backdrop-filter: blur(10px);
            border-radius: 15px;
            padding: 1.5rem 1rem;
            text-align: center;
            transition: all 0.3s ease;
            border: 1px solid rgba(255, 255, 255, 0.2);
            position: relative;
            overflow: hidden;
        }

        .tech-item::before {
            content: '';
            position: absolute;
            top: 0;
            left: -100%;
            width: 100%;
            height: 100%;
            background: linear-gradient(90deg, transparent, rgba(255, 255, 255, 0.2), transparent);
            transition: left 0.5s;
        }

        .tech-item:hover::before {
            left: 100%;
        }

        .tech-item:hover {
            transform: translateY(-5px) scale(1.05);
            box-shadow: 0 15px 30px rgba(0, 0, 0, 0.3);
        }

        .tech-icon {
            font-size: 2.5rem;
            margin-bottom: 1rem;
            display: block;
        }

        .tech-name {
            font-size: 0.9rem;
            font-weight: 500;
        }

        /* About Section */
        .about-section {
            background: rgba(255, 255, 255, 0.1);
            backdrop-filter: blur(10px);
            border-radius: 20px;
            padding: 3rem;
            margin: 4rem 0;
            border: 1px solid rgba(255, 255, 255, 0.2);
        }

        .about-text {
            font-size: 1.1rem;
            line-height: 1.8;
            text-align: center;
            opacity: 0.9;
        }

        /* GitHub Stats */
        .github-stats {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(400px, 1fr));
            gap: 2rem;
            margin: 4rem 0;
        }

        .stat-img {
            border-radius: 15px;
            transition: all 0.3s ease;
            border: 2px solid rgba(255, 255, 255, 0.2);
        }

        .stat-img:hover {
            transform: scale(1.05);
            box-shadow: 0 15px 30px rgba(0, 0, 0, 0.3);
        }

        /* Connect Section */
        .connect-section {
            text-align: center;
            margin: 4rem 0;
        }

        .social-links {
            display: flex;
            justify-content: center;
            gap: 2rem;
            margin-top: 2rem;
        }

        .social-link {
            display: inline-block;
            padding: 1rem 2rem;
            background: rgba(255, 255, 255, 0.1);
            backdrop-filter: blur(10px);
            border-radius: 50px;
            text-decoration: none;
            color: #fff;
            font-weight: 500;
            transition: all 0.3s ease;
            border: 1px solid rgba(255, 255, 255, 0.2);
        }

        .social-link:hover {
            background: rgba(255, 255, 255, 0.2);
            transform: translateY(-3px);
            box-shadow: 0 10px 20px rgba(0, 0, 0, 0.3);
        }

        /* Footer */
        .footer {
            text-align: center;
            padding: 2rem 0;
            border-top: 1px solid rgba(255, 255, 255, 0.2);
            margin-top: 4rem;
        }

        .snake-animation {
            margin: 2rem 0;
            text-align: center;
        }

        /* Responsive */
        @media (max-width: 768px) {
            .name {
                font-size: 2.5rem;
            }
            
            .tech-grid {
                grid-template-columns: repeat(auto-fit, minmax(100px, 1fr));
            }
            
            .social-links {
                flex-direction: column;
                align-items: center;
            }
            
            .github-stats {
                grid-template-columns: 1fr;
            }
        }

        /* Additional Animations */
        .fade-in {
            animation: fadeInUp 1s ease-out;
        }

        .fade-in-delay-1 { animation-delay: 0.2s; }
        .fade-in-delay-2 { animation-delay: 0.4s; }
        .fade-in-delay-3 { animation-delay: 0.6s; }
        .fade-in-delay-4 { animation-delay: 0.8s; }
    </style>
</head>
<body>
    <div class="container">
        <!-- Header -->
        <header class="header">
            <div class="profile-img">👨‍💻</div>
            <h1 class="name">Seu Nome</h1>
            <p class="title">Full Stack Developer & DevOps Engineer</p>
            <div class="typing-animation" id="typing-text">console.log("Bem-vindo ao meu perfil!");</div>
        </header>

        <!-- Stats -->
        <section class="stats-section fade-in fade-in-delay-1">
            <div class="stat-card">
                <div class="stat-number">5+</div>
                <div class="stat-label">Anos de Experiência</div>
            </div>
            <div class="stat-card">
                <div class="stat-number">100+</div>
                <div class="stat-label">Projetos Concluídos</div>
            </div>
            <div class="stat-card">
                <div class="stat-number">50+</div>
                <div class="stat-label">Tecnologias Dominadas</div>
            </div>
        </section>

        <!-- About -->
        <section class="about-section fade-in fade-in-delay-2">
            <h2 class="section-title">Sobre Mim</h2>
            <p class="about-text">
                Desenvolvedor Full Stack apaixonado por criar soluções inovadoras e escaláveis. 
                Especializado em desenvolvimento web moderno, arquitetura de sistemas e DevOps. 
                Sempre em busca de novos desafios e tecnologias emergentes para entregar 
                experiências excepcionais aos usuários.
            </p>
        </section>

        <!-- Tech Stack -->
        <section class="tech-section fade-in fade-in-delay-3">
            <h2 class="section-title">🚀 Tech Stack</h2>
            
            <h3 style="text-align: center; margin: 2rem 0; font-size: 1.5rem; opacity: 0.9;">Frontend</h3>
            <div class="tech-grid">
                <div class="tech-item">
                    <span class="tech-icon">🌐</span>
                    <div class="tech-name">HTML5</div>
                </div>
                <div class="tech-item">
                    <span class="tech-icon">🎨</span>
                    <div class="tech-name">CSS3</div>
                </div>
                <div class="tech-item">
                    <span class="tech-icon">⚡</span>
                    <div class="tech-name">JavaScript</div>
                </div>
                <div class="tech-item">
                    <span class="tech-icon">💚</span>
                    <div class="tech-name">Vue.js</div>
                </div>
            </div>

            <h3 style="text-align: center; margin: 2rem 0; font-size: 1.5rem; opacity: 0.9;">Backend</h3>
            <div class="tech-grid">
                <div class="tech-item">
                    <span class="tech-icon">🐘</span>
                    <div class="tech-name">PHP</div>
                </div>
                <div class="tech-item">
                    <span class="tech-icon">🎼</span>
                    <div class="tech-name">Laravel</div>
                </div>
            </div>

            <h3 style="text-align: center; margin: 2rem 0; font-size: 1.5rem; opacity: 0.9;">DevOps & Infraestrutura</h3>
            <div class="tech-grid">
                <div class="tech-item">
                    <span class="tech-icon">🐧</span>
                    <div class="tech-name">Linux</div>
                </div>
                <div class="tech-item">
                    <span class="tech-icon">🛡️</span>
                    <div class="tech-name">Segurança</div>
                </div>
                <div class="tech-item">
                    <span class="tech-icon">☁️</span>
                    <div class="tech-name">Cloud</div>
                </div>
                <div class="tech-item">
                    <span class="tech-icon">🐳</span>
                    <div class="tech-name">Docker</div>
                </div>
            </div>
        </section>

        <!-- GitHub Stats -->
        <section class="github-stats fade-in fade-in-delay-4">
            <h2 class="section-title">📊 GitHub Stats</h2>
            <div style="text-align: center; margin-top: 2rem;">
                <img class="stat-img" src="https://github-readme-stats.vercel.app/api?username=SEU_USERNAME&show_icons=true&theme=radical&hide_border=true&bg_color=0d1117&title_color=00ff88&icon_color=00d4ff&text_color=ffffff" alt="GitHub Stats" />
                <img class="stat-img" src="https://github-readme-stats.vercel.app/api/top-langs/?username=SEU_USERNAME&layout=compact&theme=radical&hide_border=true&bg_color=0d1117&title_color=00ff88&text_color=ffffff" alt="Top Languages" />
                <img class="stat-img" src="https://github-readme-streak-stats.herokuapp.com/?user=SEU_USERNAME&theme=radical&hide_border=true&background=0d1117&stroke=00ff88&ring=00d4ff&fire=00ff88&currStreakLabel=ffffff" alt="GitHub Streak" />
            </div>
        </section>

        <!-- Snake Animation -->
        <div class="snake-animation">
            <img src="https://raw.githubusercontent.com/SEU_USERNAME/SEU_USERNAME/output/github-contribution-grid-snake.svg" alt="Snake Animation" style="max-width: 100%; border-radius: 10px;" />
        </div>

        <!-- Connect -->
        <section class="connect-section">
            <h2 class="section-title">🤝 Vamos Conectar!</h2>
            <div class="social-links">
                <a href="https://linkedin.com/in/seu-perfil" class="social-link">💼 LinkedIn</a>
                <a href="mailto:seu-email@exemplo.com" class="social-link">📧 Email</a>
                <a href="https://twitter.com/seu-perfil" class="social-link">🐦 Twitter</a>
                <a href="https://seu-portfolio.com" class="social-link">🌐 Portfolio</a>
            </div>
        </section>

        <!-- Footer -->
        <footer class="footer">
            <p>⭐ Não esqueça de dar uma estrela nos meus repositórios se você gostar do que vê!</p>
            <p style="margin-top: 1rem; opacity: 0.7;">Feito com ❤️ e muito ☕</p>
        </footer>
    </div>

    <script>
        // Typing animation
        const texts = [
            'console.log("Bem-vindo ao meu perfil!");',
            'const developer = "Full Stack Engineer";',
            'while(coding) { coffee++; }',
            'git commit -m "Building amazing things"',
            'docker run --rm awesome-projects'
        ];
        
        let textIndex = 0;
        let charIndex = 0;
        let isDeleting = false;
        const typingElement = document.getElementById('typing-text');
        
        function typeText() {
            const currentText = texts[textIndex];
            
            if (isDeleting) {
                typingElement.textContent = currentText.substring(0, charIndex - 1);
                charIndex--;
            } else {
                typingElement.textContent = currentText.substring(0, charIndex + 1);
                charIndex++;
            }
            
            let typeSpeed = isDeleting ? 50 : 100;
            
            if (!isDeleting && charIndex === currentText.length) {
                typeSpeed = 2000;
                isDeleting = true;
            } else if (isDeleting && charIndex === 0) {
                isDeleting = false;
                textIndex = (textIndex + 1) % texts.length;
                typeSpeed = 500;
            }
            
            setTimeout(typeText, typeSpeed);
        }
        
        // Start typing animation
        typeText();
        
        // Add scroll animations
        function addScrollAnimations() {
            const observer = new IntersectionObserver((entries) => {
                entries.forEach(entry => {
                    if (entry.isIntersecting) {
                        entry.target.style.opacity = '1';
                        entry.target.style.transform = 'translateY(0)';
                    }
                });
            });
            
            document.querySelectorAll('.fade-in').forEach(el => {
                el.style.opacity = '0';
                el.style.transform = 'translateY(30px)';
                el.style.transition = 'all 0.6s ease-out';
                observer.observe(el);
            });
        }
        
        // Initialize animations when page loads
        document.addEventListener('DOMContentLoaded', addScrollAnimations);
    </script>
</body>
</html>
