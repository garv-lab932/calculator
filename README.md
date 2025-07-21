<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <title>Calculator</title>
  <style>
    body {
      background-color: #f4f4f4;
      display: flex;
      justify-content: center;
      align-items: center;
      height: 100vh;
      font-family: Arial, sans-serif;
    }

    .calculator {
      background-color: #fff;
      padding: 20px;
      border-radius: 20px;
      box-shadow: 0 10px 25px rgba(0, 0, 0, 0.1);
    }

    #display {
      width: 100%;
      height: 60px;
      font-size: 24px;
      text-align: right;
      margin-bottom: 10px;
      padding: 10px;
      border: 2px solid #ccc;
      border-radius: 10px;
    }

    .buttons {
      display: grid;
      grid-template-columns: repeat(4, 60px);
      gap: 10px;
      justify-content: center;
    }

    button {
      height: 60px;
      font-size: 20px;
      border: none;
      border-radius: 10px;
      background-color: #e0e0e0;
      cursor: pointer;
      transition: background 0.2s;
    }

    button:hover {
      background-color: #d4d4d4;
    }

    .operator {
      background-color: #ff9500;
      color: white;
    }

    .equal {
      background-color: #34c759;
      color: white;
      grid-column: span 2;
    }

    .clear {
      background-color: #ff3b30;
      color: white;
    }
  </style>
</head>
<body>

  <div class="calculator">
    <input type="text" id="display" disabled placeholder="0">
    <div class="buttons">
      <button onclick="clearDisplay()" class="clear">C</button>
      <button onclick="appendValue('(')">(</button>
      <button onclick="appendValue(')')">)</button>
      <button onclick="appendValue('/')" class="operator">÷</button>

      <button onclick="appendValue('7')">7</button>
      <button onclick="appendValue('8')">8</button>
      <button onclick="appendValue('9')">9</button>
      <button onclick="appendValue('*')" class="operator">×</button>

      <button onclick="appendValue('4')">4</button>
      <button onclick="appendValue('5')">5</button>
      <button onclick="appendValue('6')">6</button>
      <button onclick="appendValue('-')" class="operator">−</button>

      <button onclick="appendValue('1')">1</button>
      <button onclick="appendValue('2')">2</button>
      <button onclick="appendValue('3')">3</button>
      <button onclick="appendValue('+')" class="operator">+</button>

      <button onclick="appendValue('0')">0</button>
      <button onclick="appendValue('.')">.</button>
      <button onclick="calculate()" class="equal">=</button>
    </div>
  </div>

  <script>
    function appendValue(value) {
      document.getElementById('display').value += value;
    }

    function clearDisplay() {
      document.getElementById('display').value = '';
    }

    function calculate() {
      try {
        const result = eval(document.getElementById('display').value);
        document.getElementById('display').value = result;
      } catch (e) {
        document.getElementById('display').value = 'Error';
      }
    }
  </script>

</body>
</html>
