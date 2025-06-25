<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Skillcraft Technology - Crafting Digital Excellence</title>
    <style>
        @import url('https://fonts.googleapis.com/css2?family=Inter:wght@300;400;500;600;700;800;900&display=swap');
        
        :root {
            --primary-blue: #2563eb;
            --primary-cyan: #06b6d4;
            --accent-orange: #f59e0b;
            --dark-bg: #0f172a;
            --darker-bg: #020617;
            --glass-bg: rgba(15, 23, 42, 0.9);
            --text-primary: #ffffff;
            --text-secondary: rgba(255, 255, 255, 0.8);
            --skillcraft-gradient: linear-gradient(135deg, #2563eb 0%, #06b6d4 50%, #f59e0b 100%);
        }

        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
        }

        html {
            scroll-behavior: smooth;
        }

        body {
            font-family: 'Inter', sans-serif;
            line-height: 1.6;
            overflow-x: hidden;
            background: var(--darker-bg);
            color: var(--text-primary);
        }

        ::-webkit-scrollbar {
            width: 8px;
        }

        ::-webkit-scrollbar-track {
            background: var(--darker-bg);
        }

        ::-webkit-scrollbar-thumb {
            background: var(--skillcraft-gradient);
            border-radius: 10px;
        }

        .navbar {
            position: fixed;
            top: 0;
            left: 0;
            right: 0;
            background: rgba(15, 23, 42, 0.7);
            backdrop-filter: blur(20px);
            border-bottom: 1px solid rgba(255, 255, 255, 0.1);
            z-index: 1000;
            transition: all 0.4s cubic-bezier(0.23, 1, 0.320, 1);
            padding: 1rem 2rem;
        }

        .navbar.scrolled {
            background: rgba(2, 6, 23, 0.95);
            backdrop-filter: blur(30px);
            box-shadow: 
                0 8px 32px rgba(0, 0, 0, 0.4),
                0 0 0 1px rgba(37, 99, 235, 0.2);
            border-bottom: 1px solid rgba(37, 99, 235, 0.3);
        }

        .nav-container {
            display: flex;
            justify-content: space-between;
            align-items: center;
            max-width: 1400px;
            margin: 0 auto;
        }

        .logo {
            display: flex;
            align-items: center;
            gap: 0.5rem;
            font-size: 1.5rem;
            font-weight: 800;
            color: var(--text-primary);
            text-decoration: none;
        }

        .logo-icon {
            width: 40px;
            height: 40px;
            background: var(--skillcraft-gradient);
            border-radius: 8px;
            display: flex;
            align-items: center;
            justify-content: center;
            font-weight: 900;
            color: white;
            font-size: 1.2rem;
        }

        .logo-text {
            background: var(--skillcraft-gradient);
            -webkit-background-clip: text;
            -webkit-text-fill-color: transparent;
            background-clip: text;
        }

        .nav-menu {
            display: flex;
            list-style: none;
            gap: 0.5rem;
            background: rgba(255, 255, 255, 0.05);
            padding: 0.5rem;
            border-radius: 16px;
            backdrop-filter: blur(10px);
            border: 1px solid rgba(255, 255, 255, 0.1);
        }

        .nav-link {
            color: var(--text-secondary);
            text-decoration: none;
            padding: 0.8rem 1.5rem;
            border-radius: 12px;
            transition: all 0.3s ease;
            font-weight: 500;
            position: relative;
            overflow: hidden;
        }

        .nav-link::before {
            content: '';
            position: absolute;
            top: 0;
            left: 0;
            right: 0;
            bottom: 0;
            background: linear-gradient(135deg, 
                rgba(37, 99, 235, 0.2) 0%, 
                rgba(6, 182, 212, 0.2) 100%);
            opacity: 0;
            transition: opacity 0.3s ease;
            z-index: -1;
        }

        .nav-link:hover::before {
            opacity: 1;
        }

        .nav-link:hover {
            color: var(--text-primary);
            transform: translateY(-2px);
            box-shadow: 0 8px 25px rgba(37, 99, 235, 0.3);
        }

        .nav-link.active {
            background: linear-gradient(135deg, 
                rgba(37, 99, 235, 0.3) 0%, 
                rgba(6, 182, 212, 0.3) 100%);
            color: var(--text-primary);
            box-shadow: 0 5px 15px rgba(37, 99, 235, 0.4);
        }

        .mobile-toggle {
            display: none;
            flex-direction: column;
            cursor: pointer;
            padding: 0.5rem;
            border-radius: 8px;
            background: rgba(255, 255, 255, 0.05);
        }

        .mobile-toggle span {
            width: 25px;
            height: 3px;
            background: var(--skillcraft-gradient);
            margin: 3px 0;
            transition: all 0.3s ease;
            border-radius: 2px;
        }

        .hero {
            min-height: 100vh;
            background: 
                radial-gradient(ellipse at top left, rgba(37, 99, 235, 0.15) 0%, transparent 50%),
                radial-gradient(ellipse at bottom right, rgba(6, 182, 212, 0.15) 0%, transparent 50%),
                linear-gradient(135deg, var(--darker-bg) 0%, var(--dark-bg) 100%);
            display: flex;
            align-items: center;
            justify-content: center;
            text-align: center;
            position: relative;
            overflow: hidden;
        }

        .hero::before {
            content: '';
            position: absolute;
            top: 0;
            left: 0;
            right: 0;
            bottom: 0;
            background: url('data:image/svg+xml,<svg width="80" height="80" viewBox="0 0 80 80" xmlns="http://www.w3.org/2000/svg"><g fill="none" fill-rule="evenodd"><g fill="%23ffffff" fill-opacity="0.04"><path d="M40 40c0-5.5-4.5-10-10-10s-10 4.5-10 10 4.5 10 10 10 10-4.5 10-10zm20-20c0-5.5-4.5-10-10-10s-10 4.5-10 10 4.5 10 10 10 10-4.5 10-10z"/></g></g></svg>');
            animation: float 20s ease-in-out infinite;
        }

        @keyframes float {
            0%, 100% { transform: translate(0, 0) rotate(0deg); }
            25% { transform: translate(-5px, -5px) rotate(90deg); }
            50% { transform: translate(5px, -3px) rotate(180deg); }
            75% { transform: translate(-3px, 5px) rotate(270deg); }
        }

        .hero-content {
            max-width: 1000px;
            margin: 0 auto;
            padding: 0 2rem;
            position: relative;
            z-index: 2;
        }

        .hero-badge {
            display: inline-block;
            padding: 0.6rem 1.5rem;
            background: rgba(37, 99, 235, 0.1);
            border: 1px solid rgba(37, 99, 235, 0.3);
            border-radius: 50px;
            font-size: 0.9rem;
            font-weight: 500;
            margin-bottom: 2rem;
            animation: fadeInUp 1s ease 0.2s both;
            backdrop-filter: blur(10px);
        }

        .hero h1 {
            font-size: 4.5rem;
            font-weight: 900;
            background: var(--skillcraft-gradient);
            -webkit-background-clip: text;
            -webkit-text-fill-color: transparent;
            background-clip: text;
            margin-bottom: 1.5rem;
            animation: fadeInUp 1s ease 0.4s both;
            line-height: 1.1;
            letter-spacing: -0.02em;
        }

        .hero-subtitle {
            font-size: 1.8rem;
            font-weight: 600;
            color: var(--text-primary);
            margin-bottom: 1rem;
            animation: fadeInUp 1s ease 0.5s both;
        }

        .hero p {
            font-size: 1.3rem;
            color: var(--text-secondary);
            margin-bottom: 3rem;
            animation: fadeInUp 1s ease 0.6s both;
            max-width: 700px;
            margin-left: auto;
            margin-right: auto;
            line-height: 1.6;
        }

        .hero-buttons {
            display: flex;
            gap: 1.5rem;
            justify-content: center;
            flex-wrap: wrap;
            animation: fadeInUp 1s ease 0.8s both;
        }

        .cta-button {
            display: inline-flex;
            align-items: center;
            gap: 0.8rem;
            padding: 1.2rem 2.5rem;
            background: var(--skillcraft-gradient);
            color: white;
            text-decoration: none;
            border-radius: 12px;
            font-weight: 600;
            font-size: 1.1rem;
            transition: all 0.3s ease;
            box-shadow: 0 8px 25px rgba(37, 99, 235, 0.3);
        }

        .cta-button:hover {
            transform: translateY(-3px);
            box-shadow: 0 15px 40px rgba(37, 99, 235, 0.4);
        }

        .cta-secondary {
            display: inline-flex;
            align-items: center;
            gap: 0.8rem;
            padding: 1.2rem 2.5rem;
            background: rgba(255, 255, 255, 0.05);
            color: var(--text-primary);
            text-decoration: none;
            border-radius: 12px;
            font-weight: 600;
            font-size: 1.1rem;
            border: 1px solid rgba(255, 255, 255, 0.2);
            backdrop-filter: blur(10px);
            transition: all 0.3s ease;
        }

        .cta-secondary:hover {
            background: rgba(255, 255, 255, 0.1);
            border-color: rgba(37, 99, 235, 0.5);
            transform: translateY(-3px);
        }

        .section {
            min-height: 100vh;
            padding: 6rem 2rem;
            display: flex;
            align-items: center;
            justify-content: center;
        }

        .about {
            background: 
                radial-gradient(ellipse at left, rgba(245, 158, 11, 0.1) 0%, transparent 50%),
                linear-gradient(135deg, var(--dark-bg), var(--darker-bg));
        }

        .services {
            background: 
                radial-gradient(ellipse at right, rgba(6, 182, 212, 0.1) 0%, transparent 50%),
                linear-gradient(135deg, var(--darker-bg), var(--dark-bg));
        }

        .contact {
            background: 
                radial-gradient(ellipse at center, rgba(37, 99, 235, 0.1) 0%, transparent 50%),
                linear-gradient(135deg, var(--dark-bg), var(--darker-bg));
        }

        .section-content {
            max-width: 1200px;
            text-align: center;
        }

        .section h2 {
            font-size: 3.5rem;
            font-weight: 800;
            margin-bottom: 2rem;
            background: var(--skillcraft-gradient);
            -webkit-background-clip: text;
            -webkit-text-fill-color: transparent;
            background-clip: text;
            line-height: 1.2;
        }

        .section p {
            font-size: 1.3rem;
            color: var(--text-secondary);
            line-height: 1.8;
            max-width: 800px;
            margin: 0 auto;
        }

        .services-grid {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(320px, 1fr));
            gap: 2rem;
            margin-top: 4rem;
        }

        .service-card {
            background: rgba(255, 255, 255, 0.05);
            border: 1px solid rgba(255, 255, 255, 0.1);
            border-radius: 16px;
            padding: 2.5rem;
            backdrop-filter: blur(10px);
            transition: all 0.3s ease;
            text-align: left;
        }

        .service-card:hover {
            transform: translateY(-8px);
            box-shadow: 0 20px 40px rgba(37, 99, 235, 0.2);
            border-color: rgba(37, 99, 235, 0.3);
        }

        .service-icon {
            width: 60px;
            height: 60px;
            background: var(--skillcraft-gradient);
            border-radius: 12px;
            display: flex;
            align-items: center;
            justify-content: center;
            margin-bottom: 1.5rem;
            font-size: 1.5rem;
        }

        .service-card h3 {
            font-size: 1.4rem;
            font-weight: 700;
            margin-bottom: 1rem;
            color: var(--text-primary);
        }

        .service-card p {
            font-size: 1rem;
            color: var(--text-secondary);
            line-height: 1.6;
            text-align: left;
        }

        .tech-stack {
            display: flex;
            justify-content: center;
            flex-wrap: wrap;
            gap: 2rem;
            margin-top: 3rem;
        }

        .tech-item {
            display: flex;
            flex-direction: column;
            align-items: center;
            gap: 0.5rem;
            padding: 1.5rem;
            background: rgba(255, 255, 255, 0.05);
            border-radius: 12px;
            border: 1px solid rgba(255, 255, 255, 0.1);
            transition: all 0.3s ease;
            min-width: 120px;
        }

        .tech-item:hover {
            transform: translateY(-5px);
            border-color: rgba(37, 99, 235, 0.3);
            box-shadow: 0 10px 25px rgba(37, 99, 235, 0.2);
        }

        .tech-icon {
            font-size: 2rem;
        }

        .tech-name {
            font-size: 0.9rem;
            font-weight: 600;
            color: var(--text-secondary);
        }

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

        @media (max-width: 768px) {
            .mobile-toggle {
                display: flex;
            }

            .nav-menu {
                position: fixed;
                top: 100%;
                left: 1rem;
                right: 1rem;
                background: rgba(2, 6, 23, 0.95);
                backdrop-filter: blur(30px);
                flex-direction: column;
                padding: 2rem;
                gap: 1rem;
                border-radius: 16px;
                transform: translateY(-100vh);
                opacity: 0;
                transition: all 0.4s ease;
                border: 1px solid rgba(37, 99, 235, 0.3);
            }

            .nav-menu.active {
                transform: translateY(0);
                opacity: 1;
            }

            .hero h1 {
                font-size: 3rem;
            }

            .hero-subtitle {
                font-size: 1.4rem;
            }

            .hero p {
                font-size: 1.1rem;
            }

            .section h2 {
                font-size: 2.5rem;
            }

            .services-grid {
                grid-template-columns: 1fr;
            }

            .hero-buttons {
                flex-direction: column;
                align-items: center;
            }

            .tech-stack {
                gap: 1rem;
            }
        }
    </style>
</head>
<body>
    <nav class="navbar" id="navbar">
        <div class="nav-container">
            <a href="#home" class="logo">
                <div class="logo-icon">S</div>
                <div class="logo-text">Skillcraft Technology</div>
            </a>
            <ul class="nav-menu" id="nav-menu">
                <li class="nav-item">
                    <a href="#home" class="nav-link active">Home</a>
                </li>
                <li class="nav-item">
                    <a href="#about" class="nav-link">About</a>
                </li>
                <li class="nav-item">
                    <a href="#services" class="nav-link">Services</a>
                </li>
                <li class="nav-item">
                    <a href="#contact" class="nav-link">Contact</a>
                </li>
            </ul>
            <div class="mobile-toggle" id="mobile-toggle">
                <span></span>
                <span></span>
                <span></span>
            </div>
        </div>
    </nav>

    <section id="home" class="hero section">
        <div class="hero-content">
            <div class="hero-badge">🚀 Innovation Meets Excellence</div>
            <h1>Skillcraft Technology</h1>
            <div class="hero-subtitle">Crafting Digital Excellence</div>
            <p>Empowering businesses with cutting-edge technology solutions, innovative web development, and transformative digital experiences that drive success in the modern world.</p>
            <div class="hero-buttons">
                <a href="#services" class="cta-button">
                    <span>Explore Services</span>
                    <span>→</span>
                </a>
                <a href="#contact" class="cta-secondary">
                    <span>Get Started</span>
                    <span>✨</span>
                </a>
            </div>
        </div>
    </section>

    <section id="about" class="about section">
        <div class="section-content">
            <h2>About Skillcraft</h2>
            <p>At Skillcraft Technology, we believe in the power of skilled craftsmanship combined with cutting-edge technology. Our team of passionate developers, designers, and innovators work together to create digital solutions that not only meet today's challenges but anticipate tomorrow's opportunities. We're committed to delivering excellence in every project, fostering growth through learning, and building lasting partnerships with our clients.</p>
            
            <div class="tech-stack">
                <div class="tech-item">
                    <div class="tech-icon">⚛️</div>
                    <div class="tech-name">React</div>
                </div>
                <div class="tech-item">
                    <div class="tech-icon">🟢</div>
                    <div class="tech-name">Node.js</div>
                </div>
                <div class="tech-item">
                    <div class="tech-icon">🐍</div>
                    <div class="tech-name">Python</div>
                </div>
                <div class="tech-item">
                    <div class="tech-icon">☁️</div>
                    <div class="tech-name">Cloud</div>
                </div>
                <div class="tech-item">
                    <div class="tech-icon">🤖</div>
                    <div class="tech-name">AI/ML</div>
                </div>
                <div class="tech-item">
                    <div class="tech-icon">📱</div>
                    <div class="tech-name">Mobile</div>
                </div>
            </div>
        </div>
    </section>

    <section id="services" class="services section">
        <div class="section-content">
            <h2>Our Services</h2>
            <p>We offer comprehensive technology solutions designed to accelerate your business growth and digital transformation. From custom software development to AI-powered applications, we have the expertise to bring your vision to life.</p>
            
            <div class="services-grid">
                <div class="service-card">
                    <div class="service-icon">💻</div>
                    <h3>Web Development</h3>
                    <p>Custom websites and web applications built with modern frameworks, responsive design, and optimized performance for exceptional user experiences.</p>
                </div>
                <div class="service-card">
                    <div class="service-icon">📱</div>
                    <h3>Mobile Development</h3>
                    <p>Native and cross-platform mobile applications that engage users and deliver seamless functionality across iOS and Android devices.</p>
                </div>
                <div class="service-card">
                    <div class="service-icon">🤖</div>
                    <h3>AI & Machine Learning</h3>
                    <p>Intelligent solutions powered by artificial intelligence and machine learning to automate processes and unlock valuable insights from your data.</p>
                </div>
                <div class="service-card">
                    <div class="service-icon">☁️</div>
                    <h3>Cloud Solutions</h3>
                    <p>Scalable cloud infrastructure, migration services, and deployment strategies that ensure your applications are secure, reliable, and performant.</p>
                </div>
                <div class="service-card">
                    <div class="service-icon">🎨</div>
                    <h3>UI/UX Design</h3>
                    <p>User-centered design that combines aesthetics with functionality, creating intuitive interfaces that enhance user satisfaction and engagement.</p>
                </div>
                <div class="service-card">
                    <div class="service-icon">🔧</div>
                    <h3>Digital Consulting</h3>
                    <p>Strategic technology consulting to help you make informed decisions, optimize workflows, and leverage technology for competitive advantage.</p>
                </div>
            </div>
        </div>
    </section>

    <section id="contact" class="contact section">
        <div class="section-content">
            <h2>Let's Build Something Amazing</h2>
            <p>Ready to transform your ideas into reality? Whether you're a startup looking to make your mark or an established business ready to innovate, we're here to help you succeed. Let's discuss how Skillcraft Technology can accelerate your digital journey.</p>
            
            <div class="hero-buttons" style="margin-top: 3rem;">
                <a href="mailto:info@skillcraft.tech" class="cta-button">
                    <span>Start Your Project</span>
                    <span>🚀</span>
                </a>
                <a href="tel:+1234567890" class="cta-secondary">
                    <span>Schedule Consultation</span>
                    <span>📞</span>
                </a>
            </div>
        </div>
    </section>

    <script>
        const navbar = document.getElementById('navbar');
        const navLinks = document.querySelectorAll('.nav-link');
        const sections = document.querySelectorAll('.section');

        window.addEventListener('scroll', () => {
            const scrolled = window.scrollY > 50;
            navbar.classList.toggle('scrolled', scrolled);

            let current = '';
            sections.forEach(section => {
                const sectionTop = section.offsetTop;
                const sectionHeight = section.clientHeight;
                if (window.scrollY >= (sectionTop - 200)) {
                    current = section.getAttribute('id');
                }
            });

            navLinks.forEach(link => {
                link.classList.remove('active');
                if (link.getAttribute('href') === '#' + current) {
                    link.classList.add('active');
                }
            });
        });

        navLinks.forEach(link => {
            link.addEventListener('click', (e) => {
                e.preventDefault();
                const targetId = link.getAttribute('href');
                const targetSection = document.querySelector(targetId);
                
                if (targetSection) {
                    targetSection.scrollIntoView({
                        behavior: 'smooth',
                        block: 'start'
                    });
                }

                document.getElementById('nav-menu').classList.remove('active');
            });
        });

        const mobileToggle = document.getElementById('mobile-toggle');
        const navMenu = document.getElementById('nav-menu');

        mobileToggle.addEventListener('click', () => {
            navMenu.classList.toggle('active');
        });

        document.addEventListener('click', (e) => {
            if (!navbar.contains(e.target)) {
                navMenu.classList.remove('active');
            }
        });

        const observerOptions = {
            threshold: 0.1,
            rootMargin: '0px 0px -50px 0px'
        };

        const observer = new IntersectionObserver((entries) => {
            entries.forEach(entry => {
                if (entry.isIntersecting) {
                    entry.target.style.opacity = '1';
                    entry.target.style.transform = 'translateY(0)';
                }
            });
        }, observerOptions);

        document.querySelectorAll('.service-card, .tech-item').forEach(item => {
            item.style.opacity = '0';
            item.style.transform = 'translateY(30px)';
            item.style.transition = 'all 0.6s ease';
            observer.observe(item);
        });

        document.querySelectorAll('.service-card').forEach((card, index) => {
            card.style.transitionDelay = `${index * 0.1}s`;
        });

        document.querySelectorAll('.tech-item').forEach((item, index) => {
            item.style.transitionDelay = `${index * 0.1}s`;
        });
    </script>
</body>
</html>
