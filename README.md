<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Rainy Days - Leave a Drop, Read the Rain</title>
    <link href="https://fonts.googleapis.com/css2?family=Playfair+Display:wght@400;600;700&family=Inter:wght@300;400;500;600&display=swap" rel="stylesheet">
    <style>
        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
        }

        body {
            font-family: 'Inter', sans-serif;
            overflow-x: hidden;
            background: #0a1628;
            color: #fff;
        }

        header {
            position: fixed;
            top: 0;
            width: 100%;
            padding: 20px 50px;
            display: flex;
            justify-content: space-between;
            align-items: center;
            z-index: 1000;
            transition: all 0.3s;
            background: rgba(10, 22, 40, 0.8);
            backdrop-filter: blur(10px);
        }

        header.scrolled {
            background: rgba(10, 22, 40, 0.95);
            padding: 15px 50px;
        }

        .logo {
            font-family: 'Playfair Display', serif;
            font-size: 28px;
            font-weight: 700;
            color: #7ab8eb;
            cursor: pointer;
        }

        nav {
            display: flex;
            gap: 35px;
        }

        nav a {
            color: #e8f1f8;
            text-decoration: none;
            font-size: 15px;
            font-weight: 400;
            transition: all 0.3s;
            position: relative;
        }

        nav a:after {
            content: '';
            position: absolute;
            bottom: -5px;
            left: 0;
            width: 0;
            height: 2px;
            background: #7ab8eb;
            transition: width 0.3s;
        }

        nav a:hover:after {
            width: 100%;
        }

        .hero {
            height: 100vh;
            display: flex;
            align-items: center;
            justify-content: center;
            position: relative;
            overflow: hidden;
            background: linear-gradient(135deg, #0a1628 0%, #1a2f4a 50%, #2a4564 100%);
        }

        .rain-container {
            position: absolute;
            top: 0;
            left: 0;
            width: 100%;
            height: 100%;
            pointer-events: none;
            overflow: hidden;
        }

        .raindrop {
            position: absolute;
            width: 2px;
            height: 50px;
            background: linear-gradient(to bottom, transparent, rgba(122, 184, 235, 0.3));
            animation: fall linear infinite;
        }

        @keyframes fall {
            to {
                transform: translateY(100vh);
            }
        }

        .hero-content {
            text-align: center;
            z-index: 10;
            max-width: 900px;
            padding: 0 20px;
            animation: fadeInUp 1s ease-out;
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

        .hero h1 {
            font-family: 'Playfair Display', serif;
            font-size: 72px;
            font-weight: 700;
            margin-bottom: 20px;
            color: #e8f1f8;
            text-shadow: 0 2px 20px rgba(122, 184, 235, 0.3);
        }

        .hero p {
            font-size: 24px;
            font-weight: 300;
            color: #b8d4ea;
            margin-bottom: 40px;
            letter-spacing: 1px;
        }

        .cta-buttons {
            display: flex;
            gap: 20px;
            justify-content: center;
            flex-wrap: wrap;
        }

        .btn {
            padding: 16px 40px;
            border-radius: 50px;
            text-decoration: none;
            font-weight: 500;
            font-size: 16px;
            transition: all 0.3s;
            display: inline-block;
            cursor: pointer;
        }

        .btn-primary {
            background: linear-gradient(135deg, #7ab8eb 0%, #5a9dd5 100%);
            color: #fff;
            box-shadow: 0 10px 30px rgba(122, 184, 235, 0.3);
        }

        .btn-primary:hover {
            transform: translateY(-3px);
            box-shadow: 0 15px 40px rgba(122, 184, 235, 0.4);
        }

        .btn-secondary {
            background: transparent;
            color: #7ab8eb;
            border: 2px solid #7ab8eb;
        }

        .btn-secondary:hover {
            background: rgba(122, 184, 235, 0.1);
            transform: translateY(-3px);
        }

        .features {
            padding: 120px 50px;
            background: #0f1f36;
        }

        .section-title {
            text-align: center;
            margin-bottom: 80px;
        }

        .section-title h2 {
            font-family: 'Playfair Display', serif;
            font-size: 48px;
            color: #e8f1f8;
            margin-bottom: 15px;
        }

        .section-title p {
            font-size: 18px;
            color: #8fa9c4;
        }

        .features-grid {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(320px, 1fr));
            gap: 40px;
            max-width: 1200px;
            margin: 0 auto;
        }

        .feature-card {
            background: rgba(26, 47, 74, 0.5);
            border-radius: 20px;
            padding: 40px;
            transition: all 0.4s;
            border: 1px solid rgba(122, 184, 235, 0.1);
        }

        .feature-card:hover {
            transform: translateY(-10px);
            background: rgba(26, 47, 74, 0.8);
            border-color: rgba(122, 184, 235, 0.3);
            box-shadow: 0 20px 60px rgba(122, 184, 235, 0.2);
        }

        .feature-icon {
            width: 70px;
            height: 70px;
            border-radius: 50%;
            background: linear-gradient(135deg, #7ab8eb 0%, #5a9dd5 100%);
            display: flex;
            align-items: center;
            justify-content: center;
            margin-bottom: 25px;
            font-size: 32px;
        }

        .feature-card h3 {
            font-family: 'Playfair Display', serif;
            font-size: 26px;
            margin-bottom: 15px;
            color: #e8f1f8;
        }

        .feature-card p {
            color: #8fa9c4;
            line-height: 1.7;
            font-size: 16px;
        }

        .stats {
            padding: 100px 50px;
            background: linear-gradient(135deg, #1a2f4a 0%, #0a1628 100%);
            text-align: center;
        }

        .stats-grid {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(200px, 1fr));
            gap: 50px;
            max-width: 900px;
            margin: 0 auto;
        }

        .stat-item h3 {
            font-family: 'Playfair Display', serif;
            font-size: 56px;
            color: #7ab8eb;
            margin-bottom: 10px;
        }

        .stat-item p {
            font-size: 18px;
            color: #8fa9c4;
        }

        footer {
            padding: 50px;
            text-align: center;
            background: #0a1628;
            border-top: 1px solid rgba(122, 184, 235, 0.1);
        }

        footer p {
            color: #8fa9c4;
            margin-bottom: 10px;
        }

        .scroll-indicator {
            position: absolute;
            bottom: 30px;
            left: 50%;
            transform: translateX(-50%);
            animation: bounce 2s infinite;
        }

        @keyframes bounce {
            0%, 20%, 50%, 80%, 100% {
                transform: translateX(-50%) translateY(0);
            }
            40% {
                transform: translateX(-50%) translateY(-10px);
            }
            60% {
                transform: translateX(-50%) translateY(-5px);
            }
        }

        .scroll-indicator::before {
            content: '↓';
            font-size: 24px;
            color: #7ab8eb;
        }

        @media (max-width: 768px) {
            header {
                padding: 15px 20px;
            }

            nav {
                gap: 20px;
                font-size: 14px;
            }

            .hero h1 {
                font-size: 42px;
            }

            .hero p {
                font-size: 18px;
            }

            .features, .stats {
                padding: 60px 20px;
            }

            .section-title h2 {
                font-size: 36px;
            }
        }
    </style>
</head>
<body>
    <header id="header">
        <div class="logo">Rainy Days</div>
        <nav>
            <a href="#home">Home</a>
            <a href="#about">About</a>
            <a href="#write">Write a Raindrop</a>
            <a href="#read">Read The Rain</a>
            <a href="#contact">Contact</a>
            <a href="#faq">FAQ</a>
            <a href="#guidelines">Guidelines</a>
        </nav>
    </header>

    <section class="hero">
        <div class="rain-container" id="rainContainer"></div>
        <div class="hero-content">
            <h1>Rainy Days</h1>
            <p>Leave a drop. Read the rain.</p>
            <div class="cta-buttons">
                <a href="#write" class="btn btn-primary">Write a Raindrop</a>
                <a href="#read" class="btn btn-secondary">Read The Rain</a>
            </div>
        </div>
        <div class="scroll-indicator"></div>
    </section>

    <section class="features">
        <div class="section-title">
            <h2>A Space for Connection</h2>
            <p>Share your thoughts, offer support, and find comfort in community</p>
        </div>
        <div class="features-grid">
            <div class="feature-card">
                <div class="feature-icon">💧</div>
                <h3>Completely Anonymous</h3>
                <p>Your privacy matters. Share your thoughts without revealing your identity. Every drop is secure and untraceable.</p>
            </div>
            <div class="feature-card">
                <div class="feature-icon">🌧️</div>
                <h3>Read & Reflect</h3>
                <p>Scroll through raindrops from others. Find comfort knowing you're not alone, and discover stories that resonate with yours.</p>
            </div>
            <div class="feature-card">
                <div class="feature-icon">💙</div>
                <h3>Express Freely</h3>
                <p>Share your feelings, thoughts, or words of encouragement. Whether it's hope, gratitude, or support—your voice matters.</p>
            </div>
        </div>
    </section>

    <section class="stats">
        <div class="stats-grid">
            <div class="stat-item">
                <h3>10,000+</h3>
                <p>Raindrops Shared</p>
            </div>
            <div class="stat-item">
                <h3>5,000+</h3>
                <p>Stories Read</p>
            </div>
            <div class="stat-item">
                <h3>100%</h3>
                <p>Anonymous & Safe</p>
            </div>
        </div>
    </section>

    <footer>
        <p>© 2023 Rainy Days</p>
        <p>Created with care for those who need it</p>
        <p style="font-size: 14px; margin-top: 20px; font-style: italic;">"Leave a drop. Read a dream. Feel the rain."</p>
    </footer>

    <script>
        // Rain animation
        const rainContainer = document.getElementById('rainContainer');
        for (let i = 0; i < 50; i++) {
            const drop = document.createElement('div');
            drop.className = 'raindrop';
            drop.style.left = Math.random() * 100 + '%';
            drop.style.animationDuration = (Math.random() * 1 + 0.5) + 's';
            drop.style.animationDelay = Math.random() * 2 + 's';
            rainContainer.appendChild(drop);
        }

        // Header scroll effect
        window.addEventListener('scroll', () => {
            const header = document.getElementById('header');
            if (window.scrollY > 100) {
                header.classList.add('scrolled');
            } else {
                header.classList.remove('scrolled');
            }
        });
    </script>
</body>
</html>