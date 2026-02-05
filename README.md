<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8" />
  <title>Valentine Crush</title>
  <link href="https://fonts.googleapis.com/css2?family=Great+Vibes&family=Poppins:wght@300;500;700&display=swap" rel="stylesheet" />
  <style>
    * {
      margin: 0;
      padding: 0;
      box-sizing: border-box;
    }

    body {
      background: radial-gradient(circle at top, #2b133d, #050308);
      height: 100vh;
      overflow: hidden;
      display: flex;
      align-items: center;
      justify-content: center;
      font-family: "Poppins", system-ui, sans-serif;
      color: #fff;
      text-align: center;
      position: relative;
    }

    /* Floating hearts background */
    .heart {
      position: absolute;
      width: 18px;
      height: 18px;
      background-color: #ff5c93;
      transform: rotate(45deg);
      animation: float 6s infinite;
      opacity: 0.7;
    }

    .heart::before,
    .heart::after {
      content: "";
      position: absolute;
      width: 18px;
      height: 18px;
      background-color: #ff5c93;
      border-radius: 50%;
    }

    .heart::before {
      top: -9px;
      left: 0;
    }

    .heart::after {
      left: -9px;
      top: 0;
    }

    @keyframes float {
      0% {
        transform: translateY(0) rotate(45deg);
        opacity: 0.8;
      }
      100% {
        transform: translateY(-110vh) rotate(45deg);
        opacity: 0;
      }
    }

    .card {
      position: relative;
      z-index: 5;
      padding: 30px 40px;
      background: rgba(10, 5, 25, 0.8);
      border-radius: 24px;
      box-shadow: 0 15px 40px rgba(0, 0, 0, 0.7);
      border: 1px solid rgba(255, 92, 147, 0.4);
      max-width: 420px;
    }

    .title {
      font-family: "Great Vibes", cursive;
      font-size: 3rem;
      color: #ff9ac9;
      margin-bottom: 10px;
    }

    .subtitle {
      font-size: 0.95rem;
      color: #f7e1ff;
      margin-bottom: 20px;
    }

    .main-line {
      font-size: 1.3rem;
      margin-bottom: 18px;
      color: #ffe5f3;
    }

    .main-line span {
      color: #ff5c93;
      font-weight: 700;
    }

    .alone-line {
      font-size: 0.9rem;
      color: #c9b3ff;
      margin-bottom: 25px;
      opacity: 0.9;
    }

    .btn {
      display: inline-block;
      padding: 10px 26px;
      border-radius: 999px;
      border: none;
      background: linear-gradient(135deg, #ff5c93, #ff9ac9);
      color: #fff;
      font-weight: 600;
      cursor: pointer;
      box-shadow: 0 8px 20px rgba(255, 92, 147, 0.5);
      transition: transform 0.2s ease, box-shadow 0.2s ease;
    }

    .btn:hover {
      transform: translateY(-2px) scale(1.03);
      box-shadow: 0 12px 26px rgba(255, 92, 147, 0.7);
    }

    .btn:active {
      transform: translateY(0) scale(0.97);
      box-shadow: 0 5px 14px rgba(255, 92, 147, 0.5);
    }

    .hidden-message {
      margin-top: 18px;
      font-size: 0.9rem;
      color: #fbd6ff;
      opacity: 0;
      transform: translateY(10px);
      transition: opacity 0.4s ease, transform 0.4s ease;
    }

    .hidden-message.show {
      opacity: 1;
      transform: translateY(0);
    }
  </style>
</head>
<body>
  <!-- Floating hearts will be created by JS -->

  <div class="card">
    <div class="title">Dear Crush,</div>
    <div class="subtitle">Another Valentine’s Day, me and my feelings again…</div>
    <div class="main-line">
      I kinda have a <span>tiny universe</span> of love for you.
    </div>
    <div class="alone-line">
      Even if I’m celebrating alone, my heart still chooses you every single time.
    </div>
    <button class="btn" onclick="revealMessage()">
      Tap to see my Valentine wish
    </button>
    <div id="hiddenMessage" class="hidden-message">
      So… would it be okay if, just in my little world, <br />
      <strong>you were my Valentine this year?</strong>
    </div>
  </div>

  <script>
    // create floating hearts
    function createHeart() {
      const heart = document.createElement("div");
      heart.classList.add("heart");
      heart.style.left = Math.random() * 100 + "vw";
      heart.style.bottom = "-40px";
      heart.style.animationDuration = 3 + Math.random() * 4 + "s";
      document.body.appendChild(heart);

      setTimeout(() => {
        heart.remove();
      }, 7000);
    }

    setInterval(createHeart, 300);

    // reveal hidden crush message
    function revealMessage() {
      const msg = document.getElementById("hiddenMessage");
      msg.classList.add("show");
    }
  </script>
</body>
</html>
