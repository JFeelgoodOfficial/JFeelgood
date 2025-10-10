<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Featured Art Prints - JFeelgood</title>
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
        }

        /* Header/Navigation */
        header {
            background: white;
            box-shadow: 0 2px 10px rgba(0, 0, 0, 0.05);
            position: sticky;
            top: 0;
            z-index: 100;
        }

        nav {
            max-width: 1400px;
            margin: 0 auto;
            padding: 20px 40px;
            display: flex;
            justify-content: space-between;
            align-items: center;
        }

        .logo {
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

        .dropdown-menu a.cta-link {
            background: var(--primary-cta);
            color: white;
            font-weight: 600;
        }

        .dropdown-menu a.cta-link:hover {
            background: #1f4437;
        }

        .nav-links {
            display: flex;
            gap: 30px;
            align-items: center;
        }

        .nav-links a {
            color: var(--text-dark);
            text-decoration: none;
            transition: color 0.3s;
        }

        .nav-links a:hover {
            color: var(--primary-cta);
        }

        /* Hero Section */
        .page-hero {
            background: linear-gradient(135deg, #667eea 0%, #764ba2 100%);
            color: white;
            padding: 80px 40px 60px;
            text-align: center;
        }

        .page-hero h1 {
            font-size: clamp(2.5rem, 5vw, 4rem);
            margin-bottom: 20px;
            font-weight: 400;
        }

        .page-hero p {
            font-size: 1.2rem;
            max-width: 700px;
            margin: 0 auto 30px;
            opacity: 0.95;
        }

        /* Filter/Sort Bar */
        .controls-bar {
            background: white;
            padding: 20px 40px;
            border-bottom: 1px solid #e0e0e0;
            position: sticky;
            top: 72px;
            z-index: 99;
        }

        .controls-container {
            max-width: 1400px;
            margin: 0 auto;
            display: flex;
            justify-content: space-between;
            align-items: center;
            flex-wrap: wrap;
            gap: 20px;
        }

        .controls-left {
            display: flex;
            gap: 15px;
            align-items: center;
            flex-wrap: wrap;
        }

        .search-box {
            position: relative;
        }

        .search-box input {
            padding: 10px 40px 10px 15px;
            border: 2px solid #ddd;
            border-radius: 4px;
            font-size: 14px;
            font-family: inherit;
            width: 250px;
            transition: border-color 0.3s;
        }

        .search-box input:focus {
            outline: none;
            border-color: var(--primary-cta);
        }

        .search-icon {
            position: absolute;
            right: 12px;
            top: 50%;
            transform: translateY(-50%);
            color: #999;
        }

        select {
            padding: 10px 15px;
            border: 2px solid #ddd;
            border-radius: 4px;
            font-size: 14px;
            font-family: inherit;
            background: white;
            cursor: pointer;
            transition: border-color 0.3s;
        }

        select:focus {
            outline: none;
            border-color: var(--primary-cta);
        }

        .results-count {
            color: #666;
            font-size: 14px;
        }

        .view-toggle {
            display: flex;
            gap: 10px;
        }

        .view-btn {
            padding: 8px 12px;
            border: 2px solid #ddd;
            background: white;
            cursor: pointer;
            border-radius: 4px;
            transition: all 0.3s;
        }

        .view-btn.active {
            background: var(--primary-cta);
            border-color: var(--primary-cta);
            color: white;
        }

        /* Main Content */
        .container {
            max-width: 1400px;
            margin: 0 auto;
            padding: 40px;
        }

        /* Carousel for mobile */
        .carousel-container-full {
            display: none;
            position: relative;
            margin-bottom: 40px;
        }

        .carousel-wrapper-full {
            overflow: hidden;
            border-radius: 8px;
        }

        .carousel-track-full {
            display: flex;
            transition: transform 0.3s ease;
        }

        .carousel-slide-full {
            min-width: 100%;
            flex-shrink: 0;
            padding: 0 10px;
        }

        .carousel-controls-full {
            position: absolute;
            top: 50%;
            transform: translateY(-50%);
            width: 100%;
            display: flex;
            justify-content: space-between;
            padding: 0 10px;
            pointer-events: none;
            z-index: 10;
        }

        .carousel-btn-full {
            pointer-events: all;
            background: rgba(255, 255, 255, 0.95);
            border: none;
            width: 50px;
            height: 50px;
            border-radius: 50%;
            font-size: 24px;
            cursor: pointer;
            display: flex;
            align-items: center;
            justify-content: center;
            box-shadow: 0 4px 16px rgba(0, 0, 0, 0.3);
            transition: all 0.3s;
            color: var(--text-dark);
        }

        .carousel-btn-full:hover {
            background: white;
            transform: scale(1.1);
        }

        .carousel-btn-full:active {
            transform: scale(0.95);
        }

        .carousel-info {
            text-align: center;
            margin-top: 20px;
            font-size: 14px;
            color: #666;
        }

        .carousel-counter {
            display: inline-block;
            padding: 8px 16px;
            background: var(--accent-light);
            border-radius: 20px;
            font-weight: 600;
        }

        /* Gallery Grid */
        .gallery {
            display: grid;
            grid-template-columns: repeat(auto-fill, minmax(280px, 1fr));
            gap: 30px;
            margin-bottom: 60px;
        }

        .gallery.list-view {
            grid-template-columns: 1fr;
        }

        /* Print Card */
        .print-card {
            background: white;
            border-radius: 8px;
            overflow: hidden;
            box-shadow: 0 2px 10px rgba(0, 0, 0, 0.08);
            transition: all 0.3s ease;
            cursor: pointer;
            display: flex;
            flex-direction: column;
        }

        .print-card:hover {
            transform: translateY(-8px);
            box-shadow: 0 12px 30px rgba(0, 0, 0, 0.15);
        }

        .list-view .print-card {
            flex-direction: row;
            max-height: 200px;
        }

        .list-view .print-card:hover {
            transform: translateY(0);
            box-shadow: 0 4px 15px rgba(0, 0, 0, 0.12);
        }

        .print-image-container {
            position: relative;
            width: 100%;
            padding-bottom: 140%;
            background: var(--accent-light);
            overflow: hidden;
        }

        .list-view .print-image-container {
            width: 200px;
            padding-bottom: 0;
            flex-shrink: 0;
        }

        .print-image {
            position: absolute;
            top: 0;
            left: 0;
            width: 100%;
            height: 100%;
            object-fit: cover;
            transition: transform 0.3s ease;
        }

        .print-card:hover .print-image {
            transform: scale(1.05);
        }

        .print-details {
            padding: 20px;
            flex-grow: 1;
            display: flex;
            flex-direction: column;
        }

        .list-view .print-details {
            justify-content: center;
        }

        .print-title {
            font-size: 1.1rem;
            font-weight: 600;
            margin-bottom: 8px;
            color: var(--text-dark);
        }

        .print-number {
            font-size: 0.9rem;
            color: #666;
            margin-bottom: 10px;
        }

        .print-specs {
            font-size: 0.85rem;
            color: #888;
            margin-bottom: 15px;
            line-height: 1.5;
        }

        .print-price {
            font-size: 1.3rem;
            color: var(--primary-cta);
            font-weight: bold;
            margin-top: auto;
        }

        .print-actions {
            display: flex;
            gap: 10px;
            margin-top: 15px;
        }

        .btn {
            padding: 12px 24px;
            background: var(--primary-cta);
            color: white;
            border: none;
            border-radius: 4px;
            font-size: 14px;
            font-family: inherit;
            cursor: pointer;
            transition: all 0.3s ease;
            text-decoration: none;
            display: inline-block;
            text-align: center;
            flex: 1;
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
            background: var(--accent-light);
            transform: translateY(-2px);
        }

        /* Modal */
        .modal {
            display: none;
            position: fixed;
            top: 0;
            left: 0;
            right: 0;
            bottom: 0;
            background: rgba(0, 0, 0, 0.9);
            z-index: 1000;
            align-items: center;
            justify-content: center;
            padding: 20px;
        }

        .modal.active {
            display: flex;
        }

        .modal-content {
            background: white;
            border-radius: 8px;
            max-width: 900px;
            width: 100%;
            max-height: 90vh;
            overflow-y: auto;
            position: relative;
        }

        .modal-close {
            position: absolute;
            top: 20px;
            right: 20px;
            background: white;
            border: none;
            font-size: 30px;
            cursor: pointer;
            width: 40px;
            height: 40px;
            border-radius: 50%;
            display: flex;
            align-items: center;
            justify-content: center;
            box-shadow: 0 2px 10px rgba(0, 0, 0, 0.2);
            z-index: 10;
        }

        .modal-body {
            display: grid;
            grid-template-columns: 1fr 1fr;
            gap: 40px;
            padding: 40px;
        }

        .modal-image {
            width: 100%;
            border-radius: 8px;
        }

        .modal-info h2 {
            font-size: 2rem;
            margin-bottom: 10px;
        }

        .modal-info .print-number {
            font-size: 1rem;
            margin-bottom: 20px;
        }

        .modal-info .print-price {
            font-size: 2rem;
            margin-bottom: 20px;
        }

        .modal-info .print-specs {
            font-size: 1rem;
            margin-bottom: 30px;
            padding: 20px;
            background: var(--accent-light);
            border-radius: 4px;
        }

        /* Footer */
        footer {
            background: var(--text-dark);
            color: white;
            padding: 40px;
            text-align: center;
            margin-top: 60px;
        }

        footer a {
            color: white;
            text-decoration: none;
        }

        footer a:hover {
            text-decoration: underline;
        }

        /* Loading State */
        .loading {
            text-align: center;
            padding: 60px 20px;
            font-size: 1.2rem;
            color: #666;
        }

        /* Responsive */
        @media (max-width: 768px) {
            nav {
                padding: 15px 20px;
            }

            .logo {
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

            .page-hero {
                padding: 60px 20px 40px;
            }

            .page-hero h1 {
                font-size: 2rem;
            }

            .page-hero p {
                font-size: 1rem;
            }

            .controls-bar {
                padding: 15px 20px;
                position: static;
            }

            .controls-container {
                flex-direction: column;
                align-items: stretch;
            }

            .controls-left {
                flex-direction: column;
                align-items: stretch;
                width: 100%;
            }

            .search-box {
                width: 100%;
            }

            .search-box input {
                width: 100%;
            }

            select {
                width: 100%;
            }

            .results-count {
                text-align: center;
            }

            .view-toggle {
                justify-content: center;
            }

            .container {
                padding: 20px;
            }

            .gallery {
                grid-template-columns: 1fr;
                gap: 20px;
                display: none;
            }

            .carousel-container-full {
                display: block;
            }

            .controls-bar {
                display: none;
            }

            .list-view .print-card {
                flex-direction: column;
                max-height: none;
            }

            .list-view .print-image-container {
                width: 100%;
                padding-bottom: 140%;
            }

            .modal-content {
                margin: 20px;
                max-height: 85vh;
            }

            .modal-body {
                grid-template-columns: 1fr;
                padding: 20px;
            }

            .modal-close {
                top: 10px;
                right: 10px;
                width: 35px;
                height: 35px;
                font-size: 24px;
            }

            .modal-info h2 {
                font-size: 1.5rem;
            }

            .modal-info .print-price {
                font-size: 1.5rem;
            }

            footer {
                padding: 30px 20px;
            }
        }

        @media (max-width: 480px) {
            .page-hero h1 {
                font-size: 1.8rem;
            }

            .gallery {
                grid-template-columns: repeat(auto-fill, minmax(150px, 1fr));
                gap: 15px;
            }

            .print-details {
                padding: 15px;
            }

            .print-title {
                font-size: 1rem;
            }

            .print-specs {
                font-size: 0.8rem;
            }

            .print-price {
                font-size: 1.1rem;
            }

            .btn {
                padding: 10px 20px;
                font-size: 13px;
            }

            .modal-info h2 {
                font-size: 1.3rem;
            }

            .modal-info .print-specs {
                font-size: 0.9rem;
                padding: 15px;
            }
        }

        /* Landscape mobile optimization */
        @media (max-width: 768px) and (orientation: landscape) {
            .page-hero {
                padding: 40px 20px 30px;
            }

            .page-hero h1 {
                font-size: 1.8rem;
            }

            .gallery {
                grid-template-columns: repeat(auto-fill, minmax(200px, 1fr));
            }
        }
    </style>
</head>
<body>
    <!-- Header -->
    <header>
        <nav>
            <a href="../../index.html" class="logo">JFeelgood</a>
            <button class="menu-button" id="menuButton" onclick="toggleMenu()">
                <span>Menu</span>
                <span id="menuIcon">☰</span>
            </button>
            <div class="dropdown-menu" id="dropdownMenu">
                <a href="../../index.html">Home</a>
                <a href="prints.html">Art Prints</a>
                <a href="../../index.html#book-feature">Book</a>
                <a href="../../index.html#artist-bio">About</a>
                <a href="../../index.html#email-capture" class="cta-link">Subscribe</a>
            </div>
        </nav>
    </header>

    <!-- Page Hero -->
    <section class="page-hero">
        <h1>Featured Art Prints</h1>
        <p>Explore our complete collection of original art prints. Each piece is professionally printed on premium paper and presented in a magnetically sealed acrylic case.</p>
    </section>

    <!-- Controls Bar -->
    <div class="controls-bar">
        <div class="controls-container">
            <div class="controls-left">
                <div class="search-box">
                    <input type="text" id="searchInput" placeholder="Search by number or title...">
                    <span class="search-icon">🔍</span>
                </div>
                <select id="sortSelect">
                    <option value="number-asc">Number (Low to High)</option>
                    <option value="number-desc">Number (High to Low)</option>
                    <option value="price-asc">Price (Low to High)</option>
                    <option value="price-desc">Price (High to Low)</option>
                </select>
                <span class="results-count" id="resultsCount">Showing 155 prints</span>
            </div>
            <div class="view-toggle">
                <button class="view-btn active" id="gridView">Grid</button>
                <button class="view-btn" id="listView">List</button>
            </div>
        </div>
    </div>

    <!-- Main Gallery -->
    <div class="container">
        <!-- Desktop Gallery -->
        <div class="gallery" id="gallery">
            <!-- Products will be dynamically inserted here -->
        </div>

        <!-- Mobile Carousel -->
        <div class="carousel-container-full">
            <div class="carousel-wrapper-full">
                <div class="carousel-track-full" id="carouselTrackFull">
                    <!-- Carousel slides will be dynamically inserted here -->
                </div>
            </div>
            <div class="carousel-controls-full">
                <button class="carousel-btn-full" id="prevBtnFull" onclick="moveCarouselFull(-1)">‹</button>
                <button class="carousel-btn-full" id="nextBtnFull" onclick="moveCarouselFull(1)">›</button>
            </div>
            <div class="carousel-info">
                <span class="carousel-counter" id="carouselCounter">1 / 155</span>
            </div>
        </div>
    </div>

    <!-- Modal -->
    <div class="modal" id="modal">
        <div class="modal-content">
            <button class="modal-close" id="modalClose">&times;</button>
            <div class="modal-body" id="modalBody">
                <!-- Modal content will be dynamically inserted -->
            </div>
        </div>
    </div>

    <!-- Footer -->
    <footer>
        <p>&copy; 2025 JFeelgood. All rights reserved. | <a href="../../index.html">Back to Home</a></p>
    </footer>

    <script>
        // Menu toggle functionality
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

        // Close menu when clicking outside
        document.addEventListener('click', (e) => {
            const menu = document.getElementById('dropdownMenu');
            const button = document.getElementById('menuButton');
            if (!menu.contains(e.target) && !button.contains(e.target)) {
                closeMenu();
            }
        });

        // Generate product data
        const products = [];
        const basePrice = 125;
        
        for (let i = 1; i <= 155; i++) {
            const num = String(i).padStart(3, '0');
            // Vary prices slightly for realism
            const priceVariation = Math.floor(Math.random() * 50) - 25;
            const price = basePrice + priceVariation;
            
            products.push({
                id: i,
                number: num,
                title: `JFeelgoodArt${num}`,
                image: `JFeelgoodArt${num}.jpg`,
                description: `JFeelgoodArt${num}`,
                size: '2.5" x 3.5"',
                specs: '2.5" x 3.5" premium print in magnetically sealed acrylic case',
                price: price
            });
        }

        let currentProducts = [...products];
        let currentView = 'grid';

        // Render gallery
        function renderGallery(productsToRender) {
            const gallery = document.getElementById('gallery');
            gallery.innerHTML = '';

            productsToRender.forEach(product => {
                const card = document.createElement('div');
                card.className = 'print-card';
                card.onclick = () => openModal(product);
                
                card.innerHTML = `
                    <div class="print-image-container">
                        <img src="${product.image}" alt="${product.title}" class="print-image" onerror="this.src='data:image/svg+xml,%3Csvg xmlns=%22http://www.w3.org/2000/svg%22 viewBox=%220 0 400 560%22%3E%3Crect fill=%22%23667eea%22 width=%22400%22 height=%22560%22/%3E%3Ctext x=%2250%25%22 y=%2250%25%22 font-family=%22Arial%22 font-size=%2224%22 fill=%22white%22 text-anchor=%22middle%22 dominant-baseline=%22middle%22%3E${product.title}%3C/text%3E%3C/svg%3E'">
                    </div>
                    <div class="print-details">
                        <div class="print-title">${product.title}</div>
                        <div class="print-number">#${product.number}</div>
                        <div class="print-specs">${product.specs}</div>
                        <div class="print-price">${product.price}</div>
                        <div class="print-actions">
                            <button class="btn" onclick="event.stopPropagation(); addToCart(${product.id})">Add to Cart</button>
                        </div>
                    </div>
                `;
                
                gallery.appendChild(card);
            });

            document.getElementById('resultsCount').textContent = 
                `Showing ${productsToRender.length} print${productsToRender.length !== 1 ? 's' : ''}`;
        }

        // Render carousel for mobile
        function renderCarousel() {
            const track = document.getElementById('carouselTrackFull');
            track.innerHTML = '';

            products.forEach(product => {
                const slide = document.createElement('div');
                slide.className = 'carousel-slide-full';
                
                slide.innerHTML = `
                    <div class="print-card" onclick="openModal(products[${product.id - 1}])">
                        <div class="print-image-container">
                            <img src="${product.image}" alt="${product.title}" class="print-image" onerror="this.src='data:image/svg+xml,%3Csvg xmlns=%22http://www.w3.org/2000/svg%22 viewBox=%220 0 400 560%22%3E%3Crect fill=%22%23667eea%22 width=%22400%22 height=%22560%22/%3E%3Ctext x=%2250%25%22 y=%2250%25%22 font-family=%22Arial%22 font-size=%2224%22 fill=%22white%22 text-anchor=%22middle%22 dominant-baseline=%22middle%22%3E${product.title}%3C/text%3E%3C/svg%3E'">
                        </div>
                        <div class="print-details">
                            <div class="print-title">${product.title}</div>
                            <div class="print-number">#${product.number}</div>
                            <div class="print-specs">${product.specs}</div>
                            <div class="print-price">${product.price}</div>
                            <div class="print-actions">
                                <button class="btn" onclick="event.stopPropagation(); addToCart(${product.id})">Add to Cart</button>
                            </div>
                        </div>
                    </div>
                `;
                
                track.appendChild(slide);
            });
        }

        // Carousel functionality
        let currentSlideFull = 0;
        const totalSlidesFull = 155;

        function updateCarouselFull() {
            const track = document.getElementById('carouselTrackFull');
            track.style.transform = `translateX(-${currentSlideFull * 100}%)`;
            document.getElementById('carouselCounter').textContent = `${currentSlideFull + 1} / ${totalSlidesFull}`;
        }

        function moveCarouselFull(direction) {
            currentSlideFull += direction;
            if (currentSlideFull < 0) currentSlideFull = totalSlidesFull - 1;
            if (currentSlideFull >= totalSlidesFull) currentSlideFull = 0;
            updateCarouselFull();
        }

        // Touch swipe support for carousel
        let touchStartX = 0;
        let touchEndX = 0;

        const carouselWrapper = document.querySelector('.carousel-wrapper-full');
        if (carouselWrapper) {
            carouselWrapper.addEventListener('touchstart', (e) => {
                touchStartX = e.changedTouches[0].screenX;
            });

            carouselWrapper.addEventListener('touchend', (e) => {
                touchEndX = e.changedTouches[0].screenX;
                handleSwipeFull();
            });
        }

        function handleSwipeFull() {
            if (touchEndX < touchStartX - 50) {
                moveCarouselFull(1); // Swipe left
            }
            if (touchEndX > touchStartX + 50) {
                moveCarouselFull(-1); // Swipe right
            }
        }

        // Search functionality
        document.getElementById('searchInput').addEventListener('input', (e) => {
            const searchTerm = e.target.value.toLowerCase();
            currentProducts = products.filter(p => 
                p.title.toLowerCase().includes(searchTerm) ||
                p.number.includes(searchTerm)
            );
            renderGallery(currentProducts);
        });

        // Sort functionality
        document.getElementById('sortSelect').addEventListener('change', (e) => {
            const sortBy = e.target.value;
            
            currentProducts.sort((a, b) => {
                switch(sortBy) {
                    case 'number-asc':
                        return a.id - b.id;
                    case 'number-desc':
                        return b.id - a.id;
                    case 'price-asc':
                        return a.price - b.price;
                    case 'price-desc':
                        return b.price - a.price;
                    default:
                        return 0;
                }
            });
            
            renderGallery(currentProducts);
        });

        // View toggle
        document.getElementById('gridView').addEventListener('click', () => {
            currentView = 'grid';
            document.getElementById('gallery').classList.remove('list-view');
            document.getElementById('gridView').classList.add('active');
            document.getElementById('listView').classList.remove('active');
        });

        document.getElementById('listView').addEventListener('click', () => {
            currentView = 'list';
            document.getElementById('gallery').classList.add('list-view');
            document.getElementById('listView').classList.add('active');
            document.getElementById('gridView').classList.remove('active');
        });

        // Modal functionality
        function openModal(product) {
            const modal = document.getElementById('modal');
            const modalBody = document.getElementById('modalBody');
            
            modalBody.innerHTML = `
                <div>
                    <img src="${product.image}" alt="${product.title}" class="modal-image" onerror="this.src='data:image/svg+xml,%3Csvg xmlns=%22http://www.w3.org/2000/svg%22 viewBox=%220 0 400 560%22%3E%3Crect fill=%22%23667eea%22 width=%22400%22 height=%22560%22/%3E%3Ctext x=%2250%25%22 y=%2250%25%22 font-family=%22Arial%22 font-size=%2224%22 fill=%22white%22 text-anchor=%22middle%22 dominant-baseline=%22middle%22%3E${product.title}%3C/text%3E%3C/svg%3E'">
                </div>
                <div class="modal-info">
                    <h2>${product.title}</h2>
                    <div class="print-number">#${product.number}</div>
                    <div class="print-price">$${product.price}</div>
                    <div class="print-specs">
                        <strong>Specifications:</strong><br>
                        Size: ${product.size}<br>
                        Premium quality print<br>
                        Magnetically sealed acrylic case included<br>
                        Ready to display or gift
                    </div>
                    <button class="btn" onclick="addToCart(${product.id})" style="width: 100%; margin-bottom: 10px;">Add to Cart</button>
                    <button class="btn btn-secondary" onclick="closeModal()" style="width: 100%;">Continue Shopping</button>
                </div>
            `;
            
            modal.classList.add('active');
            document.body.style.overflow = 'hidden';
        }

        function closeModal() {
            document.getElementById('modal').classList.remove('active');
            document.body.style.overflow = 'auto';
        }

        document.getElementById('modalClose').addEventListener('click', closeModal);
        
        document.getElementById('modal').addEventListener('click', (e) => {
            if (e.target.id === 'modal') {
                closeModal();
            }
        });

        // Add to cart functionality
        function addToCart(productId) {
            const product = products.find(p => p.id === productId);
            alert(`Added ${product.title} to cart!\n\nPrice: $${product.price}\n\nNote: Cart functionality would integrate with your e-commerce platform.`);
        }

        // Initial render
        renderGallery(currentProducts);
        renderCarousel();
    </script>
</body>
</html>
