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
                flex-direction: column;
                gap: 20px;
                padding: 20px;
            }

            .nav-links {
                flex-direction: column;
                gap: 15px;
            }

            .controls-container {
                flex-direction: column;
                align-items: stretch;
            }

            .controls-left {
                flex-direction: column;
                align-items: stretch;
            }

            .search-box input {
                width: 100%;
            }

            .gallery {
                grid-template-columns: repeat(auto-fill, minmax(200px, 1fr));
                gap: 20px;
            }

            .modal-body {
                grid-template-columns: 1fr;
                padding: 20px;
            }

            .list-view .print-card {
                flex-direction: column;
                max-height: none;
            }

            .list-view .print-image-container {
                width: 100%;
                padding-bottom: 140%;
            }
        }
    </style>
</head>
<body>
    <!-- Header -->
    <header>
        <nav>
            <a href="index.html" class="logo">JFeelgood</a>
            <div class="nav-links">
                <a href="index.html">Home</a>
                <a href="prints.html">Art Prints</a>
                <a href="index.html#book-feature">Book</a>
                <a href="index.html#artist-bio">About</a>
                <a href="index.html#email-capture" class="btn" style="padding: 10px 20px;">Subscribe</a>
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
        <div class="gallery" id="gallery">
            <!-- Products will be dynamically inserted here -->
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
        <p>&copy; 2025 JFeelgood. All rights reserved. | <a href="index.html">Back to Home</a></p>
    </footer>

    <script>
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
                        <div class="print-price">$${product.price}</div>
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
    </script>
</body>
</html>
