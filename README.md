<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>Produto Escolhido</title>
  <style>
    /* Estilos gerais */
    body {
      font-family: Arial, sans-serif;
      line-height: 1.6;
      text-align: center;
    }

    /* Estilos para dispositivos móveis */
    @media screen and (max-width: 768px) {
      .timer-section {
        background-color: #f2f2f2;
        padding: 20px;
      }

      .timer-text {
        font-size: 18px;
        color: #333;
      }

      .timer-button {
        padding: 10px 20px;
        font-size: 16px;
        background-color: #007bff;
        color: #fff;
        border: none;
        border-radius: 5px;
        cursor: pointer;
      }
    }

    /* Estilos para desktop */
    @media screen and (min-width: 769px) {
      .timer-section {
        background-color: #007bff;
        padding: 30px;
      }

      .timer-text {
        font-size: 24px;
        color: #fff;
      }

      .timer-button {
        padding: 15px 30px;
        font-size: 20px;
        background-color: #f2f2f2;
        color: #007bff;
        border: none;
        border-radius: 5px;
        cursor: pointer;
      }
    }
  </style>
</head>
<body>
  <!-- Seção do Timer -->
  <div class="timer-section">
    <p class="timer-text">Aproveite nossa oferta por tempo limitado!</p>
    <p class="timer-text">Tempo restante:</p>
    <div id="timer" class="timer-text"></div>
    <button class="timer-button" onclick="alert('Parabéns! Você ganhou um desconto!')">Clique aqui para ganhar um desconto</button>
  </div>

  <script>
    // Timer
    var countdownDate = new Date().getTime() + 3600000; // Defina aqui o tempo do timer em milissegundos (neste exemplo, 1 hora)
    var x = setInterval(function() {
      var now = new Date().getTime();
      var distance = countdownDate - now;
      var hours = Math.floor((distance % (1000 * 60 * 60 * 24)) / (1000 * 60 * 60));
      var minutes = Math.floor((distance % (1000 * 60 * 60)) / (1000 * 60));
      var seconds = Math.floor((distance % (1000 * 60)) / 1000);
      document.getElementById("timer").innerHTML = hours + "h " + minutes + "m " + seconds + "s ";
      if (distance < 0) {
        clearInterval(x);
        document.getElementById("timer").innerHTML = "EXPIRADO";
      }
    }, 1000);
  </script>
</body>
</html>
