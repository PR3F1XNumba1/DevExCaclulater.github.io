<!DOCTYPE html>
<html>
<head>
  <title>Roblox Tax Calculator</title>
  <style>
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
  <h1>Welcome to the Roblox Tax Calculator!</h1>

  <label for="robux-earned-input">Amount of Robux earned:</label>
  <input type="number" id="robux-earned-input">

  <button onclick="calculateTax()">Calculate Tax</button>

  <p id="tax-owed-result"></p>

  <script>
    function calculateTax() {
      var robuxEarnedInput = document.getElementById("robux-earned-input");
      var robuxEarned = parseInt(robuxEarnedInput.value);

      if (isNaN(robuxEarned) || robuxEarned < 0) {
        document.getElementById("tax-owed-result").textContent = "Invalid input. Please enter a positive number.";
        return;
      }

      var taxRate = 0.3; // Assuming a 30% tax rate
      var taxOwed = robuxEarned * taxRate;

      document.getElementById("tax-owed-result").textContent = "Based on the Robux earned, the tax owed is: " + taxOwed + " Robux.";
    }
  </script>
</body>
</html>
