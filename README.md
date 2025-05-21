# kue

<!DOCTYPE html>
<html lang="en">
  <head>
    <meta charset="UTF-8" />
    <meta name="viewport" content="width=device-width, initial-scale=1.0" />
    <title>Happy Birthday</title>
    <style>
      @import url("https://fonts.googleapis.com/css2?family=Pacifico&family=Quicksand&display=swap");

      * {
        margin: 0;
        padding: 0;
        box-sizing: border-box;
      }

      html,
      body {
        height: 100%;
        background-color: #0d1117;
        font-family: "Quicksand", sans-serif;
        color: white;
        overflow: hidden;
      }

      .happy__birthday {
        display: flex;
        flex-direction: column;
        align-items: center;
        justify-content: center;
        min-height: 100vh;
        text-align: center;
        position: relative;
        padding: 20px;
        z-index: 1;
      }

      .subtitle {
        color: #00ff88;
        font-family: "Pacifico", cursive;
        font-size: 1.3em;
        margin-bottom: 20px;
      }

      .main-text {
        font-size: 2em;
        margin-top: 10px;
      }

      .highlight {
        color: #32ff7e;
        font-weight: bold;
        text-shadow: 0 0 10px #32ff7e;
      }

      .cake {
        font-size: 4em;
        animation: bounce 1s infinite alternate;
      }

      .balloons {
        position: absolute;
        bottom: -100px;
        width: 100%;
        display: flex;
        justify-content: space-around;
        pointer-events: none;
        z-index: 2;
      }

      .balloon {
        width: 40px;
        height: 60px;
        border-radius: 50%;
        border: 3px solid var(--clr);
        animation: rise 8s linear infinite;
        position: relative;
      }

      .balloon::after {
        content: "";
        position: absolute;
        width: 2px;
        height: 30px;
        background: var(--clr);
        bottom: -30px;
        left: 50%;
        transform: translateX(-50%);
      }

      @keyframes bounce {
        from {
          transform: translateY(0);
        }
        to {
          transform: translateY(-10px);
        }
      }

      @keyframes rise {
        0% {
          transform: translateY(100vh);
          opacity: 0;
        }
        10% {
          opacity: 1;
        }
        100% {
          transform: translateY(-100vh);
          opacity: 0;
        }
      }

      .firework {
        position: absolute;
        width: 5px;
        height: 5px;
        background: transparent;
        box-shadow: 0 0 #fff, 60px -60px #ff0, -60px -60px #f0f, 60px 60px #0ff,
          -60px 60px #0f0, 90px 0 #f00, -90px 0 #00f;
        animation: fireworks 1s ease-out infinite;
        top: 50%;
        left: 50%;
        transform: translate(-50%, -50%);
        z-index: 0;
      }

      @keyframes fireworks {
        0% {
          box-shadow: 0 0 #fff;
          opacity: 1;
        }
        50% {
          box-shadow: 0 0 #fff, 30px -30px #ff0, -30px -30px #f0f,
            30px 30px #0ff, -30px 30px #0f0, 45px 0 #f00, -45px 0 #00f;
        }
        100% {
          box-shadow: 0 0 #fff, 60px -60px #ff0, -60px -60px #f0f,
            60px 60px #0ff, -60px 60px #0f0, 90px 0 #f00, -90px 0 #00f;
          opacity: 0;
        }
      }
    </style>
  </head>
  <body>
    <!-- Musik -->
    <audio autoplay loop>
      <source
        src="https://www.soundhelix.com/examples/mp3/SoundHelix-Song-1.mp3"
        type="audio/mpeg"
      />
      Your browser does not support the audio element.
    </audio>

    <!-- Fireworks -->
    <div
      class="firework"
      style="top: 20%; left: 25%; animation-delay: 0s"
    ></div>
    <div
      class="firework"
      style="top: 30%; left: 75%; animation-delay: 0.5s"
    ></div>
    <div
      class="firework"
      style="top: 60%; left: 50%; animation-delay: 1s"
    ></div>

    <!-- Konten -->
    <div class="happy__birthday">
      <h3 class="subtitle">For the love of my life!</h3>
      <div class="cake">🎂</div>
      <h1 class="main-text">
        Happy <span class="highlight">20th</span> Birthday!
      </h1>

      <div class="balloons">
        <div class="balloon" style="--clr: #00f2ff"></div>
        <div class="balloon" style="--clr: #9eff00"></div>
        <div class="balloon" style="--clr: #fcd200"></div>
        <div class="balloon" style="--clr: #ff00f2"></div>
      </div>
    </div>

    <!-- Confetti -->
    <script src="https://cdn.jsdelivr.net/npm/canvas-confetti@1.6.0/dist/confetti.browser.min.js"></script>
    <script>
      setTimeout(() => {
        confetti({
          particleCount: 200,
          spread: 160,
          origin: { y: 0.6 },
        });
      }, 500);
    </script>
  </body>
</html>
