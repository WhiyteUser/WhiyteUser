<!DOCTYPE html>
<html lang="pt-BR">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Aventura na Floresta Mágica</title>
    <style>
        body { font-family: Arial, sans-serif; background-color: #f0f8ff; color: #333; text-align: center; }
        img { max-width: 400px; height: auto; }
        .choice { margin: 20px; }
        button { padding: 10px 20px; }
    </style>
</head>
<body>
    <h1>A Aventura na Floresta Mágica</h1>
    <img id="imagem" src="" alt="Imagem da Aventura">
    <p id="texto"></p>
    <div id="opcoes" class="choice"></div>

    <script>
        const cenas = [
            {
                texto: "Você se encontra na entrada da Floresta Mágica. À sua esquerda, há uma trilha coberta de flores. À direita, uma trilha sombria.",
                img: "https://via.placeholder.com/400x200?text=Entrada+da+Floresta",
                opcoes: [
                    { texto: "Seguir a trilha das flores", cena: 1 },
                    { texto: "Entrar na trilha sombria", cena: 2 }
                ]
            },
            {
                texto: "Você segue a trilha das flores e encontra uma fada que lhe oferece ajuda. Ela pode guiá-lo ou lhe dar uma poção mágica.",
                img: "https://via.placeholder.com/400x200?text=Fada",
                opcoes: [
                    { texto: "Pedir ajuda para a fada", cena: 3 },
                    { texto: "Aceitar a poção mágica", cena: 4 }
                ]
            },
            {
                texto: "A trilha sombria leva você a uma caverna cheia de mistérios. Um dragão está dormindo dentro.",
                img: "https://via.placeholder.com/400x200?text=Caverna+Sombria",
                opcoes: [
                    { texto: "Tentar acordar o dragão", cena: 5 },
                    { texto: "Voltar e escolher a trilha das flores", cena: 0 }
                ]
            },
            {
                texto: "A fada o guia com segurança para fora da floresta. Você chegou em casa! Fim da aventura.",
                img: "https://via.placeholder.com/400x200?text=Felicidade",
                opcoes: []
            },
            {
                texto: "A poção mágica faz você encolher! Você agora é do tamanho de uma formiga e precisa encontrar uma saída.",
                img: "https://via.placeholder.com/400x200?text=Poção+Mágica",
                opcoes: [
                    { texto: "Explorar a floresta do tamanho de uma formiga", cena: 6 },
                    { texto: "Tentar reverter a poção", cena: 7 }
                ]
            },
            {
                texto: "Você acorda o dragão, que fica furioso. Mas, ao invés de te devorar, ele te oferece um passeio. Você aceita?",
                img: "https://via.placeholder.com/400x200?text=Dragão",
                opcoes: [
                    { texto: "Sim, vou passear!", cena: 8 },
                    { texto: "Não, prefiro fugir!", cena: 9 }
                ]
            },
            {
                texto: "Você explora a floresta e encontra um grupo de formigas que se tornam suas amigas. Você decide viver entre elas. Fim da aventura.",
                img: "https://via.placeholder.com/400x200?text=Amizade",
                opcoes: []
            },
            {
                texto: "Você não consegue reverter a poção e se perde ainda mais na floresta. Fim da aventura.",
                img: "https://via.placeholder.com/400x200?text=Perdido",
                opcoes: []
            },
            {
                texto: "O dragão o leva para um lugar mágico, onde você descobre novos amigos e vive grandes aventuras. Fim da aventura.",
                img: "https://via.placeholder.com/400x200?text=Aventura+Mágica",
                opcoes: []
            },
            {
                texto: "Você foge do dragão e acaba se perdendo na floresta. Fim da aventura.",
                img: "https://via.placeholder.com/400x200?text=Fuga",
                opcoes: []
            }
        ];

        let cenaAtual = 0;

        function mostrarCena() {
            const cena = cenas[cenaAtual];
            document.getElementById('imagem').src = cena.img;
            document.getElementById('texto').innerText = cena.texto;

            const opcoesDiv = document.getElementById('opcoes');
            opcoesDiv.innerHTML = '';

            cena.opcoes.forEach(opcao => {
                const botao = document.createElement('button');
                botao.innerText = opcao.texto;
                botao.onclick = () => {
                    cenaAtual = opcao.cena;
                    mostrarCena();
                };
                opcoesDiv.appendChild(botao);
            });
        }

        mostrarCena();
    </script>
</body>
</html>
