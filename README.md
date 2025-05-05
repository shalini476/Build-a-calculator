# Build-a-calculator
<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <title>Simple Calculator</title>
  <style>
    body {
      background-color: #e8eaf6;
      font-family: Arial, sans-serif;
      display: flex;
      justify-content: center;
      align-items: center;
      height: 100vh;
      margin: 0;
    }

    .calculator {
      background-color: #ffffff;
      padding: 20px;
      border-radius: 15px;
      box-shadow: 0 4px 10px rgba(0,0,0,0.2);
      width: 300px;
    }

    .display {
      width: 100%;
      height: 50px;
      font-size: 24px;
      margin-bottom: 15px;
      text-align: right;
      padding: 10px;
      border: 2px solid #ccc;
      border-radius: 8px;
      box-sizing: border-box;
    }

    .buttons {
      display: grid;
      grid-template-columns: repeat(4, 1fr);
      gap: 10px;
    }

    button {
      padding: 20px;
      font-size: 18px;
      border: none;
      border-radius: 8px;
      background-color: #3f51b5;
      color: white;
      cursor: pointer;
      transition: 0.2s ease;
    }

    button:hover {
      background-color: #303f9f;
    }

    .operator {
      background-color: #f50057;
    }

    .operator:hover {
      background-color: #c51162;
    }

    .equal {
      background-color: #4caf50;
    }

    .equal:hover {
      background-color: #388e3c;
    }

    .clear {
      background-color: #ff9800;
    }

    .clear:hover {
      background-color: #ef6c00;
    }
  </style>
</head>
<body>

<div class="calculator">
  <input type="text" class="display" id="display" readonly>
  <div class="buttons">
    <button onclick="appendValue('7')">7</button>
    <button onclick="appendValue('8')">8</button>
    <button onclick="appendValue('9')">9</button>
    <button class="operator" onclick="appendValue('/')">÷</button>

    <button onclick="appendValue('4')">4</button>
    <button onclick="appendValue('5')">5</button>
    <button onclick="appendValue('6')">6</button>
    <button class="operator" onclick="appendValue('*')">×</button>

    <button onclick="appendValue('1')">1</button>
    <button onclick="appendValue('2')">2</button>
    <button onclick="appendValue('3')">3</button>
    <button class="operator" onclick="appendValue('-')">−</button>

    <button onclick="appendValue('0')">0</button>
    <button onclick="appendValue('.')">.</button>
    <button class="equal" onclick="calculate()">=</button>
    <button class="operator" onclick="appendValue('+')">+</button>

    <button class="clear" onclick="clearDisplay()" style="grid-column: span 4">Clear</button>
  </div>
</div>

<script>
  let display = document.getElementById("display");

  function appendValue(value) {
    display.value += value;
  }

  function clearDisplay() {
    display.value = "";
  }

  function calculate() {
    try {
      display.value = eval(display.value);
    } catch {
      display.value = "Error";
    }
  }
</script>

</body>
</html>
