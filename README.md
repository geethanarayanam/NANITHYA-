<html lang="te">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>A Grand Surprise for Ravi & Sneha!</title>
    <link href="https://fonts.googleapis.com/css2?family=Poppins:wght@300;600&display=swap" rel="stylesheet">
    <style>
        :root {
            --hot-pink: #ff0a78;
            --gold: #ffd700;
            --spiritual-gold: #fff8e1;
        }
        body, html { margin: 0; padding: 0; height: 100%; font-family: 'Poppins', sans-serif; overflow: hidden; background: #000; color: white; }
        
        /* PAGE SYSTEM - Catchy Backgrounds per Page */
        .page { display: none; height: 100vh; width: 100vw; flex-direction: column; align-items: center; justify-content: center; position: absolute; text-align: center; background-size: cover; background-position: center; }
        .active { display: flex; animation: pageZoomIn 1.2s cubic-bezier(0.19, 1, 0.22, 1) forwards; }
        @keyframes pageZoomIn { from { transform: scale(1.1); opacity: 0; } to { transform: scale(1); opacity: 1; } }

        /* --- PAGE 1: BIG CATCHY HEART --- */
        #page1 { background: linear-gradient(135deg, #2b0014 0%, #1a0033 50%, #000 100%); }
        .bg-particles { position: absolute; top: 0; left: 0; width: 100%; height: 100%; }
        .floating-p { position: absolute; width: 10px; height: 10px; background: rgba(255,10,120,0.4); border-radius: 50%; animation: pFloat 6s linear infinite; }
        @keyframes pFloat { 0% { transform: translateY(100vh) scale(0); opacity: 0; } 10% { opacity: 1; } 90% { opacity: 1; } 100% { transform: translateY(-10vh) scale(1.5); opacity: 0; } }

        .super-big-heart {
            position: relative; width: 180px; height: 180px; /* BIGger than before */
            background: var(--hot-pink); transform: rotate(45deg);
            box-shadow: 0 0 100px var(--hot-pink);
            animation: pulseBeat 1.8s infinite ease-in-out; cursor: pointer;
            transition: 0.3s;
        }
        .super-big-heart::before, .super-big-heart::after {
            content: ""; position: absolute; width: 180px; height: 180px;
            background: var(--hot-pink); border-radius: 50%;
        }
        .super-big-heart::before { left: -90px; }
        .super-big-heart::after { top: -90px; }
        @keyframes pulseBeat { 0% { transform: rotate(45deg) scale(1); } 50% { transform: rotate(45deg) scale(1.15); box-shadow: 0 0 150px var(--hot-pink); } 100% { transform: rotate(45deg) scale(1); } }
        
        .beat-text { margin-top: 120px; font-size: 30px; letter-spacing: 5px; font-weight: 200; animation: textGlow 2s infinite; font-weight: bold;}
        @keyframes textGlow { 0%, 100% { text-shadow: 0 0 5px #fff; } 50% { text-shadow: 0 0 30px var(--hot-pink); color: var(--gold); } }

        /* --- PAGE 2: CATCHY GREETING (BOKEH BACKGROUND) --- */
        #page2 { background: radial-gradient(circle, #fff5f7 0%, #ffc1e3 100%); color: #333; }
        .card { background: white; padding: 50px; border-radius: 25px; box-shadow: 0 30px 60px rgba(0,0,0,0.15); border: 3px solid var(--hot-pink); max-width: 380px; }
        .btn-action { background: var(--hot-pink); color: white; border: none; padding: 18px 50px; border-radius: 35px; cursor: pointer; font-size: 20px; margin-top: 30px; transition: 0.3s; font-weight: bold; }
        .btn-action:hover { background: #d00040; transform: translateY(-5px); box-shadow: 0 10px 20px rgba(255,10,120,0.3); }

        /* --- PAGE 3: CATCHY GIFT (PARTY BACKGROUND) --- */
        #page3 { background: radial-gradient(circle, #001f3f 0%, #000 100%); }
        .big-gift { font-size: 150px; cursor: pointer; filter: drop-shadow(0 0 30px gold); animation: wobbleGift 2.5s infinite alternate; }
        @keyframes wobbleGift { from { transform: rotate(-8deg); } to { transform: rotate(8deg); } }

        /* --- PAGE 4: CATCHY TEMPLE (ETHEREAL BACKGROUND) --- */
        #page4 { background: linear-gradient(to bottom, #fff8e1 0%, #ffe0b2 100%); color: #5d4037; }
        .ethereal-light { position: absolute; width: 100%; height: 100%; background: radial-gradient(circle, rgba(255,215,0,0.3) 0%, rgba(255,215,0,0) 70%); }
        .temple-main { font-size: 140px; filter: drop-shadow(0 0 15px orange); position: relative; }
        .big-bell { font-size: 90px; cursor: pointer; transition: 0.2s; position: relative; }
        .ring-action { animation: ringBellAnim 0.6s ease-in-out; }
        @keyframes ringBellAnim { from { transform: rotate(-25deg); } to { transform: rotate(25deg); } }
        .telugu-msg { font-size: 26px; color: #800000; padding: 25px; background: rgba(255, 255, 255, 0.7); border-radius: 15px; display: none; margin-top: 30px; font-weight: bold; }
    </style>
</head>
<body onload="initCatchyFX()">

    <div id="page1" class="page active" onclick="nextPage(2)">
        <div class="bg-particles" id="page1Particles"></div>
        <div class="super-big-heart"></div>
        <div class="beat-text">CLICK THE HEART</div>
        <p style="opacity: 0.7; font-size: 14px; margin-top: 15px;">A surprise for Ravi & Sneha!</p>
    </div>

    <div id="page2" class="page">
        <div class="card">
            <h1 style="color: var(--hot-pink); font-weight: 600;">Happy Anniversary! 🥂</h1>
            <p style="font-size: 18px;">Dearest Ravi & Sneha,</p>
            <p>Wishing you another year of love, laughter, and incredible happiness!</p>
            <button class="btn-action" onclick="nextPage(3)">Unwrap Your Gift 🎁</button>
        </div>
    </div>

    <div id="page3" class="page">
        <div class="big-gift" onclick="openGift()">🎁</div>
        <h1 id="gift-h1" style="color: gold; margin-top: 30px;">Open up for Celebration!</h1>
        <button id="next-to-temple" class="btn-action" style="display:none; background: gold; color: #333;" onclick="nextPage(4)">Seek Divine Blessings </button>
    </div>

    <div id="page4" class="page">
        <div class="ethereal-light"></div>
        <div class="temple-main">🛕</div>
        <div class="big-bell" id="mainBell" onclick="ringBell()">🔔</div>
        <p style="font-weight: bold; font-size: 18px;">Ring the sacred bell for the happy couple!</p>
        <div id="teluguMsg" class="telugu-msg">
            మీ ఇద్దరికీ వివాహ వార్షికోత్సవ శుభాకాంక్షలు!<br>
            మరిన్ని సుఖసంతోషాలతో నిండు నూరేళ్లు వర్ధిల్లాలి. 
        </div>
    </div>

    <script>
        function initCatchyFX() {
            // Add particles to Page 1
            const container = document.getElementById('page1Particles');
            for (let i = 0; i < 60; i++) {
                let p = document.createElement('div');
                p.className = 'floating-p';
                p.style.left = Math.random() * 100 + 'vw';
                p.style.animationDelay = Math.random() * 5 + 's';
                p.style.animationDuration = Math.random() * 4 + 4 + 's';
                if (Math.random() > 0.5) p.style.backgroundColor = 'rgba(255,215,0,0.3)'; // Gold ones
                container.appendChild(p);
            }
        }

        function nextPage(num) {
            document.querySelectorAll('.page').forEach(p => p.classList.remove('active'));
            document.getElementById('page' + num).classList.add('active');
        }

        function openGift() {
            document.getElementById('gift-h1').innerText = "Congratulations! ✨";
            document.getElementById('next-to-temple').style.display = "block";
            for (let i = 0; i < 80; i++) {
                let c = document.createElement('div');
                c.style.position = 'absolute';
                c.style.width = '12px'; c.style.height = '12px';
                c.style.left = '50%'; c.style.top = '50%';
                c.style.background = ['var(--hot-pink)','#ffd700','#ffffff','#00e5ff'][Math.floor(Math.random()*4)];
                c.style.borderRadius = (Math.random() > 0.5) ? '50%' : '2px';
                document.getElementById('page3').appendChild(c);
                let x = (Math.random() - 0.5) * 1200;
                let y = (Math.random() - 0.5) * 1200;
                c.animate([
                    { transform: 'translate(0,0)', opacity: 1 },
                    { transform: `translate(${x}px, ${y}px)`, opacity: 0 }
                ], { duration: 2500, easing: 'cubic-bezier(0.1, 1, 0.1, 1)' });
                setTimeout(() => c.remove(), 2500);
            }
        }

        function ringBell() {
            const bell = document.getElementById('mainBell');
            bell.classList.add('ring-action');
            setTimeout(() => bell.classList.remove('ring-action'), 1200);
            document.getElementById('teluguMsg').style.display = "block";
            document.getElementById('teluguMsg').animate([
                { opacity: 0, transform: 'translateY(10px)' },
                { opacity: 1, transform: 'translateY(0)' }
            ], { duration: 1000, fill: 'forwards' });
        }
    </script>
</body>
</html>
