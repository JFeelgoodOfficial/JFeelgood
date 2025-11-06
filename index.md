<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <title>JFeelgood Art Gallery</title>
  <link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/Swiper/4.0.5/css/swiper.css">
  <style>
    body { font-family: Arial, sans-serif; margin: 0; }
    header { text-align: center; padding: 2rem 1rem 0.5rem; font-size: 2.2rem; }
    .profile, .info, .blog, .footer { padding: 1rem 2rem; }
    .gallery-section { margin: 2rem auto; max-width: 700px;}
  </style>
</head>
<body>
  <header>JFeelgood</header>
  <div class="profile">
    <!-- Profile pic + About info goes here -->
    <img src="profile.jpg" alt="Profile" style="width:100px;height:100px;">
    <p>About the artist...</p>
  </div>
  <div class="info">
    <!-- Description/blurb about art or current series -->
    <h2>Featured Series</h2>
    <p>This month's collection focuses on vibrant abstracts.</p>
  </div>
  <div class="gallery-section">
    <!-- Carousel Gallery using Swiper.js -->
    <div class="swiper-container">
      <div class="swiper-wrapper">
        <div class="swiper-slide"><img src="JFeelgoodArt001.jpg" alt="Art 1" /></div>
        <div class="swiper-slide"><img src="JFeelgoodArt002.jpg" alt="Art 2" /></div>
        <div class="swiper-slide"><img src="JFeelgoodArt003.jpg" alt="Art 3" /></div>
        <div class="swiper-slide"><img src="JFeelgoodArt004.jpg" alt="Art 4" /></div>
        <div class="swiper-slide"><img src="JFeelgoodArt005.jpg" alt="Art 5" /></div>
        <div class="swiper-slide"><img src="JFeelgoodArt006.jpg" alt="Art 6" /></div>
        <div class="swiper-slide"><img src="JFeelgoodArt007.jpg" alt="Art 7" /></div>
        <div class="swiper-slide"><img src="JFeelgoodArt008.jpg" alt="Art 8" /></div>
        <!-- Add more slides as needed -->
      </div>
      <div class="swiper-pagination"></div>
      <div class="swiper-button-prev"></div>
      <div class="swiper-button-next"></div>
    </div>
  </div>
  <div class="blog">
    <!-- Posts, updates, or additional blocks -->
    <h2>Latest Posts</h2>
    <ul>
      <li><a href="#">Painting Process: October Highlights</a></li>
      <li><a href="#">Sale Announcement</a></li>
    </ul>
  </div>
  <div class="footer">
    <p>Contact: info@jfeelgood.com</p>
  </div>
  <script src="https://cdnjs.cloudflare.com/ajax/libs/Swiper/4.0.5/js/swiper.min.js"></script>
  <script>
    var swiper = new Swiper('.swiper-container', {
      effect: 'coverflow',
      grabCursor: true,
      centeredSlides: true,
      slidesPerView: 'auto',
      navigation: {
        nextEl: '.swiper-button-next',
        prevEl: '.swiper-button-prev',
      },
      pagination: {
        el: '.swiper-pagination',
        clickable: true,
      },
      autoplay: {
        delay: 2500,
      },
      coverflowEffect: {
        rotate: 20,
        stretch: 0,
        depth: 300,
        modifier: 1,
        slideShadows: true,
      }
    });
  </script>
</body>
</html>
