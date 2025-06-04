# Futebol de Combate 2D

Bem-vindo ao Futebol de Combate 2D! Este é um simples jogo de luta para dois jogadores, criado inteiramente com HTML, CSS e JavaScript puro. Os personagens são estilizados como jogadores de futebol e enfrentam-se numa arena básica.

## Visão Geral

O jogo apresenta dois personagens jogáveis com controlos distintos:

* **Artilheiro Veloz:** Um lutador ágil com uniforme verde e detalhes amarelos.
* **Zagueiro Muralha:** Um lutador mais robusto com uniforme azul escuro e detalhes cinzas.

O objetivo é simples: seja o primeiro a reduzir a barra de vida do oponente a zero, utilizando uma combinação de socos e chutes!

## Como Executar o Jogo

1.  **Requisitos:** Apenas um navegador web moderno (como Google Chrome, Mozilla Firefox, Microsoft Edge, etc.).
2.  **Obter o Código:**
    * Guarde o código principal do jogo (que inclui HTML, CSS e JavaScript) num único ficheiro chamado `index.html` (ou qualquer outro nome com a extensão `.html`) na pasta do seu projeto.
3.  **Executar:**
    * Abra o ficheiro `index.html` diretamente no seu navegador web. Pode fazer isto clicando duas vezes no ficheiro ou arrastando-o para a janela do navegador.
    * Se estiver a usar o VS Code com a extensão "Live Server", pode clicar com o botão direito no ficheiro `index.html` e selecionar "Open with Live Server".

O jogo foi desenhado para ser autónomo e não requer instalações ou dependências complexas. O Tailwind CSS é utilizado para alguns estilos e é carregado através de uma CDN, pelo que uma ligação à Internet é necessária para a correta aplicação desses estilos na primeira vez que o jogo é carregado.

## Controles

**Jogador 1 (Artilheiro Veloz - Verde):**

* **Movimento Esquerda:** Tecla `A`
* **Movimento Direita:** Tecla `D`
* **Pulo:** Tecla `W`
* **Agachar:** Tecla `S` (manter pressionado)
* **Chute:** Tecla `E`
* **Soco:** Tecla `Q`

**Jogador 2 (Zagueiro Muralha - Azul):**

* **Movimento Esquerda:** Seta Esquerda (←)
* **Movimento Direita:** Seta Direita (→)
* **Pulo:** Seta Cima (↑)
* **Agachar:** Seta Baixo (↓) (manter pressionado)
* **Chute:** Tecla `Numpad 1` (do teclado numérico)
* **Soco:** Tecla `Numpad 0` (do teclado numérico)

## Estrutura do Código

O jogo está contido num único ficheiro HTML (`index.html`) e é estruturado da seguinte forma:

* **HTML (`<head>` e `<body>`):**
    * Define a estrutura básica da página, incluindo o título, a ligação para o Tailwind CSS (via CDN), e os elementos do jogo como o elemento `<canvas>`, as barras de vida (`health-bars`), informações de controlos (`controls-info`), e a caixa de mensagens de estado (`messageBox`).
* **CSS (dentro de `<style>`):**
    * Contém os estilos personalizados para o corpo da página, o canvas do jogo, as barras de vida, a secção de controlos e a caixa de mensagens, assegurando uma apresentação visual coesa e temática.
* **JavaScript (dentro de `<script>`):**
    * **Configuração Inicial:** Seleciona elementos do DOM (canvas, barras de vida, etc.) e define constantes globais como `GRAVITY` e `FLOOR_Y`.
    * **Classe `Player`:** Representa a lógica e as propriedades de cada jogador.
        * `constructor`: Inicializa posição, dimensões, cor, vida, controlos, função de desenho específica e o elemento da barra de vida.
        * Métodos para `draw()`, `update(opponent)` (incluindo física básica, movimento, limites do ecrã, gestão de ataques), `jump()`, `crouch()`, `attack(type)`, `checkAttackCollision(opponent)`, `takeDamage(amount)`, e `flash()` (efeito visual ao ser atingido).
    * **Funções de Desenho Específicas (`drawArtilheiro`, `drawZagueiro`):**
        * Responsáveis por renderizar cada personagem no canvas utilizando formas geométricas 2D, conferindo a cada um uma silhueta e detalhes visuais distintos que remetem a jogadores de futebol.
    * **Instanciação dos Jogadores:** Cria os objetos `player1` e `player2` com as suas respetivas configurações.
    * **Gestão de Entradas do Utilizador:**
        * Objeto `keys` para rastrear o estado das teclas.
        * Event listeners para `keydown` e `keyup`.
        * Função `handleInput()` para processar as teclas pressionadas e executar as ações correspondentes dos jogadores.
    * **Funções Auxiliares:**
        * `drawFloor()`: Desenha o chão/cenário.
        * `showMessage()`, `hideMessage()`: Gerem a caixa de mensagens.
    * **Lógica de Jogo:**
        * `checkGameOver()`: Verifica as condições de fim de jogo.
        * `resetGame()`: Restaura o estado do jogo para uma nova partida.
        * `gameLoop()`: O ciclo principal do jogo, responsável por limpar o ecrã, processar entradas, atualizar os estados dos objetos e redesenhar tudo a cada frame (`requestAnimationFrame`).
    * **Início do Jogo:** Uma breve mensagem de "Prepare-se" é exibida antes de o jogo ser efetivamente iniciado.

## Contribuições

Este é um projeto simples criado como demonstração. Sinta-se à vontade para fazer um fork deste repositório, modificar o código e experimentar!

## Possíveis Melhorias Futuras

* Implementação de sprites e animações detalhadas para movimentos e ataques.
* Mecânicas de luta mais avançadas (defesas, esquivas, combos, ataques especiais).
* Seleção de personagens e cenários variados.
* Efeitos sonoros e música de fundo para maior imersão.

Divirta-se a jogar e a explorar o código!