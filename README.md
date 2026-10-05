# 7-mois
<!DOCTYPE html>
<html lang="fr">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Pour ma Sarah 🤍 - 7 Mois</title>
    <!-- Polices Google Fonts élégantes -->
    <link href="https://fonts.googleapis.com/css2?family=Great+Vibes&family=Playfair+Display:ital,wght@0,400;0,600;1,400&family=Plus+Jakarta+Sans:wght@300;400;500;600&display=swap" rel="stylesheet">
    <style>
        :root {
            --bg-deep: #120d13;
            --bg-card: rgba(26, 18, 26, 0.75);
            --border-gold: rgba(214, 158, 44, 0.3);
            --accent-rose: #e53e3e;
            --accent-gold: #d69e2e;
            --text-main: #f7fafc;
            --text-muted: #cbd5e0;
        }

        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
        }

        body {
            font-family: 'Plus Jakarta Sans', sans-serif;
            background: var(--bg-deep);
            color: var(--text-main);
            min-height: 100vh;
            display: flex;
            justify-content: center;
            align-items: center;
            padding: 20px;
            overflow-x: hidden;
            position: relative;
        }

        /* Arrière-plan animé avec des étoiles/cœurs discrets */
        .bg-particles {
            position: fixed;
            top: 0;
            left: 0;
            width: 100%;
            height: 100%;
            pointer-events: none;
            z-index: 0;
        }

        .particle {
            position: absolute;
            background: rgba(214, 158, 44, 0.2);
            border-radius: 50%;
            animation: floatParticle 8s infinite linear;
        }

        @keyframes floatParticle {
            0% { transform: translateY(100vh) scale(0); opacity: 0; }
            50% { opacity: 0.6; }
            100% { transform: translateY(-10vh) scale(1); opacity: 0; }
        }

        .container {
            position: relative;
            z-index: 1;
            width: 100%;
            max-width: 650px;
            background: var(--bg-card);
            backdrop-filter: blur(16px);
            -webkit-backdrop-filter: blur(16px);
            border: 1px solid var(--border-gold);
            border-radius: 28px;
            padding: 40px 30px;
            box-shadow: 0 25px 50px rgba(0, 0, 0, 0.5);
            text-align: center;
            transition: all 0.5s ease;
        }

        /* Étape 1 : Le Mini-Jeu (Attrape les 7 cœurs) */
        #game-section h2 {
            font-family: 'Playfair Display', serif;
            font-size: 2rem;
            margin-bottom: 10px;
            color: #fff;
        }

        #game-section p {
            color: var(--text-muted);
            font-size: 0.95rem;
            margin-bottom: 25px;
            line-height: 1.6;
        }

        .game-area {
            position: relative;
            width: 100%;
            height: 280px;
            background: rgba(0, 0, 0, 0.3);
            border: 1px dashed rgba(214, 158, 44, 0.4);
            border-radius: 16px;
            overflow: hidden;
            margin-bottom: 20px;
            cursor: pointer;
        }

        .target-heart {
            position: absolute;
            font-size: 2.2rem;
            cursor: pointer;
            user-select: none;
            transition: transform 0.1s;
            animation: pulseHeart 1.5s infinite alternate;
        }

        @keyframes pulseHeart {
            0% { transform: scale(1); }
            100% { transform: scale(1.15); }
        }

        .score-board {
            font-size: 1.1rem;
            font-weight: 600;
            color: var(--accent-gold);
            margin-bottom: 15px;
        }

        /* Étape 2 : La Lettre (Cachée au début) */
        #letter-section {
            display: none;
            text-align: left;
            animation: fadeInLetter 1s ease forwards;
        }

        @keyframes fadeInLetter {
            from { opacity: 0; transform: translateY(15px); }
            to { opacity: 1; transform: translateY(0); }
        }

        .letter-header {
            text-align: center;
            margin-bottom: 30px;
        }

        .letter-header h1 {
            font-family: 'Great Vibes', cursive;
            font-size: 3.8rem;
            color: #feb2b2;
            margin-bottom: 5px;
        }

        .badge-months {
            display: inline-block;
            background: rgba(229, 62, 62, 0.15);
            color: #feb2b2;
            font-weight: 600;
            font-size: 0.85rem;
            padding: 5px 14px;
            border-radius: 50px;
            border: 1px solid rgba(229, 62, 62, 0.3);
        }

        .letter-body {
            font-size: 1.02rem;
            line-height: 1.85;
            color: var(--text-muted);
        }

        .letter-body p {
            margin-bottom: 20px;
            text-align: justify;
        }

        .highlight-gold {
            color: var(--accent-gold);
            font-weight: 600;
        }

        .signature {
            margin-top: 35px;
            text-align: right;
            font-family: 'Great Vibes', cursive;
            font-size: 2.5rem;
            color: #feb2b2;
        }

        /* Bouton stylé */
        .btn-custom {
            background: linear-gradient(135deg, #d69e2e 0%, #b7791f 100%);
            color: #fff;
            border: none;
            padding: 12px 28px;
            font-size: 1rem;
            font-weight: 600;
            border-radius: 50px;
            cursor: pointer;
            box-shadow: 0 4px 15px rgba(214, 158, 44, 0.3);
            transition: transform 0.2s, opacity 0.2s;
        }

        .btn-custom:hover {
            transform: translateY(-2px);
            opacity: 0.9;
        }

        @media (max-width: 480px) {
            .container { padding: 25px 20px; }
            .letter-header h1 { font-size: 3rem; }
        }
    </style>
</head>
<body>

    <!-- Particules d'arrière-plan -->
    <div class="bg-particles" id="particles"></div>

    <div class="container">
        <!-- SECTION 1 : MINI-JEU -->
        <div id="game-section">
            <h2>Un petit jeu pour toi 🤍</h2>
            <p>Attrape <strong>7 cœurs magiques</strong> (un pour chaque mois passé ensemble) pour déverrouiller ta surprise...</p>
            <div class="score-board">Cœurs attrapés : <span id="score">0</span> / 7</div>
            <div class="game-area" id="gameArea"></div>
        </div>

        <!-- SECTION 2 : LA LETTRE D'AMOUR -->
        <div id="letter-section">
            <div class="letter-header">
                <h1>7 Mois à tes côtés</h1>
                <div class="badge-months">Mon amour Sarah 🤍</div>
            </div>

            <div class="letter-body">
                <p>Ça fait déjà sept mois qu’on se connaît, mais c’est pas assez. J’espère que Dieu nous permet qu’on reste ensemble pour l’éternité (avec une petite bague sur les doigts hehehe).</p>
                
                <p>Je sais très bien que je suis loin d'être quelqu'un de parfait. Je ne suis ni le gars le plus beau, ni le plus charismatique, et j'ai mes défauts. Mais ce que je te promets, c'est que je ferai tout pour être l'homme qui te donne du bonheur au quotidien.</p>
                
                <p>Quand je regarde tout ce qu'on a traversé, je me rends compte de la chance immense que j'ai. Ton amour, je le reçois à 1000 %. Tu es une femme tellement incroyable et parfaite pour moi. Tu veux toujours avancer avec moi, ça montre à quel point tu m'aimes vraiment, et je ne te remercierai jamais assez pour ça. Sur ma vie wAllah que jamais j’oublierai ça et je te le montrerai.</p>
                
                <p>Je veux que tu saches que je ne prends rien de tout ça pour acquis. Je veux vraiment cette vie avec toi. Je veux avancer que avec toi, parce que sans toi, je serai au point mort.</p>
                
                <p>Oublie pas la femme que tu es. Quand je te regarde, je vois une beauté incroyable, de celles qui illuminent tout autour d'elles. Tu es belle, tout simplement, dans ton sourire, dans ton regard, et dans chacune de tes facettes. Il n'y a pas un jour où je ne me trouve pas chanceux d'avoir une copine aussi sublime à mes côtés.</p>
                
                <p>Mais ce qu'il y a d'encore plus fort, c'est que cette beauté extérieure, elle est pareille à l'intérieur. Tu as <span class="highlight-gold">un cœur en or</span>, une gentillesse rare et une lumière qui me touche au plus profond de moi. Tu es belle de partout, et c'est ce qui fait que je suis complètement fou de toi.</p>
            </div>

            <div class="signature">
                Ton homme 🤍
            </div>
        </div>
    </div>

    <script>
        // Génération des particules d'arrière-plan
        const particlesContainer = document.getElementById('particles');
        for (let i = 0; i < 25; i++) {
            const p = document.createElement('div');
            p.classList.add('particle');
            p.style.left = Math.random() * 100 + 'vw';
            p.style.top = Math.random() * 100 + 'vh';
            p.style.width = (Math.random() * 4 + 2) + 'px';
            p.style.height = p.style.width;
            p.style.animationDuration = (Math.random() * 6 + 4) + 's';
            p.style.animationDelay = (Math.random() * 5) + 's';
            particlesContainer.appendChild(p);
        }

        // Logique du mini-jeu
        let score = 0;
        const targetScore = 7;
        const gameArea = document.getElementById('gameArea');
        const scoreDisplay = document.getElementById('score');
        const gameSection = document.getElementById('game-section');
        const letterSection = document.getElementById('letter-section');

        function spawnHeart() {
            if (score >= targetScore) return;

            const heart = document.createElement('div');
            heart.classList.add('target-heart');
            heart.innerHTML = '❤️';

            // Position aléatoire dans la zone de jeu
            const maxX = gameArea.clientWidth - 50;
            const maxY = gameArea.clientHeight - 50;
            const randomX = Math.max(10, Math.floor(Math.random() * maxX));
            const randomY = Math.max(10, Math.floor(Math.random() * maxY));

            heart.style.left = randomX + 'px';
            heart.style.top = randomY + 'px';

            heart.addEventListener('click', (e) => {
                e.stopPropagation();
                score++;
                scoreDisplay.textContent = score;
                heart.remove();

                if (score >= targetScore) {
                    // Transition vers la lettre
                    setTimeout(() => {
                        gameSection.style.display = 'none';
                        letterSection.style.display = 'block';
                    }, 400);
                } else {
                    spawnHeart();
                }
            });

            // Supprime le cœur s'il n'est pas cliqué après 1.8 secondes pour en faire apparaître un autre
            setTimeout(() => {
                if (heart.parentElement) {
                    heart.remove();
                    if (score < targetScore) spawnHeart();
                }
            }, 1800);

            gameArea.appendChild(heart);
        }

        // Lancement du premier cœur
        spawnHeart();
    </script>
</body>
</html>
