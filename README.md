<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>A Special Message for My Wife</title>
    <style>
        body {
            display: flex;
            justify-content: center;
            align-items: center;
            height: 100vh;
            margin: 0;
            background-color: #fff0f3;
            font-family: 'Segoe UI', Tahoma, Geneva, Verdana, sans-serif;
            overflow: hidden;
            text-align: center;
        }

        #container {
            background: white;
            padding: 3rem;
            border-radius: 20px;
            box-shadow: 0 10px 25px rgba(255, 75, 110, 0.2);
            position: relative;
            max-width: 400px;
            width: 90%;
        }

        h1 {
            color: #ff4d6d;
            font-size: 2rem;
            margin-bottom: 1rem;
        }

        p {
            color: #590d22;
            font-size: 1.1rem;
            line-height: 1.5;
        }

        .buttons {
            display: flex;
            justify-content: center;
            gap: 20px;
            margin-top: 2rem;
        }

        button {
            padding: 12px 25px;
            font-size: 1rem;
            font-weight: bold;
            border: none;
            border-radius: 50px;
            cursor: pointer;
            transition: transform 0.2s;
        }

        #yesBtn {
            background-color: #ff4d6d;
            color: white;
        }

        #noBtn {
            background-color: #a4133c;
            color: white;
            position: relative;
        }

        #message {
            display: none;
            color: #ff4d6d;
            font-size: 1.5rem;
            font-weight: bold;
            margin-top: 1rem;
        }

        .heart {
            color: #ff4d6d;
            font-size: 50px;
            margin-bottom: 10px;
        }
    </style>
</head>
<body>

    <div id="container">
        <div class="heart">❤️</div>
        <div id="content">
            <img src="baby_us.jpg" 
             alt="Us as Baby" 
             style="width:100%; max-height: 300px; object-fit: cover; border-radius:15px; margin-bottom: 15px; box-shadow: 0 4px 10px rgba(0,0,0,0.1);">
            <h1>Will you be my Valentine?</h1>
            <p>To the most beautiful woman I know... <br> I promise to love you more every single day.</p>
            
            <div class="buttons">
                <button id="yesBtn" onclick="showLove()">YES!</button>
                <button id="noBtn" onmouseover="moveButton()">No</button>
            </div>
        </div>
        <div id="message">I knew you'd say yes! <br> I love you! 🌹</div>
    </div>

    <script>
        function moveButton() {
            const btn = document.getElementById('noBtn');
            // Calculate random positions within the viewport
            const x = Math.random() * (window.innerWidth - btn.offsetWidth);
            const y = Math.random() * (window.innerHeight - btn.offsetHeight);
            
            btn.style.position = 'absolute';
            btn.style.left = x + 'px';
            btn.style.top = y + 'px';
        }

        function showLove() {
            document.getElementById('content').style.display = 'none';
            document.getElementById('message').style.display = 'block';
            
            // Start confetti or heart shower (simple version)
            for(let i=0; i<50; i++) {
                createHeart();
            }
        }

        function createHeart() {
            const heart = document.createElement('div');
            heart.innerHTML = '❤️';
            heart.style.position = 'absolute';
            heart.style.left = Math.random() * 100 + 'vw';
            heart.style.top = '-20px';
            heart.style.fontSize = (Math.random() * 20 + 10) + 'px';
            heart.style.transition = 'transform ' + (Math.random() * 3 + 2) + 's linear';
            document.body.appendChild(heart);

            setTimeout(() => {
                heart.style.transform = 'translateY(110vh)';
            }, 100);

            setTimeout(() => {
                heart.remove();
            }, 5000);
        }
    </script>
</body>
</html>
