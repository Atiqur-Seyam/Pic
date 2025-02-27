# Pic<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Guess the Number Game</title>
    <style>
        body {
            font-family: Arial, sans-serif;
            display: flex;
            justify-content: center;
            align-items: center;
            height: 100vh;
            margin: 0;
            background-color: #f0f0f0;
        }
        .game-container {
            text-align: center;
            background-color: white;
            padding: 30px;
            border-radius: 10px;
            box-shadow: 0 5px 15px rgba(0, 0, 0, 0.1);
        }
        input, button {
            padding: 10px;
            margin: 5px;
            font-size: 16px;
            border-radius: 5px;
        }
        button {
            background-color: #4CAF50;
            color: white;
            border: none;
            cursor: pointer;
        }
        button:hover {
            background-color: #45a049;
        }
        .result {
            margin-top: 15px;
            font-size: 18px;
        }
    </style>
</head>
<body>
    <div class="game-container">
        <h1>Guess the Number Game</h1>
        <p>Guess a number between 1 and 100:</p>
        <input type="number" id="userGuess" min="1" max="100" />
        <button onclick="checkGuess()">Guess</button>
        <div id="result" class="result"></div>
    </div>

    <script>
        // Generate a random number between 1 and 100
        let randomNumber = Math.floor(Math.random() * 100) + 1;
        let attempts = 0;

        // Function to check the user's guess
        function checkGuess() {
            const userGuess = document.getElementById("userGuess").value;
            const resultDiv = document.getElementById("result");
            attempts++;

            if (userGuess == randomNumber) {
                resultDiv.innerHTML = `Congratulations! You guessed the number in ${attempts} attempts.`;
                resultDiv.style.color = 'green';
            } else if (userGuess > randomNumber) {
                resultDiv.innerHTML = `Too high! Try again.`;
                resultDiv.style.color = 'red';
            } else if (userGuess < randomNumber) {
                resultDiv.innerHTML = `Too low! Try again.`;
                resultDiv.style.color = 'red';
            }
        }
    </script>
</body>
</html>
