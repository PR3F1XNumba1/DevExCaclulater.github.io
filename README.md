
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

      var devExRate = 0.0035; // DevEx rate of 0.35%
      var devExAmount = robuxEarned * devExRate;

      document.getElementById("devex-result").textContent = "Based on the Robux earned, the DevEx amount is: " + devExAmount.toFixed(2) + " USD.";
    }
  </script>
</body>
</html>
