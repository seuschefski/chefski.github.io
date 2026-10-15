[index.html](https://github.com/user-attachments/files/33490579/index.html)
<!doctype html>
<html lang="ja">
<head>
  <meta charset="utf-8">
  <meta name="viewport" content="width=device-width, initial-scale=1">
  <link rel="preconnect" href="https://fonts.googleapis.com">
  <link rel="preconnect" href="https://fonts.gstatic.com" crossorigin>
  <link href="https://fonts.googleapis.com/css2?family=Open+Sans:ital,wght@0,300..800;1,300..800&family=Quicksand:wght@300..700&display=swap" rel="stylesheet">
  <title>ou</title>
  <style>
    /* CSSはページの見た目を決める場所です。色や余白はここで調整できます。 */
    :root {
      color-scheme: dark;
      --background: #101114;
      --card: rgba(255, 255, 255, 0.045);
      --text: #e9e7e2;
      --muted: #a6a4a1;
      --accent: #c8b8dc;
      --line: rgba(255, 255, 255, 0.12);
    }

    * { box-sizing: border-box; }

    body {
      min-height: 100vh;
      margin: 0;
      display: grid;
      place-items: center;
      padding: 28px 18px;
      color: var(--text);
      background:
        radial-gradient(ellipse at 50% 0%, rgba(133, 111, 160, 0.16), transparent 48%),
        var(--background);
      font-family: Inter, ui-sans-serif, system-ui, -apple-system, "Segoe UI", sans-serif;
    }

    .site-menu {
      position: fixed;
      z-index: 10;
      top: 22px;
      right: 22px;
    }

    .menu-toggle {
      display: flex;
      width: 48px;
      height: 48px;
      flex-direction: column;
      align-items: center;
      justify-content: center;
      gap: 5px;
      border: 0;
      border-radius: 12px;
      background: transparent;
      color: var(--text);
      cursor: pointer;
      list-style: none;
      transition: background 180ms ease;
    }

    .menu-toggle:hover { background: rgba(255, 255, 255, 0.07); }
    .menu-toggle:focus-visible { outline: 1px solid var(--accent); outline-offset: 3px; }
    .menu-toggle::-webkit-details-marker { display: none; }

    .menu-toggle span {
      display: block;
      width: 21px;
      height: 2px;
      border-radius: 2px;
      background: currentColor;
      transition: transform 220ms ease, opacity 160ms ease;
    }

    .site-menu[open] .menu-toggle span:first-child { transform: translateY(7px) rotate(45deg); }
    .site-menu[open] .menu-toggle span:nth-child(2) { opacity: 0; }
    .site-menu[open] .menu-toggle span:last-child { transform: translateY(-7px) rotate(-45deg); }

    @media (prefers-reduced-motion: reduce) {
      .menu-toggle, .menu-toggle span { transition: none; }
    }
    .profile {
      width: min(100%, 440px);
      padding: 34px;
      border: 1px solid var(--line);
      border-radius: 22px;
      background: var(--card);
      box-shadow: 0 24px 80px rgba(0, 0, 0, 0.28);
      backdrop-filter: blur(12px);
      animation: appear 700ms ease both;
    }

    .eyebrow {
      margin: 0 0 18px;
      color: var(--muted);
      font-size: 0.75rem;
      letter-spacing: 0.18em;
      text-transform: uppercase;
    }

    .profile-icon {
      display: block;
      width: 88px;
      height: 88px;
      margin: 0 auto 20px;
      border: 1px solid var(--line);
      border-radius: 24px;
      object-fit: cover;
    }
    h1 {
      font-family: 'Quicksand', sans-serif;
      text-align: center;
      margin: 0;
      font-size: clamp(2.5rem, 12vw, 4rem);
      font-weight: 650;
      letter-spacing: -0.02em;
      line-height: 1;
    }

    .hello {
       margin: 14px 0 30px;
      color: var(--accent);
      font-size: 1.5rem;
      text-align: center;
    }

    .label {
      margin: 0 0 12px;
      color: var(--muted);
      font-size: 0.72rem;
      letter-spacing: 0.15em;
      text-transform: uppercase;
    }<img width="372" height="372" alt="profile-icon" src="https://github.com/user-attachments/assets/fe644744-53fc-44a2-a197-420160138777" />


    .artists {
      display: flex;
      flex-wrap: wrap;
      gap: 8px;
      margin: 0 0 28px;
      padding: 0;
      list-style: none;
    }

    .artists li {
      padding: 8px 12px;
      border: 1px solid var(--line);
      border-radius: 999px;
      color: var(--text);
      font-size: 0.88rem;
    }

    .links {
      display: flex;
      justify-content: center;
      gap: 10px;
      padding-top: 20px;
      border-top: 1px solid var(--line);
    }

    .links a {
      display: grid;
      width: 42px;
      height: 42px;
      place-items: center;
      border: 1px solid var(--line);
      border-radius: 50%;
      color: var(--text);
      text-decoration: none;
      transition: color 180ms ease, border-color 180ms ease, transform 180ms ease;
    }

    .links svg {
      width: 19px;
      height: 19px;
      fill: currentColor;
    }

    .links a:hover {
      color: var(--accent);
      border-color: var(--accent);
      transform: translateY(-2px);
    }

    .note {
      margin: 26px 0 0;
      color: var(--muted);
      font-size: 0.75rem;
    }

    @keyframes appear {
      from { opacity: 0; transform: translateY(10px); }
      to { opacity: 1; transform: translateY(0); }
    }

    @media (max-width: 420px) {
      .profile { padding: 27px 23px; }
    }

    /* 動きを少なくする設定の人には、表示アニメーションを止めます。 */
    @media (prefers-reduced-motion: reduce) {
      *, *::before, *::after { animation-duration: 0.01ms !important; transition-duration: 0.01ms !important; }
    }
  </style>
</head>
<body>
  <details class="site-menu">
    <summary class="menu-toggle" aria-label="メニューを開閉する"><span></span><span></span><span></span></summary>
  </details>
  <main class="profile">
    <!-- HTMLはページの内容と構造を作ります。ここを編集すると表示される文章が変わります。 -->
    <p class="eyebrow">welcome to my profile</p>
    <img class="profile-icon" src="profile-icon.jpg" alt="CHEFSKIのプロフィールアイコン">
    <h1>CHEFSKI</h1>
    <p class="hello">16yo│osu/sf6/lol/etc.</p>

    <nav class="links" aria-label="Social links">
      <!-- href="#" は仮置きです。SNSのURLが決まったら # をURLに置き換えます。 -->
      <a href="https://github.com/seuschefski" target="_blank" rel="noopener noreferrer" aria-label="GitHub" title="GitHub">
        <svg viewBox="0 0 24 24" aria-hidden="true"><path d="M12 .9a11.1 11.1 0 0 0-3.51 21.63c.56.1.76-.24.76-.54v-2.1c-3.1.67-3.76-1.31-3.76-1.31-.51-1.29-1.24-1.63-1.24-1.63-1.02-.7.08-.69.08-.69 1.13.08 1.72 1.16 1.72 1.16 1 1.71 2.62 1.22 3.26.94.1-.73.39-1.22.71-1.5-2.48-.28-5.09-1.24-5.09-5.52 0-1.22.44-2.22 1.16-3-.12-.28-.5-1.42.11-2.96 0 0 .95-.3 3.05 1.15a10.6 10.6 0 0 1 5.55 0c2.1-1.45 3.05-1.15 3.05-1.15.61 1.54.23 2.68.11 2.96.72.78 1.16 1.78 1.16 3 0 4.29-2.62 5.24-5.11 5.51.4.35.76 1.03.76 2.08v3.06c0 .3.2.65.77.54A11.1 11.1 0 0 0 12 .9Z"/></svg>
      </a>
      <a href="https://x.com/seuschefski" target="_blank" rel="noopener noreferrer" aria-label="X" title="X">
        <svg viewBox="0 0 24 24" aria-hidden="true"><path d="M18.9 2H22l-6.78 7.75L23.2 22h-6.25l-4.9-7.28L5.68 22H2.55l7.25-8.29L1.8 2h6.4l4.43 6.68L18.9 2Zm-1.1 17.86h1.73L7.28 4.03H5.42L17.8 19.86Z"/></svg>
      </a>
      <a href="https://open.spotify.com/user/31o2vdcbziq3xd33akbbl7kxrhii?si=8b6ab1e7384a4689" target="_blank" rel="noopener noreferrer" aria-label="Spotify" title="Spotify">
        <svg viewBox="0 0 24 24" aria-hidden="true"><path d="M12 1.5a10.5 10.5 0 1 0 0 21 10.5 10.5 0 0 0 0-21Zm4.82 15.14a.66.66 0 0 1-.91.22c-2.5-1.53-5.65-1.88-9.36-1.03a.66.66 0 1 1-.29-1.29c4.06-.93 7.54-.52 10.34 1.19.31.19.41.6.22.91Zm1.3-2.9a.82.82 0 0 1-1.13.27c-2.86-1.76-7.22-2.27-10.6-1.24a.82.82 0 1 1-.48-1.57c3.86-1.17 8.66-.6 11.94 1.41.39.24.51.74.27 1.13Zm.11-3.02c-3.43-2.04-9.1-2.23-12.38-1.23a.99.99 0 1 1-.58-1.9c3.77-1.14 10.03-.92 13.99 1.43a.99.99 0 0 1-1.03 1.7Z"/></svg>
      </a>
    </nav>

    <p class="note"></p>
  </main>
</body>
</html>













