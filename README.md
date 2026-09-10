<!DOCTYPE html>
<html lang="es">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Nexos Tech & CCTV | Soluciones Tecnológicas y Seguridad</title>
    <!-- FontAwesome Icons -->
    <link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.4.0/css/all.min.css">
    <!-- Google Fonts -->
    <link href="https://fonts.googleapis.com/css2?family=Poppins:wght@300;400;600;700;800&display=swap" rel="stylesheet">
    <style>
        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
            font-family: 'Poppins', sans-serif;
            scroll-behavior: smooth;
        }

        :root {
            --primary: #0a192f;
            --secondary: #00d2ff;
            --accent: #0072ff;
            --card-bg: #112240;
            --text-light: #e6f1ff;
            --text-dim: #8892b0;
        }

        body {
            background-color: var(--primary);
            color: var(--text-light);
            line-height: 1.6;
            overflow-x: hidden;
        }

        /* --- BACKGROUND PARTICLES EFFECT --- */
        .bg-glow {
            position: fixed;
            width: 400px;
            height: 400px;
            background: radial-gradient(circle, rgba(0, 210, 255, 0.15) 0%, rgba(0,0,0,0) 70%);
            border-radius: 50%;
            pointer-events: none;
            z-index: 0;
            animation: floatGlow 10s infinite alternate ease-in-out;
        }

        @keyframes floatGlow {
            0% { transform: translate(-10%, -10%); }
            100% { transform: translate(50vw, 50vh); }
        }

        /* --- HEADER & NAVBAR --- */
        header {
            display: flex;
            justify-content: space-between;
            align-items: center;
            padding: 18px 8%;
            background: rgba(10, 25, 47, 0.85);
            backdrop-filter: blur(12px);
            position: fixed;
            width: 100%;
            top: 0;
            z-index: 1000;
            border-bottom: 1px solid rgba(0, 210, 255, 0.1);
            transition: all 0.3s ease;
        }

        .logo {
            font-size: 1.6rem;
            font-weight: 800;
            color: #fff;
            text-decoration: none;
            display: flex;
            align-items: center;
            gap: 12px;
        }

        .logo i {
            color: var(--secondary);
            animation: pulse 2s infinite;
        }

        .logo span {
            color: var(--secondary);
        }

        nav ul {
            display: flex;
            list-style: none;
            gap: 25px;
        }

        nav a {
            color: var(--text-light);
            text-decoration: none;
            font-weight: 500;
            position: relative;
            padding: 5px 0;
            transition: color 0.3s;
        }

        nav a::after {
            content: '';
            position: absolute;
            width: 0;
            height: 2px;
            bottom: 0;
            left: 0;
            background-color: var(--secondary);
            transition: width 0.3s ease-in-out;
        }

        nav a:hover {
            color: var(--secondary);
        }

        nav a:hover::after {
            width: 100%;
        }

        /* --- HERO SECTION --- */
        .hero {
            min-height: 100vh;
            display: flex;
            flex-direction: column;
            justify-content: center;
            align-items: center;
            text-align: center;
            padding: 120px 8% 60px;
            position: relative;
            z-index: 1;
        }

        .badge {
            background: rgba(0, 210, 255, 0.1);
            color: var(--secondary);
            padding: 6px 18px;
            border-radius: 20px;
            font-size: 0.85rem;
            font-weight: 600;
            border: 1px solid rgba(0, 210, 255, 0.3);
            margin-bottom: 20px;
            animation: fadeInDown 1s ease;
        }

        .hero h1 {
            font-size: 3.2rem;
            font-weight: 800;
            margin-bottom: 20px;
            animation: fadeInUp 1s ease;
        }

        .hero h1 span {
            background: linear-gradient(45deg, var(--secondary), #0072ff);
            -webkit-background-clip: text;
            -webkit-text-fill-color: transparent;
        }

        .hero p {
            font-size: 1.15rem;
            max-width: 750px;
            color: var(--text-dim);
            margin-bottom: 35px;
            animation: fadeInUp 1.2s ease;
        }

        .btn-group {
            display: flex;
            gap: 15px;
            animation: fadeInUp 1.4s ease;
        }

        .btn {
            padding: 14px 32px;
            border-radius: 30px;
            text-decoration: none;
            font-weight: 600;
            transition: all 0.3s ease;
            display: inline-flex;
            align-items: center;
            gap: 10px;
        }

        .btn-primary {
            background: linear-gradient(45deg, var(--accent), var(--secondary));
            color: #fff;
            box-shadow: 0 4px 20px rgba(0, 210, 255, 0.4);
        }

        .btn-primary:hover {
            transform: translateY(-4px);
            box-shadow: 0 8px 30px rgba(0, 210, 255, 0.6);
        }

        .btn-secondary {
            border: 2px solid var(--secondary);
            color: var(--secondary);
            background: transparent;
        }

        .btn-secondary:hover {
            background: rgba(0, 210, 255, 0.1);
            transform: translateY(-4px);
        }

        /* --- SERVICES SECTION --- */
        .services {
            padding: 100px 8%;
            position: relative;
            z-index: 1;
            background: rgba(13, 30, 54, 0.6);
        }

        .section-header {
            text-align: center;
            margin-bottom: 60px;
        }

        .section-header h2 {
            font-size: 2.3rem;
            margin-bottom: 10px;
        }

        .section-header p {
            color: var(--text-dim);
        }

        .grid {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(280px, 1fr));
            gap: 30px;
        }

        .card {
            background-color: var(--card-bg);
            padding: 35px 25px;
            border-radius: 16px;
            border: 1px solid rgba(255,255,255,0.05);
            transition: all 0.4s cubic-bezier(0.175, 0.885, 0.32, 1.275);
            position: relative;
            overflow: hidden;
        }

        .card::before {
            content: '';
            position: absolute;
            top: 0;
            left: 0;
            width: 100%;
            height: 4px;
            background: linear-gradient(90deg, var(--accent), var(--secondary));
            transform: scaleX(0);
            transition: transform 0.4s ease;
            transform-origin: left;
        }

        .card:hover {
            transform: translateY(-12px);
            box-shadow: 0 15px 35px rgba(0, 0, 0, 0.4);
            border-color: rgba(0, 210, 255, 0.3);
        }

        .card:hover::before {
            transform: scaleX(1);
        }

        .icon-box {
            width: 70px;
            height: 70px;
            background: rgba(0, 210, 255, 0.1);
            border-radius: 14px;
            display: flex;
            align-items: center;
            justify-content: center;
            margin-bottom: 25px;
            font-size: 1.8rem;
            color: var(--secondary);
            transition: all 0.3s;
        }

        .card:hover .icon-box {
            background: var(--secondary);
            color: var(--primary);
            transform: rotateY(360deg);
        }

        .card h3 {
            font-size: 1.3rem;
            margin-bottom: 15px;
        }

        .card p {
            color: var(--text-dim);
            font-size: 0.92rem;
        }

        /* --- STATS COUNTER SECTION --- */
        .stats {
            padding: 60px 8%;
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(200px, 1fr));
            gap: 20px;
            text-align: center;
            background: var(--primary);
        }

        .stat-item h3 {
            font-size: 2.5rem;
            color: var(--secondary);
            font-weight: 800;
        }

        .stat-item p {
            color: var(--text-dim);
            font-size: 0.9rem;
        }

        /* --- CONTACT SECTION --- */
        .contact {
            padding: 100px 8%;
            text-align: center;
            background: rgba(17, 34, 64, 0.4);
        }

        .contact-cards {
            display: flex;
            justify-content: center;
            gap: 30px;
            flex-wrap: wrap;
            margin-top: 40px;
        }

        .contact-card {
            background: var(--card-bg);
            padding: 25px 35px;
            border-radius: 12px;
            display: flex;
            align-items: center;
            gap: 15px;
            border: 1px solid rgba(255, 255, 255, 0.05);
            transition: 0.3s;
            text-decoration: none;
            color: var(--text-light);
        }

        .contact-card:hover {
            border-color: var(--secondary);
            transform: scale(1.05);
        }

        .contact-card i {
            font-size: 1.5rem;
            color: var(--secondary);
        }

        /* --- FLOATING WHATSAPP BUTTON --- */
        .whatsapp-float {
            position: fixed;
            bottom: 30px;
            right: 30px;
            width: 60px;
            height: 60px;
            background-color: #25d366;
            color: #fff;
            border-radius: 50%;
            display: flex;
            align-items: center;
            justify-content: center;
            font-size: 30px;
            box-shadow: 0 4px 15px rgba(37, 211, 102, 0.4);
            z-index: 1000;
            transition: all 0.3s;
            text-decoration: none;
            animation: pulseGlow 2s infinite;
        }

        .whatsapp-float:hover {
            transform: scale(1.15);
        }

        /* --- ANIMATIONS & KEYFRAMES --- */
        @keyframes pulse {
            0%, 100% { transform: scale(1); }
            50% { transform: scale(1.1); }
        }

        @keyframes pulseGlow {
            0% { box-shadow: 0 0 0 0 rgba(37, 211, 102, 0.7); }
            70% { box-shadow: 0 0 0 15px rgba(37, 211, 102, 0); }
            100% { box-shadow: 0 0 0 0 rgba(37, 211, 102, 0); }
        }

        @keyframes fadeInUp {
            from { opacity: 0; transform: translateY(30px); }
            to { opacity: 1; transform: translateY(0); }
        }

        @keyframes fadeInDown {
            from { opacity: 0; transform: translateY(-20px); }
            to { opacity: 1; transform: translateY(0); }
        }

        .reveal {
            opacity: 0;
            transform: translateY(40px);
            transition: all 0.8s ease;
        }

        .reveal.active {
            opacity: 1;
            transform: translateY(0);
        }

        /* --- FOOTER --- */
        footer {
            text-align: center;
            padding: 25px;
            background-color: #07111e;
            color: var(--text-dim);
            font-size: 0.85rem;
            border-top: 1px solid rgba(255,255,255,0.05);
        }

        @media (max-width: 768px) {
            header { flex-direction: column; gap: 15px; }
            .hero h1 { font-size: 2.2rem; }
            .btn-group { flex-direction: column; width: 100%; }
            .btn { width: 100%; justify-content: center; }
        }
    </style>
</head>
<body>

    <div class="bg-glow"></div>

    <!-- Header / Nav -->
    <header>
        <a href="#" class="logo">
            <i class="fa-solid fa-shield-halved"></i>
            Nexos <span>Tech & CCTV</span>
        </a>
        <nav>
            <ul>
                <li><a href="#inicio">Inicio</a></li>
                <li><a href="#servicios">Servicios</a></li>
                <li><a href="#contacto">Contacto</a></li>
            </ul>
        </nav>
    </header>

    <!-- Hero Section -->
    <section class="hero" id="inicio">
        <div class="badge"><i class="fa-solid fa-bolt"></i> Soluciones Profesionales en Ecuador</div>
        <h1>Tecnología, Redes y <span>Seguridad Electrónica</span></h1>
        <p>En <strong>Nexos Tech & CCTV</strong> ofrecemos soluciones integrales en instalación de videovigilancia, redes de alta velocidad y soporte informático especializado. Mantén tu negocio u hogar seguro y conectado.</p>
        <div class="btn-group">
            <a href="https://wa.me/593987654321?text=Hola,%20deseo%20más%20información%20sobre%20sus%20servicios" target="_blank" class="btn btn-primary">
                <i class="fa-brands fa-whatsapp"></i> Contactar por WhatsApp
            </a>
            <a href="#servicios" class="btn btn-secondary">Ver Servicios</a>
        </div>
    </section>

    <!-- Stats Section -->
    <section class="stats reveal">
        <div class="stat-item">
            <h3>100%</h3>
            <p>Garantía de Calidad</p>
        </div>
        <div class="stat-item">
            <h3>CCTV</h3>
            <p>Monitoreo HD / 4K</p>
        </div>
        <div class="stat-item">
            <h3>Redes</h3>
            <p>Fibra & Wi-Fi Estable</p>
        </div>
        <div class="stat-item">
            <h3>24/7</h3>
            <p>Soporte Confiable</p>
        </div>
    </section>

    <!-- Services Section -->
    <section class="services" id="servicios">
        <div class="section-header reveal">
            <h2>Nuestros Servicios Especializados</h2>
            <p>Tecnología avanzada adaptada a tus requerimientos</p>
        </div>
        <div class="grid">
            <div class="card reveal">
                <div class="icon-box"><i class="fa-solid fa-video"></i></div>
                <h3>Sistemas CCTV</h3>
                <p>Instalación, configuración y mantenimiento de cámaras IP y analógicas HD. Acceso y visualización remota desde tu smartphone.</p>
            </div>
            <div class="card reveal">
                <div class="icon-box"><i class="fa-solid fa-network-wired"></i></div>
                <h3>Redes y Conectividad</h3>
                <p>Diseño de redes LAN/Wi-Fi, cableado estructurado, configuración de routers MikroTik, switches y optimización de velocidad.</p>
            </div>
            <div class="card reveal">
                <div class="icon-box"><i class="fa-solid fa-laptop-code"></i></div>
                <h3>Soporte Informático</h3>
                <p>Mantenimiento preventivo y correctivo de PCs/laptops, limpieza de virus, actualización de componentes y sistemas operativos.</p>
            </div>
            <div class="card reveal">
                <div class="icon-box"><i class="fa-solid fa-server"></i></div>
                <h3>Infraestructura & Servidores</h3>
                <p>Implementación de respaldos, configuración de subredes y soluciones informáticas integrales para negocios.</p>
            </div>
        </div>
    </section>

    <!-- Contact Section -->
    <section class="contact" id="contacto">
        <div class="section-header reveal">
            <h2>¿Listo para proteger y optimizar tu espacio?</h2>
            <p>Atención directa por parte de especialistas</p>
        </div>
        <div class="contact-cards reveal">
            <a href="tel:+593987654321" class="contact-card">
                <i class="fa-solid fa-user-gear"></i>
                <div>
                    <strong>Tec. Oswaldo Quispe</strong>
                    <p style="font-size: 0.8rem; color: var(--text-dim);">Especialista Técnico</p>
                </div>
            </a>
            <a href="https://wa.me/593987654321" target="_blank" class="contact-card">
                <i class="fa-solid fa-phone"></i>
                <div>
                    <strong> WhatsApp / Teléfono</strong>
                    <p style="font-size: 0.8rem; color: var(--text-dim);">+593 98 765 4321</p>
                </div>
            </a>
        </div>
    </section>

    <!-- Floating WhatsApp Button -->
    <a href="https://wa.me/593987654321?text=Hola,%20necesito%20asistencia%20técnica" class="whatsapp-float" target="_blank" title="Escríbenos por WhatsApp">
        <i class="fa-brands fa-whatsapp"></i>
    </a>

    <!-- Footer -->
    <footer>
        <p>&copy; 2026 Nexos Tech & CCTV - Soluciones Informáticas y Seguridad. Todos los derechos reservados.</p>
    </footer>

    <!-- JavaScript for Animations -->
    <script>
        // Scroll Reveal Animation Functionality
        window.addEventListener('scroll', reveal);

        function reveal() {
            var reveals = document.querySelectorAll('.reveal');
            for (var i = 0; i < reveals.length; i++) {
                var windowHeight = window.innerHeight;
                var elementTop = reveals[i].getBoundingClientRect().top;
                var elementVisible = 100;

                if (elementTop < windowHeight - elementVisible) {
                    reveals[i].classList.add('active');
                }
            }
        }

        // Trigger reveal once on page load
        reveal();
    </script>
</body>
</html>
