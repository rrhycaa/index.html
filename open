<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>A Message for Anthony</title>
    <link href="https://fonts.googleapis.com/css2?family=Space+Grotesk:wght@300;700&family=Outfit:wght@400;900&display=swap" rel="stylesheet">
    <style>
        :root {
            --bg: #08080c;
            --accent: #00f2ff;
            --text: #ffffff;
        }

        body, html {
            margin: 0;
            padding: 0;
            height: 100%;
            display: flex;
            justify-content: center;
            align-items: center;
            background-color: var(--bg);
            font-family: 'Space Grotesk', sans-serif;
            color: var(--text);
            overflow: hidden;
        }

        .bg-glow {
            position: absolute;
            width: 100vw;
            height: 100vh;
            background: radial-gradient(circle at var(--x, 50%) var(--y, 50%), rgba(0, 242, 255, 0.12), transparent 40%);
            z-index: -1;
        }

        .container { text-align: center; padding: 20px; }

        .btn {
            padding: 18px 35px;
            background: transparent;
            color: var(--accent);
            border: 2px solid var(--accent);
            font-family: 'Space Grotesk', sans-serif;
            font-weight: bold;
            text-transform: uppercase;
            letter-spacing: 3px;
            cursor: pointer;
            transition: all 0.3s ease;
            border-radius: 4px;
        }

        .btn:hover {
            background: var(--accent);
            color: var(--bg);
            box-shadow: 0 0 30px var(--accent);
            transform: translateY(-2px);
        }

        /* The Surprise Card */
        #final-card {
            display: none;
            opacity: 0;
            transform: translateY(20px);
            transition: all 1s cubic-bezier(0.19, 1, 0.22, 1);
            padding: 50px 30px;
            border-radius: 20px;
            background: rgba(255, 255, 255, 0.03);
            border: 1px solid rgba(255, 255, 255, 0.1);
            backdrop-filter: blur(15px);
            max-width: 400px;
        }

        h1 { 
            font-family: 'Outfit', sans-serif;
            font-size: 3rem; 
            margin: 0; 
            letter-spacing: -1px;
            line-height: 1;
            background: linear-gradient(to bottom, #fff, #888);
            -webkit-background-clip: text;
            -webkit-text-fill-color: transparent;
        }

        .name {
            color: var(--accent);
            font-weight: 900;
            display: block;
            margin-top: 10px;
            -webkit-text-fill-color: var(--accent); /* Override the gradient for the name */
        }

        .wish {
            margin-top: 25px;
            line-height: 1.8;
            font-size: 1rem;
            color: #ccc;
        }

        .stats {
            margin-top: 30px;
            font-size: 0.7rem;
            letter-spacing: 5px;
            color: var(--accent);
            text-transform: uppercase;
        }

        .hidden { display: none; }
    </style>
</head>
<body onmousemove="updateGlow(event)" ontouchmove="updateGlowTouch(event)">

    <div class="bg-glow" id="glow"></div>

    <div class="container">
        <div id="step1">
            <button class="btn" onclick="nextStep(1)">ACCESS DENIED</button>
        </div>

        <div id="step2" class="hidden">
            <p style="letter-spacing: 2px;">AUTHORIZATION REQUIRED...</p>
            <button class="btn" onclick="nextStep(2)">GRANT ACCESS</button>
        </div>

        <div id="step3" class="hidden">
            <p>Verification Complete. Hello, Anthony.</p>
            <button class="btn" onclick="nextStep(3)">INITIALIZE SURPRISE</button>
        </div>

        <div id="final-card">
            <h1>HAPPY BIRTHDAY, <span class="name">ANTHONY FRANK</span></h1>
            
            <p class="wish">
                Happy 18th! You've officially reached the milestone of adulthood. I wish you nothing but the best as you start this new chapter—may you achieve all your goals, stay focused on your dreams, and keep that same energy that makes you, you. Stay blessed!
            </p>

            <div class="stats">
                LEVEL 18 UNLOCKED // 2026
            </div>
        </div>
    </div>

    <script>
        function updateGlow(e) {
            const glow = document.getElementById('glow');
            glow.style.setProperty('--x', e.clientX + 'px');
            glow.style.setProperty('--y', e.clientY + 'px');
        }

        function updateGlowTouch(e) {
            const glow = document.getElementById('glow');
            glow.style.setProperty('--x', e.touches[0].clientX + 'px');
            glow.style.setProperty('--y', e.touches[0].clientY + 'px');
        }

        function nextStep(step) {
            document.getElementById('step' + step).classList.add('hidden');
            
            if(step < 3) {
                document.getElementById('step' + (step + 1)).classList.remove('hidden');
            } else {
                const card = document.getElementById('final-card');
                card.style.display = 'block';
                setTimeout(() => {
                    card.style.opacity = '1';
                    card.style.transform = 'translateY(0)';
                }, 100);
                createSparks();
            }
        }

        function createSparks() {
            for(let i=0; i<30; i++) {
                const spark = document.createElement('div');
                spark.style.position = 'absolute';
                spark.style.width = '2px';
                spark.style.height = '2px';
                spark.style.backgroundColor = '#00f2ff';
                spark.style.left = '50vw';
                spark.style.top = '50vh';
                document.body.appendChild(spark);

                const destX = (Math.random() - 0.5) * 800;
                const destY = (Math.random() - 0.5) * 800;

                spark.animate([
                    { transform: 'translate(0, 0)', opacity: 1 },
                    { transform: `translate(${destX}px, ${destY}px)`, opacity: 0 }
                ], {
                    duration: 1000 + Math.random() * 1000,
                    easing: 'ease-out'
                }).onfinish = () => spark.remove();
            }
        }
    </script>
</body>
</html>
