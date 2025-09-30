---
layout: default
title: JFeelgood Art
permalink: /
---

<!-- Navigation with anchor links to sections -->
<nav class="landing-nav">
  <ul>
    <li><a href="#hero">Home</a></li>
    <li><a href="#about">About</a></li>
    <li><a href="#featured">Featured Work</a></li>
    <li><a href="#gallery">Gallery & Shop</a></li>
    <li><a href="#contact">Contact</a></li>
  </ul>
</nav>

<!-- HERO SECTION -->
<section id="hero" class="hero-banner" style="padding-top:4em;">
  <h2>Discover Unique, Original Art Pieces by JFeelgood</h2>
  <p>Elevate your space with one-of-a-kind creations.</p>
  <a class="cta-button" href="#gallery">Explore Gallery</a>
  <img src="assets/images/JFeelgood_portrait2.jpg" 
     alt="Portrait_of_JFeelgood_02" 
     style="max-width:200px; border-radius:12px; display:block; margin:1.5em auto 1em auto;" />
</section>

<!-- ABOUT SECTION -->
<section id="about">
  <h1>About JFeelgood</h1>
  <img src="assets/images/JFeelgood_portrait1.jpg" alt="Portrait_of_JFeelgood_01" style="max-width:200px;border-radius:12px;float:left;margin:0 1em 1em 0;" />

  <p>
    JFeelgood is an accomplished artist with over 18 years of experience in various mediums. He has produced a substantial body of work, including several hundred paintings, five published books, five music albums, and a video game. In addition to his own artistic pursuits, JFeelgood has also organized community events and served in leadership roles for various art organizations. He is dedicated to using his art as a means of self-expression and has a strong passion for helping others explore their own creative gifts. JFeelgood's relationship with art is central to his life and he continues to seek new ways to enrich this connection through life experiences and experimentation with new mediums.
  </p>
  <h3>What Collectors Are Saying:</h3>
  <blockquote>
    <p>"JFeelgood’s work brings a new dimension to my living space. Each piece is more than just art—it’s a conversation starter."<br>
    <span style="font-size:0.9em;">— Sarah M., Austin, TX</span></p>
  </blockquote>
  <blockquote>
    <p>"The quality of the prints is outstanding. The colors are as vibrant as the originals, and the paper is top-notch."<br>
    <span style="font-size:0.9em;">​— Michael P., New York, NY</span></p>
  </blockquote>
  <div style="clear:both;"></div>
</section>

<!-- FEATURED WORK SECTION -->
<section id="featured">
  <h2>Featured Work</h2>
  <div class="gallery-grid-featured">
    <!-- Dynamically render all 153 images -->
    {% for i in (1..153) %}
      {% assign num = i | prepend: "000" | slice: -3, 3 %}
      <div class="featured-artwork-card">
        <img 
          src="/assets/images/JFeelgoodArt{{ num }}.jpg" 
          alt="JFeelgoodArt{{ num }}" 
          loading="lazy"
        />
      </div>
    {% endfor %}
  </div>
</section>

<style>
.landing-nav {
  position: fixed;
  top: 0; left: 0; right: 0;
  background: #fff;
  border-bottom: 1px solid #eee;
  z-index: 100;
  padding: 0.5em 0;
}
.landing-nav ul {
  margin: 0;
  padding: 0 1em;
  display: flex;
  gap: 2em;
  list-style: none;
  justify-content: center;
  align-items: center;
}
.landing-nav a {
  text-decoration: none;
  color: #222;
  font-weight: bold;
}
.landing-nav a:hover {
  color: #b85c35;
}
section {
  padding: 3em 1em 2em 1em;
  max-width: 900px;
  margin: 0 auto;
}
.hero-banner {
  background: #f5f3ef;
  border-radius: 16px;
  margin-top: 3em;
  text-align: center;
  padding: 2em 1em;
}
.cta-button {
  background: #b85c35;
  color: #fff;
  border: none;
  border-radius: 8px;
  padding: 0.7em 2em;
  font-size: 1.1em;
  font-weight: bold;
  text-decoration: none;
  transition: background 0.2s;
  display: inline-block;
  margin-top: 1em;
}
.cta-button:hover { background: #a44d29; }

.gallery-grid-featured {
  display: grid;
  grid-template-columns: repeat(5, 1fr);
  gap: 1.3em;
}
.featured-artwork-card {
  background: #faf7f3;
  border-radius: 12px;
  box-shadow: 0 2px 16px rgba(0,0,0,0.04);
  padding: 0.5em;
  display: flex;
  align-items: center;
  justify-content: center;
  height: 185px; /* uniform height for all cards */
}
.featured-artwork-card img {
  max-height: 160px;
  max-width: 100%;
  width: auto;
  height: auto;
  object-fit: contain;
  border-radius: 8px;
  display: block;
  margin: 0 auto;
  background: #fff;
}

.gallery-grid {
  display: grid;
  grid-template-columns: repeat(auto-fit, minmax(220px, 1fr));
  gap: 2em;
  margin: 2em 0;
}
.artwork-card {
  background: #faf7f3;
  border-radius: 12px;
  box-shadow: 0 2px 16px rgba(0,0,0,0.04);
  padding: 1em;
  text-align: center;
}
.artwork-card img {
  max-width: 100%;
  border-radius: 8px;
  margin-bottom: 1em;
}
blockquote {
  background: #f8f5f2;
  border-left: 4px solid #b85c35;
  margin: 1.5em 0;
  padding: 1em 1.5em;
  font-style: italic;
  border-radius: 8px;
}
@media (max-width: 900px) {
  .gallery-grid-featured { grid-template-columns: repeat(3, 1fr); }
}
@media (max-width: 700px) {
  .gallery-grid-featured { grid-template-columns: repeat(2, 1fr); }
  .gallery-grid { grid-template-columns: 1fr; }
  .landing-nav ul { flex-direction: column; gap: 0.5em; }
  section { padding: 2em 0.5em 1em 0.5em; }
}
</style>
