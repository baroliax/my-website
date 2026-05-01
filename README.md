<!DOCTYPE html>
<html lang="en">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>Radha Rani — The Eternal Bhakti Path</title>
<link href="https://fonts.googleapis.com/css2?family=Cormorant+Garamond:ital,wght@0,300;0,400;0,600;1,300;1,400&family=Cinzel+Decorative:wght@400;700&family=Crimson+Pro:ital,wght@0,300;1,300&display=swap" rel="stylesheet">
<style>
  *, *::before, *::after { box-sizing: border-box; margin: 0; padding: 0; }

  :root {
    --gold: #D4A843;
    --rose: #C4607A;
    --deep: #1A0A1E;
    --ink: #120818;
    --cream: #F5ECD7;
    --muted: #C8A88A;
    --lotus: #E8849A;
    --twilight: #2D1438;
    --glow: rgba(212,168,67,0.18);
  }

  html { scroll-behavior: smooth; }

  body {
    font-family: 'Cormorant Garamond', serif;
    background: var(--ink);
    color: var(--cream);
    overflow-x: hidden;
    cursor: none;
  }

  /* Custom Cursor */
  .cursor {
    position: fixed; width: 18px; height: 18px; border-radius: 50%;
    background: var(--gold); mix-blend-mode: screen;
    pointer-events: none; z-index: 9999;
    transform: translate(-50%, -50%);
    transition: transform 0.08s ease, width 0.2s, height 0.2s;
  }
  .cursor-trail {
    position: fixed; width: 38px; height: 38px; border-radius: 50%;
    border: 1px solid rgba(212,168,67,0.4);
    pointer-events: none; z-index: 9998;
    transform: translate(-50%, -50%);
    transition: all 0.18s ease;
  }

  /* ========== STARFIELD ========== */
  #starfield {
    position: fixed; inset: 0; z-index: 0;
    pointer-events: none;
  }

  /* ========== NAV ========== */
  nav {
    position: fixed; top: 0; left: 0; right: 0;
    z-index: 100;
    padding: 20px 60px;
    display: flex; align-items: center; justify-content: space-between;
    background: linear-gradient(180deg, rgba(18,8,24,0.95) 0%, transparent 100%);
    backdrop-filter: blur(8px);
  }
  .nav-logo {
    font-family: 'Cinzel Decorative', cursive;
    font-size: 1.1rem; letter-spacing: 0.08em;
    color: var(--gold);
    text-shadow: 0 0 30px rgba(212,168,67,0.5);
  }
  .nav-links { display: flex; gap: 40px; list-style: none; }
  .nav-links a {
    font-family: 'Crimson Pro', serif; font-size: 1rem;
    letter-spacing: 0.12em; color: var(--muted);
    text-decoration: none; text-transform: uppercase;
    transition: color 0.3s;
  }
  .nav-links a:hover { color: var(--gold); }

  /* ========== HERO ========== */
  #hero {
    position: relative; min-height: 100vh;
    display: flex; flex-direction: column;
    align-items: center; justify-content: center;
    text-align: center; z-index: 2;
    padding: 120px 40px 80px;
    overflow: hidden;
  }

  .hero-mandala {
    position: absolute; top: 50%; left: 50%;
    transform: translate(-50%, -50%);
    width: 700px; height: 700px;
    opacity: 0.07; pointer-events: none;
    animation: spin-slow 80s linear infinite;
  }

  @keyframes spin-slow { to { transform: translate(-50%,-50%) rotate(360deg); } }

  .hero-glow {
    position: absolute; top: 50%; left: 50%;
    transform: translate(-50%, -50%);
    width: 600px; height: 600px; border-radius: 50%;
    background: radial-gradient(circle, rgba(196,96,122,0.12) 0%, rgba(212,168,67,0.06) 40%, transparent 70%);
    animation: pulse-glow 6s ease-in-out infinite;
  }
  @keyframes pulse-glow {
    0%, 100% { transform: translate(-50%,-50%) scale(1); opacity: 0.6; }
    50% { transform: translate(-50%,-50%) scale(1.12); opacity: 1; }
  }

  .tag-line {
    font-family: 'Cinzel Decorative', cursive;
    font-size: 0.72rem; letter-spacing: 0.4em;
    color: var(--rose); text-transform: uppercase;
    margin-bottom: 24px; opacity: 0;
    animation: fade-up 1.2s 0.4s forwards;
  }
  .hero-title {
    font-family: 'Cinzel Decorative', cursive;
    font-size: clamp(2.8rem, 8vw, 6.5rem);
    font-weight: 700; line-height: 1.08;
    color: var(--gold);
    text-shadow: 0 0 60px rgba(212,168,67,0.4), 0 0 120px rgba(212,168,67,0.15);
    opacity: 0; animation: fade-up 1.2s 0.7s forwards;
    margin-bottom: 8px;
  }
  .hero-sub {
    font-family: 'Cormorant Garamond', serif;
    font-size: clamp(1.2rem, 3vw, 2rem);
    font-style: italic; font-weight: 300;
    color: var(--lotus);
    opacity: 0; animation: fade-up 1.2s 1s forwards;
    margin-bottom: 32px;
  }
  .hero-desc {
    max-width: 640px;
    font-size: 1.15rem; line-height: 1.85;
    color: var(--muted); font-weight: 300;
    opacity: 0; animation: fade-up 1.2s 1.3s forwards;
    margin-bottom: 48px;
  }
  .btn-primary {
    display: inline-block; padding: 16px 48px;
    border: 1px solid var(--gold); border-radius: 2px;
    color: var(--gold); font-family: 'Cinzel Decorative', cursive;
    font-size: 0.75rem; letter-spacing: 0.25em; text-decoration: none;
    text-transform: uppercase; transition: all 0.4s;
    position: relative; overflow: hidden;
    opacity: 0; animation: fade-up 1.2s 1.6s forwards;
  }
  .btn-primary::before {
    content: ''; position: absolute; inset: 0;
    background: var(--gold); transform: translateX(-101%);
    transition: transform 0.4s ease;
  }
  .btn-primary:hover::before { transform: translateX(0); }
  .btn-primary:hover { color: var(--ink); }
  .btn-primary span { position: relative; z-index: 1; }

  .scroll-indicator {
    position: absolute; bottom: 40px; left: 50%; transform: translateX(-50%);
    display: flex; flex-direction: column; align-items: center; gap: 8px;
    opacity: 0; animation: fade-up 1.2s 2.2s forwards;
  }
  .scroll-indicator p {
    font-family: 'Crimson Pro', serif; font-size: 0.75rem;
    letter-spacing: 0.25em; text-transform: uppercase; color: var(--muted);
  }
  .scroll-line {
    width: 1px; height: 60px;
    background: linear-gradient(180deg, var(--gold), transparent);
    animation: scroll-pulse 2s ease-in-out infinite;
  }
  @keyframes scroll-pulse {
    0%, 100% { opacity: 0.3; transform: scaleY(1); }
    50% { opacity: 1; transform: scaleY(1.15); }
  }

  @keyframes fade-up {
    from { opacity: 0; transform: translateY(28px); }
    to   { opacity: 1; transform: translateY(0); }
  }

  /* ========== SECTION SHARED ========== */
  section { position: relative; z-index: 2; }

  .section-divider {
    text-align: center; padding: 12px 0; font-size: 1.4rem;
    color: var(--gold); opacity: 0.4; letter-spacing: 0.3em;
  }

  /* ========== WHO IS RADHA RANI ========== */
  #radha {
    padding: 120px 60px;
    background: linear-gradient(180deg, var(--ink) 0%, var(--deep) 100%);
  }
  .radha-grid {
    max-width: 1200px; margin: 0 auto;
    display: grid; grid-template-columns: 1fr 1fr; gap: 80px;
    align-items: center;
  }
  .section-label {
    font-family: 'Cinzel Decorative', cursive;
    font-size: 0.65rem; letter-spacing: 0.5em;
    color: var(--rose); text-transform: uppercase; margin-bottom: 20px;
  }
  .section-title {
    font-family: 'Cinzel Decorative', cursive;
    font-size: clamp(1.8rem, 4vw, 3.2rem);
    color: var(--gold); line-height: 1.2; margin-bottom: 28px;
  }
  .section-body {
    font-size: 1.1rem; line-height: 1.95; color: var(--muted);
    font-weight: 300;
  }
  .section-body p { margin-bottom: 18px; }
  .radha-visual {
    display: flex; align-items: center; justify-content: center;
  }

  /* 3D Spinning Lotus */
  .lotus-3d {
    width: 340px; height: 340px; position: relative;
    perspective: 900px;
  }
  .lotus-inner {
    width: 100%; height: 100%; position: relative;
    transform-style: preserve-3d;
    animation: lotus-spin 18s linear infinite;
  }
  @keyframes lotus-spin { to { transform: rotateY(360deg) rotateX(15deg); } }

  .petal {
    position: absolute; top: 50%; left: 50%;
    width: 120px; height: 48px; border-radius: 50%;
    background: linear-gradient(135deg, var(--rose), #8B1A3A);
    transform-origin: 0 50%;
    box-shadow: 0 0 20px rgba(196,96,122,0.3);
  }

  .lotus-center {
    position: absolute; top: 50%; left: 50%;
    transform: translate(-50%, -50%);
    width: 80px; height: 80px; border-radius: 50%;
    background: radial-gradient(circle, var(--gold), #8B6914);
    box-shadow: 0 0 40px rgba(212,168,67,0.5);
    display: flex; align-items: center; justify-content: center;
    font-size: 2rem; z-index: 10;
  }

  /* ========== BHAKTI STEPS ========== */
  #bhakti {
    padding: 120px 60px;
    background: var(--deep);
  }
  .bhakti-header { text-align: center; margin-bottom: 80px; }

  .steps-grid {
    max-width: 1200px; margin: 0 auto;
    display: grid; grid-template-columns: repeat(3, 1fr);
    gap: 30px;
  }
  .step-card {
    background: rgba(255,255,255,0.03);
    border: 1px solid rgba(212,168,67,0.12);
    border-radius: 2px; padding: 48px 36px;
    position: relative; overflow: hidden;
    transition: all 0.5s ease; cursor: pointer;
  }
  .step-card::before {
    content: ''; position: absolute;
    top: 0; left: 0; right: 0; height: 2px;
    background: linear-gradient(90deg, transparent, var(--gold), transparent);
    transform: scaleX(0); transition: transform 0.5s;
  }
  .step-card:hover::before { transform: scaleX(1); }
  .step-card:hover {
    background: rgba(212,168,67,0.06);
    border-color: rgba(212,168,67,0.3);
    transform: translateY(-8px);
  }
  .step-card::after {
    content: ''; position: absolute; inset: 0;
    background: radial-gradient(circle at 50% 0%, rgba(212,168,67,0.08) 0%, transparent 70%);
    opacity: 0; transition: opacity 0.5s;
  }
  .step-card:hover::after { opacity: 1; }

  .step-num {
    font-family: 'Cinzel Decorative', cursive;
    font-size: 3.5rem; font-weight: 700;
    color: rgba(212,168,67,0.1);
    position: absolute; top: 24px; right: 28px;
    line-height: 1;
  }
  .step-icon {
    font-size: 2.4rem; margin-bottom: 20px;
    display: block; filter: drop-shadow(0 0 12px rgba(212,168,67,0.4));
  }
  .step-title {
    font-family: 'Cinzel Decorative', cursive;
    font-size: 1rem; color: var(--gold);
    margin-bottom: 14px; letter-spacing: 0.05em;
  }
  .step-desc {
    font-size: 1rem; line-height: 1.8; color: var(--muted);
    font-weight: 300;
  }

  /* ========== SLOKAS / CHANTS ========== */
  #slokas {
    padding: 120px 60px;
    background: linear-gradient(180deg, var(--deep) 0%, #240D2C 50%, var(--deep) 100%);
    text-align: center;
  }
  .sloka-container {
    max-width: 800px; margin: 0 auto;
  }
  .sloka-card {
    background: rgba(212,168,67,0.04);
    border: 1px solid rgba(212,168,67,0.15);
    border-radius: 2px; padding: 60px 64px;
    margin: 40px 0; position: relative;
    transition: all 0.6s ease;
  }
  .sloka-card:hover {
    background: rgba(212,168,67,0.08);
    box-shadow: 0 0 60px rgba(212,168,67,0.06);
  }
  .sloka-text {
    font-family: 'Cormorant Garamond', serif;
    font-size: 1.45rem; font-style: italic; font-weight: 300;
    color: var(--cream); line-height: 1.85;
    margin-bottom: 20px;
  }
  .sloka-translation {
    font-size: 0.95rem; color: var(--muted);
    letter-spacing: 0.05em; line-height: 1.7;
  }
  .sloka-source {
    margin-top: 20px; font-family: 'Cinzel Decorative', cursive;
    font-size: 0.6rem; letter-spacing: 0.3em;
    color: var(--gold); opacity: 0.6; text-transform: uppercase;
  }
  .quote-mark {
    font-size: 6rem; line-height: 0; color: var(--gold);
    opacity: 0.15; font-family: Georgia, serif;
    position: absolute; top: 30px; left: 28px;
  }

  /* ========== LEELAS ========== */
  #leelas {
    padding: 120px 60px;
    background: var(--deep);
  }
  .leelas-header { text-align: center; margin-bottom: 80px; }
  .leela-timeline {
    max-width: 900px; margin: 0 auto;
    position: relative;
  }
  .leela-timeline::before {
    content: ''; position: absolute;
    left: 50%; top: 0; bottom: 0; width: 1px;
    background: linear-gradient(180deg, transparent, var(--gold), transparent);
    opacity: 0.3; transform: translateX(-50%);
  }
  .leela-item {
    display: grid; grid-template-columns: 1fr 60px 1fr;
    gap: 0; margin-bottom: 60px; align-items: start;
  }
  .leela-item:nth-child(even) .leela-content { grid-column: 3; }
  .leela-item:nth-child(even) .leela-empty { grid-column: 1; }
  .leela-content {
    padding: 32px 36px;
    background: rgba(255,255,255,0.02);
    border: 1px solid rgba(212,168,67,0.1);
    border-radius: 2px; transition: all 0.4s;
  }
  .leela-content:hover {
    background: rgba(212,168,67,0.05);
    border-color: rgba(212,168,67,0.25);
  }
  .leela-dot {
    display: flex; align-items: flex-start; justify-content: center;
    padding-top: 36px;
  }
  .leela-dot span {
    width: 12px; height: 12px; border-radius: 50%;
    background: var(--gold); display: block;
    box-shadow: 0 0 20px rgba(212,168,67,0.4);
  }
  .leela-title {
    font-family: 'Cinzel Decorative', cursive;
    font-size: 0.85rem; color: var(--gold);
    margin-bottom: 10px; letter-spacing: 0.05em;
  }
  .leela-text {
    font-size: 1rem; line-height: 1.8; color: var(--muted);
    font-weight: 300;
  }

  /* ========== TEMPLE TOUR ========== */
  #temples {
    padding: 120px 60px;
    background: linear-gradient(180deg, var(--deep) 0%, var(--ink) 100%);
  }
  .temples-header { text-align: center; margin-bottom: 80px; }
  .temples-grid {
    max-width: 1200px; margin: 0 auto;
    display: grid; grid-template-columns: repeat(3, 1fr);
    gap: 24px;
  }
  .temple-card {
    border: 1px solid rgba(212,168,67,0.1);
    border-radius: 2px; overflow: hidden;
    transition: all 0.5s; cursor: pointer; position: relative;
  }
  .temple-card:hover {
    border-color: rgba(212,168,67,0.35);
    transform: translateY(-6px);
    box-shadow: 0 24px 60px rgba(0,0,0,0.4);
  }
  .temple-img {
    height: 200px; position: relative; overflow: hidden;
    display: flex; align-items: center; justify-content: center;
    font-size: 4rem;
  }
  .temple-img-bg {
    position: absolute; inset: 0;
    transition: transform 0.6s ease;
  }
  .temple-card:hover .temple-img-bg { transform: scale(1.08); }
  .temple-info { padding: 28px 28px 32px; background: rgba(18,8,24,0.9); }
  .temple-name {
    font-family: 'Cinzel Decorative', cursive;
    font-size: 0.85rem; color: var(--gold); margin-bottom: 8px;
  }
  .temple-location {
    font-size: 0.8rem; letter-spacing: 0.15em;
    text-transform: uppercase; color: var(--rose); margin-bottom: 12px;
  }
  .temple-desc {
    font-size: 0.95rem; line-height: 1.75; color: var(--muted);
    font-weight: 300;
  }

  /* ========== DAILY SADHANA ========== */
  #sadhana {
    padding: 120px 60px;
    background: var(--ink);
  }
  .sadhana-header { text-align: center; margin-bottom: 80px; }
  .sadhana-timeline {
    max-width: 700px; margin: 0 auto;
  }
  .sadhana-item {
    display: grid; grid-template-columns: 120px 1fr;
    gap: 32px; margin-bottom: 40px; align-items: start;
  }
  .sadhana-time {
    font-family: 'Cinzel Decorative', cursive;
    font-size: 0.7rem; letter-spacing: 0.15em;
    color: var(--gold); text-align: right;
    padding-top: 6px; line-height: 1.5;
  }
  .sadhana-practice {
    border-left: 1px solid rgba(212,168,67,0.2);
    padding-left: 32px; position: relative;
  }
  .sadhana-practice::before {
    content: ''; position: absolute;
    left: -4px; top: 8px;
    width: 7px; height: 7px; border-radius: 50%;
    background: var(--gold);
  }
  .sadhana-name {
    font-family: 'Cormorant Garamond', serif;
    font-size: 1.15rem; font-weight: 600;
    color: var(--cream); margin-bottom: 6px;
  }
  .sadhana-desc {
    font-size: 0.95rem; line-height: 1.75; color: var(--muted);
    font-weight: 300;
  }

  /* ========== INTERACTIVE 3D MANDALA ========== */
  #mandala-section {
    padding: 120px 60px;
    background: var(--deep);
    text-align: center;
  }
  .mandala-header { margin-bottom: 60px; }
  #mandala-canvas {
    width: 100%; max-width: 700px; height: 500px;
    margin: 0 auto; display: block;
    border: 1px solid rgba(212,168,67,0.1);
    border-radius: 2px;
    cursor: grab;
  }
  #mandala-canvas:active { cursor: grabbing; }
  .mandala-hint {
    margin-top: 20px; font-size: 0.85rem;
    color: var(--muted); font-style: italic;
    letter-spacing: 0.1em;
  }

  /* ========== ABOUT CREATOR ========== */
  #creator {
    padding: 140px 60px;
    background: linear-gradient(180deg, var(--ink) 0%, #0D0512 100%);
    position: relative; overflow: hidden;
  }
  #creator::before {
    content: ''; position: absolute; inset: 0;
    background: radial-gradient(ellipse at 50% 0%, rgba(196,96,122,0.06) 0%, transparent 60%);
  }
  .creator-inner {
    max-width: 1100px; margin: 0 auto;
    position: relative; z-index: 1;
    display: grid; grid-template-columns: 1fr 2fr; gap: 100px;
    align-items: start;
  }
  .creator-left { text-align: center; }
  .creator-avatar {
    width: 220px; height: 220px; border-radius: 50%;
    margin: 0 auto 32px;
    background: linear-gradient(135deg, var(--twilight) 0%, var(--deep) 100%);
    border: 2px solid rgba(212,168,67,0.25);
    display: flex; align-items: center; justify-content: center;
    font-size: 5rem;
    box-shadow: 0 0 60px rgba(212,168,67,0.1), 0 0 120px rgba(196,96,122,0.06);
    position: relative; overflow: hidden;
    animation: avatar-glow 6s ease-in-out infinite;
  }
  @keyframes avatar-glow {
    0%, 100% { box-shadow: 0 0 40px rgba(212,168,67,0.1); }
    50% { box-shadow: 0 0 80px rgba(212,168,67,0.25), 0 0 160px rgba(196,96,122,0.08); }
  }
  .creator-avatar::after {
    content: ''; position: absolute; inset: -2px;
    border-radius: 50%; border: 2px solid transparent;
    background: linear-gradient(135deg, var(--gold), var(--rose), var(--gold)) border-box;
    -webkit-mask: linear-gradient(#fff 0 0) padding-box, linear-gradient(#fff 0 0);
    -webkit-mask-composite: destination-out;
    mask-composite: exclude;
    animation: spin-slow 8s linear infinite;
  }
  .creator-name {
    font-family: 'Cinzel Decorative', cursive;
    font-size: 1.6rem; color: var(--gold); margin-bottom: 8px;
  }
  .creator-role {
    font-family: 'Crimson Pro', serif; font-size: 1rem;
    font-style: italic; color: var(--rose); margin-bottom: 28px;
    letter-spacing: 0.1em;
  }
  .creator-badges {
    display: flex; flex-wrap: wrap; gap: 10px; justify-content: center;
  }
  .badge {
    padding: 6px 16px; border: 1px solid rgba(212,168,67,0.2);
    font-size: 0.72rem; letter-spacing: 0.15em; text-transform: uppercase;
    color: var(--muted); border-radius: 2px;
    transition: all 0.3s;
  }
  .badge:hover {
    border-color: var(--gold); color: var(--gold);
    background: rgba(212,168,67,0.06);
  }

  .creator-right {}
  .creator-tag {
    font-family: 'Cinzel Decorative', cursive;
    font-size: 0.6rem; letter-spacing: 0.5em;
    color: var(--rose); text-transform: uppercase; margin-bottom: 16px;
  }
  .creator-heading {
    font-family: 'Cinzel Decorative', cursive;
    font-size: clamp(1.4rem, 3vw, 2.6rem);
    color: var(--gold); line-height: 1.25; margin-bottom: 32px;
  }
  .creator-bio {
    font-size: 1.08rem; line-height: 1.95;
    color: var(--muted); font-weight: 300;
    margin-bottom: 18px;
  }

  .creator-stats {
    display: grid; grid-template-columns: repeat(3, 1fr);
    gap: 24px; margin: 40px 0;
  }
  .stat-box {
    padding: 24px 20px; text-align: center;
    background: rgba(212,168,67,0.04);
    border: 1px solid rgba(212,168,67,0.1); border-radius: 2px;
    transition: all 0.4s;
  }
  .stat-box:hover {
    background: rgba(212,168,67,0.08);
    border-color: rgba(212,168,67,0.25);
    transform: translateY(-4px);
  }
  .stat-num {
    font-family: 'Cinzel Decorative', cursive;
    font-size: 1.8rem; color: var(--gold); display: block; margin-bottom: 6px;
  }
  .stat-label {
    font-size: 0.75rem; letter-spacing: 0.2em;
    text-transform: uppercase; color: var(--muted);
  }

  .creator-vision {
    background: rgba(196,96,122,0.06);
    border: 1px solid rgba(196,96,122,0.15);
    border-radius: 2px; padding: 32px 36px;
    margin-top: 32px;
    position: relative; overflow: hidden;
  }
  .creator-vision::before {
    content: '"'; position: absolute; top: -10px; left: 20px;
    font-size: 8rem; color: var(--rose); opacity: 0.08;
    font-family: Georgia, serif; line-height: 1;
  }
  .creator-vision p {
    font-family: 'Cormorant Garamond', serif;
    font-size: 1.18rem; font-style: italic;
    color: var(--cream); line-height: 1.9;
  }
  .creator-vision .vision-sig {
    margin-top: 16px; font-size: 0.8rem;
    letter-spacing: 0.2em; color: var(--rose);
    text-transform: uppercase;
  }

  .creator-tech {
    margin-top: 32px;
  }
  .tech-label {
    font-family: 'Cinzel Decorative', cursive;
    font-size: 0.6rem; letter-spacing: 0.3em;
    color: var(--gold); text-transform: uppercase; margin-bottom: 16px;
  }
  .tech-stack {
    display: flex; flex-wrap: wrap; gap: 10px;
  }
  .tech-pill {
    padding: 6px 18px;
    background: rgba(212,168,67,0.06);
    border: 1px solid rgba(212,168,67,0.15);
    font-size: 0.8rem; color: var(--muted);
    border-radius: 2px; font-family: 'Crimson Pro', serif;
    letter-spacing: 0.08em;
    transition: all 0.3s;
  }
  .tech-pill:hover {
    color: var(--gold); border-color: var(--gold);
    background: rgba(212,168,67,0.1);
  }

  /* ========== FOOTER ========== */
  footer {
    padding: 60px;
    background: var(--ink);
    border-top: 1px solid rgba(212,168,67,0.08);
    text-align: center;
  }
  .footer-logo {
    font-family: 'Cinzel Decorative', cursive;
    font-size: 1.4rem; color: var(--gold);
    margin-bottom: 20px;
    text-shadow: 0 0 30px rgba(212,168,67,0.3);
  }
  .footer-mantra {
    font-family: 'Cormorant Garamond', serif;
    font-size: 1.1rem; font-style: italic;
    color: var(--muted); margin-bottom: 32px; line-height: 1.8;
  }
  .footer-copy {
    font-size: 0.8rem; letter-spacing: 0.15em;
    color: rgba(200,168,138,0.4); text-transform: uppercase;
  }
  .footer-copy span { color: var(--rose); }

  /* Floating petals */
  .petal-float {
    position: fixed; pointer-events: none; z-index: 1;
    font-size: 1.2rem; opacity: 0;
    animation: petal-fall linear infinite;
  }
  @keyframes petal-fall {
    0% { transform: translateY(-20px) rotate(0deg); opacity: 0; }
    10% { opacity: 0.6; }
    90% { opacity: 0.3; }
    100% { transform: translateY(110vh) rotate(720deg); opacity: 0; }
  }

  /* Responsive */
  @media (max-width: 900px) {
    nav { padding: 16px 24px; }
    .nav-links { display: none; }
    .radha-grid, .creator-inner { grid-template-columns: 1fr; gap: 50px; }
    .steps-grid { grid-template-columns: 1fr; }
    .temples-grid { grid-template-columns: 1fr; }
    .creator-stats { grid-template-columns: repeat(3, 1fr); }
    section { padding: 80px 24px; }
    #radha, #bhakti, #slokas, #leelas, #temples, #sadhana, #mandala-section, #creator { padding: 80px 24px; }
    footer { padding: 40px 24px; }
    .leela-timeline::before { left: 16px; }
    .leela-item { grid-template-columns: 1fr; }
    .leela-dot { display: none; }
  }
</style>
</head>
<body>

<!-- Custom Cursor -->
<div class="cursor" id="cursor"></div>
<div class="cursor-trail" id="cursor-trail"></div>

<!-- Starfield Canvas -->
<canvas id="starfield"></canvas>

<!-- Floating Petals -->
<div id="petals"></div>

<!-- NAV -->
<nav>
  <div class="nav-logo">🌸 Radha Rani</div>
  <ul class="nav-links">
    <li><a href="#radha">About</a></li>
    <li><a href="#bhakti">Bhakti Path</a></li>
    <li><a href="#slokas">Slokas</a></li>
    <li><a href="#leelas">Leelas</a></li>
    <li><a href="#temples">Temples</a></li>
    <li><a href="#sadhana">Sadhana</a></li>
    <li><a href="#creator">Creator</a></li>
  </ul>
</nav>

<!-- HERO -->
<section id="hero">
  <div class="hero-glow"></div>
  <svg class="hero-mandala" viewBox="0 0 400 400" xmlns="http://www.w3.org/2000/svg">
    <circle cx="200" cy="200" r="190" fill="none" stroke="#D4A843" stroke-width="0.5"/>
    <circle cx="200" cy="200" r="160" fill="none" stroke="#D4A843" stroke-width="0.5"/>
    <circle cx="200" cy="200" r="130" fill="none" stroke="#C4607A" stroke-width="0.5"/>
    <circle cx="200" cy="200" r="80" fill="none" stroke="#D4A843" stroke-width="1"/>
    <g stroke="#D4A843" stroke-width="0.4" fill="none">
      <line x1="10" y1="200" x2="390" y2="200"/>
      <line x1="200" y1="10" x2="200" y2="390"/>
      <line x1="55" y1="55" x2="345" y2="345"/>
      <line x1="345" y1="55" x2="55" y2="345"/>
      <line x1="10" y1="130" x2="390" y2="270"/>
      <line x1="10" y1="270" x2="390" y2="130"/>
      <line x1="130" y1="10" x2="270" y2="390"/>
      <line x1="270" y1="10" x2="130" y2="390"/>
    </g>
    <g fill="#D4A843" opacity="0.7">
      <polygon points="200,20 205,195 200,190 195,195" />
      <polygon points="200,380 205,205 200,210 195,205" />
      <polygon points="20,200 195,205 190,200 195,195" />
      <polygon points="380,200 205,205 210,200 205,195" />
    </g>
    <circle cx="200" cy="200" r="20" fill="#D4A843" opacity="0.2"/>
    <circle cx="200" cy="200" r="8" fill="#D4A843" opacity="0.5"/>
  </svg>

  <p class="tag-line">✦ The Supreme Goddess of Devotion ✦</p>
  <h1 class="hero-title">Radha Rani</h1>
  <p class="hero-sub">Shri Vrindavan Dham ki Adhishwari</p>
  <p class="hero-desc">
    Embark upon the sacred Bhakti Path — a timeless journey into the boundless love, 
    divine grace, and eternal bliss of Shrimati Radharani, the beloved of Shri Krishna 
    and the Queen of Vrindavan.
  </p>
  <a href="#radha" class="btn-primary"><span>Begin the Journey</span></a>

  <div class="scroll-indicator">
    <p>Scroll</p>
    <div class="scroll-line"></div>
  </div>
</section>

<div class="section-divider">✦ ❋ ✦</div>

<!-- WHO IS RADHA RANI -->
<section id="radha">
  <div class="radha-grid">
    <div>
      <p class="section-label">✦ Parichay</p>
      <h2 class="section-title">Who is Shrimati Radharani?</h2>
      <div class="section-body">
        <p>Shrimati Radharani is the supreme Shakti — the internal potency — of Bhagavan Shri Krishna. She is the personification of divine love (Prema), compassion, and devotion (Bhakti). Without Radha, Krishna is incomplete; She is His very life-breath.</p>
        <p>Born in Barsana, the daughter of Vrishabhanu and Kirtida, Radha Rani is the highest ideal of a devotee. Her love for Krishna is unconditional, all-consuming, and transcends all earthly understanding — it is Mahabhava, the highest ecstasy of divine love.</p>
        <p>She is Hrishikesh Hrishikesha Sevana — the one who engages all senses in the service of the Lord. By meditating on Radha, one attains the highest form of devotion and ultimately reaches the lotus feet of Sri Hari.</p>
      </div>
    </div>
    <div class="radha-visual">
      <div class="lotus-3d" id="lotus3d">
        <div class="lotus-inner" id="lotus-inner">
          <!-- Petals generated by JS -->
          <div class="lotus-center">🌸</div>
        </div>
      </div>
    </div>
  </div>
</section>

<div class="section-divider">✦ ❋ ✦</div>

<!-- BHAKTI PATH STEPS -->
<section id="bhakti">
  <div class="bhakti-header">
    <p class="section-label" style="text-align:center">✦ Navavidha Bhakti ✦</p>
    <h2 class="section-title" style="text-align:center">The Nine Paths of Devotion</h2>
  </div>
  <div class="steps-grid">
    <div class="step-card">
      <span class="step-num">01</span>
      <span class="step-icon">🙏</span>
      <h3 class="step-title">Shravanam</h3>
      <p class="step-desc">Listening to the divine glories, names, and pastimes of Radha and Krishna with a pure and receptive heart. Every word becomes nectar for the soul.</p>
    </div>
    <div class="step-card">
      <span class="step-num">02</span>
      <span class="step-icon">🎵</span>
      <h3 class="step-title">Kirtanam</h3>
      <p class="step-desc">Singing the holy names and glories of the Lord. Kirtan dissolves the ego and fills the heart with divine Ananda. "Hare Krishna, Hare Rama..."</p>
    </div>
    <div class="step-card">
      <span class="step-num">03</span>
      <span class="step-icon">🌺</span>
      <h3 class="step-title">Smaranam</h3>
      <p class="step-desc">Constant remembrance and meditation upon the Lord's form, qualities, and pastimes. To always keep Radha-Krishna in one's awareness.</p>
    </div>
    <div class="step-card">
      <span class="step-num">04</span>
      <span class="step-icon">🪷</span>
      <h3 class="step-title">Pada Sevanam</h3>
      <p class="step-desc">Serving the lotus feet of the Lord with complete surrender. Offering flowers, Tulsi leaves, and one's entire being at Radha's feet.</p>
    </div>
    <div class="step-card">
      <span class="step-num">05</span>
      <span class="step-icon">⛩️</span>
      <h3 class="step-title">Archanam</h3>
      <p class="step-desc">Worship through rituals, offering incense, lamps, flowers, and food to the deity with devotion and a purified mind.</p>
    </div>
    <div class="step-card">
      <span class="step-num">06</span>
      <span class="step-icon">🙇</span>
      <h3 class="step-title">Vandanam</h3>
      <p class="step-desc">Prostration and prayer — humbling oneself completely before the divine. Offering all pride, all ego, at the altar of Radha Rani's grace.</p>
    </div>
    <div class="step-card">
      <span class="step-num">07</span>
      <span class="step-icon">🤲</span>
      <h3 class="step-title">Dasyam</h3>
      <p class="step-desc">Cultivating the attitude of a servant — serving with joy, love, and humility. Seeing oneself as a humble servant of the Supreme.</p>
    </div>
    <div class="step-card">
      <span class="step-num">08</span>
      <span class="step-icon">💞</span>
      <h3 class="step-title">Sakhyam</h3>
      <p class="step-desc">Developing a friendship with the Lord — an intimate, loving relationship filled with trust, openness, and joyous exchange.</p>
    </div>
    <div class="step-card">
      <span class="step-num">09</span>
      <span class="step-icon">✨</span>
      <h3 class="step-title">Atma Nivedanam</h3>
      <p class="step-desc">Complete self-surrender — offering one's entire self, body, mind, and soul at the feet of Radha Rani. The highest state of Bhakti.</p>
    </div>
  </div>
</section>

<div class="section-divider">✦ ❋ ✦</div>

<!-- SLOKAS -->
<section id="slokas">
  <div>
    <p class="section-label" style="text-align:center">✦ Sacred Verses ✦</p>
    <h2 class="section-title" style="text-align:center">Divine Slokas & Prayers</h2>
  </div>
  <div class="sloka-container">
    <div class="sloka-card">
      <span class="quote-mark">"</span>
      <p class="sloka-text">
        Tapta-kanchana-gaurangi, Radhe Vrindavaneshvari,<br>
        Vrishabhanu-sute Devi, Pranamami Hari-priye.
      </p>
      <p class="sloka-translation">
        O Radha, whose complexion glows like molten gold, O Queen of Vrindavan,<br>
        O daughter of Vrishabhanu, O beloved of Hari — I offer my humble obeisances unto You.
      </p>
      <p class="sloka-source">✦ Radha Pranama ✦</p>
    </div>

    <div class="sloka-card">
      <span class="quote-mark">"</span>
      <p class="sloka-text">
        Radha Krishna Prana Mora, Yugala Kishora,<br>
        Jivane Marane Gati, Aaro Nahi Mora.
      </p>
      <p class="sloka-translation">
        Radha and Krishna are my life and soul, the divine couple in their youthful form,<br>
        In life and in death, I have no other refuge — only Their lotus feet.
      </p>
      <p class="sloka-source">✦ Bhakti Geet ✦</p>
    </div>

    <div class="sloka-card">
      <span class="quote-mark">"</span>
      <p class="sloka-text">
        Hare Krishna Hare Krishna, Krishna Krishna Hare Hare,<br>
        Hare Rama Hare Rama, Rama Rama Hare Hare.
      </p>
      <p class="sloka-translation">
        The Maha-Mantra — the great chant for deliverance. These 16 holy names 
        contain the full power of the divine and carry the devotee to the highest realm of love.
      </p>
      <p class="sloka-source">✦ Maha Mantra — Kali Santarana Upanishad ✦</p>
    </div>
  </div>
</section>

<div class="section-divider">✦ ❋ ✦</div>

<!-- LEELAS -->
<section id="leelas">
  <div class="leelas-header">
    <p class="section-label" style="text-align:center">✦ Divine Pastimes ✦</p>
    <h2 class="section-title" style="text-align:center">Sacred Leelas of Radha Rani</h2>
  </div>
  <div class="leela-timeline">
    <div class="leela-item">
      <div class="leela-content">
        <h3 class="leela-title">The Raas Leela</h3>
        <p class="leela-text">The cosmic dance of love — where Radha and Krishna danced the eternal Raas on the banks of the Yamuna under the full moon of Sharad Purnima. Every Gopi became Radha, and Krishna multiplied Himself for each.</p>
      </div>
      <div class="leela-dot"><span></span></div>
      <div></div>
    </div>
    <div class="leela-item">
      <div></div>
      <div class="leela-dot"><span></span></div>
      <div class="leela-content">
        <h3 class="leela-title">Maan Leela</h3>
        <p class="leela-text">Radha's divine sulking — the Maan — is among the most celebrated pastimes. When Radha would feign anger, Krishna would go to extraordinary lengths to appease Her, singing Her glories and offering Himself at Her feet.</p>
      </div>
    </div>
    <div class="leela-item">
      <div class="leela-content">
        <h3 class="leela-title">Govardhan Leela — Radha's Role</h3>
        <p class="leela-text">During the Govardhan episode, it is said that Radha's devotion sustained Krishna. Her unwavering love empowered Him to lift the great mountain with ease, sheltering all the people of Braj.</p>
      </div>
      <div class="leela-dot"><span></span></div>
      <div></div>
    </div>
    <div class="leela-item">
      <div></div>
      <div class="leela-dot"><span></span></div>
      <div class="leela-content">
        <h3 class="leela-title">Viraha — The Pain of Separation</h3>
        <p class="leela-text">When Krishna left for Mathura, Radha's anguish of separation became the highest expression of love. Her Viraha — the divine longing — is considered equal to, if not greater than, union itself in Bhakti theology.</p>
      </div>
    </div>
    <div class="leela-item">
      <div class="leela-content">
        <h3 class="leela-title">Radha Kund — The Sacred Lake</h3>
        <p class="leela-text">Radha created the sacred Kund (lake) by the power of Her love. This holy body of water at Govardhan Hill is considered as dear to the Lord as Radha Herself — bathing there is said to grant the highest divine grace.</p>
      </div>
      <div class="leela-dot"><span></span></div>
      <div></div>
    </div>
  </div>
</section>

<div class="section-divider">✦ ❋ ✦</div>

<!-- TEMPLES -->
<section id="temples">
  <div class="temples-header">
    <p class="section-label" style="text-align:center">✦ Sacred Dhams ✦</p>
    <h2 class="section-title" style="text-align:center">Holy Temples of Radha Rani</h2>
  </div>
  <div class="temples-grid">
    <div class="temple-card">
      <div class="temple-img">
        <div class="temple-img-bg" style="background: linear-gradient(135deg, #3D1040 0%, #1A0A1E 100%);"></div>
        <span style="position:relative;z-index:1;font-size:3.5rem">🛕</span>
      </div>
      <div class="temple-info">
        <h3 class="temple-name">Shri Radha Rani Temple</h3>
        <p class="temple-location">Barsana, Uttar Pradesh</p>
        <p class="temple-desc">The divine birthplace of Radha Rani. Nestled atop Brahma Parvat hill, this temple is the most sacred site for Radha's devotees. Lathmar Holi here is a world-famous celebration.</p>
      </div>
    </div>
    <div class="temple-card">
      <div class="temple-img">
        <div class="temple-img-bg" style="background: linear-gradient(135deg, #2D1020 0%, #0D0512 100%);"></div>
        <span style="position:relative;z-index:1;font-size:3.5rem">🌸</span>
      </div>
      <div class="temple-info">
        <h3 class="temple-name">Radha Damodara Temple</h3>
        <p class="temple-location">Vrindavan, Uttar Pradesh</p>
        <p class="temple-desc">Founded by the great Vaishnava saint Jiva Goswami in 1542 CE. Home to the Samadhi of Rupa Goswami and beloved by Srila Prabhupada. A powerhouse of Bhakti tradition.</p>
      </div>
    </div>
    <div class="temple-card">
      <div class="temple-img">
        <div class="temple-img-bg" style="background: linear-gradient(135deg, #1A1A40 0%, #0A0818 100%);"></div>
        <span style="position:relative;z-index:1;font-size:3.5rem">✨</span>
      </div>
      <div class="temple-info">
        <h3 class="temple-name">Radha Raman Temple</h3>
        <p class="temple-location">Vrindavan, Uttar Pradesh</p>
        <p class="temple-desc">Founded by Gopala Bhatta Goswami. The Radha Raman deity is self-manifested (Swayambhu) and is among the most venerated deities in the entire Vaishnava tradition.</p>
      </div>
    </div>
    <div class="temple-card">
      <div class="temple-img">
        <div class="temple-img-bg" style="background: linear-gradient(135deg, #2A0A30 0%, #14061A 100%);"></div>
        <span style="position:relative;z-index:1;font-size:3.5rem">🪷</span>
      </div>
      <div class="temple-info">
        <h3 class="temple-name">Radha Kund</h3>
        <p class="temple-location">Govardhan, Uttar Pradesh</p>
        <p class="temple-desc">The most sacred lake in all of Braj Mandal, created by Radha's own hands. Bathing here, especially on Bahulastami, is said to be as meritorious as circumambulating the entire earth.</p>
      </div>
    </div>
    <div class="temple-card">
      <div class="temple-img">
        <div class="temple-img-bg" style="background: linear-gradient(135deg, #301028 0%, #180A14 100%);"></div>
        <span style="position:relative;z-index:1;font-size:3.5rem">🕌</span>
      </div>
      <div class="temple-info">
        <h3 class="temple-name">Nidhivan</h3>
        <p class="temple-location">Vrindavan, Uttar Pradesh</p>
        <p class="temple-desc">The mystical grove where Radha and Krishna are believed to perform the Raas Leela every night even today. The entire forest is sealed at sunset — no mortal may witness this divine secret.</p>
      </div>
    </div>
    <div class="temple-card">
      <div class="temple-img">
        <div class="temple-img-bg" style="background: linear-gradient(135deg, #28102A 0%, #120814 100%);"></div>
        <span style="position:relative;z-index:1;font-size:3.5rem">🌿</span>
      </div>
      <div class="temple-info">
        <h3 class="temple-name">Seva Kunj</h3>
        <p class="temple-location">Vrindavan, Uttar Pradesh</p>
        <p class="temple-desc">The sacred grove where Radha and Krishna would rest after the Raas dance. It is said that Radha's handmaidens (Sakhis) would personally serve the divine couple here.</p>
      </div>
    </div>
  </div>
</section>

<div class="section-divider">✦ ❋ ✦</div>

<!-- DAILY SADHANA -->
<section id="sadhana">
  <div class="sadhana-header">
    <p class="section-label" style="text-align:center">✦ Daily Practice ✦</p>
    <h2 class="section-title" style="text-align:center">The Bhakta's Daily Sadhana</h2>
  </div>
  <div class="sadhana-timeline">
    <div class="sadhana-item">
      <div class="sadhana-time">Brahma Muhurta<br>4:00 AM</div>
      <div class="sadhana-practice">
        <div class="sadhana-name">🌙 Mangalacharana — Auspicious Beginning</div>
        <p class="sadhana-desc">Rise before dawn. Chant the morning prayers, remember Radha-Krishna, and offer gratitude for this sacred day of devotion.</p>
      </div>
    </div>
    <div class="sadhana-item">
      <div class="sadhana-time">Morning<br>5:00–7:00 AM</div>
      <div class="sadhana-practice">
        <div class="sadhana-name">📿 Japa Meditation</div>
        <p class="sadhana-desc">Chant 16 rounds of the Maha Mantra on Tulsi beads — "Hare Krishna Hare Krishna, Krishna Krishna Hare Hare..." With full attention and love.</p>
      </div>
    </div>
    <div class="sadhana-item">
      <div class="sadhana-time">Dawn Puja<br>7:00–8:00 AM</div>
      <div class="sadhana-practice">
        <div class="sadhana-name">🪔 Deity Worship — Archana</div>
        <p class="sadhana-desc">Bathe and dress the deities, offer incense, lamps (Arati), flowers, Tulsi, and food (Bhoga). Sing the Ashtakam of Radha Rani.</p>
      </div>
    </div>
    <div class="sadhana-item">
      <div class="sadhana-time">Midday<br>12:00 PM</div>
      <div class="sadhana-practice">
        <div class="sadhana-name">📖 Shastra Paath — Scripture Study</div>
        <p class="sadhana-desc">Read from Srimad Bhagavatam, Chaitanya Charitamrita, or Brahma Vaivarta Purana. Contemplate the pastimes and teachings of Radha-Krishna.</p>
      </div>
    </div>
    <div class="sadhana-item">
      <div class="sadhana-time">Afternoon<br>4:00 PM</div>
      <div class="sadhana-practice">
        <div class="sadhana-name">🎶 Kirtan & Bhajans</div>
        <p class="sadhana-desc">Sing the bhajans of Mirabai, Surdas, and Raskhan. Let the music of devotion fill your heart and home with Radha's grace.</p>
      </div>
    </div>
    <div class="sadhana-item">
      <div class="sadhana-time">Sandhya Arati<br>6:30 PM</div>
      <div class="sadhana-practice">
        <div class="sadhana-name">🔔 Evening Arati</div>
        <p class="sadhana-desc">The beautiful Sandhya Arati — offering lamps and singing "Jaya Radha Madhava" as twilight descends. The most blissful moment of the day.</p>
      </div>
    </div>
    <div class="sadhana-item">
      <div class="sadhana-time">Night<br>9:00 PM</div>
      <div class="sadhana-practice">
        <div class="sadhana-name">🌸 Shayana Bhog & Rest</div>
        <p class="sadhana-desc">Offer the evening bhoga and prepare the deities for rest (Shayana). Recite the Radha Ashtakam and surrender to Radha's love before sleep.</p>
      </div>
    </div>
  </div>
</section>

<div class="section-divider">✦ ❋ ✦</div>

<!-- INTERACTIVE MANDALA -->
<section id="mandala-section">
  <div class="mandala-header">
    <p class="section-label">✦ Interactive Sacred Geometry ✦</p>
    <h2 class="section-title">The Living Mandala</h2>
  </div>
  <canvas id="mandala-canvas" width="700" height="500"></canvas>
  <p class="mandala-hint">✦ Move your mouse over the mandala to bring it to life ✦</p>
</section>

<div class="section-divider">✦ ❋ ✦</div>

<!-- ABOUT THE CREATOR -->
<section id="creator">
  <div class="creator-inner">
    <div class="creator-left">
      <div class="creator-avatar">👨‍💻</div>
      <h3 class="creator-name">Aryan Barolia</h3>
      <p class="creator-role">Web Developer & Digital Devotee</p>
      <div class="creator-badges">
        <span class="badge">🌸 Bhakta</span>
        <span class="badge">💻 Developer</span>
        <span class="badge">🎨 Designer</span>
        <span class="badge">🇮🇳 India</span>
        <span class="badge">✨ Creator</span>
      </div>
    </div>
    <div class="creator-right">
      <p class="creator-tag">✦ The Mind Behind This Journey ✦</p>
      <h2 class="creator-heading">Crafted with Love & Devotion by Aryan Barolia</h2>

      <p class="creator-bio">
        Namaste 🙏 I'm <strong style="color: var(--gold)">Aryan Barolia</strong> — a passionate web developer, digital creator, and devotee of Shri Radha Rani from the holy land of India. This website was born from the deepest corner of my heart, where devotion meets technology.
      </p>
      <p class="creator-bio">
        I believe that technology, when used with love and intention, becomes a form of seva (service). Creating this sacred digital space for Radha Rani is my way of offering something meaningful to the world — a bridge between the ancient wisdom of Bhakti and the modern digital age.
      </p>
      <p class="creator-bio">
        As a developer, I specialize in crafting immersive, visually rich web experiences. This project, with its 3D animations, sacred geometry, and devotional content, represents my deepest artistic and spiritual vision — a digital Vrindavan for seekers around the world.
      </p>

      <div class="creator-stats">
        <div class="stat-box">
          <span class="stat-num">∞</span>
          <span class="stat-label">Lines of Code Written with Love</span>
        </div>
        <div class="stat-box">
          <span class="stat-num">108</span>
          <span class="stat-label">Names of Radha Rani Honored</span>
        </div>
        <div class="stat-box">
          <span class="stat-num">1</span>
          <span class="stat-label">Heart Dedicated to Bhakti</span>
        </div>
      </div>

      <div class="creator-vision">
        <p>
          "My vision was to create not just a website, but a sacred digital sanctuary — 
          a place where any soul, anywhere in the world, can come and feel the presence of 
          Shrimati Radharani. Every pixel, every animation, every line of Sanskrit is an offering 
          at Her lotus feet. Jai Shri Radhe!"
        </p>
        <p class="vision-sig">✦ — Aryan Barolia, Creator & Devotee ✦</p>
      </div>

      <div class="creator-tech">
        <p class="tech-label">✦ Technologies Used in This Sacred Creation ✦</p>
        <div class="tech-stack">
          <span class="tech-pill">HTML5 Canvas</span>
          <span class="tech-pill">CSS3 Animations</span>
          <span class="tech-pill">Vanilla JavaScript</span>
          <span class="tech-pill">3D Transforms</span>
          <span class="tech-pill">Sacred Geometry</span>
          <span class="tech-pill">Particle Systems</span>
          <span class="tech-pill">Web Typography</span>
          <span class="tech-pill">Responsive Design</span>
          <span class="tech-pill">Cinzel Decorative Font</span>
          <span class="tech-pill">Cormorant Garamond</span>
        </div>
      </div>
    </div>
  </div>
</section>

<!-- FOOTER -->
<footer>
  <div class="footer-logo">🌸 Shri Radhe Vrindavaneshwari 🌸</div>
  <p class="footer-mantra">
    "Radhe Radhe bolo, shyam milenge raste mein,<br>
    Bolo Radhe Radhe, bolo Radhe Radhe..."
  </p>
  <p class="footer-copy">
    Crafted with 🌸 devotion by <span>Aryan Barolia</span> · Jai Shri Radhe · © 2025
  </p>
</footer>

<script>
// ===== CURSOR =====
const cursor = document.getElementById('cursor');
const trail = document.getElementById('cursor-trail');
let mx = 0, my = 0, tx = 0, ty = 0;
document.addEventListener('mousemove', e => {
  mx = e.clientX; my = e.clientY;
  cursor.style.left = mx + 'px';
  cursor.style.top = my + 'px';
});
setInterval(() => {
  tx += (mx - tx) * 0.15;
  ty += (my - ty) * 0.15;
  trail.style.left = tx + 'px';
  trail.style.top = ty + 'px';
}, 16);

// ===== STARFIELD =====
const sf = document.getElementById('starfield');
sf.width = window.innerWidth;
sf.height = window.innerHeight;
const sfCtx = sf.getContext('2d');
const stars = Array.from({length: 220}, () => ({
  x: Math.random() * sf.width,
  y: Math.random() * sf.height,
  r: Math.random() * 1.5 + 0.3,
  a: Math.random(),
  sp: Math.random() * 0.006 + 0.002,
  t: Math.random() * Math.PI * 2
}));
function drawStars() {
  sfCtx.clearRect(0, 0, sf.width, sf.height);
  stars.forEach(s => {
    s.t += s.sp;
    s.a = 0.3 + 0.5 * Math.sin(s.t);
    sfCtx.beginPath();
    sfCtx.arc(s.x, s.y, s.r, 0, Math.PI * 2);
    sfCtx.fillStyle = `rgba(212,168,67,${s.a})`;
    sfCtx.fill();
  });
  requestAnimationFrame(drawStars);
}
drawStars();
window.addEventListener('resize', () => {
  sf.width = window.innerWidth; sf.height = window.innerHeight;
});

// ===== LOTUS PETALS =====
const lotusInner = document.getElementById('lotus-inner');
for (let i = 0; i < 12; i++) {
  const p = document.createElement('div');
  p.className = 'petal';
  const angle = (i / 12) * 360;
  const r = i % 2 === 0 ? 110 : 70;
  const scale = i % 2 === 0 ? 1 : 0.65;
  p.style.cssText = `
    transform: rotate(${angle}deg) translateX(${r}px) scaleY(${scale});
    opacity: ${0.7 + 0.3 * Math.sin(i)};
    background: linear-gradient(135deg, ${i%3===0?'#C4607A':'#E8849A'}, ${i%2===0?'#8B1A3A':'#C4607A'});
  `;
  lotusInner.appendChild(p);
}

// ===== FLOATING PETALS =====
const petals = document.getElementById('petals');
const petalEmojis = ['🌸','🌺','🪷','✿','❀'];
for (let i = 0; i < 10; i++) {
  const p = document.createElement('div');
  p.className = 'petal-float';
  p.textContent = petalEmojis[i % petalEmojis.length];
  p.style.cssText = `
    left: ${Math.random() * 100}vw;
    animation-delay: ${Math.random() * 20}s;
    animation-duration: ${14 + Math.random() * 12}s;
    font-size: ${0.8 + Math.random() * 0.8}rem;
    top: -30px;
  `;
  petals.appendChild(p);
}

// ===== INTERACTIVE MANDALA =====
const mc = document.getElementById('mandala-canvas');
const mCtx = mc.getContext('2d');
let mAngle = 0, mMouseX = mc.width/2, mMouseY = mc.height/2;
mc.addEventListener('mousemove', e => {
  const r = mc.getBoundingClientRect();
  mMouseX = e.clientX - r.left;
  mMouseY = e.clientY - r.top;
});

function drawMandala() {
  mCtx.clearRect(0, 0, mc.width, mc.height);
  const cx = mc.width / 2, cy = mc.height / 2;
  const distX = (mMouseX - cx) / cx;
  const distY = (mMouseY - cy) / cy;
  const influence = Math.sqrt(distX*distX + distY*distY);
  const speed = 0.006 + influence * 0.018;
  mAngle += speed;

  // Background glow
  const grd = mCtx.createRadialGradient(cx, cy, 0, cx, cy, 240);
  grd.addColorStop(0, `rgba(196,96,122,${0.06 + influence * 0.08})`);
  grd.addColorStop(0.5, `rgba(212,168,67,0.03)`);
  grd.addColorStop(1, 'transparent');
  mCtx.fillStyle = grd;
  mCtx.fillRect(0, 0, mc.width, mc.height);

  const layers = [
    { r: 200, petals: 16, color: 'rgba(212,168,67,0.35)', rev: false },
    { r: 160, petals: 12, color: 'rgba(196,96,122,0.4)', rev: true },
    { r: 120, petals: 8,  color: 'rgba(212,168,67,0.5)', rev: false },
    { r: 80,  petals: 8,  color: 'rgba(196,96,122,0.6)', rev: true },
    { r: 45,  petals: 6,  color: 'rgba(232,132,154,0.7)', rev: false },
  ];

  layers.forEach((layer, li) => {
    const a = mAngle * (layer.rev ? -1 : 1) * (1 + li * 0.2);
    mCtx.save();
    mCtx.translate(cx, cy);
    mCtx.rotate(a + distX * 0.3);
    for (let i = 0; i < layer.petals; i++) {
      const angle = (i / layer.petals) * Math.PI * 2;
      mCtx.save();
      mCtx.rotate(angle);
      mCtx.beginPath();
      mCtx.ellipse(layer.r / 2, 0, layer.r * 0.28, layer.r * 0.11, 0, 0, Math.PI * 2);
      mCtx.fillStyle = layer.color;
      mCtx.fill();
      mCtx.restore();
    }
    // Circle
    mCtx.beginPath();
    mCtx.arc(0, 0, layer.r, 0, Math.PI * 2);
    mCtx.strokeStyle = layer.color.replace('0.', '0.15').replace(/, 0\.\d+\)/, ', 0.15)');
    mCtx.lineWidth = 0.5;
    mCtx.stroke();
    mCtx.restore();
  });

  // Center
  const cg = mCtx.createRadialGradient(cx, cy, 0, cx, cy, 30);
  cg.addColorStop(0, '#D4A843');
  cg.addColorStop(1, '#8B6914');
  mCtx.beginPath();
  mCtx.arc(cx, cy, 22, 0, Math.PI * 2);
  mCtx.fillStyle = cg;
  mCtx.fill();
  mCtx.font = '20px serif';
  mCtx.textAlign = 'center';
  mCtx.textBaseline = 'middle';
  mCtx.fillText('🌸', cx, cy);

  // Spoke lines
  mCtx.save();
  mCtx.translate(cx, cy);
  mCtx.rotate(mAngle * 0.3);
  for (let i = 0; i < 16; i++) {
    const a = (i / 16) * Math.PI * 2;
    mCtx.beginPath();
    mCtx.moveTo(Math.cos(a) * 25, Math.sin(a) * 25);
    mCtx.lineTo(Math.cos(a) * 195, Math.sin(a) * 195);
    mCtx.strokeStyle = 'rgba(212,168,67,0.06)';
    mCtx.lineWidth = 0.5;
    mCtx.stroke();
  }
  mCtx.restore();

  requestAnimationFrame(drawMandala);
}
drawMandala();

// ===== SCROLL REVEAL =====
const observer = new IntersectionObserver((entries) => {
  entries.forEach(e => {
    if (e.isIntersecting) {
      e.target.style.opacity = '1';
      e.target.style.transform = 'translateY(0)';
    }
  });
}, { threshold: 0.1 });

document.querySelectorAll('.step-card, .sloka-card, .leela-content, .temple-card, .sadhana-item, .stat-box').forEach(el => {
  el.style.opacity = '0';
  el.style.transform = 'translateY(30px)';
  el.style.transition = 'opacity 0.7s ease, transform 0.7s ease';
  observer.observe(el);
});
</script>
</body>
</html>
