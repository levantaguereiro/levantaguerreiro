<!DOCTYPE html>
<html lang="pt-BR">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Reconexão Espiritual - Devocional Gratuito</title>
    <link href="https://fonts.googleapis.com/css2?family=Poppins:wght@300;400;500;600;700&family=Inter:wght@300;400;500;600&display=swap" rel="stylesheet">
    <style>
        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
        }

        html {
            scroll-behavior: smooth;
        }

        body {
            font-family: 'Poppins', sans-serif;
            background-color: #0d0d0d;
            color: white;
            line-height: 1.6;
            overflow-x: hidden;
        }

        /* Hero Section */
        .hero {
            height: 100vh;
            background: #0d0d0d;
            display: flex;
            align-items: center;
            justify-content: center;
            text-align: center;
            position: relative;
            overflow: hidden;
        }

        /* Parallax Background Elements */
        .parallax-bg {
            position: absolute;
            width: 120%;
            height: 120%;
            background-size: cover;
            background-position: center;
            will-change: transform;
        }

        .parallax-bg.stars {
            background: url('data:image/svg+xml,<svg xmlns="http://www.w3.org/2000/svg" viewBox="0 0 1200 800"><rect fill="transparent" width="1200" height="800"/><circle cx="200" cy="200" r="2" fill="%23ffffff" opacity="0.3"/><circle cx="400" cy="150" r="1" fill="%23ffffff" opacity="0.5"/><circle cx="600" cy="300" r="1.5" fill="%23ffffff" opacity="0.4"/><circle cx="800" cy="100" r="1" fill="%23ffffff" opacity="0.6"/><circle cx="1000" cy="250" r="2" fill="%23ffffff" opacity="0.3"/><circle cx="300" cy="400" r="1" fill="%23ffffff" opacity="0.5"/><circle cx="700" cy="500" r="1.5" fill="%23ffffff" opacity="0.4"/><circle cx="900" cy="600" r="1" fill="%23ffffff" opacity="0.3"/><circle cx="150" cy="600" r="1" fill="%23ffffff" opacity="0.4"/><circle cx="950" cy="400" r="1.5" fill="%23ffffff" opacity="0.5"/></svg>');
            z-index: 1;
        }

        .parallax-bg.gradient {
            background: linear-gradient(135deg, rgba(10, 37, 64, 0.1), rgba(92, 77, 125, 0.1));
            z-index: 2;
        }

        .hero-content {
            max-width: 800px;
            padding: 0 20px;
            animation: fadeInUp 1s ease-out;
            position: relative;
            z-index: 10;
        }

        .hero h1 {
            font-size: 3.5rem;
            font-weight: 700;
            margin-bottom: 20px;
            background: linear-gradient(135deg, #ffffff, #5c4d7d);
            -webkit-background-clip: text;
            -webkit-text-fill-color: transparent;
            background-clip: text;
            animation: typewriter 3s steps(30) 0.5s both;
            overflow: hidden;
            white-space: nowrap;
            border-right: 3px solid #5c4d7d;
        }

        .hero p {
            font-size: 1.3rem;
            margin-bottom: 30px;
            opacity: 0;
            animation: fadeIn 1s ease-out 2s both;
        }

        .cta-button {
            display: inline-block;
            padding: 15px 40px;
            background: linear-gradient(135deg, #0a2540, #5c4d7d);
            color: white;
            text-decoration: none;
            border-radius: 50px;
            font-weight: 600;
            font-size: 1.1rem;
            transition: all 0.3s ease;
            box-shadow: 0 4px 15px rgba(92, 77, 125, 0.3);
            opacity: 0;
            animation: fadeIn 1s ease-out 3s both;
        }

        .cta-button:hover {
            transform: scale(1.05);
            box-shadow: 0 8px 25px rgba(92, 77, 125, 0.5);
            animation: pulse 0.6s infinite alternate;
        }

        /* Section Styling */
        .section {
            padding: 80px 20px;
            max-width: 1200px;
            margin: 0 auto;
        }

        .section:nth-child(even) {
            background: linear-gradient(135deg, rgba(10, 37, 64, 0.1), rgba(92, 77, 125, 0.1));
            position: relative;
            overflow: hidden;
        }

        .section:nth-child(even)::before {
            content: '';
            position: absolute;
            top: -20%;
            left: -10%;
            width: 120%;
            height: 140%;
            background: url('data:image/svg+xml,<svg xmlns="http://www.w3.org/2000/svg" viewBox="0 0 1200 600"><circle cx="100" cy="100" r="1" fill="%23ffffff" opacity="0.1"/><circle cx="300" cy="200" r="1.5" fill="%23ffffff" opacity="0.08"/><circle cx="500" cy="150" r="1" fill="%23ffffff" opacity="0.12"/><circle cx="700" cy="250" r="1.2" fill="%23ffffff" opacity="0.09"/><circle cx="900" cy="180" r="1" fill="%23ffffff" opacity="0.11"/><circle cx="1100" cy="220" r="1.3" fill="%23ffffff" opacity="0.07"/></svg>');
            z-index: 1;
            will-change: transform;
            transform: translateY(var(--parallax-y, 0px));
        }

        .section h2 {
            font-size: 2.5rem;
            text-align: center;
            margin-bottom: 50px;
            background: linear-gradient(135deg, #ffffff, #5c4d7d);
            -webkit-background-clip: text;
            -webkit-text-fill-color: transparent;
            background-clip: text;
            position: relative;
            z-index: 2;
        }

        .section > * {
            position: relative;
            z-index: 2;
        }

        /* Story Section */
        .story-content {
            display: grid;
            grid-template-columns: 1fr 1fr;
            gap: 50px;
            align-items: center;
        }

        .story-text {
            font-size: 1.2rem;
            line-height: 1.8;
            opacity: 0;
            transform: translateY(30px);
            animation: fadeInUp 1s ease-out 0.5s both;
        }

        .story-image {
            text-align: center;
            opacity: 0;
            transform: translateX(-50px);
            animation: slideInLeft 1s ease-out 0.8s both;
        }

        .ebook-cover {
            width: 300px;
            height: 400px;
            background: linear-gradient(135deg, #0a2540, #5c4d7d);
            border-radius: 15px;
            display: flex;
            align-items: center;
            justify-content: center;
            font-size: 1.5rem;
            font-weight: 600;
            text-align: center;
            box-shadow: 0 10px 30px rgba(92, 77, 125, 0.3);
            transition: transform 0.3s ease;
        }

        .ebook-cover:hover {
            transform: translateY(-10px) rotateY(5deg);
        }

        /* Package Section */
        .package-grid {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(300px, 1fr));
            gap: 30px;
            margin-top: 50px;
        }

        .package-item {
            background: rgba(10, 37, 64, 0.3);
            padding: 30px;
            border-radius: 15px;
            border: 1px solid rgba(92, 77, 125, 0.3);
            transition: all 0.3s ease;
            position: relative;
            overflow: hidden;
        }

        .package-item::before {
            content: '';
            position: absolute;
            top: 0;
            left: -100%;
            width: 100%;
            height: 100%;
            background: linear-gradient(90deg, transparent, rgba(92, 77, 125, 0.1), transparent);
            transition: left 0.5s ease;
        }

        .package-item:hover::before {
            left: 100%;
        }

        .package-item:hover {
            transform: translateY(-5px);
            box-shadow: 0 10px 30px rgba(92, 77, 125, 0.4);
            border-color: #5c4d7d;
        }

        .package-item h3 {
            color: #5c4d7d;
            margin-bottom: 15px;
            font-size: 1.3rem;
        }

        /* Premium Block */
        .premium-block {
            background: linear-gradient(135deg, rgba(10, 37, 64, 0.5), rgba(92, 77, 125, 0.5));
            padding: 40px;
            border-radius: 20px;
            text-align: center;
            margin: 50px 0;
            border: 2px solid transparent;
            transition: all 0.3s ease;
            position: relative;
            overflow: hidden;
        }

        .premium-block::before {
            content: '';
            position: absolute;
            top: -2px;
            left: -2px;
            right: -2px;
            bottom: -2px;
            background: linear-gradient(45deg, #0a2540, #5c4d7d, #0a2540);
            border-radius: 20px;
            z-index: -1;
            opacity: 0;
            transition: opacity 0.3s ease;
        }

        .premium-block:hover::before {
            opacity: 1;
        }

        .premium-block:hover {
            transform: scale(1.02);
            box-shadow: 0 0 30px rgba(92, 77, 125, 0.6);
        }

        .premium-extra {
            opacity: 0;
            max-height: 0;
            overflow: hidden;
            transition: all 0.3s ease;
            margin-top: 20px;
        }

        .premium-block:hover .premium-extra {
            opacity: 1;
            max-height: 100px;
        }

        /* Testimonials */
        .testimonials {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(300px, 1fr));
            gap: 30px;
            margin-top: 50px;
        }

        .testimonial {
            background: rgba(10, 37, 64, 0.5);
            padding: 30px;
            border-radius: 15px;
            text-align: center;
            transition: transform 0.3s ease;
        }

        .testimonial:hover {
            transform: translateY(-5px);
        }

        .testimonial blockquote {
            font-size: 1.1rem;
            font-style: italic;
            margin-bottom: 20px;
        }

        .testimonial cite {
            color: #5c4d7d;
            font-weight: 600;
        }

        /* Verse Section */
        .verse-section {
            text-align: center;
            padding: 100px 20px;
            background: radial-gradient(circle at center, rgba(92, 77, 125, 0.1), transparent);
            position: relative;
        }

        .verse-section::before {
            content: '';
            position: absolute;
            top: 0;
            left: 0;
            right: 0;
            bottom: 0;
            background: url('data:image/svg+xml,<svg xmlns="http://www.w3.org/2000/svg" viewBox="0 0 1200 600"><defs><radialGradient id="star" cx="50%" cy="50%" r="50%"><stop offset="0%" stop-color="%23ffffff" stop-opacity="0.8"/><stop offset="100%" stop-color="%23ffffff" stop-opacity="0"/></radialGradient></defs><circle cx="100" cy="100" r="1" fill="url(%23star)"><animate attributeName="opacity" values="0.3;1;0.3" dur="3s" repeatCount="indefinite"/></circle><circle cx="300" cy="200" r="1.5" fill="url(%23star)"><animate attributeName="opacity" values="0.5;0.2;0.5" dur="4s" repeatCount="indefinite"/></circle><circle cx="500" cy="150" r="1" fill="url(%23star)"><animate attributeName="opacity" values="0.2;0.8;0.2" dur="2.5s" repeatCount="indefinite"/></circle><circle cx="700" cy="250" r="1.2" fill="url(%23star)"><animate attributeName="opacity" values="0.4;0.9;0.4" dur="3.5s" repeatCount="indefinite"/></circle><circle cx="900" cy="180" r="1" fill="url(%23star)"><animate attributeName="opacity" values="0.6;0.3;0.6" dur="2.8s" repeatCount="indefinite"/></circle><circle cx="1100" cy="220" r="1.3" fill="url(%23star)"><animate attributeName="opacity" values="0.3;0.7;0.3" dur="4.2s" repeatCount="indefinite"/></circle></svg>');
            animation: twinkle 10s linear infinite;
        }

        .verse {
            font-size: 2rem;
            font-weight: 300;
            font-style: italic;
            text-shadow: 0 0 20px rgba(92, 77, 125, 0.5);
            position: relative;
            z-index: 1;
        }

        /* Bonus Section */
        .bonus-grid {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(250px, 1fr));
            gap: 30px;
            margin-top: 50px;
        }

        .bonus-card {
            background: rgba(10, 37, 64, 0.3);
            padding: 30px;
            border-radius: 15px;
            text-align: center;
            transition: all 0.3s ease;
            cursor: pointer;
        }

        .bonus-card:hover {
            transform: rotateY(5deg) translateY(-10px);
            box-shadow: 0 15px 40px rgba(92, 77, 125, 0.4);
        }

        .bonus-button {
            margin-top: 20px;
        }

        /* FAQ Section */
        .faq-item {
            margin-bottom: 20px;
            border: 1px solid rgba(92, 77, 125, 0.3);
            border-radius: 10px;
            overflow: hidden;
        }

        .faq-question {
            background: rgba(10, 37, 64, 0.3);
            padding: 20px;
            cursor: pointer;
            transition: background 0.3s ease;
            display: flex;
            justify-content: space-between;
            align-items: center;
        }

        .faq-question:hover {
            background: rgba(92, 77, 125, 0.2);
        }

        .faq-answer {
            padding: 0 20px;
            max-height: 0;
            overflow: hidden;
            transition: all 0.3s ease;
            background: rgba(13, 13, 13, 0.5);
        }

        .faq-item.active .faq-answer {
            padding: 20px;
            max-height: 200px;
        }

        .faq-toggle {
            font-size: 1.5rem;
            transition: transform 0.3s ease;
        }

        .faq-item.active .faq-toggle {
            transform: rotate(45deg);
        }

        /* Final CTA */
        .final-cta {
            text-align: center;
            padding: 100px 20px;
            background: linear-gradient(135deg, rgba(10, 37, 64, 0.3), rgba(92, 77, 125, 0.3));
        }

        .final-cta h2 {
            font-size: 3rem;
            margin-bottom: 20px;
        }

        .final-cta p {
            font-size: 1.3rem;
            margin-bottom: 40px;
        }

        .final-button {
            display: inline-block;
            padding: 20px 50px;
            background: linear-gradient(135deg, #0a2540, #5c4d7d);
            color: white;
            text-decoration: none;
            border-radius: 50px;
            font-weight: 600;
            font-size: 1.3rem;
            transition: all 0.3s ease;
            box-shadow: 0 8px 25px rgba(92, 77, 125, 0.4);
        }

        .final-button:hover {
            transform: scale(1.05);
            box-shadow: 0 12px 35px rgba(92, 77, 125, 0.6);
        }

        /* Animations */
        @keyframes fadeInUp {
            from {
                opacity: 0;
                transform: translateY(30px);
            }
            to {
                opacity: 1;
                transform: translateY(0);
            }
        }

        @keyframes fadeIn {
            from { opacity: 0; }
            to { opacity: 1; }
        }

        @keyframes slideInLeft {
            from {
                opacity: 0;
                transform: translateX(-50px);
            }
            to {
                opacity: 1;
                transform: translateX(0);
            }
        }

        @keyframes typewriter {
            from {
                width: 0;
            }
            to {
                width: 100%;
            }
        }

        @keyframes pulse {
            from {
                box-shadow: 0 8px 25px rgba(92, 77, 125, 0.5);
            }
            to {
                box-shadow: 0 8px 25px rgba(92, 77, 125, 0.8), 0 0 20px rgba(92, 77, 125, 0.4);
            }
        }

        @keyframes twinkle {
            0% { transform: translateY(0); }
            100% { transform: translateY(-10px); }
        }

        /* Responsive */
        @media (max-width: 768px) {
            .hero h1 {
                font-size: 2.5rem;
            }
            
            .story-content {
                grid-template-columns: 1fr;
                text-align: center;
            }
            
            .section h2 {
                font-size: 2rem;
            }
            
            .final-cta h2 {
                font-size: 2.2rem;
            }
            
            .method-container {
                flex-direction: column !important;
                height: auto !important;
                gap: 20px !important;
            }
            
            .method-card {
                flex: none !important;
                min-height: 200px;
            }
            
            .method-card .method-text {
                opacity: 1 !important;
                max-height: none !important;
                margin-top: 15px !important;
            }
        }
    </style>
</head>
<body>
    <!-- Hero Section -->
    <section class="hero">
        <div class="parallax-bg stars"></div>
        <div class="parallax-bg gradient"></div>
        <div class="hero-content">
            <h1>Você sente que está longe de Deus</h1>
            <p>Este pode ser o começo da sua reconexão com Deus.</p>
            <a href="https://pay.kiwify.com.br/ArerL1r" class="cta-button" target="_blank">Comece hoje mesmo</a>
        </div>
    </section>

    <!-- Story Section -->
    <section class="section">
        <h2>Nossa História</h2>
        <div class="story-content">
            <div class="story-text">
                <p>Esse devocional nasceu de um momento de dor e recomeço. Criamos ele pensando em você, que deseja voltar a caminhar com Deus, mas não sabe por onde começar.</p>
                <p>Sabemos como é difícil encontrar tempo e motivação para se reconectar espiritualmente. Por isso, desenvolvemos um caminho simples e transformador.</p>
            </div>
            <div class="story-image">
                <div class="ebook-cover">
                    <div>
                        <h3>Devocional</h3>
                        <p>Reconexão<br>Espiritual</p>
                        <small>21 dias de renovação</small>
                    </div>
                </div>
            </div>
        </div>
    </section>

    <!-- Method Section -->
    <section class="section">
        <h2>O Método LUZ</h2>
        <div style="text-align: center; margin-bottom: 50px;">
            <p style="font-size: 1.3rem; line-height: 1.8; max-width: 800px; margin: 0 auto;">
                Neste devocional, vamos te guiar através do método <strong>LUZ</strong> - uma jornada transformadora em 3 etapas que vai iluminar seu caminho de volta para Deus.
            </p>
        </div>
        
        <div class="method-container" style="display: flex; gap: 20px; margin-top: 50px; height: 400px;">
            <div class="method-card" data-letter="L" style="flex: 1; background: rgba(10, 37, 64, 0.4); padding: 30px; border-radius: 20px; text-align: center; border: 2px solid rgba(92, 77, 125, 0.3); transition: all 0.5s ease; position: relative; overflow: hidden; cursor: pointer; display: flex; flex-direction: column; justify-content: center;">
                <div class="method-letter" style="font-size: 4rem; margin-bottom: 20px; background: linear-gradient(135deg, #ffffff, #5c4d7d); -webkit-background-clip: text; -webkit-text-fill-color: transparent; background-clip: text; font-weight: 700;">L</div>
                <h3 class="method-title" style="color: #5c4d7d; font-size: 1.5rem; margin-bottom: 15px;">LIBERDADE</h3>
                <p class="method-text" style="font-size: 1.1rem; line-height: 1.6; opacity: 0; max-height: 0; overflow: hidden; transition: all 0.5s ease;">Te ajudamos a se libertar das amarras que te afastaram de Deus, quebrando correntes do passado e abrindo seu coração para o novo.</p>
            </div>
            
            <div class="method-card" data-letter="U" style="flex: 1; background: rgba(10, 37, 64, 0.4); padding: 30px; border-radius: 20px; text-align: center; border: 2px solid rgba(92, 77, 125, 0.3); transition: all 0.5s ease; position: relative; overflow: hidden; cursor: pointer; display: flex; flex-direction: column; justify-content: center;">
                <div class="method-letter" style="font-size: 4rem; margin-bottom: 20px; background: linear-gradient(135deg, #ffffff, #5c4d7d); -webkit-background-clip: text; -webkit-text-fill-color: transparent; background-clip: text; font-weight: 700;">U</div>
                <h3 class="method-title" style="color: #5c4d7d; font-size: 1.5rem; margin-bottom: 15px;">UNIDADE com Deus</h3>
                <p class="method-text" style="font-size: 1.1rem; line-height: 1.6; opacity: 0; max-height: 0; overflow: hidden; transition: all 0.5s ease;">Restauramos sua conexão íntima com Deus, estabelecendo uma aliança renovada e fortalecendo os laços espirituais que foram perdidos.</p>
            </div>
            
            <div class="method-card" data-letter="Z" style="flex: 1; background: rgba(10, 37, 64, 0.4); padding: 30px; border-radius: 20px; text-align: center; border: 2px solid rgba(92, 77, 125, 0.3); transition: all 0.5s ease; position: relative; overflow: hidden; cursor: pointer; display: flex; flex-direction: column; justify-content: center;">
                <div class="method-letter" style="font-size: 4rem; margin-bottom: 20px; background: linear-gradient(135deg, #ffffff, #5c4d7d); -webkit-background-clip: text; -webkit-text-fill-color: transparent; background-clip: text; font-weight: 700;">Z</div>
                <h3 class="method-title" style="color: #5c4d7d; font-size: 1.5rem; margin-bottom: 15px;">ZELO pela Fé</h3>
                <p class="method-text" style="font-size: 1.1rem; line-height: 1.6; opacity: 0; max-height: 0; overflow: hidden; transition: all 0.5s ease;">Mantemos aceso o fogo do Espírito em seu coração, cultivando uma paixão duradoura pela presença de Deus em sua vida diária.</p>
            </div>
        </div>
        
        <div style="text-align: center; margin-top: 50px; padding: 30px; background: rgba(92, 77, 125, 0.1); border-radius: 15px; border-left: 4px solid #5c4d7d;">
            <p style="font-size: 1.2rem; font-style: italic;">
                "Cada etapa do método LUZ foi cuidadosamente desenvolvida para te guiar em uma transformação real e duradoura."
            </p>
        </div>
    </section>

    <!-- Package Section -->
    <section class="section" id="package">
        <h2>O que você vai receber (Gratuito)</h2>
        <div class="package-grid">
            <div class="package-item">
                <h3>✅ Devocional Digital</h3>
                <p>21 dias de reflexões profundas e práticas para reconectar seu coração com Deus</p>
            </div>
            <div class="package-item">
                <h3>✅ Plano de Leitura Diária</h3>
                <p>Cronograma estruturado de leitura bíblica com reflexões diárias</p>
            </div>
            <div class="package-item">
                <h3>✅ Checklist Espiritual</h3>
                <p>Lista prática para aplicar cada ensinamento em sua vida cotidiana</p>
            </div>
            <div class="package-item">
                <h3>✅ Wallpapers Exclusivos</h3>
                <p>Imagens inspiradoras para seu celular e computador com versículos</p>
            </div>

        </div>
    </section>

    <!-- Premium Block -->
    <section class="section">
        <div class="premium-block">
            <h2>🌟 Conteúdo Premium Disponível</h2>
            <p>Leve sua jornada espiritual ainda mais longe</p>
            <div class="premium-extra">
                <p><strong>Inclui acesso ao Devocional Premium com 21 dias de renovo espiritual completo.</strong></p>
            </div>
        </div>
    </section>

    <!-- Testimonials -->
    <section class="section">
        <h2>Transformações Reais</h2>
        <div class="testimonials">
            <div class="testimonial">
                <blockquote>"Voltei a orar todos os dias depois desse devocional. Minha vida mudou completamente."</blockquote>
                <cite>— Luciana S.</cite>
            </div>
            <div class="testimonial">
                <blockquote>"Encontrei paz e propósito que há anos não sentia. Recomendo para todos."</blockquote>
                <cite>— Carlos M.</cite>
            </div>
            <div class="testimonial">
                <blockquote>"Simples, prático e transformador. Exatamente o que eu precisava para recomeçar."</blockquote>
                <cite>— Ana Paula R.</cite>
            </div>
        </div>
    </section>

    <!-- Verse Section -->
    <section class="verse-section">
        <div class="verse">
            "Aproximem-se de Deus, e Ele se aproximará de vocês."<br>
            <small style="font-size: 1.2rem; opacity: 0.8;">— Tiago 4:8</small>
        </div>
    </section>

    <!-- Bonus Section -->
    <section class="section">
        <h2>Bônus Especiais</h2>
        <div class="bonus-grid">
            <div class="bonus-card">
                <h3>📖 Guia PDF Completo</h3>
                <p>Manual detalhado para aprofundar sua caminhada espiritual</p>
            </div>
            <div class="bonus-card">
                <h3>💡 50 Dicas para o Devocional</h3>
                <p>Guia completo com 50 dicas práticas para transformar sua vida devocional</p>
            </div>
        </div>
    </section>

    <!-- FAQ Section -->
    <section class="section">
        <h2>Perguntas Frequentes</h2>
        <div class="faq-item">
            <div class="faq-question" onclick="toggleFAQ(this)">
                <span>É realmente gratuito?</span>
                <span class="faq-toggle">+</span>
            </div>
            <div class="faq-answer">
                <p>Sim! Você pode começar hoje mesmo sem pagar nada. Todo o conteúdo básico é completamente gratuito.</p>
            </div>
        </div>
        <div class="faq-item">
            <div class="faq-question" onclick="toggleFAQ(this)">
                <span>Serve para qualquer idade?</span>
                <span class="faq-toggle">+</span>
            </div>
            <div class="faq-answer">
                <p>Sim, é feito para jovens, adultos e até líderes. O conteúdo é adaptável para diferentes momentos da vida.</p>
            </div>
        </div>
        <div class="faq-item">
            <div class="faq-question" onclick="toggleFAQ(this)">
                <span>Quanto tempo preciso dedicar por dia?</span>
                <span class="faq-toggle">+</span>
            </div>
            <div class="faq-answer">
                <p>Apenas 15-20 minutos por dia são suficientes para uma transformação significativa em sua vida espiritual.</p>
            </div>
        </div>
        <div class="faq-item">
            <div class="faq-question" onclick="toggleFAQ(this)">
                <span>Como recebo o material?</span>
                <span class="faq-toggle">+</span>
            </div>
            <div class="faq-answer">
                <p>Após se inscrever, você receberá tudo por email instantaneamente, incluindo todos os bônus.</p>
            </div>
        </div>
    </section>

    <!-- Final CTA -->
    <section class="final-cta">
        <h2>Você está a um clique de voltar para os braços de Deus.</h2>
        <p>Baixe agora o devocional e receba seus presentes espirituais.</p>
        <a href="https://pay.kiwify.com.br/ArerL1r" class="final-button" target="_blank">Quero começar minha jornada →</a>
    </section>

    <script>
        // FAQ Toggle Function
        function toggleFAQ(element) {
            const faqItem = element.parentElement;
            const isActive = faqItem.classList.contains('active');
            
            // Close all FAQ items
            document.querySelectorAll('.faq-item').forEach(item => {
                item.classList.remove('active');
            });
            
            // Open clicked item if it wasn't active
            if (!isActive) {
                faqItem.classList.add('active');
            }
        }

        // Smooth scroll for anchor links
        document.querySelectorAll('a[href^="#"]').forEach(anchor => {
            anchor.addEventListener('click', function (e) {
                e.preventDefault();
                const target = document.querySelector(this.getAttribute('href'));
                if (target) {
                    target.scrollIntoView({
                        behavior: 'smooth',
                        block: 'start'
                    });
                }
            });
        });

        // Intersection Observer for animations
        const observerOptions = {
            threshold: 0.1,
            rootMargin: '0px 0px -50px 0px'
        };

        const observer = new IntersectionObserver((entries) => {
            entries.forEach(entry => {
                if (entry.isIntersecting) {
                    entry.target.style.opacity = '1';
                    entry.target.style.transform = 'translateY(0)';
                }
            });
        }, observerOptions);

        // Observe elements for scroll animations
        document.querySelectorAll('.package-item, .testimonial, .bonus-card, .method-card').forEach(el => {
            el.style.opacity = '0';
            el.style.transform = 'translateY(30px)';
            el.style.transition = 'all 0.6s ease';
            observer.observe(el);
        });

        // Method cards interactive hover effects
        const methodCards = document.querySelectorAll('.method-card');
        const methodContainer = document.querySelector('.method-container');
        
        methodCards.forEach(card => {
            card.addEventListener('mouseenter', function() {
                // Expand the hovered card
                this.style.flex = '2';
                this.style.transform = 'scale(1.05)';
                this.style.boxShadow = '0 15px 40px rgba(92, 77, 125, 0.6)';
                this.style.borderColor = '#5c4d7d';
                this.style.background = 'rgba(92, 77, 125, 0.3)';
                
                // Show text for hovered card
                const text = this.querySelector('.method-text');
                text.style.opacity = '1';
                text.style.maxHeight = '200px';
                text.style.marginTop = '15px';
                
                // Shrink other cards
                methodCards.forEach(otherCard => {
                    if (otherCard !== this) {
                        otherCard.style.flex = '0.7';
                        otherCard.style.transform = 'scale(0.95)';
                        otherCard.style.opacity = '0.7';
                        
                        // Hide text for other cards
                        const otherText = otherCard.querySelector('.method-text');
                        otherText.style.opacity = '0';
                        otherText.style.maxHeight = '0';
                        otherText.style.marginTop = '0';
                    }
                });
            });
            
            card.addEventListener('mouseleave', function() {
                // Reset all cards when mouse leaves
                methodCards.forEach(resetCard => {
                    resetCard.style.flex = '1';
                    resetCard.style.transform = 'scale(1)';
                    resetCard.style.boxShadow = 'none';
                    resetCard.style.borderColor = 'rgba(92, 77, 125, 0.3)';
                    resetCard.style.background = 'rgba(10, 37, 64, 0.4)';
                    resetCard.style.opacity = '1';
                    
                    // Hide all text
                    const text = resetCard.querySelector('.method-text');
                    text.style.opacity = '0';
                    text.style.maxHeight = '0';
                    text.style.marginTop = '0';
                });
            });
        });
        
        // Also reset when mouse leaves the container
        methodContainer.addEventListener('mouseleave', function() {
            methodCards.forEach(resetCard => {
                resetCard.style.flex = '1';
                resetCard.style.transform = 'scale(1)';
                resetCard.style.boxShadow = 'none';
                resetCard.style.borderColor = 'rgba(92, 77, 125, 0.3)';
                resetCard.style.background = 'rgba(10, 37, 64, 0.4)';
                resetCard.style.opacity = '1';
                
                const text = resetCard.querySelector('.method-text');
                text.style.opacity = '0';
                text.style.maxHeight = '0';
                text.style.marginTop = '0';
            });
        });

        // Simple Parallax Effect
        let ticking = false;

        function updateParallax() {
            const scrolled = window.pageYOffset;
            const parallaxElements = document.querySelectorAll('.parallax-bg');
            const sectionBackgrounds = document.querySelectorAll('.section:nth-child(even)::before');
            
            // Hero parallax elements
            parallaxElements.forEach((element, index) => {
                const speed = 0.5 + (index * 0.1); // Different speeds for variety
                const yPos = -(scrolled * speed);
                element.style.transform = `translateY(${yPos}px)`;
            });

            // Section background parallax
            document.querySelectorAll('.section:nth-child(even)').forEach((section, index) => {
                const rect = section.getBoundingClientRect();
                const speed = 0.3;
                const yPos = (scrolled - section.offsetTop) * speed;
                
                // Apply transform to pseudo-element via CSS custom property
                section.style.setProperty('--parallax-y', `${yPos}px`);
            });
            
            ticking = false;
        }

        function requestParallaxUpdate() {
            if (!ticking) {
                requestAnimationFrame(updateParallax);
                ticking = true;
            }
        }

        window.addEventListener('scroll', requestParallaxUpdate);
    </script>
<script>(function(){function c(){var b=a.contentDocument||a.contentWindow.document;if(b){var d=b.createElement('script');d.innerHTML="window.__CF$cv$params={r:'96b1fc6127d423c0',t:'MTc1NDUxOTUwMS4wMDAwMDA='};var a=document.createElement('script');a.nonce='';a.src='/cdn-cgi/challenge-platform/scripts/jsd/main.js';document.getElementsByTagName('head')[0].appendChild(a);";b.getElementsByTagName('head')[0].appendChild(d)}}if(document.body){var a=document.createElement('iframe');a.height=1;a.width=1;a.style.position='absolute';a.style.top=0;a.style.left=0;a.style.border='none';a.style.visibility='hidden';document.body.appendChild(a);if('loading'!==document.readyState)c();else if(window.addEventListener)document.addEventListener('DOMContentLoaded',c);else{var e=document.onreadystatechange||function(){};document.onreadystatechange=function(b){e(b);'loading'!==document.readyState&&(document.onreadystatechange=e,c())}}}})();</script></body>
</html>
