<!DOCTYPE html>
<html lang="vi">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>KODER HEADSHOT</title>
    <style>
        body {
            display: flex;
            flex-direction: column;
            align-items: center;
            justify-content: center;
            height: 100vh;
            background-color: #808080; 
            position: relative; 
        }
        h1 {
            margin-bottom: 15px; 
            font-size: 38px; 
            color: #333; 
            animation: colorChange 2s infinite; 
            position: absolute; 
            top: 20px; 
            z-index: 3; 
            text-shadow: 2px 2px 4px rgba(0, 0, 0, 0.3); 
            font-family: 'Arial', sans-serif; 
            text-align: center; 
        }
        @keyframes colorChange {
            0% { color: #ff0000; }
            25% { color: #00ff00; }
            50% { color: #0000ff; }
            75% { color: #ff00ff; }
            100% { color: #ff0000; }
        }
        .npc {
            width: 100px;
            height: 300px;
            position: relative;
            margin-bottom: 20px;
            z-index: 2; 
            top: 50px; 
        }
        .head, .body, .arm, .leg {
            position: absolute;
            border-radius: 10px;
            border: 2px solid black; 
        }
        .head {
            width: 50px;
            height: 50px;
            background-color: #ffcc00;
            top: 0;
            left: 25px;
            display: flex;
            align-items: center;
            justify-content: center;
        }
        .body {
            width: 70px;
            height: 100px;
            background-color: #00ccff;
            top: 50px;
            left: 15px;
        }
        .arm {
            width: 22px; 
            height: 100px; 
            background-color: #33cc33; 
            top: 50px;
        }
        .arm.left {
            left: -6px; 
        }
        .arm.right {
            right: -8px; 
        }
        .leg {
            width: 30px;
            height: 100px;
            background-color: #33cc33; 
            top: 150px; 
        }
        .leg.left {
            left: 10px;
        }
        .leg.right {
            right: 10px;
        }
        .hidden {
            display: none; 
        }
        #npcImage {
            position: absolute; 
            top: 0; 
            left: 50%; 
            transform: translateX(-50%); 
            width: 300px; 
            z-index: 1; 
        }
        .icon {
            font-size: 30px; 
            position: absolute;
            top: 10px; 
            left: 50%; 
            transform: translateX(-50%); 
        }
        .button-container {
            display: flex;
            flex-wrap: wrap; 
            justify-content: center; 
            margin-top: 0px; 
        }
        button {
            margin: 10px;
            padding: 15px 30px; 
            font-size: 16px; 
            cursor: pointer; 
            background-color: transparent; 
            border: 2px solid #000; 
            transition: background-color 0.3s; 
            font-weight: bold; 
            color: #ffcc00; 
        }
        button.active {
            background-color: #4caf50; 
            color: white; 
        }
        .credit {
            margin-top: 20px; 
            font-size: 20px; 
            color: black; 
            text-align: center; 
        }
    </style>
</head>
<body>

    <h1>KODER HEADSHOT</h1>

    <img id="npcImage" src="https://img.upanh.tv/2025/01/20/4774CA97-678E-429D-8F46-8DF853ABD1FC.png" alt="Hình ảnh NPC" class="hidden">

    <div class="npc">
        <div class="head">
            <span class="icon">💀</span>
        </div>
        <div class="body"></div>
        <div class="arm left"></div>
        <div class="arm right"></div>
        <div class="leg left"></div>
        <div class="leg right"></div>
    </div>
    
    <div class="button-container">
        <button onclick="toggleHead(this)">HEADTRICK</button>
        <button onclick="toggleBody(this)">Body Aim</button>
        <button onclick="window.location.href='https://zalo.me/0868124375'">🩴 Admin</button>
        <button onclick="activateButton(this)">Aimlock Vip</button> 
    </div>

    <div class="credit">Phạm Đồng An</div> 

    <script>
        let headShotActive = false;
        let bodyActive = false;

        function toggleHead(button) {
            const head = document.querySelector('.head');
            const npcImage = document.getElementById('npcImage');
            headShotActive = !headShotActive;

            head.style.backgroundColor = headShotActive ? 'red' : '#ffcc00';

            npcImage.classList.toggle('hidden', !headShotActive);

            activateButton(button);
        }

        function toggleBody(button) {
            const body = document.querySelector('.body');
            bodyActive = !bodyActive;
            body.style.backgroundColor = bodyActive ? 'red' : '#00ccff';

            activateButton(button);
        }

        function activateButton(button) {
            const buttons = document.querySelectorAll('.button-container button');
            buttons.forEach(btn => {
                if (btn !== document.querySelector('button:nth-child(3)')) {
                    btn.classList.remove('active');
                }
            });
            button.classList.add('active');
        }
    </script>

</body>
</html>
