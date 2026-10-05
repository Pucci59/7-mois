# 7-mois
<!DOCTYPE html>
<html lang="fr">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Pour ma Sarah 🤍</title>
    <!-- Importation de polices élégantes depuis Google Fonts -->
    <link href="https://fonts.googleapis.com/css2?family=Great+Vibes&family=Plus+Jakarta+Sans:wght@300;400;500;600&display=swap" rel="stylesheet">
    <style>
        :root {
            --bg-gradient: linear-gradient(135deg, #fdfbfb 0%, #ebedee 100%);
            --card-bg: rgba(255, 255, 255, 0.85);
            --text-color: #2d3748;
            --accent-color: #e53e3e;
            --accent-light: #fff5f5;
            --gold-color: #d69e2e;
        }

        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
        }

        body {
            font-family: 'Plus Jakarta Sans', sans-serif;
            background: linear-gradient(135deg, #fce4ec 0%, #f3e5f5 50%, #e8eaf6 100%);
            background-attachment: fixed;
            color: var(--text-color);
            min-height: 100vh;
            display: flex;
            justify-content: center;
            align-items: center;
            padding: 20px;
            overflow-x: hidden;
            position: relative;
        }

        /* Effet de cœurs en arrière-plan (générés dynamiquement en JS) */
        .floating-heart {
            position: absolute;
            color: rgba(229, 62, 62, 0.15);
            animation: floatUp 6s linear infinite;
            z-index: 0;
            user-select: none;
        }

        @keyframes floatUp {
            0% {
                transform: translateY(100vh) scale(0.5);
                opacity: 0;
            }
            50% {
                opacity: 0.8;
            }
            100% {
                transform: translateY(-10vh) scale(1.2);
                opacity: 0;
            }
        }

        .container {
            position: relative;
            z-index: 1;
            width: 100%;
            max-width: 650px;
            background: var(--card-bg);
            backdrop-filter: blur(10px);
            border: 1px solid rgba(255, 255, 255, 0.6);
            border-radius: 24px;
            padding: 40px 30px;
            box-shadow: 0 20px 40px rgba(0, 0, 0, 0.08);
            animation: fadeIn 1.2s ease-out;
        }

        @keyframes fadeIn {
            from {
                opacity: 0;
                transform: translateY(20px);
            }
            to {
                opacity: 1;
                transform: translateY(0);
            }
        }

        .header {
            text-align: center;
            margin-bottom: 30px;
        }

        .header h1 {
            font-family: 'Great Vibes', cursive;
            font-size: 3.5rem;
            color: var(--accent-color);
            margin-bottom: 5px;
        }

        .badge-months {
            display: inline-block;
            background: var(--accent-light);
            color: var(--accent-color);
            font-weight: 600;
            font-size: 0.9rem;
            padding: 6px 16px;
            border-radius: 50px;
            border: 1px solid rgba(229, 62, 62, 0.2);
            box-shadow: 0 2px 5px rgba(229, 62, 62, 0.05);
        }

        .message-content {
            font-size: 1.05rem;
            line-height: 1.8;
            color: #4a5568;
        }

        .message-content p {
            margin-bottom: 20px;
            text-align: justify;
        }

        .highlight-gold {
            color: var(--gold-color);
            font-weight: 600;
        }

        .signature {
            margin-top: 35px;
            text-align: right;
            font-family: 'Great Vibes', cursive;
            font-size: 2.2rem;
            color: var(--accent-color);
        }

        /* Responsive design pour téléphones */
        @media (max-width: 480px) {
            .container {
                padding: 25px 20px;
            }
            .header h1 {
                font-size: 2.8rem;
            }
            .message-content {
                font-size: 1rem;
            }
        }
    </style>
</head>
<body>

    <!-- Conteneur principal de la lettre -->
    <div class="container">
        <div class="header">
            <h1>7 Mois à tes côtés</h1>
            <div class="badge-months">Mon amour 🤍</div>
        </div>

        <div class="message-content">
            <p>Ça fait déjà sept mois qu’on se connaît, mais c’est pas assez. J’espère que Dieu nous permet qu’on reste ensemble pour l’éternité (avec une petite bague sur les doigts hehehe).</p>
            
            <p>Je sais très bien que je suis loin d'être quelqu'un de parfait. Je ne suis ni le gars le plus beau, ni le plus charismatique, et j'ai mes défauts. Mais ce que je te promets, c'est que je ferai tout pour être l'homme qui te donne du bonheur au quotidien.</p>
            
            <p>Quand je regarde tout ce qu'on a traversé, je me rends compte de la chance immense que j'ai. Ton amour, je le reçois à 1000 %. Tu es une femme tellement incroyable et parfaite pour moi. Tu veux toujours avancer avec moi, ça montre à quel point tu m'aimes vraiment, et je ne te remercierai jamais assez pour ça. Sur ma vie wAllah que jamais j’oublierai ça et je te le montrerai chaque jour.</p>
            
            <p>Je veux que tu saches que je ne prends rien de tout ça pour acquis. Je veux vraiment cette vie avec toi. Je veux avancer que avec toi, parce que sans toi, je serai au point mort.</p>
            
            <p>Oublie pas la femme que tu es. Quand je te regarde, je vois une beauté incroyable, de celles qui illuminent tout autour d'elles. Tu es belle, tout simplement, dans ton sourire, dans ton regard, et dans chacune de tes facettes. Il n'y a pas un jour où je ne me trouve pas chanceux d'avoir une copine aussi sublime à mes côtés.</p>
            
            <p>Mais ce qu'il y a d'encore plus fort, c'est que cette beauté extérieure, elle est pareille à l'intérieur. Tu as <span class="highlight-gold">un cœur en or</span>, une gentillesse rare et une lumière qui me touche au plus profond de moi. Tu es belle de partout, et c'est ce qui fait que je suis complètement fou de toi.</p>
        </div>

        <div class="signature">
            Ton homme
        </div>
    </div>

    <!-- Script JavaScript pour animer de petits cœurs en fond -->
    <script>
        function createHeart() {
            const heart = document.createElement('div');
            heart.classList.add('floating-heart');
            heart.innerHTML = '❤️';
            heart.style.left = Math.random() * 100 + 'vw';
            heart.style.animationDuration = (Math.random() * 3 + 4) + 's';
            heart.style.fontSize = (Math.random() * 15 + 10) + 'px';
            document.body.appendChild(heart);

            setTimeout(() => {
                heart.remove();
            }, 7000);
        }

        // Crée un cœur toutes les 400 millisecondes
        setInterval(createHeart, 400);
    </script>
</body>
</html>
