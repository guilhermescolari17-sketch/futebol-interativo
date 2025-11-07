<html lang="pt-br">
<head>
    <meta charset="UTF-8">
    <title>Futebol Interativo</title>
    <style>
        body {
            font-family: Arial, sans-serif;
            text-align: center;
            margin-top: 50px;
            background-color: #f4f4f4;
        }
        h1 {
            color: #333;
        }
        button {
            padding: 12px 25px;
            font-size: 16px;
            margin: 10px;
            border: none;
            border-radius: 6px;
            cursor: pointer;
            background-color: #007BFF;
            color: white;
        }
        button:hover {
            background-color: #0056b3;
        }
        .content {
            margin-top: 30px;
        }
        .news, .games {
            margin-top: 20px;
            padding: 15px;
            background-color: white;
            border-radius: 8px;
            display: inline-block;
            text-align: left;
            min-width: 300px;
        }
        ul {
            padding-left: 20px;
        }
    </style>
</head>
<body>
    <h1>Futebol Interativo</h1>
    <p>Escolha seu time para ver próximos jogos e notícias:</p>

    <button onclick="chooseTeam('Grêmio')">Grêmio</button>
    <button onclick="chooseTeam('Internacional')">Internacional</button>
    <button onclick="chooseTeam('Outro')">Outro time</button>

    <div class="content" id="teamContent" style="display:none;">
        <h2 id="teamName"></h2>
        <div class="games">
            <h3>Próximos Jogos</h3>
            <ul id="gamesList"></ul>
        </div>
        <div class="news">
            <h3>Últimas Notícias</h3>
            <ul id="newsList"></ul>
        </div>
    </div>

    <script>
        const data = {
            "Grêmio": {
                games: [
                    "Grêmio vs Internacional - 10/11/2025",
                    "Grêmio vs Flamengo - 15/11/2025",
                    "Grêmio vs Palmeiras - 20/11/2025"
                ],
                news: [
                    "Grêmio anuncia novo reforço para o ataque",
                    "Jogador do Grêmio se destaca em treino",
                    "Técnico do Grêmio fala sobre próximos desafios"
                ]
            },
            "Internacional": {
                games: [
                    "Internacional vs Grêmio - 10/11/2025",
                    "Internacional vs Santos - 17/11/2025",
                    "Internacional vs Atlético-MG - 22/11/2025"
                ],
                news: [
                    "Internacional renova contrato com goleiro",
                    "Inter enfrenta rival em clássico decisivo",
                    "Jogador do Inter faz gol histórico"
                ]
            },
            "Outro": {
                games: [
                    "Time X vs Time Y - 12/11/2025",
                    "Time X vs Time Z - 18/11/2025"
                ],
                news: [
                    "Time X se prepara para o campeonato",
                    "Treinador fala sobre tática do time"
                ]
            }
        };

        function chooseTeam(team) {
            document.getElementById("teamContent").style.display = "block";
            document.getElementById("teamName").innerText = team

            const gamesList = document.getElementById("gamesList");
            gamesList.innerHTML = "";
            data[team].games.forEach(game => {
                const li = document.createElement("li");
                li.textContent = game;
                gamesList.appendChild(li);
            });

            const newsList = document.getElementById("newsList");
            newsList.innerHTML = "";
            data[team].news.forEach(news => {
                const li = document.createElement("li");
                li.textContent = news;
                newsList.appendChild(li);
            });
        }
    </script>
</body>
</html>
