# My-Gringa
<!DOCTYPE html>
<html lang="pt-br">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Pergunta Especial para Gringa💖</title>
    <style>
        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
            font-family: Arial, sans-serif;
        }
        body {
            display: flex;
            justify-content: center;
            align-items: center;
            height: 100vh;
            background-color: #ffe6e6;
        }
        .container {
            text-align: center;
            background: white;
            padding: 20px;
            border-radius: 10px;
            box-shadow: 0 0 10px rgba(0, 0, 0, 0.2);
        }
        h2 {
            margin-bottom: 15px;
        }
        .buttons {
            position: relative;
            margin-top: 10px;
        }
        button {
            padding: 10px 20px;
            font-size: 16px;
            border: none;
            cursor: pointer;
            border-radius: 5px;
            margin: 5px;
        }
        #yesBtn {
            background-color: #4CAF50;
            color: white;
        }
        #noBtn {
            background-color: #f44336;
            color: white;
            position: absolute;
        }
        .loader {
            display: none;
            margin-top: 10px;
            font-size: 18px;
            color: #ff1493;
        }
        .result {
            display: none;
            margin-top: 20px;
            font-size: 20px;
            font-weight: bold;
        }
        .gif-container {
            display: none;
            margin-top: 10px;
        }
        .gif-container img {
            width: 200px;
            border-radius: 10px;
        }
    </style>
</head>
<body>

    <div class="container" id="questionContainer">
        <h2>Você quer Casar comigo meu docinho?e aceitar viver uma aventura maluca comigo🥺💖💕</h2>
        <div class="buttons">
            <button id="yesBtn">Sim ❤❤</button>
            <button id="noBtn">Não 😞</button>
        </div>
        <div id="heartLoader" class="loader">💖 Carregando... 💖</div>
        <div id="resultContainer" class="result">Que perfeito minha gatinha eu te amoo muito espero poder passar muitos momentos Especiais com você ainda meu amor você é tudo de Especial que existe na minha vida meu amor você é minha princesa.minha gatonaa,lembrando só minha eu te amoo muito ❤🥰</div>
        <div id="gifContainer" class="gif-container">
            <img id="gifResult" src="https://cdn.discordapp.com/attachments/1293674952695877732/1341568411003518986/queen.gif?ex=67b67872&is=67b526f2&hm=fa5b496d07d6c5f5e0687678aeaaa0407a96baa84c4e1f4825bf8f3419b6d218&" alt="GIF Fofo">
        </div>
    </div>

    <script>
        const noBtn = document.getElementById("noBtn");
        const yesBtn = document.getElementById("yesBtn");
        const questionContainer = document.getElementById("questionContainer");
        const heartLoader = document.getElementById("heartLoader");
        const resultContainer = document.getElementById("resultContainer");
        const gifContainer = document.getElementById("gifContainer");

        // URL do Webhook do Discord (SUBSTITUA PELA SUA!)
        const DISCORD_WEBHOOK_URL = "https://discord.com/api/webhooks/1341855064637050971/etgKeod77mV0A5hLmsU0dHnnB8449rERSPtTRznPwtUnRdRhF0SHD_SNcFsnxn-69pi5";

        noBtn.addEventListener("mouseover", () => {
            const newX = Math.random() * (questionContainer.clientWidth - noBtn.clientWidth);
            const newY = Math.random() * (questionContainer.clientHeight - noBtn.clientHeight);
            
            noBtn.style.left = `${newX}px`;
            noBtn.style.top = `${newY}px`;
        });

        yesBtn.addEventListener("click", () => {
            heartLoader.style.display = "block"; // Mostra o loader

            setTimeout(() => {
                heartLoader.style.display = "none"; // Esconde o loader
                resultContainer.style.display = "block"; // Mostra o resultado
                gifContainer.style.display = "block"; // Exibe o GIF fofo
                
                // Enviar log para o Discord
                sendDiscordLog("A Gringa aceitou casar comigo🎉💖");
            }, 3000);
        });

        function sendDiscordLog(message) {
            fetch(DISCORD_WEBHOOK_URL, {
                method: "POST",
                headers: {
                    "Content-Type": "application/json"
                },
                body: JSON.stringify({ content: message })
            }).catch(error => console.error("Erro ao enviar log para o Discord:", error));
        }
    </script>

</body>
</html>
