<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>Be My Valentine</title>
  <style>
    @import url('https://fonts.googleapis.com/css2?family=Pacifico&display=swap');
    
    body {
      font-family: 'Arial', sans-serif;
      background: linear-gradient(to bottom right, #ffe4e1, #ffb6c1);
      height: 100vh;
      overflow: hidden;
      display: flex;
      justify-content: center;
      align-items: center;
      margin: 0;
    }
    .container {
      text-align: center;
      color: #ff69b4;
    }
    h1 {
      font-family: 'Pacifico', cursive;
      font-size: 3.5rem;
      margin-bottom: 20px;
      color: #d33;
      text-shadow: 2px 2px #ffa6a6;
    }
    .button-container {
      display: flex;
      justify-content: center;
      gap: 30px;
    }
    button {
      font-size: 1.5rem;
      padding: 15px 30px;
      border: none;
      border-radius: 15px;
      cursor: pointer;
      transition: 0.3s ease;
    }
    .yes-btn {
      background-color: #ff69b4;
      color: white;
      box-shadow: 0 0 15px rgba(255, 105, 180, 0.7);
    }
    .yes-btn:hover {
      transform: scale(1.1);
    }
    .no-btn {
      background-color: #f08080;
      color: white;
      position: relative;
    }
    .no-btn:hover {
      background-color: #ff4d4d;
    }
    .final-message {
      font-family: 'Pacifico', cursive;
      font-size: 2.5rem;
      color: #ff1493;
      display: none;
      animation: fadeIn 2s ease;
    }
    @keyframes fadeIn {
      0% { opacity: 0; }
      100% { opacity: 1; }
    }
    .gif-container {
      margin-top: 20px;
    }
    .gif {
      width: 150px;
      height: auto;
      display: none;
      transition: 0.5s ease;
    }
  </style>
</head>
<body>
  <div class="container">
    <h1>Will you be my Valentine? 💖</h1>
    <div class="button-container">
      <button class="yes-btn">Yes</button>
      <button class="no-btn">No</button>
    </div>
    <div class="gif-container">
      <img src="https://media.giphy.com/media/l41YtZOb9EUABnuqA/giphy.gif" alt="Cute Gif" class="gif" id="gif">
    </div>
    <div class="final-message">
      Thank you for choosing me! You made the correct choice. You won't regret it! ❤️ You are my Valentine now! 🎉
    </div>
  </div>

  <script>
    const noBtn = document.querySelector('.no-btn');
    const yesBtn = document.querySelector('.yes-btn');
    const finalMessage = document.querySelector('.final-message');
    const container = document.querySelector('.container');
    const gif = document.querySelector('.gif');

    let reasons = [
      "Because I'm the best at giving hugs! 🥰",
      "Who else will send you memes at midnight? 🤭",
      "I'll bring you chocolates every day! 🍫",
      "We make the cutest team ever! 😍",
      "No one else will love you as much as I do! ❤️",
      "I promise, I'll always be there to make you smile! 😊",
      "Pwetty Please 😟😟"
    ];

    let gifs = [
      "https://media.giphy.com/media/l41YtZOb9EUABnuqA/giphy.gif",
      "https://media.giphy.com/media/xUPGcguWZHRC2HyBRS/giphy.gif",
      "https://media.giphy.com/media/3o6ZsYm5HnbsoMeKow/giphy.gif",
      "https://media.giphy.com/media/1BcfiGlOGXzQk/giphy.gif",
      "https://media.giphy.com/media/26AHONQ79FdWZhAI0/giphy.gif"
    ];

    noBtn.addEventListener('mouseover', () => {
      const randomX = Math.random() * (window.innerWidth - noBtn.offsetWidth);
      const randomY = Math.random() * (window.innerHeight - noBtn.offsetHeight);
      noBtn.style.position = 'absolute';
      noBtn.style.left = `${randomX}px`;
      noBtn.style.top = `${randomY}px`;
      container.querySelector('h1').innerText = reasons[Math.floor(Math.random() * reasons.length)];
      gif.src = gifs[Math.floor(Math.random() * gifs.length)];
      gif.style.display = 'block';
    });

    yesBtn.addEventListener('click', () => {
      container.querySelector('.button-container').style.display = 'none';
      container.querySelector('h1').style.display = 'none';
      gif.style.display = 'none';
      finalMessage.style.display = 'block';
    });
  </script>
</body>
</html>
