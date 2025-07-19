<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Simple Calculator</title>
    <style>
        body {
            font-family: Arial, sans-serif;
            background-color: #e9e9e9;
            display: flex;
            justify-content: center;
            align-items: center;
            height: 100vh;
        }
        .calculator {
            background-color: #fff;
            padding: 20px;
            border-radius: 15px;
            box-shadow: 0 0 15px rgba(0,0,0,0.1);
        }
        #result {
            width: 100%;
            height: 40px;
            font-size: 1.5rem;
            text-align: right;
            margin-bottom: 10px;
            padding-right: 10px;
            border: 1px solid #ccc;
            border-radius: 5px;
        }
        .buttons {
            display: grid;
            grid-template-columns: repeat(4, 60px);
            grid-gap: 10px;
        }
    button {
        height: 60px;
            font-size: 1.2rem;
            border: none;
            border-radius: 8px;
            background-color: #f2f2f2;
            cursor: pointer;
            transition: background-color 0.2s;
        }
        button:hover {
            background-color: #9f1818;
        }
        .equal {
            background-color: #14518e;
            color: rgb(0, 0, 0);
        }
        .equal:hover {
            background-color: #070505;
        }
    </style>
</head>
<body>
    <div class="calculator">
        <input type="text" id="result" disabled>
        <div class="buttons">
            <button onclick="clearDisplay()">C</button>
            <button onclick="appendValue('(')">(</button>
            <button onclick="appendValue(')')">)</button>
            <button onclick="appendValue('/')">÷</button>

            <button onclick="appendValue('7')">7</button>
            <button onclick="appendValue('8')">8</button>
            <button onclick="appendValue('9')">9</button>
            <button onclick="appendValue('*')">×</button>

            <button onclick="appendValue('4')">4</button>
            <button onclick="appendValue('5')">5</button>
            <button onclick="appendValue('6')">6</button>
            <button onclick="appendValue('-')">−</button>

            <button onclick="appendValue('1')">1</button>
            <button onclick="appendValue('2')">2</button>
            <button onclick="appendValue('3')">3</button>
            <button onclick="appendValue('+')">+</button>

            <button onclick="appendValue('0')">0</button>
            <button onclick="appendValue('.')">.</button>
            <button class="equal" onclick="calculate()">=</button>
        </div>
    </div>

    <script>
        function appendValue(value) {
            document.getElementById('result').value += value;
        }

        function clearDisplay() {
            document.getElementById('result').value = '';
        }

        function calculate() {
            try {
                document.getElementById('result').value = eval(document.getElementById('result').value);
            } catch {
                document.getElementById('result').value = 'Error';
            }
        }
    </script>
</body>
</html>
    
