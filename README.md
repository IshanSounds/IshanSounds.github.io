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
      background: #111;
      color: #fff;
      display: flex;
      justify-content: center;
      align-items: center;
      height: 100vh;
      text-align: center;
    }

    .container {
      max-width: 600px;
      padding: 20px;
    }

    h1 {
      font-size: clamp(1.8rem, 5vw, 2.5rem);
      margin-bottom: 30px;
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
      border-radius: 8px;
      cursor: pointer;
      transition: transform 0.2s ease, box-shadow 0.2s ease;
    }

    button:hover {
      transform: scale(1.05);
      box-shadow: 0 10px 20px rgba(0, 0, 0, 0.3);
    }

    .yes {
      background: #2ecc71;
      color: #0b3d1f;
    }

    .no {
      background: #e74c3c;
      color: #fff;
    }

    /* Celebration screen */
    .celebration {
      display: none;
      position: fixed;
      inset: 0;
      background: radial-gradient(circle at top, #7cff9b, #1e7f43);
      color: #0b3d1f;
      justify-content: center;
      align-items: center;
      flex-direction: column;
      font-size: 2.5rem;
    }

    .celebration span {
      font-size: 4rem;
      margin-top: 20px;
    }

    /* Ghost screen */
    .ghost {
      display: none;
      position: fixed;
      inset: 0;
      background: #000;
      justify-content: center;
      align-items: center;
      flex-direction: column;
    }

    .ghost img {
      max-width: 80%;
      max-height: 80%;
      filter: grayscale(100%) contrast(120%);
    }

    .ghost p {
      margin-top: 20px;
      font-size: 1.5rem;
      color: #aaa;
    }
  </style>
</head>

<body>
  <div class="container" id="question">
    <h1>Will you be my Valentine? 💖</h1>

    <div class="buttons">
      <button class="yes" onclick="sayYes()">Yes</button>
      <button class="no" onclick="sayNo()">No</button>
    </div>
  </div>

  <div class="celebration" id="celebration">
    <div>YAYYY 💚</div>
    <span>🎉🌸✨</span>
    <p>Best Valentine ever.</p>
  </div>

  <div class="ghost" id="ghost">
    <img
      src="https://i.imgur.com/5ZQZ5Zy.jpeg"
      alt="Junji Ito style ghost"
    />
    <p>…oh.</p>
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
