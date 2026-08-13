html
<!DOCTYPE html>
<html lang="uk">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">

  <title>SCISSORS — Barber Studio</title>

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
      background: #0b0b0b;
      color: #f5f1e8;
      font-family: Arial, Helvetica, sans-serif;
      overflow-x: hidden;
    }

    a {
      color: inherit;
      text-decoration: none;
    }

    /* HEADER */

    header {
      position: fixed;
      top: 0;
      left: 0;
      right: 0;
      z-index: 1000;

      height: 80px;
      padding: 0 6%;

      display: flex;
      align-items: center;
      justify-content: space-between;

      background: rgba(11, 11, 11, 0.85);
      backdrop-filter: blur(15px);

      border-bottom: 1px solid #222;
    }

    .logo {
      font-size: 24px;
      font-weight: 900;
      letter-spacing: 5px;
    }

    .logo span {
      color: #c9a76a;
    }

    nav {
      display: flex;
      gap: 30px;
    }

    nav a {
      color: #aaa;
      font-size: 12px;
      letter-spacing: 2px;
      text-transform: uppercase;
      transition: 0.3s;
    }

    nav a:hover {
      color: #c9a76a;
    }

    .header-button {
      border: 1px solid #c9a76a;
      color: #c9a76a;
      padding: 12px 18px;
      font-size: 11px;
      letter-spacing: 2px;
      text-transform: uppercase;
      transition: 0.3s;
    }

    .header-button:hover {
      background: #c9a76a;
      color: #0b0b0b;
    }

    /* HERO */

    .hero {
      min-height: 100vh;
      position: relative;

      display: flex;
      align-items: center;

      padding: 140px 8% 100px;

      overflow: hidden;
    }

    .hero-content {
      position: relative;
      z-index: 5;
      max-width: 800px;
    }

    .small-title {
      color: #c9a76a;
      font-size: 12px;
      letter-spacing: 5px;
      text-transform: uppercase;
      margin-bottom: 25px;
    }

    h1 {
      font-size: clamp(70px, 13vw, 170px);
      line-height: 0.8;
      letter-spacing: -8px;
      text-transform: uppercase;
      font-weight: 900;
    }

    h1 span {
      color: transparent;
      -webkit-text-stroke: 1px #f5f1e8;
    }

    .hero-text {
      max-width: 500px;
      margin-top: 40px;

      color: #999;
      font-size: 16px;
      line-height: 1.8;
    }

    .buttons {
      display: flex;
      gap: 15px;
      margin-top: 35px;
    }

    .button {
      display: inline-block;
      padding: 17px 28px;

      text-transform: uppercase;
      letter-spacing: 2px;
      font-size: 11px;

      transition: 0.3s;
    }

    .button.gold {
      background: #c9a76a;
      color: #0b0b0b;
    }

    .button.gold:hover {
      transform: translateY(-4px);
      box-shadow: 0 15px 40px rgba(201, 167, 106, 0.2);
    }

    .button.outline {
      border: 1px solid #444;
      color: #eee;
    }

    .button.outline:hover {
      border-color: #c9a76a;
      color: #c9a76a;
    }

    /* SCISSORS */

    .scissors {
      position: absolute;
      right: 3%;
      top: 50%;

      width: 500px;
      height: 500px;

      transform: translateY(-50%) rotate(-20deg);

      opacity: 0.12;

      animation: scissorsFloat 6s ease-in-out infinite;
    }

    .blade {
      position: absolute;

      width: 350px;
      height: 35px;

      left: 60px;
      top: 230px;

      border-radius: 50px 5px 5px 50px;

      background: linear-gradient(
        90deg,
        #eee,
        #555
      );

      transform-origin: right center;
    }

    .blade-1 {
      transform: rotate(25deg);
    }

    .blade-2 {
      transform: rotate(-25deg);
    }

    .ring {
      position: absolute;

      width: 120px;
      height: 120px;

      right: 15px;

      border: 25px solid #999;
      border-radius: 50%;
    }

    .ring-1 {
      top: 120px;
    }

    .ring-2 {
      top: 275px;
    }

    .center {
      position: absolute;

      width: 38px;
      height: 38px;

      left: 70px;
      top: 230px;

      border-radius: 50%;

      background: #c9a76a;

      box-shadow:
        0 0 30px #c9a76a;
    }

    @keyframes scissorsFloat {
      0% {
        transform: translateY(-50%) rotate(-20deg);
      }

      50% {
        transform: translateY(calc(-50% - 20px)) rotate(-13deg);
      }

      100% {
        transform: translateY(-50%) rotate(-20deg);
      }
    }

    /* MOVING LINE */

    .moving-line {
      width: 100%;
      overflow: hidden;

      border-top: 1px solid #222;
      border-bottom: 1px solid #222;

      padding: 20px 0;

      white-space: nowrap;
    }

    .moving-text {
      display: inline-block;

      color: #c9a76a;

      font-size: 12px;
      letter-spacing: 5px;
      text-transform: uppercase;

      animation: moveText 18s linear infinite;
    }

    @keyframes moveText {
      from {
        transform: translateX(0);
      }

      to {
        transform: translateX(-50%);
      }
    }

    /* GENERAL SECTION */

    section {
      padding: 120px 8%;
    }

    .label {
      color: #c9a76a;
      font-size: 11px;
      letter-spacing: 4px;
      text-transform: uppercase;

      margin-bottom: 20px;
    }

    .title {
      font-size: clamp(50px, 8vw, 100px);
      line-height: 0.9;
      letter-spacing: -5px;
      text-transform: uppercase;

      margin-bottom: 60px;
    }

    /* SERVICES */

    .services {
      display: grid;
      grid-template-columns: 1fr 1fr;

      border-top: 1px solid #292929;
    }

    .service {
      padding: 40px 20px;

      border-bottom: 1px solid #292929;

      transition: 0.3s;
    }

    .service:nth-child(odd) {
      border-right: 1px solid #292929;
    }

    .service:hover {
      background: #111;
    }

    .number {
      color: #555;
      font-size: 12px;
    }

    .service h3 {
      margin-top: 20px;

      font-size: 25px;
      text-transform: uppercase;
    }

    .service p {
      margin-top: 12px;

      color: #777;
      line-height: 1.7;
      max-width: 450px;
    }

    .price {
      margin-top: 20px;

      color: #c9a76a;
      font-size: 20px;
    }


    .service-style {
      color: #c9a76a;
      font-size: 11px;
      letter-spacing: 1px;
      text-transform: uppercase;
    }

    /* ABOUT */

    .about {
      display: grid;
      grid-template-columns: 1fr 1fr;

      gap: 100px;

      align-items: center;
    }

    .about-picture {
      min-height: 500px;

      border: 1px solid #292929;

      display: flex;
      justify-content: center;
      align-items: center;

      overflow: hidden;

      position: relative;
    }

    .big-scissors {
      font-size: 260px;
      opacity: 0.12;

      transform: rotate(-20deg);

      animation: bigScissors 5s ease-in-out infinite;
    }

    @keyframes bigScissors {
      0% {
        transform: rotate(-20deg) scale(1);
      }

      50% {
        transform: rotate(-10deg) scale(1.08);
      }

      100% {
        transform: rotate(-20deg) scale(1);
      }
    }

    .about-text p {
      color: #999;

      line-height: 1.9;

      margin-bottom: 25px;
    }

    /* QUOTE */

    .quote {
      padding: 170px 8%;

      background: #111;

      text-align: center;

      border-top: 1px solid #222;
      border-bottom: 1px solid #222;
    }

    .quote h2 {
      font-size: clamp(40px, 7vw, 90px);

      line-height: 0.9;

      letter-spacing: -4px;

      text-transform: uppercase;
    }

    .quote span {
      color: #c9a76a;
    }

    /* GALLERY */

    .gallery {
      display: grid;

      grid-template-columns: repeat(4, 1fr);

      gap: 15px;
    }

    .gallery-card {
      height: 420px;

      background:
        linear-gradient(
          135deg,
          #202020,
          #0d0d0d
        );

      border: 1px solid #292929;

      display: flex;

      justify-content: center;
      align-items: center;

      transition: 0.5s;
    }

    .gallery-card:hover {
      transform: translateY(-10px);
      border-color: #c9a76a;
    }

    .gallery-card span {
      font-size: 100px;
      opacity: 0.15;
    }


    .gallery-card {
      height: 520px;
      position: relative;
      overflow: hidden;
      background: #111;
      border: 1px solid #292929;
      display: block;
      transition: 0.5s;
    }

    .gallery-card img {
      width: 100%;
      height: 100%;
      display: block;
      object-fit: cover;
      object-position: center;
      filter: grayscale(18%);
      transition: transform 0.6s ease, filter 0.6s ease;
    }

    .gallery-card:hover img {
      transform: scale(1.06);
      filter: grayscale(0%);
    }

    .gallery-card::after {
      content: "";
      position: absolute;
      inset: 45% 0 0;
      background: linear-gradient(transparent, rgba(0,0,0,0.9));
      pointer-events: none;
    }

    .gallery-info {
      position: absolute;
      left: 25px;
      right: 25px;
      bottom: 25px;
      z-index: 2;
    }

    .gallery-info small {
      color: #c9a76a;
      font-size: 10px;
      letter-spacing: 3px;
      text-transform: uppercase;
    }

    .gallery-info h3 {
      margin-top: 8px;
      font-size: 22px;
      text-transform: uppercase;
    }

    .gallery-info p {
      margin-top: 7px;
      color: #bbb;
      font-size: 13px;
      line-height: 1.5;
    }

    /* CONTACT */

    .contact {
      display: grid;

      grid-template-columns: 1fr 1fr;

      gap: 100px;
    }

    .contact-item {
      margin-bottom: 35px;
    }

    .contact-item small {
      color: #666;

      font-size: 10px;

      text-transform: uppercase;

      letter-spacing: 3px;
    }

    .contact-item p {
      margin-top: 10px;

      font-size: 20px;
    }

    form {
      display: flex;

      flex-direction: column;

      gap: 15px;
    }

    input,
    select {
      width: 100%;

      padding: 18px 5px;

      background: transparent;

      border: none;

      border-bottom: 1px solid #333;

      outline: none;

      color: white;

      font-size: 14px;
    }

    input:focus,
    select:focus {
      border-color: #c9a76a;
    }

    select option {
      background: #111;
    }

    button {
      border: none;
      cursor: pointer;
      margin-top: 15px;
    }


    input::placeholder {
      color: #666;
    }

    button:disabled {
      opacity: 0.6;
      cursor: wait;
      transform: none !important;
    }

    /* FOOTER */

    footer {
      padding: 40px 8%;

      border-top: 1px solid #222;

      display: flex;

      justify-content: space-between;

      color: #555;

      font-size: 10px;

      letter-spacing: 2px;

      text-transform: uppercase;
    }


    @media (max-width: 1100px) and (min-width: 801px) {
      .gallery {
        grid-template-columns: repeat(2, 1fr);
      }
    }

    /* MOBILE */

    @media (max-width: 800px) {

      header {
        padding: 0 5%;
      }

      nav {
        display: none;
      }

      .header-button {
        padding: 10px 12px;
      }

      .hero {
        padding: 130px 7% 80px;
      }

      h1 {
        font-size: 75px;
        letter-spacing: -5px;
      }

      .hero-text {
        font-size: 14px;
      }

      .scissors {
        right: -180px;
        width: 400px;
        height: 400px;
        opacity: 0.08;
      }

      section {
        padding: 80px 7%;
      }

      .services {
        grid-template-columns: 1fr;
      }

      .service:nth-child(odd) {
        border-right: none;
      }

      .about {
        grid-template-columns: 1fr;
        gap: 50px;
      }

      .about-picture {
        min-height: 350px;
      }

      .gallery {
        grid-template-columns: 1fr;
      }

      .gallery-card {
        height: 470px;
      }

      .contact {
        grid-template-columns: 1fr;
        gap: 60px;
      }

      footer {
        flex-direction: column;
        gap: 15px;
      }
    }
  </style>
  </head>

<body>

  <!-- HEADER -->

  <header>

    <a href="#" class="logo">
      SCISSORS<span>.</span>
    </a>

    <nav>
      <a href="#services">Послуги</a>
      <a href="#about">Про нас</a>
      <a href="#gallery">Роботи</a>
      <a href="#contact">Запис</a>
    </nav>

    <a href="#contact" class="header-button">
      Записатись
    </a>

  </header>


  <!-- HERO -->

  <section class="hero">

    <div class="hero-content">

      <div class="small-title">
        Barber Studio / 2026
      </div>

      <h1>
        Your<br>
        <span>Style.</span>
      </h1>

      <p class="hero-text">
        Чоловічі стрижки, оформлення бороди та
        класичний барберинг у сучасній атмосфері.
        Твій стиль починається тут.
      </p>

      <div class="buttons">

        <a class="button gold" href="#contact">
          Записатись
        </a>

        <a class="button outline" href="#services">
          Послуги
        </a>

      </div>

    </div>


    <!-- SCISSORS -->

    <div class="scissors">

      <div class="blade blade-1"></div>
      <div class="blade blade-2"></div>

      <div class="ring ring-1"></div>
      <div class="ring ring-2"></div>

      <div class="center"></div>

    </div>

  </section>


  <!-- MOVING TEXT -->

  <div class="moving-line">

    <div class="moving-text">

      ✂ SCISSORS BARBER STUDIO
      &nbsp;&nbsp;&nbsp;
      CUT • SHAVE • STYLE
      &nbsp;&nbsp;&nbsp;
      ✂ SCISSORS BARBER STUDIO
      &nbsp;&nbsp;&nbsp;
      CUT • SHAVE • STYLE
      &nbsp;&nbsp;&nbsp;

    </div>

  </div>


  <!-- SERVICES -->

  <section id="services">

    <div class="label">
      01 / Послуги
    </div>

    <h2 class="title">
      Cut.<br>
      Shave.<br>
      Style.
    </h2>


    <div class="services">

      <div class="service">

        <div class="number">01</div>

        <h3>Classic Haircut</h3>

        <p>
          Класична чоловіча стрижка
          з підбором форми під твоє обличчя.
          <br><br><span class="service-style">Стиль: Textured Crop / Classic Fade</span>
        </p>

        <div class="price">
          €25
        </div>

      </div>


      <div class="service">

        <div class="number">02</div>

        <h3>Hair + Beard</h3>

        <p>
          Стрижка волосся та професійне
          оформлення бороди.
          <br><br><span class="service-style">Стиль: будь-яка стрижка + Beard</span>
        </p>

        <div class="price">
          €35
        </div>

      </div>


      <div class="service">

        <div class="number">03</div>

        <h3>Beard</h3>

        <p>
          Корекція довжини, форми
          та контурів бороди.
          <br><br><span class="service-style">Форма під риси обличчя</span>
        </p>

        <div class="price">
          €18
        </div>

      </div>


      <div class="service">

        <div class="number">04</div>

        <h3>Premium</h3>

        <p>
          Повний комплекс: волосся,
          борода, гарячий рушник
          та фінальний стайлінг.
          <br><br><span class="service-style">Максимум деталей + укладка</span>
        </p>

        <div class="price">
          €45
        </div>

      </div>

    </div>

  </section>


  <!-- ABOUT -->

  <section id="about">

    <div class="about">

      <div class="about-picture">

        <div class="big-scissors">
          ✂
        </div>

      </div>


      <div class="about-text">

        <div class="label">
          02 / Про нас
        </div>

        <h2 class="title">
          More<br>
          than<br>
          a cut.
        </h2>

        <p>
          SCISSORS — це місце для тих,
          хто цінує стиль, якість та деталі.
        </p>

        <p>
          Ми поєднуємо традиційний барберинг
          із сучасними техніками, щоб кожна
          стрижка виглядала саме так,
          як потрібно тобі.
        </p>

      </div>

    </div>

  </section>


  <!-- QUOTE -->

  <div class="quote">

    <h2>
      Sharp scissors.<br>
      <span>Sharp style.</span>
    </h2>

  </div>


  <!-- GALLERY -->

  <section id="gallery">

    <div class="label">
      03 / Наші роботи
    </div>

    <h2 class="title">
      The<br>
      Cuts.
    </h2>


    <div class="gallery">

      <div class="gallery-card">
        <img src="images/01-textured-crop-fade.jpg" alt="Textured Crop + Fade">
        <div class="gallery-info">
          <small>01 / Textured Crop</small>
          <h3>Textured Crop + Fade</h3>
          <p>Текстурований кроп із плавним fade. Чітко, сучасно та легко укладається.</p>
        </div>
      </div>

      <div class="gallery-card">
        <img src="images/02-pink-shag-mullet.jpg" alt="Curly Shag / Mullet">
        <div class="gallery-info">
          <small>02 / Curly Shag</small>
          <h3>Curly Shag / Mullet</h3>
          <p>Об'ємна текстурна стрижка з кучерями та подовженням ззаду.</p>
        </div>
      </div>

      <div class="gallery-card">
        <img src="images/03-blue-flat-top-fade.jpg" alt="Modern Flat Top + Fade">
        <div class="gallery-info">
          <small>03 / Flat Top</small>
          <h3>Modern Flat Top + Fade</h3>
          <p>Високий flat top із геометричною формою та контрастним fade.</p>
        </div>
      </div>

      <div class="gallery-card">
        <img src="images/04-classic-textured-fade.jpg" alt="Classic Textured Fade">
        <div class="gallery-info">
          <small>04 / Classic Fade</small>
          <h3>Classic Textured Fade</h3>
          <p>Класична текстурована форма з акуратним fade та природним верхом.</p>
        </div>
      </div>

    </div>

  </section>


  <!-- CONTACT -->

  <section id="contact">

    <div class="label">
      04 / Запис
    </div>

    <h2 class="title">
      Book<br>
      your cut.
    </h2>


    <div class="contact">


      <div>

        <div class="contact-item">

          <small>Адреса</small>

          <p>
            Ваша адреса
          </p>

        </div>


        <div class="contact-item">

          <small>Телефон</small>

          <p>
            +380 00 000 00 00
          </p>

        </div>


        <div class="contact-item">

          <small>Години роботи</small>

          <p>
            Пн–Пт: 09:00 — 20:00<br>
            Сб–Нд: 10:00 — 18:00
          </p>

        </div>

      </div>
      <form
        id="bookingForm"
        action="https://formspree.io/f/xnpavyge"
        method="POST"
      >
        <input type="hidden" name="_subject" value="Нова заявка на стрижку — SCISSORS BARBER STUDIO">
        <input type="text" name="name" placeholder="Ваше ім'я" required>
        <input type="tel" name="phone" placeholder="Номер телефону" required>
        <input type="email" name="email" placeholder="Ваш Email" required>

        <select name="service" required>
          <option value="">Оберіть послугу</option>
          <option value="Classic Haircut — €25">Classic Haircut — €25</option>
          <option value="Hair + Beard — €35">Hair + Beard — €35</option>
          <option value="Beard — €18">Beard — €18</option>
          <option value="Premium — €45">Premium — €45</option>
        </select>

        <input type="date" name="date" required>

        <button
          type="submit"
          class="button gold"
        >
          Відправити заявку ✂
        </button>
      </form>

    </div>

  </section>


  <!-- FOOTER -->

  <footer>

    <div>
      © 2026 SCISSORS BARBER STUDIO
    </div>

    <div>
      Cut with character.
    </div>

  </footer>

  <script>
    const form = document.getElementById("bookingForm");

    form.addEventListener("submit", async function (event) {
      event.preventDefault();

      const button = form.querySelector("button");
      const originalText = button.textContent;

      button.disabled = true;
      button.textContent = "ВІДПРАВЛЯЄМО...";

      try {
        const response = await fetch(form.action, {
          method: "POST",
          body: new FormData(form),
          headers: {
            "Accept": "application/json"
          }
        });

        if (response.ok) {
          alert(
            "✂ Дякуємо за заявку!

" +
            "Заявка успішно відправлена. Ми зв'яжемося з вами найближчим часом."
          );
          form.reset();
        } else {
          alert(
            "Не вдалося відправити заявку.

" +
            "Спробуйте ще раз або зв'яжіться з нами телефоном."
          );
        }
      } catch (error) {
        alert(
          "Помилка з'єднання.

" +
          "Перевірте інтернет і спробуйте ще раз."
        );
      } finally {
        button.disabled = false;
        button.textContent = originalText;
      }
    });
  </script>
