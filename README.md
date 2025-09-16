<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>LunarGrove - Celestial Pixel Adventure</title>
    <link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.4.0/css/all.min.css">
    <style>
        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
        }

        :root {
            --dark-purple: #2d1b69;
            --purple: #6a5acd;
            --light-purple: #9370db;
            --moon-glow: #e6e6fa;
            --silver: #c0c0c0;
            --gold: #ffd700;
            --deep-blue: #191970;
            --midnight: #0a0a23;
            --star-white: #f8f8ff;
        }

        body {
            font-family: 'Arial Rounded MT Bold', 'Comic Sans MS', sans-serif;
            background: linear-gradient(135deg, var(--midnight) 0%, var(--deep-blue) 100%);
            color: var(--star-white);
            line-height: 1.6;
            overflow-x: hidden;
            background-image: 
                radial-gradient(2px 2px at 20px 30px, var(--star-white), transparent),
                radial-gradient(2px 2px at 40px 70px, rgba(255,255,255,0.5), transparent),
                radial-gradient(1px 1px at 90px 40px, var(--star-white), transparent),
                radial-gradient(1px 1px at 130px 80px, rgba(255,255,255,0.5), transparent),
                radial-gradient(2px 2px at 160px 30px, var(--star-white), transparent);
            background-size: 200px 200px;
            animation: twinkle 4s ease-in-out infinite alternate;
        }

        @keyframes twinkle {
            0% { background-position: 0 0; }
            100% { background-position: 20px 20px; }
        }

        .container {
            max-width: 1200px;
            margin: 0 auto;
            padding: 0 20px;
        }

        /* Header & Navigation */
        header {
            background: rgba(10, 10, 35, 0.95);
            backdrop-filter: blur(10px);
            position: fixed;
            width: 100%;
            z-index: 1000;
            border-bottom: 2px solid var(--purple);
            box-shadow: 0 4px 20px rgba(0, 0, 0, 0.3);
        }

        nav {
            display: flex;
            justify-content: space-between;
            align-items: center;
            padding: 15px 0;
        }

        .logo {
            display: flex;
            align-items: center;
            gap: 12px;
            font-size: 1.8rem;
            font-weight: 700;
            color: var(--moon-glow);
            text-decoration: none;
        }

        .logo-icon {
            width: 45px;
            height: 45px;
            background: linear-gradient(45deg, var(--purple), var(--light-purple));
            border-radius: 50%;
            display: flex;
            align-items: center;
            justify-content: center;
            font-size: 1.5rem;
            color: var(--moon-glow);
            border: 2px solid var(--silver);
            box-shadow: 0 0 15px var(--purple);
        }

        .nav-links {
            display: flex;
            gap: 30px;
        }

        .nav-links a {
            color: var(--moon-glow);
            text-decoration: none;
            font-weight: 600;
            font-size: 1.1rem;
            transition: all 0.3s ease;
            padding: 8px 16px;
            border-radius: 20px;
        }

        .nav-links a:hover {
            background: var(--purple);
            color: var(--moon-glow);
            transform: translateY(-2px);
            box-shadow: 0 0 15px var(--purple);
        }

        .cta-button {
            background: linear-gradient(45deg, var(--purple), var(--light-purple));
            color: var(--moon-glow);
            border: none;
            padding: 12px 24px;
            border-radius: 30px;
            font-weight: 700;
            font-size: 1.1rem;
            cursor: pointer;
            transition: all 0.3s ease;
            box-shadow: 0 0 15px var(--purple);
            border: 2px solid var(--silver);
        }

        .cta-button:hover {
            transform: translateY(-3px) scale(1.05);
            box-shadow: 0 0 25px var(--light-purple);
        }

        /* Hero Section */
        .hero {
            padding: 180px 0 80px;
            text-align: center;
            position: relative;
            overflow: hidden;
        }

        .moon {
            position: absolute;
            top: 10%;
            right: 10%;
            width: 120px;
            height: 120px;
            background: radial-gradient(circle, var(--moon-glow) 0%, var(--silver) 70%);
            border-radius: 50%;
            box-shadow: 0 0 50px var(--moon-glow);
            animation: float 6s ease-in-out infinite;
        }

        .hero h1 {
            font-size: 4rem;
            margin-bottom: 20px;
            color: var(--moon-glow);
            text-shadow: 0 0 20px var(--purple), 0 0 30px var(--light-purple);
            letter-spacing: -1px;
        }

        .hero p {
            font-size: 1.4rem;
            color: var(--moon-glow);
            max-width: 700px;
            margin: 0 auto 40px;
            font-weight: 500;
            text-shadow: 0 0 10px rgba(106, 90, 205, 0.5);
        }

        .hero-buttons {
            display: flex;
            gap: 25px;
            justify-content: center;
            margin-bottom: 50px;
            flex-wrap: wrap;
        }

        .secondary-button {
            background: linear-gradient(45deg, var(--deep-blue), var(--purple));
            color: var(--moon-glow);
            border: 2px solid var(--silver);
            padding: 12px 24px;
            border-radius: 30px;
            font-weight: 700;
            font-size: 1.1rem;
            cursor: pointer;
            transition: all 0.3s ease;
            box-shadow: 0 0 15px var(--deep-blue);
        }

        .secondary-button:hover {
            transform: translateY(-3px) scale(1.05);
            box-shadow: 0 0 25px var(--purple);
        }

        .support-button {
            background: linear-gradient(45deg, var(--gold), var(--silver));
            color: var(--midnight);
            border: 2px solid var(--gold);
            padding: 12px 24px;
            border-radius: 30px;
            font-weight: 700;
            font-size: 1.1rem;
            cursor: pointer;
            transition: all 0.3s ease;
            box-shadow: 0 0 15px var(--gold);
        }

        .support-button:hover {
            transform: translateY(-3px) scale(1.05);
            box-shadow: 0 0 25px var(--gold);
        }

        .hero-image {
            max-width: 800px;
            margin: 0 auto;
            border-radius: 20px;
            overflow: hidden;
            box-shadow: 0 0 30px var(--purple);
            border: 3px solid var(--silver);
            position: relative;
        }

        .hero-image::before {
            content: "";
            position: absolute;
            top: -5px;
            left: -5px;
            right: -5px;
            bottom: -5px;
            background: linear-gradient(45deg, var(--purple), var(--light-purple), var(--moon-glow));
            border-radius: 25px;
            z-index: -1;
        }

        .hero-image img {
            width: 100%;
            height: auto;
            display: block;
        }

        /* Decorative Elements */
        .decoration {
            position: absolute;
            font-size: 2rem;
            opacity: 0.7;
            animation: float 3s ease-in-out infinite;
        }

        @keyframes float {
            0%, 100% { transform: translateY(0px); }
            50% { transform: translateY(-10px); }
        }

        .decoration-1 { top: 20%; left: 10%; animation-delay: 0s; }
        .decoration-2 { top: 30%; right: 15%; animation-delay: 0.5s; }
        .decoration-3 { bottom: 20%; left: 20%; animation-delay: 1s; }
        .decoration-4 { bottom: 30%; right: 10%; animation-delay: 1.5s; }

        /* Sections */
        section {
            padding: 100px 0;
            position: relative;
        }

        .section-header {
            text-align: center;
            margin-bottom: 60px;
            position: relative;
        }

        .section-header h2 {
            font-size: 3rem;
            color: var(--moon-glow);
            margin-bottom: 15px;
            text-shadow: 0 0 20px var(--purple);
        }

        .section-header p {
            color: var(--moon-glow);
            font-size: 1.3rem;
            max-width: 600px;
            margin: 0 auto;
            font-weight: 500;
        }

        /* Art Gallery */
        #art {
            background: linear-gradient(135deg, var(--deep-blue) 0%, var(--midnight) 100%);
        }

        .art-grid {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(280px, 1fr));
            gap: 30px;
        }

        .art-card {
            background: rgba(45, 27, 105, 0.7);
            border-radius: 20px;
            overflow: hidden;
            transition: all 0.4s ease;
            border: 2px solid var(--silver);
            box-shadow: 0 0 20px var(--purple);
            position: relative;
        }

        .art-card:hover {
            transform: translateY(-15px) rotate(2deg);
            box-shadow: 0 0 30px var(--light-purple);
            border-color: var(--gold);
        }

        .art-image {
            width: 100%;
            height: 250px;
            object-fit: cover;
            border-bottom: 2px solid var(--purple);
        }

        .art-info {
            padding: 20px;
            text-align: center;
        }

        .art-info h3 {
            font-size: 1.4rem;
            color: var(--moon-glow);
            margin-bottom: 8px;
            text-shadow: 0 0 10px var(--purple);
        }

        .art-category {
            color: var(--moon-glow);
            font-weight: 600;
            font-size: 1rem;
            background: rgba(106, 90, 205, 0.3);
            display: inline-block;
            padding: 4px 12px;
            border-radius: 15px;
            border: 1px solid var(--purple);
        }

        /* Gameplay Snippets */
        #gameplay {
            background: linear-gradient(135deg, var(--midnight) 0%, var(--deep-blue) 100%);
        }

        .gameplay-grid {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(350px, 1fr));
            gap: 30px;
        }

        .gameplay-card {
            background: rgba(25, 25, 112, 0.7);
            border-radius: 20px;
            overflow: hidden;
            transition: all 0.4s ease;
            border: 2px solid var(--silver);
            box-shadow: 0 0 20px var(--deep-blue);
            position: relative;
        }

        .gameplay-card:hover {
            transform: translateY(-15px) rotate(-1deg);
            box-shadow: 0 0 30px var(--purple);
            border-color: var(--gold);
        }

        .gameplay-video {
            width: 100%;
            height: 250px;
            background: linear-gradient(45deg, var(--deep-blue), var(--purple));
            display: flex;
            align-items: center;
            justify-content: center;
            color: var(--moon-glow);
            font-size: 3rem;
            border-bottom: 2px solid var(--purple);
        }

        .gameplay-info {
            padding: 20px;
        }

        .gameplay-info h3 {
            font-size: 1.4rem;
            color: var(--moon-glow);
            margin-bottom: 10px;
            text-shadow: 0 0 10px var(--purple);
        }

        .gameplay-info p {
            color: var(--moon-glow);
            font-size: 1rem;
        }

        /* Support Section */
        #support {
            background: linear-gradient(135deg, var(--deep-blue) 0%, var(--midnight) 100%);
            text-align: center;
        }

        .support-content {
            max-width: 800px;
            margin: 0 auto;
        }

        .support-content h2 {
            font-size: 3rem;
            color: var(--moon-glow);
            margin-bottom: 20px;
            text-shadow: 0 0 20px var(--gold);
        }

        .support-content p {
            font-size: 1.3rem;
            color: var(--moon-glow);
            margin-bottom: 40px;
            font-weight: 500;
        }

        .support-options {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(250px, 1fr));
            gap: 30px;
            margin-top: 50px;
        }

        .support-option {
            background: rgba(45, 27, 105, 0.7);
            border-radius: 20px;
            padding: 30px;
            border: 2px solid var(--silver);
            box-shadow: 0 0 20px var(--purple);
            position: relative;
            transition: all 0.3s ease;
        }

        .support-option:hover {
            transform: translateY(-10px);
            box-shadow: 0 0 30px var(--light-purple);
            border-color: var(--gold);
        }

        .support-icon {
            font-size: 3rem;
            margin-bottom: 20px;
            color: var(--gold);
            text-shadow: 0 0 15px var(--gold);
        }

        .support-option h3 {
            font-size: 1.5rem;
            color: var(--moon-glow);
            margin-bottom: 15px;
            text-shadow: 0 0 10px var(--purple);
        }

        .support-option p {
            color: var(--moon-glow);
            font-size: 1rem;
            margin-bottom: 20px;
        }

        .support-price {
            font-size: 1.8rem;
            font-weight: 700;
            color: var(--gold);
            margin-bottom: 20px;
            text-shadow: 0 0 10px var(--gold);
        }

        /* Footer */
        footer {
            background: linear-gradient(135deg, var(--purple) 0%, var(--deep-blue) 100%);
            padding: 60px 0 30px;
            color: var(--moon-glow);
            text-align: center;
            border-top: 2px solid var(--silver);
        }

        .footer-content {
            display: flex;
            flex-direction: column;
            align-items: center;
            gap: 30px;
            margin-bottom: 40px;
        }

        .footer-logo {
            display: flex;
            align-items: center;
            gap: 12px;
            font-size: 2rem;
            font-weight: 700;
        }

        .social-links {
            display: flex;
            gap: 25px;
        }

        .social-link {
            color: var(--moon-glow);
            font-size: 1.8rem;
            transition: all 0.3s ease;
            width: 50px;
            height: 50px;
            border-radius: 50%;
            display: flex;
            align-items: center;
            justify-content: center;
            background: rgba(255, 255, 255, 0.1);
            border: 1px solid var(--silver);
        }

        .social-link:hover {
            background: var(--gold);
            color: var(--midnight);
            transform: translateY(-5px);
            box-shadow: 0 0 15px var(--gold);
        }

        .copyright {
            text-align: center;
            color: var(--moon-glow);
            padding-top: 30px;
            border-top: 1px solid var(--silver);
            font-weight: 500;
        }

        /* Responsive */
        @media (max-width: 768px) {
            .nav-links {
                display: none;
            }

            .hero h1 {
                font-size: 2.8rem;
            }

            .hero p {
                font-size: 1.1rem;
            }

            .hero-buttons {
                flex-direction: column;
                align-items: center;
                gap: 15px;
            }

            .gameplay-grid {
                grid-template-columns: 1fr;
            }

            .section-header h2 {
                font-size: 2.2rem;
            }
            
            .moon {
                display: none;
            }
        }

        /* Pixel Art Style */
        .pixel-border {
            image-rendering: pixelated;
            image-rendering: -moz-crisp-edges;
            image-rendering: crisp-edges;
        }
    </style>
</head>
<body>
    <!-- Decorative Elements -->
    <div class="decoration decoration-1">🌙</div>
    <div class="decoration decoration-2">⭐</div>
    <div class="decoration decoration-3">✨</div>
    <div class="decoration decoration-4">🌙</div>
    <div class="moon"></div>

    <!-- Header -->
    <header>
        <div class="container">
            <nav>
                <a href="#" class="logo">
                    <div class="logo-icon">🌙</div>
                    <span>LunarGrove</span>
                </a>
                <div class="nav-links">
                    <a href="#home">Home</a>
                    <a href="#art">Art Gallery</a>
                    <a href="#gameplay">Gameplay</a>
                    <a href="#support">Support Me</a>
                </div>
                <button class="cta-button">
                    <i class="fas fa-play"></i> Play Demo
                </button>
            </nav>
        </div>
    </header>

    <!-- Hero Section -->
    <section class="hero" id="home">
        <div class="container">
            <h1>Welcome to LunarGrove! 🌙</h1>
            <p>A celestial pixel adventure where you cultivate enchanted lunar gardens, befriend mystical moon creatures, and uncover ancient cosmic secrets!</p>
            <div class="hero-buttons">
                <button class="cta-button">
                    <i class="fas fa-download"></i> Download Demo
                </button>
                <button class="secondary-button">
                    <i class="fas fa-film"></i> Watch Trailer
                </button>
                <button class="support-button">
                    <i class="fas fa-heart"></i> Support Me
                </button>
            </div>
            <div class="hero-image">
                <img src="https://placehold.co/800x450/191970/e6e6fa?text=LunarGrove+Gameplay" alt="Game Screenshot" class="pixel-border">
            </div>
        </div>
    </section>

    <!-- Art Gallery Section -->
    <section id="art">
        <div class="container">
            <div class="section-header">
                <h2>🎨 Celestial Art Gallery 🎨</h2>
                <p>Our enchanting lunar-themed pixel art collection</p>
            </div>
            <div class="art-grid">
                <div class="art-card">
                    <img src="https://placehold.co/400x300/2d1b69/e6e6fa?text=Lunar+Character" alt="Character Design" class="art-image pixel-border">
                    <div class="art-info">
                        <h3>Moon Guardian Designs</h3>
                        <div class="art-category">Characters</div>
                    </div>
                </div>
                <div class="art-card">
                    <img src="https://placehold.co/400x300/6a5acd/e6e6fa?text=Lunar+Environment" alt="Environment Concept" class="art-image pixel-border">
                    <div class="art-info">
                        <h3>Cosmic Environments</h3>
                        <div class="art-category">Environments</div>
                    </div>
                </div>
                <div class="art-card">
                    <img src="https://placehold.co/400x300/9370db/e6e6fa?text=UI+Design" alt="UI Mockup" class="art-image pixel-border">
                    <div class="art-info">
                        <h3>Ethereal UI Design</h3>
                        <div class="art-category">UI/UX</div>
                    </div>
                </div>
                <div class="art-card">
                    <img src="https://placehold.co/400x300/c0c0c0/2d1b69?text=Magical+Items" alt="Item Design" class="art-image pixel-border">
                    <div class="art-info">
                        <h3>Enchanted Item Art</h3>
                        <div class="art-category">Items</div>
                    </div>
                </div>
            </div>
        </div>
    </section>

    <!-- Gameplay Snippets Section -->
    <section id="gameplay">
        <div class="container">
            <div class="section-header">
                <h2>🎮 Lunar Gameplay 🎮</h2>
                <p>Experience the magic of LunarGrove</p>
            </div>
            <div class="gameplay-grid">
                <div class="gameplay-card">
                    <div class="gameplay-video">
                        <i class="fas fa-moon"></i>
                    </div>
                    <div class="gameplay-info">
                        <h3>Lunar Gardening</h3>
                        <p>Plant celestial seeds under the moonlight and watch them grow into magical lunar flora with unique cosmic properties.</p>
                    </div>
                </div>
                <div class="gameplay-card">
                    <div class="gameplay-video">
                        <i class="fas fa-star"></i>
                    </div>
                    <div class="gameplay-info">
                        <h3>Stellar Crafting</h3>
                        <p>Collect fallen stars and cosmic materials to craft powerful enchanted tools and beautiful decorative items.</p>
                    </div>
                </div>
                <div class="gameplay-card">
                    <div class="gameplay-video">
                        <i class="fas fa-home"></i>
                    </div>
                    <div class="gameplay-info">
                        <h3>Cosmic Cottage</h3>
                        <p>Customize your lunar sanctuary with celestial furniture and watch it glow under the phases of the moon.</p>
                    </div>
                </div>
            </div>
        </div>
    </section>

    <!-- Support Section -->
    <section id="support">
        <div class="container">
            <div class="support-content">
                <h2>🌟 Support My Cosmic Journey 🌟</h2>
                <p>Your support helps me continue creating this enchanting lunar world and brings LunarGrove closer to completion!</p>
                
                <div class="support-options">
                    <div class="support-option">
                        <div class="support-icon">
                            <i class="fas fa-moon"></i>
                        </div>
                        <h3>New Moon Supporter</h3>
                        <p>Help fuel my creative journey among the stars!</p>
                        <div class="support-price">🌙 $5
