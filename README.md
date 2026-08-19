#```html
<!DOCTYPE html>
<html lang="pt-BR">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">

    <title>GameCode — Jogos & Programação</title>

    <style>
        /* =========================
           RESET
        ========================== */

        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
            scroll-behavior: smooth;
        }

        body {
            font-family: Arial, Helvetica, sans-serif;
            background: #b30000;
            color: #ffffff;
            line-height: 1.6;
        }

        a {
            color: inherit;
            text-decoration: none;
        }

        /* =========================
           HEADER
        ========================== */

        header {
            position: fixed;
            top: 0;
            left: 0;
            width: 100%;
            height: 75px;

            display: flex;
            align-items: center;
            justify-content: space-between;

            padding: 0 7%;

            background: #080808;
            border-bottom: 2px solid #ff1a1a;

            z-index: 1000;
        }

        .logo {
            font-size: 1.7rem;
            font-weight: 900;
            letter-spacing: 1px;
        }

        .logo span {
            color: #ff1a1a;
        }

        nav ul {
            display: flex;
            list-style: none;
            gap: 30px;
        }

        nav a {
            font-weight: bold;
            position: relative;
            transition: 0.3s;
        }

        nav a::after {
            content: "";
            position: absolute;
            left: 0;
            bottom: -7px;

            width: 0;
            height: 3px;

            background: #ff1a1a;
            transition: 0.3s;
        }

        nav a:hover {
            color: #ff3333;
        }

        nav a:hover::after {
            width: 100%;
        }

        /* =========================
           HERO
        ========================== */

        .hero {
            min-height: 100vh;

            display: flex;
            align-items: center;

            padding: 120px 7% 80px;

            background:
                radial-gradient(
                    circle at 80% 40%,
                    rgba(0, 0, 0, 0.35),
                    transparent 35%
                ),
                #b30000;
        }

        .hero-content {
            max-width: 800px;
        }

        .tag {
            display: inline-block;

            padding: 8px 15px;
            margin-bottom: 20px;

            background: #080808;
            color: #ff3333;

            border-radius: 4px;

            font-size: 0.85rem;
            font-weight: bold;
            text-transform: uppercase;
            letter-spacing: 2px;
        }

        .hero h1 {
            font-size: clamp(3rem, 8vw, 7rem);
            line-height: 0.95;
            text-transform: uppercase;
            font-weight: 900;
            margin-bottom: 30px;
        }

        .hero h1 span {
            color: #080808;
        }

        .hero p {
            max-width: 650px;

            font-size: 1.2rem;
            color: #ffe5e5;

            margin-bottom: 35px;
        }

        .btn {
            display: inline-block;

            padding: 15px 28px;

            background: #080808;
            color: #ffffff;

            border: 2px solid #080808;

            font-weight: bold;
            text-transform: uppercase;

            transition: 0.3s;
        }

        .btn:hover {
            background: transparent;
            color: #080808;
            transform: translateY(-4px);
        }

        /* =========================
           SEÇÕES
        ========================== */

        section {
            padding: 100px 7%;
        }

        .dark-section {
            background: #080808;
            color: #ffffff;
        }

        .section-title {
            max-width: 750px;
            margin-bottom: 60px;
        }

        .section-title small {
            color: #ff3333;
            font-weight: bold;
            text-transform: uppercase;
            letter-spacing: 3px;
        }

        .section-title h2 {
            font-size: clamp(2.3rem, 5vw, 4.5rem);
            line-height: 1;
            margin-top: 15px;
        }

        .section-title p {
            margin-top: 20px;
            color: #cccccc;
        }

        /* =========================
           CARDS
        ========================== */

        .cards {
            display: grid;
            grid-template-columns: repeat(3, 1fr);
            gap: 25px;
        }

        .card {
            padding: 35px;

            background: #151515;
            border: 1px solid #333;

            transition: 0.3s;
        }

        .card:hover {
            transform: translateY(-10px);
            border-color: #ff1a1a;
            box-shadow: 0 15px 40px rgba(255, 0, 0, 0.15);
        }

        .card-number {
            font-size: 3rem;
            font-weight: 900;
            color: #ff1a1a;

            margin-bottom: 20px;
        }

        .card h3 {
            font-size: 1.5rem;
            margin-bottom: 15px;
        }

        .card p {
            color: #bbbbbb;
        }

        /* =========================
           PRODUTIVIDADE
        ========================== */

        .productivity {
            background: #d90000;
        }

        .productivity-container {
            display: grid;
            grid-template-columns: 1fr 1fr;
            gap: 70px;
            align-items: center;
        }

        .productivity h2 {
            font-size: clamp(2.5rem, 5vw, 5rem);
            line-height: 1;
            color: #080808;
        }

        .productivity-text p {
            margin-top: 25px;
            font-size: 1.1rem;
            color: #ffeaea;
        }

        .stats {
            display: grid;
            grid-template-columns: repeat(2, 1fr);
            gap: 15px;
            margin-top: 30px;
        }

        .stat {
            background: #080808;
            padding: 25px;
        }

        .stat strong {
            display: block;

            font-size: 2.5rem;
            color: #ff3333;
        }

        .stat span {
            color: #ffffff;
            font-size: 0.9rem;
        }

        /* =========================
           JOGOS NA PROGRAMAÇÃO
        ========================== */

        .game-section {
            background: #f1f1f1;
            color: #080808;
        }

        .game-grid {
            display: grid;
            grid-template-columns: 1fr 1fr;
            gap: 50px;
        }

        .game-item {
            padding: 35px;

            border-left: 6px solid #d90000;
            background: #ffffff;

            transition: 0.3s;
        }

        .game-item:hover {
            transform: translateX(10px);
            box-shadow: 10px 10px 0 #080808;
        }

        .game-item h3 {
            margin-bottom: 12px;
            font-size: 1.5rem;
        }

        .game-item p {
            color: #555555;
        }

        /* =========================
           CTA
        ========================== */

        .cta {
            text-align: center;
            background: #080808;
        }

        .cta h2 {
            font-size: clamp(2.5rem, 6vw, 5rem);
            line-height: 1;
            margin-bottom: 25px;
        }

        .cta h2 span {
            color: #ff1a1a;
        }

        .cta p {
            max-width: 650px;
            margin: 0 auto 35px;
            color: #bbbbbb;
        }

        /* =========================
           FOOTER
        ========================== */

        footer {
            padding: 30px 7%;

            display: flex;
            justify-content: space-between;
            align-items: center;

            background: #050505;
            border-top: 1px solid #292929;

            color: #888;
        }

        footer strong {
            color: #ff1a1a;
        }

        /* =========================
           ANIMAÇÃO
        ========================== */

        .fade-in {
            opacity: 0;
            transform: translateY(30px);
            transition: opacity 0.8s ease, transform 0.8s ease;
        }

        .fade-in.visible {
            opacity: 1;
            transform: translateY(0);
        }

        /* =========================
           RESPONSIVIDADE
        ========================== */

        @media (max-width: 900px) {

            header {
                padding: 0 5%;
            }

            nav ul {
                gap: 15px;
            }

            .cards {
                grid-template-columns: 1fr;
            }

            .productivity-container {
                grid-template-columns: 1fr;
            }

            .game-grid {
                grid-template-columns: 1fr;
            }
        }

        @media (max-width: 600px) {

            header {
                height: auto;
                min-height: 70px;

                padding: 15px 5%;

                flex-direction: column;
                gap: 10px;
            }

            nav ul {
                gap: 12px;
                font-size: 0.85rem;
            }

            .hero {
                padding-top: 160px;
            }

            section {
                padding: 70px 5%;
            }

            .stats {
                grid-template-columns: 1fr;
            }

            footer {
                flex-direction: column;
                gap: 10px;
                text-align: center;
            }
        }
    </style>
</head>

<body>

    <!-- =========================
         CABEÇALHO
    ========================== -->

    <header>

        <a href="#inicio" class="logo">
            GAME<span>CODE</span>
        </a>

        <nav>
            <ul>
                <li>
                    <a href="#inicio">Início</a>
                </li>

                <li>
                    <a href="#importancia">Importância</a>
                </li>

                <li>
                    <a href="#produtividade">Produtividade</a>
                </li>

                <li>
                    <a href="#programacao">Programação</a>
                </li>
            </ul>
        </nav>

    </header>


    <!-- =========================
         HERO
    ========================== -->

    <main>

        <section class="hero" id="inicio">

            <div class="hero-content fade-in">

                <span class="tag">
                    Gaming + Technology
                </span>

                <h1>
                    JOGAR.
                    <br>
                    APRENDER.
                    <br>
                    <span>PROGRAMAR.</span>
                </h1>

                <p>
                    Os jogos vão muito além do entretenimento.
                    Eles podem estimular criatividade, raciocínio lógico,
                    resolução de problemas e habilidades fundamentais
                    para quem trabalha com programação.
                </p>

                <a href="#importancia" class="btn">
                    Descubra mais
                </a>

            </div>

        </section>


        <!-- =========================
             IMPORTÂNCIA
        ========================== -->

        <section class="dark-section" id="importancia">

            <div class="section-title fade-in">

                <small>01 — Por que importa?</small>

                <h2>
                    O jogo também pode ser uma ferramenta de aprendizado.
                </h2>

                <p>
                    Jogar exige decisões rápidas, planejamento e adaptação.
                    Essas características possuem uma relação direta com
                    diversas competências utilizadas no desenvolvimento
                    de software.
                </p>

            </div>


            <div class="cards">

                <article class="card fade-in">

                    <div class="card-number">01</div>

                    <h3>
                        Raciocínio lógico
                    </h3>

                    <p>
                        Jogos apresentam desafios que incentivam o jogador
                        a analisar situações, identificar padrões e encontrar
                        soluções.
                    </p>

                </article>


                <article class="card fade-in">

                    <div class="card-number">02</div>

                    <h3>
                        Resolução de problemas
                    </h3>

                    <p>
                        Assim como na programação, muitos jogos exigem
                        tentativa, erro, análise e criação de estratégias
                        para superar obstáculos.
                    </p>

                </article>


                <article class="card fade-in">

                    <div class="card-number">03</div>

                    <h3>
                        Criatividade
                    </h3>

                    <p>
                        Games estimulam a exploração de diferentes
                        possibilidades, algo essencial para desenvolver
                        soluções criativas em tecnologia.
                    </p>

                </article>

            </div>

        </section>


        <!-- =========================
             PRODUTIVIDADE
        ========================== -->

        <section class="productivity" id="produtividade">

            <div class="productivity-container">

                <div class="productivity-text fade-in">

                    <small>
                        02 — Tecnologia & produtividade
                    </small>

                    <h2>
                        JOGAR PODE MUDAR A FORMA COMO TRABALHAMOS.
                    </h2>

                    <p>
                        Quando utilizados de maneira equilibrada, jogos
                        digitais podem funcionar como momentos de pausa
                        e descontração durante a rotina tecnológica.
                    </p>

                    <p>
                        A combinação entre tecnologia, interação e desafios
                        pode ajudar a criar ambientes mais dinâmicos,
                        especialmente em equipes que trabalham diariamente
                        com computadores e programação.
                    </p>

                </div>


                <div class="stats fade-in">

                    <div class="stat">
                        <strong>01</strong>
                        <span>
                            Pausas mais dinâmicas
                        </span>
                    </div>

                    <div class="stat">
                        <strong>02</strong>
                        <span>
                            Estímulo à criatividade
                        </span>
                    </div>

                    <div class="stat">
                        <strong>03</strong>
                        <span>
                            Interação entre equipes
                        </span>
                    </div>

                    <div class="stat">
                        <strong>04</strong>
                        <span>
                            Desenvolvimento de estratégias
                        </span>
                    </div>

                </div>

            </div>

        </section>


        <!-- =========================
             JOGOS + PROGRAMAÇÃO
        ========================== -->

        <section class="game-section" id="programacao">

            <div class="section-title fade-in">

                <small>
                    03 — Games na programação
                </small>

                <h2>
                    Habilidades de jogador também podem aparecer no código.
                </h2>

                <p>
                    Programar é resolver problemas constantemente.
                    Por isso, várias habilidades desenvolvidas nos games
                    podem ser úteis durante a criação de sistemas e
                    aplicações.
                </p>

            </div>


            <div class="game-grid">

                <article class="game-item fade-in">

                    <h3>
                        🎯 Estratégia
                    </h3>

                    <p>
                        Planejar movimentos em um jogo é semelhante a
                        planejar a estrutura de uma aplicação antes de
                        começar a escrever o código.
                    </p>

                </article>


                <article class="game-item fade-in">

                    <h3>
                        🧠 Pensamento crítico
                    </h3>

                    <p>
                        Identificar o que está funcionando e o que precisa
                        ser alterado é uma habilidade importante tanto
                        nos jogos quanto no desenvolvimento de software.
                    </p>

                </article>


                <article class="game-item fade-in">

                    <h3>
                        ⚡ Adaptação
                    </h3>

                    <p>
                        Bugs e problemas inesperados fazem parte da
                        programação. A capacidade de se adaptar ajuda
                        o desenvolvedor a encontrar novas soluções.
                    </p>

                </article>


                <article class="game-item fade-in">

                    <h3>
                        🏆 Persistência
                    </h3>

                    <p>
                        Nem todo desafio é resolvido na primeira tentativa.
                        A persistência presente nos jogos também é valiosa
                        para aprender programação.
                    </p>

                </article>

            </div>

        </section>


        <!-- =========================
             CTA
        ========================== -->

        <section class="cta">

            <div class="fade-in">

                <h2>
                    TRANSFORME
                    <span>JOGOS</span>
                    EM APRENDIZADO.
                </h2>

                <p>
                    Jogar pode ser divertido. Programar também.
                    Quando os dois mundos se encontram, tecnologia,
                    criatividade e resolução de problemas podem andar
                    juntos.
                </p>

                <a href="#inicio" class="btn">
                    Voltar ao início
                </a>

            </div>

        </section>

    </main>


    <!-- =========================
         FOOTER
    ========================== -->

    <footer>

        <div>
            <strong>GAMECODE</strong>
            — Jogos & Programação
        </div>

        <div>
            HTML5 • CSS3 • JavaScript
        </div>

    </footer>


    <!-- =========================
         JAVASCRIPT
    ========================== -->

    <script>

        // ==========================================
        // SCROLL SUAVE
        // ==========================================

        document.querySelectorAll('a[href^="#"]').forEach(link => {

            link.addEventListener("click", function(event) {

                event.preventDefault();

                const target = document.querySelector(
                    this.getAttribute("href")
                );

                if (target) {

                    target.scrollIntoView({
                        behavior: "smooth",
                        block: "start"
                    });

                }

            });

        });


        // ==========================================
        // ANIMAÇÃO AO ENTRAR NA TELA
        // ==========================================

        const observer = new IntersectionObserver(
            (entries) => {

                entries.forEach(entry => {

                    if (entry.isIntersecting) {

                        entry.target.classList.add("visible");

                        observer.unobserve(entry.target);

                    }

                });

            },
            {
                threshold: 0.15
            }
        );


        document.querySelectorAll(".fade-in").forEach(element => {

            observer.observe(element);

        });


        // ==========================================
        // EFEITO NO HEADER AO ROLAR
        // ==========================================

        const header = document.querySelector("header");

        window.addEventListener("scroll", () => {

            if (window.scrollY > 50) {

                header.style.background = "#000000";

            } else {

                header.style.background = "#080808";

            }

        });

    </script>

</body>
</html>
```
 Uso-da-programacao-nos-jogos-digitais
pratica da programacao com jogos digitais
