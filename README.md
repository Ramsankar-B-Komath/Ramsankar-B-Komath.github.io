<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Valentine's Surprise</title>
    <style>
        body {
            font-family: Arial, sans-serif;
            background-color: pink;
            text-align: center;
            margin: 0;
            padding: 0;
        }
        .container {
            position: absolute;
            top: 50%;
            left: 50%;
            transform: translate(-50%, -50%);
        }
        .hidden {
            display: none;
        }
        .btn {
            padding: 10px 20px;
            font-size: 18px;
            border: none;
            cursor: pointer;
            margin: 10px;
            border-radius: 5px;
        }
        .yes-btn {
            background-color: red;
            color: white;
        }
        .no-btn {
            background-color: gray;
            color: white;
            position: absolute;
        }
    </style>
</head>
<body>
    <div id="password-page" class="container">
        <h2>Enter the Secret Password</h2>
        <input type="password" id="password-input" placeholder="Password">
        <button class="btn" onclick="checkPassword()">Submit</button>
    </div>

    <div id="valentine-page" class="container hidden">
        <h2>Will you be my Valentine?</h2>
        <button class="btn yes-btn" onclick="showLove()">Yes</button>
        <button class="btn no-btn" onmouseover="moveNoButton()" id="no-btn">No</button>
    </div>

    <div id="result-page" class="container hidden">
        <h2>Yay! You're my Valentine! ❤️</h2>
        <img src="https://placekitten.com/300/300" alt="Cute Cat">
    </div>

    <script>
        function checkPassword() {
            let password = document.getElementById("password-input").value;
            if (password === "16042007") {
                document.getElementById("password-page").classList.add("hidden");
                document.getElementById("valentine-page").classList.remove("hidden");
            } else {
                alert("Wrong password! Try again.");
            }
        }

        function moveNoButton() {
            let noBtn = document.getElementById("no-btn");
            let x = Math.random() * (window.innerWidth - 100);
            let y = Math.random() * (window.innerHeight - 50);
            noBtn.style.left = x + "px";
            noBtn.style.top = y + "px";
        }

        function showLove() {
            document.getElementById("valentine-page").classList.add("hidden");
            document.getElementById("result-page").classList.remove("hidden");
        }
    </script>
</body>
</html>
