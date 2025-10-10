
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

        /* Navigation */
        nav {
            background: white;
            box-shadow: 0 2px 10px rgba(0,0,0,0.05);
            position: sticky;
            top: 0;
            z-index: 1000;
        }

        .nav-container {
            max-width: 1400px;
            margin: 0 auto;
            padding: 20px 40px;
            display: flex;
            justify-content: space-between;
            align-items: center;
        }

        .nav-logo {
            font-size: 1.5rem;
            font-weight: 600;
            color: var(--text-dark);
            text-decoration: none;
        }

        .menu-button {
            background: none;
            border: none;
            font-size: 1.8rem;
            cursor: pointer;
            padding: 5px 10px;
            color: var(--text-dark);
            display: flex;
            align-items: center;
            gap: 8px;
            transition: color 0.3s;
        }

        .menu-button:hover {
            color: var(--primary-cta);
        }

        .menu-button span {
            font-size: 0.9rem;
            font-family: Georgia, serif;
        }

        .dropdown-menu {
            position: absolute;
            top: 100%;
            right: 40px;
            background: white;
            box-shadow: 0 8px 30px rgba(0,0,0,0.15);
            border-radius: 8px;
            overflow: hidden;
            min-width: 200px;
            display: none;
        }

        .dropdown-menu.active {
            display: block;
        }

        .dropdown-menu a {
            display: block;
            padding: 15px 25px;
            color: var(--text-dark);
            text-decoration: none;
            transition: background 0.3s;
            border-bottom: 1px solid #f0f0f0;
        }

        .dropdown-menu a:last-child {
            border-bottom: none;
        }

        .dropdown-menu a:hover {
            background: var(--accent-light);
            color: var(--primary-cta);
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

        /* Container */
        .container {
            max-width: 1400px;
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
            margin-bottom: 20px;
            font-weight: 400;
        }

        .section-subtitle {
            text-align: center;
            font-size: 1.1rem;
            color: #666;
            margin-bottom: 50px;
            max-width: 700px;
            margin-left: auto;
            margin-right: auto;
        }

        /* Carousel Section */
        .carousel-section {
            background: white;
            padding: 80px 0;
        }

        .carousel-container {
            position: relative;
            max-width: 900px;
            margin: 0 auto;
            padding: 0 60px;
        }

        .carousel-wrapper {
            overflow: hidden;
            border-radius: 12px;
            box-shadow: 0 10px 40px rgba(0, 0, 0, 0.15);
        }

        .carousel-track {
            display: flex;
            transition: transform 0.4s ease;
        }

        .carousel-slide {
            min-width: 100%;
            flex-shrink: 0;
        }

        .carousel-card {
            background: white;
            display: flex;
            flex-direction: column;
        }

        .carousel-image-container {
            position: relative;
            width: 100%;
            padding-bottom: 140%;
            background: var(--accent-light);
            overflow: hidden;
        }

        .carousel-image {
            position: absolute;
            top: 0;
            left: 0;
            width: 100%;
            height: 100%;
            object-fit: cover;
        }

        .carousel-details {
            padding: 30px;
            text-align: center;
        }

        .carousel-title {
            font-size: 1.5rem;
            margin-bottom: 10px;
            color: var(--text-dark);
        }

        .carousel-number {
            font-size: 1rem;
            color: #666;
            margin-bottom: 15px;
        }

        .carousel-specs {
            font-size: 0.95rem;
            color: #888;
            margin-bottom: 20px;
            line-height: 1.6;
        }

        .carousel-price {
            font-size: 1.8rem;
            color: var(--primary-cta);
            font-weight: bold;
            margin-bottom: 20px;
        }

        .carousel-controls {
            position: absolute;
            top: 50%;
            transform: translateY(-50%);
            width: 100%;
            display: flex;
            justify-content: space-between;
            pointer-events: none;
            z-index: 10;
        }

        .carousel-btn {
            pointer-events: all;
            background: rgba(255, 255, 255, 0.95);
            border: none;
            width: 50px;
            height: 50px;
            border-radius: 50%;
            font-size: 28px;
            cursor: pointer;
            display: flex;
            align-items: center;
            justify-content: center;
            box-shadow: 0 4px 16px rgba(0, 0, 0, 0.2);
            transition: all 0.3s;
            color: var(--text-dark);
        }

        .carousel-btn:hover {
            background: white;
            transform: scale(1.1);
            box-shadow: 0 6px 20px rgba(0, 0, 0, 0.3);
        }

        .carousel-btn:active {
            transform: scale(0.95);
        }

        .carousel-info {
            text-align: center;
            margin-top: 30px;
        }

        .carousel-counter {
            display: inline-block;
            padding: 12px 24px;
            background: var(--accent-light);
            border-radius: 25px;
            font-weight: 600;
            font-size: 1rem;
            color: var(--text-dark);
        }

        /* Book Section */
        .book-section {
            background: var(--bg-light);
        }

        .book-content {
            display: grid;
            grid-template-columns: 1fr 1fr;
            gap: 60px;
            align-items: center;
            max-width: 1200px;
            margin: 0 auto;
        }

        .book-image {
            text-align: center;
        }

        .book-cover {
            width: 100%;
            max-width: 400px;
            height: 500px;
            box-shadow: 0 20px 60px rgba(0, 0, 0, 0.2);
            transition: transform 0.3s ease;
            display: flex;
            align-items: center;
            justify-content: center;
            background: linear-gradient(135deg, #667eea 0%, #764ba2 100%);
            color: white;
            font-size: 2rem;
            border-radius: 4px;
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
            margin-bottom: 20px;
            line-height: 1.8;
        }

        /* Artist Bio */
        .bio-section {
            background: white;
        }

        .bio-content {
            display: grid;
            grid-template-columns: 300px 1fr;
            gap: 60px;
            align-items: start;
            max-width: 1200px;
            margin: 0 auto;
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
            padding: 40px 20px;
            text-align: center;
        }

        footer a {
            color: rgba(255, 255, 255, 0.8);
            text-decoration: none;
        }

        footer a:hover {
            color: white;
        }

        /* Responsive Design */
        @media (max-width: 768px) {
            .nav-container {
                padding: 15px 20px;
            }

            .nav-logo {
                font-size: 1.3rem;
            }

            .menu-button {
                font-size: 1.5rem;
            }

            .menu-button span:first-child {
                display: none;
            }

            .dropdown-menu {
                right: 20px;
                left: 20px;
                min-width: auto;
            }

            .hero {
                min-height: 500px;
                padding: 40px 20px;
            }

            .hero h1 {
                font-size: 2rem;
                margin-bottom: 15px;
            }

            .hero p {
                font-size: 1rem;
                margin-bottom: 30px;
            }

            section {
                padding: 50px 0;
            }

            .section-title {
                font-size: 1.8rem;
                margin-bottom: 15px;
            }

            .section-subtitle {
                font-size: 1rem;
                margin-bottom: 30px;
            }

            .carousel-container {
                padding: 0 15px;
            }

            .carousel-btn {
                width: 40px;
                height: 40px;
                font-size: 22px;
            }

            .carousel-details {
                padding: 20px;
            }

            .carousel-title {
                font-size: 1.2rem;
            }

            .carousel-price {
                font-size: 1.5rem;
            }

            .carousel-counter {
                padding: 10px 20px;
                font-size: 0.9rem;
            }

            .book-content {
                grid-template-columns: 1fr;
                gap: 30px;
            }

            .book-cover {
                max-width: 300px;
                height: 400px;
                font-size: 1.5rem;
                margin: 0 auto;
            }

            .book-info h2 {
                font-size: 1.8rem;
            }

            .book-info p {
                font-size: 1rem;
            }

            .bio-content {
                grid-template-columns: 1fr;
                gap: 30px;
            }

            .bio-image {
                max-width: 300px;
                margin: 0 auto;
            }

            .bio-text h2 {
                font-size: 1.8rem;
            }

            .bio-text p {
                font-size: 1rem;
            }

            .social-links {
                justify-content: center;
            }
        }

        @media (max-width: 480px) {
            .hero h1 {
                font-size: 1.8rem;
            }

            .section-title {
                font-size: 1.5rem;
            }

            .carousel-btn {
                width: 35px;
                height: 35px;
                font-size: 20px;
            }

            .book-info h2,
            .bio-text h2 {
                font-size: 1.5rem;
            }

            .btn {
                padding: 12px 25px;
                font-size: 15px;
            }
        }
    </style>
</head>
<body>
    <!-- Navigation -->
    <nav>
        <div class="nav-container">
            <a href="#" class="nav-logo">JFeelgood</a>
            <button class="menu-button" id="menuButton" onclick="toggleMenu()">
                <span>Menu</span>
                <span id="menuIcon">☰</span>
            </button>
            <div class="dropdown-menu" id="dropdownMenu">
                <a href="#hero">Home</a>
                <a href="#art-prints" onclick="closeMenu()">Art Prints</a>
                <a href="#book" onclick="closeMenu()">Book</a>
                <a href="#about" onclick="closeMenu()">About</a>
            </div>
        </div>
    </nav>

    <!-- Hero Section -->
    <section class="hero" id="hero">
        <div class="hero-overlay"></div>
        <div class="hero-content">
            <h1>Transform Through Art</h1>
            <p>Discover the intersection of creativity, self-discovery, and visual storytelling. Welcome to a journey of personal transformation through the power of artistic expression.</p>
            <a href="#art-prints" class="btn">Explore Art Collection</a>
        </div>
    </section>

    <!-- Art Prints Carousel -->
    <section class="carousel-section" id="art-prints">
        <div class="container">
            <h2 class="section-title">Art Collection</h2>
            <p class="section-subtitle">Browse through our complete collection of 155 original art prints. Each piece is professionally printed on premium paper (2.5" x 3.5") and presented in a magnetically sealed acrylic case.</p>
            
            <div class="carousel-container">
                <div class="carousel-wrapper">
                    <div class="carousel-track" id="carouselTrack">
                        <!-- Slides will be dynamically generated -->
                    </div>
                </div>
                <div class="carousel-controls">
                    <button class="carousel-btn" onclick="moveCarousel(-1)" aria-label="Previous">‹</button>
                    <button class="carousel-btn" onclick="moveCarousel(1)" aria-label="Next">›</button>
                </div>
            </div>
            
            <div class="carousel-info">
                <span class="carousel-counter" id="carouselCounter">1 / 155</span>
            </div>
        </div>
    </section>

    <!-- Book Section -->
    <section class="book-section" id="book">
        <div class="container">
            <div class="book-content">
                <div class="book-image">
                    <div class="book-cover">Thought Entropy</div>
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

    <!-- Artist Bio -->
    <section class="bio-section" id="about">
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
        <p>&copy; 2025 JFeelgood. All rights reserved.</p>
    </footer>

    <script>
        // Menu toggle
        function toggleMenu() {
            const menu = document.getElementById('dropdownMenu');
            const icon = document.getElementById('menuIcon');
            menu.classList.toggle('active');
            icon.textContent = menu.classList.contains('active') ? '✕' : '☰';
        }

        function closeMenu() {
            const menu = document.getElementById('dropdownMenu');
            const icon = document.getElementById('menuIcon');
            menu.classList.remove('active');
            icon.textContent = '☰';
        }

        document.addEventListener('click', (e) => {
            const menu = document.getElementById('dropdownMenu');
            const button = document.getElementById('menuButton');
            if (!menu.contains(e.target) && !button.contains(e.target)) {
                closeMenu();
            }
        });

        // Generate all 155 products
        const products = [];
        const basePrice = 125;
        
        for (let i = 1; i <= 155; i++) {
            const num = String(i).padStart(3, '0');
            const priceVariation = Math.floor(Math.random() * 50) - 25;
            const price = basePrice + priceVariation;
            
            products.push({
                id: i,
                number: num,
                title: `JFeelgoodArt${num}`,
                image: `JFeelgoodArt${num}.jpg`,
                specs: '2.5" x 3.5" premium print in magnetically sealed acrylic case',
                price: price
            });
        }

        // Generate carousel
        const track = document.getElementById('carouselTrack');
        products.forEach(product => {
            const slide = document.createElement('div');
            slide.className = 'carousel-slide';
            
            slide.innerHTML = `
                <div class="carousel-card">
                    <div class="carousel-image-container">
                        <img src="${product.image}" alt="${product.title}" class="carousel-image" 
                             onerror="this.src='data:image/svg+xml,%3Csvg xmlns=%22http://www.w3.org/2000/svg%22 viewBox=%220 0 400 560%22%3E%3Crect fill=%22%23667eea%22 width=%22400%22 height=%22560%22/%3E%3Ctext x=%2250%25%22 y=%2250%25%22 font-family=%22Arial%22 font-size=%2224%22 fill=%22white%22 text-anchor=%22middle%22 dominant-baseline=%22middle%22%3E${product.title}%3C/text%3E%3C/svg%3E'">
                    </div>
                    <div class="carousel-details">
                        <div class="carousel-title">${product.title}</div>
                        <div class="carousel-number">#${product.number}</div>
                        <div class="carousel-specs">${product.specs}</div>
                        <div class="carousel-price">$${product.price}</div>
                        <button class="btn" onclick="addToCart(${product.id})">Add to Cart</button>
                    </div>
                </div>
            `;
            
            track.appendChild(slide);
        });

        // Carousel functionality
        let currentSlide = 0;
        const totalSlides = 155;

        function updateCarousel() {
            const track = document.getElementById('carouselTrack');
            track.style.transform = `translateX(-${currentSlide * 100}%)`;
            document.getElementById('carouselCounter').textContent = `${currentSlide + 1} / ${totalSlides}`;
        }

        function moveCarousel(direction) {
            currentSlide += direction;
            if (currentSlide < 0) currentSlide = totalSlides - 1;
            if (currentSlide >= totalSlides) currentSlide = 0;
            updateCarousel();
        }

        // Touch swipe support
        let touchStartX = 0;
        let touchEndX = 0;

        const carouselWrapper = document.querySelector('.carousel-wrapper');
        carouselWrapper.addEventListener('touchstart', (e) => {
            touchStartX = e.changedTouches[0].screenX;
        });

        carouselWrapper.addEventListener('touchend', (e) => {
            touchEndX = e.changedTouches[0].screenX;
            handleSwipe();
        });

        function handleSwipe() {
            if (touchEndX < touchStartX - 50) {
                moveCarousel(1);
            }
            if (touchEndX > touchStartX + 50) {
                moveCarousel(-1);
            }
        }

        // Add to cart
        function addToCart(productI
