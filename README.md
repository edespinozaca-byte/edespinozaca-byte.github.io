!DOCTYPE html
html lang=es
head
  meta charset=UTF-8
  meta name=viewport content=width=device-width, initial-scale=1.0
  titleFlores Amarillas para Mi Cachetonatitle
  style
    body {
      margin 0;
      padding 0;
      background #fffbea;
      display flex;
      justify-content center;
      align-items center;
      height 100vh;
      overflow hidden;
      font-family 'Cursive', sans-serif;
    }

    .bouquet {
      position relative;
      width 300px;
      height 400px;
    }

    .flower {
      position absolute;
      width 80px;
      height 80px;
      background radial-gradient(circle, #ffeb3b, #fbc02d);
      border-radius 50%;
      animation float 6s infinite ease-in-out;
    }

    .flowerbefore, .flowerafter {
      content ;
      position absolute;
      width 80px;
      height 80px;
      background radial-gradient(circle, #ffeb3b, #fbc02d);
      border-radius 50%;
    }

    .flowerbefore { transform rotate(60deg); }
    .flowerafter { transform rotate(-60deg); }

    @keyframes float {
      0%, 100% { transform translateY(0px); }
      50% { transform translateY(-20px); }
    }

    .stem {
      position absolute;
      bottom 0;
      left 50%;
      width 10px;
      height 200px;
      background green;
      transform translateX(-50%);
      border-radius 5px;
    }

    .ribbon {
      position absolute;
      bottom 0;
      left 50%;
      transform translateX(-50%);
      width 180px;
      height 40px;
      background red;
      border-radius 20px;
      text-align center;
      line-height 40px;
      color white;
      font-weight bold;
      font-size 18px;
      box-shadow 0 0 15px rgba(255,0,0,0.5);
    }

     Pétalos cayendo 
    .petal {
      position absolute;
      width 15px;
      height 15px;
      background #ffeb3b;
      border-radius 50%;
      opacity 0.8;
      animation fall linear infinite;
    }

    @keyframes fall {
      0% { transform translateY(-10vh) rotate(0deg); opacity 1; }
      100% { transform translateY(110vh) rotate(360deg); opacity 0; }
    }

     Botón sorpresa 
    .surprise-btn {
      position absolute;
      bottom -70px;
      left 50%;
      transform translateX(-50%);
      background #ff4081;
      color white;
      border none;
      padding 15px 25px;
      border-radius 30px;
      font-size 18px;
      cursor pointer;
      animation pulse 2s infinite;
      box-shadow 0 0 20px rgba(255,64,129,0.6);
    }

    @keyframes pulse {
      0% { transform translateX(-50%) scale(1); }
      50% { transform translateX(-50%) scale(1.1); }
      100% { transform translateX(-50%) scale(1); }
    }

     Modal 
    .modal {
      display none;
      position fixed;
      z-index 1000;
      left 0;
      top 0;
      width 100%;
      height 100%;
      background rgba(0,0,0,0.7);
      backdrop-filter blur(5px);
      justify-content center;
      align-items center;
    }

    .modal-content {
      background #fff3cd;
      padding 30px;
      border-radius 20px;
      text-align center;
      max-width 500px;
      font-size 20px;
      color #5a2d0c;
      position relative;
      box-shadow 0 0 25px rgba(255, 193, 7, 0.8);
      animation zoomIn 0.5s ease;
    }

    @keyframes zoomIn {
      from { transform scale(0.5); opacity 0; }
      to { transform scale(1); opacity 1; }
    }

    .close-btn {
      margin-top 20px;
      padding 10px 20px;
      background gold;
      border none;
      border-radius 15px;
      cursor pointer;
      font-weight bold;
      transition background 0.3s;
    }

    .close-btnhover { background orange; }

     Corazones en el modal 
    .heart {
      position absolute;
      color red;
      font-size 24px;
      animation floatHearts 4s infinite ease-in-out;
    }

    @keyframes floatHearts {
      0% { transform translateY(0) scale(1); opacity 1; }
      100% { transform translateY(-50px) scale(1.5); opacity 0; }
    }
  style
head
body

  !-- Música de fondo --
  audio autoplay loop
    source src=httpswww.bensound.combensound-musicbensound-romantic.mp3 type=audiompeg
  audio

  div class=bouquet
    div class=flower style=top 0; left 30%;div
    div class=flower style=top 20%; left 10%;div
    div class=flower style=top 15%; left 60%;div
    div class=flower style=top 40%; left 40%;div
    div class=stemdiv
    div class=ribbonMi Cachetona 💛div
    button class=surprise-btn onclick=openModal()Sorpresa 💌button
  div

  !-- Pétalos infinitos --
  script
    function createPetal() {
      const petal = document.createElement('div');
      petal.classList.add('petal');
      document.body.appendChild(petal);
      petal.style.left = Math.random()  100 + 'vw';
      petal.style.animationDuration = (3 + Math.random()  5) + 's';
      petal.style.opacity = Math.random();
      setTimeout(() = { petal.remove(); }, 8000);
    }
    setInterval(createPetal, 300);
  script

  !-- Modal --
  div id=myModal class=modal
    div class=modal-content
      p id=mensajep
      button class=close-btn onclick=closeModal()Cerrarbutton
      span class=heart style=top10%; left20%;❤️span
      span class=heart style=top50%; left80%;❤️span
      span class=heart style=top70%; left40%;❤️span
    div
  div

  script
    const frases = [
      Eres el sueño que jamás pensé cumplir y la razón de mi sonrisa cada día.,
      Si el mundo me pidiera definir el color de la felicidad, diría que es el amarillo de tus flores.,
      Tenerte cerca es como vivir en primavera eterna.,
      Mi mayor fortuna no es regalarte flores, es que tú florecieras en mi vida.,
      Las flores se marchitan, pero lo que siento por ti florece cada día más.
    ];

    function openModal() {
      document.getElementById(myModal).style.display = flex;
      document.getElementById(mensaje).innerText =
        frases[Math.floor(Math.random()frases.length)];
    }

    function closeModal() {
      document.getElementById(myModal).style.display = none;
    }
  script

body
html
