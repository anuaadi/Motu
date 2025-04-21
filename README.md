# Motu
<html lang="en">
<head>
  <meta charset="UTF-8" />
  <meta name="viewport" content="width=device-width, initial-scale=1.0"/>
  <title>Happy Birthday Motu</title>
  <style>
    body {
      margin: 0;
      font-family: 'Segoe UI', sans-serif;
      background-color: #0e0e0e;
      color: #fff;
      overflow-x: hidden;
    }
    .container {
      text-align: center;
      padding: 2rem;
      animation: fadeIn 2s ease-in-out;
    }
    h1 {
      font-size: 3em;
      color: #ff66cc;
      margin-bottom: 0.5em;
    }
    .love-message {
      font-size: 1.1em;
      max-width: 700px;
      margin: 1em auto;
      line-height: 1.6;
      color: #ccc;
      animation: fadeText 8s ease-in-out forwards;
    }
    @keyframes fadeText {
      0% { opacity: 0; }
      100% { opacity: 1; }
    }
    @keyframes fadeIn {
      from { opacity: 0; transform: translateY(30px); }
      to { opacity: 1; transform: translateY(0); }
    }
    .gallery {
      display: flex;
      flex-wrap: wrap;
      justify-content: center;
      gap: 12px;
      margin-top: 2em;
    }
    .gallery img {
      width: 120px;
      height: 120px;
      border-radius: 12px;
      border: 2px solid #ff66cc;
      object-fit: cover;
      transition: transform 0.3s;
    }
    .gallery img:hover {
      transform: scale(1.05);
    }
    .cake {
      position: relative;
      width: 160px;
      margin: 3rem auto 2rem;
    }
    .layer {
      height: 30px;
      border-radius: 10px;
      background: linear-gradient(to right, #ff99cc, #ff66cc);
      margin-bottom: 5px;
      border: 2px solid #fff;
    }
    .layer-bottom { width: 160px; }
    .layer-middle { width: 130px; margin: auto; }
    .layer-top { width: 100px; margin: auto; }
    .candle {
      width: 10px;
      height: 30px;
      background: #fff;
      position: absolute;
      top: -35px;
      left: 50%;
      transform: translateX(-50%);
      border-radius: 2px;
    }
    .flame {
      width: 10px;
      height: 15px;
      background: orange;
      border-radius: 50% 50% 0 0;
      position: absolute;
      top: -18px;
      left: 0;
      animation: flicker 0.3s infinite;
    }
    @keyframes flicker {
      0%, 100% { transform: scale(1); background: gold; }
      50% { transform: scale(1.1); background: orange; }
    }
  </style>
</head>
<body>
  <div class="container">
    <h1>Happy 21st Birthday, Motu</h1>
    <p id="ageText">Calculating age...</p>

    <div class="cake">
      <div class="layer layer-bottom"></div>
      <div class="layer layer-middle"></div>
      <div class="layer layer-top"></div>
      <div class="candle">
        <div class="flame"></div>
      </div>
    </div>

    <p class="love-message" id="loveMessage"></p>

    <div class="gallery">
      <img src="images/1.jpg" />
      <img src="images/2.jpg" />
      <img src="images/3.jpg" />
      <img src="images/4.jpg" />
      <img src="images/5.jpg" />
      <img src="images/6.jpg" />
      <img src="images/7.jpg" />
      <img src="images/8.jpg" />
    </div>

    <audio autoplay loop>
      <source src="audio/tu-hai-to.mp3" type="audio/mpeg" />
    </audio>
  </div>

  <script>
    function updateAge() {
      const birth = new Date('2003-04-22T00:00:00');
      const now = new Date();
      const diff = now - birth;
      const days = Math.floor(diff / (1000 * 60 * 60 * 24));
      const hrs = Math.floor((diff / (1000 * 60 * 60)) % 24);
      const mins = Math.floor((diff / (1000 * 60)) % 60);
      const secs = Math.floor((diff / 1000) % 60);
      document.getElementById('ageText').innerText =
        `Motu is ${days} days, ${hrs} hours, ${mins} minutes, and ${secs} seconds old.`;
    }
    setInterval(updateAge, 1000);

    const message = `From December 21, 2019, not a single second has passed without you in my thoughts.\nSometimes we fight, sometimes I say breakup—but deep down I never want you to leave.\nYou're my child, my friend, my best friend, my girlfriend—my everything.\nAll I want is to protect and love you forever.`;
    document.getElementById("loveMessage").innerText = message;
  </script>
</body>
</html>
