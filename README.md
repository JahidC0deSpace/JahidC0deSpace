<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Md. Jahid Hasan Jitu — GitHub Profile</title>
    <script src="https://cdn.jsdelivr.net/npm/@tailwindcss/browser@4"></script>
    <link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.5.1/css/all.min.css">
    <style>
        @import url('https://fonts.googleapis.com/css2?family=Inter:wght@300;400;500;600;700;800;900&family=Fira+Code:wght@400;500&family=Space+Grotesk:wght@400;500;600;700&display=swap');

        :root {
            --bg-primary: #0d1117;
            --bg-secondary: #161b22;
            --bg-tertiary: #1c2333;
            --border: #30363d;
            --text-primary: #e6edf3;
            --text-secondary: #8b949e;
            --accent-blue: #58a6ff;
            --accent-purple: #bc8cff;
            --accent-green: #3fb950;
            --accent-orange: #f78166;
            --accent-yellow: #d29922;
            --accent-pink: #f778ba;
            --accent-cyan: #39d353;
        }

        * { box-sizing: border-box; }

        body {
            font-family: 'Inter', -apple-system, BlinkMacSystemFont, sans-serif;
            background-color: var(--bg-primary);
            color: var(--text-primary);
            overflow-x: hidden;
        }

        code, .code-font {
            font-family: 'Fira Code', monospace;
        }

        .heading-font {
            font-family: 'Space Grotesk', sans-serif;
        }

        /* Animated gradient background */
        .hero-gradient {
            background: linear-gradient(135deg, #0d1117 0%, #161b22 25%, #1a1e2e 50%, #1c1a2e 75%, #0d1117 100%);
            position: relative;
        }

        .hero-gradient::before {
            content: '';
            position: absolute;
            top: 0; left: 0; right: 0; bottom: 0;
            background: radial-gradient(ellipse at 20% 50%, rgba(88, 166, 255, 0.08) 0%, transparent 50%),
                        radial-gradient(ellipse at 80% 20%, rgba(188, 140, 255, 0.08) 0%, transparent 50%),
                        radial-gradient(ellipse at 50% 80%, rgba(247, 129, 102, 0.05) 0%, transparent 50%);
            pointer-events: none;
        }

        /* Profile image glow */
        .profile-ring {
            position: relative;
            display: inline-block;
        }

        .profile-ring::before {
            content: '';
            position: absolute;
            top: -4px; left: -4px; right: -4px; bottom: -4px;
            border-radius: 50%;
            background: conic-gradient(from 0deg, #58a6ff, #bc8cff, #f78166, #d29922, #3fb950, #58a6ff);
            animation: spin 4s linear infinite;
            z-index: 0;
        }

        .profile-ring::after {
            content: '';
            position: absolute;
            top: -4px; left: -4px; right: -4px; bottom: -4px;
            border-radius: 50%;
            background: conic-gradient(from 0deg, #58a6ff, #bc8cff, #f78166, #d29922, #3fb950, #58a6ff);
            animation: spin 4s linear infinite;
            filter: blur(15px);
            opacity: 0.5;
            z-index: -1;
        }

        @keyframes spin {
            to { transform: rotate(360deg); }
        }

        .profile-img {
            position: relative;
            z-index: 1;
            border: 3px solid var(--bg-primary);
        }

        /* Typing animation */
        .typing-text {
            display: inline-block;
            border-right: 2px solid var(--accent-blue);
            animation: blink 0.8s step-end infinite;
            white-space: nowrap;
            overflow: hidden;
        }

        @keyframes blink {
            50% { border-color: transparent; }
        }

        /* Card styles */
        .glass-card {
            background: linear-gradient(135deg, rgba(22, 27, 34, 0.8), rgba(28, 35, 51, 0.6));
            backdrop-filter: blur(10px);
            border: 1px solid var(--border);
            transition: all 0.4s cubic-bezier(0.4, 0, 0.2, 1);
        }

        .glass-card:hover {
            border-color: var(--accent-blue);
            transform: translateY(-4px);
            box-shadow: 0 8px 32px rgba(88, 166, 255, 0.1);
        }

        .project-card {
            position: relative;
            overflow: hidden;
        }

        .project-card::before {
            content: '';
            position: absolute;
            top: 0; left: 0;
            width: 100%; height: 3px;
            background: linear-gradient(90deg, var(--accent-blue), var(--accent-purple), var(--accent-orange));
            transform: scaleX(0);
            transform-origin: left;
            transition: transform 0.4s ease;
        }

        .project-card:hover::before {
            transform: scaleX(1);
        }

        /* Tech badge */
        .tech-pill {
            background: rgba(88, 166, 255, 0.1);
            border: 1px solid rgba(88, 166, 255, 0.2);
            color: var(--accent-blue);
            padding: 6px 14px;
            border-radius: 20px;
            font-size: 13px;
            font-weight: 500;
            transition: all 0.3s ease;
            display: inline-flex;
            align-items: center;
            gap: 6px;
        }

        .tech-pill:hover {
            background: rgba(88, 166, 255, 0.2);
            transform: translateY(-2px);
        }

        .tech-pill-purple {
            background: rgba(188, 140, 255, 0.1);
            border-color: rgba(188, 140, 255, 0.2);
            color: var(--accent-purple);
        }
        .tech-pill-purple:hover { background: rgba(188, 140, 255, 0.2); }

        .tech-pill-green {
            background: rgba(63, 185, 80, 0.1);
            border-color: rgba(63, 185, 80, 0.2);
            color: var(--accent-green);
        }
        .tech-pill-green:hover { background: rgba(63, 185, 80, 0.2); }

        .tech-pill-orange {
            background: rgba(247, 129, 102, 0.1);
            border-color: rgba(247, 129, 102, 0.2);
            color: var(--accent-orange);
        }
        .tech-pill-orange:hover { background: rgba(247, 129, 102, 0.2); }

        .tech-pill-yellow {
            background: rgba(210, 153, 34, 0.1);
            border-color: rgba(210, 153, 34, 0.2);
            color: var(--accent-yellow);
        }
        .tech-pill-yellow:hover { background: rgba(210, 153, 34, 0.2); }

        .tech-pill-pink {
            background: rgba(247, 120, 186, 0.1);
            border-color: rgba(247, 120, 186, 0.2);
            color: var(--accent-pink);
        }
        .tech-pill-pink:hover { background: rgba(247, 120, 186, 0.2); }

        /* Section divider */
        .section-divider {
            height: 1px;
            background: linear-gradient(90deg, transparent, var(--border), var(--accent-blue), var(--border), transparent);
        }

        /* Stat card shimmer */
        .stat-card {
            position: relative;
            overflow: hidden;
        }

        .stat-card::after {
            content: '';
            position: absolute;
            top: -50%; left: -50%;
            width: 200%; height: 200%;
            background: linear-gradient(45deg, transparent 40%, rgba(255,255,255,0.03) 50%, transparent 60%);
            transform: translateX(-100%);
            transition: transform 0.6s ease;
        }

        .stat-card:hover::after {
            transform: translateX(100%);
        }

        /* Fun fact cards */
        .fun-card {
            transition: all 0.3s ease;
        }

        .fun-card:hover {
            transform: scale(1.05) rotate(-1deg);
        }

        /* Scroll animations */
        .reveal {
            opacity: 0;
            transform: translateY(30px);
            transition: all 0.6s cubic-bezier(0.4, 0, 0.2, 1);
        }

        .reveal.visible {
            opacity: 1;
            transform: translateY(0);
        }

        /* Contact link hover */
        .contact-link {
            transition: all 0.3s ease;
            position: relative;
        }

        .contact-link::after {
            content: '';
            position: absolute;
            bottom: -2px; left: 0;
            width: 0; height: 2px;
            background: var(--accent-blue);
            transition: width 0.3s ease;
        }

        .contact-link:hover::after {
            width: 100%;
        }

        /* Custom scrollbar */
        ::-webkit-scrollbar { width: 8px; }
        ::-webkit-scrollbar-track { background: var(--bg-primary); }
        ::-webkit-scrollbar-thumb { background: var(--border); border-radius: 4px; }
        ::-webkit-scrollbar-thumb:hover { background: #484f58; }

        /* Wave SVG animation */
        .wave-separator svg {
            display: block;
        }

        /* Floating particles */
        .particle {
            position: absolute;
            border-radius: 50%;
            pointer-events: none;
            animation: float linear infinite;
            opacity: 0.3;
        }

        @keyframes float {
            0% { transform: translateY(100vh) rotate(0deg); opacity: 0; }
            10% { opacity: 0.3; }
            90% { opacity: 0.3; }
            100% { transform: translateY(-10vh) rotate(720deg); opacity: 0; }
        }

        /* Social icon hover */
        .social-icon {
            width: 48px; height: 48px;
            display: inline-flex;
            align-items: center;
            justify-content: center;
            border-radius: 12px;
            border: 1px solid var(--border);
            background: var(--bg-secondary);
            color: var(--text-secondary);
            font-size: 20px;
            transition: all 0.3s ease;
        }

        .social-icon:hover {
            transform: translateY(-4px);
            box-shadow: 0 6px 20px rgba(0,0,0,0.3);
        }

        .social-icon.email:hover { background: #ea4335; border-color: #ea4335; color: white; }
        .social-icon.linkedin:hover { background: #0077b5; border-color: #0077b5; color: white; }
        .social-icon.facebook:hover { background: #1877f2; border-color: #1877f2; color: white; }
        .social-icon.github:hover { background: #333; border-color: #555; color: white; }

        /* About me icon boxes */
        .about-icon-box {
            width: 40px; height: 40px;
            display: flex;
            align-items: center;
            justify-content: center;
            border-radius: 10px;
            font-size: 18px;
            flex-shrink: 0;
        }
    </style>
</head>
<body class="min-h-screen">

    <!-- Floating Particles Background -->
    <div id="particles" class="fixed inset-0 pointer-events-none z-0"></div>

    <!-- ============ HERO SECTION ============ -->
    <section class="hero-gradient relative min-h-[90vh] flex items-center justify-center px-4 py-16">
        <div class="relative z-10 text-center max-w-4xl mx-auto">

            <!-- Greeting -->
            <div class="mb-6 reveal">
                <span class="inline-block bg-[#1c2333] border border-[#30363d] rounded-full px-5 py-2 text-sm text-[#8b949e]">
                    <span class="mr-2">👋</span> Welcome to my GitHub Profile
                </span>
            </div>

            <!-- Profile Image -->
            <div class="mb-8 reveal" style="transition-delay: 0.1s">
                <div class="profile-ring inline-block rounded-full">
                    <img src="https://images2.imgbox.com/c8/6e/86YsmniG_o.jpg"
                         alt="Md. Jahid Hasan Jitu"
                         class="profile-img w-40 h-40 md:w-48 md:h-48 rounded-full object-cover">
                </div>
            </div>

            <!-- Name -->
            <h1 class="heading-font text-4xl md:text-6xl font-bold mb-4 reveal" style="transition-delay: 0.2s">
                Hi, I'm <span class="bg-gradient-to-r from-[#58a6ff] via-[#bc8cff] to-[#f78166] bg-clip-text text-transparent">Md. Jahid Hasan Jitu</span>
            </h1>

            <!-- Typing subtitle -->
            <div class="text-xl md:text-2xl text-[#8b949e] mb-8 h-8 reveal" style="transition-delay: 0.3s">
                <span id="typingText" class="typing-text"></span>
            </div>

            <!-- Role badges -->
            <div class="flex flex-wrap justify-center gap-3 mb-10 reveal" style="transition-delay: 0.4s">
                <span class="tech-pill"><i class="fa-solid fa-rocket"></i> Web Developer</span>
                <span class="tech-pill tech-pill-purple"><i class="fa-solid fa-robot"></i> AI & ML Enthusiast</span>
                <span class="tech-pill tech-pill-green"><i class="fa-solid fa-lightbulb"></i> Continuous Learner</span>
            </div>

            <!-- Social icons -->
            <div class="flex justify-center gap-4 reveal" style="transition-delay: 0.5s">
                <a href="mailto:jahidjitu095@gmail.com" class="social-icon email" title="Email"><i class="fa-solid fa-envelope"></i></a>
                <a href="https://www.linkedin.com/in/md-jahid-hasan-jitu-a94a27230" target="_blank" class="social-icon linkedin" title="LinkedIn"><i class="fa-brands fa-linkedin-in"></i></a>
                <a href="https://www.facebook.com/muhammad.jahidhasanjitu" target="_blank" class="social-icon facebook" title="Facebook"><i class="fa-brands fa-facebook-f"></i></a>
                <a href="https://github.com/JahidC0deSpace" target="_blank" class="social-icon github" title="GitHub"><i class="fa-brands fa-github"></i></a>
            </div>

            <!-- Scroll indicator -->
            <div class="mt-16 animate-bounce reveal" style="transition-delay: 0.6s">
                <i class="fa-solid fa-chevron-down text-[#30363d] text-2xl"></i>
            </div>
        </div>
    </section>

    <!-- Wave separator -->
    <div class="wave-separator relative -mt-1">
        <svg viewBox="0 0 1440 80" fill="none" xmlns="http://www.w3.org/2000/svg">
            <path d="M0,40 C360,80 720,0 1080,40 C1260,60 1380,50 1440,40 L1440,80 L0,80 Z" fill="#0d1117"/>
        </svg>
    </div>

    <!-- ============ MAIN CONTENT ============ -->
    <main class="relative z-10 max-w-5xl mx-auto px-4 pb-20">

        <!-- ===== ABOUT ME ===== -->
        <section class="mb-20 reveal">
            <div class="flex items-center gap-3 mb-8">
                <div class="w-10 h-10 rounded-lg bg-gradient-to-br from-[#58a6ff] to-[#bc8cff] flex items-center justify-center text-lg">🧠</div>
                <h2 class="heading-font text-3xl font-bold">About Me</h2>
                <div class="flex-1 h-px bg-gradient-to-r from-[#30363d] to-transparent ml-4"></div>
            </div>

            <div class="glass-card rounded-2xl p-6 md:p-8">
                <div class="space-y-5">
                    <div class="flex items-start gap-4">
                        <div class="about-icon-box bg-[#1a2a3a]">🎓</div>
                        <div>
                            <p class="text-[#c9d1d9] leading-relaxed">Computer Science student with a strong interest in <strong class="text-[#58a6ff]">Web Development</strong> and <strong class="text-[#bc8cff]">Artificial Intelligence / Machine Learning</strong></p>
                        </div>
                    </div>
                    <div class="flex items-start gap-4">
                        <div class="about-icon-box bg-[#1a2a1f]">💻</div>
                        <div>
                            <p class="text-[#c9d1d9] leading-relaxed">Focused on building <strong class="text-[#3fb950]">scalable, real-world applications</strong> that solve practical problems</p>
                        </div>
                    </div>
                    <div class="flex items-start gap-4">
                        <div class="about-icon-box bg-[#2a2115]">🌱</div>
                        <div>
                            <p class="text-[#c9d1d9] leading-relaxed">Currently working with <strong class="text-[#d29922]">MERN Stack</strong>, <strong class="text-[#f78166]">real-time systems</strong>, and <strong class="text-[#f778ba]">backend architecture</strong></p>
                        </div>
                    </div>
                    <div class="flex items-start gap-4">
                        <div class="about-icon-box bg-[#1a1f2e]">🎯</div>
                        <div>
                            <p class="text-[#c9d1d9] leading-relaxed">Goal: Grow as a software engineer by solving practical problems and building <strong class="text-[#58a6ff]">impactful software</strong></p>
                        </div>
                    </div>
                </div>
            </div>
        </section>

        <!-- Divider -->
        <div class="section-divider mb-20"></div>

        <!-- ===== TECH STACK ===== -->
        <section class="mb-20 reveal">
            <div class="flex items-center gap-3 mb-8">
                <div class="w-10 h-10 rounded-lg bg-gradient-to-br from-[#f78166] to-[#d29922] flex items-center justify-center text-lg">⚒️</div>
                <h2 class="heading-font text-3xl font-bold">Tech Stack</h2>
                <div class="flex-1 h-px bg-gradient-to-r from-[#30363d] to-transparent ml-4"></div>
            </div>

            <div class="grid grid-cols-1 md:grid-cols-2 gap-4">
                <!-- Languages -->
                <div class="glass-card rounded-2xl p-6">
                    <div class="flex items-center gap-3 mb-5">
                        <span class="text-2xl">🔤</span>
                        <h3 class="font-semibold text-lg text-[#e6edf3]">Languages</h3>
                    </div>
                    <div class="flex flex-wrap gap-2">
                        <span class="tech-pill text-xs"><i class="fa-solid fa-code"></i> C</span>
                        <span class="tech-pill text-xs"><i class="fa-solid fa-code"></i> C++</span>
                        <span class="tech-pill tech-pill-orange text-xs"><i class="fa-brands fa-java"></i> Java</span>
                        <span class="tech-pill tech-pill-yellow text-xs"><i class="fa-brands fa-js"></i> JavaScript</span>
                        <span class="tech-pill tech-pill-green text-xs"><i class="fa-brands fa-python"></i> Python</span>
                    </div>
                </div>

                <!-- Frontend -->
                <div class="glass-card rounded-2xl p-6">
                    <div class="flex items-center gap-3 mb-5">
                        <span class="text-2xl">🎨</span>
                        <h3 class="font-semibold text-lg text-[#e6edf3]">Frontend</h3>
                    </div>
                    <div class="flex flex-wrap gap-2">
                        <span class="tech-pill tech-pill-orange text-xs"><i class="fa-brands fa-html5"></i> HTML</span>
                        <span class="tech-pill tech-pill-purple text-xs"><i class="fa-brands fa-css3-alt"></i> CSS</span>
                        <span class="tech-pill text-xs"><i class="fa-brands fa-react"></i> React.js</span>
                        <span class="tech-pill text-xs">🌊 Tailwind CSS</span>
                        <span class="tech-pill tech-pill-green text-xs">⚡ Chakra UI</span>
                    </div>
                </div>

                <!-- Backend -->
                <div class="glass-card rounded-2xl p-6">
                    <div class="flex items-center gap-3 mb-5">
                        <span class="text-2xl">⚙️</span>
                        <h3 class="font-semibold text-lg text-[#e6edf3]">Backend</h3>
                    </div>
                    <div class="flex flex-wrap gap-2">
                        <span class="tech-pill tech-pill-green text-xs"><i class="fa-brands fa-node-js"></i> Node.js</span>
                        <span class="tech-pill text-xs">🚂 Express.js</span>
                        <span class="tech-pill tech-pill-purple text-xs">🔌 RESTful APIs</span>
                        <span class="tech-pill tech-pill-yellow text-xs">⚡ Socket.IO</span>
                    </div>
                </div>

                <!-- Database & Tools -->
                <div class="glass-card rounded-2xl p-6">
                    <div class="flex items-center gap-3 mb-5">
                        <span class="text-2xl">🗄️</span>
                        <h3 class="font-semibold text-lg text-[#e6edf3]">Database & Tools</h3>
                    </div>
                    <div class="flex flex-wrap gap-2">
                        <span class="tech-pill tech-pill-green text-xs">🍃 MongoDB</span>
                        <span class="tech-pill text-xs"><i class="fa-brands fa-git-alt"></i> Git & GitHub</span>
                        <span class="tech-pill tech-pill-orange text-xs">🔐 JWT Auth</span>
                        <span class="tech-pill tech-pill-purple text-xs">🐻 Zustand</span>
                        <span class="tech-pill tech-pill-pink text-xs">☁️ Cloudinary</span>
                    </div>
                </div>
            </div>
        </section>

        <!-- Divider -->
        <div class="section-divider mb-20"></div>

        <!-- ===== FEATURED PROJECTS ===== -->
        <section class="mb-20 reveal">
            <div class="flex items-center gap-3 mb-8">
                <div class="w-10 h-10 rounded-lg bg-gradient-to-br from-[#3fb950] to-[#58a6ff] flex items-center justify-center text-lg">🛠️</div>
                <h2 class="heading-font text-3xl font-bold">Featured Projects</h2>
                <div class="flex-1 h-px bg-gradient-to-r from-[#30363d] to-transparent ml-4"></div>
            </div>

            <div class="space-y-4">

                <!-- Near Chat App -->
                <div class="glass-card project-card rounded-2xl p-6 cursor-pointer">
                    <div class="flex flex-col md:flex-row md:items-center gap-4">
                        <div class="flex items-center gap-4 flex-1">
                            <div class="w-12 h-12 rounded-xl bg-gradient-to-br from-[#58a6ff] to-[#3b82f6] flex items-center justify-center text-2xl flex-shrink-0">💬</div>
                            <div class="flex-1">
                                <h3 class="font-bold text-lg text-[#e6edf3] mb-1">Near Chat App</h3>
                                <p class="text-sm text-[#8b949e]">Real-time chat application with authentication, live messaging, and media handling</p>
                            </div>
                        </div>
                        <div class="flex flex-wrap gap-1.5">
                            <span class="text-xs bg-[#1a2a3a] text-[#58a6ff] px-2.5 py-1 rounded-full border border-[#1f3a5f]">MERN</span>
                            <span class="text-xs bg-[#2a2115] text-[#d29922] px-2.5 py-1 rounded-full border border-[#5a4215]">Socket.IO</span>
                        </div>
                    </div>
                </div>

                <!-- Authentication System -->
                <div class="glass-card project-card rounded-2xl p-6 cursor-pointer">
                    <div class="flex flex-col md:flex-row md:items-center gap-4">
                        <div class="flex items-center gap-4 flex-1">
                            <div class="w-12 h-12 rounded-xl bg-gradient-to-br from-[#f78166] to-[#da3633] flex items-center justify-center text-2xl flex-shrink-0">🔐</div>
                            <div class="flex-1">
                                <h3 class="font-bold text-lg text-[#e6edf3] mb-1">Authentication System</h3>
                                <p class="text-sm text-[#8b949e]">Secure authentication with email verification, JWT, and password recovery</p>
                            </div>
                        </div>
                        <div class="flex flex-wrap gap-1.5">
                            <span class="text-xs bg-[#1a2a1f] text-[#3fb950] px-2.5 py-1 rounded-full border border-[#1a4a2f]">Node.js</span>
                            <span class="text-xs bg-[#1a2a3a] text-[#58a6ff] px-2.5 py-1 rounded-full border border-[#1f3a5f]">Express</span>
                            <span class="text-xs bg-[#1a2a1f] text-[#3fb950] px-2.5 py-1 rounded-full border border-[#1a4a2f]">MongoDB</span>
                        </div>
                    </div>
                </div>

                <!-- Product Store -->
                <div class="glass-card project-card rounded-2xl p-6 cursor-pointer">
                    <div class="flex flex-col md:flex-row md:items-center gap-4">
                        <div class="flex items-center gap-4 flex-1">
                            <div class="w-12 h-12 rounded-xl bg-gradient-to-br from-[#d29922] to-[#f78166] flex items-center justify-center text-2xl flex-shrink-0">🛒</div>
                            <div class="flex-1">
                                <h3 class="font-bold text-lg text-[#e6edf3] mb-1">Product Store</h3>
                                <p class="text-sm text-[#8b949e]">CRUD product management system with image support and modern UI</p>
                            </div>
                        </div>
                        <div class="flex flex-wrap gap-1.5">
                            <span class="text-xs bg-[#1a2a3a] text-[#58a6ff] px-2.5 py-1 rounded-full border border-[#1f3a5f]">MERN</span>
                        </div>
                    </div>
                </div>

                <!-- ThinkBoard -->
                <div class="glass-card project-card rounded-2xl p-6 cursor-pointer">
                    <div class="flex flex-col md:flex-row md:items-center gap-4">
                        <div class="flex items-center gap-4 flex-1">
                            <div class="w-12 h-12 rounded-xl bg-gradient-to-br from-[#bc8cff] to-[#8b5cf6] flex items-center justify-center text-2xl flex-shrink-0">🧠</div>
                            <div class="flex-1">
                                <h3 class="font-bold text-lg text-[#e6edf3] mb-1">ThinkBoard</h3>
                                <p class="text-sm text-[#8b949e]">Minimal notes app with timestamped create, update, and delete features</p>
                            </div>
                        </div>
                        <div class="flex flex-wrap gap-1.5">
                            <span class="text-xs bg-[#1a2a3a] text-[#58a6ff] px-2.5 py-1 rounded-full border border-[#1f3a5f]">MERN</span>
                        </div>
                    </div>
                </div>

                <!-- AI Voice Assistant -->
                <div class="glass-card project-card rounded-2xl p-6 cursor-pointer">
                    <div class="flex flex-col md:flex-row md:items-center gap-4">
                        <div class="flex items-center gap-4 flex-1">
                            <div class="w-12 h-12 rounded-xl bg-gradient-to-br from-[#3fb950] to-[#238636] flex items-center justify-center text-2xl flex-shrink-0">🤖</div>
                            <div class="flex-1">
                                <h3 class="font-bold text-lg text-[#e6edf3] mb-1">AI Voice Assistant</h3>
                                <p class="text-sm text-[#8b949e]">Desktop AI assistant inspired by JARVIS with voice commands</p>
                            </div>
                        </div>
                        <div class="flex flex-wrap gap-1.5">
                            <span class="text-xs bg-[#1a2a1f] text-[#3fb950] px-2.5 py-1 rounded-full border border-[#1a4a2f]">Python</span>
                        </div>
                    </div>
                </div>

            </div>
        </section>

        <!-- Divider -->
        <div class="section-divider mb-20"></div>

        <!-- ===== GITHUB STATS ===== -->
        <section class="mb-20 reveal">
            <div class="flex items-center gap-3 mb-8">
                <div class="w-10 h-10 rounded-lg bg-gradient-to-br from-[#bc8cff] to-[#f778ba] flex items-center justify-center text-lg">📈</div>
                <h2 class="heading-font text-3xl font-bold">GitHub Stats</h2>
                <div class="flex-1 h-px bg-gradient-to-r from-[#30363d] to-transparent ml-4"></div>
            </div>

            <div class="grid grid-cols-1 md:grid-cols-2 gap-4 mb-4">
                <div class="glass-card stat-card rounded-2xl p-2 flex items-center justify-center">
                    <img src="https://github-readme-stats.vercel.app/api?username=JahidC0deSpace&show_icons=true&count_private=true&include_all_commits=true&theme=radical&hide_border=true&bg_color=00000000" alt="GitHub Stats" class="w-full rounded-xl">
                </div>
                <div class="glass-card stat-card rounded-2xl p-2 flex items-center justify-center">
                    <img src="https://github-readme-streak-stats.herokuapp.com/?user=JahidC0deSpace&theme=radical&hide_border=true&background=00000000" alt="GitHub Streak" class="w-full rounded-xl">
                </div>
            </div>

            <div class="glass-card stat-card rounded-2xl p-2 flex items-center justify-center mb-4">
                <img src="https://github-readme-stats.vercel.app/api/top-langs/?username=JahidC0deSpace&layout=compact&theme=radical&hide_border=true&bg_color=00000000" alt="Top Languages" class="w-full md:w-1/2 rounded-xl">
            </div>

            <div class="glass-card stat-card rounded-2xl p-2 flex items-center justify-center">
                <img src="https://github-readme-activity-graph.vercel.app/graph?username=JahidC0deSpace&theme=react-dark&hide_border=true&bg_color=00000000" alt="Contribution Graph" class="w-full rounded-xl">
            </div>
        </section>

        <!-- Divider -->
        <div class="section-divider mb-20"></div>

        <!-- ===== CONTACT ME ===== -->
        <section class="mb-20 reveal">
            <div class="flex items-center gap-3 mb-8">
                <div class="w-10 h-10 rounded-lg bg-gradient-to-br from-[#d29922] to-[#f78166] flex items-center justify-center text-lg">📫</div>
                <h2 class="heading-font text-3xl font-bold">Contact Me</h2>
                <div class="flex-1 h-px bg-gradient-to-r from-[#30363d] to-transparent ml-4"></div>
            </div>

            <div class="grid grid-cols-1 md:grid-cols-3 gap-4">
                <!-- Email -->
                <a href="mailto:jahidjitu095@gmail.com" class="glass-card rounded-2xl p-6 text-center group no-underline">
                    <div class="w-14 h-14 rounded-full bg-gradient-to-br from-[#ea4335]/20 to-[#ea4335]/5 border border-[#ea4335]/20 flex items-center justify-center text-2xl mx-auto mb-4 group-hover:scale-110 transition-transform">
                        📧
                    </div>
                    <h3 class="font-semibold text-[#e6edf3] mb-1">Email</h3>
                    <p class="text-sm text-[#58a6ff] contact-link inline-block">jahidjitu095@gmail.com</p>
                </a>

                <!-- LinkedIn -->
                <a href="https://www.linkedin.com/in/md-jahid-hasan-jitu-a94a27230" target="_blank" class="glass-card rounded-2xl p-6 text-center group no-underline">
                    <div class="w-14 h-14 rounded-full bg-gradient-to-br from-[#0077b5]/20 to-[#0077b5]/5 border border-[#0077b5]/20 flex items-center justify-center text-2xl mx-auto mb-4 group-hover:scale-110 transition-transform">
                        💼
                    </div>
                    <h3 class="font-semibold text-[#e6edf3] mb-1">LinkedIn</h3>
                    <p class="text-sm text-[#58a6ff] contact-link inline-block">Md. Jahid Hasan Jitu</p>
                </a>

                <!-- Facebook -->
                <a href="https://www.facebook.com/muhammad.jahidhasanjitu" target="_blank" class="glass-card rounded-2xl p-6 text-center group no-underline">
                    <div class="w-14 h-14 rounded-full bg-gradient-to-br from-[#1877f2]/20 to-[#1877f2]/5 border border-[#1877f2]/20 flex items-center justify-center text-2xl mx-auto mb-4 group-hover:scale-110 transition-transform">
                        🌐
                    </div>
                    <h3 class="font-semibold text-[#e6edf3] mb-1">Facebook</h3>
                    <p class="text-sm text-[#58a6ff] contact-link inline-block">Muhammad Jahid Hasan Jitu</p>
                </a>
            </div>
        </section>

        <!-- Divider -->
        <div class="section-divider mb-20"></div>

        <!-- ===== FUN FACTS ===== -->
        <section class="mb-20 reveal">
            <div class="flex items-center gap-3 mb-8">
                <div class="w-10 h-10 rounded-lg bg-gradient-to-br from-[#f778ba] to-[#bc8cff] flex items-center justify-center text-lg">🎲</div>
                <h2 class="heading-font text-3xl font-bold">Fun Facts</h2>
                <div class="flex-1 h-px bg-gradient-to-r from-[#30363d] to-transparent ml-4"></div>
            </div>

            <div class="grid grid-cols-1 md:grid-cols-3 gap-4">
                <div class="fun-card glass-card rounded-2xl p-6 text-center">
                    <div class="text-4xl mb-4">✈️</div>
                    <p class="text-[#c9d1d9]">I enjoy <strong class="text-[#58a6ff]">traveling</strong> and discovering new places</p>
                </div>
                <div class="fun-card glass-card rounded-2xl p-6 text-center">
                    <div class="text-4xl mb-4">😴</div>
                    <p class="text-[#c9d1d9]">I appreciate <strong class="text-[#bc8cff]">good sleep</strong> 😄</p>
                </div>
                <div class="fun-card glass-card rounded-2xl p-6 text-center">
                    <div class="text-4xl mb-4">👨‍💻</div>
                    <p class="text-[#c9d1d9]">Most of my free time goes into <strong class="text-[#3fb950]">coding & learning</strong> new technologies</p>
                </div>
            </div>
        </section>

        <!-- Divider -->
        <div class="section-divider mb-16"></div>

        <!-- ===== PROFILE VIEWS ===== -->
        <section class="mb-16 reveal text-center">
            <img src="https://komarev.com/ghpvc/?username=JahidC0deSpace&color=blueviolet&style=for-the-badge" alt="Profile Views" class="inline-block rounded-lg">
        </section>

    </main>

    <!-- ===== FOOTER ===== -->
    <footer class="relative z-10 border-t border-[#30363d] py-12">
        <div class="max-w-5xl mx-auto px-4 text-center">
            <p class="text-3xl mb-4">⭐</p>
            <p class="text-[#e6edf3] font-semibold text-lg mb-2">Thanks for visiting my profile!</p>
            <p class="text-[#8b949e] text-sm mb-6">Feel free to explore my repositories</p>

            <div class="flex justify-center gap-4 mb-8">
                <a href="mailto:jahidjitu095@gmail.com" class="social-icon email" title="Email"><i class="fa-solid fa-envelope"></i></a>
                <a href="https://www.linkedin.com/in/md-jahid-hasan-jitu-a94a27230" target="_blank" class="social-icon linkedin" title="LinkedIn"><i class="fa-brands fa-linkedin-in"></i></a>
                <a href="https://www.facebook.com/muhammad.jahidhasanjitu" target="_blank" class="social-icon facebook" title="Facebook"><i class="fa-brands fa-facebook-f"></i></a>
                <a href="https://github.com/JahidC0deSpace" target="_blank" class="social-icon github" title="GitHub"><i class="fa-brands fa-github"></i></a>
            </div>

            <p class="text-xs text-[#484f58]">Made with ❤️ and lots of ☕ · © 2024 Md. Jahid Hasan Jitu</p>
        </div>
    </footer>

    <script>
        // ===== TYPING ANIMATION =====
        const roles = [
            "🚀 Full-Stack Web Developer",
            "🤖 AI & ML Enthusiast",
            "💡 Continuous Learner",
            "🔧 MERN Stack Developer",
            "🎯 Problem Solver"
        ];
        let roleIndex = 0;
        let charIndex = 0;
        let isDeleting = false;
        const typingEl = document.getElementById('typingText');

        function type() {
            const currentRole = roles[roleIndex];

            if (isDeleting) {
                typingEl.textContent = currentRole.substring(0, charIndex - 1);
                charIndex--;
            } else {
                typingEl.textContent = currentRole.substring(0, charIndex + 1);
                charIndex++;
            }

            let speed = isDeleting ? 40 : 80;

            if (!isDeleting && charIndex === currentRole.length) {
                speed = 2000; // pause at end
                isDeleting = true;
            } else if (isDeleting && charIndex === 0) {
                isDeleting = false;
                roleIndex = (roleIndex + 1) % roles.length;
                speed = 500;
            }

            setTimeout(type, speed);
        }

        type();

        // ===== FLOATING PARTICLES =====
        function createParticles() {
            const container = document.getElementById('particles');
            const colors = ['#58a6ff', '#bc8cff', '#3fb950', '#f78166', '#d29922'];

            for (let i = 0; i < 20; i++) {
                const particle = document.createElement('div');
                particle.className = 'particle';
                const size = Math.random() * 4 + 2;
                const color = colors[Math.floor(Math.random() * colors.length)];
                particle.style.cssText = `
                    width: ${size}px;
                    height: ${size}px;
                    background: ${color};
                    left: ${Math.random() * 100}%;
                    animation-duration: ${Math.random() * 15 + 10}s;
                    animation-delay: ${Math.random() * 10}s;
                `;
                container.appendChild(particle);
            }
        }
        createParticles();

        // ===== SCROLL REVEAL =====
        const revealObserver = new IntersectionObserver((entries) => {
            entries.forEach(entry => {
                if (entry.isIntersecting) {
                    entry.target.classList.add('visible');
                }
            });
        }, { threshold: 0.1, rootMargin: '0px 0px -50px 0px' });

        document.querySelectorAll('.reveal').forEach(el => {
            revealObserver.observe(el);
        });

        // ===== PROJECT CARD CLICK =====
        document.querySelectorAll('.project-card').forEach(card => {
            card.addEventListener('click', function() {
                this.style.transform = 'scale(0.98)';
                setTimeout(() => {
                    this.style.transform = '';
                }, 150);
            });
        });
    </script>

</body>
</html>
