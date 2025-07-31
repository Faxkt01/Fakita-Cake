<!DOCTYPE html>
<html lang="pt-BR">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Fakita Vale</title>
    <link href="https://fonts.googleapis.com/css2?family=Poppins:wght@600&family=Roboto:wght@400&display=swap" rel="stylesheet">
    <style>
        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
        }

        body {
            background: #ff69b4; /* Rosa inicial */
            animation: colorShift 12s ease infinite; /* Alterna tons de rosa e azul */
            overflow: hidden;
            display: flex;
            justify-content: center;
            align-items: center;
            height: 100vh;
            font-family: 'Roboto', sans-serif;
            position: relative;
        }

        /* Morango grande de fundo */
        body::before {
            content: '';
            position: absolute;
            bottom: -50px;
            right: -50px;
            width: 300px;
            height: 300px;
            background-image: url('https://img.icons8.com/emoji/100/000000/strawberry-emoji.png');
            background-size: cover;
            opacity: 0.25; /* Semi-transparente */
            z-index: 1;
            filter: drop-shadow(5px 5px 10px rgba(0, 0, 0, 0.3)); /* Sombra suave */
        }

        .container {
            background: rgba(255, 255, 255, 0.97); /* Fundo branco translúcido */
            padding: 2.5rem 3.5rem;
            border-radius: 20px;
            box-shadow: 0 10px 25px rgba(0, 0, 0, 0.15);
            text-align: center;
            z-index: 10;
            max-width: 90%;
            position: relative;
        }

        h1 {
            font-family: 'Poppins', sans-serif;
            color: #c71585; /* Rosa escura */
            font-size: 2.3rem;
            margin-bottom: 0.5rem;
            text-shadow: 1px 1px 3px rgba(0, 0, 0, 0.1);
        }

        h2 {
            font-family: 'Roboto', sans-serif;
            color: #4a4a4a; /* Cinza escuro */
            font-size: 1.3rem;
            margin-bottom: 0.8rem;
            font-weight: 400;
        }

        h3 {
            font-family: 'Roboto', sans-serif;
            color: #c71585; /* Rosa escura */
            font-size: 1.1rem;
            margin-top: 0.5rem;
            margin-bottom: 1.5rem;
            font-weight: 400;
            z-index: 10;
        }

        .instagram-btn {
            display: inline-block;
            padding: 12px 30px;
            background: linear-gradient(45deg, #f09433, #e6683c, #dc2743, #cc2366, #bc1888); /* Gradiente Instagram */
            color: #fff;
            font-family: 'Roboto', sans-serif;
            font-size: 1.1rem;
            font-weight: bold;
            text-decoration: none;
            border-radius: 30px;
            box-shadow: 0 5px 12px rgba(0, 0, 0, 0.2);
            transition: transform 0.3s, box-shadow 0.3s;
        }

        .instagram-btn:hover {
            transform: translateY(-3px);
            box-shadow: 0 8px 18px rgba(0, 0, 0, 0.3);
        }

        .strawberry {
            position: absolute;
            width: 30px;
            height: 30px;
            background-image: url('https://img.icons8.com/emoji/48/000000/strawberry-emoji.png');
            background-size: cover;
            animation: fall linear infinite;
            pointer-events: none;
            z-index: 3;
            filter: drop-shadow(2px 2px 5px rgba(0, 0, 0, 0.2));
        }

        @keyframes fall {
            0% {
                transform: translateY(-100vh) rotate(0deg) scale(0.8);
                opacity: 0.9;
            }
            100% {
                transform: translateY(100vh) rotate(360deg) scale(1.2);
                opacity: 0.2;
            }
        }

        @keyframes colorShift {
            0% { background: #ff69b4; } /* Rosa quente */
            25% { background: #ff1493; } /* Rosa vibrante */
            50% { background: #1e90ff; } /* Azul dodger */
            75% { background: #4169e1; } /* Azul royal */
            100% { background: #ff69b4; } /* Volta ao rosa inicial */
        }

        /* Responsividade */
        @media (max-width: 600px) {
            .container {
                padding: 1.5rem 2rem;
            }
            h1 {
                font-size: 1.9rem;
            }
            h2 {
                font-size: 1.1rem;
            }
            h3 {
                font-size: 0.9rem;
            }
            .instagram-btn {
                padding: 10px 25px;
                font-size: 1rem;
            }
            .strawberry {
                width: 25px;
                height: 25px;
            }
            body::before {
                width: 200px;
                height: 200px;
                bottom: -30px;
                right: -30px;
            }
        }
    </style>
</head>
<body>
    <div class="container">
        <h1>Fakita Vale</h1>
        <h2>Reta Final</h2>
        <h3>Morango do Amor</h3>
        <a href="https://www.instagram.com/fakita_cake?igsh=bDEwcmtpdzVkbWI3&utm_source=qr" class="instagram-btn" target="_blank">Instagram</a>
    </div>
    <div id="strawberries-container"></div>
    <script>
        const container = document.getElementById('strawberries-container');

        function createStrawberry() {
            const strawberry = document.createElement('div');
            strawberry.classList.add('strawberry');
            
            // Posição horizontal aleatória
            strawberry.style.left = Math.random() * 100 + 'vw';
            
            // Duração da animação aleatória entre 8 e 14 segundos
            strawberry.style.animationDuration = Math.random() * 6 + 8 + 's';
            
            // Tamanho aleatório para variedade
            const scale = Math.random() * 0.5 + 0.7; // Entre 0.7 e 1.2
            strawberry.style.width = `${30 * scale}px`;
            strawberry.style.height = `${30 * scale}px`;
            
            container.appendChild(strawberry);
            
            // Remove o morango após a animação
            setTimeout(() => {
                strawberry.remove();
            }, parseFloat(strawberry.style.animationDuration) * 1000);
        }

        // Cria novos morangos a cada 1200ms
        setInterval(createStrawberry, 1200);
    </script>
</body>
</html>
