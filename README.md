# BIRTHDAY
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Happy 23rd Mayana Jabeen Khan</title>
    <link href="https://fonts.googleapis.com/css2?family=Dancing+Script:wght@700&family=Poppins:wght@300;400;600&display=swap" rel="stylesheet">
    <style>
        :root {
            --primary-pink: #ff4d6d;
            --secondary-pink: #ff85a1;
            --soft-pink: #fce4ec;
            --deep-pink: #c9184a;
        }

        * { 
            margin: 0; 
            padding: 0; 
            box-sizing: border-box; 
            cursor: url('data:image/svg+xml;utf8,<svg xmlns="http://www.w3.org/2000/svg" width="24" height="24" viewBox="0 0 24 24" fill="%23ff4d6d"><path d="M12 21.35l-1.45-1.32C5.4 15.36 2 12.28 2 8.5 2 5.42 4.42 3 7.5 3c1.74 0 3.41.81 4.5 2.09C13.09 3.81 14.76 3 16.5 3 19.58 3 22 5.42 22 8.5c0 3.78-3.4 6.86-8.55 11.54L12 21.35z"/></svg>'), auto; 
        }

        body {
            font-family: 'Poppins', sans-serif;
            background-color: var(--soft-pink);
            overflow: hidden; /* Locked until YES is clicked */
            text-align: center;
        }

        /* Continuous Falling Hearts */
        .heart-particle {
            position: fixed;
            top: -10%;
            color: var(--primary-pink);
            z-index: 999;
            pointer-events: none;
            animation: fall linear forwards;
        }
        @keyframes fall {
            to { transform: translateY(110vh) rotate(360deg); }
        }

        /* Opening Overlay */
        #overlay {
            position: fixed;
            inset: 0;
            background: var(--soft-pink);
            z-index: 2000;
            display: flex;
            flex-direction: column;
            justify-content: center;
            align-items: center;
            padding: 20px;
        }

        h1 { font-family: 'Dancing Script', cursive; color: var(--deep-pink); font-size: 2.8rem; }
        
        .btn-group { display: flex; gap: 20px; margin-top: 30px; }
        .btn {
            padding: 15px 45px;
            border: none;
            border-radius: 50px;
            font-weight: bold;
            font-size: 1.2rem;
            transition: 0.3s;
        }
        #yes-btn { background: var(--primary-pink); color: white; box-shadow: 0 4px 15px rgba(255, 77, 109, 0.4); }
        #no-btn { background: #e0e0e0; color: #9e9e9e; opacity: 0.6; pointer-events: none; }

        /* General Section Styling */
        section { 
            min-height: 100vh; 
            display: flex; 
            flex-direction: column; 
            align-items: center; 
            justify-content: center; 
            position: relative; 
            padding: 60px 20px; 
        }

        /* 23 Background Watermark */
        .age-watermark {
            position: absolute;
            font-size: 25rem;
            font-weight: 900;
            color: rgba(255, 77, 109, 0.07);
            z-index: -1;
            user-select: none;
        }

        /* Cake Section */
        .cake { position: relative; width: 220px; height: 130px; background: #f48fb1; border-radius: 10px 10px 0 0; margin-top: 60px; box-shadow: inset 0 -15px 0 #f06292; }
        .candles { position: absolute; top: -35px; left: 25px; display: flex; gap: 22px; }
        .candle { width: 12px; height: 45px; background: #fff; border-top: 5px solid var(--primary-pink); position: relative; }
        .flame { 
            position: absolute; top: -18px; left: 50%; transform: translateX(-50%);
            width: 14px; height: 20px; background: #ffca28; border-radius: 50% 50% 20% 20%;
            box-shadow: 0 0 10px #ffca28; animation: flicker 0.1s infinite alternate;
        }
        @keyframes flicker { from { opacity: 0.8; } to { opacity: 1; transform: translateX(-50%) scale(1.2); } }
        .blown .flame { display: none; }

        .blow-btn {
            margin-top: 50px; background: var(--primary-pink); color: white;
            padding: 18px 40px; border-radius: 8px; border: none; font-size: 1.1rem;
            font-weight: 600; text-transform: uppercase;
        }

        /* Envelope and Letter */
        .envelope-container { margin: 40px auto; perspective: 1000px; cursor: pointer; }
        .envelope {
            width: 300px; height: 180px; background: #e57373;
            position: relative; border-radius: 0 0 5px 5px;
            display: flex; align-items: center; justify-content: center;
            box-shadow: 0 10px 20px rgba(0,0,0,0.1);
        }
        .envelope::before {
            content: ''; position: absolute; top: -100px; left: 0;
            border-left: 150px solid transparent; border-right: 150px solid transparent;
            border-bottom: 100px solid #ef9a9a;
        }
        .open-btn { background: white; color: var(--deep-pink); border: none; padding: 12px 25px; border-radius: 20px; font-weight: bold; }

        .letter-content {
            display: none; width: 90%; max-width: 850px; background: white; 
            padding: 50px; margin: 40px auto; border-radius: 15px;
            box-shadow: 0 20px 50px rgba(0,0,0,0.1);
            font-family: 'Dancing Script', cursive; font-size: 1.7rem;
            line-height: 1.8; color: #333; text-align: left;
        }

        .love-text {
            color: #444; border-left: 5px solid var(--primary-pink); padding-left: 25px;
        }

        footer { padding: 40px; opacity: 0.6; font-size: 0.9rem; font-style: italic; }
    </style>
</head>
<body>

    <audio id="birthdaySong" loop>
        <source src="music.mp3" type="audio/mpeg">
    </audio>

    <div id="overlay">
        <h1>Is it the Birthday of the most beautiful girl?</h1>
        <div class="btn-group">
            <button class="btn" id="yes-btn" onclick="startAll()">YES</button>
            <button class="btn" id="no-btn">NO</button>
        </div>
    </div>

    <section>
        <div class="age-watermark">23</div>
        <h1>Happy 23rd Birthday</h1>
        <h2 style="font-family: 'Dancing Script'; font-size: 3.5rem; color: var(--primary-pink); margin-top: 10px;">Mayana Jabeen Khan</h2>
        
        <div class="cake" id="cakeObj">
            <div class="candles">
                <div class="candle"><div class="flame"></div></div>
                <div class="candle"><div class="flame"></div></div>
                <div class="candle"><div class="flame"></div></div>
                <div class="candle"><div class="flame"></div></div>
                <div class="candle"><div class="flame"></div></div>
            </div>
        </div>
        <button class="blow-btn" onclick="blowCandles()">BLOW CANDLE</button>
        <p style="margin-top: 40px; font-style: italic; opacity: 0.7;">Scroll down for a surprise...</p>
    </section>

    <section>
        <h1>A Special Birthday Wish</h1>
        <div class="envelope-container" onclick="revealBox('wishBox')">
            <div class="envelope">
                <button class="open-btn">OPEN ENVELOPE</button>
            </div>
        </div>
        
        <div id="wishBox" class="letter-content">
            <p>Dearest Jabeen,</p>
            <p>On your 23rd birthday, I wish you all the happiness your heart can hold. You are a unique soul, and being 23 only adds more charm to your beautiful personality. May this year be line-by-line filled with success, laughter, and endless blessings.</p>
            <p>You make the world a better place just by being in it. ❤️</p>
        </div>
    </section>

    <section>
        <h1>Express My Love On You Jabeen</h1>
        <div class="envelope-container" onclick="revealBox('loveBox')">
            <div class="envelope" style="background: var(--deep-pink);">
                <button class="open-btn">OPEN MY HEART</button>
            </div>
        </div>

        <div id="loveBox" class="letter-content">
            <div class="love-text">
                <p>Jabeen, mai tum se kuch khena chata hu, ur oo baat yeh hai ki hamare beech ithne dino se chalti huyi baato se has mazak se baad kar b koi ristha reh saktha hai jaise ki "Payar".</p><br>
                <p>Haan mujhe mai jaan saktha hu aap ne yeh sob socha na hoga par mere ko aap ke saath yeh wali feeling kyu aai pata nahi, Haan app kahen gey mai hi kyu ? Aaisa ky hai mujhe mai ?</p><br>
                <p>Payar kyu kidar kaisa halat jan ke nahi hota bas hojata hai aur oo aap se hua hai balke aap se hi hai, badal aur pani mile tho "barish hoti hai, aur mere bane the meri zindgi hoti hai".</p><br>
                <p>Mere payar aap par kitna hai oo lafzo mai eijehar nahi kar saktha par karna hoga tabhi tho aap ko mere payar ka pata hoga aur yeh akhri...</p><br>
                <p style="font-size: 2.2rem; color: var(--deep-pink); text-align: center; margin: 20px 0;">"JABEEN I LOVE U 🥂"</p>
                <p style="text-align: center; font-weight: 600;">Can u be my girl forever? Yeh Mera payar hai qabool karna aap ke uupar nir bhar hai jo b hoga I respect ur opinion.</p>
            </div>
        </div>
    </section>

    <footer>Created with ❤️ for Mayana Jabeen Khan</footer>

    <script>
        function startAll() {
            // Remove overlay and unlock scroll
            document.getElementById('overlay').style.display = 'none';
            document.body.style.overflow = 'auto';
            
            // Audio Playback
            const music = document.getElementById('birthdaySong');
            music.play().catch(error => console.log("User interaction required for audio."));

            // Start Heart Rain
            setInterval(generateHeart, 250);
        }

        function generateHeart() {
            const heart = document.createElement('div');
            heart.innerHTML = '❤️';
            heart.classList.add('heart-particle');
            heart.style.left = Math.random() * 100 + 'vw';
            heart.style.fontSize = (Math.random() * 20 + 15) + 'px';
            heart.style.animationDuration = (Math.random() * 3 + 3) + 's';
            document.body.appendChild(heart);
            setTimeout(() => heart.remove(), 6000);
        }

        function blowCandles() {
            document.getElementById('cakeObj').classList.add('blown');
            alert("Happy Birthday Jabeen! Your wish is on its way!");
        }

        function revealBox(id) {
            const box = document.getElementById(id);
            box.style.display = 'block';
            box.scrollIntoView({ behavior: 'smooth' });
        }

        // Keep page locked on load
        window.onload = () => {
            document.body.style.overflow = 'hidden';
        };
    </script>
</body>
</html>
