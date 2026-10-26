<script lang="ts">
  let visitorCount = 1;

  const menuItems = [
    { label: 'ABOUT', description: 'LOCAMinasEについて', href: '#about' },
    { label: 'WORKS', description: '制作した作品', href: '#works' },
    { label: 'GALLERY', description: 'イラストギャラリー', href: '#gallery' },
    { label: 'MUSIC', description: '音楽作品', href: '#music' }
  ];

  function sayHello() {
    visitorCount += 1;
  }
</script>

<svelte:head>
  <title>LOCAMinasE // Official Site</title>
  <meta
    name="description"
    content="LOCAMinasE's personal creative playground. Illustration, music, code and more."
  />
</svelte:head>

<div class="site-wrapper">
  <header class="site-header">
    <a class="logo" href="#top" aria-label="LOCAMinasE トップページ">
      <span class="logo-mark">L.</span>
      <span class="logo-text">LOCAMinasE<span class="logo-sub">OFFICIAL SITE</span></span>
    </a>

    <div class="header-status">
      <span class="status-dot"></span>
      SYSTEM ONLINE
    </div>
  </header>

  <main id="top">
    <section class="hero">
      <div class="hero-noise" aria-hidden="true"></div>

      <div class="hero-content">
        <p class="eyebrow">WELCOME TO MY LITTLE UNIVERSE</p>

        <h1>
          LOCAMinasE
          <span class="title-sub">CREATIVE ARCHIVE_</span>
        </h1>

        <p class="hero-description">
          Illustration / Music / Development<br />
          A little chaos, a little nostalgia.
        </p>

        <a class="enter-button" href="#about">
          <span>ENTER THE SITE</span>
          <span aria-hidden="true">↘</span>
        </a>

        <p class="hero-note">THIS WEBSITE IS UNDER CONSTRUCTION...</p>
      </div>

      <div class="hero-side-label" aria-hidden="true">
        INTERNET NEVER DIES — EST. 2026
      </div>

      <div class="hero-sticker sticker-one" aria-hidden="true">♡ ONLINE ♡</div>
      <div class="hero-sticker sticker-two" aria-hidden="true">404<br />BORING NOT FOUND</div>

      <div class="hero-coordinate" aria-hidden="true">
        <span>35° 39' N</span>
        <span>139° 42' E</span>
      </div>
    </section>

    <section class="mascot-section" id="about">
      <div class="section-index">01 / ABOUT</div>

      <div class="mascot-card">
        <div class="mascot-symbol" aria-hidden="true">✳</div>

        <div class="mascot-copy">
          <p class="tiny-label">SITE MASCOT // YO-I</p>
          <h2>Hey, you found me!</h2>
          <p>
            こんにちは。 LOCAMinasEの箱庭にようこそ。<br />
            イラストも音楽もコードも、好きなものを詰め込んでいく予定です。
          </p>

          <button class="hello-button" onclick={sayHello}>
            CLICK TO SAY HELLO <span aria-hidden="true">♡</span>
          </button>

          <p class="visitor-message" aria-live="polite">
            HELLO SIGNAL: {visitorCount}
          </p>
        </div>

        <div class="mascot-placeholder">
          <span>YO-I</span>
          <span class="placeholder-caption">MASCOT IMAGE<br />COMING SOON</span>
        </div>
      </div>
    </section>

    <section class="works-section" id="works">
      <div class="section-heading">
        <div>
          <p class="section-index">02 / CONTENTS</p>
          <h2>Choose your <span>dimension.</span></h2>
        </div>
        <p class="heading-note">SELECT A PORTAL<br />AND GET LOST.</p>
      </div>

      <div class="menu-grid">
        {#each menuItems as item, index}
          <a class="menu-card" href={item.href}>
            <span class="menu-number">0{index + 1}</span>
            <span class="menu-title">{item.label}</span>
            <span class="menu-description">{item.description}</span>
            <span class="menu-arrow" aria-hidden="true">↗</span>
          </a>
        {/each}
      </div>
    </section>

    <section class="update-section" id="gallery">
      <div class="update-terminal">
        <div class="terminal-bar">
          <span>LOCAMinasE.log</span>
          <span>● ● ●</span>
        </div>

        <div class="terminal-body">
          <p><span class="terminal-prompt">&gt;</span> INITIALIZING PERSONAL WEBSITE...</p>
          <p><span class="terminal-prompt">&gt;</span> LOADING ARTWORKS, MUSIC AND MEMORIES...</p>
          <p><span class="terminal-prompt">&gt;</span> <span class="terminal-success">SYSTEM READY_</span></p>
        </div>
      </div>

      <p class="update-caption">
        THIS PLACE WILL GROW WITH ME.<br />
        THANK YOU FOR BEING HERE.
      </p>
    </section>
  </main>

  <footer class="site-footer" id="music">
    <a class="footer-logo" href="#top">LOCAMinasE<span>®</span></a>
    <p>MADE WITH CURIOSITY &amp; TOO MUCH INTERNET.</p>
    <a class="back-to-top" href="#top">BACK TO TOP ↑</a>
  </footer>
</div>

<style>
  :global(*) {
    box-sizing: border-box;
  }

  :global(html) {
    scroll-behavior: smooth;
    background: #f4f0e9;
  }

  :global(body) {
    margin: 0;
    color: #22202a;
    font-family: "Arial", "Helvetica Neue", sans-serif;
  }

  :global(body)::selection {
    background: #d7ff47;
    color: #22202a;
  }

  :global(a) {
    color: inherit;
    text-decoration: none;
  }

  .site-wrapper {
    --ink: #22202a;
    --paper: #f4f0e9;
    --pink: #ff82bb;
    --lime: #d7ff47;
    --purple: #b7a2ff;
    max-width: 1600px;
    min-height: 100vh;
    margin: 0 auto;
    overflow: hidden;
    background: var(--paper);
  }

  .site-header {
    min-height: 82px;
    padding: 0 6%;
    display: flex;
    align-items: center;
    justify-content: space-between;
    border-bottom: 1px solid rgba(34, 32, 42, 0.18);
  }

  .logo {
    display: flex;
    align-items: center;
    gap: 12px;
  }

  .logo-mark {
    width: 42px;
    height: 42px;
    display: grid;
    place-items: center;
    background: var(--ink);
    color: var(--lime);
    font-weight: 900;
    font-size: 23px;
    transform: rotate(-5deg);
  }

  .logo-text {
    font-size: 15px;
    font-weight: 900;
    letter-spacing: 0.04em;
  }

  .logo-sub {
    display: block;
    margin-top: 4px;
    font-size: 9px;
    font-weight: 500;
    letter-spacing: 0.2em;
  }

  .header-status {
    display: flex;
    align-items: center;
    gap: 9px;
    font-size: 10px;
    font-weight: 800;
    letter-spacing: 0.12em;
  }

  .status-dot {
    width: 8px;
    height: 8px;
    border-radius: 50%;
    background: #6bc46b;
    box-shadow: 0 0 10px #6bc46b;
  }

  .hero {
    min-height: 600px;
    position: relative;
    display: flex;
    align-items: center;
    padding: 90px 12%;
    overflow: hidden;
    background: var(--pink);
    isolation: isolate;
  }

  .hero::before {
    content: "";
    position: absolute;
    z-index: -1;
    width: 540px;
    height: 540px;
    top: 45px;
    right: -30px;
    border: 1px solid rgba(34, 32, 42, 0.25);
    border-radius: 50%;
    box-shadow:
      0 0 0 35px rgba(34, 32, 42, 0.04),
      0 0 0 75px rgba(34, 32, 42, 0.04),
      0 0 0 115px rgba(34, 32, 42, 0.04);
  }

  .hero-noise {
    position: absolute;
    inset: 0;
    z-index: -1;
    opacity: 0.18;
    background-image: radial-gradient(#22202a 0.7px, transparent 0.7px);
    background-size: 7px 7px;
    pointer-events: none;
  }

  .hero-content {
    position: relative;
    z-index: 1;
  }

  .eyebrow,
  .tiny-label,
  .section-index {
    font-size: 10px;
    font-weight: 800;
    letter-spacing: 0.18em;
  }

  .eyebrow {
    margin-bottom: 25px;
  }

  .hero h1 {
    margin: 0;
    font-size: clamp(46px, 8vw, 112px);
    font-weight: 950;
    line-height: 0.92;
    letter-spacing: -0.075em;
  }

  .title-sub {
    display: block;
    margin-top: 17px;
    font-size: clamp(13px, 2vw, 21px);
    font-weight: 800;
    letter-spacing: 0.19em;
  }

  .hero-description {
    margin: 32px 0;
    font-size: 14px;
    line-height: 1.9;
  }

  .enter-button {
    width: 225px;
    min-height: 55px;
    display: flex;
    align-items: center;
    justify-content: space-between;
    padding: 0 19px;
    background: var(--ink);
    color: white;
    font-size: 11px;
    font-weight: 800;
    letter-spacing: 0.1em;
    transition:
      background 180ms ease,
      color 180ms ease,
      transform 180ms ease;
  }

  .enter-button:hover {
    background: var(--lime);
    color: var(--ink);
    transform: translate(4px, -4px);
  }

  .hero-note {
    margin-top: 22px;
    font-size: 9px;
    letter-spacing: 0.1em;
  }

  .hero-side-label {
    position: absolute;
    right: 25px;
    top: 50%;
    writing-mode: vertical-rl;
    font-size: 9px;
    letter-spacing: 0.2em;
  }

  .hero-sticker {
    position: absolute;
    display: grid;
    place-items: center;
    text-align: center;
    font-size: 10px;
    font-weight: 900;
    line-height: 1.5;
  }

  .sticker-one {
    top: 17%;
    right: 17%;
    width: 90px;
    height: 90px;
    border: 1px solid var(--ink);
    border-radius: 50%;
    background: var(--lime);
    transform: rotate(12deg);
  }

  .sticker-two {
    right: 14%;
    bottom: 15%;
    width: 100px;
    height: 80px;
    background: var(--purple);
    transform: rotate(-9deg);
  }

  .hero-coordinate {
    position: absolute;
    right: 5%;
    bottom: 5%;
    display: flex;
    gap: 15px;
    font-size: 9px;
    letter-spacing: 0.1em;
  }

  .mascot-section,
  .works-section {
    padding: 100px 10%;
  }

  .section-index {
    margin-bottom: 25px;
  }

  .mascot-card {
    position: relative;
    display: grid;
    grid-template-columns: 1.2fr 1fr 0.75fr;
    align-items: center;
    gap: 35px;
    padding: 45px;
    background: #fffdf8;
    border: 1px solid rgba(34, 32, 42, 0.18);
    box-shadow: 8px 8px 0 var(--ink);
  }

  .mascot-symbol {
    position: absolute;
    top: 15px;
    left: 18px;
    color: var(--pink);
    font-size: 25px;
  }

  .mascot-copy {
    grid-column: 1 / 3;
    grid-row: 1;
  }

  .tiny-label {
    color: #7e6aaf;
  }

  .mascot-copy h2 {
    margin: 12px 0;
    font-size: clamp(26px, 4vw, 42px);
    letter-spacing: -0.05em;
  }

  .mascot-copy > p:not(.tiny-label):not(.visitor-message) {
    font-size: 13px;
    line-height: 2;
  }

  .hello-button {
    margin-top: 15px;
    padding: 13px 16px;
    border: 1px solid var(--ink);
    background: var(--lime);
    color: var(--ink);
    font-size: 10px;
    font-weight: 900;
    letter-spacing: 0.05em;
    cursor: pointer;
  }

  .hello-button:hover {
    background: var(--pink);
  }

  .visitor-message {
    margin-top: 12px;
    font-family: monospace;
    font-size: 11px;
  }

  .mascot-placeholder {
    grid-column: 3;
    grid-row: 1;
    min-height: 230px;
    display: flex;
    flex-direction: column;
    align-items: center;
    justify-content: center;
    gap: 12px;
    border: 1px dashed #7e6aaf;
    background:
      linear-gradient(135deg, transparent 49.7%, rgba(183, 162, 255, 0.4) 50%, transparent 50.3%),
      linear-gradient(45deg, transparent 49.7%, rgba(255, 130, 187, 0.4) 50%, transparent 50.3%);
    font-weight: 900;
    letter-spacing: 0.15em;
  }

  .placeholder-caption {
    text-align: center;
    font-size: 9px;
    line-height: 1.7;
    letter-spacing: 0.08em;
  }

  .works-section {
    background: #e9e3fa;
  }

  .section-heading {
    display: flex;
    align-items: end;
    justify-content: space-between;
    gap: 25px;
    margin-bottom: 35px;
  }

  .section-heading h2 {
    margin: 0;
    font-size: clamp(28px, 4vw, 48px);
    letter-spacing: -0.06em;
  }

  .section-heading h2 span {
    color: #8d65db;
  }

  .heading-note {
    font-size: 9px;
    font-weight: 800;
    line-height: 1.8;
    letter-spacing: 0.1em;
    text-align: right;
  }

  .menu-grid {
    display: grid;
    grid-template-columns: repeat(2, minmax(0, 1fr));
    gap: 16px;
  }

  .menu-card {
    position: relative;
    min-height: 190px;
    display: flex;
    flex-direction: column;
    align-items: flex-start;
    justify-content: center;
    padding: 30px;
    border: 1px solid var(--ink);
    background: var(--paper);
    transition:
      transform 180ms ease,
      background 180ms ease;
  }

  .menu-card:hover {
    transform: translateY(-5px);
    background: var(--lime);
  }

  .menu-number {
    margin-bottom: 18px;
    font-size: 10px;
    font-weight: 800;
  }

  .menu-title {
    font-size: clamp(22px, 3vw, 32px);
    font-weight: 950;
    letter-spacing: -0.05em;
  }

  .menu-description {
    margin-top: 8px;
    font-size: 11px;
  }

  .menu-arrow {
    position: absolute;
    top: 25px;
    right: 25px;
    font-size: 22px;
  }

  .update-section {
    padding: 85px 10%;
    display: grid;
    grid-template-columns: 1.5fr 1fr;
    align-items: center;
    gap: 50px;
  }

  .update-terminal {
    background: var(--ink);
    color: #f4f0e9;
    box-shadow: 8px 8px 0 var(--purple);
  }

  .terminal-bar {
    display: flex;
    justify-content: space-between;
    padding: 14px 18px;
    border-bottom: 1px solid rgba(244, 240, 233, 0.2);
    font-family: monospace;
    font-size: 10px;
  }

  .terminal-body {
    padding: 25px 20px;
    font-family: monospace;
    font-size: 10px;
    line-height: 2.2;
    overflow-wrap: anywhere;
  }

  .terminal-prompt {
    color: var(--pink);
  }

  .terminal-success {
    color: var(--lime);
  }

  .update-caption {
    font-size: 11px;
    font-weight: 900;
    line-height: 2;
    letter-spacing: 0.08em;
  }

  .site-footer {
    min-height: 100px;
    padding: 25px 6%;
    display: flex;
    align-items: center;
    justify-content: space-between;
    gap: 20px;
    border-top: 1px solid rgba(34, 32, 42, 0.2);
  }

  .footer-logo {
    font-size: 15px;
    font-weight: 950;
    letter-spacing: -0.04em;
  }

  .footer-logo span {
    margin-left: 3px;
    font-size: 8px;
    vertical-align: top;
  }

  .site-footer p,
  .back-to-top {
    font-size: 9px;
    font-weight: 800;
    letter-spacing: 0.06em;
  }

  .back-to-top:hover {
    color: #8d65db;
  }

  @media (max-width: 700px) {
    .site-header {
      min-height: 70px;
      padding: 0 5%;
    }

    .header-status {
      font-size: 8px;
    }

    .hero {
      min-height: 570px;
      padding: 75px 7%;
    }

    .hero::before {
      top: 170px;
      right: -280px;
      width: 450px;
      height: 450px;
    }

    .hero-sticker {
      font-size: 8px;
    }

    .sticker-one {
      top: 8%;
      right: 12%;
      width: 70px;
      height: 70px;
    }

    .sticker-two {
      right: 9%;
      bottom: 13%;
      width: 85px;
      height: 70px;
    }

    .hero-side-label {
      right: 10px;
      font-size: 8px;
    }

    .hero-coordinate {
      left: 7%;
      right: auto;
      bottom: 4%;
      font-size: 8px;
    }

    .mascot-section,
    .works-section {
      padding: 65px 7%;
    }

    .mascot-card {
      grid-template-columns: 1fr;
      gap: 25px;
      padding: 35px 25px;
    }

    .mascot-copy {
      grid-column: 1;
      grid-row: 1;
    }

    .mascot-placeholder {
      grid-column: 1;
      grid-row: 2;
      min-height: 180px;
    }

    .section-heading {
      align-items: flex-start;
      flex-direction: column;
    }

    .heading-note {
      text-align: left;
    }

    .menu-grid {
      grid-template-columns: 1fr;
    }

    .menu-card {
      min-height: 155px;
    }

    .update-section {
      grid-template-columns: 1fr;
      gap: 35px;
      padding: 65px 7%;
    }

    .site-footer {
      align-items: flex-start;
      flex-direction: column;
      gap: 12px;
      padding: 30px 7%;
    }

    .site-footer p {
      line-height: 1.8;
    }
  }

  @media (prefers-reduced-motion: reduce) {
    :global(html) {
      scroll-behavior: auto;
    }

    *,
    *::before,
    *::after {
      transition-duration: 0.01ms !important;
      animation-duration: 0.01ms !important;
    }
  }
</style>