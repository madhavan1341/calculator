# calculator

<!DOCTYPE html>
<html>
<head>
  <title>Calculator</title>
  <style>
	  .calculator {
  width: 220px;
  margin: 50px auto;
  padding: 10px;
  background-color: #ff0000;
  border-radius: 5px;
  text-align: center;
  box-shadow: 0px 0px 10px rgba(0, 0, 0, 0.3);
}

#result {
  width: 90%;
  margin: 10px;
  padding: 10px;
  font-size: 20px;
  border: none;
  background-color: #ffffff;
  color: #333333;
  border-radius: 5px;
  text-align: right;
}

.buttons {
  display: grid;
  grid-template-columns: repeat(4, 1fr);
  grid-gap: 5px;
}

button {
  padding: 15px;
  background-color: #ff7f7f;
  color: #ffffff;
  border: none;
  border-radius: 5px;
  cursor: pointer;
  font-size: 18px;
}

button:hover {
  background-color: #ff5f5f;
}

button.operator {
  background-color: #ffd37f;
  color: #333333;
  font-weight: bold;
}

button.operator:hover {
  background-color: #ffc36f;
}

button.equal {
  background-color: #7fff7f;
  color: #ffffff;
}

button.equal:hover {
  background-color: #5fff5f;
}

  </style>
  </head>
<body>
  <div class="calculator">
    <input type="text" id="result" readonly>
    <div class="buttons">
      <button onclick="clearResult()">C</button>
      <button onclick="appendValue(7)">7</button>
      <button onclick="appendValue(8)">8</button>
      <button onclick="appendValue(9)">9</button>
      <button onclick="appendValue(4)">4</button>
      <button onclick="appendValue(5)">5</button>
      <button onclick="appendValue(6)">6</button>
      <button onclick="appendValue(1)">1</button>
      <button onclick="appendValue(2)">2</button>
      <button onclick="appendValue(3)">3</button>
      <button onclick="appendValue(0)">0</button>
      <button onclick="appendOperator('+')">+</button>
      <button onclick="appendOperator('-')">-</button>
      <button onclick="appendOperator('*')">*</button>
      <button onclick="appendOperator('/')">/</button>
      <button onclick="calculate()">=</button>
    </div>
  </div>
  <script>let calculation = '';

function appendValue(value) {
  calculation += value;
  document.getElementById('result').value = calculation;
}

function appendOperator(operator) {
  calculation += operator;
  document.getElementById('result').value = calculation;
}

function calculate() {
  try {
    const result = eval(calculation);
    document.getElementById('result').value = result;
    calculation = '';
  } catch (error) {
    document.getElementById('result').value = 'Error';
  }
}

function clearResult() {
  calculation = '';
  document.getElementById('result').value = '';
}
</script>
</body>
</html>
