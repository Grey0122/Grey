<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8" />
  <meta name="viewport" content="width=device-width, initial-scale=1.0"/>
  <title>NS Digital Clock</title>
  <style>
    * {
      box-sizing: border-box;
      margin: 0;
      padding: 0;
      font-family: 'Segoe UI', Tahoma, Geneva, Verdana, sans-serif;
    }

    body {
      background: linear-gradient(135deg, #0f2027, #203a43, #2c5364);
      height: 100vh;
      display: flex;
      align-items: center;
      justify-content: center;
      animation: backgroundShift 20s ease infinite alternate;
    }

    @keyframes backgroundShift {
      0% {
        background: linear-gradient(135deg, #0f2027, #203a43, #2c5364);
      }
      100% {
        background: linear-gradient(135deg, #1a2a6c, #b21f1f, #fdbb2d);
      }
    }

    .clock-container {
      background: rgba(255, 255, 255, 0.1);
      backdrop-filter: blur(15px);
      border: 2px solid rgba(255, 255, 255, 0.2);
      padding: 50px 60px;
      border-radius: 25px;
      box-shadow: 0 10px 40px rgba(0, 0, 0, 0.4);
      text-align: center;
      transition: transform 0.3s ease;
    }

    .clock-container:hover {
      transform: scale(1.02);
      box-shadow: 0 12px 50px rgba(0, 255, 204, 0.5);
    }

    .title {
      font-size: 2.5rem;
      font-weight: bold;
      color: #ffffff;
      margin-bottom: 30px;
      letter-spacing: 3px;
      text-shadow: 1px 1px 10px rgba(255, 255, 255, 0.3);
    }

    #clock {
      font-size: 5rem;
      font-weight: 700;
      color: #00ffcc;
      text-shadow: 0 0 15px #00ffcc, 0 0 25px #00ffcc;
      transition: all 0.3s ease-in-out;
    }
  </style>
</head>
<body>
  <div class="clock-container">
    <div class="title">NS Digital Clock</div>
    <div id="clock">--:--:--</div>
  </div>

  <script>
    function updateClock() {
      const now = new Date();
      let hours = now.getHours().toString().padStart(2, '0');
      let minutes = now.getMinutes().toString().padStart(2, '0');
      let seconds = now.getSeconds().toString().padStart(2, '0');

      const currentTime = `${hours}:${minutes}:${seconds}`;
      document.getElementById('clock').textContent = currentTime;
    }

    // Initial call
    updateClock();

    // Update every second
    setInterval(updateClock, 1000);
  </script>
</body>
</html>
