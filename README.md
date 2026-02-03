# by-paviFrom paaaipuu
<html>
<head>
    <title>For Prabalika 💖</title>

    <!-- Google Font -->
    <link href="https://fonts.googleapis.com/css2?family=Leckerli+One&display=swap" rel="stylesheet">

    <style>
        body {
            text-align: center;
            font-family: 'Leckerli One', cursive;
            background: linear-gradient(to bottom right, #ffe6f0, #ffccd5);
            margin: 0;
            overflow: hidden;
        }

        h1 { color: #ff3366; margin-top: 100px; }
        h2 { color: #ff4d6d; }

        button {
            padding: 12px 25px;
            font-size: 18px;
            margin: 10px;
            cursor: pointer;
            border-radius: 12px;
            border: none;
            font-family: 'Leckerli One', cursive;
        }

        #yesBtn { background-color: #ff4d6d; color: white; }
        #noBtn { background-color: gray; color: white; position: absolute; }

        .gifts { display: none; margin-top: 40px; }

        .card {
            display: inline-block;
            background: white;
            padding: 20px;
            margin: 15px;
            border-radius: 15px;
            box-shadow: 0px 4px 15px rgba(0,0,0,0.2);
            width: 220px;
            cursor: pointer;
            transition: transform 0.3s;
        }

        .card:hover { transform: scale(1.1); }

        .heart {
            position: fixed;
            bottom: -10px;
            font-size: 20px;
            animation: floatUp 6s linear infinite;
        }

        @keyframes floatUp {
            0% { transform: translateY(0); opacity: 1; }
            100% { transform: translateY(-100vh); opacity: 0; }
        }

        .popup {
            position: fixed;
            top: 50%;
            left: 50%;
            transform: translate(-50%, -50%);
            background: white;
            padding: 25px;
            border-radius: 15px;
            box-shadow: 0px 4px 20px rgba(0,0,0,0.3);
            display: none;
            z-index: 10;
            max-width: 400px;
            text-align: center;
        }

        .popup button {
            margin-top: 15px;
            background: #ff4d6d;
            color: white;
        }

        .firework {
            position: fixed;
            font-size: 25px;
            animation: explode 1s ease-out forwards;
        }

        @keyframes explode {
            0% { transform: scale(0); opacity: 1; }
            100% { transform: scale(3); opacity: 0; }
        }

        .final-screen {
            display: none;
            position: fixed;
            top: 0;
            left: 0;
            width: 100%;
            height: 100%;
            background: black;
            color: white;
            justify-content: center;
            align-items: center;
            flex-direction: column;
            font-size: 40px;
            animation: fadeIn 2s ease-in;
        }

        @keyframes fadeIn {
            from {opacity: 0;}
            to {opacity: 1;}
        }

        .love-text {
            animation: pulse 1.5s infinite;
            color: #ff4d6d;
        }

        @keyframes pulse {
            0% { transform: scale(1); }
            50% { transform: scale(1.2); }
            100% { transform: scale(1); }
        }
    </style>
</head>

<body>

<h1>Prabalika 💖</h1>
<h2>Will You Be My Valentine? 🌹</h2>

<button id="yesBtn" onclick="celebrate()">Yes 💘</button>
<button id="noBtn">No 😢</button>

<!-- Background Music -->
<audio id="bgMusic" loop>
    <source src="piche-tere.mp3" type="audio/mpeg">
</audio>

<div class="gifts" id="giftsSection">
    <h2>Choose Your Gift 🎁</h2>

    <div class="card" onclick="openPopup(1)">
        <h3>🌹 Gift 1</h3>
        <p>A beautiful bouquet just for you.</p>
    </div>

    <div class="card" onclick="openPopup(2)">
        <h3>💌 Gift 2</h3>
        <p>A heartfelt love letter from me.</p>
    </div>

    <div class="card" onclick="openPopup(3)">
        <h3>✨ Gift 3</h3>
        <p>Our special confession memory.</p>
    </div>
</div>

<div class="popup" id="popupBox">
    <div id="popupText"></div>
    <button onclick="closePopup()">Close ❤️</button>
</div>

<div class="final-screen" id="finalScreen">
    <div class="love-text">I Love You 💝</div>
    <div style="margin-top:20px;">Prabalika ❤️</div>
</div>

<script>

const noBtn = document.getElementById("noBtn");

noBtn.addEventListener("mouseover", function() {
    const x = Math.random() * (window.innerWidth - 100);
    const y = Math.random() * (window.innerHeight - 50);
    noBtn.style.left = x + "px";
    noBtn.style.top = y + "px";
});

function celebrate() {
    document.getElementById("giftsSection").style.display = "block";

    const music = document.getElementById("bgMusic");
    music.volume = 0.5;
    music.play().catch(() => {});

    launchFireworks();
    setTimeout(showFinalScreen, 5000);
}

function launchFireworks() {
    for (let i = 0; i < 30; i++) {
        const firework = document.createElement("div");
        firework.className = "firework";
        firework.innerHTML = "🎆";
        firework.style.left = Math.random() * 100 + "vw";
        firework.style.top = Math.random() * 100 + "vh";
        document.body.appendChild(firework);
        setTimeout(() => { firework.remove(); }, 1000);
    }
}

function showFinalScreen() {
    document.getElementById("finalScreen").style.display = "flex";
}

function openPopup(gift) {
    const popup = document.getElementById("popupBox");
    const text = document.getElementById("popupText");

    if (gift === 1) {
        text.innerHTML = `
            <h3>🌹 Gift 1</h3>
            <p>For the most beautiful girl, these flowers represent how special you are to me.</p>
        `;
    }

    if (gift === 2) {
        text.innerHTML = `
            <h3>💌 A Letter For You</h3>
            <p>
            From the start since we met, you have always been my lucky charm 💖. 
            I want to face every happiness and sadness with you 🥺🤍. 
            You're my most favorite person ever 🥰.
            Love you forever ❤️
            </p>
            <img src="FB8E2649-232C-4B96-AA14-C4B3D0E63352.jpeg"
                 style="width:100%; max-width:300px; margin-top:15px; border-radius:15px; box-shadow:0 4px 15px rgba(0,0,0,0.3);">
        `;
    }

    if (gift === 3) {
        text.innerHTML = `
            <h3>✨ Gift 3</h3>
            <p>The day we confessed our feelings will always be my favorite memory.</p>
        `;
    }

    popup.style.display = "block";
}

function closePopup() {
    document.getElementById("popupBox").style.display = "none";
}

function createHeart() {
    const heart = document.createElement("div");
    heart.className = "heart";
    heart.innerHTML = "❤️";
    heart.style.left = Math.random() * 100 + "vw";
    heart.style.fontSize = Math.random() * 20 + 15 + "px";
    document.body.appendChild(heart);
    setTimeout(() => { heart.remove(); }, 6000);
}

setInterval(createHeart, 500);

</script>

</body>
</html>
