<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8" />
  <title>I'm Sorry, Hasti</title>
  <style>
    * {
      margin: 0;
      padding: 0;
      box-sizing: border-box;
    }

    body {
      font-family: 'Segoe UI', sans-serif;
      background-color: #fff0f5;
      overflow: hidden;
      position: relative;
      height: 100vh;
    }

    .message-box {
      position: relative;
      max-width: 600px;
      margin: 100px auto;
      padding: 30px;
      background: #ffffffdd;
      border-radius: 20px;
      text-align: center;
      box-shadow: 0 10px 30px rgba(0,0,0,0.2);
      z-index: 2;
    }

    h1 {
      font-size: 2.5rem;
      color: #e91e63;
      animation: bounce 1s infinite alternate;
    }

    p {
      font-size: 1.1rem;
      color: #333;
      line-height: 1.6;
      margin-top: 20px;
    }

    @keyframes bounce {
      from { transform: translateY(0); }
      to { transform: translateY(-10px); }
    }

    .heart-bg {
      position: absolute;
      top: 0;
      left: 0;
      width: 100%;
      height: 100%;
      z-index: 1;
      overflow: hidden;
    }

    .heart {
      position: absolute;
      width: 12px;
      height: 12px;
      background-color: red;
      transform: rotate(45deg);
      animation: floatUp 10s linear infinite;
      opacity: 0.7;
    }

    .heart::before,
    .heart::after {
      content: "";
      position: absolute;
      width: 12px;
      height: 12px;
      background-color: inherit;
      border-radius: 50%;
    }

    .heart::before {
      top: -6px;
      left: 0;
    }

    .heart::after {
      left: -6px;
      top: 0;
    }

    @keyframes floatUp {
      0% {
        transform: translateY(100vh) rotate(0deg);
        opacity: 0.7;
      }
      100% {
        transform: translateY(-100vh) rotate(360deg);
        opacity: 0;
      }
    }

    .button {
      display: inline-block;
      margin-top: 30px;
      padding: 12px 25px;
      background: #ff4081;
      color: white;
      font-size: 1.1rem;
      border: none;
      border-radius: 30px;
      box-shadow: 0 4px 12px rgba(0,0,0,0.3);
      cursor: pointer;
      text-decoration: none;
      animation: glow 1.5s infinite alternate;
    }

    @keyframes glow {
      from {
        box-shadow: 0 0 10px #ff4081;
      }
      to {
        box-shadow: 0 0 20px #ff4081, 0 0 30px #ff79a8;
      }
    }

    .hidden {
      display: none;
    }

  </style>
</head>
<body>

  <div class="heart-bg"></div>

  <div class="message-box">
    <h1>Hello Hasti</h1>
    <p id="introMessage" class="hidden">
      I just want to say something special to you...<br><br>
      I'm sorry for any hurt I caused you. You mean a lot to me.<br><br>
      Please read this, from my heart to yours.
    </p>

    <p id="poeticMessage" class="hidden">
      Dear Hasti,<br><br>
      Sometimes words fall short,<br>
      and silence gets loud.<br>
      I never meant to hurt you,<br>
      or make you feel left out.<br><br>

      You're more than just a friend to me,<br>
      you're sunshine on my rainy days.<br>
      And I miss your smile, your jokes,<br>
      and all our silly ways.<br><br>

      So here I am, heart in hand,<br>
      saying sorry with all I am.<br>
      Hoping that this message<br>
      brings a little smile back again.<br><br>

      With all my heart,<br>
      —Nisarg
    </p>

    <button id="helloButton" class="button">Hello Hasti</button>
    <button id="sorryButton" class="button hidden">Sorry Message</button>
    <button id="forgiveButton" class="button hidden">Will you forgive me?</button>
    <button id="thankYouButton" class="button hidden">Thank You!</button>
  </div>

  <script>
    // Floating colorful hearts
    const colors = ['#e91e63', '#f06292', '#f8bbd0', '#ff80ab', '#ec407a'];
    for (let i = 0; i < 40; i++) {
      let heart = document.createElement("div");
      heart.className = "heart";
      heart.style.left = Math.random() * 100 + "vw";
      heart.style.top = Math.random() * 100 + "vh";
      heart.style.backgroundColor = colors[Math.floor(Math.random() * colors.length)];
      heart.style.animationDuration = (Math.random() * 5 + 5) + "s";
      heart.style.opacity = Math.random();
      document.querySelector(".heart-bg").appendChild(heart);
    }

    // Show "Sorry" message after clicking "Hello Hasti"
    document.getElementById('helloButton').addEventListener('click', function() {
      document.getElementById('introMessage').classList.remove('hidden');
      document.getElementById('helloButton').classList.add('hidden');
      document.getElementById('sorryButton').classList.remove('hidden');
    });

    // Show poetic message after clicking "Sorry Message"
    document.getElementById('sorryButton').addEventListener('click', function() {
      document.getElementById('poeticMessage').classList.remove('hidden');
      document.getElementById('sorryButton').classList.add('hidden');
      document.getElementById('forgiveButton').classList.remove('hidden');
    });

    // Show Thank You message after clicking "Will you forgive me?"
    document.getElementById('forgiveButton').addEventListener('click', function() {
      document.getElementById('thankYouButton').classList.remove('hidden');
      document.getElementById('forgiveButton').classList.add('hidden');
      alert('Thank you for forgiving me, Hasti!');
    });
  </script>

</body>
</html>
