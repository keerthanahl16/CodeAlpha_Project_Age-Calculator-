<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Age Calculator</title>
    <style>
        body {
            font-family: Arial, sans-serif;
            text-align: center;
            margin-top: 50px;
        }
    </style>
</head>
<body>
    <h2>Age Calculator</h2>
    <label for="dob">Date of Birth:</label>
    <input type="date" id="dob" required>
    <button onclick="calculateAge()">Calculate Age</button>
    <p id="result"></p>

    <script>
        function calculateAge() {
            var dobInput = document.getElementById('dob').value;
            var dob = new Date(dobInput);
            var today = new Date();
            var age = today.getFullYear() - dob.getFullYear();
            var monthDiff = today.getMonth() - dob.getMonth();

            // If the birthday has not occurred yet this year, subtract one year
            if (monthDiff < 0 || (monthDiff === 0 && today.getDate() < dob.getDate())) {
                age--;
            }

            document.getElementById('result').innerHTML = "Your age is: " + age;
        }
    </script>
</body>
</html>
