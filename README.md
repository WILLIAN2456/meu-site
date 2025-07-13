<!DOCTYPE html>
<html lang="pt-BR">
  <head>
    <meta charset="UTF-8" />
    <meta name="viewport" content="width=device-width, initial-scale=1.0" />
    <title>Calculadora</title>
    <style>
      body {
        display: flex;
        justify-content: center;
        align-items: center;
        height: 100vh;
        margin: 0;
        font-family: Arial, sans-serif;
        background-color: #f0f0f0;
      }
      .calculator {
        background-color: #333;
        padding: 20px;
        border-radius: 10px;
        box-shadow: 0 0 10px rgba(0, 0, 0, 0.3);
      }
      #display {
        width: 100%;
        height: 50px;
        font-size: 24px;
        text-align: right;
        padding: 10px;
        margin-bottom: 10px;
        border: none;
        background-color: #fff;
        border-radius: 5px;
      }
      .buttons {
        display: grid;
        grid-template-columns: repeat(4, 60px);
        gap: 5px;
      }
      button {
        padding: 20px;
        font-size: 18px;
        border: none;
        border-radius: 5px;
        background-color: #555;
        color: white;
        cursor: pointer;
      }
      button:hover {
        background-color: #777;
      }
      .operator {
        background-color: #ff9500;
      }
      .operator:hover {
        background-color: #ffaa33;
      }
      .equals {
        background-color: #28a745;
      }
      .equals:hover {
        background-color: #2cc24a;
      }
      .clear {
        background-color: #dc3545;
      }
      .clear:hover {
        background-color: #e4606d;
      }
    </style>
  </head>
  <body>
    <div class="calculator">
      <input type="text" id="display" readonly value="0" />
      <div class="buttons">
        <button class="clear" onclick="clearDisplay()">C</button>
        <button onclick="appendToDisplay('(')">(</button>
        <button onclick="appendToDisplay(')')">)</button>
        <button class="operator" onclick="appendToDisplay('/')">/</button>
        <button onclick="appendToDisplay('7')">7</button>
        <button onclick="appendToDisplay('8')">8</button>
        <button onclick="appendToDisplay('9')">9</button>
        <button class="operator" onclick="appendToDisplay('*')">×</button>
        <button onclick="appendToDisplay('4')">4</button>
        <button onclick="appendToDisplay('5')">5</button>
        <button onclick="appendToDisplay('6')">6</button>
        <button class="operator" onclick="appendToDisplay('-')">-</button>
        <button onclick="appendToDisplay('1')">1</button>
        <button onclick="appendToDisplay('2')">2</button>
        <button onclick="appendToDisplay('3')">3</button>
        <button class="operator" onclick="appendToDisplay('+')">+</button>
        <button onclick="appendToDisplay('0')">0</button>
        <button onclick="appendToDisplay('.')">.</button>
        <button class="equals" onclick="calculate()">=</button>
      </div>
    </div>

    <script>
      let display = document.getElementById("display");

      function appendToDisplay(value) {
        if (display.value === "0" && value !== ".") {
          display.value = value;
        } else {
          display.value += value;
        }
      }

      function clearDisplay() {
        display.value = "0";
      }

      function calculate() {
        try {
          display.value = eval(display.value);
        } catch (error) {
          display.value = "Erro";
          setTimeout(clearDisplay, 1000);
        }
      }
    </script>
  </body>
</html>
