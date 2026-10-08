<!doctype html>
<html lang="ru">
<head>
  <meta charset="utf-8">
  <meta name="viewport" content="width=device-width, initial-scale=1">
  <title>Grass — движение к лучшей версии себя</title>
  <style>
    :root {
      --green: #159b57;
      --green-dark: #087b43;
      --mint: #e9f7ee;
      --ink: #111827;
      --muted: #667085;
      --line: #e7eee9;
      --navy: #0c111d;
      --radius: 18px;
      --shadow: 0 14px 40px rgba(15, 50, 30, .08);
    }

    * { box-sizing: border-box; }
    html { scroll-behavior: smooth; }
    body {
      margin: 0;
      color: var(--ink);
      background: #fff;
      font-family: Inter, ui-sans-serif, system-ui, -apple-system, "Segoe UI", sans-serif;
    }
    a { color: inherit; text-decoration: none; }
    .wrap { width: min(1120px, calc(100% - 40px)); margin-inline: auto; }

    header {
      position: sticky;
      top: 0;
      z-index: 10;
      height: 72px;
      border-bottom: 1px solid #edf1ee;
      background: rgba(255,255,255,.94);
      backdrop-filter: blur(12px);
    }
    .nav {
      display: flex;
      align-items: center;
      justify-content: space-between;
      gap: 24px;
      height: 100%;
    }
    .brand {
      display: flex;
      align-items: center;
      gap: 9px;
      font-size: 19px;
      font-weight: 800;
      letter-spacing: -.04em;
    }
    .brand-mark {
      display: grid;
      width: 29px;
      height: 29px;
      place-items: center;
      border-radius: 10px 10px 10px 3px;
      background: var(--green);
      color: #fff;
      font-size: 17px;
    }
    .navlinks { display: flex; gap: 29px; color: #475467; font-size: 13px; }
    .navlinks a:hover { color: var(--green); }
    .nav-cta, .button {
      display: inline-flex;
      align-items: center;
      justify-content: center;
      gap: 8px;
      padding: 12px 18px;
      border-radius: 999px;
      background: var(--green);
      color: #fff;
      font-size: 13px;
      font-weight: 700;
      transition: .2s;
    }
    .nav-cta:hover, .button:hover {
      transform: translateY(-1px);
      background: var(--green-dark);
    }
    .menu { display: none; border: 0; background: transparent; font-size: 24px; }

    .hero { overflow: hidden; background: #f1faf4; }
    .hero-grid {
      display: grid;
      min-height: 430px;
      grid-template-columns: 1fr .93fr;
      align-items: center;
      gap: 24px;
    }
    .hero-copy { padding: 54px 0; }
    .eyebrow {
      display: inline-flex;
      align-items: center;
      gap: 8px;
      padding: 8px 12px;
      border-radius: 999px;
      background: #e0f3e7;
      color: var(--green-dark);
      font-size: 11px;
      font-weight: 750;
      letter-spacing: .04em;
      text-transform: uppercase;
    }
    .eyebrow i {
      width: 7px;
      height: 7px;
      border-radius: 50%;
      background: var(--green);
    }
    h1 {
      max-width: 540px;
      margin: 20px 0 16px;
      font-size: clamp(38px, 5vw, 59px);
      line-height: .99;
      letter-spacing: -.055em;
    }
    h1 span { color: var(--green); }
    .lead {
      max-width: 425px;
      margin: 0 0 24px;
      color: #52615a;
      font-size: 15px;
      line-height: 1.65;
    }
    .hero-actions { display: flex; align-items: center; gap: 18px; flex-wrap: wrap; }
    .text-link { color: #344054; font-size: 13px; font-weight: 700; }
    .text-link span { margin-left: 5px; color: var(--green); }
    .hero-photo {
      position: relative;
      align-self: end;
      height: 376px;
      overflow: hidden;
      border-radius: 170px 170px 22px 22px;
      background: linear-gradient(145deg, #cfe9d7, #96cba8 54%, #397b55);
      box-shadow: var(--shadow);
    }
    .hero-photo img {
      display: block;
      width: 100%;
      height: 100%;
      object-fit: cover;
      object-position: center 36%;
    }
    .photo-badge {
      position: absolute;
      bottom: 30px;
      left: -16px;
      padding: 12px 16px;
      border-radius: 14px;
      background: #fff;
      box-shadow: var(--shadow);
      font-size: 12px;
      font-weight: 750;
    }
    .photo-badge b { margin-right: 4px; color: var(--green); font-size: 20px; }

    .proof { position: relative; margin-top: -1px; }
    .proof-row {
      display: grid;
      grid-template-columns: repeat(4, 1fr);
      padding: 20px 10px;
      border: 1px solid var(--line);
      border-radius: 16px;
      background: #fff;
      box-shadow: var(--shadow);
    }
    .proof-item {
      display: flex;
      align-items: center;
      justify-content: center;
      gap: 10px;
      padding: 0 10px;
      border-right: 1px solid var(--line);
    }
    .proof-item:last-child { border: 0; }
    .proof-icon, .icon {
      display: grid;
      place-items: center;
      background: var(--mint);
      color: var(--green);
    }
    .proof-icon { width: 37px; height: 37px; border-radius: 12px; font-size: 18px; }
    .proof-item strong { display: block; font-size: 14px; }
    .proof-item small { display: block; margin-top: 3px; color: var(--muted); font-size: 10px; }

    section { padding: 76px 0; }
    .section-head { max-width: 590px; margin: 0 auto 32px; text-align: center; }
    .section-head .eyebrow { margin-bottom: 12px; }
    h2 {
      margin: 0 0 11px;
      font-size: clamp(27px, 3.5vw, 38px);
      line-height: 1.08;
      letter-spacing: -.045em;
    }
    .section-head p { margin: 0; color: var(--muted); font-size: 14px; line-height: 1.6; }
    .cards { display: grid; grid-template-columns: repeat(3, 1fr); gap: 18px; }
    .card {
      padding: 23px;
      border: 1px solid var(--line);
      border-radius: var(--radius);
      background: #fff;
      transition: .2s;
    }
    .card:hover { transform: translateY(-4px); box-shadow: var(--shadow); }
    .card:nth-child(2) { background: #f5fbf6; }
    .icon { width: 46px; height: 46px; margin-bottom: 18px; border-radius: 14px; font-size: 23px; }
    .card h3 { margin: 0 0 8px; font-size: 17px; }
    .card p { margin: 0 0 14px; color: var(--muted); font-size: 12px; line-height: 1.65; }
    .card a { color: var(--green-dark); font-size: 11px; font-weight: 750; }

    .about { background: #f7faf8; }
    .about-grid {
      display: grid;
      grid-template-columns: .9fr 1.1fr;
      align-items: center;
      gap: 54px;
    }
    .about-art {
      position: relative;
      display: grid;
      min-height: 310px;
      place-items: center;
      overflow: hidden;
      border-radius: 24px;
      background: radial-gradient(circle at 68% 36%, #e6f6e8 0 13%, transparent 14%), linear-gradient(135deg, #eaf7ed, #c3e3cc);
    }
    .about-art::before, .about-art::after {
      position: absolute;
      width: 280px;
      height: 280px;
      border: 1px solid rgba(21,155,87,.18);
      border-radius: 50%;
      content: "";
    }
    .about-art::after { width: 210px; height: 210px; }
    .leaf { z-index: 1; color: var(--green); font-size: 104px; transform: rotate(-24deg); }
    .about-copy p { color: var(--muted); font-size: 14px; line-height: 1.75; }
    .ticks { display: grid; grid-template-columns: 1fr 1fr; gap: 12px; margin-top: 20px; }
    .ticks span { font-size: 12px; font-weight: 650; }
    .ticks b { margin-right: 7px; color: var(--green); }

    .cta-band { padding: 46px 0; }
    .cta-inner {
      display: flex;
      align-items: center;
      justify-content: space-between;
      gap: 24px;
      padding: 36px 42px;
      border-radius: 24px;
      background: var(--green);
      color: #fff;
    }
    .cta-inner h2 { max-width: 470px; font-size: 30px; }
    .cta-inner p { margin: 8px 0 0; color: #e5f6eb; font-size: 13px; }
    .button-light { background: #fff; color: var(--green-dark); }
    .button-light:hover { background: #f1fff5; }

    .footer { padding: 34px 0 22px; background: var(--navy); color: #fff; }
    .footer-top {
      display: flex;
      align-items: center;
      justify-content: space-between;
      gap: 20px;
      padding-bottom: 25px;
      border-bottom: 1px solid #263040;
    }
    .footer .brand-mark { background: #173d2a; }
    .footer-note { max-width: 340px; color: #a6afbd; font-size: 11px; }
    .footer-links { display: flex; gap: 22px; color: #c8ced8; font-size: 11px; }
    .copyright {
      display: flex;
      justify-content: space-between;
      padding-top: 16px;
      color: #8791a1;
      font-size: 10px;
    }

    @media (max-width: 760px) {
      .wrap { width: min(100% - 32px, 560px); }
      header { height: 64px; }
      .navlinks {
        position: absolute;
        top: 63px;
        right: 0;
        left: 0;
        display: none;
        flex-direction: column;
        gap: 17px;
        padding: 18px 22px;
        background: #fff;
        box-shadow: var(--shadow);
      }
      .navlinks.open { display: flex; }
      .menu { display: block; }
      .nav-cta { margin-left: auto; padding: 10px 14px; font-size: 11px; }
      .hero-grid { grid-template-columns: 1fr; gap: 0; }
      .hero-copy { padding: 42px 0 18px; }
      .hero-photo {
        width: min(100%, 410px);
        height: 310px;
        justify-self: center;
        align-self: auto;
        border-radius: 145px 145px 18px 18px;
      }
      .photo-badge { left: 7px; }
      .proof { margin-top: 18px; }
      .proof-row { grid-template-columns: 1fr 1fr; row-gap: 17px; padding: 16px 8px; }
      .proof-item { justify-content: flex-start; padding-left: 12px; }
      .proof-item:nth-child(2) { border: 0; }
      .proof-item strong { font-size: 12px; }
      .proof-item small { font-size: 9px; }
      section { padding: 58px 0; }
      .cards { grid-template-columns: 1fr; gap: 12px; }
      .card { padding: 20px; }
      .icon { margin-bottom: 13px; }
      .about-grid { grid-template-columns: 1fr; gap: 25px; }
      .about-art { min-height: 230px; }
      .cta-band { padding: 30px 0; }
      .cta-inner { align-items: flex-start; flex-direction: column; padding: 27px 23px; }
      .cta-inner h2 { font-size: 26px; }
      .footer-top { align-items: flex-start; flex-direction: column; }
      .footer-links { flex-wrap: wrap; gap: 14px; }
      .copyright { flex-direction: column; gap: 12px; }
    }
    @media (min-width: 761px) and (max-width: 980px) {
      .hero-grid { min-height: 390px; }
      .hero-photo { height: 335px; }
      .proof-item { gap: 7px; }
      .proof-icon { width: 32px; height: 32px; }
      .about-grid { gap: 30px; }
    }
  </style>
</head>
<body>
  <header>
    <div class="wrap nav">
      <a class="brand" href="#top" aria-label="Grass — главная"><span class="brand-mark">✳</span>Grass</a>
      <nav class="navlinks" id="navlinks">
        <a href="#programs">Программы</a>
        <a href="#about">О нас</a>
        <a href="#benefits">Преимущества</a>
        <a href="#contacts">Контакты</a>
      </nav>
      <a class="nav-cta" href="https://wa.me/996507588832" target="_blank" rel="noopener">Написать нам ↗</a>
      <button class="menu" id="menu" aria-label="Открыть меню" aria-expanded="false">☰</button>
    </div>
  </header>

  <main id="top">
    <section class="hero">
      <div class="wrap hero-grid">
        <div class="hero-copy">
          <div class="eyebrow"><i></i>Тренируйся в своём ритме</div>
          <h1>Здоровое тело —<br><span>счастливая жизнь</span></h1>
          <p class="lead">Простые тренировки, приятные привычки и поддержка каждый день. Начни с малого — почувствуй разницу.</p>
          <div class="hero-actions">
            <a class="button" href="https://wa.me/996507588832" target="_blank" rel="noopener">Начать сейчас ↗</a>
            <a class="text-link" href="#programs">Выбрать программу <span>→</span></a>
          </div>
        </div>
        <div class="hero-photo">
          <img src="https://images.unsplash.com/photo-1518611012118-696072aa579a?auto=format&fit=crop&w=1000&q=85" alt="Девушка занимается растяжкой" onerror="this.style.display='none'">
          <div class="photo-badge"><b>710 × 440</b> минут заботы о себе</div>
        </div>
      </div>
    </section>

    <div class="wrap proof" id="benefits">
      <div class="proof-row">
        <div class="proof-item"><span class="proof-icon">♧</span><div><strong>Йога</strong><small>Баланс и гибкость</small></div></div>
        <div class="proof-item"><span class="proof-icon">◉</span><div><strong>Силовая тренировка</strong><small>Энергия и сила</small></div></div>
        <div class="proof-item"><span class="proof-icon">♡</span><div><strong>Кардио</strong><small>Здоровье сердца</small></div></div>
        <div class="proof-item"><span class="proof-icon">✦</span><div><strong>Поддержка</strong><small>На каждом этапе</small></div></div>
      </div>
    </div>

    <section id="programs">
      <div class="wrap">
        <div class="section-head">
          <div class="eyebrow"><i></i>Найди своё</div>
          <h2>Выберите занятие<br>по настроению</h2>
          <p>Для каждого уровня и любой цели — программа, которая помогает двигаться вперёд с удовольствием.</p>
        </div>
        <div class="cards">
          <article class="card"><div class="icon">♧</div><h3>Йога</h3><p>Гибкость, баланс и спокойствие. Практика, которая возвращает лёгкость телу.</p><a href="https://wa.me/996507588832" target="_blank" rel="noopener">Подобрать занятие →</a></article>
          <article class="card"><div class="icon">◌</div><h3>Силовая тренировка</h3><p>Укрепляй мышцы и открывай новые возможности в комфортном темпе.</p><a href="https://wa.me/996507588832" target="_blank" rel="noopener">Подобрать занятие →</a></article>
          <article class="card"><div class="icon">♡</div><h3>Кардио</h3><p>Больше энергии, выносливости и хорошего настроения с каждой тренировкой.</p><a href="https://wa.me/996507588832" target="_blank" rel="noopener">Подобрать занятие →</a></article>
        </div>
      </div>
    </section>

    <section class="about" id="about">
      <div class="wrap about-grid">
        <div class="about-art" aria-hidden="true"><span class="leaf">❧</span></div>
        <div class="about-copy">
          <div class="eyebrow"><i></i>О Grass</div>
          <h2>Забота о себе —<br>это привычка</h2>
          <p>Grass помогает сделать движение естественной частью жизни. Выбирай занятие под своё настроение, занимайся в удобном темпе и отмечай каждый маленький шаг.</p>
          <div class="ticks">
            <span><b>✓</b>Подходит новичкам</span><span><b>✓</b>Гибкий график</span>
            <span><b>✓</b>Понятные программы</span><span><b>✓</b>Поддержка тренера</span>
          </div>
        </div>
      </div>
    </section>

    <section class="cta-band" id="contacts">
      <div class="wrap cta-inner">
        <div><h2>Готовы начать заботиться о себе?</h2><p>Напишите нам — поможем выбрать подходящую тренировку.</p></div>
        <a class="button button-light" href="https://wa.me/996507588832" target="_blank" rel="noopener">Связаться в WhatsApp ↗</a>
      </div>
    </section>
  </main>

  <footer class="footer">
    <div class="wrap">
      <div class="footer-top">
        <div><a class="brand" href="#top"><span class="brand-mark">✳</span>Grass</a><p class="footer-note">Простые тренировки, приятные привычки и поддержка каждый день.</p></div>
        <nav class="footer-links"><a href="#programs">Программы</a><a href="#about">О нас</a><a href="#benefits">Преимущества</a><a href="https://wa.me/996507588832" target="_blank" rel="noopener">WhatsApp</a></nav>
      </div>
      <div class="copyright"><span>© 2026 Grass. Все права защищены.</span><span>Двигайся с удовольствием 🌱</span></div>
    </div>
  </footer>

  <script>
    const menu = document.getElementById("menu");
    const links = document.getElementById("navlinks");

    menu.addEventListener("click", () => {
      const isOpen = links.classList.toggle("open");
      menu.setAttribute("aria-expanded", isOpen);
      menu.textContent = isOpen ? "×" : "☰";
    });

    links.querySelectorAll("a").forEach(link => {
      link.addEventListener("click", () => {
        links.classList.remove("open");
        menu.setAttribute("aria-expanded", "false");
        menu.textContent = "☰";
      });
    });
  </script>
</body>
</html>
