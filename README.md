```html
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
      background: #080808;
      color: #f4f0e8;
      font-family: Arial, Helvetica, sans-serif;
      overflow-x: hidden;
    }

    a {
      text-decoration: none;
      color: inherit;
    }

    /* ================= HEADER ================= */

    header {
      position: fixed;
      top: 0;
      left: 0;
      right: 0;
      height: 82px;

      padding: 0 6%;

      display: flex;
      align-items: center;
      justify-content: space-between;

      z-index: 1000;

      background: rgba(8, 8, 8, .75);
      backdrop-filter: blur(18px);

      border-bottom: 1px solid rgba(255,255,255,.08);
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
      font-size: 11px;
      letter-spacing: 2px;
      text-transform: uppercase;
      transition: .3s;
    }

    nav a:hover {
      color: #c9a76a;
    }

    .book {
      border: 1px solid #c9a76a;
      color: #c9a76a;

      padding: 12px 20px;

      font-size: 10px;
      letter-spacing: 2px;
      text-transform: uppercase;

      transition: .3s;
    }

    .book:hover {
      background: #c9a76a;
      color: #080808;
    }

    /* ================= HERO ================= */

    .hero {
      min-height: 100vh;

      position: relative;

      display: flex;
      align-items: center;

      padding: 150px 8% 100px;

      overflow: hidden;

      background:
        linear-gradient(
          90deg,
          rgba(8,8,8,.98) 0%,
          rgba(8,8,8,.85) 38%,
          rgba(8,8,8,.35) 75%,
          rgba(8,8,8,.75) 100%
        ),
        url("https://images.pexels.com/photos/4969866/pexels-photo-4969866.jpeg?auto=compress&cs=tinysrgb&w=1800")
        center/cover no-repeat;
    }

    .hero::after {
      content: "";

      position: absolute;
      inset: 0;

      background:
        linear-gradient(
          transparent 60%,
          #080808 100%
        );

      pointer-events: none;
    }

    .hero-content {
      position: relative;
      z-index: 5;

      max-width: 850px;
    }

    .eyebrow {
      color: #c9a76a;

      font-size: 11px;
      letter-spacing: 5px;
      text-transform: uppercase;

      margin-bottom: 25px;

      animation: fadeUp 1s ease forwards;
    }

    h1 {
      font-size: clamp(70px, 13vw, 175px);

      line-height: .78;

      letter-spacing: -9px;

      text-transform: uppercase;

      font-weight: 900;

      animation: fadeUp 1s .1s ease both;
    }

    h1 span {
      color: transparent;

      -webkit-text-stroke: 1px #f4f0e8;
    }

    .hero-description {
      max-width: 510px;

      margin-top: 45px;

      color: #aaa;

      font-size: 16px;

      line-height: 1.8;

      animation: fadeUp 1s .2s ease both;
    }

    .hero-buttons {
      display: flex;
      gap: 15px;

      margin-top: 35px;

      animation: fadeUp 1s .3s ease both;
    }

    .button {
      display: inline-block;

      padding: 17px 30px;

      font-size: 10px;

      letter-spacing: 2px;

      text-transform: uppercase;

      transition: .3s;
    }

    .button.gold {
      background: #c9a76a;
      color: #080808;
    }

    .button.gold:hover {
      transform: translateY(-4px);

      box-shadow:
        0 15px 40px rgba(201,167,106,.25);
    }

    .button.outline {
      border: 1px solid #555;
      color: #eee;
    }

    .button.outline:hover {
      border-color: #c9a76a;
      color: #c9a76a;
    }

    /* ================= SCISSORS ================= */

    .scissors {
      position: absolute;

      right: 4%;
      top: 48%;

      width: 470px;
      height: 470px;

      z-index: 3;

      opacity: .18;

      transform:
        translateY(-50%)
        rotate(-18deg);

      animation: scissorsMove 6s ease-in-out infinite;
    }

    .blade {
      position: absolute;

      width: 330px;
      height: 32px;

      left: 50px;
      top: 220px;

      border-radius: 50px;

      background:
        linear-gradient(
          90deg,
          #fff,
          #777,
          #222
        );

      transform-origin: right center;
    }

    .blade.one {
      transform: rotate(25deg);
    }

    .blade.two {
      transform: rotate(-25deg);
    }

    .ring {
      position: absolute;

      width: 115px;
      height: 115px;

      border-radius: 50%;

      border: 23px solid #aaa;

      right: 5px;
    }

    .ring.one {
      top: 105px;
    }

    .ring.two {
      top: 260px;
    }

    .pivot {
      position: absolute;

      width: 38px;
      height: 38px;

      border-radius: 50%;

      background: #c9a76a;

      left: 65px;
      top: 220px;

      box-shadow:
        0 0 40px #c9a76a;
    }

    @keyframes scissorsMove {
      0%,100% {
        transform:
          translateY(-50%)
          rotate(-18deg);
      }

      50% {
        transform:
          translateY(calc(-50% - 20px))
          rotate(-10deg);
      }
    }

    /* ================= MARQUEE ================= */

    .marquee {
      overflow: hidden;

      padding: 20px 0;

      border-top: 1px solid #222;
      border-bottom: 1px solid #222;

      white-space: nowrap;
    }

    .marquee-text {
      display: inline-block;

      color: #c9a76a;

      font-size: 11px;

      letter-spacing: 6px;

      text-transform: uppercase;

      animation: marquee 20s linear infinite;
    }

    @keyframes marquee {
      from {
        transform: translateX(0);
      }

      to {
        transform: translateX(-50%);
      }
    }

    /* ================= SECTIONS ================= */

    section {
      padding: 120px 8%;
    }

    .label {
      color: #c9a76a;

      font-size: 10px;

      letter-spacing: 4px;

      text-transform: uppercase;

      margin-bottom: 20px;
    }

    .section-title {
      font-size: clamp(50px, 8vw, 100px);

      line-height: .85;

      letter-spacing: -5px;

      text-transform: uppercase;

      margin-bottom: 65px;
    }

    /* ================= SERVICES ================= */

    .services {
      display: grid;

      grid-template-columns: 1fr 1fr;

      border-top: 1px solid #292929;
    }

    .service {
      padding: 40px 20px;

      border-bottom: 1px solid #292929;

      transition: .4s;
    }

    .service:nth-child(odd) {
      border-right: 1px solid #292929;
    }

    .service:hover {
      background: #111;
    }

    .service-number {
      color: #555;

      font-size: 11px;
    }

    .service h3 {
      margin-top: 20px;

      font-size: 25px;

      text-transform: uppercase;
    }

    .service p {
      max-width: 470px;

      margin-top: 12px;

      color: #777;

      line-height: 1.7;
    }

    .price {
      margin-top: 20px;

      color: #c9a76a;

      font-size: 20px;
    }

    /* ================= ABOUT ================= */

    .about {
      display: grid;

      grid-template-columns: 1fr 1fr;

      gap: 90px;

      align-items: center;
    }

    .about-image {
      height: 620px;

      position: relative;

      overflow: hidden;

      border: 1px solid #292929;
    }

    .about-image img {
      width: 100%;
      height: 100%;

      object-fit: cover;

      transition: 1s;
    }

    .about-image:hover img {
      transform: scale(1.05);
    }

    .about-image::after {
      content: "";

      position: absolute;

      inset: 0;

      background:
        linear-gradient(
          180deg,
          transparent,
          rgba(0,0,0,.65)
        );
    }

    .about-text p {
      color: #999;

      line-height: 1.9;

      margin-bottom: 25px;

      font-size: 15px;
    }

    .signature {
      margin-top: 35px;

      color: #c9a76a;

      font-style: italic;

      font-size: 20px;
    }

    /* ================= QUOTE ================= */

    .quote {
      padding: 180px 8%;

      background: #111;

      text-align: center;

      border-top: 1px solid #222;
      border-bottom: 1px solid #222;
    }

    .quote h2 {
      font-size: clamp(45px, 7vw, 95px);

      line-height: .85;

      letter-spacing: -5px;

      text-transform: uppercase;
    }

    .quote span {
      color: #c9a76a;
    }

    /* ================= GALLERY ================= */

    .gallery {
      display: grid;

      grid-template-columns:
        1fr
        1fr
        1fr;

      gap: 15px;
    }

    .gallery-card {
      height: 480px;

      position: relative;

      overflow: hidden;

      background: #111;

      border: 1px solid #292929;
    }

    .gallery-card:nth-child(2) {
      transform: translateY(70px);
    }

    .gallery-card img {
      width: 100%;
      height: 100%;

      object-fit: cover;

      transition:
        transform .7s,
        filter .7s;

      filter: brightness(.65);
    }

    .gallery-card:hover img {
      transform: scale(1.08);

      filter: brightness(.9);
    }

    .gallery-overlay {
      position: absolute;

      left: 25px;
      bottom: 25px;

      z-index: 2;

      color: white;

      font-size: 11px;

      letter-spacing: 3px;

      text-transform: uppercase;
    }

    /* ================= BOOKING ================= */

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

      letter-spacing: 3px;

      text-transform: uppercase;
    }

    .contact-item p {
      margin-top: 10px;

      font-size: 19px;
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

    /* ================= FOOTER ================= */

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

    /* ================= ANIMATION ================= */

    @keyframes fadeUp {
      from {
        opacity: 0;

        transform:
          translateY(30px);
      }

      to {
        opacity: 1;

        transform:
          translateY(0);
      }
    }

    /* ================= MOBILE ================= */

    @media (max-width: 800px) {

      header {
        height: 70px;

        padding: 0 5%;
      }

      nav {
        display: none;
      }

      .logo {
        font-size: 20px;
      }

      .book {
        padding: 10px 12px;
      }

      .hero {
        padding:
          130px
          7%
          100px;

        background-position: 65% center;
      }

      h1 {
        font-size: 75px;

        letter-spacing: -5px;
      }

      .hero-description {
        font-size: 14px;
      }

      .scissors {
        width: 330px;
        height: 330px;

        right: -150px;

        opacity: .1;
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

      .about-image {
        height: 450px;
      }

      .gallery {
        grid-template-columns: 1fr;
      }

      .gallery-card {
        height: 450px;
      }

      .gallery-card:nth-child(2) {
        transform: none;
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


  <!-- ================= HEADER ================= -->

  <header>

    <a href="#" class="logo">
      SCISSORS<span>.</span>
    </a>

    <nav>

      <a href="#services">
        Послуги
      </a>

      <a href="#about">
        Про нас
      </a>

      <a href="#gallery">
        Роботи
      </a>

      <a href="#contact">
        Запис
      </a>

    </nav>

    <a href="#contact" class="book">
      Записатись
    </a>

  </header>


  <!-- ================= HERO ================= -->

  <section class="hero">

    <div class="hero-content">

      <div class="eyebrow">
        Barber Studio / 2026
      </div>

      <h1>
        Your<br>
        <span>Style.</span>
      </h1>

      <p class="hero-description">
        Чоловічі стрижки, оформлення бороди
        та класичний барберинг у сучасній
        атмосфері.
      </p>

      <div class="hero-buttons">

        <a
          href="#contact"
          class="button gold"
        >
          Записатись
        </a>

        <a
          href="#services"
          class="button outline"
        >
          Послуги
        </a>

      </div>

    </div>


    <!-- ANIMATED SCISSORS -->

    <div class="scissors">

      <div class="blade one"></div>
      <div class="blade two"></div>

      <div class="ring one"></div>
      <div class="ring two"></div>

      <div class="pivot"></div>

    </div>

  </section>


  <!-- ================= MARQUEE ================= -->

  <div class="marquee">

    <div class="marquee-text">

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


  <!-- ================= SERVICES ================= -->

  <section id="services">

    <div class="label">
      01 / Послуги
    </div>

    <h2 class="section-title">
      Cut.<br>
      Shave.<br>
      Style.
    </h2>


    <div class="services">

      <div class="service">

        <div class="service-number">
          01
        </div>

        <h3>
          Classic Haircut
        </h3>

        <p>
          Класична чоловіча стрижка
          з підбором форми під твоє
          обличчя та стиль.
        </p>

        <div class="price">
          €25
        </div>

      </div>


      <div class="service">

        <div class="service-number">
          02
        </div>

        <h3>
          Hair + Beard
        </h3>

        <p>
          Стрижка волосся та професійне
          оформлення бороди.
        </p>

        <div class="price">
          €35
        </div>

      </div>


      <div class="service">

        <div class="service-number">
          03
        </div>

        <h3>
          Beard
        </h3>

        <p>
          Корекція форми, довжини
          та контурів бороди.
        </p>

        <div class="price">
          €18
        </div>

      </div>


      <div class="service">

        <div class="service-number">
          04
        </div>

        <h3>
          Premium
        </h3>

        <p>
          Повний комплекс: волосся,
          борода, гарячий рушник
          та фінальний стайлінг.
        </p>

        <div class="price">
          €45
        </div>

      </div>

    </div>

  </section>


  <!-- ================= ABOUT ================= -->

  <section id="about">

    <div class="about">

      <div class="about-image">

        <img
          src="https://images.pexels.com/photos/5188621/pexels-photo-5188621.jpeg?auto=compress&cs=tinysrgb&w=1400"
          alt="Barber with scissors"
        >

      </div>


      <div class="about-text">

        <div class="label">
          02 / Про нас
        </div>

        <h2 class="section-title">
          More<br>
          than<br>
          a cut.
        </h2>

        <p>
          SCISSORS — це місце для тих,
          хто цінує стиль, якість
          та увагу до деталей.
        </p>

        <p>
          Ми поєднуємо традиційний
          барберинг із сучасними
          техніками, щоб кожна
          стрижка виглядала саме так,
          як потрібно тобі.
        </p>

        <div class="signature">
          — Your barber
        </div>

      </div>

    </div>

  </section>


  <!-- ================= QUOTE ================= -->

  <div class="quote">

    <h2>

      Sharp scissors.<br>

      <span>
        Sharp style.
      </span>

    </h2>

  </div>


  <!-- ================= GALLERY ================= -->

  <section id="gallery">

    <div class="label">
      03 / Наші роботи
    </div>

    <h2 class="section-title">
      The<br>
      Cuts.
    </h2>


    <div class="gallery">


      <div class="gallery-card">

        <img
          src="https://images.pexels.com/photos/4969866/pexels-photo-4969866.jpeg?auto=compress&cs=tinysrgb&w=1200"
          alt="Barber haircut"
        >

        <div class="gallery-overlay">
          Scissor Cut
        </div>

      </div>


      <div class="gallery-card">

        <img
          src="https://images.pexels.com/photos/8552631/pexels-photo-8552631.jpeg?auto=compress&cs=tinysrgb&w=1200"
          alt="Barber scissors"
        >

        <div class="gallery-overlay">
          Detail
        </div>

      </div>


      <div class="gallery-card">

        <img
          src="https://images.pexels.com/photos/5188621/pexels-photo-5188621.jpeg?auto=compress&cs=tinysrgb&w=1200"
          alt="Barber"
        >

        <div class="gallery-overlay">
          Precision
        </div>

      </div>


    </div>

  </section>


  <!-- ================= BOOKING ================= -->

  <section id="contact">

    <div class="label">
      04 / Запис
    </div>

    <h2 class="section-title">
      Book<br>
      your cut.
    </h2>


    <div class="contact">


      <div>

        <div class="contact-item">

          <small>
            Адреса
          </small>

          <p>
            Ваша адреса
          </p>

        </div>


        <div class="contact-item">

          <small>
            Телефон
          </small>

          <p>
            +380 00 000 00 00
          </p>

        </div>


        <div class="contact-item">

          <small>
            Години роботи
          </small>

          <p>
            Пн–Пт: 09:00 — 20:00<br>
            Сб–Нд: 10:00 — 18:00
          </p>

        </div>

      </div>


      <form id="bookingForm">

        <input
          type="text"
          placeholder="Ваше ім'я"
          required
        >

        <input
          type="tel"
          placeholder="Номер телефону"
          required
        >

        <select required>

          <option value="">
            Оберіть послугу
          </option>

          <option>
            Classic Haircut — €25
          </option>

          <option>
            Hair + Beard — €35
          </option>

          <option>
            Beard — €18
          </option>

          <option>
            Premium — €45
          </option>

        </select>


        <input
          type="date"
          required
        >


        <button
          type="submit"
          class="button gold"
        >
          Відправити заявку ✂
        </button>

      </form>

    </div>

  </section>


  <!-- ================= FOOTER ================= -->

  <footer>

    <div>
      © 2026 SCISSORS BARBER STUDIO
    </div>

    <div>
      Cut with character.
    </div>

  </footer>


  <!-- ================= SCRIPT ================= -->

  <script>

    const form =
      document.getElementById("bookingForm");

    form.addEventListener(
      "submit",
      function(event) {

        event.preventDefault();

        alert(
          "✂ Дякуємо за заявку!\n\n" +
          "Ми зв'яжемося з вами найближчим часом."
        );

        form.reset();

      }
    );

  </script>

</body>
</html>
```
