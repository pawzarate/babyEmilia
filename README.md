
<html lang="es">
<head>
  <meta charset="UTF-8" />
  <meta name="viewport" content="width=device-width, initial-scale=1.0" />
  <title></title>
  <style>
    :root {
      --cream: #fbf7ef;
      --paper: #fffdf8;
      --sage: #8d9f70;
      --sage-dark: #65764e;
      --sage-light: #dfe8cf;
      --pistachio: #b9cf91;
      --beige: #e9dac6;
      --gold: #c9b58e;
      --text: #454438;
      --soft-shadow: rgba(83, 93, 62, 0.14);
    }

    * { box-sizing: border-box; }

    html { scroll-behavior: smooth; }

    body {
      margin: 0;
      background:
        radial-gradient(circle at 15% 5%, rgba(185, 207, 145, 0.24), transparent 30%),
        radial-gradient(circle at 90% 25%, rgba(233, 218, 198, 0.45), transparent 28%),
        linear-gradient(180deg, #fbf7ef 0%, #f7f4ea 58%, #e7edd8 100%);
      color: var(--text);
      font-family: Avenir, "Avenir Next", "Helvetica Neue", Arial, sans-serif;
      min-height: 100vh;
    }

    .page {
      width: min(980px, 100%);
      margin: 0 auto;
      padding: 34px 18px 0;
      overflow: hidden;
    }

    .hero {
      position: relative;
      background: rgba(255, 253, 248, 0.9);
      border: 1px solid rgba(255, 255, 255, 0.9);
      border-radius: 36px;
      padding: 42px 24px 30px;
      box-shadow: 0 24px 80px var(--soft-shadow);
      text-align: center;
      overflow: hidden;
    }

    .hero::before,
    .hero::after {
      content: "";
      position: absolute;
      bottom: 90px;
      width: 290px;
      height: 290px;
      background:
        radial-gradient(ellipse at 50% 85%, transparent 58%, rgba(101, 118, 78, 0.12) 59%, transparent 61%),
        radial-gradient(ellipse at 30% 42%, var(--sage-light) 0 10px, transparent 11px),
        radial-gradient(ellipse at 62% 28%, var(--sage-light) 0 9px, transparent 10px),
        radial-gradient(ellipse at 70% 58%, var(--sage-light) 0 12px, transparent 13px);
      opacity: 0.7;
      pointer-events: none;
    }

    .hero::before { left: -80px; transform: rotate(-18deg); }
    .hero::after { right: -80px; transform: rotate(18deg) scaleX(-1); }

    .eyebrow {
      position: relative;
      z-index: 2;
      margin: 0 0 14px;
      color: var(--sage-dark);
      font-size: 13px;
      letter-spacing: 0.35em;
      text-transform: uppercase;
      font-weight: 600;
    }

    .divider {
      width: 120px;
      height: 18px;
      margin: 0 auto 18px;
      position: relative;
      z-index: 2;
    }

    .divider::before {
      content: "";
      position: absolute;
      left: 0;
      right: 0;
      top: 9px;
      height: 1px;
      background: var(--sage);
    }

    .divider span,
    .divider span::before,
    .divider span::after {
      position: absolute;
      width: 22px;
      height: 10px;
      background: var(--sage-light);
      border: 1px solid rgba(101, 118, 78, 0.18);
      border-radius: 100% 0 100% 0;
    }

    .divider span { left: 49px; top: 4px; transform: rotate(-30deg); }
    .divider span::before { content: ""; left: -33px; top: 3px; transform: rotate(45deg); }
    .divider span::after { content: ""; left: 33px; top: 3px; transform: rotate(45deg); }

    .bunny-envelope {
      position: relative;
      z-index: 2;
      width: min(520px, 92vw);
      height: 300px;
      margin: 6px auto 0;
    }

    .bunny {
      position: absolute;
      left: 50%;
      top: 0;
      transform: translateX(-50%);
      width: 150px;
      height: 150px;
      z-index: 4;
    }

    .ear {
      position: absolute;
      top: 0;
      width: 42px;
      height: 118px;
      background: #fffaf3;
      border: 2px solid #dfcbb1;
      border-radius: 50% 50% 45% 45%;
      box-shadow: inset 0 0 0 11px rgba(185, 207, 145, 0.16);
    }

    .ear.left { left: 36px; transform: rotate(-14deg); }
    .ear.right { right: 36px; transform: rotate(14deg); }

    .head {
      position: absolute;
      left: 26px;
      top: 76px;
      width: 98px;
      height: 74px;
      background: #fffaf3;
      border: 2px solid #dfcbb1;
      border-radius: 48% 48% 46% 46%;
      box-shadow: 0 12px 20px rgba(91, 84, 68, 0.06);
    }

    .eye {
      position: absolute;
      top: 105px;
      width: 8px;
      height: 8px;
      background: var(--sage-dark);
      border-radius: 50%;
      z-index: 6;
    }

    .eye.left { left: 54px; }
    .eye.right { right: 54px; }

    .nose {
      position: absolute;
      left: 71px;
      top: 119px;
      width: 10px;
      height: 8px;
      background: var(--pistachio);
      border-radius: 50%;
      z-index: 6;
    }

    .paw {
      position: absolute;
      top: 138px;
      width: 26px;
      height: 16px;
      background: #fffaf3;
      border: 2px solid #dfcbb1;
      border-radius: 50%;
      z-index: 7;
    }

    .paw.left { left: 36px; transform: rotate(12deg); }
    .paw.right { right: 36px; transform: rotate(-12deg); }

    .envelope {
      position: absolute;
      left: 50%;
      bottom: 4px;
      transform: translateX(-50%);
      width: min(460px, 90vw);
      height: 220px;
      border-radius: 18px;
      background: linear-gradient(145deg, #fff6ea, #f0dfc9);
      box-shadow: 0 25px 45px rgba(90, 80, 60, 0.11);
      overflow: hidden;
      z-index: 3;
    }

    .envelope::before {
      content: "";
      position: absolute;
      inset: 0;
      background: rgba(255,255,255,0.38);
      clip-path: polygon(0 0, 50% 58%, 100% 0, 100% 100%, 0 100%);
    }

    .seal {
      position: absolute;
      left: 50%;
      top: 92px;
      transform: translateX(-50%);
      width: 70px;
      height: 70px;
      border-radius: 50%;
      background: var(--sage);
      color: white;
      display: grid;
      place-items: center;
      font-family: Georgia, "Times New Roman", serif;
      font-size: 38px;
      box-shadow: 0 10px 26px rgba(101, 118, 78, 0.28);
    }

    .seal::before { content: "E"; }

    .script {
      position: relative;
      z-index: 4;
      margin: -4px 0 0;
      color: var(--sage-dark);
      font-family: Georgia, "Times New Roman", serif;
      font-size: clamp(44px, 9vw, 78px);
      font-style: italic;
      font-weight: 400;
      line-height: 1;
    }

    .honor {
      position: relative;
      z-index: 4;
      margin: 12px 0 4px;
      letter-spacing: 0.22em;
      color: var(--sage-dark);
      font-size: 13px;
      text-transform: uppercase;
    }

    .name {
      position: relative;
      z-index: 4;
      margin: 0;
      color: var(--sage-dark);
      font-family: Georgia, "Times New Roman", serif;
      font-size: clamp(54px, 13vw, 92px);
      letter-spacing: 0.22em;
      font-weight: 500;
    }

    .info-card,
    .horizontal-card,
    .message-card {
      position: relative;
      background: rgba(255, 253, 248, 0.92);
      border: 1px solid rgba(255, 255, 255, 0.88);
      border-radius: 28px;
      box-shadow: 0 16px 42px rgba(83, 93, 62, 0.10);
      margin: 18px auto;
      padding: 24px;
      overflow: hidden;
    }

    .info-card {
      display: grid;
      grid-template-columns: 1.05fr 1fr 1fr 1.25fr;
      gap: 0;
      align-items: center;
      text-align: center;
    }

    .info-card > div:not(:last-child) {
      border-right: 1px solid rgba(101, 118, 78, 0.18);
    }

    .mini-bunny {
      width: 112px;
      height: 115px;
      margin: 0 auto;
      position: relative;
    }

    .mini-bunny .ear {
      width: 28px;
      height: 75px;
      border-width: 1.5px;
      box-shadow: inset 0 0 0 8px rgba(185, 207, 145, 0.14);
    }

    .mini-bunny .ear.left { left: 24px; }
    .mini-bunny .ear.right { right: 24px; }
    .mini-bunny .head {
      left: 20px;
      top: 48px;
      width: 72px;
      height: 54px;
      border-width: 1.5px;
    }

    .mini-bunny .eye { top: 70px; width: 5px; height: 5px; }
    .mini-bunny .eye.left { left: 42px; }
    .mini-bunny .eye.right { right: 42px; }
    .mini-bunny .nose { top: 80px; left: 53px; width: 7px; height: 5px; }

    .info-icon {
      width: 34px;
      height: 34px;
      margin: 0 auto 10px;
      border: 3px solid var(--sage);
      border-radius: 10px;
      position: relative;
      opacity: .95;
    }

    .info-icon.calendar::before,
    .info-icon.calendar::after {
      content: "";
      position: absolute;
      width: 5px;
      height: 9px;
      top: -8px;
      background: var(--sage);
      border-radius: 3px;
    }

    .info-icon.calendar::before { left: 7px; }
    .info-icon.calendar::after { right: 7px; }

    .info-icon.clock { border-radius: 50%; }
    .info-icon.clock::before {
      content: "";
      position: absolute;
      width: 3px;
      height: 10px;
      background: var(--sage);
      left: 14px;
      top: 6px;
      border-radius: 3px;
    }

    .info-icon.clock::after {
      content: "";
      position: absolute;
      width: 10px;
      height: 3px;
      background: var(--sage);
      left: 14px;
      top: 15px;
      border-radius: 3px;
    }

    .info-icon.pin {
      border-radius: 50% 50% 50% 0;
      transform: rotate(-45deg);
    }

    .info-icon.pin::after {
      content: "";
      position: absolute;
      width: 9px;
      height: 9px;
      background: var(--sage);
      border-radius: 50%;
      left: 9px;
      top: 9px;
    }

    .label {
      display: block;
      color: var(--sage-dark);
      letter-spacing: 0.18em;
      text-transform: uppercase;
      font-size: 13px;
      font-weight: 700;
      margin-bottom: 8px;
    }

    .big {
      display: block;
      color: var(--sage-dark);
      font-family: Georgia, "Times New Roman", serif;
      font-size: 42px;
      line-height: 1;
      margin-bottom: 4px;
    }

    .small {
      display: block;
      letter-spacing: 0.12em;
      text-transform: uppercase;
      font-size: 13px;
      line-height: 1.5;
    }

    .main-button {
      display: inline-flex;
      justify-content: center;
      align-items: center;
      gap: 12px;
      min-width: 240px;
      padding: 15px 28px;
      border-radius: 12px;
      background: linear-gradient(135deg, #9caf7a, #7f9161);
      color: white;
      text-decoration: none;
      letter-spacing: 0.12em;
      text-transform: uppercase;
      font-size: 13px;
      font-weight: 700;
      box-shadow: 0 12px 24px rgba(101, 118, 78, 0.22);
      transition: transform .25s ease, box-shadow .25s ease;
    }

    .main-button:hover {
      transform: translateY(-2px);
      box-shadow: 0 16px 32px rgba(101, 118, 78, 0.26);
    }

    .horizontal-card {
      display: grid;
      grid-template-columns: 1fr 0.85fr;
      align-items: center;
      gap: 20px;
      text-align: left;
    }

    .horizontal-card.center { text-align: center; }

    .section-title {
      margin: 0 0 10px;
      color: var(--sage-dark);
      letter-spacing: 0.20em;
      text-transform: uppercase;
      font-family: Georgia, "Times New Roman", serif;
      font-size: 22px;
      font-weight: 600;
    }

    .horizontal-card p,
    .message-card p {
      margin: 8px 0;
      font-size: 16px;
      line-height: 1.7;
    }

    .whatsapp-mark {
      width: 74px;
      height: 74px;
      border: 6px solid var(--sage);
      border-radius: 50%;
      margin: 0 auto;
      position: relative;
    }

    .whatsapp-mark::before {
      content: "";
      position: absolute;
      width: 26px;
      height: 13px;
      border-left: 6px solid var(--sage);
      border-bottom: 6px solid var(--sage);
      transform: rotate(-48deg);
      left: 20px;
      top: 24px;
      border-radius: 3px;
    }

    .whatsapp-mark::after {
      content: "";
      position: absolute;
      left: 2px;
      bottom: -7px;
      width: 21px;
      height: 21px;
      background: var(--paper);
      border-left: 6px solid var(--sage);
      border-bottom: 6px solid var(--sage);
      transform: rotate(-20deg);
    }

    .amazon-word {
      font-family: Arial, sans-serif;
      font-size: 44px;
      font-weight: 800;
      color: #111;
      letter-spacing: -2px;
      display: inline-block;
      position: relative;
      margin-bottom: 12px;
    }

    .amazon-word::after {
      content: "";
      position: absolute;
      left: 56px;
      right: 6px;
      bottom: -5px;
      height: 10px;
      border-bottom: 5px solid #f0a22a;
      border-radius: 50%;
      transform: rotate(-5deg);
    }

    .basket {
      width: 150px;
      height: 120px;
      margin: 0 auto;
      position: relative;
    }

    .basket::before {
      content: "";
      position: absolute;
      left: 24px;
      bottom: 0;
      width: 102px;
      height: 70px;
      background: linear-gradient(180deg, #e9dac6, #d8c0a2);
      border: 2px solid #c7ad88;
      border-radius: 12px 12px 20px 20px;
    }

    .basket::after {
      content: "";
      position: absolute;
      left: 38px;
      bottom: 54px;
      width: 76px;
      height: 48px;
      border: 6px solid #c7ad88;
      border-bottom: 0;
      border-radius: 70px 70px 0 0;
    }

    .basket .blanket {
      position: absolute;
      right: 6px;
      bottom: 20px;
      width: 70px;
      height: 58px;
      background: #f7efe2;
      border-radius: 18px;
      transform: rotate(-10deg);
      border: 1px solid #decbb1;
    }

    .message-card {
      width: min(620px, 92%);
      text-align: center;
      padding: 28px 32px;
    }

    .heart {
      width: 20px;
      height: 20px;
      margin: 0 auto 12px;
      background: var(--sage);
      transform: rotate(45deg);
      opacity: .8;
      border-radius: 3px;
    }

    .heart::before,
    .heart::after {
      content: "";
      position: absolute;
      width: 20px;
      height: 20px;
      background: var(--sage);
      border-radius: 50%;
    }

    .heart::before { left: -10px; top: 0; }
    .heart::after { left: 0; top: -10px; }

    .footer {
      margin: 32px -18px 0;
      padding: 22px 18px;
      background: linear-gradient(135deg, #b8c59f, #8d9f70);
      color: white;
      text-align: center;
      letter-spacing: 0.22em;
      text-transform: uppercase;
      font-size: 13px;
      font-weight: 600;
    }

    @media (max-width: 760px) {
      .page { padding: 18px 12px 0; }
      .hero { padding: 34px 16px 24px; border-radius: 28px; }
      .eyebrow { font-size: 11px; letter-spacing: 0.26em; }
      .bunny-envelope { height: 250px; }
      .bunny { transform: translateX(-50%) scale(.84); transform-origin: top center; }
      .envelope { width: 310px; height: 170px; bottom: 12px; }
      .seal { width: 58px; height: 58px; top: 70px; font-size: 32px; }
      .name { letter-spacing: 0.16em; }
      .info-card {
        grid-template-columns: 1fr;
        padding: 24px 18px;
        gap: 18px;
      }
      .info-card > div:not(:last-child) {
        border-right: 0;
        border-bottom: 1px solid rgba(101, 118, 78, 0.16);
        padding-bottom: 18px;
      }
      .horizontal-card {
        grid-template-columns: 1fr;
        text-align: center;
        padding: 24px 18px;
      }
      .message-card { width: 100%; padding: 26px 20px; }
      .main-button { width: 100%; min-width: 0; }
    }
  </style>
</head>
<body>
  <main class="page">
    <section class="hero">
      <p class="eyebrow">Un mensajito especial te espera</p>
      <div class="divider"><span></span></div>

      <div class="bunny-envelope" aria-hidden="true">
        <div class="bunny">
          <div class="ear left"></div>
          <div class="ear right"></div>
          <div class="head"></div>
          <div class="eye left"></div>
          <div class="eye right"></div>
          <div class="nose"></div>
          <div class="paw left"></div>
          <div class="paw right"></div>
        </div>
        <div class="envelope">
          <div class="seal"></div>
        </div>
      </div>

      <h1 class="script">Baby Shower</h1>
      <p class="honor">En honor a</p>
      <h2 class="name">Emilia</h2>
      <div class="divider"><span></span></div>
    </section>

    <section class="info-card">
      <div>
        <div class="mini-bunny" aria-hidden="true">
          <div class="ear left"></div>
          <div class="ear right"></div>
          <div class="head"></div>
          <div class="eye left"></div>
          <div class="eye right"></div>
          <div class="nose"></div>
        </div>
      </div>
      <div>
        <div class="info-icon calendar" aria-hidden="true"></div>
        <span class="label">Domingo</span>
        <span class="big">24</span>
        <span class="small">Mayo 2026</span>
      </div>
      <div>
        <div class="info-icon clock" aria-hidden="true"></div>
        <span class="label">Hora</span>
        <span class="big">12:00</span>
        <span class="small">PM</span>
      </div>
      <div>
        <div class="info-icon pin" aria-hidden="true"></div>
        <span class="label">Lugar</span>
        <span class="small">Río Lerma 76<br>Ciudad de México</span>
      </div>
    </section>

    <div style="text-align:center; margin: 16px auto 24px;">
      <a class="main-button" href="https://www.google.com/maps?q=R%C3%ADo+Lerma+76,+Ciudad+de+M%C3%A9xico" target="_blank" rel="noopener noreferrer">Ver ubicación</a>
    </div>

    <section class="horizontal-card center">
      <div>
        <h3 class="section-title">Confirma tu asistencia</h3>
        <div class="divider"><span></span></div>
        <p>Tu confirmación es muy importante para nosotros.</p>
      </div>
      <div>
        <div class="whatsapp-mark" aria-hidden="true"></div>
        <div style="margin-top:16px;">
          <a class="main-button" href="https://wa.me/5215527746036?text=Hola%2C%20confirmo%20mi%20asistencia%20al%20Baby%20Shower%20de%20Emilia" target="_blank" rel="noopener noreferrer">Confirmar por WhatsApp</a>
        </div>
      </div>
    </section>

    <section class="horizontal-card">
      <div class="basket" aria-hidden="true"><span class="blanket"></span></div>
      <div style="text-align:center;">
        <h3 class="section-title">Mesa de regalos</h3>
        <div class="divider"><span></span></div>
        <p>Si quieres consentir a nuestra bebé, aquí encontrarás opciones que nos serán de gran ayuda.</p>
        <div class="amazon-word">amazon</div>
        <div>
          <a class="main-button" href="https://www.amazon.com.mx/baby-reg/beb-fajardozarate-julio-2026-ciudaddemexico/3949LULADM9OA?ref_=cm_sw_r_cp_ud_dp_YJFHCG5FJC99JAFJX4SQ_1" target="_blank" rel="noopener noreferrer">Ver mesa de regalos</a>
        </div>
      </div>
    </section>

    <section class="message-card">
      <div class="heart" aria-hidden="true"></div>
      <p>Aunque soy una hermosa niña,<br>no soy tan fan de que todo sea color rosita.</p>
      <p>Tonos neutros, verdes, beige y blancos también me encantarán.</p>
      <div class="heart" aria-hidden="true" style="margin-top:18px; transform: rotate(45deg) scale(.75);"></div>
    </section>

    <footer class="footer">Te esperamos para celebrar juntos</footer>
  </main>
</body>
</html>
