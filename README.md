<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8" />
  <meta name="viewport" content="width=device-width, initial-scale=1.0" />
  <title>Yusufs Frames | Cinematic Portfolio</title>

  <!-- Google Fonts -->
  <link href="https://fonts.googleapis.com/css2?family=Cinzel:wght@400;600;700&family=Inter:wght@300;400;500;600&display=swap" rel="stylesheet">

  <style>
    :root{
      --bg:#050505;
      --bg-soft:#101010;
      --card:#111111b7;
      --text:#e8e8e8;
      --muted:#9b9b9b;
      --accent:#c1121f;
      --accent-glow:#ff003c;
      --border:rgba(255,255,255,0.08);
      --glass:rgba(255,255,255,0.06);
      --shadow:0 0 25px rgba(255,0,60,0.18);
    }

    *{
      margin:0;
      padding:0;
      box-sizing:border-box;
      scroll-behavior:smooth;
    }

    body{
      background:var(--bg);
      color:var(--text);
      font-family:'Inter', sans-serif;
      overflow-x:hidden;
      position:relative;
    }

    /* Film Grain Overlay */
    body::before{
      content:"";
      position:fixed;
      inset:0;
      background-image:url("https://www.transparenttextures.com/patterns/asfalt-dark.png");
      opacity:0.08;
      pointer-events:none;
      z-index:9999;
      mix-blend-mode:soft-light;
    }

    h1,h2,h3{
      font-family:'Cinzel', serif;
      letter-spacing:1px;
    }

    section{
      padding:100px 8%;
      position:relative;
      z-index:2;
    }

    /* NAVBAR */
    nav{
      position:fixed;
      width:100%;
      top:0;
      left:0;
      z-index:1000;
      backdrop-filter:blur(12px);
      background:rgba(0,0,0,0.35);
      border-bottom:1px solid var(--border);
    }

    .nav-container{
      display:flex;
      justify-content:space-between;
      align-items:center;
      padding:18px 8%;
    }

    .logo{
      font-size:1.2rem;
      font-family:'Cinzel', serif;
      color:#fff;
      letter-spacing:2px;
    }

    .nav-links{
      display:flex;
      gap:28px;
    }

    .nav-links a{
      color:var(--muted);
      text-decoration:none;
      transition:0.3s;
      font-size:0.95rem;
    }

    .nav-links a:hover{
      color:#fff;
    }

    /* HERO */
    .hero{
      height:100vh;
      display:flex;
      align-items:center;
      justify-content:center;
      text-align:center;
      overflow:hidden;
      position:relative;
    }

    .hero::before{
      content:"";
      position:absolute;
      inset:0;
      background:
      linear-gradient(to bottom, rgba(0,0,0,0.65), rgba(0,0,0,0.9)),
      url('https://images.unsplash.com/photo-1500530855697-b586d89ba3ee?q=80&w=1600&auto=format&fit=crop');
      background-size:cover;
      background-position:center;
      filter:brightness(0.45);
      transform:scale(1.05);
    }

    .hero-content{
      position:relative;
      z-index:5;
      max-width:900px;
      animation:fadeUp 1.2s ease;
    }

    .hero h1{
      font-size:5rem;
      margin-bottom:20px;
      text-transform:uppercase;
      line-height:1.05;
      text-shadow:0 0 20px rgba(255,255,255,0.08);
    }

    .hero p{
      color:var(--muted);
      max-width:650px;
      margin:auto;
      font-size:1.05rem;
      line-height:1.8;
    }

    .cta{
      margin-top:35px;
      display:inline-block;
      padding:15px 34px;
      border-radius:50px;
      background:rgba(255,255,255,0.08);
      border:1px solid rgba(255,255,255,0.15);
      backdrop-filter:blur(12px);
      color:#fff;
      text-decoration:none;
      transition:0.4s;
      box-shadow:var(--shadow);
    }

    .cta:hover{
      transform:translateY(-4px) scale(1.03);
      background:rgba(255,0,60,0.15);
      border-color:rgba(255,0,60,0.4);
      box-shadow:0 0 30px rgba(255,0,60,0.35);
    }

    /* SECTION TITLES */
    .section-title{
      font-size:2.5rem;
      margin-bottom:20px;
      position:relative;
      display:inline-block;
    }

    .section-title::after{
      content:"";
      position:absolute;
      width:60%;
      height:2px;
      left:0;
      bottom:-8px;
      background:linear-gradient(to right,var(--accent),transparent);
    }

    .section-sub{
      color:var(--muted);
      margin-bottom:60px;
      max-width:700px;
      line-height:1.8;
    }

    /* PHOTO GALLERY */
    .gallery-grid{
      columns:3 280px;
      column-gap:18px;
    }

    .gallery-item{
      position:relative;
      margin-bottom:18px;
      overflow:hidden;
      border-radius:18px;
      cursor:pointer;
      border:1px solid rgba(255,255,255,0.05);
      background:#000;
    }

    .gallery-item img{
      width:100%;
      display:block;
      transition:0.6s ease;
      filter:grayscale(100%) brightness(0.8);
    }

    .gallery-item:hover img{
      transform:scale(1.05);
      filter:grayscale(0%) brightness(1);
    }

    .gallery-item::after{
      content:"VIEW";
      position:absolute;
      inset:0;
      display:flex;
      align-items:center;
      justify-content:center;
      color:#fff;
      font-size:1rem;
      letter-spacing:4px;
      opacity:0;
      transition:0.4s;
      background:rgba(0,0,0,0.25);
      backdrop-filter:blur(4px);
    }

    .gallery-item:hover::after{
      opacity:1;
    }

    /* VIDEO SECTION */
    .video-grid{
      display:grid;
      grid-template-columns:repeat(auto-fit,minmax(320px,1fr));
      gap:30px;
    }

    .video-card{
      background:var(--card);
      border:1px solid var(--border);
      border-radius:20px;
      overflow:hidden;
      backdrop-filter:blur(14px);
      transition:0.4s;
      box-shadow:0 0 0 rgba(255,0,60,0);
    }

    .video-card:hover{
      transform:translateY(-8px);
      box-shadow:0 0 35px rgba(255,0,60,0.2);
    }

    .video-frame{
      position:relative;
      padding-top:56.25%;
      overflow:hidden;
    }

    .video-frame iframe{
      position:absolute;
      inset:0;
      width:100%;
      height:100%;
      border:none;
    }

    .video-content{
      padding:24px;
    }

    .video-content h3{
      margin-bottom:10px;
      font-size:1.3rem;
    }

    .video-content p{
      color:var(--muted);
      line-height:1.7;
      font-size:0.95rem;
    }

    /* ABOUT */
    .about{
      display:grid;
      grid-template-columns:1fr 1fr;
      gap:50px;
      align-items:center;
    }

    .about-card{
      padding:40px;
      border-radius:24px;
      background:rgba(255,255,255,0.04);
      border:1px solid rgba(255,255,255,0.08);
      backdrop-filter:blur(12px);
      box-shadow:0 0 30px rgba(255,255,255,0.02);
    }

    .about-card p{
      color:var(--muted);
      line-height:2;
      font-size:1rem;
    }

    .quote{
      font-size:2rem;
      color:#fff;
      line-height:1.5;
      font-family:'Cinzel', serif;
    }

    /* FOOTER */
    footer{
      padding:40px 8%;
      text-align:center;
      color:var(--muted);
      border-top:1px solid rgba(255,255,255,0.06);
      background:#080808;
    }

    /* LIGHTBOX */
    .lightbox{
      position:fixed;
      inset:0;
      background:rgba(0,0,0,0.92);
      display:flex;
      justify-content:center;
      align-items:center;
      opacity:0;
      pointer-events:none;
      transition:0.4s;
      z-index:99999;
    }

    .lightbox.active{
      opacity:1;
      pointer-events:auto;
    }

    .lightbox img{
      max-width:90%;
      max-height:85%;
      border-radius:10px;
      box-shadow:0 0 50px rgba(255,255,255,0.12);
    }

    .lightbox-close{
      position:absolute;
      top:30px;
      right:40px;
      font-size:2rem;
      color:white;
      cursor:pointer;
    }

    /* Fade-in Animations */
    .fade-in{
      opacity:0;
      transform:translateY(40px);
      transition:all 1s ease;
    }

    .fade-in.show{
      opacity:1;
      transform:translateY(0);
    }

    /* Custom Scrollbar */
    ::-webkit-scrollbar{
      width:10px;
    }

    ::-webkit-scrollbar-track{
      background:#0d0d0d;
    }

    ::-webkit-scrollbar-thumb{
      background:linear-gradient(var(--accent),#42000f);
      border-radius:20px;
    }

    /* Responsive */
    @media(max-width:900px){
      .hero h1{
        font-size:3rem;
      }

      .about{
        grid-template-columns:1fr;
      }
    }

    @media(max-width:600px){
      .nav-links{
        gap:15px;
      }

      .hero h1{
        font-size:2.2rem;
      }

      .section-title{
        font-size:2rem;
      }

      .quote{
        font-size:1.5rem;
      }
    }

    @keyframes fadeUp{
      from{
        opacity:0;
        transform:translateY(30px);
      }
      to{
        opacity:1;
        transform:translateY(0);
      }
    }

  </style>
</head>
<body>

  <!-- NAV -->
  <nav>
    <div class="nav-container">
      <div class="logo">NOIR FRAMES</div>

      <div class="nav-links">
        <a href="#gallery">Photography</a>
        <a href="#films">Films</a>
        <a href="#about">About</a>
      </div>
    </div>
  </nav>

  <!-- HERO -->
  <section class="hero">
    <div class="hero-content">
      <h1>Stories Born <br> In The Dark</h1>

      <p>
        Cinematic visions carved from shadows, silence, neon lights,
        and fractured memories. A portfolio of noir-inspired short films
        and haunting photography.
      </p>

      <a href="#films" class="cta">Watch Latest Film</a>
    </div>
  </section>

  <!-- GALLERY -->
  <section id="gallery" class="fade-in">
    <h2 class="section-title">Photography</h2>

    <p class="section-sub">
      Every frame is a confession — fragments of neon streets,
      cigarette smoke, midnight rain, and silent rebellion.
    </p>

    <div class="gallery-grid">

      <div class="gallery-item">
        <img src="https://images.unsplash.com/photo-1492691527719-9d1e07e534b4?q=80&w=1200&auto=format&fit=crop" alt="">
      </div>

      <div class="gallery-item">
        <img src="https://images.unsplash.com/photo-1516035069371-29a1b244cc32?q=80&w=1200&auto=format&fit=crop" alt="">
      </div>

      <div class="gallery-item">
        <img src="https://images.unsplash.com/photo-1493246507139-91e8fad9978e?q=80&w=1200&auto=format&fit=crop" alt="">
      </div>

      <div class="gallery-item">
        <img src="https://images.unsplash.com/photo-1517423440428-a5a00ad493e8?q=80&w=1200&auto=format&fit=crop" alt="">
      </div>

      <div class="gallery-item">
        <img src="https://images.unsplash.com/photo-1487412912498-0447578fcca8?q=80&w=1200&auto=format&fit=crop" alt="">
      </div>

      <div class="gallery-item">
        <img src="https://images.unsplash.com/photo-1500530855697-b586d89ba3ee?q=80&w=1200&auto=format&fit=crop" alt="">
      </div>

    </div>
  </section>

  <!-- FILMS -->
  <section id="films" class="fade-in">
    <h2 class="section-title">Short Films</h2>

    <p class="section-sub">
      Visual poetry in motion — experimental neo-noir narratives,
      psychological tension, and cinematic atmosphere.
    </p>

    <div class="video-grid">

      <div class="video-card">
        <div class="video-frame">
          <iframe src="https://www.youtube.com/embed/ScMzIvxBSi4"
            allowfullscreen></iframe>
        </div>

        <div class="video-content">
          <h3>Midnight Echoes</h3>
          <p>
            A fragmented descent through rain-soaked streets
            and fading memories.
          </p>
        </div>
      </div>

      <div class="video-card">
        <div class="video-frame">
          <iframe src="https://www.youtube.com/embed/tgbNymZ7vqY"
            allowfullscreen></iframe>
        </div>

        <div class="video-content">
          <h3>Neon Confession</h3>
          <p>
            A quiet villain monologue wrapped in crimson light,
            silence, and smoke.
          </p>
        </div>
      </div>

    </div>
  </section>

  <!-- ABOUT -->
  <section id="about" class="fade-in">
    <div class="about">

      <div class="quote">
        “Cinema is not escape. <br>
        It is controlled darkness.”
      </div>

      <div class="about-card">
        <h2 class="section-title">About</h2>

        <p>
          I create visual worlds inspired by vintage noir films,
          psychological tension, and the beauty hidden inside chaos.
          My work blends cinematic storytelling with atmospheric
          photography — exploring loneliness, rebellion, obsession,
          and silence through moving images.
          <br><br>
          Every frame is designed like a memory:
          imperfect, dangerous, and impossible to forget.
        </p>
      </div>

    </div>
  </section>

  <!-- FOOTER -->
  <footer>
    © 2026 Noir Frames — Crafted in shadows.
  </footer>

  <!-- LIGHTBOX -->
  <div class="lightbox" id="lightbox">
    <span class="lightbox-close" id="closeLightbox">&times;</span>
    <img src="" alt="Preview" id="lightboxImg">
  </div>

  <script>

    // Fade-in Animation
    const fadeElements = document.querySelectorAll('.fade-in');

    const observer = new IntersectionObserver((entries)=>{
      entries.forEach(entry=>{
        if(entry.isIntersecting){
          entry.target.classList.add('show');
        }
      });
    }, {
      threshold:0.15
    });

    fadeElements.forEach(el => observer.observe(el));

    // Lightbox
    const galleryImages = document.querySelectorAll('.gallery-item img');
    const lightbox = document.getElementById('lightbox');
    const lightboxImg = document.getElementById('lightboxImg');
    const closeLightbox = document.getElementById('closeLightbox');

    galleryImages.forEach(img => {
      img.addEventListener('click', ()=>{
        lightbox.classList.add('active');
        lightboxImg.src = img.src;
      });
    });

    closeLightbox.addEventListener('click', ()=>{
      lightbox.classList.remove('active');
    });

    lightbox.addEventListener('click', (e)=>{
      if(e.target !== lightboxImg){
        lightbox.classList.remove('active');
      }
    });

    // Smooth Active Scroll Glow
    document.querySelectorAll('a[href^="#"]').forEach(anchor => {
      anchor.addEventListener('click', function (e) {
        e.preventDefault();

        document.querySelector(this.getAttribute('href'))
          .scrollIntoView({
            behavior: 'smooth'
          });
      });
    });

  </script>

</body>
</html># My-web1
