<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8" />
  <meta name="viewport" content="width=device-width, initial-scale=1.0" />
  <title>Will You Be My Valentine?</title>

  <style>
    body {
      margin: 0;
      font-family: Arial, Helvetica, sans-serif;
      height: 100vh;
      overflow: hidden;
    }

    /* Main Question Screen */
    .container {
      position: fixed;
      inset: 0;
      background: #ffb6c1;
      display: flex;
      justify-content: center;
      align-items: center;
      text-align: center;
    }

    .card {
      position: relative;
      z-index: 2;
    }

    h1 {
      font-size: clamp(1.8rem, 5vw, 2.5rem);
      margin-bottom: 30px;
      color: #4a0033;
    }

    .buttons {
      display: flex;
      justify-content: center;
      gap: 20px;
    }

    button {
      padding: 15px 30px;
      font-size: 1.2rem;
      border: none;
      border-radius: 10px;
      cursor: pointer;
    }

    .yes {
      background: #2ecc71;
      color: #0b3d1f;
    }

    .no {
      background: #e74c3c;
      color: #fff;
    }

    /* Floating emojis */
    .emoji {
      position: absolute;
      font-size: 2rem;
      animation: float 6s infinite ease-in-out;
      opacity: 0.8;
    }

    @keyframes float {
      0%   { transform: translateY(0); }
      50%  { transform: translateY(-40px); }
      100% { transform: translateY(0); }
    }

    /* YES Screen */
    .celebration {
      display: none;
      position: fixed;
      inset: 0;
      background: #2ecc71;
      color: #0b3d1f;
      display: flex;
      flex-direction: column;
      justify-content: center;
      align-items: center;
      font-size: 2.5rem;
      z-index: 10;
    }

    /* NO Screen */
    .ghost {
      display: none;
      position: fixed;
      inset: 0;
      background: #000;
      display: flex;
      justify-content: center;
      align-items: center;
      z-index: 10;
    }

    .ghost img {
      width: 100%;
      height: 100%;
      object-fit: cover;
      filter: grayscale(100%) contrast(120%);
    }
  </style>
</head>

<body>

  <!-- Question -->
  <div class="container" id="question">
    <div class="card">
      <h1>Will you be my Valentine? 💖</h1>
      <div class="buttons">
        <button class="yes" onclick="sayYes()">Yes</button>
        <button class="no" onclick="sayNo()">No</button>
      </div>
    </div>

    <!-- Floating emojis -->
    <div class="emoji" style="top:10%; left:15%;">💖</div>
    <div class="emoji" style="top:20%; right:20%;">🌸</div>
    <div class="emoji" style="bottom:20%; left:25%;">✨</div>
    <div class="emoji" style="bottom:15%; right:30%;">💗</div>
  </div>

  <!-- YES -->
  <div class="celebration" id="celebration">
    <div>YAYYY 💚</div>
    <div>🎉🌸✨</div>
  </div>

  <!-- NO -->
  <div class="ghost" id="ghost">
    <img src="ghost.png" alt="ghost" />
  </div>

  <script>
    function sayYes() {
      document.getElementById("question").style.display = "none";
      document.getElementById("celebration").style.display = "flex";
    }

    function sayNo() {
      document.getElementById("question").style.display = "none";
      document.getElementById("ghost").style.display = "flex";
    }
  </script>

</body>
</html>
