<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>JFeelgood - Art & Thought Entropy</title>
    <style>
        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
        }

        body {
            font-family: 'Georgia', serif;
            line-height: 1.6;
            color: #333;
            background: #f9f9f9;
        }

        .container {
            max-width: 1200px;
            margin: 0 auto;
            padding: 0 20px;
        }

        /* Hero Section */
        .hero {
            height: 100vh;
            background: linear-gradient(135deg, #667eea 0%, #764ba2 100%);
            display: flex;
            align-items: center;
            justify-content: center;
            text-align: center;
            color: white;
            position: relative;
        }

        .hero-content h1 {
            font-size: 4rem;
            margin-bottom: 1rem;
            font-weight: 300;
            letter-spacing: 2px;
        }

        .hero-content p {
            font-size: 1.5rem;
            margin-bottom: 2rem;
            opacity: 0.9;
        }

        .btn {
            display: inline-block;
            padding: 15px 40px;
            background: white;
            color: #667eea;
            text-decoration: none;
            border-radius: 50px;
            font-weight: bold;
            transition: transform 0.3s ease, box-shadow 0.3s ease;
        }

        .btn:hover {
            transform: translateY(-2px);
            box-shadow: 0 10px 25px rgba(0,0,0,0.2);
        }

        /* Gallery Section */
        .gallery-section {
            padding: 80px 0;
            background: #2a2a2a;
            min-height: 100vh;
            position: relative;
        }

        .gallery-section h2 {
            text-align: center;
            color: white;
            font-size: 3rem;
            margin-bottom: 3rem;
            font-weight: 300;
        }

        .gallery-container {
            position: relative;
            width: 100%;
            height: 600px;
            perspective: 1000px;
            overflow: hidden;
        }

        .gallery-wall {
            position: relative;
            width: 100%;
            height: 100%;
            display: flex;
            align-items: center;
            justify-content: center;
            gap: 80px;
            padding: 0 100px;
            transition: transform 0.5s ease;
        }

        .artwork {
            flex-shrink: 0;
            background: white;
            padding: 20px;
            box-shadow: 0 10px 40px rgba(0,0,0,0.5);
            position: relative;
        }

        .artwork img {
            display: block;
            width: 400px;
            height: 500px;
            object-fit: cover;
        }

        .gallery-nav {
            position: absolute;
            top: 50%;
            transform: translateY(-50%);
            background: rgba(255,255,255,0.1);
            border: 2px solid rgba(255,255,255,0.3);
            color: white;
            width: 60px;
            height: 60px;
            border-radius: 50%;
            display: flex;
            align-items: center;
            justify-content: center;
            cursor: pointer;
            transition: all 0.3s ease;
            font-size: 2rem;
            z-index: 10;
        }

        .gallery-nav:hover {
            background: rgba(255,255,255,0.2);
            transform: translateY(-50%) scale(1.1);
        }

        .gallery-nav.prev {
            left: 20px;
        }

        .gallery-nav.next {
            right: 20px;
        }

        .gallery-counter {
            text-align: center;
            color: white;
            margin-top: 30px;
            font-size: 1.2rem;
        }

        /* Book Section */
        .book-section {
            padding: 100px 0;
            background: white;
        }

        .book-content {
            display: flex;
            align-items: center;
            gap: 60px;
        }

        .book-image {
            flex: 1;
            display: flex;
            justify-content: center;
        }

        .book-cover {
            width: 350px;
            height: 500px;
            background: linear-gradient(135deg, #667eea 0%, #764ba2 100%);
            display: flex;
            align-items: center;
            justify-content: center;
            color: white;
            font-size: 2.5rem;
            font-weight: bold;
            box-shadow: 0 20px 60px rgba(0,0,0,0.3);
            border-radius: 10px;
            padding: 40px;
            text-align: center;
        }

        .book-info {
            flex: 1;
        }

        .book-info h2 {
            font-size: 2.5rem;
            margin-bottom: 1.5rem;
            color: #667eea;
        }

        .book-info p {
            margin-bottom: 1.5rem;
            font-size: 1.1rem;
            color: #555;
        }

        /* Bio Section */
        .bio-section {
            padding: 100px 0;
            background: #f5f5f5;
        }

        .bio-content {
            display: flex;
            align-items: center;
            gap: 60px;
        }

        .bio-image {
            flex: 1;
            height: 400px;
            background: linear-gradient(135deg, #764ba2 0%, #667eea 100%);
            border-radius: 10px;
            box-shadow: 0 20px 60px rgba(0,0,0,0.2);
        }

        .bio-text {
            flex: 1;
        }

        .bio-text h2 {
            font-size: 2.5rem;
            margin-bottom: 1.5rem;
            color: #333;
        }

        .bio-text p {
            margin-bottom: 1.5rem;
            font-size: 1.1rem;
            color: #555;
        }

        .social-links {
            margin-top: 2rem;
        }

        .social-icon {
            display: inline-block;
            width: 40px;
            height: 40px;
            background: #667eea;
            color: white;
            border-radius: 50%;
            display: inline-flex;
            align-items: center;
            justify-content: center;
            margin-right: 10px;
            transition: transform 0.3s ease;
        }

        .social-icon:hover {
            transform: translateY(-3px);
        }

        /* Responsive */
        @media (max-width: 768px) {
            .hero-content h1 {
                font-size: 2.5rem;
            }

            .book-content,
            .bio-content {
                flex-direction: column;
            }

            .artwork img {
                width: 300px;
                height: 400px;
            }

            .gallery-wall {
                padding: 0 80px;
            }
        }
    </style>
</head>
<body>
    <!-- Hero Section -->
    <section class="hero">
        <div class="hero-content">
            <h1>JFeelgood</h1>
            <p>Where Chaos Becomes Creation</p>
            <a href="#gallery" class="btn">Explore Gallery</a>
        </div>
    </section>

    <!-- Gallery Section -->
    <section class="gallery-section" id="gallery">
        <div class="container">
            <h2>Art Gallery</h2>
            <div class="gallery-container">
                <div class="gallery-wall" id="galleryWall"></div>
                <div class="gallery-nav prev" onclick="navigateGallery(-1)">‹</div>
                <div class="gallery-nav next" onclick="navigateGallery(1)">›</div>
            </div>
            <div class="gallery-counter">
                <span id="currentImage">1</span> / <span id="totalImages">155</span>
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
                   
                            </svg>
                        </a>
                    </div>
                </div>
            </div>
        </div>
    </section>

    <script>
        const totalImages = 155;
        let currentIndex = 0;
        const visibleArtworks = 3;

        function initGallery() {
            const galleryWall = document.getElementById('galleryWall');
            
            for (let i = 1; i <= totalImages; i++) {
                const artwork = document.createElement('div');
                artwork.className = 'artwork';
                artwork.innerHTML = `<img src="assets/image/JFeelgoodArt${String(i).padStart(3, '0')}.jpg" alt="JFeelgood Art ${i}" onerror="this.src='https://via.placeholder.com/400x500?text=Art+${i}'">`;
                galleryWall.appendChild(artwork);
            }

            updateGallery();
        }

        function navigateGallery(direction) {
            currentIndex += direction;
            
            if (currentIndex < 0) {
                currentIndex = totalImages - 1;
            } else if (currentIndex >= totalImages) {
                currentIndex = 0;
            }
            
            updateGallery();
        }

        function updateGallery() {
            const galleryWall = document.getElementById('galleryWall');
            const artworkWidth = 480;
            const offset = -currentIndex * artworkWidth;
            
            galleryWall.style.transform = `translateX(${offset}px)`;
            
            document.getElementById('currentImage').textContent = currentIndex + 1;
        }

        // Keyboard navigation
        document.addEventListener('keydown', (e) => {
            if (e.key === 'ArrowLeft') navigateGallery(-1);
            if (e.key === 'ArrowRight') navigateGallery(1);
        });

        // Initialize gallery on load
        initGallery();
    </script>
</body>
</html>
