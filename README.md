<!DOCTYPE html>
<html lang="id">
<head>
  <meta charset="UTF-8">
  <title>Selamat Ulang Tahun, Ayang!</title>
  <style>
    body {
      margin: 0;
      padding: 0;
      font-family: 'Segoe UI', sans-serif;
      background: linear-gradient(#ffe6f0, #ffccff);
      color: #444;
      text-align: center;
    }

    h1 {
      color: #e91e63;
      font-size: 3em;
      margin-top: 40px;
    }

    .slideshow {
      margin: 30px auto;
      width: 300px;
      height: 300px;
      border-radius: 20px;
      overflow: hidden;
      box-shadow: 0 10px 20px rgba(0,0,0,0.3);
    }

    .slideshow img {
      width: 100%;
      height: 100%;
      object-fit: cover;
      display: none;
    }

    .slideshow img.active {
      display: block;
    }

    .message {
      font-size: 1.4em;
      max-width: 700px;
      margin: 30px auto;
      padding: 0 20px;
      animation: fadeIn 3s ease-in-out;
    }

    @keyframes fadeIn {
      from {opacity: 0;}
      to {opacity: 1;}
    }

    .button {
      background-color: #ff69b4;
      color: white;
      padding: 15px 30px;
      font-size: 1.2em;
      border: none;
      border-radius: 30px;
      cursor: pointer;
      margin-top: 30px;
      box-shadow: 0 5px 15px rgba(0,0,0,0.2);
      transition: transform 0.2s;
    }

    .button:hover {
      transform: scale(1.05);
    }

    .hearts {
      position: fixed;
      bottom: 0;
      left: 0;
      width: 100%;
      pointer-events: none;
    }

    .heart {
      width: 20px;
      height: 20px;
      position: absolute;
      background: red;
      transform: rotate(45deg);
      animation: floatUp 3s linear forwards;
    }

    .heart::before,
    .heart::after {
      content: "";
      width: 20px;
      height: 20px;
      background: red;
      position: absolute;
      border-radius: 50%;
    }

    .heart::before {
      top: -10px;
      left: 0;
    }

    .heart::after {
      top: 0;
      left: -10px;
    }

    @keyframes floatUp {
      to {
        transform: translateY(-800px) rotate(45deg);
        opacity: 0;
      }
    }

    audio {
      display: none;
    }
  </style>
</head>
<body>

<h1>🎂 Selamat Ulang Tahun Ayang! 🎂</h1>

<div class="slideshow">
  <img src="foto1.jpg" class="active" alt="Foto 1">
  <img src="foto2.jpg" alt="Foto 2">
  <img src="foto3.jpg" alt="Foto 3">
</div>

<div class="message">
  <p>Hari ini adalah hari di mana seseorang yang paling spesial di hidupku lahir ke dunia 🌍💖</p>
  <p>Terima kasih sudah hadir dan membuat hari-hariku berwarna 🎨</p>
  <p>Aku berjanji akan selalu sayang dan jaga kamu, dalam suka maupun duka 💑</p>
  <p>Happy Birthday, Sayang! 💕</p>
</div>

<button class="button" onclick="showLove()">Klik untuk kejutan 💌</button>

<div class="hearts" id="hearts"></div>

<audio autoplay loop>
  <source src="lagu.mp3" type="audio/mpeg">
</audio>

<script>
  // Slideshow
  let slideIndex = 0;
  const slides = document.querySelectorAll('.slideshow img');
  setInterval(() => {
    slides[slideIndex].classList.remove('active');
    slideIndex = (slideIndex + 1) % slides.length;
    slides[slideIndex].classList.add('active');
  }, 3000);

  // Heart animation
  function showLove() {
    for (let i = 0; i < 20; i++) {
      const heart = document.createElement('div');
      heart.classList.add('heart');
      heart.style.left = Math.random() * 100 + 'vw';
      heart.style.background = `hsl(${Math.random() * 360}, 100%, 70%)`;
      document.getElementById('hearts').appendChild(heart);
      setTimeout(() => heart.remove(), 3000);
    }
  }
</script>

</body>
</html>
