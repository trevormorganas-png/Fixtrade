<!DOCTYPE html>
<html lang="en">
<head>
<meta charset="UTF-8" />
<meta name="viewport" content="width=device-width, initial-scale=1" />
<title>Careers — Axiom Trade</title>
<link rel="preconnect" href="https://fonts.googleapis.com">
<link rel="preconnect" href="https://fonts.gstatic.com" crossorigin>
<link href="https://fonts.googleapis.com/css2?family=Inter:wght@400;500;600;700;800&display=swap" rel="stylesheet">
<style>
  /* ---------- Base ---------- */
  *,
  *::before,
  *::after { box-sizing: border-box; margin: 0; padding: 0; }

  :root {
    --bg: #080a10;
    --bg-soft: #0c1019;
    --card: #111725;
    --card-2: #151d2d;
    --border: rgba(255, 255, 255, .08);
    --border-strong: rgba(255, 255, 255, .16);
    --text: #e9eef7;
    --muted: #8b97ad;
    --accent: #00e08a;
    --accent-soft: rgba(0, 224, 138, .12);
    --accent-2: #4f8cff;
    --danger: #ff5c72;
    --radius: 16px;
    --radius-sm: 10px;
    --max: 1180px;
    --nav-h: 72px;
    --shadow: 0 24px 60px -20px rgba(0, 0, 0, .8);
  }

  html { scroll-behavior: smooth; scroll-padding-top: 100px; }

  body {
    font-family: 'Inter', system-ui, -apple-system, 'Segoe UI', sans-serif;
    background: var(--bg);
    color: var(--text);
    line-height: 1.6;
    -webkit-font-smoothing: antialiased;
    overflow-x: hidden;
  }

  /* Ambient background glow */
  body::before {
    content: "";
    position: fixed;
    inset: 0;
    background:
      radial-gradient(600px 400px at 12% -5%, rgba(0, 224, 138, .13), transparent 70%),
      radial-gradient(700px 500px at 92% 8%, rgba(79, 140, 255, .12), transparent 70%);
    pointer-events: none;
    z-index: 0;
  }

  img, svg { display: block; max-width: 100%; }
  a { color: inherit; text-decoration: none; }
  button { font: inherit; cursor: pointer; border: none; background: none; color: inherit; }
  ul { list-style: none; }

  .container {
    width: 100%;
    max-width: var(--max);
    margin-inline: auto;
    padding-inline: 22px;
    position: relative;
    z-index: 1;
  }

  /* ---------- Buttons ---------- */
  .btn {
    display: inline-flex;
    align-items: center;
    justify-content: center;
    gap: 9px;
    padding: 13px 24px;
    border-radius: 999px;
    font-weight: 600;
    font-size: .94rem;
    letter-spacing: -.01em;
    transition: transform .18s ease, background .18s ease, border-color .18s ease, box-shadow .18s ease;
    white-space: nowrap;
  }
  .btn:active { transform: translateY(1px) scale(.99); }

  .btn-primary {
    background: var(--accent);
    color: #04150d;
    box-shadow: 0 10px 30px -10px rgba(0, 224, 138, .6);
  }
  .btn-primary:hover { background: #22f79e; box-shadow: 0 14px 34px -10px rgba(0, 224, 138, .75); }

  .btn-ghost {
    border: 1px solid var(--border-strong);
    color: var(--text);
    background: rgba(255, 255, 255, .02);
  }
  .btn-ghost:hover { background: rgba(255, 255, 255, .07); border-color: rgba(255, 255, 255, .3); }

  /* ---------- Navbar ---------- */
  .nav {
    position: sticky;
    top: 0;
    z-index: 60;
    height: var(--nav-h);
    display: flex;
    align-items: center;
    transition: background .3s ease, border-color .3s ease, backdrop-filter .3s ease;
    border-bottom: 1px solid transparent;
  }
  .nav.scrolled {
    background: rgba(8, 10, 16, .8);
    backdrop-filter: blur(16px);
    -webkit-backdrop-filter: blur(16px);
    border-bottom-color: var(--border);
  }

  .nav-inner {
    display: flex;
    align-items: center;
    justify-content: space-between;
    gap: 20px;
    width: 100%;
  }

  .logo { display: flex; align-items: center; gap: 10px; font-weight: 800; letter-spacing: -.03em; font-size: 1.06rem; }
  .logo-mark {
    width: 32px; height: 32px;
    border-radius: 9px;
    background: linear-gradient(140deg, var(--accent), #0a9c66);
    display: grid; place-items: center;
    color: #04150d; font-weight: 900; font-size: .95rem;
    box-shadow: 0 6px 18px -6px rgba(0, 224, 138, .8);
  }
  .logo span { color: var(--muted); font-weight: 600; }

  .nav-links { display: flex; align-items: center; gap: 6px; }
  .nav-links a {
    padding: 9px 14px;
    border-radius: 999px;
    font-size: .9rem;
    font-weight: 500;
    color: var(--muted);
    transition: color .18s ease, background .18s ease;
  }
  .nav-links a:hover { color: var(--text); background: rgba(255, 255, 255, .06); }

  .nav-cta { display: flex; align-items: center; gap: 10px; }
  .nav-cta .btn { padding: 10px 20px; font-size: .88rem; }

  .burger {
    display: none;
    width: 42px; height: 42px;
    border-radius: 11px;
    border: 1px solid var(--border);
    align-items: center;
    justify-content: center;
    flex-direction: column;
    gap: 5px;
  }
  .burger span {
    display: block;
    width: 18px; height: 2px;
    background: var(--text);
    border-radius: 2px;
    transition: transform .3s ease, opacity .25s ease;
  }
  .burger.open span:nth-child(1) { transform: translateY(7px) rotate(45deg); }
  .burger.open span:nth-child(2) { opacity: 0; }
  .burger.open span:nth-child(3) { transform: translateY(-7px) rotate(-45deg); }

  /* Mobile menu */
  .mobile-menu {
    position: fixed;
    inset: var(--nav-h) 0 auto 0;
    background: rgba(10, 13, 20, .97);
    backdrop-filter: blur(18px);
    border-bottom: 1px solid var(--border);
    padding: 14px 22px 26px;
    display: grid;
    gap: 4px;
    z-index: 55;
    transform: translateY(-12px);
    opacity: 0;
    visibility: hidden;
    transition: opacity .25s ease, transform .25s ease, visibility .25s;
  }
  .mobile-menu.open { opacity: 1; transform: translateY(0); visibility: visible; }
  .mobile-menu a {
    padding: 14px 10px;
    border-radius: 12px;
    font-weight: 500;
    color: var(--muted);
  }
  .mobile-menu a:hover { background: rgba(255, 255, 255, .05); color: var(--text); }
  .mobile-menu .btn { margin-top: 12px; width: 100%; }

  /* ---------- Hero ---------- */
  .hero { padding: 68px 0 74px; }

  .hero-grid {
    display: grid;
    grid-template-columns: 1.1fr .9fr;
    gap: 56px;
    align-items: center;
  }

  .pill {
    display: inline-flex;
    align-items: center;
    gap: 9px;
    padding: 7px 15px 7px 9px;
    border-radius: 999px;
    background: rgba(0, 224, 138, .08);
    border: 1px solid rgba(0, 224, 138, .25);
    font-size: .8rem;
    font-weight: 600;
    color: var(--accent);
    margin-bottom: 22px;
  }
  .pill .dot {
    width: 7px; height: 7px; border-radius: 50%;
    background: var(--accent);
    box-shadow: 0 0 0 0 rgba(0, 224, 138, .7);
    animation: pulse 2s infinite;
  }
  @keyframes pulse {
    70% { box-shadow: 0 0 0 9px rgba(0, 224, 138, 0); }
    100% { box-shadow: 0 0 0 0 rgba(0, 224, 138, 0); }
  }

  h1 {
    font-size: clamp(2.1rem, 5.2vw, 3.5rem);
    line-height: 1.06;
    letter-spacing: -.045em;
    font-weight: 800;
    margin-bottom: 20px;
  }
  h1 .grad {
    background: linear-gradient(100deg, var(--accent), #6ffbc0 45%, var(--accent-2));
    -webkit-background-clip: text;
    background-clip: text;
    color: transparent;
  }

  .hero-sub {
    color: var(--muted);
    font-size: 1.04rem;
    max-width: 520px;
    margin-bottom: 32px;
  }

  .hero-actions { display: flex; flex-wrap: wrap; gap: 12px; }

  /* Hero visual card */
  .hero-card {
    background: linear-gradient(160deg, var(--card-2), var(--card));
    border: 1px solid var(--border);
    border-radius: 22px;
    padding: 22px;
    box-shadow: var(--shadow);
    position: relative;
    overflow: hidden;
  }
  .hero-card::after {
    content: "";
    position: absolute;
    inset: -40% -20% auto auto;
    width: 260px; height: 260px;
    background: radial-gradient(circle, rgba(0, 224, 138, .22), transparent 65%);
    pointer-events: none;
  }

  .hc-top {
    display: flex;
    align-items: center;
    gap: 9px;
    font-size: .82rem;
    font-weight: 600;
    color: var(--muted);
    margin-bottom: 20px;
  }
  .hc-top .dot { width: 7px; height: 7px; border-radius: 50%; background: var(--accent); }
  .hc-badge {
    margin-left: auto;
    font-size: .7rem;
    letter-spacing: .08em;
    padding: 4px 10px;
    border-radius: 999px;
    border: 1px solid var(--border-strong);
    color: var(--text);
  }

  .chart {
    display: flex;
    align-items: flex-end;
    gap: 7px;
    height: 132px;
    padding-bottom: 4px;
    border-bottom: 1px dashed var(--border);
    margin-bottom: 18px;
  }
  .chart .bar {
    flex: 1;
    height: var(--h);
    border-radius: 6px 6px 3px 3px;
    background: linear-gradient(180deg, var(--accent), rgba(0, 224, 138, .18));
    transform-origin: bottom;
    animation: grow .9s cubic-bezier(.2, .8, .3, 1) backwards;
  }
  .chart .bar.alt { background: linear-gradient(180deg, var(--accent-2), rgba(79, 140, 255, .16)); }
  @keyframes grow { from { transform: scaleY(.05); opacity: .3; } to { transform: scaleY(1); opacity: 1; } }

  .hc-stats { display: grid; grid-template-columns: 1fr 1fr; gap: 14px; }
  .hc-stats div {
    background: rgba(255, 255, 255, .03);
    border: 1px solid var(--border);
    border-radius: 12px;
    padding: 12px 14px;
  }
  .hc-stats strong { display: block; font-size: 1.15rem; letter-spacing: -.02em; }
  .hc-stats span { font-size: .74rem; color: var(--muted); }
  .hc-stats .up { color: var(--accent); }

  /* ---------- Stats strip ---------- */
  .stats {
    display: grid;
    grid-template-columns: repeat(4, 1fr);
    gap: 1px;
    background: var(--border);
    border: 1px solid var(--border);
    border-radius: var(--radius);
    overflow: hidden;
  }
  .stat {
    background: var(--bg-soft);
    padding: 26px 22px;
    text-align: center;
  }
  .stat strong {
    display: block;
    font-size: 1.6rem;
    font-weight: 800;
    letter-spacing: -.035em;
    color: var(--text);
  }
  .stat span { font-size: .82rem; color: var(--muted); }

  /* ---------- Section header ---------- */
  .section { padding: 84px 0; }
  .sec-head { max-width: 620px; margin-bottom: 44px; }
  .eyebrow {
    font-size: .78rem;
    font-weight: 700;
    letter-spacing: .16em;
    text-transform: uppercase;
    color: var(--accent);
    margin-bottom: 12px;
  }
  h2 {
    font-size: clamp(1.6rem, 3.4vw, 2.4rem);
    letter-spacing: -.035em;
    line-height: 1.15;
    font-weight: 800;
    margin-bottom: 14px;
  }
  .sec-head p { color: var(--muted); }

  /* ---------- Perks ---------- */
  .perks-grid {
    display: grid;
    grid-template-columns: repeat(3, 1fr);
    gap: 18px;
  }
  .perk {
    background: var(--card);
    border: 1px solid var(--border);
    border-radius: var(--radius);
    padding: 26px 24px;
    transition: transform .22s ease, border-color .22s ease, background .22s ease;
  }
  .perk:hover {
    transform: translateY(-4px);
    border-color: rgba(0, 224, 138, .35);
    background: var(--card-2);
  }
  .perk-icon {
    width: 44px; height: 44px;
    border-radius: 12px;
    display: grid; place-items: center;
    background: var(--accent-soft);
    color: var(--accent);
    font-size: 1.15rem;
    margin-bottom: 16px;
  }
  .perk h3 { font-size: 1.02rem; font-weight: 700; margin-bottom: 7px; letter-spacing: -.015em; }
  .perk p { font-size: .9rem; color: var(--muted); }

  /* ---------- Jobs ---------- */
  .jobs-toolbar {
    display: flex;
    flex-wrap: wrap;
    gap: 14px;
    align-items: center;
    justify-content: space-between;
    margin-bottom: 24px;
  }

  .tabs {
    display: flex;
    gap: 6px;
    overflow-x: auto;
    padding-bottom: 4px;
    scrollbar-width: none;
  }
  .tabs::-webkit-scrollbar { display: none; }

  .tab {
    padding: 9px 16px;
    border-radius: 999px;
    font-size: .86rem;
    font-weight: 600;
    color: var(--muted);
    border: 1px solid var(--border);
    white-space: nowrap;
    transition: all .18s ease;
  }
  .tab:hover { color: var(--text); border-color: var(--border-strong); }
  .tab.active {
    background: var(--accent);
    border-color: var(--accent);
    color: #04150d;
  }

  .search-wrap { position: relative; flex: 1 1 240px; max-width: 300px; }
  .search-wrap svg {
    position: absolute;
    left: 15px; top: 50%;
    transform: translateY(-50%);
    width: 16px; height: 16px;
    stroke: var(--muted);
    pointer-events: none;
  }
  .search {
    width: 100%;
    padding: 12px 16px 12px 42px;
    border-radius: 999px;
    background: var(--card);
    border: 1px solid var(--border);
    color: var(--text);
    font-size: .88rem;
    outline: none;
    transition: border-color .2s ease, background .2s ease;
  }
  .search::placeholder { color: #5f6b80; }
  .search:focus { border-color: rgba(0, 224, 138, .5); background: var(--card-2); }

  .result-count {
    font-size: .82rem;
    color: var(--muted);
    margin-bottom: 14px;
  }
  .result-count b { color: var(--text); }

  .job-list { display: grid; gap: 12px; }

  .job {
    background: var(--card);
    border: 1px solid var(--border);
    border-radius: var(--radius);
    overflow: hidden;
    transition: border-color .22s ease, background .22s ease;
  }
  .job:hover { border-color: var(--border-strong); }
  .job.open { border-color: rgba(0, 224, 138, .4); background: var(--card-2); }

  .job-head {
    width: 100%;
    display: flex;
    align-items: center;
    gap: 18px;
    padding: 20px 22px;
    text-align: left;
  }
  .job-main { flex: 1; min-width: 0; }
  .job-title {
    font-size: 1.02rem;
    font-weight: 700;
    letter-spacing: -.02em;
    margin-bottom: 6px;
  }
  .job-meta {
    display: flex;
    flex-wrap: wrap;
    align-items: center;
    gap: 8px;
    font-size: .78rem;
    color: var(--muted);
  }
  .job-meta .tag {
    padding: 3px 10px;
    border-radius: 999px;
    background: rgba(255, 255, 255, .05);
    border: 1px solid var(--border);
  }
  .job-meta .tag.dept { color: var(--accent); background: var(--accent-soft); border-color: rgba(0, 224, 138, .25); }

  .job-arrow {
    width: 34px; height: 34px;
    flex: 0 0 34px;
    border-radius: 50%;
    display: grid; place-items: center;
    border: 1px solid var(--border);
    transition: transform .3s ease, border-color .3s ease, background .3s ease;
    color: var(--muted);
  }
  .job.open .job-arrow {
    transform: rotate(180deg);
    border-color: rgba(0, 224, 138, .5);
    color: var(--accent);
  }

  .job-body {
    display: grid;
    grid-template-rows: 0fr;
    transition: grid-template-rows .35s cubic-bezier(.4, 0, .2, 1);
  }
  .job.open .job-body { grid-template-rows: 1fr; }
  .job-body-inner { overflow: hidden; }
  .job-body-content {
    padding: 0 22px 22px;
    border-top: 1px solid var(--border);
    margin-top: 0;
    padding-top: 18px;
  }
  .job-body-content p { color: var(--muted); font-size: .9rem; margin-bottom: 16px; }

  .chip-row { display: flex; flex-wrap: wrap; gap: 8px; margin-bottom: 20px; }
  .chip {
    font-size: .75rem;
    font-weight: 600;
    padding: 5px 12px;
    border-radius: 999px;
    background: rgba(79, 140, 255, .1);
    border: 1px solid rgba(79, 140, 255, .25);
    color: #9dbcff;
  }

  .job-actions { display: flex; flex-wrap: wrap; gap: 10px; }
  .job-actions .btn { padding: 11px 20px; font-size: .86rem; }

  .empty {
    text-align: center;
    padding: 60px 20px;
    border: 1px dashed var(--border-strong);
    border-radius: var(--radius);
    color: var(--muted);
  }
  .empty strong { display: block; color: var(--text); font-size: 1.05rem; margin-bottom: 6px; }

  /* ---------- CTA ---------- */
  .cta-wrap {
    border-radius: 24px;
    border: 1px solid rgba(0, 224, 138, .22);
    background:
      radial-gradient(600px 240px at 20% 0%, rgba(0, 224, 138, .16), transparent 70%),
      radial-gradient(500px 240px at 85% 100%, rgba(79, 140, 255, .16), transparent 70%),
      var(--card);
    padding: 58px 40px;
    text-align: center;
  }
  .cta-wrap h2 { margin-bottom: 12px; }
  .cta-wrap p { color: var(--muted); max-width: 520px; margin: 0 auto 28px; }
  .cta-actions { display: flex; flex-wrap: wrap; gap: 12px; justify-content: center; }

  /* ---------- Footer ---------- */
  footer {
    border-top: 1px solid var(--border);
    padding: 46px 0 34px;
    margin-top: 40px;
  }
  .footer-grid {
    display: flex;
    flex-wrap: wrap;
    gap: 40px;
    justify-content: space-between;
    margin-bottom: 34px;
  }
  .footer-brand { max-width: 280px; }
  .footer-brand p { color: var(--muted); font-size: .87rem; margin-top: 14px; }
  .footer-cols { display: flex; flex-wrap: wrap; gap: 56px; }
  .footer-col h4 {
    font-size: .78rem;
    text-transform: uppercase;
    letter-spacing: .12em;
    color: var(--muted);
    margin-bottom: 14px;
    font-weight: 700;
  }
  .footer-col a {
    display: block;
    font-size: .88rem;
    color: var(--text);
    opacity: .75;
    padding: 5px 0;
    transition: opacity .18s ease, color .18s ease;
  }
  .footer-col a:hover { opacity: 1; color: var(--accent); }

  .footer-bottom {
    display: flex;
    flex-wrap: wrap;
    gap: 12px;
    justify-content: space-between;
    align-items: center;
    padding-top: 22px;
    border-top: 1px solid var(--border);
    font-size: .82rem;
    color: var(--muted);
  }

  /* ---------- Modal ---------- */
  .modal {
    position: fixed;
    inset: 0;
    z-index: 100;
    display: grid;
    place-items: center;
    padding: 20px;
    opacity: 0;
    visibility: hidden;
    transition: opacity .25s ease, visibility .25s;
  }
  .modal.open { opacity: 1; visibility: visible; }

  .modal-backdrop {
    position: absolute;
    inset: 0;
    background: rgba(3, 5, 9, .78);
    backdrop-filter: blur(6px);
  }

  .modal-card {
    position: relative;
    width: 100%;
    max-width: 500px;
    max-height: 90vh;
    overflow-y: auto;
    background: var(--card-2);
    border: 1px solid var(--border-strong);
    border-radius: 20px;
    padding: 30px;
    box-shadow: var(--shadow);
    transform: translateY(16px) scale(.98);
    transition: transform .3s cubic-bezier(.2, .8, .3, 1);
  }
  .modal.open .modal-card { transform: translateY(0) scale(1); }

  .modal-close {
    position: absolute;
    top: 16px; right: 16px;
    width: 34px; height: 34px;
    border-radius: 50%;
    display: grid; place-items: center;
    border: 1px solid var(--border);
    color: var(--muted);
    transition: all .18s ease;
  }
  .modal-close:hover { background: rgba(255, 255, 255, .07); color: var(--text); }

  .modal-card h3 { font-size: 1.3rem; letter-spacing: -.03em; margin-bottom: 6px; }
  .modal-role {
    font-size: .86rem;
    color: var(--accent);
    font-weight: 600;
    margin-bottom: 22px;
  }

  .field { margin-bottom: 16px; }
  .field label {
    display: block;
    font-size: .8rem;
    font-weight: 600;
    color: var(--muted);
    margin-bottom: 7px;
  }
  .field input,
  .field textarea {
    width: 100%;
    padding: 12px 14px;
    border-radius: 11px;
    background: rgba(255, 255, 255, .04);
    border: 1px solid var(--border);
    color: var(--text);
    font-size: .9rem;
    font-family: inherit;
    outline: none;
    transition: border-color .2s ease, background .2s ease;
  }
  .field input:focus,
  .field textarea:focus { border-color: rgba(0, 224, 138, .55); background: rgba(255, 255, 255, .07); }
  .field textarea { resize: vertical; min-height: 92px; }
  .field input::placeholder,
  .field textarea::placeholder { color: #5a6579; }

  .row-2 { display: grid; grid-template-columns: 1fr 1fr; gap: 14px; }

  .form-note { font-size: .76rem; color: var(--muted); margin-top: 12px; }

  .success {
    text-align: center;
    padding: 26px 8px;
  }
  .success .check {
    width: 62px; height: 62px;
    margin: 0 auto 18px;
    border-radius: 50%;
    display: grid; place-items: center;
    background: var(--accent-soft);
    border: 1px solid rgba(0, 224, 138, .4);
    color: var(--accent);
    font-size: 1.7rem;
  }
  .success h3 { margin-bottom: 8px; }
  .success p { color: var(--muted); font-size: .9rem; }

  /* ---------- Reveal animation ---------- */
  .reveal {
    opacity: 0;
    transform: translateY(22px);
    transition: opacity .7s cubic-bezier(.2, .8, .3, 1), transform .7s cubic-bezier(.2, .8, .3, 1);
  }
  .reveal.in { opacity: 1; transform: none; }

  @media (prefers-reduced-motion: reduce) {
    *, *::before, *::after { animation-duration: .01ms !important; transition-duration: .01ms !important; }
    .reveal { opacity: 1; transform: none; }
  }

  /* ---------- Responsive ---------- */
  @media (max-width: 980px) {
    .nav-links, .nav-cta .btn-ghost { display: none; }
    .burger { display: flex; }
    .hero-grid { grid-template-columns: 1fr; gap: 44px; }
    .hero-card { max-width: 460px; }
    .perks-grid { grid-template-columns: repeat(2, 1fr); }
    .stats { grid-template-columns: repeat(2, 1fr); }
  }

  @media (max-width: 640px) {
    :root { --nav-h: 64px; }
    .hero { padding: 44px 0 56px; }
    .section { padding: 60px 0; }
    .perks-grid { grid-template-columns: 1fr; }
    .stats { grid-template-columns: repeat(2, 1fr); }
    .stat { padding: 20px 14px; }
    .stat strong { font-size: 1.3rem; }
    .jobs-toolbar { flex-direction: column; align-items: stretch; }
    .search-wrap { max-width: none; }
    .job-head { padding: 16px; gap: 12px; }
    .job-body-content { padding: 16px; padding-top: 16px; }
    .row-2 { grid-template-columns: 1fr; }
    .modal-card { padding: 24px 20px; }
    .cta-wrap { padding: 42px 22px; }
    .footer-cols { gap: 32px; }
    .footer-bottom { justify-content: flex-start; }
    .hero-actions .btn { flex: 1 1 auto; }
  }
</style>
</head>
<body>

<!-- ================= NAVBAR ================= -->
<header class="nav" id="nav">
  <div class="container nav-inner">
    <a href="#" class="logo">
      <span class="logo-mark">A</span>
      Axiom<span>Trade</span>
    </a>

    <nav class="nav-links">
      <a href="#openings">Open Roles</a>
      <a href="#culture">Culture</a>
      <a href="#perks">Benefits</a>
      <a href="#life">Life at Axiom</a>
    </nav>

    <div class="nav-cta">
      <a href="#openings" class="btn btn-ghost">Refer a friend</a>
      <a href="#openings" class="btn btn-primary">View openings</a>
      <button class="burger" id="burger" aria-label="Toggle menu" aria-expanded="false">
        <span></span><span></span><span></span>
      </button>
    </div>
  </div>
</header>

<!-- Mobile menu -->
<div class="mobile-menu" id="mobileMenu">
  <a href="#openings">Open Roles</a>
  <a href="#culture">Culture</a>
  <a href="#perks">Benefits</a>
  <a href="#life">Life at Axiom</a>
  <a href="#openings" class="btn btn-primary">View openings</a>
</div>

<main>
  <!-- ================= HERO ================= -->
  <section class="hero">
    <div class="container hero-grid">
      <div class="hero-copy">
        <div class="pill"><span class="dot"></span> We're hiring across 5 teams</div>
        <h1>Build the future of <span class="grad">global trading</span> with us.</h1>
        <p class="hero-sub">
          Join a team of engineers, traders and risk specialists moving billions in
          volume every day. Low ego, high ownership, relentless curiosity.
        </p>
        <div class="hero-actions">
          <a href="#openings" class="btn btn-primary">
            Explore open roles
            <svg width="16" height="16" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2.4" stroke-linecap="round" stroke-linejoin="round"><path d="M5 12h14M13 6l6 6-6 6"/></svg>
          </a>
          <a href="#culture" class="btn btn-ghost">Life at Axiom</a>
        </div>
      </div>

      <div class="hero-card reveal">
        <div class="hc-top">
          <span class="dot"></span> Live trading desk
          <span class="hc-badge">24 / 7</span>
        </div>
        <div class="chart">
          <div class="bar" style="--h:38%; animation-delay:.05s"></div>
          <div class="bar alt" style="--h:58%; animation-delay:.1s"></div>
          <div class="bar" style="--h:46%; animation-delay:.15s"></div>
          <div class="bar alt" style="--h:72%; animation-delay:.2s"></div>
          <div class="bar" style="--h:55%; animation-delay:.25s"></div>
          <div class="bar" style="--h:84%; animation-delay:.3s"></div>
          <div class="bar alt" style="--h:63%; animation-delay:.35s"></div>
          <div class="bar" style="--h:92%; animation-delay:.4s"></div>
          <div class="bar alt" style="--h:70%; animation-delay:.45s"></div>
          <div class="bar" style="--h:100%; animation-delay:.5s"></div>
        </div>
        <div class="hc-stats">
          <div><strong>$4.2B</strong><span>Daily volume</span></div>
          <div><strong class="up">+18.4%</strong><span>YoY growth</span></div>
        </div>
      </div>
    </div>
  </section>

  <!-- ================= STATS ================= -->
  <section class="container">
    <div class="stats reveal">
      <div class="stat"><strong>240+</strong><span>Team members</span></div>
      <div class="stat"><strong>14</strong><span>Global offices</span></div>
      <div class="stat"><strong>92%</strong><span>Retention rate</span></div>
      <div class="stat"><strong>4.7/5</strong><span>Glassdoor rating</span></div>
    </div>
  </section>

  <!-- ================= PERKS ================= -->
  <section class="section" id="perks">
    <div class="container">
      <div class="sec-head reveal">
        <div class="eyebrow">Why Axiom</div>
        <h2>Benefits built for people who think long-term</h2>
        <p>We hire adults and treat them like adults. That means real ownership, real flexibility and real support.</p>
      </div>

      <div class="perks-grid">
        <div class="perk reveal">
          <div class="perk-icon">
            <svg width="20" height="20" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2" stroke-linecap="round" stroke-linejoin="round"><path d="M12 2v20M17 5H9.5a3.5 3.5 0 0 0 0 7h5a3.5 3.5 0 0 1 0 7H6"/></svg>
          </div>
          <h3>Top-of-market comp</h3>
          <p>Competitive base, performance bonuses and meaningful equity from day one.</p>
        </div>

        <div class="perk reveal">
          <div class="perk-icon">
            <svg width="20" height="20" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2" stroke-linecap="round" stroke-linejoin="round"><path d="M3 12a9 9 0 1 0 9-9 9 9 0 0 0-9 9Z"/><path d="M12 7v5l3 2"/></svg>
          </div>
          <h3>Flexible hours</h3>
          <p>Remote-first with core overlap hours. Work when you're sharpest.</p>
        </div>

        <div class="perk reveal">
          <div class="perk-icon">
            <svg width="20" height="20" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2" stroke-linecap="round" stroke-linejoin="round"><path d="M20.8 4.6a5.5 5.5 0 0 0-7.8 0L12 5.7l-1-1.1a5.5 5.5 0 0 0-7.8 7.8l8.8 8.8 8.8-8.8a5.5 5.5 0 0 0 0-7.8Z"/></svg>
          </div>
          <h3>Health & wellness</h3>
          <p>Full medical, dental and vision coverage plus a monthly wellness stipend.</p>
        </div>

        <div class="perk reveal">
          <div class="perk-icon">
            <svg width="20" height="20" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2" stroke-linecap="round" stroke-linejoin="round"><path d="M22 10 12 5 2 10l10 5 10-5Z"/><path d="M6 12v5c0 1.7 2.7 3 6 3s6-1.3 6-3v-5"/></svg>
          </div>
          <h3>Learning budget</h3>
          <p>$3,000 a year for courses, conferences and certifications — no approval loops.</p>
        </div>

        <div class="perk reveal">
          <div class="perk-icon">
            <svg width="20" height="20" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2" stroke-linecap="round" stroke-linejoin="round"><path d="M17 21v-2a4 4 0 0 0-4-4H5a4 4 0 0 0-4 4v2"/><circle cx="9" cy="7" r="4"/><path d="M23 21v-2a4 4 0 0 0-3-3.9"/></svg>
          </div>
          <h3>Team retreats</h3>
          <p>Two global offsites a year — past trips include Lisbon, Tokyo and Tulum.</p>
        </div>

        <div class="perk reveal">
          <div class="perk-icon">
            <svg width="20" height="20" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2" stroke-linecap="round" stroke-linejoin="round"><path d="M4 20V10M10 20V4M16 20v-7M22 20v-4"/></svg>
          </div>
          <h3>Real ownership</h3>
          <p>Small teams, short decision chains. Your work ships to production in days.</p>
        </div>
      </div>
    </div>
  </section>

  <!-- ================= OPENINGS ================= -->
  <section class="section" id="openings">
    <div class="container">
      <div class="sec-head reveal">
        <div class="eyebrow">Open positions</div>
        <h2>Find your next role</h2>
        <p>Filter by team or search by keyword. Every role is reviewed by a human within 48 hours.</p>
      </div>

      <div class="jobs-toolbar reveal">
        <div class="tabs" id="tabs">
          <button class="tab active" data-filter="all">All roles</button>
          <button class="tab" data-filter="engineering">Engineering</button>
          <button class="tab" data-filter="trading">Trading</button>
          <button class="tab" data-filter="risk">Risk</button>
          <button class="tab" data-filter="product">Product</button>
          <button class="tab" data-filter="operations">Operations</button>
        </div>

        <div class="search-wrap">
          <svg viewBox="0 0 24 24" fill="none" stroke-width="2" stroke-linecap="round" stroke-linejoin="round"><circle cx="11" cy="11" r="7"/><path d="m20 20-3.5-3.5"/></svg>
          <input type="search" class="search" id="search" placeholder="Search roles, skills…" aria-label="Search roles" />
        </div>
      </div>

      <div class="result-count" id="resultCount"></div>
      <div class="job-list" id="jobList"></div>
    </div>
  </section>

  <!-- ================= CULTURE / CTA ================= -->
  <section class="section" id="culture">
    <div class="container">
      <div class="cta-wrap reveal" id="life">
        <h2>Don't see your role? Reach out anyway.</h2>
        <p>We're always interested in exceptional people. Send us a note and tell us what you'd build at Axiom Trade.</p>
        <div class="cta-actions">
          <button class="btn btn-primary" data-open-modal="General application">Send a general application</button>
          <a href="#openings" class="btn btn-ghost">Browse all roles</a>
        </div>
      </div>
    </div>
  </section>
</main>

<!-- ================= FOOTER ================= -->
<footer>
  <div class="container">
    <div class="footer-grid">
      <div class="footer-brand">
        <a href="#" class="logo">
          <span class="logo-mark">A</span>
          Axiom<span>Trade</span>
        </a>
        <p>Global trading infrastructure built by a small team with outsized ambition.</p>
      </div>

      <div class="footer-cols">
        <div class="footer-col">
          <h4>Careers</h4>
          <a href="#openings">Open roles</a>
          <a href="#perks">Benefits</a>
          <a href="#culture">Culture</a>
          <a href="#">Internships</a>
        </div>
        <div class="footer-col">
          <h4>Company</h4>
          <a href="#">About us</a>
          <a href="#">Newsroom</a>
          <a href="#">Contact</a>
          <a href="#">Legal</a>
        </div>
        <div class="footer-col">
          <h4>Social</h4>
          <a href="#">LinkedIn</a>
          <a href="#">X / Twitter</a>
          <a href="#">GitHub</a>
        </div>
      </div>
    </div>

    <div class="footer-bottom">
      <span>© 2025 Axiom Trade. All rights reserved.</span>
      <span>Equal opportunity employer · Privacy · Terms</span>
    </div>
  </div>
</footer>

<!-- ================= APPLY MODAL ================= -->
<div class="modal" id="applyModal" role="dialog" aria-modal="true" aria-labelledby="modalTitle">
  <div class="modal-backdrop" data-close-modal></div>

  <div class="modal-card">
    <button class="modal-close" data-close-modal aria-label="Close">
      <svg width="16" height="16" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2.4" stroke-linecap="round"><path d="M18 6 6 18M6 6l12 12"/></svg>
    </button>

    <div id="formView">
      <h3 id="modalTitle">Apply now</h3>
      <div class="modal-role" id="modalRole">Position</div>

      <form id="applyForm" novalidate>
        <div class="row-2">
          <div class="field">
            <label for="fname">First name</label>
            <input type="text" id="fname" name="fname" placeholder="Alex" required />
          </div>
          <div class="field">
            <label for="lname">Last name</label>
            <input type="text" id="lname" name="lname" placeholder="Morgan" required />
          </div>
        </div>

        <div class="field">
          <label for="email">Email address</label>
          <input type="email" id="email" name="email" placeholder="alex@example.com" required />
        </div>

        <div class="field">
          <label for="linkedin">LinkedIn / Portfolio</label>
          <input type="url" id="linkedin" name="linkedin" placeholder="https://linkedin.com/in/..." />
        </div>

        <div class="field">
          <label for="message">Why this role?</label>
          <textarea id="message" name="message" placeholder="Tell us briefly about your experience…"></textarea>
        </div>

        <button type="submit" class="btn btn-primary" style="width:100%">Submit application</button>
        <p class="form-note">We review every application within 48 hours. No recruiters, no spam.</p>
      </form>
    </div>

    <div class="success" id="successView" style="display:none">
      <div class="check">
        <svg width="28" height="28" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="3" stroke-linecap="round" stroke-linejoin="round"><path d="M20 6 9 17l-5-5"/></svg>
      </div>
      <h3>Application received!</h3>
      <p>Thanks for applying. Our talent team will be in touch within 48 hours.</p>
    </div>
  </div>
</div>

<script>
/* ============================================================
   DATA
============================================================ */
const jobs = [
  {
    id: 1,
    title: "Senior Backend Engineer",
    dept: "engineering",
    deptLabel: "Engineering",
    location: "Remote · EU",
    type: "Full-time",
    desc: "Design and scale the low-latency order routing services that power our trading infrastructure. You'll own services end to end, from schema design to on-call.",
    tags: ["Go", "Kafka", "PostgreSQL", "Low latency"]
  },
  {
    id: 2,
    title: "Quantitative Trader",
    dept: "trading",
    deptLabel: "Trading",
    location: "London, UK",
    type: "Full-time",
    desc: "Research, build and run systematic strategies across futures and FX. You'll work directly with the risk desk and see your P&L in real time.",
    tags: ["Python", "Statistics", "Market microstructure"]
  },
  {
    id: 3,
    title: "Frontend Engineer (React)",
    dept: "engineering",
    deptLabel: "Engineering",
    location: "Remote · Global",
    type: "Full-time",
    desc: "Build the trading terminal our customers live in every day. Focus on sub-second rendering, real-time data streams and pixel-perfect UX.",
    tags: ["React", "TypeScript", "WebSockets", "Design systems"]
  },
  {
    id: 4,
    title: "Risk Analyst",
    dept: "risk",
    deptLabel: "Risk",
    location: "New York, US",
    type: "Full-time",
    desc: "Monitor portfolio exposure across asset classes, build real-time risk models and partner with the trading desk on limit frameworks.",
    tags: ["Risk modelling", "SQL", "Python", "Derivatives"]
  },
  {
    id: 5,
    title: "Product Designer",
    dept: "product",
    deptLabel: "Product",
    location: "Remote · EU",
    type: "Full-time",
    desc: "Own end-to-end design for our trading products — from discovery and wireframes to polished, shipped interfaces. You'll shape the design system.",
    tags: ["Figma", "Prototyping", "Design systems", "UX research"]
  },
  {
    id: 6,
    title: "DevOps Engineer",
    dept: "engineering",
    deptLabel: "Engineering",
    location: "Remote · Global",
    type: "Full-time",
    desc: "Keep a 24/7 trading platform fast, observable and boring. Own Kubernetes clusters, CI/CD pipelines and incident response tooling.",
    tags: ["Kubernetes", "Terraform", "AWS", "Observability"]
  },
  {
    id: 7,
    title: "Compliance Operations Lead",
    dept: "operations",
    deptLabel: "Operations",
    location: "Singapore",
    type: "Full-time",
    desc: "Lead our APAC compliance operations, manage regulatory reporting and build scalable onboarding processes for institutional clients.",
    tags: ["KYC/AML", "Regulatory reporting", "Team lead"]
  },
  {
    id: 8,
    title: "Product Manager — Trading APIs",
    dept: "product",
    deptLabel: "Product",
    location: "Remote · US",
    type: "Full-time",
    desc: "Own the roadmap for our public trading APIs and developer platform. Work closely with engineering, sales and top-tier institutional clients.",
    tags: ["APIs", "Roadmapping", "B2B", "Fintech"]
  },
  {
    id: 9,
    title: "Junior Risk Engineer",
    dept: "risk",
    deptLabel: "Risk",
    location: "Remote · EU",
    type: "Full-time",
    desc: "Help build the data pipelines and dashboards that keep our risk desk ahead of market moves. Great first role for a quantitative graduate.",
    tags: ["Python", "Data pipelines", "Grafana"]
  }
];

/* ============================================================
   RENDER JOBS
============================================================ */
const jobList = document.getElementById('jobList');
const tabsEl = document.getElementById('tabs');
const searchEl = document.getElementById('search');
const resultCount = document.getElementById('resultCount');

function jobHTML(job) {
  return `
    <article class="job" data-dept="${job.dept}">
      <button class="job-head" aria-expanded="false">
        <div class="job-main">
          <div class="job-title">${job.title}</div>
          <div class="job-meta">
            <span class="tag dept">${job.deptLabel}</span>
            <span class="tag">${job.location}</span>
            <span class="tag">${job.type}</span>
          </div>
        </div>
        <span class="job-arrow" aria-hidden="true">
          <svg width="15" height="15" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2.4" stroke-linecap="round" stroke-linejoin="round"><path d="m6 9 6 6 6-6"/></svg>
        </span>
      </button>

      <div class="job-body">
        <div class="job-body-inner">
          <div class="job-body-content">
            <p>${job.desc}</p>
            <div class="chip-row">
              ${job.tags.map(t => `<span class="chip">${t}</span>`).join('')}
            </div>
            <div class="job-actions">
              <button class="btn btn-primary apply-btn" data-role="${job.title}">Apply now</button>
              <button class="btn btn-ghost save-btn">Save role</button>
            </div>
          </div>
        </div>
      </div>
    </article>
  `;
}

function renderJobs() {
  const activeTab = document.querySelector('.tab.active').dataset.filter;
  const q = searchEl.value.trim().toLowerCase();

  const filtered = jobs.filter(job => {
    const matchesDept = activeTab === 'all' || job.dept === activeTab;
    const haystack = (job.title + ' ' + job.deptLabel + ' ' + job.location + ' ' + job.tags.join(' ')).toLowerCase();
    const matchesQuery = !q || haystack.includes(q);
    return matchesDept && matchesQuery;
  });

  resultCount.innerHTML = `Showing <b>${filtered.length}</b> open role${filtered.length === 1 ? '' : 's'}`;

  if (!filtered.length) {
    jobList.innerHTML = `
      <div class="empty">
        <strong>No matching roles</strong>
        Try a different keyword or clear your filters — new roles open every week.
      </div>`;
    return;
  }

  jobList.innerHTML = filtered.map(jobHTML).join('');
}

/* Tabs */
tabsEl.addEventListener('click', e => {
  const tab = e.target.closest('.tab');
  if (!tab) return;
  document.querySelectorAll('.tab').forEach(t => t.classList.remove('active'));
  tab.classList.add('active');
  renderJobs();
});

/* Search (debounced) */
let searchTimer;
searchEl.addEventListener('input', () => {
  clearTimeout(searchTimer);
  searchTimer = setTimeout(renderJobs, 140);
});

/* Accordion + Apply (event delegation) */
jobList.addEventListener('click', e => {
  const applyBtn = e.target.closest('.apply-btn');
  if (applyBtn) {
    openModal(applyBtn.dataset.role);
    return;
  }

  const saveBtn = e.target.closest('.save-btn');
  if (saveBtn) {
    const isSaved = saveBtn.textContent.trim() === 'Saved ✓';
    saveBtn.textContent = isSaved ? 'Save role' : 'Saved ✓';
    saveBtn.style.color = isSaved ? '' : 'var(--accent)';
    saveBtn.style.borderColor = isSaved ? '' : 'rgba(0,224,138,.5)';
    return;
  }

  const head = e.target.closest('.job-head');
  if (!head) return;

  const card = head.closest('.job');
  const isOpen = card.classList.contains('open');

  document.querySelectorAll('.job.open').forEach(j => {
    j.classList.remove('open');
    j.querySelector('.job-head').setAttribute('aria-expanded', 'false');
  });

  if (!isOpen) {
    card.classList.add('open');
    head.setAttribute('aria-expanded', 'true');
  }
});

renderJobs();

/* ============================================================
   MODAL
============================================================ */
const modal = document.getElementById('applyModal');
const modalRole = document.getElementById('modalRole');
const formView = document.getElementById('formView');
const successView = document.getElementById('successView');
const applyForm = document.getElementById('applyForm');
let lastFocused = null;

function openModal(role) {
  lastFocused = document.activeElement;
  modalRole.textContent = role;
  formView.style.display = 'block';
  successView.style.display = 'none';
  applyForm.reset();
  modal.classList.add('open');
  document.body.style.overflow = 'hidden';
  setTimeout(() => document.getElementById('fname').focus(), 120);
}

function closeModal() {
  modal.classList.remove('open');
  document.body.style.overflow = '';
  if (lastFocused) lastFocused.focus();
}

document.querySelectorAll('[data-close-modal]').forEach(el => el.addEventListener('click', closeModal));

document.addEventListener('keydown', e => {
  if (e.key === 'Escape' && modal.classList.contains('open')) closeModal();
});

document.querySelector('[data-open-modal]').addEventListener('click', e => {
  openModal(e.currentTarget.dataset.openModal);
});

applyForm.addEventListener('submit', e => {
  e.preventDefault();

  const required = ['fname', 'lname', 'email'];
  let valid = true;

  required.forEach(id => {
    const input = document.getElementById(id);
    if (!input.value.trim()) {
      input.style.borderColor = 'var(--danger)';
      valid = false;
    } else {
      input.style.borderColor = '';
    }
  });

  const email = document.getElementById('email');
  if (email.value && !/^[^\s@]+@[^\s@]+\.[^\s@]+$/.test(email.value)) {
    email.style.borderColor = 'var(--danger)';
    valid = false;
  }

  if (!valid) return;

  formView.style.display = 'none';
  successView.style.display = 'block';
  setTimeout(closeModal, 2600);
});

/* ============================================================
   NAVBAR / MOBILE MENU / SCROLL
============================================================ */
const nav = document.getElementById('nav');
const burger = document.getElementById('burger');
const mobileMenu = document.getElementById('mobileMenu');

window.addEventListener('scroll', () => {
  nav.classList.toggle('scrolled', window.scrollY > 12);
}, { passive: true });

burger.addEventListener('click', () => {
  const open = burger.classList.toggle('open');
  mobileMenu.classList.toggle('open', open);
  burger.setAttribute('aria-expanded', String(open));
});

mobileMenu.addEventListener('click', e => {
  if (e.target.tagName === 'A') {
    burger.classList.remove('open');
    mobileMenu.classList.remove('open');
    burger.setAttribute('aria-expanded', 'false');
  }
});

/* ============================================================
   SCROLL REVEAL
============================================================ */
const revealEls = document.querySelectorAll('.reveal');
const io = new IntersectionObserver((entries) => {
  entries.forEach((entry, i) => {
    if (entry.isIntersecting) {
      setTimeout(() => entry.target.classList.add('in'), i * 60);
      io.unobserve(entry.target);
    }
  });
}, { threshold: 0.12, rootMargin: '0px 0px -40px 0px' });

revealEls.forEach(el => io.observe(el));
</script>
</body>
</html>
