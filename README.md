<html>
<head>
  <title>Roblox DevEx Calculator</title>
  <style>
    /* Add your CSS styles here */
    body {
      font-family: Arial, sans-serif;
      margin: 0;
      padding: 20px;
      background-color: #f1f1f1;
    }

    h1 {
      color: #333;
      text-align: center;
    }

    label {
      display: block;
      margin-bottom: 10px;
      font-weight: bold;
    }

    input[type="number"] {
      width: 100%;
      padding: 10px;
      font-size: 16px;
      border: 1px solid #ccc;
      border-radius: 4px;
    }

    select {
      width: 100%;
      padding: 10px;
      font-size: 16px;
      border: 1px solid #ccc;
      border-radius: 4px;
      background-color: #fff;
    }

    button {
      display: block;
      margin-top: 10px;
      padding: 10px;
      font-size: 16px;
      color: #fff;
      background-color: #337ab7;
      border: none;
      border-radius: 4px;
      cursor: pointer;
    }

    button:hover {
      background-color: #23527c;
    }

    p {
      margin-top: 10px;
      font-weight: bold;
    }
  </style>
</head>
<body>
  <h1>Roblox DevEx Calculator</h1>

  <label for="robux-earned-input">Amount of Robux earned:</label>
  <input type="number" id="robux-earned-input">

  <label for="currency-select">Select currency:</label>
  <select id="currency-select">
    <option value="USD">USD</option>
    <option value="EUR">EUR</option>
    <option value="GBP">GBP</option>
    <option value="JPY">JPY</option>
    <!-- Add more currency options as needed -->
  </select>

  <button onclick="calculateDevEx()">Calculate DevEx</button>

  <p id="devex-result"></p>

  <script>
    function calculateDevEx() {
      var robuxEarnedInput = document.getElementById("robux-earned-input");
      var robuxEarned = parseInt(robuxEarnedInput.value);

      if (isNaN(robuxEarned) || robuxEarned < 0) {
        document.getElementById("devex-result").textContent = "Invalid input. Please enter a positive number.";
        return;
      }

      var currencySelect = document.getElementById("currency-select");
      var selectedCurrency = currencySelect.value;

      var exchangeRates = {
        USD: 0.0035, // DevEx rate for USD (0.35%)
        EUR: 0.003, // DevEx rate for EUR (0.30%)
        GBP: 0.0025, // DevEx rate for GBP (0.25%)
        JPY: 0.004, // DevEx rate for JPY (0.40%)
        // Add more currency rates as needed
      };

      var devExRate = exchangeRates[selectedCurrency];
      var devExAmount = robuxEarned * devExRate;

      document.getElementById("devex-result
