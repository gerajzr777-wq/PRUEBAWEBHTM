# PRUEBAWEBHTM
WEB PROFESIONAL
<!DOCTYPE html>
<html lang="es">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<meta name="description" content="HTMC Servicios Especializados Aeronáuticos — Taller AFAC No. 400. Mantenimiento, certificación periódica de GSE, NDT, calibración y soporte técnico aeronáutico en México.">
<title>HTMC Servicios Especializados Aeronáuticos</title>
<link rel="preconnect" href="https://fonts.googleapis.com">
<link rel="preconnect" href="https://fonts.gstatic.com" crossorigin>
<link href="https://fonts.googleapis.com/css2?family=Inter:wght@300;400;500;600&display=swap" rel="stylesheet">
<style>
  *, *::before, *::after { box-sizing: border-box; margin: 0; padding: 0; }

  :root {
    --black: #0a0a0a;
    --dark: #1a1a1a;
    --dark-mid: #111111;
    --white: #f5f5f7;
    --gray-100: #e8e8ed;
    --gray-400: #86868b;
    --gray-600: #48484a;
    --accent: #2563eb;
    --accent-light: #3b82f6;
    --gold: #c8a96e;
    --max: 980px;
    --max-wide: 1200px;
  }

  html { scroll-behavior: smooth; }

  body {
    font-family: 'Inter', -apple-system, BlinkMacSystemFont, sans-serif;
    background: var(--black);
    color: var(--white);
    overflow-x: hidden;
    -webkit-font-smoothing: antialiased;
  }

  /* ── NAV ── */
  nav {
    position: fixed;
    top: 0; left: 0; right: 0;
    z-index: 100;
    padding: 0 40px;
    height: 56px;
    display: flex;
    align-items: center;
    justify-content: space-between;
    background: rgba(10,10,10,0.72);
    backdrop-filter: saturate(180%) blur(20px);
    -webkit-backdrop-filter: saturate(180%) blur(20px);
    border-bottom: 0.5px solid rgba(255,255,255,0.08);
    transition: background 0.3s;
  }

  .nav-logo {
    font-size: 17px;
    font-weight: 600;
    letter-spacing: -0.02em;
    color: var(--white);
    text-decoration: none;
  }
  .nav-logo span { color: var(--gold); }

  .nav-links {
    display: flex;
    gap: 32px;
    list-style: none;
  }
  .nav-links a {
    font-size: 13px;
    color: var(--gray-400);
    text-decoration: none;
    transition: color 0.2s;
  }
  .nav-links a:hover { color: var(--white); }

  .nav-cta {
    font-size: 13px;
    padding: 7px 18px;
    border-radius: 980px;
    background: var(--accent);
    color: #fff;
    text-decoration: none;
    font-weight: 500;
    transition: background 0.2s, transform 0.15s;
  }
  .nav-cta:hover { background: var(--accent-light); transform: scale(1.02); }

  /* ── HERO ── */
  .hero {
    position: relative;
    min-height: 100vh;
    display: flex;
    flex-direction: column;
    align-items: center;
    justify-content: center;
    text-align: center;
    padding: 120px 24px 80px;
    overflow: hidden;
  }

  .hero-bg {
    position: absolute;
    inset: 0;
    z-index: 0;
  }
  .hero-bg img {
    width: 100%; height: 100%;
    object-fit: cover;
    object-position: center;
    filter: brightness(0.32);
  }
  .hero-bg::after {
    content: '';
    position: absolute;
    inset: 0;
    background: linear-gradient(to bottom, rgba(10,10,10,0.2) 0%, rgba(10,10,10,0.85) 100%);
  }

  .hero-inner {
    position: relative;
    z-index: 1;
    max-width: 780px;
  }

  .hero-eyebrow {
    display: inline-block;
    font-size: 12px;
    font-weight: 500;
    letter-spacing: 0.14em;
    text-transform: uppercase;
    color: var(--gold);
    margin-bottom: 28px;
    opacity: 0;
    transform: translateY(16px);
    animation: fadeUp 0.8s ease 0.2s forwards;
  }

  .hero h1 {
    font-size: clamp(44px, 7vw, 88px);
    font-weight: 500;
    line-height: 1.04;
    letter-spacing: -0.03em;
    margin-bottom: 28px;
    opacity: 0;
    transform: translateY(20px);
    animation: fadeUp 0.9s ease 0.4s forwards;
  }

  .hero-sub {
    font-size: clamp(16px, 2vw, 20px);
    font-weight: 300;
    color: var(--gray-100);
    line-height: 1.6;
    max-width: 620px;
    margin: 0 auto 48px;
    opacity: 0;
    transform: translateY(20px);
    animation: fadeUp 0.9s ease 0.6s forwards;
  }

  .hero-actions {
    display: flex;
    gap: 16px;
    justify-content: center;
    flex-wrap: wrap;
    opacity: 0;
    transform: translateY(20px);
    animation: fadeUp 0.9s ease 0.8s forwards;
  }

  .btn-primary {
    font-size: 15px;
    font-weight: 500;
    padding: 14px 32px;
    border-radius: 980px;
    background: var(--accent);
    color: #fff;
    text-decoration: none;
    transition: background 0.2s, transform 0.15s;
  }
  .btn-primary:hover { background: var(--accent-light); transform: scale(1.02); }

  .btn-secondary {
    font-size: 15px;
    font-weight: 400;
    padding: 14px 32px;
    border-radius: 980px;
    border: 1px solid rgba(255,255,255,0.25);
    color: var(--white);
    text-decoration: none;
    transition: border-color 0.2s, background 0.2s, transform 0.15s;
  }
  .btn-secondary:hover { border-color: rgba(255,255,255,0.5); background: rgba(255,255,255,0.06); transform: scale(1.02); }

  .hero-badge {
    position: absolute;
    bottom: 48px;
    left: 50%;
    transform: translateX(-50%);
    font-size: 11px;
    color: var(--gray-400);
    letter-spacing: 0.06em;
    opacity: 0;
    animation: fadeUp 1s ease 1.2s forwards;
    white-space: nowrap;
  }
  .hero-badge strong { color: var(--gold); font-weight: 500; }

  /* ── SCROLL INDICATOR ── */
  .scroll-hint {
    position: absolute;
    bottom: 24px;
    left: 50%;
    transform: translateX(-50%);
    display: flex;
    flex-direction: column;
    align-items: center;
    gap: 6px;
    opacity: 0;
    animation: fadeUp 1s ease 1.4s forwards;
  }
  .scroll-hint span { font-size: 10px; letter-spacing: 0.1em; color: var(--gray-400); text-transform: uppercase; }
  .scroll-dot {
    width: 1.5px;
    height: 36px;
    background: linear-gradient(to bottom, var(--gold), transparent);
    animation: scrollPulse 1.8s ease-in-out infinite;
  }

  /* ── STATS BAND ── */
  .stats-band {
    background: var(--dark-mid);
    border-top: 0.5px solid rgba(255,255,255,0.07);
    border-bottom: 0.5px solid rgba(255,255,255,0.07);
    padding: 56px 40px;
  }
  .stats-grid {
    max-width: var(--max-wide);
    margin: 0 auto;
    display: grid;
    grid-template-columns: repeat(4, 1fr);
    gap: 24px;
    text-align: center;
  }
  .stat-item { padding: 16px; }
  .stat-num {
    font-size: clamp(36px, 4vw, 52px);
    font-weight: 300;
    letter-spacing: -0.03em;
    color: var(--white);
    line-height: 1;
    margin-bottom: 8px;
  }
  .stat-num em { font-style: normal; color: var(--gold); }
  .stat-label { font-size: 13px; color: var(--gray-400); line-height: 1.4; }

  /* ── SECTIONS GENERIC ── */
  section { position: relative; overflow: hidden; }

  .section-dark { background: var(--black); }
  .section-mid { background: var(--dark-mid); }
  .section-light { background: #f5f5f7; color: #1d1d1f; }
  .section-light .section-eyebrow { color: var(--accent); }
  .section-light p, .section-light .body-text { color: #48484a; }

  .section-inner {
    max-width: var(--max);
    margin: 0 auto;
    padding: 120px 40px;
  }

  .section-inner-wide {
    max-width: var(--max-wide);
    margin: 0 auto;
    padding: 120px 40px;
  }

  .section-eyebrow {
    font-size: 12px;
    font-weight: 500;
    letter-spacing: 0.14em;
    text-transform: uppercase;
    color: var(--gold);
    margin-bottom: 20px;
    display: block;
  }

  .section-title {
    font-size: clamp(32px, 4.5vw, 56px);
    font-weight: 500;
    letter-spacing: -0.025em;
    line-height: 1.08;
    margin-bottom: 28px;
  }

  .body-text {
    font-size: 17px;
    font-weight: 300;
    line-height: 1.7;
    color: var(--gray-100);
    max-width: 640px;
  }

  /* ── REVEAL ANIMATION ── */
  .reveal {
    opacity: 0;
    transform: translateY(36px);
    transition: opacity 0.8s ease, transform 0.8s ease;
  }
  .reveal.visible {
    opacity: 1;
    transform: translateY(0);
  }
  .reveal-delay-1 { transition-delay: 0.1s; }
  .reveal-delay-2 { transition-delay: 0.2s; }
  .reveal-delay-3 { transition-delay: 0.3s; }
  .reveal-delay-4 { transition-delay: 0.45s; }

  /* ── INTRO / COMPROMISO ── */
  .intro-section {
    background: var(--dark-mid);
    border-top: 0.5px solid rgba(255,255,255,0.07);
  }
  .intro-inner {
    max-width: var(--max);
    margin: 0 auto;
    padding: 120px 40px;
    text-align: center;
  }
  .intro-inner .section-title { max-width: 700px; margin: 0 auto 32px; }
  .intro-inner .body-text { margin: 0 auto 20px; text-align: center; }
  .divider-line {
    width: 48px;
    height: 2px;
    background: var(--gold);
    margin: 40px auto;
    border-radius: 2px;
  }

  /* ── ABOUT / NOSOTROS ── */
  .about-grid {
    display: grid;
    grid-template-columns: 1fr 1fr;
    gap: 80px;
    align-items: center;
  }
  .about-image {
    border-radius: 20px;
    overflow: hidden;
    aspect-ratio: 4/3;
  }
  .about-image img {
    width: 100%; height: 100%;
    object-fit: cover;
    transition: transform 0.6s ease;
  }
  .about-image:hover img { transform: scale(1.04); }
  .about-badge {
    display: inline-flex;
    align-items: center;
    gap: 8px;
    font-size: 12px;
    font-weight: 500;
    letter-spacing: 0.05em;
    color: var(--gold);
    border: 1px solid rgba(200,169,110,0.3);
    border-radius: 980px;
    padding: 6px 16px;
    margin-bottom: 28px;
  }
  .about-badge::before {
    content: '';
    width: 6px; height: 6px;
    background: var(--gold);
    border-radius: 50%;
  }

  /* ── MISION/VISION SIDE BY SIDE ── */
  .mv-grid {
    display: grid;
    grid-template-columns: 1fr 1fr;
    gap: 2px;
  }
  .mv-card {
    padding: 64px 56px;
    border: 0.5px solid rgba(255,255,255,0.08);
  }
  .mv-card:first-child { border-right: none; }
  .mv-icon {
    width: 40px; height: 40px;
    margin-bottom: 28px;
    opacity: 0.6;
  }
  .mv-card h3 {
    font-size: 13px;
    font-weight: 500;
    letter-spacing: 0.12em;
    text-transform: uppercase;
    color: var(--gold);
    margin-bottom: 20px;
  }
  .mv-card p {
    font-size: 16px;
    font-weight: 300;
    line-height: 1.7;
    color: var(--gray-100);
    margin-bottom: 16px;
  }

  /* ── CALIDAD ── */
  .calidad-section { background: #f5f5f7; color: #1d1d1f; }
  .calidad-section .section-eyebrow { color: var(--accent); }
  .calidad-inner {
    max-width: var(--max);
    margin: 0 auto;
    padding: 120px 40px;
    text-align: center;
  }
  .calidad-inner .section-title { color: #1d1d1f; margin: 0 auto 24px; }
  .calidad-inner .body-text { color: #48484a; margin: 0 auto; text-align: center; }
  .calidad-tags {
    display: flex;
    flex-wrap: wrap;
    gap: 12px;
    justify-content: center;
    margin-top: 48px;
  }
  .calidad-tag {
    font-size: 13px;
    font-weight: 500;
    padding: 10px 22px;
    border-radius: 980px;
    border: 1.5px solid #1d1d1f;
    color: #1d1d1f;
  }

  /* ── SERVICIOS HERO ── */
  .servicios-intro {
    text-align: center;
    padding: 120px 40px 80px;
    max-width: var(--max);
    margin: 0 auto;
  }

  /* ── SERVICIO CARDS ── */
  .servicios-grid {
    display: grid;
    grid-template-columns: repeat(3, 1fr);
    gap: 2px;
    background: rgba(255,255,255,0.05);
    padding: 0;
  }

  .servicio-card {
    background: var(--dark);
    padding: 52px 44px;
    border: 0.5px solid rgba(255,255,255,0.06);
    transition: background 0.3s;
    cursor: default;
    position: relative;
    overflow: hidden;
  }
  .servicio-card::before {
    content: '';
    position: absolute;
    bottom: 0; left: 0; right: 0;
    height: 2px;
    background: var(--gold);
    transform: scaleX(0);
    transform-origin: left;
    transition: transform 0.4s ease;
  }
  .servicio-card:hover { background: #1f1f1f; }
  .servicio-card:hover::before { transform: scaleX(1); }

  .servicio-num {
    font-size: 11px;
    font-weight: 500;
    letter-spacing: 0.1em;
    color: var(--gray-600);
    margin-bottom: 32px;
  }
  .servicio-icon {
    width: 44px; height: 44px;
    margin-bottom: 24px;
    opacity: 0.5;
    transition: opacity 0.3s;
  }
  .servicio-card:hover .servicio-icon { opacity: 0.85; }

  .servicio-card h3 {
    font-size: 20px;
    font-weight: 500;
    letter-spacing: -0.01em;
    margin-bottom: 16px;
    line-height: 1.2;
  }
  .servicio-card p {
    font-size: 14px;
    font-weight: 300;
    line-height: 1.7;
    color: var(--gray-400);
  }

  /* ── GSE CERTIFICACIÓN (FEATURED) ── */
  .gse-section { background: var(--dark-mid); }
  .gse-inner {
    max-width: var(--max-wide);
    margin: 0 auto;
    padding: 120px 40px;
  }
  .gse-header {
    display: grid;
    grid-template-columns: 1fr 1fr;
    gap: 80px;
    align-items: end;
    margin-bottom: 80px;
  }
  .gse-header .body-text { max-width: 480px; }

  .gse-equipos {
    display: grid;
    grid-template-columns: repeat(3, 1fr);
    gap: 16px;
  }
  .equipo-card {
    background: rgba(255,255,255,0.03);
    border: 0.5px solid rgba(255,255,255,0.08);
    border-radius: 16px;
    padding: 32px 28px;
    transition: background 0.3s, border-color 0.3s, transform 0.3s;
  }
  .equipo-card:hover {
    background: rgba(255,255,255,0.06);
    border-color: rgba(200,169,110,0.3);
    transform: translateY(-4px);
  }
  .equipo-img {
    width: 100%;
    aspect-ratio: 16/9;
    object-fit: cover;
    border-radius: 10px;
    margin-bottom: 20px;
    opacity: 0.8;
    transition: opacity 0.3s;
  }
  .equipo-card:hover .equipo-img { opacity: 1; }
  .equipo-card h4 {
    font-size: 15px;
    font-weight: 500;
    margin-bottom: 10px;
    color: var(--white);
  }
  .equipo-card p {
    font-size: 13px;
    font-weight: 300;
    line-height: 1.6;
    color: var(--gray-400);
  }
  .equipo-norm {
    display: inline-block;
    margin-top: 12px;
    font-size: 11px;
    font-weight: 500;
    letter-spacing: 0.06em;
    color: var(--gold);
    text-transform: uppercase;
  }

  /* ── SOPORTE TECNICO ── */
  .soporte-section {
    background: var(--black);
  }
  .soporte-inner {
    max-width: var(--max-wide);
    margin: 0 auto;
    padding: 120px 40px;
    display: grid;
    grid-template-columns: 1fr 1fr;
    gap: 80px;
    align-items: center;
  }
  .soporte-image {
    border-radius: 20px;
    overflow: hidden;
    aspect-ratio: 3/2;
  }
  .soporte-image img {
    width: 100%; height: 100%;
    object-fit: cover;
    filter: brightness(0.85);
    transition: transform 0.6s ease;
  }
  .soporte-image:hover img { transform: scale(1.04); }
  .aog-badge {
    display: inline-flex;
    align-items: center;
    gap: 10px;
    margin-top: 40px;
    padding: 16px 24px;
    background: rgba(200,169,110,0.08);
    border: 1px solid rgba(200,169,110,0.25);
    border-radius: 12px;
    font-size: 14px;
    color: var(--gold);
    font-weight: 400;
    line-height: 1.5;
  }
  .aog-dot {
    width: 8px; height: 8px;
    background: var(--gold);
    border-radius: 50%;
    flex-shrink: 0;
    animation: pulse 2s ease-in-out infinite;
  }

  /* ── IMAGEN STICKY PARALLAX ── */
  .sticky-section {
    display: grid;
    grid-template-columns: 1fr 1fr;
    min-height: 100vh;
  }
  .sticky-image-col {
    position: sticky;
    top: 0;
    height: 100vh;
    overflow: hidden;
  }
  .sticky-image-col img {
    width: 100%; height: 100%;
    object-fit: cover;
    filter: brightness(0.75);
  }
  .sticky-text-col {
    padding: 120px 60px;
    background: var(--dark-mid);
  }
  .sticky-block {
    min-height: 60vh;
    display: flex;
    flex-direction: column;
    justify-content: center;
    padding: 40px 0;
    border-bottom: 0.5px solid rgba(255,255,255,0.07);
  }
  .sticky-block:last-child { border-bottom: none; }
  .sticky-block h3 {
    font-size: 28px;
    font-weight: 500;
    letter-spacing: -0.015em;
    margin-bottom: 20px;
    line-height: 1.15;
  }
  .sticky-block p {
    font-size: 16px;
    font-weight: 300;
    line-height: 1.7;
    color: var(--gray-100);
  }

  /* ── GESTIÓN DOCUMENTAL ── */
  .documental-section { background: #f5f5f7; color: #1d1d1f; }
  .documental-inner {
    max-width: var(--max-wide);
    margin: 0 auto;
    padding: 120px 40px;
    display: grid;
    grid-template-columns: 1fr 1fr;
    gap: 80px;
    align-items: center;
  }
  .documental-section .section-eyebrow { color: var(--accent); }
  .documental-section .section-title { color: #1d1d1f; }
  .documental-section .body-text { color: #48484a; }
  .doc-list {
    list-style: none;
    margin-top: 32px;
  }
  .doc-list li {
    display: flex;
    align-items: flex-start;
    gap: 16px;
    padding: 20px 0;
    border-bottom: 0.5px solid rgba(0,0,0,0.08);
    font-size: 15px;
    color: #1d1d1f;
    font-weight: 400;
  }
  .doc-list li::before {
    content: '';
    width: 6px; height: 6px;
    background: var(--accent);
    border-radius: 50%;
    margin-top: 8px;
    flex-shrink: 0;
  }
  .documental-image {
    border-radius: 20px;
    overflow: hidden;
    aspect-ratio: 4/3;
  }
  .documental-image img {
    width: 100%; height: 100%;
    object-fit: cover;
    transition: transform 0.6s ease;
  }
  .documental-image:hover img { transform: scale(1.04); }

  /* ── CAPACITACION ── */
  .capacitacion-section { background: var(--dark-mid); }
  .capacitacion-inner {
    max-width: var(--max-wide);
    margin: 0 auto;
    padding: 120px 40px;
    display: grid;
    grid-template-columns: 1fr 1fr;
    gap: 80px;
    align-items: center;
  }
  .capacitacion-image {
    border-radius: 20px;
    overflow: hidden;
    aspect-ratio: 4/3;
  }
  .capacitacion-image img {
    width: 100%; height: 100%;
    object-fit: cover;
    filter: brightness(0.85);
    transition: transform 0.6s ease;
  }
  .capacitacion-image:hover img { transform: scale(1.04); }

  /* ── CONTACTO CTA ── */
  .cta-section {
    background: var(--black);
    text-align: center;
  }
  .cta-inner {
    max-width: var(--max);
    margin: 0 auto;
    padding: 160px 40px;
  }
  .cta-inner .section-title { margin-bottom: 24px; }
  .cta-inner .body-text { margin: 0 auto 48px; text-align: center; }
  .cta-contact-info {
    display: flex;
    gap: 48px;
    justify-content: center;
    flex-wrap: wrap;
    margin-top: 56px;
    padding-top: 56px;
    border-top: 0.5px solid rgba(255,255,255,0.08);
  }
  .contact-item { text-align: center; }
  .contact-label {
    font-size: 11px;
    letter-spacing: 0.1em;
    text-transform: uppercase;
    color: var(--gray-400);
    margin-bottom: 8px;
  }
  .contact-value {
    font-size: 16px;
    font-weight: 400;
    color: var(--white);
    text-decoration: none;
    transition: color 0.2s;
  }
  .contact-value:hover { color: var(--gold); }

  /* ── FOOTER ── */
  footer {
    background: var(--dark-mid);
    border-top: 0.5px solid rgba(255,255,255,0.07);
    padding: 48px 40px;
  }
  .footer-inner {
    max-width: var(--max-wide);
    margin: 0 auto;
    display: flex;
    align-items: center;
    justify-content: space-between;
    flex-wrap: wrap;
    gap: 24px;
  }
  .footer-brand { font-size: 14px; font-weight: 500; }
  .footer-brand span { color: var(--gold); }
  .footer-links { display: flex; gap: 28px; }
  .footer-links a { font-size: 13px; color: var(--gray-400); text-decoration: none; transition: color 0.2s; }
  .footer-links a:hover { color: var(--white); }
  .footer-copy { font-size: 12px; color: var(--gray-600); }

  /* ── KEYFRAMES ── */
  @keyframes fadeUp {
    to { opacity: 1; transform: translateY(0); }
  }
  @keyframes scrollPulse {
    0%, 100% { opacity: 0.4; transform: scaleY(0.6); }
    50% { opacity: 1; transform: scaleY(1); }
  }
  @keyframes pulse {
    0%, 100% { opacity: 1; transform: scale(1); }
    50% { opacity: 0.5; transform: scale(0.7); }
  }

  /* ── RESPONSIVE ── */
  @media (max-width: 900px) {
    nav { padding: 0 20px; }
    .nav-links { display: none; }
    .stats-grid { grid-template-columns: repeat(2, 1fr); }
    .about-grid, .soporte-inner, .documental-inner, .capacitacion-inner { grid-template-columns: 1fr; gap: 48px; }
    .mv-grid { grid-template-columns: 1fr; }
    .mv-card:first-child { border-right: 0.5px solid rgba(255,255,255,0.08); border-bottom: none; }
    .servicios-grid { grid-template-columns: 1fr; }
    .gse-equipos { grid-template-columns: 1fr; }
    .gse-header { grid-template-columns: 1fr; gap: 32px; }
    .sticky-section { grid-template-columns: 1fr; }
    .sticky-image-col { position: relative; height: 50vw; }
    .sticky-text-col { padding: 60px 24px; }
    .section-inner, .section-inner-wide, .gse-inner, .soporte-inner,
    .documental-inner, .capacitacion-inner { padding: 80px 24px; }
    .cta-inner { padding: 100px 24px; }
    .mv-card { padding: 48px 32px; }
    .servicio-card { padding: 40px 32px; }
  }

  @media (prefers-reduced-motion: reduce) {
    .reveal { opacity: 1; transform: none; transition: none; }
    * { animation-duration: 0.01ms !important; transition-duration: 0.01ms !important; }
  }
</style>
</head>
<body>

<!-- NAV -->
<nav>
  <a class="nav-logo" href="#">HTMC <span>Aero</span></a>
  <ul class="nav-links">
    <li><a href="#nosotros">Nosotros</a></li>
    <li><a href="#servicios">Servicios</a></li>
    <li><a href="#gse">Certificación GSE</a></li>
    <li><a href="#soporte">Soporte</a></li>
    <li><a href="#contacto">Contacto</a></li>
  </ul>
  <a href="#contacto" class="nav-cta">Solicitar servicio</a>
</nav>

<!-- HERO -->
<section class="hero">
  <div class="hero-bg">
    <img src="https://images.unsplash.com/photo-1540962351504-03099e0a754b?w=1800&q=80&auto=format&fit=crop" alt="Aeronave comercial en pista">
  </div>
  <div class="hero-inner">
    <span class="hero-eyebrow">Taller AFAC No. 400 · Toluca, México</span>
    <h1>Mantenimiento aeronáutico de precisión</h1>
    <p class="hero-sub">Certificación periódica de GSE, overhaul de componentes, NDT y calibración. Seguridad operacional con trazabilidad total en cada intervención.</p>
    <div class="hero-actions">
      <a href="#servicios" class="btn-primary">Explorar servicios</a>
      <a href="#contacto" class="btn-secondary">Contactar</a>
    </div>
  </div>
  <div class="hero-badge"><strong>AFAC Permiso No. 400</strong> &nbsp;·&nbsp; ISO/IEC 17025 Trazabilidad &nbsp;·&nbsp; ASME B30</div>
</section>

<!-- STATS -->
<div class="stats-band">
  <div class="stats-grid">
    <div class="stat-item reveal">
      <div class="stat-num">+15<em>años</em></div>
      <div class="stat-label">de experiencia técnica especializada en aviación</div>
    </div>
    <div class="stat-item reveal reveal-delay-1">
      <div class="stat-num">400</div>
      <div class="stat-label">Permiso de Taller Aeronáutico AFAC</div>
    </div>
    <div class="stat-item reveal reveal-delay-2">
      <div class="stat-num">3<em>sectores</em></div>
      <div class="stat-label">Comercial, ejecutivo y militar</div>
    </div>
    <div class="stat-item reveal reveal-delay-3">
      <div class="stat-num">17025</div>
      <div class="stat-label">Trazabilidad ISO/IEC en cada medición crítica</div>
    </div>
  </div>
</div>

<!-- INTRO / COMPROMISO INSTITUCIONAL -->
<section class="intro-section" id="compromiso">
  <div class="intro-inner">
    <span class="section-eyebrow reveal">Compromiso Institucional</span>
    <h2 class="section-title reveal reveal-delay-1">Ética, responsabilidad<br>y excelencia operacional</h2>
    <div class="divider-line reveal reveal-delay-2"></div>
    <p class="body-text reveal reveal-delay-2">En HTMC Servicios Especializados Aeronáuticos S.A. de C.V., fundamentamos nuestra operación en los más altos estándares de ética y responsabilidad social. Entendemos que la sostenibilidad de nuestra compañía depende de una planificación estratégica alineada con la integridad y el respeto hacia las personas, la comunidad y el entorno nacional.</p>
    <p class="body-text reveal reveal-delay-3" style="margin-top:20px;">Este Código es nuestra guía de referencia para la toma de decisiones cotidianas. Su propósito es alinear el comportamiento de todos nuestros niveles jerárquicos y Colaboradores con la visión de excelencia que nos define.</p>
  </div>
</section>

<!-- NOSOTROS -->
<section class="section-dark" id="nosotros">
  <div class="section-inner-wide">
    <div class="about-grid">
      <div class="reveal">
        <span class="about-badge">Permiso AFAC No. 400</span>
        <h2 class="section-title">Quiénes somos</h2>
        <p class="body-text">HTMC Servicios Especializados Aeronáuticos S.A. de C.V. es una empresa mexicana establecida en Toluca, Estado de México. Nos especializamos en el mantenimiento, overhaul, inspección, certificación periódica y pruebas de carga de componentes aeronáuticos y Equipos de Soporte en Tierra (GSE).</p>
        <p class="body-text" style="margin-top:20px;">Somos el punto de referencia en México para mantener tu flota de herramienta aeronáutica siempre operativa y en pleno cumplimiento regulatorio ante la AFAC.</p>
      </div>
      <div class="about-image reveal reveal-delay-2">
        <img src="https://images.unsplash.com/photo-1558618666-fcd25c85cd64?w=900&q=80&auto=format&fit=crop" alt="Técnico aeronáutico en taller">
      </div>
    </div>
  </div>
</section>

<!-- MISIÓN / VISIÓN -->
<section class="section-mid" id="mision">
  <div class="mv-grid">
    <div class="mv-card reveal">
      <svg class="mv-icon" viewBox="0 0 40 40" fill="none" xmlns="http://www.w3.org/2000/svg">
        <circle cx="20" cy="20" r="18" stroke="#c8a96e" stroke-width="1.5"/>
        <path d="M20 8v12l8 4" stroke="#c8a96e" stroke-width="1.5" stroke-linecap="round"/>
      </svg>
      <h3>Misión</h3>
      <p>Asegurar la aeronavegabilidad de los componentes y sistemas aeronáuticos mediante procesos de mantenimiento especializados en ruedas, frenos, baterías, pruebas RVSM (Pitot-Static), control de Peso y Balance de aeronaves y Ensayos No Destructivos (NDT).</p>
      <p>Ejecutamos cada servicio bajo estrictos estándares del fabricante, normativa vigente y control documental, fortaleciendo nuestra contribución directa a la seguridad operacional.</p>
      <p>Nuestro propósito es entregar componentes y servicios confiables, seguros y plenamente trazables, que garanticen operaciones aéreas continuas y seguras para nuestros clientes en los sectores comercial, ejecutivo y militar.</p>
    </div>
    <div class="mv-card reveal reveal-delay-2">
      <svg class="mv-icon" viewBox="0 0 40 40" fill="none" xmlns="http://www.w3.org/2000/svg">
        <path d="M20 4l4 8 9 1-6.5 6.3 1.5 9L20 24l-8 4.3 1.5-9L7 13l9-1 4-8z" stroke="#c8a96e" stroke-width="1.5" stroke-linejoin="round"/>
      </svg>
      <h3>Visión</h3>
      <p>Consolidarnos como el taller de servicios especializados aeronáuticos líder en México, reconocido por nuestra excelencia técnica, disciplina normativa y cumplimiento regulatorio.</p>
      <p>Impulsamos nuestro crecimiento mediante la mejora continua y la obtención de certificaciones nacionales e internacionales que fortalezcan nuestra competitividad y estándares de calidad.</p>
      <p>Aspiramos a convertirnos en un referente de confianza, trazabilidad y seguridad operacional a nivel mundial, ampliando de manera constante nuestros alcances técnicos para ofrecer servicios cada vez más completos y especializados a los sectores comercial, ejecutivo y militar.</p>
    </div>
  </div>
</section>

<!-- POLÍTICA DE CALIDAD -->
<section class="calidad-section">
  <div class="calidad-inner">
    <span class="section-eyebrow reveal">Política de Calidad</span>
    <h2 class="section-title reveal reveal-delay-1">Respaldados por norma,<br>cada vez, sin excepción</h2>
    <p class="body-text reveal reveal-delay-2">Cada servicio que ejecutamos está respaldado por los manuales del fabricante, las disposiciones de la AFAC y los estándares técnicos internacionales aplicables. Nuestros instrumentos de medición y prueba cuentan con trazabilidad metrológica hacia laboratorios acreditados bajo ISO/IEC 17025, garantizando precisión y confiabilidad en cada resultado. Entregamos documentación técnica completa en cada intervención, con registros auditables que respaldan el cumplimiento regulatorio de nuestros clientes.</p>
    <div class="calidad-tags reveal reveal-delay-3">
      <span class="calidad-tag">AFAC No. 400</span>
      <span class="calidad-tag">ASME B30</span>
      <span class="calidad-tag">ISO/IEC 17025</span>
      <span class="calidad-tag">Manuales del fabricante</span>
      <span class="calidad-tag">Trazabilidad total</span>
      <span class="calidad-tag">Documentación auditable</span>
    </div>
  </div>
</section>

<!-- SERVICIOS -->
<section class="section-dark" id="servicios">
  <div class="servicios-intro">
    <span class="section-eyebrow reveal">Servicios</span>
    <h2 class="section-title reveal reveal-delay-1">Tu socio técnico<br>aeronáutico integral</h2>
    <p class="body-text reveal reveal-delay-2" style="margin: 0 auto;">En HTMC mantenemos tu herramienta aeronáutica y GSE siempre operativos. Desde la certificación periódica obligatoria hasta la reparación, calibración, capacitación y gestión documental.</p>
  </div>
  <div class="servicios-grid">
    <!-- Servicio 1 -->
    <div class="servicio-card reveal">
      <div class="servicio-num">01</div>
      <svg class="servicio-icon" viewBox="0 0 44 44" fill="none" xmlns="http://www.w3.org/2000/svg">
        <circle cx="22" cy="22" r="14" stroke="#f5f5f7" stroke-width="1.5"/>
        <circle cx="22" cy="22" r="6" stroke="#f5f5f7" stroke-width="1.5"/>
        <path d="M22 8v4M22 32v4M8 22h4M32 22h4" stroke="#f5f5f7" stroke-width="1.5" stroke-linecap="round"/>
      </svg>
      <h3>Ruedas, Frenos y Baterías</h3>
      <p>Desensamble, inspección, overhaul y ensamble de ruedas de tren de nariz y tren principal, frenos de carbón y acero, y baterías de aeronaves comerciales, ejecutivas y militares. Conforme a manuales del fabricante y AFAC No. 400.</p>
    </div>
    <!-- Servicio 2 -->
    <div class="servicio-card reveal reveal-delay-1">
      <div class="servicio-num">02</div>
      <svg class="servicio-icon" viewBox="0 0 44 44" fill="none" xmlns="http://www.w3.org/2000/svg">
        <circle cx="22" cy="22" r="16" stroke="#f5f5f7" stroke-width="1.5" stroke-dasharray="4 2"/>
        <circle cx="22" cy="22" r="5" fill="#f5f5f7" fill-opacity="0.3" stroke="#f5f5f7" stroke-width="1.5"/>
        <path d="M22 6v6M38 22h-6M22 38v-6M6 22h6" stroke="#f5f5f7" stroke-width="1.5" stroke-linecap="round"/>
      </svg>
      <h3>Inspecciones No Destructivas (NDT)</h3>
      <p>Personal calificado para inspecciones mediante Corrientes de Eddy, Ultrasonido, Líquidos Penetrantes, Luz Negra y Partículas Magnéticas sobre componentes aeronáuticos y estructuras metálicas.</p>
    </div>
    <!-- Servicio 3 -->
    <div class="servicio-card reveal reveal-delay-2">
      <div class="servicio-num">03</div>
      <svg class="servicio-icon" viewBox="0 0 44 44" fill="none" xmlns="http://www.w3.org/2000/svg">
        <rect x="8" y="16" width="28" height="20" rx="3" stroke="#f5f5f7" stroke-width="1.5"/>
        <path d="M16 16v-4a6 6 0 0112 0v4" stroke="#f5f5f7" stroke-width="1.5" stroke-linecap="round"/>
        <circle cx="22" cy="26" r="3" stroke="#f5f5f7" stroke-width="1.5"/>
      </svg>
      <h3>Certificación Periódica de GSE</h3>
      <p>Proceso completo conforme a ASME B30 y manuales del fabricante. Prueba de carga, instrumentos con trazabilidad ISO/IEC 17025, certificado de aptitud y documentación auditable para cada equipo.</p>
    </div>
    <!-- Servicio 4 -->
    <div class="servicio-card reveal">
      <div class="servicio-num">04</div>
      <svg class="servicio-icon" viewBox="0 0 44 44" fill="none" xmlns="http://www.w3.org/2000/svg">
        <path d="M10 34l8-8 6 6 10-14" stroke="#f5f5f7" stroke-width="1.5" stroke-linecap="round" stroke-linejoin="round"/>
        <rect x="6" y="6" width="32" height="32" rx="4" stroke="#f5f5f7" stroke-width="1.5"/>
      </svg>
      <h3>Reparación y Mantenimiento de GSE</h3>
      <p>Reparación estructural, mecánica e hidráulica de GSE. Validada mediante prueba de carga o prueba de presión antes de reincorporación al servicio. Incluye acabados y esquemas de pintura aeronáutica.</p>
    </div>
    <!-- Servicio 5 -->
    <div class="servicio-card reveal reveal-delay-1">
      <div class="servicio-num">05</div>
      <svg class="servicio-icon" viewBox="0 0 44 44" fill="none" xmlns="http://www.w3.org/2000/svg">
        <path d="M22 10v24M10 22h24" stroke="#f5f5f7" stroke-width="1.5" stroke-linecap="round"/>
        <circle cx="22" cy="22" r="4" stroke="#f5f5f7" stroke-width="1.5"/>
        <circle cx="22" cy="22" r="16" stroke="#f5f5f7" stroke-width="1" stroke-opacity="0.4"/>
      </svg>
      <h3>Calibración de Herramienta y Equipo</h3>
      <p>Calibración de dinamómetros, manómetros, células de carga, torquímetros y equipo de medición dimensional. Trazabilidad metrológica hacia patrones acreditados bajo ISO/IEC 17025.</p>
    </div>
    <!-- Servicio 6 -->
    <div class="servicio-card reveal reveal-delay-2">
      <div class="servicio-num">06</div>
      <svg class="servicio-icon" viewBox="0 0 44 44" fill="none" xmlns="http://www.w3.org/2000/svg">
        <rect x="8" y="10" width="28" height="26" rx="3" stroke="#f5f5f7" stroke-width="1.5"/>
        <path d="M14 18h16M14 24h12M14 30h8" stroke="#f5f5f7" stroke-width="1.5" stroke-linecap="round"/>
      </svg>
      <h3>Capacitación Técnica</h3>
      <p>Formación para personal técnico en mantenimiento de GSE, procedimientos de pruebas de carga, uso correcto de herramienta aeronáutica y seguridad operacional. En nuestras instalaciones o en sitio del cliente.</p>
    </div>
  </div>
</section>

<!-- GSE CERTIFICACIÓN DETALLADA -->
<section class="gse-section" id="gse">
  <div class="gse-inner">
    <div class="gse-header">
      <div class="reveal">
        <span class="section-eyebrow">Certificación Periódica de GSE</span>
        <h2 class="section-title">Cada equipo.<br>Certificado.<br>Trazable.</h2>
      </div>
      <div class="reveal reveal-delay-2">
        <p class="body-text">La certificación periódica de los Equipos de Soporte en Tierra es un requisito obligatorio para garantizar la seguridad del personal, la integridad de las aeronaves y el cumplimiento regulatorio. Ejecutamos el proceso completo conforme a ASME B30 y los manuales del fabricante de cada equipo.</p>
      </div>
    </div>
    <div class="gse-equipos">
      <div class="equipo-card reveal">
        <img class="equipo-img" src="https://images.unsplash.com/photo-1521747116042-5a810fda9664?w=600&q=80&auto=format&fit=crop" alt="Gatos hidráulicos aeronáuticos">
        <h4>Gatos Hidráulicos</h4>
        <p>Axle jacks, tripod jacks y wing jacks. Prueba de carga estática verificando capacidad estructural e hidráulica.</p>
        <span class="equipo-norm">ASME B30 · Manual fabricante</span>
      </div>
      <div class="equipo-card reveal reveal-delay-1">
        <img class="equipo-img" src="https://images.unsplash.com/photo-1504307651254-35680f356dfd?w=600&q=80&auto=format&fit=crop" alt="Eslingas y dispositivos de izaje">
        <h4>Eslingas y Equipos de Izaje</h4>
        <p>Eslingas textiles, metálicas, cadenas y arneses. Certificación individual con registro de vida útil y control de flota.</p>
        <span class="equipo-norm">ASME B30.9</span>
      </div>
      <div class="equipo-card reveal reveal-delay-2">
        <img class="equipo-img" src="https://images.unsplash.com/photo-1565043589221-1a6fd9ae45c7?w=600&q=80&auto=format&fit=crop" alt="Unidades Bootstrap aeronáuticas">
        <h4>Unidades Bootstrap</h4>
        <p>Prueba de carga y verificación de presión operacional conforme a especificaciones del fabricante.</p>
        <span class="equipo-norm">Especificación fabricante</span>
      </div>
      <div class="equipo-card reveal">
        <img class="equipo-img" src="https://images.unsplash.com/photo-1474302770737-173ee21bab63?w=600&q=80&auto=format&fit=crop" alt="Stands de motores aeronáuticos">
        <h4>Stands de Motores y Nacelas</h4>
        <p>Prueba de carga estructural validando integridad operativa antes de cada ciclo de uso.</p>
        <span class="equipo-norm">ASME B30 · Manual fabricante</span>
      </div>
      <div class="equipo-card reveal reveal-delay-1">
        <img class="equipo-img" src="https://images.unsplash.com/photo-1504917595217-d4dc5ebe6122?w=600&q=80&auto=format&fit=crop" alt="Polipastos y equipos de izaje">
        <h4>Polipastos y Equipos de Izaje</h4>
        <p>Prueba de carga verificando capacidad mecánica y funcional de polipastos manuales, de cadena y de cable.</p>
        <span class="equipo-norm">ASME B30.21</span>
      </div>
      <div class="equipo-card reveal reveal-delay-2">
        <img class="equipo-img" src="https://images.unsplash.com/photo-1436491865332-7a61a109cc05?w=600&q=80&auto=format&fit=crop" alt="GSE especializado aeronáutico">
        <h4>GSE Especializado</h4>
        <p>Equipos de remolque, plataformas de acceso, carritos de servicio, dispensadores de fluidos y utillaje aeronáutico.</p>
        <span class="equipo-norm">Normas y manuales aplicables</span>
      </div>
    </div>
  </div>
</section>

<!-- STICKY PARALLAX — NDT + CALIBRACIÓN -->
<section class="sticky-section" aria-label="Detalles de servicios">
  <div class="sticky-image-col">
    <img src="https://images.unsplash.com/photo-1581091226825-a6a2a5aee158?w=1200&q=80&auto=format&fit=crop" alt="Técnico realizando inspección NDT">
  </div>
  <div class="sticky-text-col">
    <div class="sticky-block reveal">
      <span class="section-eyebrow">Inspecciones NDT</span>
      <h3>Detección precisa.<br>Decisiones seguras.</h3>
      <p>Corrientes de Eddy, Ultrasonido, Líquidos Penetrantes, Luz Negra y Partículas Magnéticas sobre componentes aeronáuticos y estructuras metálicas. Personal calificado bajo estándares internacionales NDT.</p>
    </div>
    <div class="sticky-block reveal">
      <span class="section-eyebrow">Calibración</span>
      <h3>Trazabilidad<br>desde el primer dígito.</h3>
      <p>Calibración de dinamómetros, manómetros, células de carga, torquímetros y equipo dimensional. Trazabilidad metrológica ISO/IEC 17025 en cada resultado crítico para tu operación.</p>
    </div>
    <div class="sticky-block reveal">
      <span class="section-eyebrow">Reparación GSE</span>
      <h3>Reparado, probado,<br>reincorporado.</h3>
      <p>Reparación estructural, mecánica e hidráulica de GSE. Toda intervención se valida mediante prueba de carga o presión antes de regresar el equipo al servicio, con acabados conforme a estándares aeronáuticos.</p>
    </div>
  </div>
</section>

<!-- SOPORTE TÉCNICO -->
<section class="soporte-section" id="soporte">
  <div class="soporte-inner">
    <div class="soporte-image reveal">
      <img src="https://images.unsplash.com/photo-1551836022-4c4c79ecde51?w=900&q=80&auto=format&fit=crop" alt="Ingenieros en soporte técnico aeronáutico">
    </div>
    <div class="reveal reveal-delay-2">
      <span class="section-eyebrow">Soporte Técnico</span>
      <h2 class="section-title">Respuesta<br>cuando más importa.</h2>
      <p class="body-text">En HTMC brindamos soporte técnico integral para todo nuestro portafolio de servicios, disponible tanto en nuestras instalaciones como en el sitio del cliente. Nuestro equipo técnico calificado atiende consultas, diagnósticos y asistencia operacional de manera remota vía telefónica o videoconferencia, y se desplaza a las instalaciones del cliente cuando la situación lo requiere.</p>
      <div class="aog-badge">
        <div class="aog-dot"></div>
        <span>Capacidad de respuesta AOG (Aircraft on Ground) — atención prioritaria para minimizar el tiempo fuera de servicio de la aeronave.</span>
      </div>
    </div>
  </div>
</section>

<!-- GESTIÓN DOCUMENTAL -->
<section class="documental-section">
  <div class="documental-inner">
    <div class="reveal">
      <span class="section-eyebrow">Gestión Documental</span>
      <h2 class="section-title">Evidencia objetiva.<br>Auditorías sin sorpresas.</h2>
      <p class="body-text">Cada servicio ejecutado en HTMC genera un expediente técnico completo que respalda auditorías internas y externas ante la AFAC y garantiza al cliente evidencia objetiva del historial de cada equipo.</p>
      <ul class="doc-list">
        <li>Orden de trabajo documentada</li>
        <li>Registros de inspección</li>
        <li>Resultados de pruebas de carga</li>
        <li>Certificados de aptitud</li>
        <li>Fichas de trazabilidad del equipo</li>
        <li>Control de flota y fechas de próxima recertificación</li>
      </ul>
    </div>
    <div class="documental-image reveal reveal-delay-2">
      <img src="https://images.unsplash.com/photo-1450101499163-c8848c66ca85?w=900&q=80&auto=format&fit=crop" alt="Documentación técnica aeronáutica">
    </div>
  </div>
</section>

<!-- CAPACITACIÓN -->
<section class="capacitacion-section">
  <div class="capacitacion-inner">
    <div class="capacitacion-image reveal">
      <img src="https://images.unsplash.com/photo-1524178232363-1fb2b075b655?w=900&q=80&auto=format&fit=crop" alt="Capacitación técnica aeronáutica">
    </div>
    <div class="reveal reveal-delay-2">
      <span class="section-eyebrow">Capacitación Técnica</span>
      <h2 class="section-title">Formación desde<br>la norma, no desde<br>la teoría.</h2>
      <p class="body-text">Programas de formación para personal técnico en mantenimiento y operación de GSE, procedimientos de pruebas de carga, uso correcto de herramienta aeronáutica y seguridad operacional en el taller.</p>
      <p class="body-text" style="margin-top:20px;">La capacitación se basa en los manuales del fabricante y la normativa AFAC vigente. Disponible en nuestras instalaciones en Toluca o directamente en el sitio del cliente.</p>
    </div>
  </div>
</section>

<!-- CTA / CONTACTO -->
<section class="cta-section" id="contacto">
  <div class="cta-inner">
    <span class="section-eyebrow reveal">Contacto</span>
    <h2 class="section-title reveal reveal-delay-1">¿Listo para mantener<br>tu flota en regla?</h2>
    <p class="body-text reveal reveal-delay-2">Cuéntanos qué equipos necesitas certificar o qué componentes requieren servicio. Nuestro equipo técnico te responde con la información que necesitas.</p>
    <div style="display:flex;gap:16px;justify-content:center;flex-wrap:wrap;margin-top:0" class="reveal reveal-delay-3">
      <a href="mailto:contacto@htmc.aero" class="btn-primary">Enviar correo</a>
      <a href="tel:+527225080922" class="btn-secondary">+52 722 508 0922</a>
    </div>
    <div class="cta-contact-info reveal reveal-delay-4">
      <div class="contact-item">
        <div class="contact-label">Dirección</div>
        <div class="contact-value">Privada Canaleja, Col. San Miguel Totoltepec<br>Toluca, Estado de México. C.P. 50225</div>
      </div>
      <div class="contact-item">
        <div class="contact-label">Teléfono</div>
        <a href="tel:+527225080922" class="contact-value">+52 722 508 0922</a>
      </div>
      <div class="contact-item">
        <div class="contact-label">Correo</div>
        <a href="mailto:contacto@htmc.aero" class="contact-value">contacto@htmc.aero</a>
      </div>
      <div class="contact-item">
        <div class="contact-label">Permiso AFAC</div>
        <div class="contact-value">Taller Aeronáutico No. 400</div>
      </div>
    </div>
  </div>
</section>

<!-- FOOTER -->
<footer>
  <div class="footer-inner">
    <div class="footer-brand">HTMC <span>Aero</span> · Taller AFAC No. 400</div>
    <nav class="footer-links" aria-label="Footer">
      <a href="#nosotros">Nosotros</a>
      <a href="#servicios">Servicios</a>
      <a href="#gse">Certificación GSE</a>
      <a href="#soporte">Soporte</a>
      <a href="#contacto">Contacto</a>
    </nav>
    <div class="footer-copy">© 2025 HTMC Servicios Especializados Aeronáuticos S.A. de C.V.</div>
  </div>
</footer>

<script>
  // IntersectionObserver para animaciones reveal
  const observer = new IntersectionObserver((entries) => {
    entries.forEach(entry => {
      if (entry.isIntersecting) {
        entry.target.classList.add('visible');
        observer.unobserve(entry.target);
      }
    });
  }, { threshold: 0.15, rootMargin: '0px 0px -60px 0px' });

  document.querySelectorAll('.reveal').forEach(el => observer.observe(el));

  // Nav scroll effect
  const nav = document.querySelector('nav');
  window.addEventListener('scroll', () => {
    if (window.scrollY > 60) {
      nav.style.background = 'rgba(10,10,10,0.92)';
    } else {
      nav.style.background = 'rgba(10,10,10,0.72)';
    }
  }, { passive: true });

  // Sticky section parallax suave
  const stickyImg = document.querySelector('.sticky-image-col img');
  if (stickyImg) {
    window.addEventListener('scroll', () => {
      const section = document.querySelector('.sticky-section');
      const rect = section.getBoundingClientRect();
      if (rect.top < window.innerHeight && rect.bottom > 0) {
        const progress = -rect.top / (rect.height - window.innerHeight);
        stickyImg.style.transform = `translateY(${progress * 40}px) scale(1.05)`;
      }
    }, { passive: true });
  }
</script>

</body>
</html>
