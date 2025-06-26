<!DOCTYPE html>
<html lang="tr">
<head>
  <meta charset="UTF-8">
  <title>Aleyna'ya</title>
  <style>
    body {
      margin: 0;
      background: linear-gradient(to bottom right, #fff0f5, #ffe4e1);
      font-family: 'Georgia', serif;
      color: #333;
      overflow-x: hidden;
    }

    .message {
      max-width: 700px;
      margin: 80px auto;
      background: white;
      padding: 40px;
      border-radius: 20px;
      box-shadow: 0 10px 25px rgba(0,0,0,0.1);
      text-align: center;
      position: relative;
    }

    .message h1 {
      color: #ff3366;
      margin-bottom: 20px;
    }

    .long-text, .note, .gallery {
      opacity: 0;
      transform: translateY(20px);
      transition: opacity 1.2s ease, transform 1.2s ease;
    }

    .visible {
      opacity: 1;
      transform: translateY(0);
    }

    .divider {
      font-size: 24px;
      margin: 25px 0;
      animation: float 2.5s infinite;
    }

    .note {
      font-size: 17px;
      font-style: italic;
      margin: 10px 0;
    }

    .hearts-container {
      position: fixed;
      top: 0;
      left: 0;
      width: 100%;
      height: 100%;
      pointer-events: none;
      overflow: hidden;
      z-index: -1;
    }

    .heart {
      position: absolute;
      color: #ff69b4;
      font-size: 24px;
      animation: rise 10s linear infinite;
      opacity: 0.8;
    }

    @keyframes rise {
      0% {
        transform: translateY(100vh) scale(1);
        opacity: 0.8;
      }
      100% {
        transform: translateY(-10vh) scale(0.5);
        opacity: 0;
      }
    }

    @keyframes float {
      0% { transform: translateY(0); }
      50% { transform: translateY(-5px); }
      100% { transform: translateY(0); }
    }

    .gallery {
      margin-top: 40px;
    }

    .gallery h3 {
      margin-bottom: 20px;
      color: #ff3366;
    }

    .gallery img {
      width: 150px;
      margin: 10px;
      border-radius: 10px;
      box-shadow: 0 4px 10px rgba(0,0,0,0.2);
    }

  </style>
</head>
<body>

  <!-- Uçuşan Kalpler -->
  <div class="hearts-container" id="hearts-container"></div>

  <div class="message">
    <h1>Canım Aleyna'ya 💖</h1>

    <p class="long-text">
      Seninle tanıştığım günden beri hayatım daha anlamlı, daha huzurlu.  
      Gözlerinle aydınlanan günlerim, gülüşünle güzelleşiyor.  
      Bazen bir bakışın, bütün yorgunluğumu alıyor.  
      Sana her baktığımda "iyi ki" demekten kendimi alamıyorum.  
      Çünkü sen; kalbimin en güzel yerinde, en özel şekilde duran kişisin.  
      Zaman geçse de, her geçen gün sevgim biraz daha büyüyor.  
      Ve şunu bil ki: Ben seninle tamamlandım, seninle ben oldum, Aleyna.
    </p>

    <div class="divider">❤️ 🌼 ❤️ 🌼 ❤️</div>

    <p class="note">Sabah uyandığımda aklıma ilk sen geliyorsun.</p>
    <p class="note">Sesin bile huzur veriyor, seni duymak bile yetiyor.</p>

    <div class="divider">🌼 ❤️ 🌼 ❤️ 🌼</div>

    <p class="note">Beraber geçirdiğimiz her an, hafızamda bir şiir gibi.</p>
    <p class="note">Senin yanındayken zamanın nasıl geçtiğini bile anlamıyorum.</p>

    <div class="divider">❤️ 🌼 ❤️ 🌼 ❤️</div>

    <p class="note">Seni seviyorum çünkü sen, olduğun halinle bile mükemmelsin.</p>
    <p class="note">Ve ben, her gün biraz daha sana aşık oluyorum.</p>

    <div class="divider">💖 Seni çoook Seviyorum, Aleyna 💖</div>

    <div class="gallery">
      <h3>🌸 Birlikte Anılarımız</h3>
      <img src="foto1.jpg" alt="Birlikte Fotoğraf 1">
      <img src="foto2.jpg" alt="Birlikte Fotoğraf 2">
      <img src="foto3.jpg" alt="Birlikte Fotoğraf 3">
    </div>
  </div>

  <script>
    // Uçuşan kalpler
    const container = document.getElementById('hearts-container');
    const heartSymbols = ["❤️", "💖", "💘", "💕", "💞"];
    for (let i = 0; i < 30; i++) {
      const heart = document.createElement('div');
      heart.classList.add('heart');
      heart.style.left = Math.random() * 100 + "vw";
      heart.style.animationDelay = (Math.random() * 10) + "s";
      heart.innerText = heartSymbols[Math.floor(Math.random() * heartSymbols.length)];
      container.appendChild(heart);
    }

    // Scroll görünme efekti
    const observer = new IntersectionObserver((entries) => {
      entries.forEach(entry => {
        if (entry.isIntersecting) {
          entry.target.classList.add('visible');
        }
      });
    }, {
      threshold: 0.1
    });

    document.querySelectorAll('.long-text, .note, .gallery').forEach(el => {
      observer.observe(el);
    });
  </script>
</body>
</html>
