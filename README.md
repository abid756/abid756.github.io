<!DOCTYPE html>
<html lang="it">
<head>
  <meta charset="UTF-8" />
  <meta name="viewport" content="width=device-width, initial-scale=1.0"/>
  <title>Indovina il Numero</title>
  <style>
    body {
      font-family: Arial, sans-serif;
      background: #f0f8ff;
      text-align: center;
      padding: 50px;
    }
    h1 {
      color: #333;
    }
    input[type="number"] {
      padding: 10px;
      font-size: 16px;
      width: 60px;
    }
    button {
      padding: 10px 20px;
      font-size: 16px;
      cursor: pointer;
      margin-left: 10px;
    }
    #result {
      margin-top: 20px;
      font-size: 18px;
      font-weight: bold;
    }
  </style>
</head>
<body>

  <h1>Indovina il Numero!</h1>
  <p>Inserisci un numero tra 1 e 1000:</p>
  <input type="number" id="guess" min="1" max="1000"/>
  <button onclick="checkGuess()">Prova</button>
  <div id="result"></div>
  <button onclick="resetGame()">Ricomincia</button>

  <script>
    let randomNumber = Math.floor(Math.random() * 1000) + 1;
    let attempts = 0;

    function checkGuess() {
      const userGuess = Number(document.getElementById('guess').value);
      attempts++;
      function resetGame() {
  randomNumber = Math.floor(Math.random() * 1000) + 1;
  attempts = 0;
  document.getElementById('result').textContent = '';
  document.getElementById('guess').value = '';
}


      if (userGuess === randomNumber) {
        document.getElementById('result').textContent = `Bravo! Hai indovinato in ${attempts} tentativi.`;
      } else if (userGuess < randomNumber) {
        document.getElementById('result').textContent = 'Troppo basso! Riprova.';
      } else {
        document.getElementById('result').textContent = 'Troppo alto! Riprova.';
      }
    }
  </script>

</body>
</html>
