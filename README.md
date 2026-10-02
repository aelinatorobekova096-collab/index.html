# index.html
<!DOCTYPE html>
<html lang="ru">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>С Днём Рождения, Мамочка!</title>
  <style>
    * {
      box-sizing: border-box;
    }
    body {
      margin: 0;
      padding: 0;
      background: linear-gradient(135deg, #ff9a9e 0%, #fecfef 99%, #fecfef 100%);
      font-family: 'Segoe UI', Tahoma, Geneva, Verdana, sans-serif;
      display: flex;
      justify-content: center;
      align-items: center;
      min-height: 100vh;
      color: #333;
      overflow-x: hidden;
    }
    .card {
      background: rgba(255, 255, 255, 0.92);
      padding: 40px 30px;
      border-radius: 25px;
      box-shadow: 0 20px 40px rgba(0, 0, 0, 0.15);
      text-align: center;
      max-width: 550px;
      margin: 20px;
      backdrop-filter: blur(10px);
      position: relative;
    }
    .icon {
      font-size: 60px;
      margin-bottom: 10px;
      animation: bounce 2s infinite;
    }
    h1 {
      color: #ff4e50;
      font-size: 2.2em;
      margin-bottom: 15px;
    }
    p {
      font-size: 1.15em;
      line-height: 1.7;
      color: #555;
      margin: 15px 0;
    }
    .btn {
      background: linear-gradient(45deg, #ff4e50, #f9d423);
      color: white;
      border: none;
      padding: 14px 28px;
      font-size: 1.1em;
      font-weight: bold;
      border-radius: 50px;
      cursor: pointer;
      box-shadow: 0 5px 15px rgba(255, 78, 80, 0.4);
      transition: transform 0.2s, box-shadow 0.2s;
      margin-top: 15px;
    }
    .btn:hover {
      transform: scale(1.05);
      box-shadow: 0 8px 20px rgba(255, 78, 80, 0.6);
    }
    .btn:active {
      transform: scale(0.98);
    }
    @keyframes bounce {
      0%, 100% { transform: translateY(0); }
      50% { transform: translateY(-10px); }
    }
    .heart-particle {
      position: fixed;
      font-size: 24px;
      user-select: none;
      pointer-events: none;
      animation: fall 3s linear forwards;
    }
    @keyframes fall {
      0% {
        opacity: 1;
        transform: translateY(0) rotate(0deg);
      }
      100% {
        opacity: 0;
        transform: translateY(100vh) rotate(360deg);
      }
    }
  </style>
</head>
<body>

  <div class="card">
    <div class="icon">🌸</div>
    <h1>С Днём Рождения, Мамочка!</h1>
    <p>
      Дорогая, любимая мамочка! С праздником тебя! Спасибо тебе за твоё бесконечное добро, нежность, заботу и поддержку. Ты — самый главный и светлый человек в моей жизни.
    </p>
    <p>
      Желаю тебе крепкого здоровья, море радости, исполнения всех заветных желаний и побольше поводов для улыбок. Пусть каждый день приносит счастье, уют и вдохновение!
    </p>
    <button class="btn" onclick="createHearts()">Нажми сюда! 💖</button>
  </div>

  <script>
    function createHearts() {
      const hearts = ['💖', '🌸', '✨', '🌷', '💕', '🎉'];
      for (let i = 0; i < 30; i++) {
        setTimeout(() => {
          const heart = document.createElement('div');
          heart.classList.add('heart-particle');
          heart.innerText = hearts[Math.floor(Math.random() * hearts.length)];
          heart.style.left = Math.random() * 100 + 'vw';
          heart.style.top = '-20px';
          heart.style.animationDuration = (Math.random() * 2 + 2) + 's';
          document.body.appendChild(heart);

          setTimeout(() => {
            heart.remove();
          }, 4000);
        }, i * 100);
      }
    }
  </script>

</body>
</html>

