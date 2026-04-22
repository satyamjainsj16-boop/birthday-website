# birthday-website
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Happy 16th Birthday Anshika ❤️</title>
    <style>
        :root {
            --primary-pink: #ff4d6d;
            --accent-gold: #ffd700;
        }

        * { margin: 0; padding: 0; box-sizing: border-box; }

        body {
            font-family: 'Segoe UI', sans-serif;
            /* Deeper gradient for perfect text visibility */
            background: linear-gradient(135deg, #4b1248 0%, #711b5e 50%, #f0357c 100%);
            color: white;
            overflow-x: hidden;
            min-height: 100vh;
        }

        .section {
            display: none;
            width: 100%;
            min-height: 100vh;
            padding: 20px;
            text-align: center;
            flex-direction: column;
            justify-content: center;
            align-items: center;
        }

        .active { display: flex; animation: fadeIn 1s ease-in; }

        @keyframes fadeIn { from { opacity: 0; } to { opacity: 1; } }

        h1 { 
            font-size: 3rem; 
            text-shadow: 2px 4px 15px rgba(0,0,0,0.4); 
            margin-bottom: 15px; 
        }

        p { font-size: 1.2rem; opacity: 0.9; margin-bottom: 25px; }

        /* Cake Section */
        .cake-container { position: relative; cursor: pointer; margin: 30px 0; scale: 1.5; }
        .cake { font-size: 80px; transition: transform 0.3s; }
        .candle { 
            position: absolute; top: -10px; left: 50%; transform: translateX(-50%);
            font-size: 25px; animation: flicker 0.5s infinite alternate;
        }
        @keyframes flicker { 
            from { opacity: 1; transform: translateX(-50%) scale(1); } 
            to { opacity: 0.7; transform: translateX(-50%) scale(1.2); } 
        }

        /* Gift Grid */
        .gift-grid {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(250px, 1fr));
            gap: 25px;
            max-width: 1000px;
            width: 100%;
            margin-top: 30px;
        }

        .card {
            background: rgba(255, 255, 255, 0.1);
            backdrop-filter: blur(15px);
            border: 1px solid rgba(255, 255, 255, 0.2);
            border-radius: 25px;
            padding: 40px 20px;
            cursor: pointer;
            transition: 0.4s;
            box-shadow: 0 10px 30px rgba(0,0,0,0.2);
        }

        .card:hover { transform: translateY(-15px); background: rgba(255, 255, 255, 0.2); }

        /* Overlay Styles */
        .overlay {
            display: none;
            position: fixed;
            top: 0; left: 0; width: 100%; height: 100%;
            background: rgba(0,0,0,0.95);
            z-index: 100;
            padding: 50px 20px;
            overflow-y: auto;
        }

        .close-btn { position: fixed; top: 20px; right: 30px; font-size: 40px; cursor: pointer; color: white; z-index: 101; }

        /* Photo Polaroids */
        .polaroid-container {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(220px, 1fr));
            gap: 30px;
            max-width: 1100px;
            margin: 40px auto;
        }

        .polaroid {
            background: white;
            padding: 15px 15px 50px 15px;
            box-shadow: 0 15px 25px rgba(0,0,0,0.5);
            transform: rotate(-3deg);
            transition: 0.3s;
        }
        .polaroid:nth-child(even) { transform: rotate(3deg); }
        .polaroid:hover { transform: rotate(0deg) scale(1.1); z-index: 10; }
        .polaroid img { width: 100%; height: 280px; object-fit: cover; }
        .polaroid span { color: #333; font-family: 'Brush Script MT', cursive; font-size: 1.4rem; display: block; margin-top: 15px; }

        /* Content Styles */
        .love-letter { font-family: 'Georgia', serif; line-height: 1.8; color: #ffe5ec; max-width: 650px; margin: auto; text-align: left; }
        .heart-box-content { font-size: 1.5rem; max-width: 600px; margin: auto; color: var(--accent-gold); }

        button {
            padding: 15px 40px;
            background: var(--primary-pink);
            border: none;
            border-radius: 50px;
            color: white;
            font-size: 1.1rem;
            font-weight: bold;
            cursor: pointer;
            box-shadow: 0 5px 20px rgba(240, 53, 124, 0.4);
            transition: 0.3s;
        }
        button:hover { transform: scale(1.05); background: #ff2e63; }
    </style>
</head>
<body>

    <div class="section active" id="stage1">
        <h1>Happy 16th Birthday, Anshika! ❤️</h1>
        <p>A magical journey awaits the most special girl in the world.</p>
        <button onclick="nextStage('stage2')">Begin the Celebration ✨</button>
    </div>

    <div class="section" id="stage2">
        <h1 id="cake-text">Make a Wish & Tap the Cake! 🎂</h1>
        <div class="cake-container" onclick="cutCake()">
            <div class="candle" id="candle">🕯️</div>
            <div class="cake" id="cake-emoji">🎂</div>
        </div>
        <p id="instruction">Click the cake to cut it</p>
    </div>

    <div class="section" id="stage3">
        <h1>For You, From Satyam Jain 🎁</h1>
        <div class="gift-grid">
            <div class="card" onclick="openGift('letter')">
                <div style="font-size: 60px;">💌</div>
                <h2>A Love Letter</h2>
                <p>Words from my heart</p>
            </div>
            <div class="card" onclick="openGift('photos')">
                <div style="font-size: 60px;">📸</div>
                <h2>Old Memories</h2>
                <p>Our journey through time</p>
            </div>
            <div class="card" onclick="openGift('heart')">
                <div style="font-size: 60px;">💖</div>
                <h2>Heart Box</h2>
                <p>A special promise</p>
            </div>
        </div>
    </div>

    <div id="overlay-letter" class="overlay">
        <span class="close-btn" onclick="closeOverlay()">×</span>
        <div class="love-letter">
            <h2 style="font-size: 2.5rem; text-align: center; margin-bottom: 30px;">Dearest Anshika,</h2>
            <p>Sixteen years ago, the world became a brighter place because you were born. You aren't just my girlfriend; you're my best friend and my favorite person to laugh with.</p>
            <br>
            <p>Every moment spent with you feels like a gift. As you turn 16, I want you to know that I'll be right here cheering for you in everything you do. You are beautiful, kind, and incredibly special to me.</p>
            <br>
            <p style="font-size: 1.5rem; font-weight: bold; text-align: right;">Forever Yours,<br>Satyam Jain ❤️</p>
        </div>
    </div>

    <div id="overlay-photos" class="overlay">
        <span class="close-btn" onclick="closeOverlay()">×</span>
        <h2>Looking Back...</h2>
        <div class="polaroid-container">
            <div class="polaroid">
                <img src="photo1.jpg" alt="Memory 1">
                <span>Where it all started...</span>
            </div>
            <div class="polaroid">
                <img src="photo2.jpg" alt="Memory 2">
                <span>The sweetest smile!</span>
            </div>
            <div class="polaroid">
                <img src="photo3.jpg" alt="Memory 3">
                <span>Adventures with you</span>
            </div>
            <div class="polaroid">
                <img src="photo4.jpg" alt="Memory 4">
                <span>Always in my heart</span>
            </div>
        </div>
    </div>

    <div id="overlay-heart" class="overlay">
        <span class="close-btn" onclick="closeOverlay()">×</span>
        <div class="heart-box-content">
            <div style="font-size: 100px; margin-bottom: 20px;">💝</div>
            <h2>The Secret Promise</h2>
            <br>
            <p>"Anshika, from the little girl in those photos to the beautiful 16-year-old you are today, you have always had a magic about you."</p>
            <br>
            <p><strong>"Inside this box is a promise: to always make you feel loved, to hold your hand through everything, and to never stop being thankful for you. You are my 1 in 8 billion."</strong></p>
            <br>
            <p style="color: white; font-size: 1.2rem;">— Satyam Jain</p>
        </div>
    </div>

    <script>
        function nextStage(stageId) {
            document.querySelectorAll('.section').forEach(s => s.classList.remove('active'));
            document.getElementById(stageId).classList.add('active');
        }

        function cutCake() {
            const candle = document.getElementById('candle');
            const cakeEmoji = document.getElementById('cake-emoji');
            const text = document.getElementById('cake-text');
            
            candle.style.display = 'none';
            cakeEmoji.innerHTML = '🍰';
            text.innerHTML = "Yay! Happy Sweet 16, Anshika! 🎉";
            
            setTimeout(() => {
                nextStage('stage3');
            }, 2500);
        }

        function openGift(type) {
            document.getElementById('overlay-' + type).style.display = 'block';
            document.body.style.overflow = 'hidden'; // Stop scrolling
        }

        function closeOverlay() {
            document.querySelectorAll('.overlay').forEach(o => o.style.display = 'none');
            document.body.style.overflow = 'auto'; // Re-enable scrolling
        }
    </script>
</body>
</html>
