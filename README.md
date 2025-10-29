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

        html, body {
            height: 100%;
            width: 100%;
            overflow: hidden;
            font-family: 'Inter', sans-serif;
        }

        body {
            background: #0a1628;
            color: #fff;
            position: relative;
        }

        header {
            position: absolute;
            top: 0;
            width: 100%;
            padding: 25px 50px;
            display: flex;
            justify-content: space-between;
            align-items: center;
            z-index: 1000;
            background: rgba(10, 22, 40, 0.3);
            backdrop-filter: blur(10px);
        }

        .logo {
            font-family: 'Playfair Display', serif;
            font-size: 32px;
            font-weight: 700;
            color: #7ab8eb;
            cursor: pointer;
            text-shadow: 0 2px 10px rgba(122, 184, 235, 0.3);
        }

        nav {
            display: flex;
            gap: 40px;
        }

        nav a {
            color: #e8f1f8;
            text-decoration: none;
            font-size: 16px;
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
            width: 100vw;
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
            height: 60px;
            background: linear-gradient(to bottom, transparent, rgba(122, 184, 235, 0.4));
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
            animation: fadeInUp 1.2s ease-out;
        }

        @keyframes fadeInUp {
            from {
                opacity: 0;
                transform: translateY(40px);
            }
            to {
                opacity: 1;
                transform: translateY(0);
            }
        }

        .hero h1 {
            font-family: 'Playfair Display', serif;
            font-size: 96px;
            font-weight: 700;
            margin-bottom: 25px;
            color: #e8f1f8;
            text-shadow: 0 4px 30px rgba(122, 184, 235, 0.4);
            letter-spacing: 2px;
        }

        .hero p {
            font-size: 28px;
            font-weight: 300;
            color: #b8d4ea;
            margin-bottom: 50px;
            letter-spacing: 2px;
        }

        .cta-buttons {
            display: flex;
            gap: 25px;
            justify-content: center;
            flex-wrap: wrap;
        }

        .btn {
            padding: 18px 45px;
            border-radius: 50px;
            text-decoration: none;
            font-weight: 500;
            font-size: 18px;
            transition: all 0.4s;
            display: inline-block;
            cursor: pointer;
            border: none;
        }

        .btn-primary {
            background: linear-gradient(135deg, #7ab8eb 0%, #5a9dd5 100%);
            color: #fff;
            box-shadow: 0 10px 40px rgba(122, 184, 235, 0.4);
        }

        .btn-primary:hover {
            transform: translateY(-5px);
            box-shadow: 0 20px 50px rgba(122, 184, 235, 0.5);
        }

        .btn-secondary {
            background: transparent;
            color: #7ab8eb;
            border: 2px solid #7ab8eb;
        }

        .btn-secondary:hover {
            background: rgba(122, 184, 235, 0.15);
            transform: translateY(-5px);
            box-shadow: 0 10px 30px rgba(122, 184, 235, 0.2);
        }

        .scroll-indicator {
            position: absolute;
            bottom: 40px;
            left: 50%;
            transform: translateX(-50%);
            animation: bounce 2s infinite;
            font-size: 28px;
            color: #7ab8eb;
            cursor: pointer;
        }

        @keyframes bounce {
            0%, 20%, 50%, 80%, 100% {
                transform: translateX(-50%) translateY(0);
            }
            40% {
                transform: translateX(-50%) translateY(-15px);
            }
            60% {
                transform: translateX(-50%) translateY(-8px);
            }
        }

        .floating-elements {
            position: absolute;
            width: 100%;
            height: 100%;
            pointer-events: none;
        }

        .float {
            position: absolute;
            opacity: 0.1;
            animation: floating 20s infinite ease-in-out;
        }

        .float1 {
            width: 80px;
            height: 80px;
            background: #7ab8eb;
            border-radius: 50%;
            top: 20%;
            left: 10%;
            animation-delay: 0s;
        }

        .float2 {
            width: 60px;
            height: 60px;
            background: #5a9dd5;
            border-radius: 50%;
            top: 60%;
            right: 15%;
            animation-delay: 5s;
        }

        .float3 {
            width: 100px;
            height: 100px;
            background: #7ab8eb;
            border-radius: 50%;
            bottom: 20%;
            left: 20%;
            animation-delay: 10s;
        }

        @keyframes floating {
            0%, 100% {
                transform: translate(0, 0) scale(1);
            }
            33% {
                transform: translate(30px, -30px) scale(1.1);
            }
            66% {
                transform: translate(-20px, 20px) scale(0.9);
            }
        }

        footer {
            position: absolute;
            bottom: 0;
            width: 100%;
            padding: 20px;
            text-align: center;
            background: rgba(10, 22, 40, 0.5);
            backdrop-filter: blur(10px);
            z-index: 100;
        }

        footer p {
            color: #8fa9c4;
            font-size: 14px;
            margin: 5px 0;
        }

        @media (max-width: 768px) {
            header {
                padding: 20px 25px;
                flex-direction: column;
                gap: 15px;
            }

            .logo {
                font-size: 24px;
            }

            nav {
                gap: 20px;
                flex-wrap: wrap;
                justify-content: center;
            }

            nav a {
                font-size: 14px;
            }

            .hero h1 {
                font-size: 48px;
            }

            .hero p {
                font-size: 20px;
            }

            .btn {
                padding: 14px 35px;
                font-size: 16px;
            }

            .cta-buttons {
                gap: 15px;
            }
        }

        @media (max-width: 480px) {
            .hero h1 {
                font-size: 36px;
            }

            .hero p {
                font-size: 18px;
            }

            .cta-buttons {
                flex-direction: column;
                width: 100%;
                padding: 0 20px;
            }

            .btn {
                width: 100%;
            }
        }
    </style>
</head>
<body>
    <header>
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
        <div class="floating-elements">
            <div class="float float1"></div>
            <div class="float float2"></div>
            <div class="float float3"></div>
        </div>
        <div class="rain-container" id="rainContainer"></div>
        <div class="hero-content">
            <h1>Rainy Days</h1>
            <p>Leave a drop. Read the rain.</p>
            <div class="cta-buttons">
                <button class="btn btn-primary">Write a Raindrop</button>
                <button class="btn btn-secondary">Read The Rain</button>
            </div>
        </div>
        <div class="scroll-indicator">↓</div>
    </section>

    <footer>
        <p>© 2023 Rainy Days</p>
        <p style="font-style: italic;">"Leave a drop. Read a dream. Feel the rain."</p>
    </footer>

    <script>
        // Rain animation
        const rainContainer = document.getElementById('rainContainer');
        for (let i = 0; i < 80; i++) {
            const drop = document.createElement('div');
            drop.className = 'raindrop';
            drop.style.left = Math.random() * 100 + '%';
            drop.style.animationDuration = (Math.random() * 1 + 0.5) + 's';
            drop.style.animationDelay = Math.random() * 3 + 's';
            rainContainer.appendChild(drop);
        }
    </script>
</body>
</html>
