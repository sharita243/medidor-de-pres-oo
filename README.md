[index.html](https://github.com/user-attachments/files/32524394/index.html)[Uploading in<!DOCTYPE html>
<html lang="pt-BR">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Pressão Quest 🩺</title>
    <link rel="stylesheet" href="style.css">
</head>

<body>

<div class="background">
    <span></span><span></span><span></span><span></span>
    <span></span><span></span><span></span><span></span>
</div>

<main class="game">

    <!-- INÍCIO -->
    <section id="inicio" class="tela ativa">

        <div class="logo">🩺</div>

        <h1>Pressão Quest</h1>

        <p class="subtitulo">
            Um simulador educativo em forma de jogo!
        </p>

        <div class="card-info">
            <span>❤️</span>
            <p>
                Preencha seus dados, registre sua pressão,
                escolha seu personagem e complete os desafios.
            </p>
        </div>

        <button class="btn principal" onclick="irPara('dados')">
            COMEÇAR AVENTURA 🚀
        </button>

        <p class="pequeno">
            ⚠️ Simulador educativo. Não substitui avaliação médica.
        </p>

    </section>


    <!-- DADOS -->
    <section id="dados" class="tela">

        <div class="cabecalho">ETAPA 1 DE 6</div>

        <h2>👤 Vamos conhecer você!</h2>

        <div class="form-grid">

            <div>
                <label>Nome</label>
                <input id="nome" type="text" placeholder="Digite seu nome">
            </div>

            <div>
                <label>Idade</label>
                <input id="idade" type="number" min="1" placeholder="Idade">
            </div>

            <div>
                <label>Altura (cm)</label>
                <input id="altura" type="number" min="1" placeholder="Ex.: 165">
            </div>

            <div>
                <label>Sexo</label>
                <select id="sexo">
                    <option value="">Selecione</option>
                    <option value="feminino">Feminino</option>
                    <option value="masculino">Masculino</option>
                    <option value="intersexo">Intersexo</option>
                    <option value="nao">Prefiro não informar</option>
                </select>
            </div>

            <div>
                <label>Identidade de gênero</label>
                <select id="genero">
                    <option value="">Selecione</option>
                    <option>Mulher cis</option>
                    <option>Homem cis</option>
                    <option>Mulher trans</option>
                    <option>Homem trans</option>
                    <option>Não binário</option>
                    <option>Outra</option>
                    <option>Prefiro não informar</option>
                </select>
            </div>

            <div>
                <label>Atividade física regular</label>
                <select id="atividade">
                    <option value="nao">Não</option>
                    <option value="sim">Sim</option>
                </select>
            </div>

            <div>
                <label>Deficiência ou condição</label>
                <input id="condicao" type="text" placeholder="Opcional">
            </div>

            <div>
                <label>Bebidas alcoólicas</label>
                <select id="alcool">
                    <option>Não</option>
                    <option>Sim</option>
                    <option>Prefiro não informar</option>
                </select>
            </div>

            <div>
                <label>Produtos derivados do tabaco</label>
                <select id="tabaco">
                    <option>Não</option>
                    <option>Sim</option>
                    <option>Prefiro não informar</option>
                </select>
            </div>

            <div>
                <label>Histórico familiar com pressão alta/baixa</label>
                <select id="historico">
                    <option>Não</option>
                    <option>Sim</option>
                    <option>Não sei</option>
                </select>
            </div>

        </div>

        <button class="btn principal" onclick="salvarDados()">
            CONTINUAR ➜
        </button>

    </section>


    <!-- PRESSÃO INICIAL -->
    <section id="pressao" class="tela">

        <div class="cabecalho">ETAPA 2 DE 6</div>

        <div class="icone-grande">🩸</div>

        <h2>Pressão antes dos exercícios</h2>

        <p class="subtitulo">
            Digite a pressão medida na sala.
        </p>

        <input
            id="valorPressao"
            class="input-pressao"
            placeholder="120/80"
        >

        <p class="exemplo">Exemplo: 120/80 mmHg</p>

        <button class="btn principal" onclick="analisarPressao()">
            CONTINUAR 🔎
        </button>

    </section>


    <!-- RESULTADO INICIAL -->
    <section id="resultado" class="tela">

        <div class="cabecalho">RESULTADO INICIAL</div>

        <h2>📊 Sua pressão inicial</h2>

        <div id="resultadoConteudo"></div>

        <button class="btn principal" onclick="iniciarDescanso()">
            CONTINUAR ➜
        </button>

    </section>


    <!-- DESCANSO -->
    <section id="descanso" class="tela">

        <div class="icone-grande">🧘</div>

        <h2>Hora de relaxar!</h2>

        <p class="subtitulo">
            Faça um período de descanso antes do desafio.
        </p>

        <div id="timerDescanso" class="timer">
            02:00
        </div>

        <div class="musica-card">

            <span>🎵</span>

            <div>
                <strong>Modo música</strong>
                <p>Uma vibe divertida para acompanhar.</p>
            </div>

            <button
                id="btnMusica"
                class="btn-musica"
                onclick="alternarMusica()">
                🔇
            </button>

        </div>

        <p id="statusMusica" class="pequeno">
            Música desligada
        </p>

    </section>


    <!-- NÍVEL -->
    <section id="nivel" class="tela">

        <div class="icone-grande">🎮</div>

        <h2>Escolha o nível</h2>

        <p class="subtitulo">
            Os exercícios ficam mais desafiadores conforme o nível.
        </p>

        <div class="niveis">

            <button class="nivel facil" onclick="escolherNivel('facil')">
                <span>🟢</span>
                <strong>FÁCIL</strong>
                <small>Desafio leve</small>
            </button>

            <button class="nivel medio" onclick="escolherNivel('medio')">
                <span>🟡</span>
                <strong>MÉDIO</strong>
                <small>Desafio moderado</small>
            </button>

            <button class="nivel dificil" onclick="escolherNivel('dificil')">
                <span>🔴</span>
                <strong>DIFÍCIL</strong>
                <small>Desafio maior</small>
            </button>

        </div>

    </section>


    <!-- AVATAR -->
    <section id="avatar" class="tela">

        <div class="cabecalho">ESCOLHA SEU PERSONAGEM</div>

        <h2>🧑 Escolha seu avatar</h2>

        <p class="subtitulo">
            Seu personagem vai acompanhar você no desafio!
        </p>

        <div id="listaAvatares" class="avatares"></div>

        <button
            class="btn principal"
            onclick="comecarExercicios()">
            COMEÇAR OS EXERCÍCIOS 🏆
        </button>

    </section>


    <!-- EXERCÍCIO -->
    <section id="exercicio" class="tela">

        <div class="jogador">

            <div id="avatarExercicio" class="avatar-jogador">
                🧑
            </div>

            <div>
                <strong id="nomeJogador">Jogador</strong>

                <div class="mini-barra">
                    <div id="energia"></div>
                </div>
            </div>

        </div>

        <p id="numeroExercicio" class="fase">
            EXERCÍCIO 1 DE 3
        </p>

        <div id="iconeExercicio" class="icone-exercicio">
            🏋️
        </div>

        <h2 id="nomeExercicio">Exercício</h2>

        <p id="descricaoExercicio" class="descricao">
            Prepare-se!
        </p>

        <div id="timerExercicio" class="timer">
            00:30
        </div>

        <div class="barra-progresso">
            <div id="progresso"></div>
        </div>

        <p id="mensagemExercicio" class="mensagem">
            Prepare-se! 💪
        </p>

    </section>


    <!-- PRESSÃO FINAL -->
    <section id="pressaoFinal" class="tela">

        <div class="icone-grande">🩸</div>

        <h2>Pressão depois dos exercícios</h2>

        <p class="subtitulo">
            Agora registre a nova medida da pressão.
        </p>

        <input
            id="valorPressaoFinal"
            class="input-pressao"
            placeholder="120/80"
        >

        <p class="exemplo">
            Exemplo: 120/80 mmHg
        </p>

        <button
            class="btn principal"
            onclick="analisarPressaoFinal()">
            VER COMPARAÇÃO 📊
        </button>

    </section>


    <!-- COMPARAÇÃO -->
    <section id="comparacao" class="tela">

        <div class="cabecalho">COMPARAÇÃO</div>

        <h2>📊 Antes x Depois</h2>

        <div id="comparacaoConteudo"></div>

        <button
            class="btn principal"
            onclick="mostrarResultadoFinal()">
            VER RECOMENDAÇÃO ➜
        </button>

    </section>


    <!-- FINAL -->
    <section id="final" class="tela">

        <div class="confetes">
            🎉✨🎊✨🎉
        </div>

        <h1>Parabéns!</h1>

        <p class="subtitulo">
            Você completou o desafio!
        </p>

        <div id="resultadoFinal"></div>

        <div class="aviso-medico">

            <h3>👩‍⚕️ Recomendação</h3>

            <p id="recomendacao"></p>

            <hr>

            <p>
                ⚠️ Este simulador é educativo e não substitui
                avaliação de um profissional de saúde.
            </p>

        </div>

        <button
            class="btn principal"
            onclick="location.reload()">
            🔄 JOGAR NOVAMENTE
        </button>

    </section>

</main>

<script src="script.js"></script>

</body>
</html>dex.html…]()
