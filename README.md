<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Invitation Website</title>
    <link rel="stylesheet" href="gf.css">
</head>
<body>
    <!-- Login Page -->
    <div class="login-page" id="login">
        <h1>Login</h1>
        <form id="loginForm">
            <label for="username">Username:</label>
            <input type="text" id="username" name="username" placeholder="Enter your username" required><br>

            <label for="password">Password:</label>
            <input type="password" id="password" name="password" placeholder="Enter your password" required><br>

            <button type="button" onclick="validateLogin()">Login</button>
        </form>
    </div>

    <!-- Welcome Page -->
    <div class="welcome-page" id="welcome" style="display: none;">
        <h1>🎉 Hello my pretty crush! 🎉</h1>
        <p>"This is a special page for you."</p>
        <button onclick="goToForm()">Let's start!</button>
    </div>

    <!-- Form Page -->
    <div class="form-page" id="form" style="display: none;">
        <h2>Invitation Form</h2>
        <form>
            <label for="location">Preferred Location:</label>
            <input type="text" id="location" name="location" placeholder="Enter location" required><br>

            <label for="date">Date of Visit:</label>
            <input type="date" id="date" name="date" required><br>

            <label for="time">Time of Visit:</label>
            <input type="time" id="time" name="time" required><br>

            <label for="food">Preferred Food:</label>
            <input type="text" id="food" name="food" placeholder="Your favorite food" required><br>

            <button type="submit">Submit</button>
        </form>
    </div>

    <script>
        function validateLogin() {
            const username = document.getElementById("username").value;
            const password = document.getElementById("password").value;

            if (username === "guest" && password === "12345") {
                document.getElementById('login').classList.add('fade-out');
                setTimeout(() => {
                    document.getElementById('login').style.display = 'none';
                    document.getElementById('welcome').style.display = 'block';
                    document.getElementById('welcome').classList.add('fade-in');
                }, 500);
            } else {
                alert("Invalid username or password. Try 'guest' and '12345'.");
            }
        }

        function goToForm() {
            document.getElementById('welcome').classList.add('fade-out');
            setTimeout(() => {
                document.getElementById('welcome').style.display = 'none';
                document.getElementById('form').style.display = 'block';
                document.getElementById('form').classList.add('fade-in');
            }, 500);
        }
    </script>
</body>
</html>
