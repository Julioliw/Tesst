# Tesst
<!DOCTYPE html>
<html lang="fr">
<head>
  <meta charset="UTF-8">
  <title>Devine le nombre</title>
  <style>
    body {
      font-family: Arial, sans-serif;
      text-align: center;
      padding: 50px;
      background: #f0f0f0;
    }
    input, button {
      padding: 10px;
      font-size: 16px;
      margin-top: 10px;
    }
    #message {
      margin-top: 20px;
      font-weight: bold;
    }
  </style>
</head>
<body>
  <h1>Jeu : Devine le nombre</h1>
  <p>J'ai choisi un nombre entre 1 et 100.</p>
  <input type="number" id="guess" placeholder="Ton choix" min="1" max="100" />
  <button onclick="checkGuess()">Vérifier</button>
  <div id="message"></div>

  <script>
    const secret = Math.floor(Math.random() * 100) + 1;
    let attempts = 0;

    function checkGuess() {
      const guess = parseInt(document.getElementById('guess').value);
      const message = document.getElementById('message');
      attempts++;

      if (isNaN(guess) || guess < 1 || guess > 100) {
        message.textContent = "Entre un nombre valide entre 1 et 100.";
      } else if (guess === secret) {
        message.textContent = `Bravo ! Tu as trouvé en ${attempts} essai(s) !`;
        message.style.color = "green";
      } else if (guess < secret) {
        message.textContent = "C'est plus grand !";
        message.style.color = "orange";
      } else {
        message.textContent = "C'est plus petit !";
        message.style.color = "orange";
      }
    }
  </script>
</body>
</html>
