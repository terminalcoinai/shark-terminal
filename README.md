<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>Shark Terminal Coin Countdown</title>
  <style>
    /* Resetting some default styles */
    * {
      margin: 0;
      padding: 0;
      box-sizing: border-box;
    }
    body {
      background-color: #000;
      color: #e0e0e0;
      font-family: Arial, sans-serif;
      display: flex;
      justify-content: center;
      align-items: center;
      height: 100vh;
      overflow: hidden;
      position: relative;
      text-align: center; /* Centering text */
    }

    /* ASCII Shark Styling */
    .shark-background {
      font-family: monospace;
      font-size: 1.5vw; /* Font size for better fit */
      line-height: 1; /* Adjusted line height for better readability */
      color: #00ffff; /* Neon blue for the ASCII art */
      opacity: 0.2; /* Adjusted opacity for better background effect */
      white-space: pre;
      position: absolute;
      z-index: 1;
      pointer-events: none;
    }

    /* Positioning sharks closer to center */
    .top-left {
      top: 20%;
      left: 20%;
      transform: translate(-50%, -50%);
    }
    .top-right {
      top: 20%;
      left: 40%; /* Moved more to the left */
      transform: translate(50%, -50%);
    }
    .bottom-left {
      bottom: 20%;
      left: 20%;
      transform: translate(-50%, 50%);
    }
    .bottom-right {
      bottom: 20%;
      left: 40%; /* Moved more to the left */
      transform: translate(50%, 50%);
    }

    /* Countdown Timer Styling */
    .countdown {
      position: relative;
      z-index: 2;
      font-size: 3rem; /* Font size for countdown */
      color: #00ffff; /* Neon blue for the countdown */
      opacity: 0.2; /* Set same opacity as shark ASCII */
      text-shadow: 0 0 10px #00ffff; /* Neon blue shadow for the countdown */
    }
  </style>
</head>
<body>
  <div class="shark-background top-left">
    ⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀<br>
    ⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀.⣤⣤⣀⠀⠀⠀<br>
    ⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⣠⡶⠾⢿⠙⠳⢿⣿⠛⠳⢄⠀<br>
    ⠀⠀⠀⠀⠀⠀⠀⠀⣴⠏⠀⠀⠴⠁⠀⢸⠀⠈⠳⢶⣌⠙⢦⠀⠀<br>
    ⠀⠀⠀⠀⢀⡀⠀⠘⠀⠀⠀⠀⠀⠀⠀⢸⠀⠀⠀⠀⠙⢦⣈⠳⢦⣄⡀⠀<br>
    ⠀⠀⠈⠙⠻⢶⣄⠀⠀⠀⠀⠀⠀⠀⢸⠀⠀⠀⠀⠀⠀⠙⢷⣌⠙⠿⣄⠀<br>
    ⠀⠀⠀⠀⠀⠀⠈⠙⠻⢶⣄⠀⠀⠀⢸⣀⡀⠀⠀⠀⢀⣀⣠⠤⠿⠛⠛⠻⢦⣄⣀⠀<br>
    ⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠈⠙⠻⣦⣤⠉⠙⠻⠿⠛⠋⠀⠀⠀⠀⠀⠀⠀⠙⠻⣦⠀<br>
    ⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠘⠙⢿⡀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⢹⠀<br>
    ⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠈⠙⠿⠦⢤⣀⡀⠀⠀⠀⠀⠀⠀⠀⢀⡿⠀<br>
    ⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠈⠙⠒⠶⢤⣤⣤⠴⠶⠾⠋⠀<br>
  </div>

  <div class="shark-background top-right">
    ⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀<br>
    ⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀.⣤⣤⣀⠀⠀⠀<br>
    ⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⣠⡶⠾⢿⠙⠳⢿⣿⠛⠳⢄⠀<br>
    ⠀⠀⠀⠀⠀⠀⠀⠀⣴⠏⠀⠀⠴⠁⠀⢸⠀⠈⠳⢶⣌⠙⢦⠀⠀<br>
    ⠀⠀⠀⠀⢀⡀⠀⠘⠀⠀⠀⠀⠀⠀⠀⢸⠀⠀⠀⠀⠙⢦⣈⠳⢦⣄⡀⠀<br>
    ⠀⠀⠈⠙⠻⢶⣄⠀⠀⠀⠀⠀⠀⠀⢸⠀⠀⠀⠀⠀⠀⠙⢷⣌⠙⠿⣄⠀<br>
    ⠀⠀⠀⠀⠀⠀⠈⠙⠻⢶⣄⠀⠀⠀⢸⣀⡀⠀⠀⠀⢀⣀⣠⠤⠿⠛⠛⠻⢦⣄⣀⠀<br>
    ⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠈⠙⠻⣦⣤⠉⠙⠻⠿⠛⠋⠀⠀⠀⠀⠀⠀⠀⠙⠻⣦⠀<br>
    ⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠘⠙⢿⡀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⢹⠀<br>
    ⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠈⠙⠿⠦⢤⣀⡀⠀⠀⠀⠀⠀⠀⠀⢀⡿⠀<br>
    ⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠈⠙⠒⠶⢤⣤⣤⠴⠶⠾⠋⠀<br>
  </div>

  <div class="shark-background bottom-left">
    ⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀<br>
    ⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀.⣤⣤⣀⠀⠀⠀<br>
    ⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⣠⡶⠾⢿⠙⠳⢿⣿⠛⠳⢄⠀<br>
    ⠀⠀⠀⠀⠀⠀⠀⠀⣴⠏⠀⠀⠴⠁⠀⢸⠀⠈⠳⢶⣌⠙⢦⠀⠀<br>
    ⠀⠀⠀⠀⢀⡀⠀⠘⠀⠀⠀⠀⠀⠀⠀⢸⠀⠀⠀⠀⠙⢦⣈⠳⢦⣄⡀⠀<br>
    ⠀⠀⠈⠙⠻⢶⣄⠀⠀⠀⠀⠀⠀⠀⢸⠀⠀⠀⠀⠀⠀⠙⢷⣌⠙⠿⣄⠀<br>
    ⠀⠀⠀⠀⠀⠀⠈⠙⠻⢶⣄⠀⠀⠀⢸⣀⡀⠀⠀⠀⢀⣀⣠⠤⠿⠛⠛⠻⢦⣄⣀⠀<br>
    ⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠈⠙⠻⣦⣤⠉⠙⠻⠿⠛⠋⠀⠀⠀⠀⠀⠀⠀⠙⠻⣦⠀<br>
    ⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠘⠙⢿⡀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⢹⠀<br>
    ⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠈⠙⠿⠦⢤⣀⡀⠀⠀⠀⠀⠀⠀⠀⢀⡿⠀<br>
    ⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠈⠙⠒⠶⢤⣤⣤⠴⠶⠾⠋⠀<br>
  </div>

  <div class="shark-background bottom-right">
    ⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀<br>
    ⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀.⣤⣤⣀⠀⠀⠀<br>
    ⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⣠⡶⠾⢿⠙⠳⢿⣿⠛⠳⢄⠀<br>
    ⠀⠀⠀⠀⠀⠀⠀⠀⣴⠏⠀⠀⠴⠁⠀⢸⠀⠈⠳⢶⣌⠙⢦⠀⠀<br>
    ⠀⠀⠀⠀⢀⡀⠀⠘⠀⠀⠀⠀⠀⠀⠀⢸⠀⠀⠀⠀⠙⢦⣈⠳⢦⣄⡀⠀<br>
    ⠀⠀⠈⠙⠻⢶⣄⠀⠀⠀⠀⠀⠀⠀⢸⠀⠀⠀⠀⠀⠀⠙⢷⣌⠙⠿⣄⠀<br>
    ⠀⠀⠀⠀⠀⠀⠈⠙⠻⢶⣄⠀⠀⠀⢸⣀⡀⠀⠀⠀⢀⣀⣠⠤⠿⠛⠛⠻⢦⣄⣀⠀<br>
    ⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠈⠙⠻⣦⣤⠉⠙⠻⠿⠛⠋⠀⠀⠀⠀⠀⠀⠀⠙⠻⣦⠀<br>
    ⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠘⠙⢿⡀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⢹⠀<br>
    ⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠈⠙⠿⠦⢤⣀⡀⠀⠀⠀⠀⠀⠀⠀⢀⡿⠀<br>
    ⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠈⠙⠒⠶⢤⣤⣤⠴⠶⠾⠋⠀<br>
  </div>

  <!-- Countdown Timer -->
  <div class="countdown">
    <span id="timer">$STC 24:00:00</span> <!-- Countdown format -->
  </div>

  <script>
    // Countdown Timer Logic
    let totalSeconds = 86400; // 24 hours in seconds
    const timerElement = document.getElementById('timer');

    const countdown = setInterval(() => {
      if (totalSeconds <= 0) {
        clearInterval(countdown);
        timerElement.innerHTML = "Time's up!";
      } else {
        const hours = String(Math.floor(totalSeconds / 3600)).padStart(2, '0');
        const minutes = String(Math.floor((totalSeconds % 3600) / 60)).padStart(2, '0');
        const seconds = String(totalSeconds % 60).padStart(2, '0');
        timerElement.innerHTML = `$STC ${hours}:${minutes}:${seconds}`; // Updated to include $STC
      }
      totalSeconds--;
    }, 1000);
  </script>
</body>
</html>
