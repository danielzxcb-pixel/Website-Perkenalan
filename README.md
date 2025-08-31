<!DOCTYPE html>
<html lang="id">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Perkenalan Diri - Daniel</title>
    <link href="https://fonts.googleapis.com/css2?family=Montserrat:wght@500;700&display=swap" rel="stylesheet">
    <style>
        :root {
            --primary: #1e88e5;
            --accent: #ffd600;
            --bg: #f4f8fb;
            --card: #fff;
            --text: #222;
        }
        html {
            scroll-behavior: smooth;
        }
        body {
            margin: 0;
            padding: 0;
            font-family: 'Montserrat', Arial, sans-serif;
            background: var(--bg);
            color: var(--text);
        }
        .navbar {
            background: var(--card);
            box-shadow: 0 2px 12px rgba(30,136,229,0.04);
            position: fixed;
            width: 100%;
            top: 0;
            left: 0;
            z-index: 100;
        }
        .navbar-list {
            display: flex;
            justify-content: center;
            gap: 28px;
            padding: 0;
            margin: 0;
            list-style: none;
        }
        .navbar-list li a {
            display: block;
            text-decoration: none;
            color: var(--primary);
            font-weight: 600;
            font-size: 1.1rem;
            padding: 18px 0;
            transition: color 0.18s;
            cursor: pointer;
        }
        .navbar-list li a.active,
        .navbar-list li a:hover {
            color: var(--accent);
        }
        main {
            max-width: 700px;
            margin: 0 auto;
            padding: 120px 16px 32px 16px;
        }
        section {
            background: var(--card);
            border-radius: 18px;
            box-shadow: 0 8px 32px rgba(30,136,229,0.10);
            padding: 40px 32px;
            margin-bottom: 38px;
        }
        .hero {
            display: flex;
            flex-direction: column;
            align-items: center;
            text-align: center;
        }
        .hero-img {
            width: 120px;
            height: 120px;
            border-radius: 50%;
            object-fit: cover;
            border: 4px solid var(--primary);
            margin-bottom: 18px;
        }
        .hero-title {
            font-size: 2.3rem;
            font-weight: 700;
            color: var(--primary);
            margin-bottom: 8px;
        }
        .hero-subtitle {
            font-size: 1.18rem;
            font-weight: 500;
            margin-bottom: 16px;
        }
        .hero-desc {
            color: #444;
            font-size: 1rem;
            margin-bottom: 18px;
        }
        .social {
            display: flex;
            justify-content: center;
            gap: 14px;
            margin-top: 10px;
        }
        .social a {
            background: var(--primary);
            color: #fff;
            padding: 9px 14px;
            border-radius: 7px;
            font-size: 1rem;
            text-decoration: none;
            font-weight: 500;
            transition: background 0.18s;
        }
        .social a:hover {
            background: var(--accent);
            color: var(--text);
        }
        h2 {
            color: var(--primary);
            font-size: 1.3rem;
            margin-bottom: 16px;
        }
        ul.project-list {
            text-align: left;
            margin: 20px 0 0 0;
            padding-left: 18px;
        }
        ul.project-list li {
            margin-bottom: 8px;
        }
        @media (max-width: 700px) {
            main {
                padding: 110px 2vw 30px 2vw;
            }
            section {
                padding: 22px 8px;
            }
            .navbar-list {
                gap: 14px;
            }
            .hero-title {
                font-size: 1.5rem;
            }
            .hero-img {
                width: 85px;
                height: 85px;
            }
        }
    </style>
    <script>
        // Navbar active link on scroll
        document.addEventListener('DOMContentLoaded', function() {
            const links = document.querySelectorAll('.navbar-list li a');
            const sections = ['welcome', 'about', 'refleksi', 'project'].map(id => document.getElementById(id));
            function onScroll() {
                let idx = 0;
                sections.forEach((sec, i) => {
                    const top = sec.offsetTop - 90;
                    if (window.scrollY >= top) idx = i;
                });
                links.forEach((a, i) => a.classList.toggle('active', i === idx));
            }
            window.addEventListener('scroll', onScroll);

            // Smooth scroll on navbar click (offset for fixed navbar)
            links.forEach((link, i) => {
                link.addEventListener('click', function(e) {
                    e.preventDefault();
                    const section = sections[i];
                    const offset = section.getBoundingClientRect().top + window.scrollY - 80;
                    window.scrollTo({top: offset, behavior: 'smooth'});
                });
            });
        });
    </script>
</head>
<body>
    <!-- Navbar -->
    <nav class="navbar">
        <ul class="navbar-list">
            <li><a href="#welcome" class="active">Welcome</a></li>
            <li><a href="#about">About Me</a></li>
            <li><a href="#refleksi">Refleksi Diri</a></li>
            <li><a href="#project">My Project</a></li>
        </ul>
    </nav>
    <main>
        <!-- Welcome Section -->
        <section id="welcome" class="hero">
            <img class="hero-img" src="https://i.pravatar.cc/120?img=3" alt="Foto Profil">
            <div class="hero-title">Daniel Z</div>
            <div class="hero-subtitle">Mahasiswa & Web Developer</div>
            <div class="hero-desc">
                Selamat datang di website perkenalan diri saya.<br>
                Saya suka belajar teknologi baru dan membangun proyek digital!
            </div>
            <div class="social">
                <a href="mailto:danielzxcb@example.com">Email</a>
                <a href="https://github.com/danielzxcb-pixel" target="_blank">GitHub</a>
                <a href="https://instagram.com/yourusername" target="_blank">Instagram</a>
            </div>
        </section>

        <!-- About Me Section -->
        <section id="about">
            <h2>About Me</h2>
            <div>
                Saya Daniel, seorang mahasiswa yang antusias di bidang pengembangan web dan AI.
                Saya suka belajar hal baru, berkolaborasi, dan menciptakan solusi digital yang bermanfaat.
                Motto saya: <b>"Tetap berkembang, jangan takut gagal."</b>
            </div>
        </section>

        <!-- Refleksi Diri Section -->
        <section id="refleksi">
            <h2>Refleksi Diri</h2>
            <div>
                Dalam proses belajar web, saya pernah gagal deploy project dan menemukan banyak bug. Tapi dari situ saya belajar pentingnya ketekunan dan evaluasi diri.
                Refleksi diri membantu saya terus memperbaiki kemampuan dan karakter.
            </div>
        </section>

        <!-- My Project Section -->
        <section id="project">
            <h2>My Project</h2>
            <div>
                Beberapa project yang pernah saya buat:
                <ul class="project-list">
                    <li><b>Website Portofolio</b> - HTML, CSS, JS</li>
                    <li><b>AI Chatbot Sederhana</b> - Python & Flask</li>
                    <li><b>Landing Page UMKM</b> - ReactJS</li>
                </ul>
                <div style="margin-top:14px;">
                    <a href="https://github.com/danielzxcb-pixel?tab=repositories" target="_blank"
                        style="background:var(--accent);color:var(--text);padding:10px 20px;border-radius:8px;text-decoration:none;font-weight:600;">
                        Lihat Repository GitHub
                    </a>
                </div>
            </div>
        </section>
    </main>
</body>
</html>
