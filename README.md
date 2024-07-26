# Claude-
Códigos generados con Claude 
<!DOCTYPE html>
<html lang="es">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Calculadora Simple</title>
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
        .calculator {
            background-color: #333;
            border-radius: 10px;
            padding: 20px;
            box-shadow: 0 0 10px rgba(0,0,0,0.2);
        }
        .display {
            background-color: #fff;
            padding: 10px;
            margin-bottom: 10px;
            text-align: right;
            font-size: 24px;
            border-radius: 5px;
        }
        .buttons {
            display: grid;
            grid-template-columns: repeat(4, 1fr);
            gap: 10px;
        }
        button {
            padding: 15px;
            font-size: 18px;
            border: none;
            border-radius: 5px;
            cursor: pointer;
            background-color: #4CAF50;
            color: white;
        }
        button:hover {
            background-color: #45a049;
        }
        .operator {
            background-color: #ff9800;
        }
        .operator:hover {
            background-color: #e68a00;
        }
        .clear {
            background-color: #f44336;
        }
        .clear:hover {
            background-color: #da190b;
        }
    </style>
</head>
<body>
    <div class="calculator">
        <div class="display" id="display">0</div>
        <div class="buttons">
            <button onclick="clearDisplay()" class="clear">C</button>
            <button onclick="appendToDisplay('7')">7</button>
            <button onclick="appendToDisplay('8')">8</button>
            <button onclick="appendToDisplay('9')">9</button>
            <button onclick="appendToDisplay('+')" class="operator">+</button>
            <button onclick="appendToDisplay('4')">4</button>
            <button onclick="appendToDisplay('5')">5</button>
            <button onclick="appendToDisplay('6')">6</button>
            <button onclick="appendToDisplay('-')" class="operator">-</button>
            <button onclick="appendToDisplay('1')">1</button>
            <button onclick="appendToDisplay('2')">2</button>
            <button onclick="appendToDisplay('3')">3</button>
            <button onclick="appendToDisplay('*')" class="operator">*</button>
            <button onclick="appendToDisplay('0')">0</button>
            <button onclick="appendToDisplay('.')">.</button>
            <button onclick="calculate()" class="operator">=</button>
            <button onclick="appendToDisplay('/')" class="operator">/</button>
        </div>
    </div>

    <script>
        let displayValue = '0';

        function updateDisplay() {
            document.getElementById('display').innerText = displayValue;
        }

        function appendToDisplay(value) {
            if (displayValue === '0' && value !== '.') {
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

        function calculate() {
            try {
                displayValue = eval(displayValue).toString();
                updateDisplay();
            } catch (error) {
                displayValue = 'Error';
                updateDisplay();
            }
        }
    </script>
</body>
</html>
