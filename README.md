<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <meta name="description" content="Hugo's Professional Portfolio - Holberton School Student">
    <title>Hugo - Developer Portfolio</title>
    <style>
        /* ========== RESET & BASE ========== */
        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
        }

        html {
            scroll-behavior: smooth;
        }

        body {
            font-family: -apple-system, BlinkMacSystemFont, 'Segoe UI', Roboto, Oxygen, Ubuntu, Cantarell, sans-serif;
            background: linear-gradient(135deg, #0a0e27 0%, #1a1f3a 100%);
            color: #e0e0e0;
            line-height: 1.6;
            min-height: 100vh;
        }

        /* ========== ANIMATIONS ========== */
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
            0%, 100% {
                transform: translateY(0px);
            }
            50% {
                transform: translateY(-10px);
            }
        }

        @keyframes pulse {
            0%, 100% {
                opacity: 1;
            }
            50% {
                opacity: 0.7;
            }
        }

        @keyframes gradientShift {
            0% {
                background-position: 0% 50%;
            }
            50% {
                background-position: 100% 50%;
            }
            100% {
                background-position: 0% 50%;
            }
        }

        /* ========== CONTAINER & LAYOUT ========== */
        .container {
            max-width: 1200px;
            margin: 0 auto;
            padding: 60px 20px;
        }

        /* ========== TYPOGRAPHY ========== */
        h1 {
            font-size: 3.5rem;
            font-weight: 700;
            text-align: center;
            margin-bottom: 20px;
            animation: fadeInUp 0.8s ease;
        }

        .gradient-text {
            background: linear-gradient(90deg, #ff6ec4, #7873f5);
            -webkit-background-clip: text;
            -webkit-text-fill-color: transparent;
            background-clip: text;
        }

        h2 {
            font-size: 2.5rem;
            font-weight: 700;
            text-align: center;
            margin-bottom: 40px;
            animation: fadeInUp 0.8s ease;
        }

        .gradient-stats {
            background: linear-gradient(90deg, #5b5555, #d1210a);
            -webkit-background-clip: text;
            -webkit-text-fill-color: transparent;
            background-clip: text;
        }

        .gradient-tech {
            background: linear-gradient(90deg, #ff6ec4, #4bc921);
            -webkit-background-clip: text;
            -webkit-text-fill-color: transparent;
            background-clip: text;
        }

        .gradient-projects {
            background: linear-gradient(90deg, #1ee2fc, #9e35a7);
            -webkit-background-clip: text;
            -webkit-text-fill-color: transparent;
            background-clip: text;
        }

        .gradient-connect {
            background: linear-gradient(90deg, #333d86, #9fd02c);
            -webkit-background-clip: text;
            -webkit-text-fill-color: transparent;
            background-clip: text;
        }

        p {
            font-size: 1.1rem;
            text-align: center;
            animation: fadeInUp 1s ease;
        }

        /* ========== SECTION DIVIDER ========== */
        hr {
            border: none;
            height: 2px;
            background: linear-gradient(90deg, transparent, #4bc921, transparent);
            margin: 80px 0;
            opacity: 0.5;
        }

        /* ========== QUOTE SECTION ========== */
        .quote-section {
            text-align: center;
            margin: 50px 0;
            padding: 30px 20px;
            border-left: 4px solid #ff6ec4;
            border-right: 4px solid #7873f5;
            border-radius: 8px;
            background: rgba(120, 115, 245, 0.05);
            animation: fadeInUp 1.2s ease;
        }

        .quote-section q {
            display: block;
            font-size: 1.2rem;
            color: #7873f5;
            font-style: italic;
            margin-bottom: 10px;
            quotes: none;
        }

        .quote-section q::before {
            content: '"';
            color: #ff6ec4;
        }

        .quote-section q::after {
            content: '"';
            color: #ff6ec4;
        }

        .quote-author {
            color: #b0b0b0;
            font-size: 0.95rem;
            font-style: italic;
        }

        /* ========== SUBTITLE ========== */
        .subtitle {
            font-size: 1rem;
            color: #c0c0c0;
            margin-bottom: 15px;
            animation: fadeInUp 0.9s ease;
        }

        /* ========== GITHUB STATS ========== */
        .stats-container {
            display: flex;
            justify-content: center;
            gap: 20px;
            flex-wrap: wrap;
            margin-bottom: 40px;
            animation: fadeInUp 1.4s ease;
        }

        .stat-card {
            border-radius: 12px;
            overflow: hidden;
            transition: transform 0.3s ease, box-shadow 0.3s ease;
            box-shadow: 0 4px 20px rgba(255, 110, 196, 0.2);
        }

        .stat-card:hover {
            transform: translateY(-5px);
            box-shadow: 0 8px 30px rgba(255, 110, 196, 0.4);
        }

        .stat-card img {
            width: 100%;
            height: auto;
            display: block;
            max-width: 400px;
            background: rgba(30, 226, 252, 0.1);
            min-height: 200px;
        }

        /* ========== TECHNOLOGIES ========== */
        .tech-container {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(150px, 1fr));
            gap: 40px;
            max-width: 600px;
            margin: 0 auto 40px;
            animation: fadeInUp 1.5s ease;
        }

        .tech-item {
            display: flex;
            flex-direction: column;
            align-items: center;
            gap: 15px;
            text-align: center;
        }

        .tech-icon {
            width: 100px;
            height: 100px;
            display: flex;
            align-items: center;
            justify-content: center;
            background: rgba(255, 110, 196, 0.1);
            border: 2px solid #ff6ec4;
            border-radius: 16px;
            animation: float 3s ease-in-out infinite;
            transition: all 0.3s ease;
        }

        .tech-item:nth-child(1) .tech-icon {
            animation-delay: 0s;
        }

        .tech-item:nth-child(2) .tech-icon {
            animation-delay: 0.5s;
        }

        .tech-item:nth-child(3) .tech-icon {
            animation-delay: 1s;
        }

        .tech-item:nth-child(4) .tech-icon {
            animation-delay: 1.5s;
        }

        .tech-icon:hover {
            transform: scale(1.1);
            border-color: #7873f5;
            background: rgba(120, 115, 245, 0.1);
        }

        .tech-icon img {
            width: 70%;
            height: 70%;
            object-fit: contain;
            filter: drop-shadow(0 0 8px rgba(255, 110, 196, 0.5));
        }

        .tech-label {
            font-size: 0.95rem;
            font-weight: 600;
            color: #e0e0e0;
        }

        /* ========== PROJECTS ========== */
        .projects-list {
            display: flex;
            flex-direction: column;
            gap: 15px;
            max-width: 600px;
            margin: 0 auto 40px;
            list-style: none;
            animation: fadeInUp 1.6s ease;
        }

        .project-item {
            padding: 20px 25px;
            background: rgba(30, 226, 252, 0.08);
            border-left: 4px solid #1ee2fc;
            border-radius: 8px;
            font-size: 1.05rem;
            transition: all 0.3s ease;
            animation: pulse 2s ease-in-out infinite;
            cursor: pointer;
        }

        .project-item:hover {
            background: rgba(30, 226, 252, 0.15);
            transform: translateX(10px);
        }

        .project-item:nth-child(2) {
            animation-delay: 0.3s;
            border-left-color: #9e35a7;
            background: rgba(158, 53, 167, 0.08);
        }

        .project-item:nth-child(2):hover {
            background: rgba(158, 53, 167, 0.15);
        }

        .project-item:nth-child(3) {
            animation-delay: 0.6s;
            border-left-color: #1ee2fc;
        }

        /* ========== SOCIAL LINKS ========== */
        .social-container {
            display: flex;
            justify-content: center;
            gap: 30px;
            flex-wrap: wrap;
            margin: 40px 0;
            animation: fadeInUp 1.7s ease;
        }

        .social-link {
            display: inline-block;
            transition: transform 0.3s ease;
            text-decoration: none;
        }

        .social-link:hover {
            transform: scale(1.12);
        }

        .social-link img {
            height: 50px;
            width: auto;
            display: block;
        }

        /* ========== FOOTER ========== */
        .footer {
            text-align: center;
            color: #a0a0a0;
            font-size: 1.1rem;
            margin-top: 80px;
            padding-top: 40px;
            border-top: 1px solid rgba(75, 201, 33, 0.3);
            animation: fadeInUp 1.8s ease;
        }

        /* ========== RESPONSIVE ========== */
        @media (max-width: 768px) {
            h1 {
                font-size: 2.5rem;
            }

            h2 {
                font-size: 1.8rem;
                margin-bottom: 30px;
            }

            p {
                font-size: 1rem;
            }

            .container {
                padding: 40px 15px;
            }

            hr {
                margin: 60px 0;
            }

            .tech-container {
                grid-template-columns: repeat(auto-fit, minmax(120px, 1fr));
                gap: 25px;
            }

            .tech-icon {
                width: 80px;
                height: 80px;
            }

            .stat-card img {
                max-width: 100%;
            }

            .social-container {
                gap: 20px;
            }
        }

        @media (max-width: 480px) {
            h1 {
                font-size: 2rem;
            }

            h2 {
                font-size: 1.5rem;
            }

            .subtitle {
                font-size: 0.9rem;
            }

            .quote-section q {
                font-size: 1rem;
            }

            .tech-container {
                grid-template-columns: repeat(2, 1fr);
            }
        }
    </style>
</head>
<body>
    <div class="container">
        <!-- HEADER SECTION -->
        <header>
            <h1><span class="gradient-text">Hi, I'm Hugo 👋</span></h1>
            <p class="subtitle">🎓 Holberton School | 💻 Programming, Cybersecurity, 3D & Game Development | 🎯 Goal: Improve my skills</p>
        </header>

        <!-- QUOTE SECTION -->
        <section class="quote-section">
            <q>Knowing is not enough, we must apply. Willing is not enough, we must do.</q>
            <p class="quote-author">– Bruce Lee</p>
        </section>

        <hr>

        <!-- GITHUB STATS SECTION -->
        <section>
            <h2 class="gradient-stats">GitHub Stats 👨‍💻</h2>
            <div class="stats-container">
                <div class="stat-card">
                    <img src="https://github-profile-summary-cards.vercel.app/api/cards/profile-details?username=hugou74130&theme=radical" alt="Profile Details">
                </div>
            </div>
            <div class="stats-container">
                <div class="stat-card">
                    <img src="https://github-profile-summary-cards.vercel.app/api/cards/repos-per-language?username=hugou74130&theme=radical" alt="Repos per Language">
                </div>
                <div class="stat-card">
                    <img src="https://github-profile-summary-cards.vercel.app/api/cards/most-commit-language?username=hugou74130&theme=radical" alt="Commits per Language">
                </div>
            </div>
            <div class="stats-container">
                <div class="stat-card">
                    <img src="https://github-profile-summary-cards.vercel.app/api/cards/stats?username=hugou74130&theme=radical" alt="Stats">
                </div>
                <div class="stat-card">
                    <img src="https://github-profile-summary-cards.vercel.app/api/cards/productive-time?username=hugou74130&theme=radical&utcOffset=1" alt="Productive Time">
                </div>
            </div>
        </section>

        <hr>

        <!-- TECHNOLOGIES SECTION -->
        <section>
            <h2 class="gradient-tech">🔧 Technologies I'm learning</h2>
            <div class="tech-container">
                <div class="tech-item">
                    <div class="tech-icon">
                        <img src="https://cdn.worldvectorlogo.com/logos/python-5.svg" alt="Python">
                    </div>
                    <span class="tech-label">Python</span>
                </div>
                <div class="tech-item">
                    <div class="tech-icon">
                        <img src="https://cdn.worldvectorlogo.com/logos/bash-1.svg" alt="Bash">
                    </div>
                    <span class="tech-label">Bash</span>
                </div>
                <div class="tech-item">
                    <div class="tech-icon">
                        <img src="https://cdn.worldvectorlogo.com/logos/blender-2.svg" alt="Blender">
                    </div>
                    <span class="tech-label">Blender</span>
                </div>
                <div class="tech-item">
                    <div class="tech-icon">
                        <img src="https://cdn.worldvectorlogo.com/logos/c-1.svg" alt="C">
                    </div>
                    <span class="tech-label">C</span>
                </div>
            </div>
        </section>

        <hr>

        <!-- PROJECTS SECTION -->
        <section>
            <h2 class="gradient-projects">🚀 Upcoming Projects</h2>
            <ul class="projects-list">
                <li class="project-item">🤖 Automation scripts</li>
                <li class="project-item">🔐 Cybersecurity / CTF challenges</li>
                <li class="project-item">🎮 3D and game development projects</li>
            </ul>
        </section>

        <hr>

        <!-- SOCIAL SECTION -->
        <section>
            <h2 class="gradient-connect">🚀 Connect with me</h2>
            <div class="social-container">
                <a href="https://github.com/hugou74130" class="social-link" target="_blank" rel="noopener noreferrer">
                    <img src="https://img.shields.io/badge/GitHub-100000?style=for-the-badge&logo=github&logoColor=white" alt="GitHub">
                </a>
                <a href="https://www.linkedin.com/in/hugou74130/" class="social-link" target="_blank" rel="noopener noreferrer">
                    <img src="https://img.shields.io/badge/LinkedIn-0077B5?style=for-the-badge&logo=linkedin&logoColor=white" alt="LinkedIn">
                </a>
                <a href="mailto:contact@example.com" class="social-link">
                    <img src="https://img.shields.io/badge/Email-D14836?style=for-the-badge&logo=gmail&logoColor=white" alt="Email">
                </a>
            </div>
        </section>

        <!-- FOOTER -->
        <footer class="footer">
            <p>Thanks for visiting my profile! 🙌</p>
        </footer>
    </div>
</body>
</html>
