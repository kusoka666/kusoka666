<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>PrimeLead Labs — AI-Powered Lead Intelligence</title>
    <link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.4.0/css/all.min.css">
    <style>
        /* ===== ROOT VARIABLES - CHANGE COLORS HERE ===== */
        :root {
            --color-bg: #0a0a0a;         /* Main background */
            --color-surface: #1a1a1a;    /* Card surfaces */
            --color-text: #ffffff;       /* Primary text */
            --color-text-muted: #b0b0b0; /* Secondary text */
            --color-accent: #4a4a4a;     /* Borders, accents */
            --color-primary: #808080;    /* Primary buttons/links */
            --border-radius: 8px;
            --shadow: 0 4px 12px rgba(0, 0, 0, 0.3);
            --transition: all 0.3s ease;
        }

        /* ===== BASE STYLES ===== */
        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
        }

        html {
            scroll-behavior: smooth;
            overflow-x: hidden;
        }

        body {
            font-family: 'Inter', 'Segoe UI', system-ui, -apple-system, sans-serif;
            color: var(--color-text);
            line-height: 1.6;
            overflow-x: hidden;
            position: relative;
            width: 100%;
        }

        /* ===== FIXED BACKGROUND ===== */
        .fixed-bg {
            position: fixed;
            top: 0;
            left: 0;
            width: 100%;
            height: 100%;
            background-image: url('https://images.unsplash.com/photo-1551288049-bebda4e38f71?ixlib=rb-4.0.3&auto=format&fit=crop&w=2000&q=80');
            background-size: cover;
            background-position: center;
            background-attachment: fixed;
            filter: blur(8px) brightness(0.4);
            z-index: -1;
        }

        /* ===== SCROLLING CONTENT ===== */
        .content-wrapper {
            position: relative;
            z-index: 1;
            background: rgba(10, 10, 10, 0.85);
            min-height: 100vh;
            width: 100%;
        }

        .container {
            width: 100%;
            max-width: 1200px;
            margin: 0 auto;
            padding: 0 20px;
        }

        /* ===== HEADER ===== */
        header {
            position: fixed;
            top: 0;
            left: 0;
            width: 100%;
            padding: 15px 0;
            background: rgba(26, 26, 26, 0.95);
            backdrop-filter: blur(10px);
            z-index: 1000;
            border-bottom: 1px solid var(--color-accent);
        }

        .header-container {
            display: flex;
            justify-content: space-between;
            align-items: center;
        }

        .logo {
            display: flex;
            align-items: center;
            gap: 10px;
            cursor: pointer;
        }

        .logo-img {
            width: 40px;
            height: 40px;
            background: var(--color-surface);
            border: 2px solid var(--color-primary);
            border-radius: 6px;
            display: flex;
            align-items: center;
            justify-content: center;
            font-weight: 700;
            font-size: 16px;
            color: var(--color-text);
        }

        .logo-text h1 {
            font-size: 20px;
            font-weight: 700;
            color: var(--color-text);
        }

        .logo-text p {
            font-size: 11px;
            color: var(--color-text-muted);
        }

        nav {
            display: flex;
            gap: 25px;
        }

        nav a {
            color: var(--color-text-muted);
            text-decoration: none;
            font-weight: 500;
            transition: var(--transition);
        }

        nav a:hover {
            color: var(--color-text);
        }

        /* ===== HERO SECTION ===== */
        .hero {
            padding: 140px 0 80px;
            text-align: center;
        }

        .eyebrow {
            display: inline-block;
            color: var(--color-text-muted);
            font-weight: 600;
            font-size: 14px;
            letter-spacing: 1px;
            margin-bottom: 15px;
            text-transform: uppercase;
        }

        .hero h1 {
            font-size: 2.8rem;
            font-weight: 700;
            line-height: 1.1;
            margin-bottom: 20px;
            color: var(--color-text);
        }

        .hero p {
            font-size: 1.1rem;
            color: var(--color-text-muted);
            margin-bottom: 30px;
            max-width: 600px;
            margin-left: auto;
            margin-right: auto;
        }

        .cta-buttons {
            display: flex;
            gap: 12px;
            justify-content: center;
            margin-bottom: 25px;
            flex-wrap: wrap;
        }

        .btn {
            padding: 12px 24px;
            border-radius: var(--border-radius);
            font-weight: 600;
            font-size: 14px;
            cursor: pointer;
            transition: var(--transition);
            border: none;
        }

        .btn-primary {
            background: var(--color-primary);
            color: var(--color-bg);
        }

        .btn-primary:hover {
            background: var(--color-text-muted);
            transform: translateY(-2px);
        }

        .btn-secondary {
            background: transparent;
            color: var(--color-text);
            border: 1px solid var(--color-primary);
        }

        .btn-secondary:hover {
            background: rgba(128, 128, 128, 0.1);
        }

        .badge {
            display: inline-flex;
            align-items: center;
            gap: 6px;
            padding: 8px 16px;
            background: rgba(128, 128, 128, 0.1);
            color: var(--color-text-muted);
            border: 1px solid var(--color-accent);
            border-radius: 20px;
            font-size: 12px;
            font-weight: 500;
        }

        /* ===== SECTIONS ===== */
        section {
            padding: 80px 0;
        }

        .section-header {
            text-align: center;
            margin-bottom: 50px;
        }

        .section-header h2 {
            font-size: 2.2rem;
            font-weight: 700;
            margin-bottom: 15px;
            color: var(--color-text);
        }

        .section-header p {
            font-size: 1rem;
            color: var(--color-text-muted);
            max-width: 700px;
            margin: 0 auto;
        }

        /* ===== SERVICES GRID ===== */
        .services-grid {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(300px, 1fr));
            gap: 20px;
        }

        .service-card {
            background: var(--color-surface);
            padding: 25px;
            border-radius: var(--border-radius);
            border: 1px solid var(--color-accent);
            transition: var(--transition);
        }

        .service-card:hover {
            transform: translateY(-5px);
            box-shadow: var(--shadow);
        }

        .service-icon {
            font-size: 2rem;
            margin-bottom: 15px;
            color: var(--color-primary);
        }

        .service-card h3 {
            font-size: 1.3rem;
            margin-bottom: 12px;
            color: var(--color-text);
        }

        .service-card p {
            color: var(--color-text-muted);
            line-height: 1.6;
        }

        /* ===== INDUSTRIES GRID - UPDATED WITH PROFESSIONAL CARDS ===== */
        .industries-grid {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(350px, 1fr));
            gap: 2rem;
        }

        .industry-card {
            background: rgba(15, 15, 15, 0.8);
            backdrop-filter: blur(10px);
            border-radius: 12px;
            padding: 2.5rem;
            border: 1px solid rgba(255, 255, 255, 0.08);
            box-shadow: 0 8px 32px rgba(0, 0, 0, 0.3);
            transition: all 0.4s cubic-bezier(0.25, 0.46, 0.45, 0.94);
            position: relative;
            overflow: hidden;
            cursor: pointer;
            height: auto;
        }

        .industry-card::before {
            content: '';
            position: absolute;
            top: 0;
            left: -100%;
            width: 100%;
            height: 100%;
            background: linear-gradient(90deg, 
                transparent, 
                rgba(255, 255, 255, 0.03), 
                transparent);
            transition: left 0.6s ease;
        }

        .industry-card:hover::before {
            left: 100%;
        }

        .industry-card:hover {
            transform: translateY(-8px);
            box-shadow: 0 15px 40px rgba(0, 0, 0, 0.5);
            border-color: rgba(255, 255, 255, 0.15);
            background: rgba(20, 20, 20, 0.85);
        }

        .card-header {
            margin-bottom: 1.8rem;
            position: relative;
            text-align: center;
            z-index: 2;
        }

        .card-icon-container {
            position: relative;
            width: 80px;
            height: 80px;
            margin: 0 auto 1.5rem;
            display: flex;
            align-items: center;
            justify-content: center;
        }

        .card-icon-bg {
            position: absolute;
            width: 100%;
            height: 100%;
            background: rgba(255, 255, 255, 0.03);
            border-radius: 50%;
            transition: all 0.4s ease;
            border: 1px solid rgba(255, 255, 255, 0.1);
        }

        .industry-card:hover .card-icon-bg {
            background: rgba(255, 255, 255, 0.08);
            transform: scale(1.1);
            box-shadow: 0 0 30px var(--industry-glow);
        }

        .card-icon {
            font-size: 2.2rem;
            color: var(--industry-color);
            position: relative;
            z-index: 2;
            transition: all 0.4s ease;
        }

        .industry-card:hover .card-icon {
            transform: scale(1.1);
            filter: brightness(1.3);
        }

        .card-title {
            font-size: 1.6rem;
            font-weight: 700;
            margin-bottom: 0.5rem;
            letter-spacing: 1px;
            text-transform: uppercase;
            color: var(--color-text);
            transition: color 0.3s ease;
        }

        .industry-card:hover .card-title {
            color: var(--industry-color);
        }

        .card-subtitle {
            font-size: 1rem;
            color: var(--color-text-muted);
            font-weight: 500;
            letter-spacing: 0.5px;
        }

        .divider {
            height: 1px;
            background: linear-gradient(90deg, transparent, var(--industry-color), transparent);
            margin: 1.5rem 0;
            opacity: 0.5;
            transition: all 0.4s ease;
        }

        .industry-card:hover .divider {
            opacity: 1;
            background: linear-gradient(90deg, transparent, var(--industry-color), var(--industry-color), transparent);
        }

        .card-content {
            margin-bottom: 1.5rem;
            position: relative;
            z-index: 2;
        }

        .feature-list {
            list-style: none;
        }

        .feature-list li {
            padding: 0.8rem 0;
            position: relative;
            padding-left: 1.5rem;
            font-size: 0.95rem;
            color: var(--color-text-muted);
            border-bottom: 1px solid rgba(255, 255, 255, 0.03);
            transition: all 0.3s ease;
        }

        .feature-list li:last-child {
            border-bottom: none;
        }

        .feature-list li::before {
            content: '→';
            position: absolute;
            left: 0;
            font-weight: normal;
            color: var(--industry-color);
            transition: all 0.3s ease;
        }

        .industry-card:hover .feature-list li {
            color: var(--color-text);
            border-bottom-color: rgba(255, 255, 255, 0.08);
        }

        .industry-card:hover .feature-list li::before {
            transform: translateX(3px);
        }

        .card-footer {
            border-top: 1px solid rgba(255, 255, 255, 0.05);
            padding-top: 1.5rem;
            text-align: center;
            font-size: 0.85rem;
            color: var(--color-text-muted);
            letter-spacing: 1px;
            position: relative;
            z-index: 2;
            transition: all 0.3s ease;
        }

        .industry-card:hover .card-footer {
            color: var(--industry-color);
            border-top-color: rgba(255, 255, 255, 0.1);
        }

        /* Industry-specific colors */
        .real-estate {
            --industry-color: #8b5cf6;
            --industry-glow: rgba(139, 92, 246, 0.3);
        }
        
        .healthcare {
            --industry-color: #10b981;
            --industry-glow: rgba(16, 185, 129, 0.3);
        }
        
        .home-services {
            --industry-color: #f59e0b;
            --industry-glow: rgba(245, 158, 11, 0.3);
        }
        
        .legal {
            --industry-color: #ef4444;
            --industry-glow: rgba(239, 68, 68, 0.3);
        }
        
        .finance {
            --industry-color: #06b6d4;
            --industry-glow: rgba(6, 182, 212, 0.3);
        }
        
        .tech {
            --industry-color: #6366f1;
            --industry-glow: rgba(99, 102, 241, 0.3);
        }
        
        .automotive {
            --industry-color: #f97316;
            --industry-glow: rgba(249, 115, 22, 0.3);
        }
        
        .local-business {
            --industry-color: #84cc16;
            --industry-glow: rgba(132, 204, 22, 0.3);
        }
        
        .custom {
            --industry-color: #ec4899;
            --industry-glow: rgba(236, 72, 153, 0.3);
        }

        /* ===== CONTACT SECTION ===== */
        .contact-grid {
            display: grid;
            grid-template-columns: 1fr 1fr;
            gap: 30px;
        }

        .contact-form {
            background: var(--color-surface);
            padding: 30px;
            border-radius: var(--border-radius);
            border: 1px solid var(--color-accent);
        }

        .form-group {
            margin-bottom: 15px;
        }

        .form-group label {
            display: block;
            margin-bottom: 5px;
            font-weight: 500;
            color: var(--color-text);
        }

        .form-group input,
        .form-group select,
        .form-group textarea {
            width: 100%;
            padding: 12px;
            border-radius: var(--border-radius);
            border: 1px solid var(--color-accent);
            background: var(--color-bg);
            color: var(--color-text);
            font-family: inherit;
            transition: var(--transition);
        }

        .form-group input:focus,
        .form-group select:focus,
        .form-group textarea:focus {
            outline: none;
            border-color: var(--color-primary);
        }

        .form-group textarea {
            min-height: 100px;
            resize: vertical;
        }

        .contact-info {
            background: var(--color-surface);
            padding: 30px;
            border-radius: var(--border-radius);
            border: 1px solid var(--color-accent);
        }

        .contact-info h3 {
            font-size: 1.3rem;
            margin-bottom: 20px;
            color: var(--color-text);
        }

        .contact-methods {
            display: flex;
            flex-direction: column;
            gap: 15px;
        }

        .contact-method {
            display: flex;
            align-items: center;
            gap: 12px;
        }

        .contact-icon {
            width: 40px;
            height: 40px;
            border-radius: 50%;
            background: var(--color-bg);
            border: 1px solid var(--color-accent);
            display: flex;
            align-items: center;
            justify-content: center;
            font-size: 16px;
            color: var(--color-primary);
        }

        .contact-details {
            flex: 1;
        }

        .contact-details h4 {
            font-size: 1rem;
            margin-bottom: 3px;
            color: var(--color-text);
        }

        .contact-details p,
        .contact-details a {
            color: var(--color-text-muted);
            text-decoration: none;
            transition: var(--transition);
            font-size: 0.9rem;
        }

        .contact-details a:hover {
            color: var(--color-primary);
        }

        /* ===== MODAL ===== */
        .modal-backdrop {
            position: fixed;
            top: 0;
            left: 0;
            width: 100%;
            height: 100%;
            background: rgba(0, 0, 0, 0.8);
            backdrop-filter: blur(5px);
            display: flex;
            align-items: center;
            justify-content: center;
            z-index: 2000;
            opacity: 0;
            visibility: hidden;
            transition: opacity 0.3s ease, visibility 0.3s ease;
        }

        .modal-backdrop.active {
            opacity: 1;
            visibility: visible;
        }

        .modal {
            background: var(--color-surface);
            border-radius: var(--border-radius);
            width: 90%;
            max-width: 500px;
            padding: 25px;
            border: 1px solid var(--color-accent);
            transform: translateY(20px);
            transition: transform 0.3s ease;
            position: relative;
        }

        .modal-backdrop.active .modal {
            transform: translateY(0);
        }

        .modal-close {
            position: absolute;
            top: 15px;
            right: 15px;
            background: none;
            border: none;
            color: var(--color-text-muted);
            font-size: 20px;
            cursor: pointer;
            transition: var(--transition);
        }

        .modal-close:hover {
            color: var(--color-text);
        }

        .modal h3 {
            font-size: 1.5rem;
            margin-bottom: 15px;
            color: var(--color-text);
            text-align: center;
        }

        .modal p {
            color: var(--color-text-muted);
            margin-bottom: 20px;
            text-align: center;
        }

        /* ===== FOOTER ===== */
        footer {
            background: var(--color-bg);
            padding: 40px 0 20px;
            border-top: 1px solid var(--color-accent);
        }

        .footer-content {
            display: flex;
            justify-content: space-between;
            align-items: center;
            flex-wrap: wrap;
            gap: 20px;
            margin-bottom: 30px;
        }

        .footer-logo {
            flex: 1;
            min-width: 200px;
        }

        .footer-text {
            color: var(--color-text-muted);
            line-height: 1.6;
            max-width: 300px;
            font-size: 0.9rem;
        }

        .footer-links {
            display: flex;
            flex-direction: column;
            gap: 10px;
        }

        .footer-links a {
            color: var(--color-text-muted);
            text-decoration: none;
            transition: var(--transition);
            font-size: 0.9rem;
        }

        .footer-links a:hover {
            color: var(--color-primary);
        }

        .footer-bottom {
            text-align: center;
            padding-top: 20px;
            border-top: 1px solid var(--color-accent);
            color: var(--color-text-muted);
            font-size: 0.8rem;
        }

        /* ===== RESPONSIVE DESIGN ===== */
        @media (max-width: 768px) {
            nav {
                display: none;
            }
            
            .hero {
                padding: 120px 0 60px;
            }
            
            .hero h1 {
                font-size: 2rem;
            }
            
            .cta-buttons {
                flex-direction: column;
            }
            
            .btn {
                width: 100%;
            }
            
            .services-grid,
            .industries-grid {
                grid-template-columns: 1fr;
            }
            
            .contact-grid {
                grid-template-columns: 1fr;
            }
            
            .footer-content {
                flex-direction: column;
                text-align: center;
            }
            
            .industry-card {
                padding: 2rem;
            }
            
            .card-title {
                font-size: 1.4rem;
            }
            
            .card-icon-container {
                width: 70px;
                height: 70px;
            }
            
            .card-icon {
                font-size: 1.8rem;
            }
        }

        @media (max-width: 480px) {
            .hero h1 {
                font-size: 1.8rem;
            }
            
            .section-header h2 {
                font-size: 1.8rem;
            }
            
            .container {
                padding: 0 15px;
            }
            
            .industry-card {
                padding: 1.5rem;
            }
        }
    </style>
</head>
<body>
    <!-- Fixed Background -->
    <div class="fixed-bg"></div>
    
    <!-- Scrolling Content -->
    <div class="content-wrapper">
        <!-- Header -->
        <header>
            <div class="container header-container">
                <div class="logo" onclick="scrollToTop()">
                    <div class="logo-img">PL</div>
                    <div class="logo-text">
                        <h1>PrimeLead Labs</h1>
                        <p>AI-Powered Lead Intelligence</p>
                    </div>
                </div>
                <nav>
                    <a href="#home">Home</a>
                    <a href="#about">About</a>
                    <a href="#services">Services</a>
                    <a href="#industries">Industries</a>
                    <a href="#contact">Contact</a>
                </nav>
            </div>
        </header>

        <!-- Hero Section -->
        <section class="hero" id="home">
            <div class="container">
                <div class="hero-content">
                    <div class="eyebrow">Stop Chasing Noise. Start Closing Conversions.</div>
                    <h1>Global AI-Powered Lead Intelligence</h1>
                    <p>PrimeLead Labs delivers surgically precise, verified prospect intelligence—not just another list. We supply your sales team with high-intent, contact-ready opportunities that protect your time, budget, and reputation.</p>
                    <div class="cta-buttons">
                        <button class="btn btn-primary" onclick="openModal('proof-of-concept')">Request a Proof of Concept</button>
                        <button class="btn btn-secondary" onclick="openModal('consultation')">Speak with Intelligence Operations</button>
                    </div>
                    <div class="badge">
                        <i class="fas fa-star"></i>
                        Pioneer Partnership Program: Priority onboarding and tailored terms
                    </div>
                </div>
            </div>
        </section>

        <!-- About Section -->
        <section class="about" id="about">
            <div class="container">
                <div class="section-header">
                    <h2>Why Settle for Hope When You Can Invest in Certainty?</h2>
                </div>
                <div class="about-content">
                    <p>PrimeLead Labs was founded on a disruptive principle: that most "lead generation" is a costly distraction. While others sell you bulk data and call it pipeline, we deliver validated opportunity.</p>
                    <p>We are not a data broker. We are your intelligence partner. Our proprietary AI engine scours global digital marketplaces, public records, and community signals in real-time. It distinguishes intent from inquiry, verifies motivation, and curates only the prospects your team can actually close.</p>
                    <p>Partnering with us is a strategic declaration—a commitment to efficiency, velocity, and ROI. You will allocate resources smarter, move faster, and win more deals with less friction. We are built for leaders who value results, not excuses.</p>
                </div>
            </div>
        </section>

        <!-- Services Section -->
        <section id="services">
            <div class="container">
                <div class="section-header">
                    <h2>Precision-Fit Intelligence for Every Stage of Growth</h2>
                    <p>We offer three tiers of verified lead intelligence, each including evidence snapshots, validated contact channels, firmographic enrichment, and our proprietary Motivation Score.</p>
                </div>
                <div class="services-grid">
                    <!-- Service cards will be generated by JavaScript -->
                </div>
            </div>
        </section>

        <!-- Industries Section -->
        <section class="industries" id="industries">
            <div class="container">
                <div class="section-header">
                    <h2>High-Intent Leads for High-Stakes Industries</h2>
                    <p>We focus on niches where lead quality directly dictates revenue. Our intelligence is tailored to the unique triggers and motivations of each sector.</p>
                </div>
                <div class="industries-grid">
                    <!-- Industry cards will be generated by JavaScript -->
                </div>
            </div>
        </section>

        <!-- Contact Section -->
        <section id="contact">
            <div class="container">
                <div class="section-header">
                    <h2>Prove Our Value Before You Commit</h2>
                    <p>Experience the PrimeLead difference with a complimentary, customized lead sample. No obligation, just proof.</p>
                </div>
                <div class="contact-grid">
                    <div class="contact-form">
                        <h3>Request Your Sample</h3>
                        <form id="contactForm">
                            <div class="form-group">
                                <label for="name">Name</label>
                                <input type="text" id="name" required>
                            </div>
                            <div class="form-group">
                                <label for="email">Email</label>
                                <input type="email" id="email" required>
                            </div>
                            <div class="form-group">
                                <label for="company">Company (optional)</label>
                                <input type="text" id="company">
                            </div>
                            <div class="form-group">
                                <label for="interest">Industry / Interest</label>
                                <select id="interest">
                                    <!-- Options will be generated by JavaScript -->
                                </select>
                            </div>
                            <div class="form-group">
                                <label for="message">Short message (optional)</label>
                                <textarea id="message"></textarea>
                            </div>
                            <button type="submit" class="btn btn-primary" style="width: 100%">Request Strategic Sample</button>
                        </form>
                    </div>
                    <div class="contact-info">
                        <h3>Contact Channels</h3>
                        <div class="contact-methods">
                            <!-- Contact methods will be generated by JavaScript -->
                        </div>
                    </div>
                </div>
            </div>
        </section>

        <!-- Footer -->
        <footer>
            <div class="container">
                <div class="footer-content">
                    <div class="footer-logo">
                        <div class="logo">
                            <div class="logo-img">PL</div>
                            <div class="logo-text">
                                <h1>PrimeLead Labs</h1>
                                <p>AI-Powered Lead Intelligence</p>
                            </div>
                        </div>
                        <p class="footer-text">We source high-intent prospects worldwide, verify contact and conversion signals, and deliver only what your sales team can convert.</p>
                    </div>
                    <div class="footer-links">
                        <a href="#home">Home</a>
                        <a href="#about">About</a>
                        <a href="#services">Services</a>
                        <a href="#industries">Industries</a>
                        <a href="#contact">Contact</a>
                    </div>
                </div>
                <div class="footer-bottom">
                    <p>© 2024 PrimeLead Labs — Automated Lead Intelligence • intelligence@primeleadlabs.com • Mon–Fri 09:00–18:00 ET</p>
                    <p>We source leads from public records, listings and marketplaces. Buyers are responsible for complying with local contact and privacy laws.</p>
                </div>
            </div>
        </footer>
    </div>

    <!-- Contact Modal -->
    <div class="modal-backdrop" id="modalBackdrop">
        <div class="modal">
            <button class="modal-close" onclick="closeModal()">&times;</button>
            <h3 id="modalTitle">Request a Proof of Concept</h3>
            <p id="modalDescription">We'll prepare a tailored sample and next steps.</p>
            <form id="modalForm">
                <div class="form-group">
                    <label for="modalName">Your Name</label>
                    <input type="text" id="modalName" required>
                </div>
                <div class="form-group">
                    <label for="modalEmail">Email Address</label>
                    <input type="email" id="modalEmail" required>
                </div>
                <div class="form-group">
                    <label for="modalCompany">Company (optional)</label>
                    <input type="text" id="modalCompany">
                </div>
                <div class="form-group">
                    <label for="modalIndustry">Industry Interest</label>
                    <select id="modalIndustry">
                        <!-- Options will be generated by JavaScript -->
                    </select>
                </div>
                <div class="form-group">
                    <label for="modalMessage">Message (optional)</label>
                    <textarea id="modalMessage"></textarea>
                </div>
                <button type="submit" class="btn btn-primary" style="width: 100%">Send Request</button>
            </form>
        </div>
    </div>

    <script>
        // ===== CENTRALIZED CONTENT OBJECT =====
        // CHANGE ALL TEXT, IMAGES, AND CONTACT INFO HERE
        const CONTENT = {
            // Company Info
            company: {
                name: "PrimeLead Labs",
                tagline: "AI-Powered Lead Intelligence",
                email: "intelligence@primeleadlabs.com",
                telegram: "https://t.me/PrimeLeadLabs",
                whatsapp: "https://wa.me/13055551234",
                signal: "https://signal.me/#p/+13055551234",
                hours: "Mon–Fri 09:00–18:00 ET",
                urgent: "Telegram or WhatsApp"
            },

            // Background Image (Replace with your own)
            backgroundImage: "https://images.unsplash.com/photo-1551288049-bebda4e38f71?ixlib=rb-4.0.3&auto=format&fit=crop&w=2000&q=80",

            // Hero Section
            hero: {
                eyebrow: "Stop Chasing Noise. Start Closing Conversions.",
                title: "Global AI-Powered Lead Intelligence",
                description: "PrimeLead Labs delivers surgically precise, verified prospect intelligence—not just another list. We supply your sales team with high-intent, contact-ready opportunities that protect your time, budget, and reputation.",
                primaryButton: "Request a Proof of Concept",
                secondaryButton: "Speak with Intelligence Operations",
                badge: "Pioneer Partnership Program: Priority onboarding and tailored terms"
            },

            // About Section
            about: {
                title: "Why Settle for Hope When You Can Invest in Certainty?",
                content: [
                    "PrimeLead Labs was founded on a disruptive principle: that most \"lead generation\" is a costly distraction. While others sell you bulk data and call it pipeline, we deliver validated opportunity.",
                    "We are not a data broker. We are your intelligence partner. Our proprietary AI engine scours global digital marketplaces, public records, and community signals in real-time. It distinguishes intent from inquiry, verifies motivation, and curates only the prospects your team can actually close.",
                    "Partnering with us is a strategic declaration—a commitment to efficiency, velocity, and ROI. You will allocate resources smarter, move faster, and win more deals with less friction. We are built for leaders who value results, not excuses."
                ]
            },

            // Services
            services: [
                {
                    icon: "fas fa-rocket",
                    title: "Pilot Packs (Exclusive Intelligence)",
                    description: "Tightly curated, exclusive leads for immediate outreach. Delivered within 24 hours with a 7-day replacement guarantee."
                },
                {
                    icon: "fas fa-layer-group",
                    title: "Shared Lists (Volume Intelligence)",
                    description: "High-velocity, non-exclusive lists sold to a limited buyer pool for maximum outreach volume."
                },
                {
                    icon: "fas fa-stream",
                    title: "Subscription Feeds (Real-Time Intelligence)",
                    description: "A continuous, API-driven stream of pre-qualified leads delivered directly to your CRM."
                },
                {
                    icon: "fas fa-database",
                    title: "Data Enrichment & Context",
                    description: "Parcel IDs, transaction history, firmographics, and public record links."
                },
                {
                    icon: "fas fa-chart-line",
                    title: "Motivation Scoring & Prioritization",
                    description: "Algorithmic Motivation Score ensuring your team engages only high-probability prospects."
                },
                {
                    icon: "fas fa-shield-alt",
                    title: "Compliance & Audit Assurance",
                    description: "Verifiable snapshot and timestamp for every lead, providing a clear audit trail."
                }
            ],

            // Industries - Updated with professional card structure
            industries: [
                {
                    title: "REAL ESTATE",
                    subtitle: "Property Intelligence Network",
                    icon: "fas fa-building",
                    features: [
                        "Predictive Market Analytics",
                        "Buyer/Seller Matching Algorithms",
                        "Investment Opportunity Scoring",
                        "Neighborhood Growth Forecasting"
                    ],
                    class: "real-estate"
                },
                {
                    title: "HEALTHCARE",
                    subtitle: "Acquisition Signals",
                    icon: "fas fa-heartbeat",
                    features: [
                        "Market Consolidation Trends",
                        "Target Identification",
                        "Regulatory Compliance Monitoring",
                        "Patient Demand Analytics"
                    ],
                    class: "healthcare"
                },
                {
                    title: "HOME SERVICES",
                    subtitle: "Market Signals",
                    icon: "fas fa-home",
                    features: [
                        "Qualified Local Professional Matching",
                        "Instant Customer Connection Platform",
                        "Service Demand Analytics",
                        "Project Readiness Scoring"
                    ],
                    class: "home-services"
                },
                {
                    title: "LEGAL",
                    subtitle: "Case Intake Solutions",
                    icon: "fas fa-gavel",
                    features: [
                        "Litigation-Ready Client Identification",
                        "Case Merit Evaluation Algorithms",
                        "Specialty Practice Matching",
                        "Settlement Probability Forecasting"
                    ],
                    class: "legal"
                },
                {
                    title: "FINANCE",
                    subtitle: "Lending Intelligence",
                    icon: "fas fa-chart-line",
                    features: [
                        "Credit Qualification Algorithms",
                        "Investment Readiness Scoring",
                        "Portfolio Optimization Insights",
                        "Market Opportunity Identification"
                    ],
                    class: "finance"
                },
                {
                    title: "TECH & SAAS",
                    subtitle: "Buyer Signals",
                    icon: "fas fa-laptop-code",
                    features: [
                        "Software Adoption Prediction",
                        "Enterprise Readiness Evaluation",
                        "Competitive Migration Signals",
                        "Implementation Timeline Forecasting"
                    ],
                    class: "tech"
                },
                {
                    title: "AUTOMOTIVE",
                    subtitle: "Marketplace Intelligence",
                    icon: "fas fa-car",
                    features: [
                        "High-Intent Seller Identification",
                        "Vehicle Valuation Analytics",
                        "Market Demand Forecasting",
                        "Dealership Opportunity Scoring"
                    ],
                    class: "automotive"
                },
                {
                    title: "LOCAL BUSINESS",
                    subtitle: "Commerce Network",
                    icon: "fas fa-store",
                    features: [
                        "Verified Owner Intent Analysis",
                        "Business Valuation Metrics",
                        "Local Market Opportunity Scoring",
                        "Acquisition Readiness Evaluation"
                    ],
                    class: "local-business"
                },
                {
                    title: "CUSTOM SOLUTIONS",
                    subtitle: "Pipeline Intelligence",
                    icon: "fas fa-cogs",
                    features: [
                        "Tailored Lead Stream Development",
                        "Niche Market Intelligence",
                        "Custom Algorithm Configuration",
                        "Dedicated Pipeline Management"
                    ],
                    class: "custom"
                }
            ],

            // Modal Content
            modal: {
                'proof-of-concept': {
                    title: 'Request a Proof of Concept',
                    description: "We'll prepare a tailored sample and next steps for your evaluation."
                },
                'consultation': {
                    title: 'Schedule a Consultation',
                    description: 'Speak with our intelligence operations team to discuss your specific needs.'
                }
            }
        };

        // ===== INITIALIZE WEBSITE =====
        document.addEventListener('DOMContentLoaded', function() {
            // Set background image
            document.querySelector('.fixed-bg').style.backgroundImage = `url('${CONTENT.backgroundImage}')`;
            
            // Render hero section
            document.querySelector('.eyebrow').textContent = CONTENT.hero.eyebrow;
            document.querySelector('.hero h1').textContent = CONTENT.hero.title;
            document.querySelector('.hero p').textContent = CONTENT.hero.description;
            document.querySelector('.btn-primary').textContent = CONTENT.hero.primaryButton;
            document.querySelector('.btn-secondary').textContent = CONTENT.hero.secondaryButton;
            document.querySelector('.badge').innerHTML = `<i class="fas fa-star"></i> ${CONTENT.hero.badge}`;
            
            // Render about section
            document.querySelector('#about .section-header h2').textContent = CONTENT.about.title;
            const aboutContent = document.querySelector('.about-content');
            aboutContent.innerHTML = CONTENT.about.content.map(p => `<p>${p}</p>`).join('');
            
            // Render services
            const servicesGrid = document.querySelector('.services-grid');
            servicesGrid.innerHTML = CONTENT.services.map(service => `
                <div class="service-card">
                    <div class="service-icon"><i class="${service.icon}"></i></div>
                    <h3>${service.title}</h3>
                    <p>${service.description}</p>
                </div>
            `).join('');
            
            // Render industries with professional cards
            const industriesGrid = document.querySelector('.industries-grid');
            industriesGrid.innerHTML = CONTENT.industries.map(industry => `
                <div class="industry-card ${industry.class}" onclick="industryClick('${industry.title}')">
                    <div class="card-header">
                        <div class="card-icon-container">
                            <div class="card-icon-bg"></div>
                            <i class="${industry.icon} card-icon"></i>
                        </div>
                        <div class="card-title">${industry.title}</div>
                        <div class="card-subtitle">${industry.subtitle}</div>
                        <div class="divider"></div>
                    </div>
                    <div class="card-content">
                        <ul class="feature-list">
                            ${industry.features.map(feature => `<li>${feature}</li>`).join('')}
                        </ul>
                    </div>
                    <div class="card-footer">
                        FUTURE OF DATA DISCOVERY
                    </div>
                </div>
            `).join('');
            
            // Render contact form options
            const interestSelect = document.getElementById('interest');
            const modalInterestSelect = document.getElementById('modalIndustry');
            interestSelect.innerHTML = modalInterestSelect.innerHTML = `
                <option value="">Select an industry</option>
                ${CONTENT.industries.map(industry => `<option value="${industry.title}">${industry.title}</option>`).join('')}
                <option value="other">Other</option>
            `;
            
            // Render contact methods
            const contactMethods = document.querySelector('.contact-methods');
            contactMethods.innerHTML = `
                <div class="contact-method">
                    <div class="contact-icon"><i class="fas fa-envelope"></i></div>
                    <div class="contact-details">
                        <h4>Email</h4>
                        <a href="mailto:${CONTENT.company.email}">${CONTENT.company.email}</a>
                    </div>
                </div>
                <div class="contact-method">
                    <div class="contact-icon"><i class="fab fa-telegram"></i></div>
                    <div class="contact-details">
                        <h4>Telegram</h4>
                        <a href="${CONTENT.company.telegram}" target="_blank">t.me/PrimeLeadLabs</a>
                    </div>
                </div>
                <div class="contact-method">
                    <div class="contact-icon"><i class="fab fa-whatsapp"></i></div>
                    <div class="contact-details">
                        <h4>WhatsApp</h4>
                        <a href="${CONTENT.company.whatsapp}" target="_blank">+1 (305) 555-1234</a>
                    </div>
                </div>
                <div class="contact-method">
                    <div class="contact-icon"><i class="fas fa-comment"></i></div>
                    <div class="contact-details">
                        <h4>Signal</h4>
                        <a href="${CONTENT.company.signal}" target="_blank">+1 (305) 555-1234</a>
                    </div>
                </div>
                <div class="contact-method">
                    <div class="contact-icon"><i class="fas fa-clock"></i></div>
                    <div class="contact-details">
                        <h4>Business Hours</h4>
                        <p>${CONTENT.company.hours}</p>
                    </div>
                </div>
                <div class="contact-method">
                    <div class="contact-icon"><i class="fas fa-bolt"></i></div>
                    <div class="contact-details">
                        <h4>Urgent Inquiries</h4>
                        <p>${CONTENT.company.urgent}</p>
                    </div>
                </div>
            `;
            
            // Set up form submissions
            document.getElementById('contactForm').addEventListener('submit', function(e) {
                e.preventDefault();
                alert('Thank you for your request! We will contact you shortly with your custom lead sample.');
                this.reset();
            });
            
            document.getElementById('modalForm').addEventListener('submit', function(e) {
                e.preventDefault();
                alert('Thank you for your request! We will contact you shortly.');
                this.reset();
                closeModal();
            });
            
            // Add animations to industry cards
            const industryCards = document.querySelectorAll('.industry-card');
            const observer = new IntersectionObserver((entries) => {
                entries.forEach(entry => {
                    if (entry.isIntersecting) {
                        entry.target.style.opacity = 1;
                        entry.target.style.transform = 'translateY(0)';
                        entry.target.style.transition = 'opacity 0.5s ease, transform 0.5s ease';
                    }
                });
            }, { threshold: 0.1 });
            
            industryCards.forEach(card => {
                card.style.opacity = 0;
                card.style.transform = 'translateY(20px)';
                observer.observe(card);
            });
        });

        // ===== MODAL FUNCTIONS =====
        function openModal(type) {
            const modal = document.getElementById('modalBackdrop');
            const modalTitle = document.getElementById('modalTitle');
            const modalDescription = document.getElementById('modalDescription');
            
            if (CONTENT.modal[type]) {
                modalTitle.textContent = CONTENT.modal[type].title;
                modalDescription.textContent = CONTENT.modal[type].description;
            }
            
            modal.classList.add('active');
            document.body.style.overflow = 'hidden';
        }

        function closeModal() {
            const modal = document.getElementById('modalBackdrop');
            modal.classList.remove('active');
            document.body.style.overflow = 'auto';
        }

        // ===== UTILITY FUNCTIONS =====
        function scrollToTop() {
            window.scrollTo({ top: 0, behavior: 'smooth' });
        }

        function industryClick(industry) {
            openModal('proof-of-concept');
            document.getElementById('modalIndustry').value = industry;
        }

        // Close modal when clicking outside
        document.getElementById('modalBackdrop').addEventListener('click', function(e) {
            if (e.target === this) {
                closeModal();
            }
        });

        // Smooth scrolling for navigation links
        document.querySelectorAll('nav a').forEach(anchor => {
            anchor.addEventListener('click', function(e) {
                e.preventDefault();
                const targetId = this.getAttribute('href');
                const targetElement = document.querySelector(targetId);
                
                if (targetElement) {
                    const headerHeight = document.querySelector('header').offsetHeight;
                    const targetPosition = targetElement.offsetTop - headerHeight;
                    
                    window.scrollTo({
                        top: targetPosition,
                        behavior: 'smooth'
                    });
                }
            });
        });

        // Fix for horizontal scrolling
        window.addEventListener('resize', function() {
            document.body.style.overflowX = 'hidden';
        });
    </script>
</body>
</html>.   