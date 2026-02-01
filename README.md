<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8" />
  <title>Be My Valentine 💖</title>
  <style>
    * {
      box-sizing: border-box;
      font-family: 'Poppins', sans-serif;
    }

    body {
      margin: 0;
      height: 100vh;
      background: radial-gradient(circle at top, #ff9a9e, #fad0c4);
      display: flex;
      align-items: center;
      justify-content: center;
      overflow: hidden;
    }

    .card {
      background: white;
      padding: 40px 50px;
      border-radius: 25px;
      text-align: center;
      box-shadow: 0 20px 40px rgba(0,0,0,0.2);
      position: relative;
      animation: pop 1s ease;
    }

    @keyframes pop {
      from { transform: scale(0.7); opacity: 0; }
      to { transform: scale(1); opacity: 1; }
    }

    h1 {
      color: #ff4d6d;
      font-size: 2.5rem;
      margin-bottom: 10px;
    }

    p {
      color: #555;
      font-size: 1.1rem;
      margin-bottom: 30px;
    }

    button {
      padding: 14px 35px;
      font-size: 1.1rem;
      border: none;
      border-radius: 50px;
      cursor: pointer;
      transition: all 0.3s ease;
      position: relative;
    }

    #yesBtn {
      background: linear-gradient(45deg, #ff4d6d, #ff758f);
      color: white;
      box-shadow: 0 10px 20px rgba(255,77,109,0.4);
    }

    #yesBtn:hover {
      transform: scale(1.1);
    }

    #noBtn {
      background: #eee;
      color: #333;
      position: absolute;
    }

    .buttons {
      position: relative;
      height: 80px;
    }

    .heart {
      position: fixed;
      color: #ff4d6d;
      font-size: 24px;
      animation: floatUp 4s linear forwards;
    }

    @keyframes floatUp {
      0% {
        transform: translateY(0) scale(1);
        opacity: 1;
      }
      100% {
        transform: translateY(-600px) scale(1.5);
        opacity: 0;
      }
    }

    .magic {
      font-size: 2rem;
      color: #ff4d6d;
      animation: glow 1.5s infinite alternate;
    }

    @keyframes glow {
      from { text-shadow: 0 0 10px #ff4d6d; }
      to { text-shadow: 0 0 30px #ff99ac; }
    }
  </style>
</head>
<body>

  <div class="card" id="card">
    <h1>Will you be my Valentine? 💘</h1>
    <p>You make my world brighter every day ✨</p>

    <div class="buttons">
      <button id="yesBtn">Yes 💖</button>
      <button id="noBtn">No 🙃</button>
    </div>
  </div>

  <script>
    const noBtn = document.getElementById("noBtn");
    const yesBtn = document.getElementById("yesBtn");
    const card = document.getElementById("card");

    noBtn.style.left = "60%";
    noBtn.style.top = "10px";

    noBtn.addEventListener("mouseover", () => {
      const x = Math.random() * 250;
      const y = Math.random() * 60;
      noBtn.style.left = `${x}px`;
      noBtn.style.top = `${y}px`;
    });

    yesBtn.addEventListener("click", () => {
      card.innerHTML = `
        <h1 class="magic">She Said YES 💍💖</h1>
        <p>Best decision ever 😘</p>
      `;
      createHearts();
      setInterval(createHearts, 500);
    });

    function createHearts() {
      for (let i = 0; i < 5; i++) {
        const heart = document.createElement("div");
        heart.className = "heart";
        heart.innerHTML = "💖";
        heart.style.left = Math.random() * 100 + "vw";
        heart.style.bottom = "-20px";
        document.body.appendChild(heart);
        setTimeout(() => heart.remove(), 4000);
      }
    }
  </script>

</body>
</html>
