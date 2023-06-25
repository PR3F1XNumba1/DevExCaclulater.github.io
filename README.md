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
    <option value="USD">United States Dollar (USD)</option>
    <option value="EUR">Euro (EUR)</option>
    <option value="GBP">British Pound (GBP)</option>
    <option value="JPY">Japanese Yen (JPY)</option>
    <option value="CAD">Canadian Dollar (CAD)</option>
    <option value="AUD">Australian Dollar (AUD)</option>
    <option value="CHF">Swiss Franc (CHF)</option>
    <option value="CNY">Chinese Yuan (CNY)</option>
    <option value="INR">Indian Rupee (INR)</option>
    <option value="RUB">Russian Ruble (RUB)</option>
    <option value="BRL">Brazilian Real (BRL)</option>
    <option value="ZAR">South African Rand (ZAR)</option>
    <option value="MXN">Mexican Peso (MXN)</option>
    <option value="SEK">Swedish Krona (SEK)</option>
    <option value="SGD">Singapore Dollar (SGD)</option>
    <option value="HKD">Hong Kong Dollar (HKD)</option>
    <option value="NZD">New Zealand Dollar (NZD)</option>
    <option value="TRY">Turkish Lira (TRY)</option>
    <option value="KRW">South Korean Won (KRW)</option>
    <option value="NOK">Norwegian Krone (NOK)</option>
    <!-- Add more currencies here -->
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
        CAD: 0.0045, // DevEx rate for CAD (0.45%)
        AUD: 0.004, // DevEx rate for AUD (0.40%)
        CHF: 0.0035, // DevEx rate for CHF (0.35%)
        CNY: 0.005, // DevEx rate for CNY (0.50%)
        INR: 0.003, // DevEx rate for INR (0.30%)
        RUB: 0.0045, // DevEx rate for RUB (0.45%)
        BRL: 0.0035, // DevEx rate for BRL (0.35%)
        ZAR: 0.004, // DevEx rate for ZAR (0.40%)
        MXN: 0.004, // DevEx rate for MXN (0.40%)
        SEK: 0.003, // DevEx rate for SEK (0.30%)
        SGD: 0.0035, // DevEx rate for SGD (0.35%)
        HKD: 0.0035, // DevEx rate for HKD (0.35%)
        NZD: 0.004, // DevEx rate for NZD (0.40%)
        TRY: 0.004, // DevEx rate for TRY (0.40%)
        KRW: 0.0035, // DevEx rate for KRW (0.35%)
        NOK: 0.003, // DevEx rate for NOK (0.30%)
        // Add more currencies and their rates here
      };

      var devExRate = exchangeRates[selectedCurrency];
      var devExAmount = robuxEarned * devExRate;

      document.getElementById("devex-result").textContent = "Based on the Robux earned, the DevEx amount is: " + devExAmount.toFixed(2) + " " + selectedCurrency;
    }
  </script>
   <a class="donation-link" href="https://www.roblox.com/catalog/6735118737/Dark-Blue-Fendi-Hoodie" target="_blank">Donate Robux</a>
</body>
</html>
