# Codeways_Task2
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Basic Calculator</title>
    <style>
        body, html {
            height: 100%;
            margin: 0;
            padding: 0;
            background-color: #e6f2f9a4;
            font-family:'Times New Roman', Times, serif;
        }

        .container {
            display: flex;
            flex-direction: column;
            justify-content: center;
            align-items: center;
            height: 100%;
        }

        .Heading {
            text-align: center;
            margin-top: 20px;
        }

        .calculator {
            width: 410px;
            border: 2.3px solid #242222;
            border-radius: 5.5px;
            padding: 15px;
            text-align: right;
        }

        .display {
            background-color: #83b189;
            border: 2px solid #030303;
            border-radius: 8px;
            padding: 30px;
            margin-bottom: 15px;
            text-align: right;
            font-size: 2.0em;
        }

        .buttons {
            display: grid;
            grid-template-columns: repeat(5, 1fr);
            grid-gap: 6px;
        }

        button {
            padding: 10px;
            font-size: 1.5em;
            border: none;
            background-color: #e3ba53;
            cursor: pointer;
        }

        button:hover {
            background-color: #877d7d;
        }

    </style>
</head>
<body>
  <div class="container">
    <div class="Heading">
      <h1>Basic Calculator</h1>
    </div>

    <div class="calculator">
        <div class="display" id="display">0</div>
        <div class="buttons">
            <button onclick="clearDisplay()">C</button>
            <button onclick="appendToDisplay('/')">/</button>
            <button onclick="appendToDisplay('*')">*</button>
            <button onclick="appendToDisplay('7')">7</button>
            <button onclick="appendToDisplay('8')">8</button>
            <button onclick="appendToDisplay('9')">9</button>
            <button onclick="appendToDisplay('-')">-</button>
            <button onclick="appendToDisplay('4')">4</button>
            <button onclick="appendToDisplay('5')">5</button>
            <button onclick="appendToDisplay('6')">6</button>
            <button onclick="appendToDisplay('+')">+</button>
            <button onclick="appendToDisplay('1')">1</button>
            <button onclick="appendToDisplay('2')">2</button>
            <button onclick="appendToDisplay('3')">3</button>
            <button onclick="calculateResult()">=</button>
            <button onclick="appendToDisplay('0')">0</button>
            <button onclick="appendToDisplay('.')">.</button>
        </div>
    </div>
  </div>

  <script>
    let displayValue = '0';

    function updateDisplay() {
        document.getElementById('display').innerText = displayValue;
    }

    function appendToDisplay(value) {
        if (displayValue === '0') {
            displayValue = value;
        } else {
            displayValue += value;
        }
        updateDisplay();
    }

    function clearDisplay() {
        displayValue = '0';
        updateDisplay();
    }

    function calculateResult() {
        try {
            displayValue = eval(displayValue);
        } catch (error) {
            displayValue = 'Error';
        }
        updateDisplay();
    }

    updateDisplay(); 
  </script>
</body>
</html>
