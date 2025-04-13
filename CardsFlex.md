Exercício de Front Page HTML e CSS matéria Padrões e Sítios 2 segundo semestre FATEC

Explicação dos códigos HTML CSS

HTML

Vamos analisar esse código HTML linha por linha, explicando cada parte de forma clara:
________________________________________
🔹 Estrutura básica do HTML
<!DOCTYPE html>
▶️ Diz ao navegador que este é um documento HTML5.
<html lang="pt-br">
▶️ Início do documento HTML. O atributo lang="pt-br" indica que o conteúdo está em português do Brasil.
________________________________________
🔹 Cabeçalho (head)
<head>
    <meta charset="UTF-8">
▶️ Define o conjunto de caracteres como UTF-8, suportando acentuação e caracteres especiais.
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
▶️ Garante que a página seja responsiva, ou seja, se ajuste corretamente em dispositivos móveis.
    <title>Cards de Pessoas</title>
▶️ Define o título que aparece na aba do navegador.
    <link rel="stylesheet" href="styles.css"> <!-- Link para o CSS -->
▶️ Conecta o HTML ao arquivo de estilo CSS externo chamado styles.css.
________________________________________
🔹 Corpo da página (body)
<body>
    <div class="container">
▶️ Começa a div principal que envolve todos os cartões (cards). A classe container será usada no CSS para layout e posicionamento.
________________________________________
🔹 Cards individuais (repetidos 6 vezes)
        <div class="card">
▶️ Início de um card individual.
            <img src="./IMG/02 foto rosto.jpg" alt="Rosto 1" class="face-image">
▶️ Adiciona a imagem da pessoa, com a classe face-image para aplicar estilo via CSS.
            <div class="name">Kimberly</div>
▶️ Exibe o nome da pessoa.
            <div class="email">Kimberly@example.com</div>
▶️ Exibe o email da pessoa.
            <div class="card-actions">
▶️ Início da seção onde ficam os ícones de ação (editar e excluir).
                <a href="outra-pagina.html">
                    <img src="IMG/edit.png" alt="Link" class="action-icon">
                </a>
▶️ Um link com um ícone (imagem edit.png) que leva o usuário para outra página. Isso seria, por exemplo, para editar o cadastro da pessoa.
                <a href="#">
                    <img src="IMG/delete.png" alt="Excluir" class="action-icon">
                </a>
▶️ Um link sem destino ainda definido (#), que exibe uma imagem de lixeira para excluir o card.
            </div> <!-- Fim das ações -->
        </div> <!-- Fim do card -->
________________________________________
Esse bloco é repetido 6 vezes, um para cada pessoa (João, Carlos, Lucas, Eduarda e Angela).
________________________________________
🔹 Fechamento do HTML
    </div> <!-- Fecha o container -->
</body>
</html>
▶️ Fecha o container principal, o corpo da página e o documento HTML.
________________________________________
✅ Em resumo:
•	O código mostra 6 cards de pessoas, com imagem, nome, e-mail e dois ícones (editar e excluir).
•	O estilo visual é definido em um arquivo externo (styles.css).
•	O HTML está limpo e bem estruturado para layout em grade com flexbox (provavelmente definido no CSS).


CSS

Vamos destrinchar esse código CSS linha por linha de forma clara e didática — como se fosse um manual para que você entenda cada comando e o que ele faz visualmente.
________________________________________
🔷 body
body {
    display: flex;
    justify-content: center;
    align-items: center;
    height: 100vh;
    margin: 0;
    background-color: #f0f0f0;
}
•	display: flex; → Ativa o Flexbox no corpo da página.
•	justify-content: center; → Centraliza horizontalmente o conteúdo (o .container).
•	align-items: center; → Centraliza verticalmente.
•	height: 100vh; → Define a altura como 100% da altura da tela.
•	margin: 0; → Remove a margem padrão do navegador.
•	background-color: #f0f0f0; → Define um cinza claro como fundo da página.
________________________________________
🔷 .container
.container {
    display: flex;
    flex-wrap: wrap;
    justify-content: center;
    width: 80%;
}
•	display: flex; → Ativa o Flexbox para os cards.
•	flex-wrap: wrap; → Permite que os cards quebrem para a próxima linha.
•	justify-content: center; → Centraliza os cards na horizontal.
•	width: 80%; → Define que o container usa 80% da largura da tela.
________________________________________
🔷 .card
.card {
    background-image: url('./IMG/mountains-6865752_1280.jpg');
    background-size: cover;
    background-position: center;
    background-repeat: no-repeat;
Essas linhas definem a imagem de fundo:
•	background-image → Caminho da imagem de fundo.
•	background-size: cover; → A imagem cobre todo o card.
•	background-position: center; → Centraliza a imagem.
•	background-repeat: no-repeat; → Evita repetição da imagem.
    background-color: white;
    border-radius: 8px;
    box-shadow: 0 2px 10px rgba(0, 0, 0, 0.1);
    margin: 10px;
    overflow: hidden;
    width: 250px;
    height: 300px;
    display: flex;
    flex-direction: column;
    align-items: center;
    position: relative;
}
•	background-color: white; → Define fundo branco para o conteúdo do card.
•	border-radius: 8px; → Bordas levemente arredondadas.
•	box-shadow: ... → Sombra sutil.
•	margin: 10px; → Espaço externo ao redor do card.
•	overflow: hidden; → Esconde conteúdo que ultrapassar o card.
•	width / height → Tamanho fixo.
•	display: flex; flex-direction: column; align-items: center; → Organiza o conteúdo verticalmente, centralizado.
•	position: relative; → Necessário para que elementos absolutos (como a tarja) funcionem corretamente.
________________________________________
🔷 .card img
.card img {
    width: 100%;
    height: auto;
}
•	Define que qualquer imagem dentro do card ocupa 100% da largura, mantendo proporção.
________________________________________
🔷 .card::after
.card::after {
    content: "";
    position: absolute;
    bottom: 0;
    left: 0;
    width: 100%;
    height: 50%;
    background-color: white;
    z-index: 0;
}
•	Cria uma tarja branca na metade inferior do card.
•	position: absolute; → Coloca a tarja no rodapé.
•	z-index: 0; → Fica atrás de outros elementos, como a imagem do rosto.
________________________________________
🔷 .face-image
.face-image {
    width: 100px !important;
    height: 100px !important;
    border-radius: 50%;
    object-fit: cover;
    position: absolute;
    top: 40%;
    left: 50%;
    transform: translate(-50%, -50%);
    border: 3px solid white;
    z-index: 1;
}
•	Define o formato redondo da imagem da pessoa.
•	object-fit: cover; → Garante que a imagem se encaixe corretamente no círculo.
•	position: absolute; + transform → Centraliza a imagem no card.
•	z-index: 1; → Fica acima da tarja branca.
________________________________________
🔷 .name e .email
.name {
    font-size: 1.2em;
    font-weight: bold;
    margin-top: 200px;
    position: relative;
    z-index: 2;
}
.email {
    font-size: 0.9em;
    color: #555;
    margin-bottom: 10px;
    position: relative;
    z-index: 2;
}
•	Define estilos básicos de texto.
•	margin-top: 200px; empurra o nome para baixo, para não sobrepor a imagem do rosto.
•	z-index: 2; → Fica acima da tarja e da imagem de fundo.
________________________________________
🔷 .actions (não está sendo usado, mas está aqui no CSS)
.actions {
    display: flex;
    justify-content: space-between;
    align-items: center;
    width: 100%;
    padding: 5px 15px;
}
•	Um bloco antigo ou alternativo para ações — talvez não esteja mais em uso no HTML atual.
________________________________________
🔷 .card-actions
.card-actions {
    position: absolute;
    bottom: 10px;
    width: 100%;
    padding-left: 30px;
    padding-right: 30px;
    display: flex;
    justify-content: space-between;
    align-items: center;
    z-index: 1;
}
•	Coloca os ícones de ação (lixeira e link) na base do card.
•	padding-left/right: 30px; → Garante espaço dos lados, como você pediu.
•	justify-content: space-between; → Um ícone à esquerda, outro à direita.
•	z-index: 1; → Aparece acima da tarja branca.
________________________________________
🔷 .action-icon
.action-icon {
    width: 24px;
    height: 24px;
    cursor: pointer;
    margin: 50 5px;
}
•	Tamanho dos ícones.
•	cursor: pointer; → Mostra a mãozinha ao passar o mouse.
•	⚠️ margin: 50 5px; está incorreto → CSS correto seria margin: 0 5px; ou margin: 5px 50px;
________________________________________
🔷 .delete e .redirect
.delete {
    color: red;
    text-decoration: none;
    z-index: 2;
}
.redirect {
    color: blue;
    text-decoration: none;
    z-index: 2;
}
•	Essas classes seriam para links (ainda não usadas nos ícones do HTML atual).
•	Definem cores e removem sublinhado.
________________________________________
🔷 Responsividade
@media (min-width: 768px) {
    .card {
        width: calc(33.33% - 20px);
    }
}
•	Quando a tela for maior que 768px, os cards ficam em 3 colunas por linha.
•	calc(33.33% - 20px) → Equilibra o espaço entre eles.
________________________________________
