---
layout: default
title: JFeelgood Art
permalink: /
---





<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>JFeelgood - Transform Through Art</title>
    <style>
        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
        }

        :root {
            --primary-cta: #2d5f4f;
            --text-dark: #2a2a2a;
            --bg-light: #fafafa;
            --accent-light: #f5f5f5;
        }

        body {
            font-family: Georgia, 'Times New Roman', serif;
            background-color: var(--bg-light);
            color: var(--text-dark);
            line-height: 1.6;
            overflow-x: hidden;
        }

        /* Sticky CTA Bar */
        .sticky-cta {
            position: fixed;
            bottom: 0;
            left: 0;
            right: 0;
            background: rgba(255, 255, 255, 0.98);
            backdrop-filter: blur(10px);
            padding: 15px 20px;
            box-shadow: 0 -2px 20px rgba(0, 0, 0, 0.1);
            z-index: 1000;
            transform: translateY(100%);
            transition: transform 0.3s ease;
        }

        .sticky-cta.visible {
            transform: translateY(0);
        }

        .sticky-cta-content {
            max-width: 1200px;
            margin: 0 auto;
            display: flex;
            align-items: center;
            justify-content: space-between;
            gap: 20px;
            flex-wrap: wrap;
        }

        .sticky-cta p {
            font-size: 14px;
            margin: 0;
        }

        .sticky-cta form {
            display: flex;
            gap: 10px;
            flex: 1;
            max-width: 400px;
        }

        /* Hero Section */
        .hero {
            height: 100vh;
            min-height: 600px;
            position: relative;
            display: flex;
            align-items: center;
            justify-content: center;
            background: linear-gradient(135deg, #667eea 0%, #764ba2 100%);
            overflow: hidden;
        }

        .hero-overlay {
            position: absolute;
            top: 0;
            left: 0;
            right: 0;
            bottom: 0;
            background: rgba(0, 0, 0, 0.3);
            z-index: 1;
        }

        .hero-content {
            position: relative;
            z-index: 2;
            text-align: center;
            color: white;
            padding: 20px;
            max-width: 800px;
            animation: fadeInUp 1s ease;
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
            font-size: clamp(2.5rem, 6vw, 4.5rem);
            margin-bottom: 20px;
            font-weight: 400;
            letter-spacing: 2px;
        }

        .hero p {
            font-size: clamp(1.1rem, 2vw, 1.4rem);
            margin-bottom: 40px;
            opacity: 0.95;
        }

        /* Container */
        .container {
            max-width: 1200px;
            margin: 0 auto;
            padding: 0 20px;
        }

        /* Section Styles */
        section {
            padding: 80px 0;
        }

        .section-title {
            font-size: clamp(2rem, 4vw, 3rem);
            text-align: center;
            margin-bottom: 50px;
            font-weight: 400;
        }

        /* Email Capture Section */
        .email-capture {
            background: var(--accent-light);
            padding: 60px 0;
        }

        .email-form {
            max-width: 600px;
            margin: 0 auto;
            text-align: center;
        }

        .email-form h2 {
            font-size: 2rem;
            margin-bottom: 15px;
        }

        .email-form p {
            margin-bottom: 30px;
            font-size: 1.1rem;
        }

        .form-group {
            display: flex;
            gap: 15px;
            flex-wrap: wrap;
        }

        input[type="email"] {
            flex: 1;
            min-width: 250px;
            padding: 15px 20px;
            border: 2px solid #ddd;
            border-radius: 4px;
            font-size: 16px;
            font-family: inherit;
            transition: border-color 0.3s;
        }

        input[type="email"]:focus {
            outline: none;
            border-color: var(--primary-cta);
        }

        .btn {
            padding: 15px 35px;
            background: var(--primary-cta);
            color: white;
            border: none;
            border-radius: 4px;
            font-size: 16px;
            font-family: inherit;
            cursor: pointer;
            transition: all 0.3s ease;
            text-decoration: none;
            display: inline-block;
        }

        .btn:hover {
            background: #1f4437;
            transform: translateY(-2px);
            box-shadow: 0 4px 12px rgba(45, 95, 79, 0.3);
        }

        .btn-secondary {
            background: white;
            color: var(--primary-cta);
            border: 2px solid var(--primary-cta);
        }

        .btn-secondary:hover {
            background: var(--primary-cta);
            color: white;
        }

        /* Book Feature Section */
        .book-feature {
            background: white;
        }

        .book-content {
            display: grid;
            grid-template-columns: 1fr 1fr;
            gap: 60px;
            align-items: center;
        }

        .book-image {
            text-align: center;
        }

        .book-cover {
            width: 100%;
            max-width: 400px;
            height: auto;
            box-shadow: 0 20px 60px rgba(0, 0, 0, 0.2);
            transition: transform 0.3s ease;
        }

        .book-cover:hover {
            transform: scale(1.05);
        }

        .book-info h2 {
            font-size: 2.5rem;
            margin-bottom: 20px;
        }

        .book-info p {
            font-size: 1.1rem;
            margin-bottom: 30px;
            line-height: 1.8;
        }

        /* Art Prints Gallery */
        .prints-gallery {
            background: var(--bg-light);
        }

        .gallery-grid {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(300px, 1fr));
            gap: 30px;
            margin-bottom: 40px;
        }

        .print-item {
            background: white;
            border-radius: 8px;
            overflow: hidden;
            transition: transform 0.3s ease, box-shadow 0.3s ease;
            cursor: pointer;
        }

        .print-item:hover {
            transform: translateY(-10px);
            box-shadow: 0 15px 40px rgba(0, 0, 0, 0.15);
        }

        .print-image {
            width: 100%;
            height: 350px;
            background: linear-gradient(135deg, #667eea 0%, #764ba2 100%);
            display: flex;
            align-items: center;
            justify-content: center;
            color: white;
            font-size: 1.2rem;
        }

        .print-info {
            padding: 20px;
            text-align: center;
        }

        .print-info h3 {
            font-size: 1.3rem;
            margin-bottom: 10px;
        }

        .print-price {
            font-size: 1.2rem;
            color: var(--primary-cta);
            font-weight: bold;
        }

        .gallery-cta {
            text-align: center;
        }

        /* Artist Bio Section */
        .artist-bio {
            background: white;
        }

        .bio-content {
            display: grid;
            grid-template-columns: 300px 1fr;
            gap: 60px;
            align-items: start;
        }

        .bio-image {
            width: 100%;
            height: 300px;
            background: linear-gradient(135deg, #667eea 0%, #764ba2 100%);
            border-radius: 8px;
        }

        .bio-text h2 {
            font-size: 2.5rem;
            margin-bottom: 20px;
        }

        .bio-text p {
            font-size: 1.1rem;
            margin-bottom: 20px;
            line-height: 1.8;
        }

        .social-links {
            display: flex;
            gap: 20px;
            margin-top: 30px;
        }

        .social-icon {
            width: 40px;
            height: 40px;
            background: var(--primary-cta);
            color: white;
            display: flex;
            align-items: center;
            justify-content: center;
            border-radius: 50%;
            text-decoration: none;
            transition: all 0.3s ease;
        }

        .social-icon:hover {
            background: #1f4437;
            transform: scale(1.1);
        }

        /* Footer */
        footer {
            background: var(--text-dark);
            color: white;
            padding: 60px 0 30px;
        }

        .footer-content {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(250px, 1fr));
            gap: 40px;
            margin-bottom: 40px;
        }

        .footer-section h3 {
            margin-bottom: 20px;
            font-size: 1.3rem;
        }

        .footer-section p,
        .footer-section a {
            color: rgba(255, 255, 255, 0.8);
            text-decoration: none;
            display: block;
            margin-bottom: 10px;
        }

        .footer-section a:hover {
            color: white;
        }

        .footer-bottom {
            border-top: 1px solid rgba(255, 255, 255, 0.1);
            padding-top: 30px;
            text-align: center;
            color: rgba(255, 255, 255, 0.6);
        }

        .success-message {
            display: none;
            padding: 15px;
            background: #d4edda;
            color: #155724;
            border-radius: 4px;
            margin-top: 15px;
        }

        /* Responsive Design */
        @media (max-width: 768px) {
            .book-content,
            .bio-content {
                grid-template-columns: 1fr;
            }

            .sticky-cta-content {
                flex-direction: column;
                text-align: center;
            }

            .sticky-cta form {
                max-width: 100%;
            }

            .form-group {
                flex-direction: column;
            }

            input[type="email"],
            .btn {
                width: 100%;
            }

            section {
                padding: 50px 0;
            }
        }
    </style>
</head>
<body>
    <!-- Navigation -->
    <nav style="background: white; box-shadow: 0 2px 10px rgba(0,0,0,0.05); position: sticky; top: 0; z-index: 1000;">
        <div style="max-width: 1200px; margin: 0 auto; padding: 20px 40px; display: flex; justify-content: space-between; align-items: center; flex-wrap: wrap; gap: 20px;">
            <a href="index.html" style="font-size: 1.5rem; font-weight: 600; color: var(--text-dark); text-decoration: none;">JFeelgood</a>
            <div style="display: flex; gap: 30px; align-items: center; flex-wrap: wrap;">
                <a href="index.html" style="color: var(--text-dark); text-decoration: none; transition: color 0.3s;">Home</a>
                <a href="assets/images/prints.html" style="color: var(--text-dark); text-decoration: none; transition: color 0.3s;">Art Prints</a>
                <a href="#book-feature" style="color: var(--text-dark); text-decoration: none; transition: color 0.3s;">Book</a>
                <a href="#artist-bio" style="color: var(--text-dark); text-decoration: none; transition: color 0.3s;">About</a>
                <a href="#email-capture" class="btn" style="padding: 10px 20px;">Subscribe</a>
            </div>
        </div>
    </nav>


 <img src="assets/images/JFeelgood_Montage.gif" 
     alt="JFeelgood_Montage" 
     style="max-width:200px; border-radius:12px; display:block; margin:1.5em auto 1em auto;" />

    <!-- Sticky CTA Bar -->
    <div class="sticky-cta" id="stickyCta">
        <div class="sticky-cta-content">
            <p><strong>Transform your perspective.</strong> Join our community for exclusive art insights.</p>
            <form onsubmit="handleEmailSubmit(event, 'sticky')">
                <input type="email" placeholder="Enter your email" required>
                <button type="submit" class="btn">Subscribe</button>
            </form>
        </div>
    </div>

    <!-- Hero Section -->
    <section class="hero">
        <div class="hero-overlay"></div>
        <div class="hero-content">
            <h1>Transform Through Art</h1>
            <p>Discover the intersection of creativity, self-discovery, and visual storytelling. Welcome to a journey of personal transformation through the power of artistic expression.</p>
            <a href="#email-capture" class="btn">Start Your Journey</a>
        </div>
    </section>

    <!-- Email Capture Section -->
    <section class="email-capture" id="email-capture">
        <div class="container">
            <div class="email-form">
                <h2>Join the Community</h2>
                <p>Get exclusive access to new artwork, inspiration for personal growth, and insights into the creative process.</p>
                <form onsubmit="handleEmailSubmit(event, 'main')">
                    <div class="form-group">
                        <input type="email" placeholder="Your email address" required>
                        <button type="submit" class="btn">Subscribe Now</button>
                    </div>
                </form>
                <div class="success-message" id="mainSuccess">
                    Thank you for subscribing! Check your email for confirmation.
                </div>
            </div>
        </div>
    </section>

    <!-- Book Feature Section -->
    <section class="book-feature" id="book-feature">
        <div class="container">
            <div class="book-content">
                <div class="book-image">
                    <div class="book-cover" style="background: linear-gradient(135deg, #667eea 0%, #764ba2 100%); display: flex; align-items: center; justify-content: center; color: white; font-size: 2rem; height: 500px;">
                        Thought Entropy
                    </div>
                </div>
                <div class="book-info">
                    <h2>Thought Entropy</h2>
                    <p>A transformative exploration of chaos, creativity, and the human condition. Thought Entropy invites you to embrace the beautiful disorder of your inner world and channel it into purposeful action.</p>
                    <p>Through powerful narratives and profound insights, discover how disorder can become your greatest source of creative energy and personal growth.</p>
                    <a href="https://www.amazon.com" target="_blank" class="btn">Buy on Amazon</a>
                </div>
            </div>
        </div>
    </section>

    <!-- Featured Art Prints -->
    <section class="prints-gallery" id="prints-gallery">
        <div class="container">
            <h2 class="section-title">Featured Art Prints</h2>
            <div class="gallery-grid">
                <div class="print-item">
                    <div class="print-image">Ethereal Dreams</div>
                    <div class="print-info">
                        <h3>Ethereal Dreams</h3>
                        <p class="print-price">$125</p>
                    </div>
                </div>
                <div class="print-item">
                    <div class="print-image">Inner Cosmos</div>
                    <div class="print-info">
                        <h3>Inner Cosmos</h3>
                        <p class="print-price">$150</p>
                    </div>
                </div>
                <div class="print-item">
                    <div class="print-image">Transformation</div>
                    <div class="print-info">
                        <h3>Transformation</h3>
                        <p class="print-price">$135</p>
                    </div>
                </div>
                <div class="print-item">
                    <div class="print-image">Mindful Chaos</div>
                    <div class="print-info">
                        <h3>Mindful Chaos</h3>
                        <p class="print-price">$140</p>
                    </div>
                </div>
            </div>
            <div class="gallery-cta">
                <a href="#" class="btn">Browse Full Print Shop</a>
            </div>
        </div>
    </section>

    <!-- Artist Bio -->
    <section class="artist-bio" id="artist-bio">
        <div class="container">
            <div class="bio-content">
                <div class="bio-image"></div>
                <div class="bio-text">
                    <h2>About the Artist</h2>
                    <p>JFeelgood is an artist dedicated to exploring the depths of human consciousness through visual storytelling. With a focus on personal transformation and self-discovery, each piece invites viewers to confront their own inner landscapes.</p>
                    <p>Inspired by the philosophy that chaos can become creation, and that our struggles can transform into our greatest strengths, JFeelgood's work bridges the gap between abstract expression and tangible emotional resonance.</p>
                    <p><strong>Mission:</strong> To inspire personal transformation through art that speaks to the universal human experience of growth, struggle, and ultimately, triumph.</p>
                    <div class="social-links">
                        <a href="https://instagram.com" target="_blank" class="social-icon" title="Instagram">
                            <svg width="20" height="20" fill="currentColor" viewBox="0 0 24 24">
                                <path d="M12 2.163c3.204 0 3.584.012 4.85.07 3.252.148 4.771 1.691 4.919 4.919.058 1.265.069 1.645.069 4.849 0 3.205-.012 3.584-.069 4.849-.149 3.225-1.664 4.771-4.919 4.919-1.266.058-1.644.07-4.85.07-3.204 0-3.584-.012-4.849-.07-3.26-.149-4.771-1.699-4.919-4.92-.058-1.265-.07-1.644-.07-4.849 0-3.204.013-3.583.07-4.849.149-3.227 1.664-4.771 4.919-4.919 1.266-.057 1.645-.069 4.849-.069zm0-2.163c-3.259 0-3.667.014-4.947.072-4.358.2-6.78 2.618-6.98 6.98-.059 1.281-.073 1.689-.073 4.948 0 3.259.014 3.668.072 4.948.2 4.358 2.618 6.78 6.98 6.98 1.281.058 1.689.072 4.948.072 3.259 0 3.668-.014 4.948-.072 4.354-.2 6.782-2.618 6.979-6.98.059-1.28.073-1.689.073-4.948 0-3.259-.014-3.667-.072-4.947-.196-4.354-2.617-6.78-6.979-6.98-1.281-.059-1.69-.073-4.949-.073zm0 5.838c-3.403 0-6.162 2.759-6.162 6.162s2.759 6.163 6.162 6.163 6.162-2.759 6.162-6.163c0-3.403-2.759-6.162-6.162-6.162zm0 10.162c-2.209 0-4-1.79-4-4 0-2.209 1.791-4 4-4s4 1.791 4 4c0 2.21-1.791 4-4 4zm6.406-11.845c-.796 0-1.441.645-1.441 1.44s.645 1.44 1.441 1.44c.795 0 1.439-.645 1.439-1.44s-.644-1.44-1.439-1.44z"/>
                            </svg>
                        </a>
                        <a href="https://facebook.com" target="_blank" class="social-icon" title="Facebook">
                            <svg width="20" height="20" fill="currentColor" viewBox="0 0 24 24">
                                <path d="M24 12.073c0-6.627-5.373-12-12-12s-12 5.373-12 12c0 5.99 4.388 10.954 10.125 11.854v-8.385H7.078v-3.47h3.047V9.43c0-3.007 1.792-4.669 4.533-4.669 1.312 0 2.686.235 2.686.235v2.953H15.83c-1.491 0-1.956.925-1.956 1.874v2.25h3.328l-.532 3.47h-2.796v8.385C19.612 23.027 24 18.062 24 12.073z"/>
                            </svg>
                        </a>
                        <a href="https://twitter.com" target="_blank" class="social-icon" title="Twitter">
                            <svg width="20" height="20" fill="currentColor" viewBox="0 0 24 24">
                                <path d="M23.953 4.57a10 10 0 01-2.825.775 4.958 4.958 0 002.163-2.723c-.951.555-2.005.959-3.127 1.184a4.92 4.92 0 00-8.384 4.482C7.69 8.095 4.067 6.13 1.64 3.162a4.822 4.822 0 00-.666 2.475c0 1.71.87 3.213 2.188 4.096a4.904 4.904 0 01-2.228-.616v.06a4.923 4.923 0 003.946 4.827 4.996 4.996 0 01-2.212.085 4.936 4.936 0 004.604 3.417 9.867 9.867 0 01-6.102 2.105c-.39 0-.779-.023-1.17-.067a13.995 13.995 0 007.557 2.209c9.053 0 13.998-7.496 13.998-13.985 0-.21 0-.42-.015-.63A9.935 9.935 0 0024 4.59z"/>
                            </svg>
                        </a>
                    </div>
                </div>
            </div>
        </div>
    </section>

    <!-- Footer -->
    <footer>
        <div class="container">
            <div class="footer-content">
                <div class="footer-section">
                    <h3>JFeelgood</h3>
                    <p>Transforming perspectives through art and self-discovery.</p>
                </div>
                <div class="footer-section">
                    <h3>Quick Links</h3>
                    <a href="#email-capture">Subscribe</a>
                    <a href="#book-feature">Thought Entropy</a>
                    <a href="#prints-gallery">Art Prints</a>
                    <a href="#artist-bio">About</a>
                </div>
                <div class="footer-section">
                    <h3>Stay Connected</h3>
                    <p>Join our mailing list for exclusive content and updates.</p>
                    <form onsubmit="handleEmailSubmit(event, 'footer')">
                        <div style="display: flex; gap: 10px; margin-top: 15px;">
                            <input type="email" placeholder="Your email" required style="flex: 1; padding: 10px; border: none; border-radius: 4px;">
                            <button type="submit" class="btn" style="padding: 10px 20px;">Join</button>
                        </div>
                    </form>
                    <div class="success-message" id="footerSuccess">
                        Thank you for subscribing!
                    </div>
                </div>
            </div>
            <div class="footer-bottom">
                <p>&copy; 2025 JFeelgood. All rights reserved. | <a href="#" style="color: inherit;">Privacy Policy</a></p>
            </div>
        </div>
    </footer>

    <script>
        // Show sticky CTA after 5 seconds
        setTimeout(() => {
            document.getElementById('stickyCta').classList.add('visible');
        }, 5000);

        // Handle email form submissions
        function handleEmailSubmit(event, formType) {
            event.preventDefault();
            const form = event.target;
            const email = form.querySelector('input[type="email"]').value;
            
            // Here you would integrate with your email service (Mailchimp, etc.)
            console.log('Email submitted:', email, 'from', formType, 'form');
            
            // Show success message
            if (formType === 'main') {
                document.getElementById('mainSuccess').style.display = 'block';
                setTimeout(() => {
                    document.getElementById('mainSuccess').style.display = 'none';
                }, 5000);
            } else if (formType === 'footer') {
                document.getElementById('footerSuccess').style.display = 'block';
                setTimeout(() => {
                    document.getElementById('footerSuccess').style.display = 'none';
                }, 5000);
            } else if (formType === 'sticky') {
                alert('Thank you for subscribing!');
            }
            
            form.reset();
        }

        // Smooth scrolling for anchor links
        document.querySelectorAll('a[href^="#"]').forEach(anchor => {
            anchor.addEventListener('click', function (e) {
                e.preventDefault();
                const target = document.querySelector(this.getAttribute('href'));
                if (target) {
                    target.scrollIntoView({
                        behavior: 'smooth',
                        block: 'start'
                    });
                }
            });
        });
    </script>
</body>
</html>
