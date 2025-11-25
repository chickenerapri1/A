# A
<?php
// Simple signup handler (optional)
if ($_SERVER["REQUEST_METHOD"] === "POST") {
    $username = htmlspecialchars($_POST["username"]);
    $password = htmlspecialchars($_POST["password"]);
    $confirm  = htmlspecialchars($_POST["confirm"]);

    if ($password !== $confirm) {
        $error = "Passwords do not match!";
    } else {
        $success = "Account created for: $username";
    }
}
?>
<!DOCTYPE html>
<html>
<head>
    <title>Roblox - Sign Up</title>
    <style>
        body {
            margin: 0;
            font-family: Arial, sans-serif;
            background: #1a57d0;
            color: white;
            text-align: center;
        }
        .container {
            width: 900px;
            margin: auto;
            margin-top: 40px;
        }
        .header {
            font-size: 40px;
            font-weight: bold;
        }
        .subheader {
            font-size: 24px;
            margin-bottom: 40px;
        }
        .box {
            display: flex;
            background: rgba(0,0,0,0.15);
            padding: 20px;
            border-radius: 8px;
        }
        .left {
            width: 50%;
            padding: 20px;
        }
        .right {
            width: 50%;
            padding: 20px;
            text-align: left;
            background: rgba(0,0,0,0.2);
            border-radius: 6px;
        }
        input, select {
            width: 100%;
            padding: 10px;
            margin: 6px 0 15px 0;
            border-radius: 5px;
            border: none;
            font-size: 16px;
        }
        .btn {
            width: 100%;
            background: #28a745;
            color: white;
            padding: 12px;
            border: none;
            font-size: 20px;
            cursor: pointer;
            border-radius: 6px;
        }
        .btn:hover {
            background: #1f8a38;
        }
        .error { color: #ff4444; }
        .success { color: #00ff88; }
    </style>
</head>
<body>

<div class="container">

    <div class="header">Join millions of builders</div>
    <div class="subheader">and explore their creations</div>

    <div class="box">
        <div class="left">
            <img src="https://tr.rbxcdn.com/483e8878b4f5c5b7d63f803f12e7c25c/420/420/Image/Png" 
                 width="100%" style="border-radius: 8px;">
            <h2>What will you build?</h2>
        </div>

        <div class="right">
            <h2>Sign Up</h2>

            <?php 
            if (!empty($error)) echo "<p class='error'>$error</p>";
            if (!empty($success)) echo "<p class='success'>$success</p>";
            ?>

            <form method="POST">

                <label>Birthday</label>
                <select><option>Month</option></select>
                <select><option>Day</option></select>
                <select><option>Year</option></select>

                <label>Gender</label>
                <select>
                    <option>Male</option>
                    <option>Female</option>
                </select>

                <label>Username</label>
                <input type="text" name="username" required>

                <label>Password</label>
                <input type="password" name="password" required>

                <label>Confirm Password</label>
                <input type="password" name="confirm" required>

                <button class="btn">Sign Up</button>
            </form>
        </div>
    </div>
</div>

</body>
</html>
