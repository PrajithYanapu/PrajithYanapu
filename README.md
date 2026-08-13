<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">

    <title>Prajith Sai | Software Engineer</title>

    <style>
        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
        }

        :root {
            --bg: #030712;
            --panel: rgba(15, 23, 42, 0.72);
            --text: #f8fafc;
            --muted: #94a3b8;
            --cyan: #22d3ee;
            --purple: #7c3aed;
            --green: #10b981;
        }

        body {
            min-height: 100vh;
            background: var(--bg);
            color: var(--text);
            font-family: Inter, Arial, sans-serif;
            overflow-x: hidden;
        }

        /* ================= BACKGROUND ================= */

        body::before {
            content: "";
            position: fixed;
            width: 500px;
            height: 500px;
            left: -180px;
            top: -150px;
            background: #22d3ee;
            opacity: 0.12;
            filter: blur(120px);
            border-radius: 50%;
            animation: floatGlow 7s ease-in-out infinite;
        }

        body::after {
            content: "";
            position: fixed;
            width: 500px;
            height: 500px;
            right: -180px;
            bottom: -150px;
            background: #7c3aed;
            opacity: 0.14;
            filter: blur(120px);
            border-radius: 50%;
            animation: floatGlow 9s ease-in-out infinite reverse;
        }

        @keyframes floatGlow {
            0%, 100% {
                transform: translate(0, 0);
            }

            50% {
                transform: translate(30px, -25px);
            }
        }

        /* ================= HERO ================= */

        .container {
            width: min(1180px, 92%);
            min-height: 650px;
            margin: 50px auto;
            padding: 55px;
            position: relative;

            display: grid;
            grid-template-columns: 38% 62%;
            gap: 35px;

            background: var(--panel);
            border: 1px solid rgba(255,255,255,0.08);
            border-radius: 30px;

            backdrop-filter: blur(25px);
            -webkit-backdrop-filter: blur(25px);

            box-shadow:
                0 30px 100px rgba(0,0,0,0.45),
                inset 0 0 50px rgba(255,255,255,0.02);

            overflow: hidden;
        }

        /* animated border */

        .container::before {
            content: "";
            position: absolute;
            inset: -2px;
            border-radius: 30px;

            background: linear-gradient(
                90deg,
                transparent,
                var(--purple),
                var(--cyan),
                var(--green),
                transparent
            );

            background-size: 300% 100%;
            animation: borderMove 7s linear infinite;

            opacity: .45;
            z-index: -1;
        }

        @keyframes borderMove {
            0% {
                background-position: 0% 50%;
            }

            100% {
                background-position: 300% 50%;
            }
        }

        /* ================= LEFT ================= */

        .left {
            display: flex;
            flex-direction: column;
            justify-content: center;
        }

        .terminal-label {
            color: var(--muted);
            font-family: monospace;
            font-size: 14px;
            margin-bottom: 25px;
        }

        .ascii {
            font-family: monospace;
            font-size: clamp(10px, 1.15vw, 15px);
            line-height: 1.35;

            background: linear-gradient(
                90deg,
                var(--purple),
                var(--cyan),
                var(--green)
            );

            background-size: 200% auto;

            -webkit-background-clip: text;
            background-clip: text;
            color: transparent;

            animation:
                gradientMove 5s linear infinite,
                asciiFloat 4s ease-in-out infinite;

            white-space: pre;
        }

        @keyframes gradientMove {
            to {
                background-position: 200% center;
            }
        }

        @keyframes asciiFloat {
            0%,100% {
                transform: translateY(0);
            }

            50% {
                transform: translateY(-8px);
            }
        }

        .left-info {
            margin-top: 35px;
            color: var(--muted);
            font-family: monospace;
            font-size: 14px;
            line-height: 2;
        }

        .green {
            color: var(--green);
        }

        .cyan {
            color: var(--cyan);
        }

        /* ================= RIGHT TERMINAL ================= */

        .terminal {
            background: rgba(2,6,23,.85);
            border: 1px solid rgba(255,255,255,.08);
            border-radius: 22px;

            box-shadow:
                0 25px 70px rgba(0,0,0,.5);

            overflow: hidden;

            animation: terminalEnter 1.2s ease forwards;
        }

        @keyframes terminalEnter {
            from {
                opacity: 0;
                transform: translateY(25px);
            }

            to {
                opacity: 1;
                transform: translateY(0);
            }
        }

        .terminal-header {
            height: 48px;
            display: flex;
            align-items: center;
            gap: 8px;
            padding: 0 18px;
            border-bottom: 1px solid rgba(255,255,255,.06);
        }

        .dot {
            width: 11px;
            height: 11px;
            border-radius: 50%;
        }

        .red {
            background: #ef4444;
        }

        .yellow {
            background: #f59e0b;
        }

        .green-dot {
            background: #22c55e;
        }

        .terminal-title {
            margin-left: 10px;
            color: #64748b;
            font-family: monospace;
            font-size: 12px;
        }

        .terminal-content {
            padding: 40px;
        }

        .hello {
            color: var(--muted);
            font-family: monospace;
            font-size: 15px;
        }

        h1 {
            margin-top: 12px;
            font-size: clamp(35px, 5vw, 58px);
            letter-spacing: -2px;
        }

        .gradient-name {
            background: linear-gradient(
                90deg,
                var(--purple),
                var(--cyan),
                var(--green)
            );

            background-size: 200% auto;

            -webkit-background-clip: text;
            background-clip: text;
            color: transparent;

            animation: gradientMove 5s linear infinite;
        }

        .typing {
            margin-top: 18px;
            color: var(--cyan);
            font-family: monospace;
            font-size: 18px;
        }

        .cursor {
            display: inline-block;
            width: 8px;
            height: 19px;
            background: var(--cyan);
            margin-left: 5px;
            vertical-align: middle;

            animation: blink .8s infinite;
        }

        @keyframes blink {
            0%, 45% {
                opacity: 1;
            }

            46%, 100% {
                opacity: 0;
            }
        }

        .description {
            margin-top: 25px;
            color: var(--muted);
            font-family: monospace;
            line-height: 1.8;
            font-size: 14px;
        }

        /* ================= DETAILS ================= */

        .details {
            margin-top: 35px;
            display: grid;
            gap: 14px;
            color: #cbd5e1;
            font-family: monospace;
            font-size: 14px;
        }

        .detail span {
            color: var(--cyan);
        }

        /* ================= SKILLS ================= */

        .skills {
            margin-top: 35px;
            display: flex;
            flex-wrap: wrap;
            gap: 10px;
        }

        .skill {
            padding: 8px 15px;
            border-radius: 30px;

            color: #cbd5e1;
            font-family: monospace;
            font-size: 12px;

            border: 1px solid rgba(34,211,238,.25);
            background: rgba(34,211,238,.06);

            transition: .3s;
        }

        .skill:hover {
            transform: translateY(-4px) scale(1.06);
            border-color: var(--cyan);
            box-shadow:
                0 0 20px rgba(34,211,238,.25);
        }

        /* ================= LINKS ================= */

        .links {
            margin-top: 35px;
            display: flex;
            gap: 15px;
        }

        .links a {
            color: var(--muted);
            text-decoration: none;

            padding: 10px 16px;

            border: 1px solid rgba(255,255,255,.08);
            border-radius: 12px;

            transition: .3s;
        }

        .links a:hover {
            color: white;
            border-color: var(--cyan);
            box-shadow: 0 0 20px rgba(34,211,238,.15);
            transform: translateY(-3px);
        }

        /* ================= SCANLINE ================= */

        .scanline {
            position: absolute;
            left: 0;
            right: 0;
            height: 2px;

            background: linear-gradient(
                90deg,
                transparent,
                var(--cyan),
                transparent
            );

            opacity: .15;

            animation: scan 5s linear infinite;
        }

        @keyframes scan {
            from {
                top: 0;
            }

            to {
                top: 100%;
            }
        }

        /* ================= PARTICLES ================= */

        .particle {
            position: fixed;
            width: 3px;
            height: 3px;
            background: var(--cyan);
            border-radius: 50%;
            opacity: .5;
            animation: particleFloat 8s linear infinite;
        }

        .p1 {
            left: 15%;
            bottom: -10px;
        }

        .p2 {
            left: 50%;
            bottom: -10px;
            animation-delay: 2s;
        }

        .p3 {
            left: 80%;
            bottom: -10px;
            animation-delay: 4s;
        }

        @keyframes particleFloat {
            from {
                transform: translateY(0);
                opacity: 0;
            }

            20% {
                opacity: .5;
            }

            to {
                transform: translateY(-100vh);
                opacity: 0;
            }
        }

        /* ================= MOBILE ================= */

        @media(max-width: 850px) {

            .container {
                grid-template-columns: 1fr;
                padding: 30px;
                margin: 25px auto;
            }

            .left {
                align-items: center;
                text-align: center;
            }

            .ascii {
                font-size: 11px;
            }

            .terminal-content {
                padding: 28px;
            }

            .skills {
                justify-content: center;
            }

            .links {
                justify-content: center;
                flex-wrap: wrap;
            }
        }
    </style>
</head>

<body>

    <!-- Floating particles -->
    <div class="particle p1"></div>
    <div class="particle p2"></div>
    <div class="particle p3"></div>

    <main class="container">

        <div class="scanline"></div>

        <!-- ================= LEFT SIDE ================= -->

        <section class="left">

            <div class="terminal-label">
                $ initializing portfolio...
            </div>

            <pre class="ascii">
        .-''''-.
      .'  .--.  '.
     /   /    \   \
    ;   |  ()  |   ;
    |   |      |   |
    ;    \____/    ;
     \     __     /
      '.        .'
        '-.__.-'
            </pre>

            <div class="left-info">

                <div>
                    <span class="green">$ whoami</span>
                </div>

                <div>
                    prajith@github:~$
                </div>

                <br>

                <div>
                    building • learning • shipping
                </div>

                <div>
                    Java • Spring Boot • React
                </div>

                <div>
                    AWS • Python • SQL
                </div>

            </div>

        </section>


        <!-- ================= RIGHT SIDE ================= -->

        <section class="terminal">

            <div class="terminal-header">

                <span class="dot red"></span>
                <span class="dot yellow"></span>
                <span class="dot green-dot"></span>

                <span class="terminal-title">
                    prajith@portfolio — bash
                </span>

            </div>


            <div class="terminal-content">

                <div class="hello">
                    Hi 👋
                </div>

                <h1>
                    I'm
                    <span class="gradient-name">
                        Prajith
                    </span>
                </h1>

                <div class="typing">
                    <span id="typingText"></span>
                    <span class="cursor"></span>
                </div>

                <p class="description">
                    I build scalable applications, backend services,
                    REST APIs and AI-powered solutions.
                    Passionate about software engineering,
                    cloud technologies and solving real-world problems.
                </p>


                <div class="details">

                    <div class="detail">
                        📍 <span>Location:</span> India
                    </div>

                    <div class="detail">
                        🎓 <span>Education:</span>
                        B.Tech — ECE + AI/ML
                    </div>

                    <div class="detail">
                        ⚡ <span>Focus:</span>
                        Full-Stack & Backend Development
                    </div>

                    <div class="detail">
                        🚀 <span>Status:</span>
                        Open to Software Engineering Opportunities
                    </div>

                </div>


                <!-- Skills -->

                <div class="skills">

                    <div class="skill">Java</div>
                    <div class="skill">Spring Boot</div>
                    <div class="skill">React</div>
                    <div class="skill">Node.js</div>
                    <div class="skill">Python</div>
                    <div class="skill">SQL</div>
                    <div class="skill">MongoDB</div>
                    <div class="skill">AWS</div>
                    <div class="skill">Git</div>
                    <div class="skill">REST APIs</div>

                </div>


                <!-- Social Links -->

                <div class="links">

                    <a
                        href="https://github.com/PrajithYanapu"
                        target="_blank">
                        GitHub
                    </a>

                    <a
                        href="https://www.linkedin.com/in/prajith-kumar18/"
                        target="_blank">
                        LinkedIn
                    </a>

                    <a
                        href="mailto:prajithyanapu@gmail.com">
                        Email
                    </a>

                </div>

            </div>

        </section>

    </main>


    <!-- ================= TYPING EFFECT ================= -->

    <script>

        const phrases = [
            "Software Engineer",
            "Java Developer",
            "Full Stack Developer",
            "Backend Developer",
            "AI/ML Enthusiast"
        ];

        const textElement =
            document.getElementById("typingText");

        let phraseIndex = 0;
        let charIndex = 0;
        let deleting = false;

        function typeEffect() {

            const current =
                phrases[phraseIndex];

            if (!deleting) {

                textElement.textContent =
                    current.substring(0, charIndex + 1);

                charIndex++;

                if (charIndex === current.length) {

                    deleting = true;

                    setTimeout(typeEffect, 1800);

                    return;
                }

            } else {

                textElement.textContent =
                    current.substring(0, charIndex - 1);

                charIndex--;

                if (charIndex === 0) {

                    deleting = false;

                    phraseIndex =
                        (phraseIndex + 1) % phrases.length;

                }

            }

            setTimeout(
                typeEffect,
                deleting ? 50 : 90
            );
        }

        typeEffect();

    </script>

</body>
</html>
