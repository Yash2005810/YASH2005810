<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Yash Surana - Frontend Developer</title>
    <style>
        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
        }

        body {
            font-family: 'Segoe UI', Tahoma, Geneva, Verdana, sans-serif;
            background: linear-gradient(135deg, #0a0a0a 0%, #1a1a2e 50%, #16213e 100%);
            color: #ffffff;
            overflow-x: hidden;
            line-height: 1.6;
            min-height: 100vh;
        }

        .container {
            max-width: 1200px;
            margin: 0 auto;
            padding: 0 20px;
        }

        /* Animated Background */
        .bg-animation {
            position: fixed;
            top: 0;
            left: 0;
            width: 100%;
            height: 100%;
            z-index: -1;
            overflow: hidden;
        }

        .bg-animation::before {
            content: '';
            position: absolute;
            top: -50%;
            left: -50%;
            width: 200%;
            height: 200%;
            background: radial-gradient(circle, rgba(56, 189, 248, 0.05) 0%, transparent 70%);
            animation: rotate 30s linear infinite;
        }

        @keyframes rotate {
            from { transform: rotate(0deg); }
            to { transform: rotate(360deg); }
        }

        /* Floating particles */
        .particle {
            position: absolute;
            border-radius: 50%;
            background: rgba(56, 189, 248, 0.3);
            animation: float 6s ease-in-out infinite;
        }

        .particle:nth-child(1) { width: 4px; height: 4px; top: 20%; left: 10%; animation-delay: 0s; }
        .particle:nth-child(2) { width: 6px; height: 6px; top: 60%; left: 80%; animation-delay: 1s; }
        .particle:nth-child(3) { width: 3px; height: 3px; top: 40%; left: 60%; animation-delay: 2s; }
        .particle:nth-child(4) { width: 5px; height: 5px; top: 80%; left: 30%; animation-delay: 3s; }

        @keyframes float {
            0%, 100% { transform: translateY(0px) rotate(0deg); opacity: 1; }
            50% { transform: translateY(-20px) rotate(180deg); opacity: 0.5; }
        }

        /* Header Section */
        .header {
            text-align: center;
            padding: 80px 0 60px;
            position: relative;
        }

        .profile-container {
            position: relative;
            display: inline-block;
            margin-bottom: 30px;
        }

        .profile-img {
            width: 140px;
            height: 140px;
            border-radius: 50%;
            background: linear-gradient(45deg, #38bdf8, #8b5cf6, #f59e0b);
            display: flex;
            align-items: center;
            justify-content: center;
            margin: 0 auto;
            position: relative;
            animation: profilePulse 3s ease-in-out infinite;
            box-shadow: 0 0 50px rgba(56, 189, 248, 0.3);
        }

        .profile-img::before {
            content: '👋';
            font-size: 60px;
            animation: wave 2s ease-in-out infinite;
        }

        @keyframes profilePulse {
            0%, 100% { transform: scale(1); box-shadow: 0 0 50px rgba(56, 189, 248, 0.3); }
            50% { transform: scale(1.05); box-shadow: 0 0 80px rgba(56, 189, 248, 0.5); }
        }

        @keyframes wave {
            0%, 50%, 100% { transform: rotate(0deg); }
            25% { transform: rotate(20deg); }
            75% { transform: rotate(-10deg); }
        }

        .title {
            font-size: 3.5rem;
            font-weight: 700;
            margin-bottom: 20px;
            background: linear-gradient(45deg, #38bdf8, #8b5cf6, #f59e0b);
            -webkit-background-clip: text;
            -webkit-text-fill-color: transparent;
            background-clip: text;
            animation: titleGlow 2s ease-in-out infinite alternate;
        }

        @keyframes titleGlow {
            from { filter: brightness(1); }
            to { filter: brightness(1.2); }
        }

        .subtitle {
            font-size: 1.5rem;
            color: #94a3b8;
            margin-bottom: 30px;
            animation: fadeInUp 1s ease-out 0.5s both;
        }

        .profile-stats {
            display: flex;
            justify-content: center;
            gap: 30px;
            margin-bottom: 40px;
            animation: fadeInUp 1s ease-out 1s both;
        }

        .stat-item {
            background: rgba(255, 255, 255, 0.05);
            padding: 15px 25px;
            border-radius: 15px;
            backdrop-filter: blur(10px);
            border: 1px solid rgba(255, 255, 255, 0.1);
            transition: all 0.3s ease;
        }

        .stat-item:hover {
            transform: translateY(-5px);
            background: rgba(56, 189, 248, 0.1);
            border-color: rgba(56, 189, 248, 0.3);
        }

        .stat-number {
            font-size: 1.5rem;
            font-weight: bold;
            color: #38bdf8;
            display: block;
        }

        .stat-label {
            font-size: 0.9rem;
            color: #94a3b8;
        }

        /* About Section */
        .about-section {
            padding: 60px 0;
            animation: fadeInUp 1s ease-out 1.5s both;
        }

        .section-title {
            font-size: 2.5rem;
            text-align: center;
            margin-bottom: 50px;
            position: relative;
        }

        .section-title::after {
            content: '';
            position: absolute;
            bottom: -10px;
            left: 50%;
            transform: translateX(-50%);
            width: 80px;
            height: 4px;
            background: linear-gradient(45deg, #38bdf8, #8b5cf6);
            border-radius: 2px;
        }

        .about-grid {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(300px, 1fr));
            gap: 30px;
            margin-bottom: 50px;
        }

        .about-card {
            background: rgba(255, 255, 255, 0.05);
            padding: 30px;
            border-radius: 20px;
            backdrop-filter: blur(10px);
            border: 1px solid rgba(255, 255, 255, 0.1);
            transition: all 0.3s ease;
            position: relative;
            overflow: hidden;
        }

        .about-card::before {
            content: '';
            position: absolute;
            top: 0;
            left: -100%;
            width: 100%;
            height: 100%;
            background: linear-gradient(90deg, transparent, rgba(56, 189, 248, 0.1), transparent);
            transition: left 0.5s;
        }

        .about-card:hover::before {
            left: 100%;
        }

        .about-card:hover {
            transform: translateY(-10px);
            border-color: rgba(56, 189, 248, 0.3);
            box-shadow: 0 20px 40px rgba(56, 189, 248, 0.1);
        }

        .about-item {
            display: flex;
            align-items: flex-start;
            margin-bottom: 15px;
            position: relative;
            z-index: 1;
        }

        .about-icon {
            margin-right: 15px;
            font-size: 1.2rem;
        }

        /* Skills Section */
        .skills-section {
            padding: 60px 0;
        }

        .skills-grid {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(100px, 1fr));
            gap: 20px;
            margin-top: 40px;
        }

        .skill-item {
            background: rgba(255, 255, 255, 0.05);
            padding: 25px;
            border-radius: 15px;
            text-align: center;
            transition: all 0.3s ease;
            border: 1px solid rgba(255, 255, 255, 0.1);
            position: relative;
            overflow: hidden;
        }

        .skill-item::before {
            content: '';
            position: absolute;
            top: 0;
            left: 0;
            right: 0;
            height: 3px;
            background: linear-gradient(45deg, #38bdf8, #8b5cf6);
            transform: scaleX(0);
            transition: transform 0.3s ease;
        }

        .skill-item:hover::before {
            transform: scaleX(1);
        }

        .skill-item:hover {
            transform: translateY(-10px);
            background: rgba(56, 189, 248, 0.1);
            border-color: rgba(56, 189, 248, 0.3);
        }

        .skill-icon {
            font-size: 2.5rem;
            margin-bottom: 10px;
            display: block;
            animation: skillFloat 3s ease-in-out infinite;
        }

        @keyframes skillFloat {
            0%, 100% { transform: translateY(0px); }
            50% { transform: translateY(-5px); }
        }

        .skill-item:nth-child(even) .skill-icon {
            animation-delay: 0.5s;
        }

        /* Connect Section */
        .connect-section {
            padding: 60px 0;
            text-align: center;
        }

        .social-links {
            display: flex;
            justify-content: center;
            gap: 20px;
            margin: 40px 0;
        }

        .social-link {
            display: flex;
            align-items: center;
            justify-content: center;
            width: 60px;
            height: 60px;
            background: rgba(255, 255, 255, 0.05);
            border-radius: 50%;
            text-decoration: none;
            color: #ffffff;
            font-size: 1.5rem;
            transition: all 0.3s ease;
            border: 1px solid rgba(255, 255, 255, 0.1);
            position: relative;
            overflow: hidden;
        }

        .social-link::before {
            content: '';
            position: absolute;
            top: 0;
            left: 0;
            width: 100%;
            height: 100%;
            background: linear-gradient(45deg, #38bdf8, #8b5cf6);
            border-radius: 50%;
            transform: scale(0);
            transition: transform 0.3s ease;
            z-index: -1;
        }

        .social-link:hover::before {
            transform: scale(1);
        }

        .social-link:hover {
            transform: translateY(-5px);
            color: #ffffff;
            box-shadow: 0 10px 25px rgba(56, 189, 248, 0.3);
        }

        /* Stats Section */
        .stats-section {
            padding: 60px 0;
        }

        .stats-grid {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(300px, 1fr));
            gap: 20px;
            margin-top: 40px;
        }

        .stat-card {
            background: rgba(255, 255, 255, 0.05);
            padding: 20px;
            border-radius: 15px;
            backdrop-filter: blur(10px);
            border: 1px solid rgba(255, 255, 255, 0.1);
            transition: all 0.3s ease;
        }

        .stat-card:hover {
            transform: translateY(-5px);
            border-color: rgba(56, 189, 248, 0.3);
        }

        .stat-card img {
            width: 100%;
            height: auto;
            border-radius: 10px;
            opacity: 0.9;
            transition: opacity 0.3s ease;
        }

        .stat-card:hover img {
            opacity: 1;
        }

        /* Animations */
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

        @keyframes slideInLeft {
            from {
                opacity: 0;
                transform: translateX(-50px);
            }
            to {
                opacity: 1;
                transform: translateX(0);
            }
        }

        /* Responsive Design */
        @media (max-width: 768px) {
            .title {
                font-size: 2.5rem;
            }
            
            .subtitle {
                font-size: 1.2rem;
            }
            
            .profile-stats {
                flex-direction: column;
                align-items: center;
                gap: 15px;
            }
            
            .about-grid {
                grid-template-columns: 1fr;
            }
            
            .skills-grid {
                grid-template-columns: repeat(auto-fit, minmax(80px, 1fr));
                gap: 15px;
            }
            
            .social-links {
                flex-wrap: wrap;
            }
        }

        /* Loading Animation */
        .loading {
            opacity: 0;
            animation: fadeInUp 0.6s ease-out forwards;
        }

        .loading:nth-child(1) { animation-delay: 0.1s; }
        .loading:nth-child(2) { animation-delay: 0.2s; }
        .loading:nth-child(3) { animation-delay: 0.3s; }
        .loading:nth-child(4) { animation-delay: 0.4s; }
    </style>
</head>
<body>
    <!-- Animated Background -->
    <div class="bg-animation">
        <div class="particle"></div>
        <div class="particle"></div>
        <div class="particle"></div>
        <div class="particle"></div>
    </div>

    <div class="container">
        <!-- Header Section -->
        <header class="header">
            <div class="profile-container">
                <div class="profile-img"></div>
            </div>
            <h1 class="title loading">Hi 👋, I'm Yash Surana</h1>
            <p class="subtitle loading">A passionate frontend developer from India</p>
            
            <div class="profile-stats loading">
                <div class="stat-item">
                    <span class="stat-number" data-target="50">0</span>
                    <span class="stat-label">Profile Views</span>
                </div>
                <div class="stat-item">
                    <span class="stat-number" data-target="15">0</span>
                    <span class="stat-label">Projects</span>
                </div>
                <div class="stat-item">
                    <span class="stat-number" data-target="8">0</span>
                    <span class="stat-label">Technologies</span>
                </div>
            </div>
        </header>

        <!-- About Section -->
        <section class="about-section loading">
            <h2 class="section-title">About Me</h2>
            <div class="about-grid">
                <div class="about-card">
                    <div class="about-item">
                        <span class="about-icon">🌱</span>
                        <div>
                            <strong>Currently Learning:</strong><br>
                            Data Structures and Algorithms (DSA)
                        </div>
                    </div>
                    <div class="about-item">
                        <span class="about-icon">👨‍💻</span>
                        <div>
                            <strong>Portfolio:</strong><br>
                            <a href="https://yash-surana-qfvnxl1.gamma.site/" target="_blank" style="color: #38bdf8;">View My Projects</a>
                        </div>
                    </div>
                </div>
                
                <div class="about-card">
                    <div class="about-item">
                        <span class="about-icon">💬</span>
                        <div>
                            <strong>Ask me about:</strong><br>
                            Git, GitHub, HTML, CSS, JavaScript
                        </div>
                    </div>
                    <div class="about-item">
                        <span class="about-icon">📫</span>
                        <div>
                            <strong>Reach me:</strong><br>
                            <a href="mailto:yashsurana2005810@gmail.com" style="color: #38bdf8;">yashsurana2005810@gmail.com</a>
                        </div>
                    </div>
                </div>
            </div>
        </section>

        <!-- Skills Section -->
        <section class="skills-section loading">
            <h2 class="section-title">Languages & Tools</h2>
            <div class="skills-grid">
                <div class="skill-item">
                    <span class="skill-icon">🔧</span>
                    <div>Arduino</div>
                </div>
                <div class="skill-item">
                    <span class="skill-icon">⚡</span>
                    <div>C++</div>
                </div>
                <div class="skill-item">
                    <span class="skill-icon">🎨</span>
                    <div>CSS3</div>
                </div>
                <div class="skill-item">
                    <span class="skill-icon">🔀</span>
                    <div>Git</div>
                </div>
                <div class="skill-item">
                    <span class="skill-icon">🌐</span>
                    <div>HTML5</div>
                </div>
                <div class="skill-item">
                    <span class="skill-icon">⚡</span>
                    <div>JavaScript</div>
                </div>
                <div class="skill-item">
                    <span class="skill-icon">🗄️</span>
                    <div>MySQL</div>
                </div>
                <div class="skill-item">
                    <span class="skill-icon">🐍</span>
                    <div>Python</div>
                </div>
            </div>
        </section>

        <!-- Connect Section -->
        <section class="connect-section loading">
            <h2 class="section-title">Connect with me</h2>
            <div class="social-links">
                <a href="https://www.linkedin.com/in/yash-surana-5714452b2/" target="_blank" class="social-link" title="LinkedIn">
                    💼
                </a>
                <a href="https://leetcode.com/u/yash810/" target="_blank" class="social-link" title="LeetCode">
                    🧠
                </a>
                <a href="mailto:yashsurana2005810@gmail.com" class="social-link" title="Email">
                    ✉️
                </a>
                <a href="https://yash-surana-qfvnxl1.gamma.site/" target="_blank" class="social-link" title="Portfolio">
                    🌐
                </a>
            </div>
        </section>

        <!-- GitHub Stats Section -->
        <section class="stats-section loading">
            <h2 class="section-title">GitHub Statistics</h2>
            <div class="stats-grid">
                <div class="stat-card">
                    <img src="https://github-readme-stats.vercel.app/api/top-langs?username=yash2005810&show_icons=true&locale=en&layout=compact&theme=dark&bg_color=0a0a0a&title_color=38bdf8&text_color=ffffff&icon_color=8b5cf6" alt="Top Languages" />
                </div>
                <div class="stat-card">
                    <img src="https://github-readme-stats.vercel.app/api?username=yash2005810&show_icons=true&locale=en&theme=dark&bg_color=0a0a0a&title_color=38bdf8&text_color=ffffff&icon_color=8b5cf6" alt="GitHub Stats" />
                </div>
                <div class="stat-card">
                    <img src="https://github-readme-streak-stats.herokuapp.com/?user=yash2005810&theme=dark&background=0a0a0a&stroke=38bdf8&ring=8b5cf6&fire=f59e0b&currStreakLabel=ffffff" alt="GitHub Streak" />
                </div>
                <div class="stat-card">
                    <img src="https://github-profile-trophy.vercel.app/?username=yash2005810&theme=darkhub&no-frame=true&margin-w=5&row=1" alt="GitHub Trophies" />
                </div>
            </div>
        </section>
    </div>

    <script>
        // Counter Animation
        function animateCounters() {
            const counters = document.querySelectorAll('.stat-number');
            const speed = 200;

            counters.forEach(counter => {
                const updateCount = () => {
                    const target = +counter.getAttribute('data-target');
                    const count = +counter.innerText;
                    const inc = target / speed;

                    if (count < target) {
                        counter.innerText = Math.ceil(count + inc);
                        setTimeout(updateCount, 1);
                    } else {
                        counter.innerText = target;
                    }
                };
                updateCount();
            });
        }

        // Intersection Observer for animations
        const observerOptions = {
            threshold: 0.1,
            rootMargin: '0px 0px -50px 0px'
        };

        const observer = new IntersectionObserver((entries) => {
            entries.forEach(entry => {
                if (entry.isIntersecting) {
                    entry.target.style.animationPlayState = 'running';
                    if (entry.target.classList.contains('profile-stats')) {
                        animateCounters();
                    }
                }
            });
        }, observerOptions);

        // Observe all loading elements
        document.querySelectorAll('.loading').forEach(el => {
            observer.observe(el);
        });

        // Smooth scrolling for internal links
        document.querySelectorAll('a[href^="#"]').forEach(anchor => {
            anchor.addEventListener('click', function (e) {
                e.preventDefault();
                document.querySelector(this.getAttribute('href')).scrollIntoView({
                    behavior: 'smooth'
                });
            });
        });

        // Add dynamic typing effect to title
        function typeWriter() {
            const text = "Hi 👋, I'm Yash Surana";
            const titleElement = document.querySelector('.title');
            let i = 0;
            
            titleElement.innerHTML = '';
            
            function type() {
                if (i < text.length) {
                    titleElement.innerHTML += text.charAt(i);
                    i++;
                    setTimeout(type, 100);
                }
            }
            
            setTimeout(type, 1000);
        }

        // Initialize animations when page loads
        window.addEventListener('load', () => {
            // Start counter animation after a delay
            setTimeout(animateCounters, 2000);
            
            // Add stagger animation to skill items
            const skillItems = document.querySelectorAll('.skill-item');
            skillItems.forEach((item, index) => {
                item.style.animationDelay = `${index * 0.1}s`;
            });
        });

        // Add parallax effect to background
        window.addEventListener('scroll', () => {
            const scrolled = window.pageYOffset;
            const parallax = document.querySelector('.bg-animation');
            const speed = scrolled * 0.5;
            parallax.style.transform = `translateY(${speed}px)`;
        });

        // Add mouse movement effect
        document.addEventListener('mousemove', (e) => {
            const particles = document.querySelectorAll('.particle');
            const x = e.clientX / window.innerWidth;
            const y = e.clientY / window.innerHeight;
            
            particles.forEach((particle, index) => {
                const speed = (index + 1) * 0.5;
                const xPos = (x - 0.5) * speed * 50;
                const yPos = (y - 0.5) * speed * 50;
                particle.style.transform = `translate(${xPos}px, ${yPos}px)`;
            });
        });
    </script>
</body>
</html>
