<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Ahsan Raza - AI Engineer & Full Stack Developer</title>
    <link href="https://fonts.googleapis.com/css2?family=Fira+Code:wght@400;500;600;700&family=Inter:wght@300;400;500;600;700&display=swap" rel="stylesheet">
    <style>
        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
        }

        body {
            background: radial-gradient(ellipse at bottom, #1b2735 0%, #090a0f 100%);
            min-height: 100vh;
            overflow-x: hidden;
            font-family: 'Inter', sans-serif;
            color: #ffffff;
        }

        .night {
            position: fixed;
            top: 0;
            left: 0;
            width: 100%;
            height: 100%;
            transform: rotateZ(45deg);
            z-index: 1;
            pointer-events: none;
        }

        .shooting_star {
            position: absolute;
            left: 50%;
            top: 50%;
            height: 2px;
            background: linear-gradient(-45deg, rgba(139, 92, 246, 1), rgba(139, 92, 246, 0));
            border-radius: 999px;
            filter: drop-shadow(0 0 6px rgba(139, 92, 246, 1));
            animation: tail 3000ms ease-in-out infinite, shooting 3000ms ease-in-out infinite;
        }

        .shooting_star::before {
            content: '';
            position: absolute;
            top: calc(50% - 1px);
            right: 0;
            height: 2px;
            background: linear-gradient(-45deg, rgba(139, 92, 246, 0), rgba(139, 92, 246, 1), rgba(139, 92, 246, 0));
            transform: translateX(50%) rotateZ(45deg);
            border-radius: 100%;
            animation: shining 3000ms ease-in-out infinite;
        }

        .shooting_star::after {
            content: '';
            position: absolute;
            top: calc(50% - 1px);
            right: 0;
            height: 2px;
            background: linear-gradient(-45deg, rgba(139, 92, 246, 0), rgba(139, 92, 246, 1), rgba(139, 92, 246, 0));
            transform: translateX(50%) rotateZ(-45deg);
            border-radius: 100%;
            animation: shining 3000ms ease-in-out infinite;
        }

        .shooting_star:nth-child(1) { top: calc(50% - 150px); left: calc(50% - 200px); animation-delay: 1000ms; }
        .shooting_star:nth-child(2) { top: calc(50% - 80px); left: calc(50% - 150px); animation-delay: 2500ms; }
        .shooting_star:nth-child(3) { top: calc(50% - 200px); left: calc(50% - 100px); animation-delay: 4000ms; }
        .shooting_star:nth-child(4) { top: calc(50% - 120px); left: calc(50% - 250px); animation-delay: 1500ms; }
        .shooting_star:nth-child(5) { top: calc(50% - 90px); left: calc(50% - 180px); animation-delay: 3200ms; }
        .shooting_star:nth-child(6) { top: calc(50% - 170px); left: calc(50% - 120px); animation-delay: 800ms; }
        .shooting_star:nth-child(7) { top: calc(50% - 140px); left: calc(50% - 220px); animation-delay: 2800ms; }
        .shooting_star:nth-child(8) { top: calc(50% - 60px); left: calc(50% - 160px); animation-delay: 1800ms; }
        .shooting_star:nth-child(9) { top: calc(50% - 180px); left: calc(50% - 140px); animation-delay: 3800ms; }
        .shooting_star:nth-child(10) { top: calc(50% - 110px); left: calc(50% - 190px); animation-delay: 600ms; }
        .shooting_star:nth-child(11) { top: calc(50% - 130px); left: calc(50% - 210px); animation-delay: 2200ms; }
        .shooting_star:nth-child(12) { top: calc(50% - 70px); left: calc(50% - 170px); animation-delay: 3600ms; }
        .shooting_star:nth-child(13) { top: calc(50% - 190px); left: calc(50% - 130px); animation-delay: 1200ms; }
        .shooting_star:nth-child(14) { top: calc(50% - 100px); left: calc(50% - 240px); animation-delay: 2900ms; }
        .shooting_star:nth-child(15) { top: calc(50% - 160px); left: calc(50% - 110px); animation-delay: 400ms; }
        .shooting_star:nth-child(16) { top: calc(50% - 50px); left: calc(50% - 200px); animation-delay: 3400ms; }
        .shooting_star:nth-child(17) { top: calc(50% - 210px); left: calc(50% - 150px); animation-delay: 1600ms; }
        .shooting_star:nth-child(18) { top: calc(50% - 85px); left: calc(50% - 230px); animation-delay: 2600ms; }
        .shooting_star:nth-child(19) { top: calc(50% - 175px); left: calc(50% - 165px); animation-delay: 3000ms; }
        .shooting_star:nth-child(20) { top: calc(50% - 125px); left: calc(50% - 185px); animation-delay: 200ms; }

        @keyframes tail {
            0% { width: 0; }
            30% { width: 100px; }
            100% { width: 0; }
        }

        @keyframes shining {
            0% { width: 0; }
            50% { width: 30px; }
            100% { width: 0; }
        }

        @keyframes shooting {
            0% { transform: translateX(0); }
            100% { transform: translateX(300px); }
        }

        .container {
            position: relative;
            z-index: 2;
            max-width: 1200px;
            margin: 0 auto;
            padding: 40px 20px;
        }

        .hero-section {
            text-align: center;
            margin-bottom: 60px;
        }

        .hero-title {
            font-size: 3.5rem;
            font-weight: 700;
            margin-bottom: 20px;
            background: linear-gradient(45deg, #8b5cf6, #3b82f6, #06b6d4);
            -webkit-background-clip: text;
            -webkit-text-fill-color: transparent;
            background-clip: text;
            animation: gradient-shift 3s ease-in-out infinite;
        }

        .hero-title .name {
            color: #8b5cf6;
            text-shadow: 0 0 20px rgba(139, 92, 246, 0.5);
        }

        .typing-animation {
            font-family: 'Fira Code', monospace;
            font-size: 1.5rem;
            font-weight: 600;
            color: #8b5cf6;
            margin-bottom: 30px;
        }

        .profile-stats {
            display: flex;
            justify-content: center;
            gap: 20px;
            margin-bottom: 40px;
            flex-wrap: wrap;
        }

        .stat-badge {
            background: rgba(139, 92, 246, 0.1);
            border: 1px solid rgba(139, 92, 246, 0.3);
            padding: 10px 20px;
            border-radius: 25px;
            backdrop-filter: blur(10px);
            transition: all 0.3s ease;
        }

        .stat-badge:hover {
            background: rgba(139, 92, 246, 0.2);
            transform: translateY(-2px);
        }

        .about-section {
            background: rgba(255, 255, 255, 0.05);
            backdrop-filter: blur(20px);
            border: 1px solid rgba(255, 255, 255, 0.1);
            border-radius: 20px;
            padding: 40px;
            margin-bottom: 40px;
        }

        .about-grid {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(300px, 1fr));
            gap: 30px;
        }

        .about-item {
            display: flex;
            align-items: center;
            gap: 15px;
            padding: 15px;
            background: rgba(139, 92, 246, 0.1);
            border-radius: 10px;
            transition: transform 0.3s ease;
        }

        .about-item:hover {
            transform: translateX(10px);
        }

        .about-icon {
            font-size: 1.5rem;
            color: #8b5cf6;
        }

        .social-section {
            text-align: center;
            margin-bottom: 40px;
        }

        .social-links {
            display: flex;
            justify-content: center;
            gap: 20px;
            flex-wrap: wrap;
            margin-bottom: 30px;
        }

        .social-link {
            display: inline-block;
            padding: 15px;
            background: rgba(139, 92, 246, 0.1);
            border-radius: 50%;
            transition: all 0.3s ease;
            border: 2px solid transparent;
        }

        .social-link:hover {
            background: rgba(139, 92, 246, 0.2);
            border-color: #8b5cf6;
            transform: scale(1.1);
        }

        .tech-section {
            margin-bottom: 40px;
        }

        .section-title {
            font-size: 2.5rem;
            font-weight: 700;
            text-align: center;
            margin-bottom: 30px;
            color: #8b5cf6;
        }

        .tech-grid {
            display: grid;
            grid-template-columns: repeat(auto-fill, minmax(80px, 1fr));
            gap: 20px;
            justify-items: center;
        }

        .tech-item {
            width: 60px;
            height: 60px;
            background: rgba(255, 255, 255, 0.1);
            border-radius: 10px;
            display: flex;
            align-items: center;
            justify-content: center;
            transition: all 0.3s ease;
            cursor: pointer;
        }

        .tech-item:hover {
            background: rgba(139, 92, 246, 0.2);
            transform: translateY(-5px);
        }

        .stats-section {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(300px, 1fr));
            gap: 30px;
            margin-bottom: 40px;
        }

        .stat-card {
            background: rgba(255, 255, 255, 0.05);
            backdrop-filter: blur(20px);
            border: 1px solid rgba(255, 255, 255, 0.1);
            border-radius: 15px;
            padding: 20px;
            text-align: center;
            transition: transform 0.3s ease;
        }

        .stat-card:hover {
            transform: translateY(-5px);
        }

        .footer {
            text-align: center;
            padding: 40px 0;
            border-top: 1px solid rgba(255, 255, 255, 0.1);
            margin-top: 40px;
        }

        .gradient-text {
            background: linear-gradient(45deg, #8b5cf6, #3b82f6);
            -webkit-background-clip: text;
            -webkit-text-fill-color: transparent;
            background-clip: text;
        }

        @keyframes gradient-shift {
            0%, 100% { background-position: 0% 50%; }
            50% { background-position: 100% 50%; }
        }

        @media (max-width: 768px) {
            .hero-title {
                font-size: 2.5rem;
            }
            
            .typing-animation {
                font-size: 1.2rem;
            }
            
            .container {
                padding: 20px 10px;
            }
        }
    </style>
</head>
<body>
    <div class="night">
        <div class="shooting_star"></div>
        <div class="shooting_star"></div>
        <div class="shooting_star"></div>
        <div class="shooting_star"></div>
        <div class="shooting_star"></div>
        <div class="shooting_star"></div>
        <div class="shooting_star"></div>
        <div class="shooting_star"></div>
        <div class="shooting_star"></div>
        <div class="shooting_star"></div>
        <div class="shooting_star"></div>
        <div class="shooting_star"></div>
        <div class="shooting_star"></div>
        <div class="shooting_star"></div>
        <div class="shooting_star"></div>
        <div class="shooting_star"></div>
        <div class="shooting_star"></div>
        <div class="shooting_star"></div>
        <div class="shooting_star"></div>
        <div class="shooting_star"></div>
    </div>

    <div class="container">
        <div class="hero-section">
            <h1 class="hero-title">Hi, I'm <span class="name">Ahsan Raza</span> 👋</h1>
            <div class="typing-animation" id="typing-text">Solutions Architect</div>
            
            <div class="profile-stats">
                <div class="stat-badge">
                    <img src="https://komarev.com/ghpvc/?username=ahsan3219&label=Profile%20views&color=8b5cf6&style=flat" alt="Profile views" />
                </div>
                <div class="stat-badge">
                    <img src="https://github-profile-trophy.vercel.app/?username=ahsan3219&theme=darkhub&no-frame=true&column=3" alt="GitHub Trophies" />
                </div>
            </div>
        </div>

        <div class="about-section">
            <h2 class="section-title">About Me</h2>
            <div class="about-grid">
                <div class="about-item">
                    <div class="about-icon">🔭</div>
                    <div>
                        <strong>Currently Working:</strong> 
                        <a href="https://www.upwork.com/freelancers/ahsanai" target="_blank" style="color: #8b5cf6;">Upwork</a>
                    </div>
                </div>
                <div class="about-item">
                    <div class="about-icon">🌱</div>
                    <div><strong>Learning:</strong> Metaverse, Blockchain, and Web 3.0</div>
                </div>
                <div class="about-item">
                    <div class="about-icon">👯</div>
                    <div><strong>Collaborating on:</strong> AGI and LLM Marketplace</div>
                </div>
                <div class="about-item">
                    <div class="about-icon">👨‍💻</div>
                    <div>
                        <strong>Portfolio:</strong> 
                        <a href="https://ahsanai.netlify.app/" target="_blank" style="color: #8b5cf6;">ahsanai.netlify.app</a>
                    </div>
                </div>
                <div class="about-item">
                    <div class="about-icon">💬</div>
                    <div><strong>Ask me about:</strong> Generative AI, LLM, Gemini-2.5 pro, GROK-4, Kimi-k2, Huggingface</div>
                </div>
                <div class="about-item">
                    <div class="about-icon">📫</div>
                    <div>
                        <strong>Email:</strong> 
                        <a href="mailto:ahsanrazasyedahsan@gmail.com" style="color: #8b5cf6;">ahsanrazasyedahsan@gmail.com</a>
                    </div>
                </div>
                <div class="about-item">
                    <div class="about-icon">⚡</div>
                    <div><strong>Hobbies:</strong> Exploring the World of Technology</div>
                </div>
            </div>
        </div>

        <div class="social-section">
            <h2 class="section-title">Connect with Me</h2>
            <div class="social-links">
                <a href="https://linkedin.com/in/ahsanai" target="_blank" class="social-link">
                    <img src="https://raw.githubusercontent.com/rahuldkjain/github-profile-readme-generator/master/src/images/icons/Social/linked-in-alt.svg" alt="LinkedIn" height="30" width="30" />
                </a>
                <a href="https://stackoverflow.com/users/12052840/ahsan-raza-syed-ahsan" target="_blank" class="social-link">
                    <img src="https://raw.githubusercontent.com/rahuldkjain/github-profile-readme-generator/master/src/images/icons/Social/stack-overflow.svg" alt="Stack Overflow" height="30" width="30" />
                </a>
                <a href="https://kaggle.com/ahsanraza1" target="_blank" class="social-link">
                    <img src="https://raw.githubusercontent.com/rahuldkjain/github-profile-readme-generator/master/src/images/icons/Social/kaggle.svg" alt="Kaggle" height="30" width="30" />
                </a>
                <a href="https://www.behance.net/ahsan3219" target="_blank" class="social-link">
                    <img src="https://raw.githubusercontent.com/rahuldkjain/github-profile-readme-generator/master/src/images/icons/Social/behance.svg" alt="Behance" height="30" width="30" />
                </a>
                <a href="https://medium.com/@ahsanrazasyedahsan" target="_blank" class="social-link">
                    <img src="https://raw.githubusercontent.com/rahuldkjain/github-profile-readme-generator/master/src/images/icons/Social/medium.svg" alt="Medium" height="30" width="30" />
                </a>
                <a href="https://www.leetcode.com/ahsan3219" target="_blank" class="social-link">
                    <img src="https://raw.githubusercontent.com/rahuldkjain/github-profile-readme-generator/master/src/images/icons/Social/leet-code.svg" alt="LeetCode" height="30" width="30" />
                </a>
                <a href="https://discord.gg/ahsanai" target="_blank" class="social-link">
                    <img src="https://raw.githubusercontent.com/rahuldkjain/github-profile-readme-generator/master/src/images/icons/Social/discord.svg" alt="Discord" height="30" width="30" />
                </a>
            </div>
        </div>

        <div class="tech-section">
            <h2 class="section-title">Languages and Tools</h2>
            <div class="tech-grid">
                <div class="tech-item">
                    <img src="https://raw.githubusercontent.com/devicons/devicon/master/icons/python/python-original.svg" alt="Python" width="40" height="40"/>
                </div>
                <div class="tech-item">
                    <img src="https://raw.githubusercontent.com/devicons/devicon/master/icons/javascript/javascript-original.svg" alt="JavaScript" width="40" height="40"/>
                </div>
                <div class="tech-item">
                    <img src="https://raw.githubusercontent.com/devicons/devicon/master/icons/react/react-original-wordmark.svg" alt="React" width="40" height="40"/>
                </div>
                <div class="tech-item">
                    <img src="https://cdn.worldvectorlogo.com/logos/nextjs-2.svg" alt="Next.js" width="40" height="40"/>
                </div>
                <div class="tech-item">
                    <img src="https://raw.githubusercontent.com/devicons/devicon/master/icons/nodejs/nodejs-original-wordmark.svg" alt="Node.js" width="40" height="40"/>
                </div>
                <div class="tech-item">
                    <img src="https://www.vectorlogo.zone/logos/tensorflow/tensorflow-icon.svg" alt="TensorFlow" width="40" height="40"/>
                </div>
                <div class="tech-item">
                    <img src="https://www.vectorlogo.zone/logos/pytorch/pytorch-icon.svg" alt="PyTorch" width="40" height="40"/>
                </div>
                <div class="tech-item">
                    <img src="https://raw.githubusercontent.com/devicons/devicon/master/icons/docker/docker-original-wordmark.svg" alt="Docker" width="40" height="40"/>
                </div>
                <div class="tech-item">
                    <img src="https://raw.githubusercontent.com/devicons/devicon/master/icons/amazonwebservices/amazonwebservices-original-wordmark.svg" alt="AWS" width="40" height="40"/>
                </div>
                <div class="tech-item">
                    <img src="https://www.vectorlogo.zone/logos/google_cloud/google_cloud-icon.svg" alt="GCP" width="40" height="40"/>
                </div>
                <div class="tech-item">
                    <img src="https://www.vectorlogo.zone/logos/microsoft_azure/microsoft_azure-icon.svg" alt="Azure" width="40" height="40"/>
                </div>
                <div class="tech-item">
                    <img src="https://raw.githubusercontent.com/devicons/devicon/master/icons/mongodb/mongodb-original-wordmark.svg" alt="MongoDB" width="40" height="40"/>
                </div>
                <div class="tech-item">
                    <img src="https://raw.githubusercontent.com/devicons/devicon/master/icons/postgresql/postgresql-original-wordmark.svg" alt="PostgreSQL" width="40" height="40"/>
                </div>
                <div class="tech-item">
                    <img src="https://www.vectorlogo.zone/logos/firebase/firebase-icon.svg" alt="Firebase" width="40" height="40"/>
                </div>
                <div class="tech-item">
                    <img src="https://www.vectorlogo.zone/logos/flutterio/flutterio-icon.svg" alt="Flutter" width="40" height="40"/>
                </div>
                <div class="tech-item">
                    <img src="https://www.vectorlogo.zone/logos/tailwindcss/tailwindcss-icon.svg" alt="Tailwind CSS" width="40" height="40"/>
                </div>
                <div class="tech-item">
                    <img src="https://raw.githubusercontent.com/devicons/devicon/master/icons/typescript/typescript-original.svg" alt="TypeScript" width="40" height="40"/>
                </div>
                <div class="tech-item">
                    <img src="https://www.vectorlogo.zone/logos/figma/figma-icon.svg" alt="Figma" width="40" height="40"/>
                </div>
                <div class="tech-item">
                    <img src="https://www.vectorlogo.zone/logos/git-scm/git-scm-icon.svg" alt="Git" width="40" height="40"/>
                </div>
                <div class="tech-item">
                    <img src="https://raw.githubusercontent.com/devicons/devicon/master/icons/java/java-original.svg" alt="Java" width="40" height="40"/>
                </div>
            </div>
        </div>

        <div class="stats-section">
            <div class="stat-card">
                <h3 class="gradient-text">GitHub Stats</h3>
                <img src="https://github-readme-stats.vercel.app/api?username=ahsan3219&show_icons=true&theme=tokyonight&hide_border=true&bg_color=0d1117&title_color=8b5cf6&icon_color=8b5cf6" alt="GitHub Stats" />
            </div>
            <div class="stat-card">
                <h3 class="gradient-text">Most Used Languages</h3>
                <img src="https://github-readme-stats.vercel.app/api/top-langs?username=ahsan3219&show_icons=true&theme=tokyonight&layout=compact&hide_border=true&bg_color=0d1117&title_color=8b5cf6" alt="Top Languages" />
            </div>
            <div class="stat-card">
                <h3 class="gradient-text">GitHub Streak</h3>
                <img src="https://github-readme-streak-stats.herokuapp.com/?user=ahsan3219&theme=tokyonight&hide_border=true&background=0d1117&stroke=8b5cf6&ring=8b5cf6&fire=8b5cf6&currStreakLabel=8b5cf6" alt="GitHub Streak" />
            </div>
        </div>

        <div class="footer">
            <p class="gradient-text">⚡ "Building the future with AI, one line of code at a time" ⚡</p>
            <p style="margin-top: 10px; opacity: 0.7;">Made with ❤️ by Ahsan Raza</p>
        </div>
    </div>

    <script>
        // Typing animation
        const texts = [
            "Solutions Architect",
            "AI Engineer", 
            "Full Stack Developer",
            "Tech Enthusiast"
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

        // Add smooth scrolling
        document.querySelectorAll('a[href^="#"]').forEach(anchor => {
            anchor.addEventListener('click', function (e) {
                e.preventDefault();
                document.querySelector(this.getAttribute('href')).scrollIntoView({
                    behavior: 'smooth'
                });
            });
        });
    </script>
</body>
</html>
