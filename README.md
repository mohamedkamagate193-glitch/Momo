
<!DOCTYPE html>
<html lang="fr">
<head>
<meta charset="UTF-8"/>
<meta name="viewport" content="width=device-width, initial-scale=1.0"/>
<title>AFAMA — Centre de Formation Football</title>
<link rel="preconnect" href="https://fonts.googleapis.com"/>
<link href="https://fonts.googleapis.com/css2?family=Anton&family=DM+Sans:ital,wght@0,300;0,400;0,500;1,300&family=Space+Mono:wght@400;700&display=swap" rel="stylesheet"/>
<style>
:root {
  --green: #b8ff57;
  --dark: #0c0c0c;
  --mid: #141414;
  --card: #1a1a1a;
  --border: #2a2a2a;
  --white: #f5f5f0;
  --gray: #888;
}
*, *::before, *::after { box-sizing: border-box; margin: 0; padding: 0; }
html { scroll-behavior: smooth; }
body {
  background: var(--dark);
  color: var(--white);
  font-family: 'DM Sans', sans-serif;
  font-size: 16px;
  overflow-x: hidden;
}

/* ── NAV ─────────────────────────────────────────────── */
nav {
  position: fixed; top: 0; left: 0; right: 0; z-index: 100;
  display: flex; align-items: center; justify-content: space-between;
  padding: 20px 40px;
  background: rgba(12,12,12,0.85);
  backdrop-filter: blur(12px);
  border-bottom: 1px solid var(--border);
}
.nav-logo {
  font-family: 'Anton', sans-serif;
  font-size: 28px;
  letter-spacing: 0.05em;
  color: var(--white);
}
.nav-logo span { color: var(--green); }
.nav-links { display: flex; gap: 32px; list-style: none; }
.nav-links a {
  font-family: 'Space Mono', monospace;
  font-size: 11px;
  text-transform: uppercase;
  letter-spacing: 0.15em;
  color: var(--gray);
  text-decoration: none;
  transition: color 0.2s;
}
.nav-links a:hover { color: var(--green); }
.nav-cta {
  font-family: 'Space Mono', monospace;
  font-size: 11px;
  text-transform: uppercase;
  letter-spacing: 0.15em;
  padding: 10px 20px;
  background: var(--green);
  color: var(--dark);
  border: none;
  cursor: pointer;
  font-weight: 700;
  text-decoration: none;
  transition: opacity 0.2s;
}
.nav-cta:hover { opacity: 0.85; }

/* ── HERO ─────────────────────────────────────────────── */
.hero {
  min-height: 100vh;
  display: grid;
  grid-template-columns: 1fr 1fr;
  padding: 120px 40px 80px;
  gap: 60px;
  align-items: center;
  position: relative;
  overflow: hidden;
}
.hero::before {
  content: '';
  position: absolute;
  top: -200px; right: -200px;
  width: 600px; height: 600px;
  background: radial-gradient(circle, rgba(184,255,87,0.08) 0%, transparent 70%);
  pointer-events: none;
}
.hero-tag {
  font-family: 'Space Mono', monospace;
  font-size: 11px;
  text-transform: uppercase;
  letter-spacing: 0.25em;
  color: var(--green);
  margin-bottom: 24px;
  display: flex;
  align-items: center;
  gap: 10px;
}
.hero-tag::before {
  content: '';
  display: inline-block;
  width: 32px; height: 1px;
  background: var(--green);
}
.hero h1 {
  font-family: 'Anton', sans-serif;
  font-size: clamp(56px, 7vw, 96px);
  line-height: 0.95;
  letter-spacing: 0.02em;
  text-transform: uppercase;
  margin-bottom: 32px;
}
.hero h1 .accent { color: var(--green); }
.hero h1 .stroke {
  -webkit-text-stroke: 1px var(--white);
  color: transparent;
}
.hero-desc {
  font-size: 17px;
  line-height: 1.7;
  color: #aaa;
  max-width: 460px;
  margin-bottom: 40px;
  font-weight: 300;
}
.hero-actions { display: flex; gap: 16px; align-items: center; }
.btn-primary {
  font-family: 'Space Mono', monospace;
  font-size: 12px;
  text-transform: uppercase;
  letter-spacing: 0.15em;
  padding: 16px 32px;
  background: var(--green);
  color: var(--dark);
  border: none;
  cursor: pointer;
  font-weight: 700;
  text-decoration: none;
  transition: transform 0.2s, opacity 0.2s;
  display: inline-block;
}
.btn-primary:hover { transform: translateY(-2px); opacity: 0.9; }
.btn-ghost {
  font-family: 'Space Mono', monospace;
  font-size: 12px;
  text-transform: uppercase;
  letter-spacing: 0.15em;
  padding: 16px 32px;
  background: transparent;
  color: var(--white);
  border: 1px solid var(--border);
  cursor: pointer;
  font-weight: 700;
  text-decoration: none;
  transition: border-color 0.2s, color 0.2s;
  display: inline-block;
}
.btn-ghost:hover { border-color: var(--green); color: var(--green); }

.hero-right {
  position: relative;
  display: flex;
  flex-direction: column;
  gap: 16px;
}
.hero-stats {
  display: grid;
  grid-template-columns: 1fr 1fr;
  gap: 12px;
}
.stat-card {
  background: var(--card);
  border: 1px solid var(--border);
  padding: 28px 24px;
  position: relative;
  overflow: hidden;
  animation: fadeUp 0.6s ease both;
}
.stat-card:nth-child(1) { animation-delay: 0.1s; }
.stat-card:nth-child(2) { animation-delay: 0.2s; }
.stat-card:nth-child(3) { animation-delay: 0.3s; }
.stat-card:nth-child(4) { animation-delay: 0.4s; }
.stat-card::after {
  content: '';
  position: absolute;
  bottom: 0; left: 0; right: 0;
  height: 2px;
  background: var(--green);
  transform: scaleX(0);
  transform-origin: left;
  transition: transform 0.3s;
}
.stat-card:hover::after { transform: scaleX(1); }
.stat-num {
  font-family: 'Anton', sans-serif;
  font-size: 48px;
  line-height: 1;
  color: var(--green);
  margin-bottom: 6px;
}
.stat-label {
  font-family: 'Space Mono', monospace;
  font-size: 10px;
  text-transform: uppercase;
  letter-spacing: 0.15em;
  color: var(--gray);
}

.hero-badge {
  background: var(--card);
  border: 1px solid var(--border);
  padding: 20px 24px;
  display: flex;
  align-items: center;
  gap: 16px;
}
.badge-icon {
  width: 48px; height: 48px;
  background: rgba(184,255,87,0.1);
  border: 1px solid rgba(184,255,87,0.3);
  display: flex; align-items: center; justify-content: center;
  font-size: 22px;
  flex-shrink: 0;
}
.badge-text { font-size: 13px; color: #aaa; line-height: 1.5; }
.badge-text strong { color: var(--white); }

/* ── TICKER ────────────────────────────────────────────── */
.ticker {
  border-top: 1px solid var(--border);
  border-bottom: 1px solid var(--border);
  padding: 14px 0;
  overflow: hidden;
  white-space: nowrap;
  background: var(--mid);
}
.ticker-inner {
  display: inline-flex;
  gap: 0;
  animation: ticker 28s linear infinite;
}
.ticker-item {
  font-family: 'Space Mono', monospace;
  font-size: 11px;
  text-transform: uppercase;
  letter-spacing: 0.15em;
  color: var(--gray);
  padding: 0 40px;
}
.ticker-item span { color: var(--green); margin-right: 12px; }
@keyframes ticker {
  from { transform: translateX(0); }
  to { transform: translateX(-50%); }
}

/* ── CATEGORIES ────────────────────────────────────────── */
.section { padding: 100px 40px; }
.section-tag {
  font-family: 'Space Mono', monospace;
  font-size: 11px;
  text-transform: uppercase;
  letter-spacing: 0.25em;
  color: var(--green);
  margin-bottom: 16px;
  display: flex; align-items: center; gap: 10px;
}
.section-tag::before { content: ''; display: inline-block; width: 24px; height: 1px; background: var(--green); }
.section h2 {
  font-family: 'Anton', sans-serif;
  font-size: clamp(36px, 5vw, 64px);
  text-transform: uppercase;
  line-height: 1;
  margin-bottom: 60px;
  letter-spacing: 0.02em;
}
.section h2 em { font-style: normal; color: var(--green); }

.cat-grid {
  display: grid;
  grid-template-columns: repeat(4, 1fr);
  gap: 2px;
}
.cat-card {
  background: var(--card);
  padding: 40px 32px;
  border: 1px solid var(--border);
  position: relative;
  overflow: hidden;
  cursor: default;
  transition: background 0.3s;
}
.cat-card:hover { background: #1f1f1f; }
.cat-card::before {
  content: '';
  position: absolute;
  top: 0; left: 0; right: 0;
  height: 3px;
}
.cat-card.u12::before { background: #fbbf24; }
.cat-card.u15::before { background: #f97316; }
.cat-card.u17::before { background: var(--green); }
.cat-card.senior::before { background: #3b82f6; }
.cat-label {
  font-family: 'Anton', sans-serif;
  font-size: 56px;
  line-height: 1;
  margin-bottom: 12px;
  letter-spacing: 0.02em;
}
.cat-card.u12 .cat-label { color: #fbbf24; }
.cat-card.u15 .cat-label { color: #f97316; }
.cat-card.u17 .cat-label { color: var(--green); }
.cat-card.senior .cat-label { color: #3b82f6; }
.cat-age {
  font-family: 'Space Mono', monospace;
  font-size: 10px;
  text-transform: uppercase;
  letter-spacing: 0.15em;
  color: var(--gray);
  margin-bottom: 20px;
}
.cat-desc { font-size: 14px; color: #888; line-height: 1.7; font-weight: 300; }
.cat-num {
  font-family: 'Anton', sans-serif;
  font-size: 18px;
  margin-top: 28px;
  color: var(--white);
}
.cat-num span { color: var(--gray); font-family: 'Space Mono', monospace; font-size: 10px; vertical-align: middle; margin-left: 6px; text-transform: uppercase; letter-spacing: 0.1em; }

/* ── VALEURS ────────────────────────────────────────────── */
.valeurs-grid {
  display: grid;
  grid-template-columns: repeat(3, 1fr);
  gap: 24px;
}
.valeur-card {
  border: 1px solid var(--border);
  padding: 40px 32px;
  position: relative;
}
.valeur-num {
  font-family: 'Anton', sans-serif;
  font-size: 80px;
  color: rgba(255,255,255,0.04);
  line-height: 1;
  position: absolute;
  top: 20px; right: 24px;
}
.valeur-icon { font-size: 32px; margin-bottom: 20px; }
.valeur-title {
  font-family: 'Anton', sans-serif;
  font-size: 22px;
  text-transform: uppercase;
  letter-spacing: 0.05em;
  margin-bottom: 12px;
}
.valeur-desc { font-size: 14px; color: #888; line-height: 1.8; font-weight: 300; }

/* ── PROGRAMME ─────────────────────────────────────────── */
.programme-bg { background: var(--mid); }
.programme-grid {
  display: grid;
  grid-template-columns: 1fr 1fr;
  gap: 40px;
  align-items: start;
}
.programme-list { display: flex; flex-direction: column; gap: 2px; }
.prog-item {
  display: flex;
  gap: 20px;
  padding: 24px 28px;
  background: var(--dark);
  border: 1px solid var(--border);
  align-items: flex-start;
  transition: border-color 0.2s;
  cursor: default;
}
.prog-item:hover { border-color: rgba(184,255,87,0.3); }
.prog-icon {
  width: 44px; height: 44px;
  background: rgba(184,255,87,0.08);
  border: 1px solid rgba(184,255,87,0.2);
  display: flex; align-items: center; justify-content: center;
  font-size: 18px;
  flex-shrink: 0;
}
.prog-title {
  font-family: 'Space Mono', monospace;
  font-size: 12px;
  text-transform: uppercase;
  letter-spacing: 0.1em;
  margin-bottom: 6px;
  color: var(--white);
}
.prog-desc { font-size: 13px; color: var(--gray); line-height: 1.6; font-weight: 300; }

.programme-aside {
  position: sticky;
  top: 100px;
}
.aside-card {
  background: var(--dark);
  border: 1px solid var(--border);
  padding: 40px;
  margin-bottom: 16px;
}
.aside-title {
  font-family: 'Anton', sans-serif;
  font-size: 28px;
  text-transform: uppercase;
  letter-spacing: 0.05em;
  margin-bottom: 8px;
}
.aside-sub { font-size: 13px; color: var(--gray); margin-bottom: 28px; font-weight: 300; }
.aside-schedule { display: flex; flex-direction: column; gap: 12px; }
.sch-row {
  display: flex;
  justify-content: space-between;
  align-items: center;
  padding: 12px 0;
  border-bottom: 1px solid var(--border);
}
.sch-day { font-family: 'Space Mono', monospace; font-size: 11px; text-transform: uppercase; letter-spacing: 0.1em; color: var(--gray); }
.sch-time { font-family: 'Space Mono', monospace; font-size: 11px; color: var(--green); }

/* ── INSCRIPTION ───────────────────────────────────────── */
.inscription-inner {
  display: grid;
  grid-template-columns: 1fr 1fr;
  gap: 80px;
  align-items: center;
}
.form-wrap {
  background: var(--card);
  border: 1px solid var(--border);
  padding: 48px;
}
.form-title {
  font-family: 'Anton', sans-serif;
  font-size: 28px;
  text-transform: uppercase;
  letter-spacing: 0.05em;
  margin-bottom: 32px;
}
.form-group { margin-bottom: 20px; }
.form-label {
  font-family: 'Space Mono', monospace;
  font-size: 10px;
  text-transform: uppercase;
  letter-spacing: 0.15em;
  color: var(--gray);
  display: block;
  margin-bottom: 8px;
}
.form-input, .form-select {
  width: 100%;
  background: var(--dark);
  border: 1px solid var(--border);
  color: var(--white);
  padding: 14px 16px;
  font-family: 'DM Sans', sans-serif;
  font-size: 15px;
  outline: none;
  transition: border-color 0.2s;
  appearance: none;
}
.form-input:focus, .form-select:focus { border-color: var(--green); }
.form-select option { background: var(--dark); }
.form-row { display: grid; grid-template-columns: 1fr 1fr; gap: 16px; }
.form-submit {
  width: 100%;
  padding: 16px;
  background: var(--green);
  color: var(--dark);
  border: none;
  font-family: 'Space Mono', monospace;
  font-size: 12px;
  text-transform: uppercase;
  letter-spacing: 0.15em;
  font-weight: 700;
  cursor: pointer;
  margin-top: 8px;
  transition: opacity 0.2s, transform 0.2s;
}
.form-submit:hover { opacity: 0.9; transform: translateY(-1px); }

.insc-info { }
.info-item {
  display: flex;
  gap: 20px;
  margin-bottom: 32px;
  align-items: flex-start;
}
.info-dot {
  width: 10px; height: 10px;
  background: var(--green);
  border-radius: 50%;
  margin-top: 6px;
  flex-shrink: 0;
}
.info-title {
  font-family: 'Space Mono', monospace;
  font-size: 12px;
  text-transform: uppercase;
  letter-spacing: 0.1em;
  color: var(--white);
  margin-bottom: 6px;
}
.info-desc { font-size: 14px; color: var(--gray); line-height: 1.7; font-weight: 300; }

/* ── FOOTER ────────────────────────────────────────────── */
footer {
  background: var(--mid);
  border-top: 1px solid var(--border);
  padding: 60px 40px 32px;
}
.footer-top {
  display: grid;
  grid-template-columns: 2fr 1fr 1fr 1fr;
  gap: 60px;
  margin-bottom: 48px;
}
.footer-brand {}
.footer-logo {
  font-family: 'Anton', sans-serif;
  font-size: 32px;
  letter-spacing: 0.05em;
  margin-bottom: 16px;
}
.footer-logo span { color: var(--green); }
.footer-tagline { font-size: 14px; color: var(--gray); line-height: 1.7; font-weight: 300; max-width: 280px; }
.footer-col-title {
  font-family: 'Space Mono', monospace;
  font-size: 10px;
  text-transform: uppercase;
  letter-spacing: 0.2em;
  color: var(--green);
  margin-bottom: 20px;
}
.footer-links { list-style: none; display: flex; flex-direction: column; gap: 10px; }
.footer-links a {
  font-size: 14px;
  color: var(--gray);
  text-decoration: none;
  transition: color 0.2s;
  font-weight: 300;
}
.footer-links a:hover { color: var(--white); }
.footer-bottom {
  border-top: 1px solid var(--border);
  padding-top: 24px;
  display: flex;
  justify-content: space-between;
  align-items: center;
}
.footer-copy {
  font-family: 'Space Mono', monospace;
  font-size: 10px;
  text-transform: uppercase;
  letter-spacing: 0.1em;
  color: var(--gray);
}

/* ── DIVIDER ──────────────────────────────────────────── */
.divider {
  height: 1px;
  background: linear-gradient(90deg, transparent, var(--border), transparent);
  margin: 0 40px;
}

/* ── ANIMATIONS ───────────────────────────────────────── */
@keyframes fadeUp {
  from { opacity: 0; transform: translateY(24px); }
  to { opacity: 1; transform: translateY(0); }
}
.hero-left { animation: fadeUp 0.7s ease 0.1s both; }
.hero-right { animation: fadeUp 0.7s ease 0.3s both; }

/* ── MOBILE ───────────────────────────────────────────── */
@media (max-width: 900px) {
  nav { padding: 16px 20px; }
  .nav-links { display: none; }
  .hero { grid-template-columns: 1fr; padding: 100px 20px 60px; }
  .hero-right { display: none; }
  .section { padding: 60px 20px; }
  .cat-grid { grid-template-columns: 1fr 1fr; }
  .valeurs-grid { grid-template-columns: 1fr; }
  .programme-grid { grid-template-columns: 1fr; }
  .programme-aside { position: static; }
  .inscription-inner { grid-template-columns: 1fr; }
  .form-wrap { padding: 28px; }
  .form-row { grid-template-columns: 1fr; }
  .footer-top { grid-template-columns: 1fr 1fr; gap: 32px; }
  .footer-bottom { flex-direction: column; gap: 12px; text-align: center; }
}
</style>
</head>
<body>

<!-- NAV -->
<nav>
  <div class="nav-logo">AF<span>A</span>MA</div>
  <ul class="nav-links">
    <li><a href="#categories">Catégories</a></li>
    <li><a href="#programme">Programme</a></li>
    <li><a href="#valeurs">Valeurs</a></li>
    <li><a href="#inscription">Inscription</a></li>
  </ul>
  <a href="#inscription" class="nav-cta">Rejoindre</a>
</nav>

<!-- HERO -->
<section class="hero">
  <div class="hero-left">
    <div class="hero-tag">Centre de Formation Football</div>
    <h1>
      Former les<br/>
      <span class="accent">Champions</span><br/>
      de <span class="stroke">Demain</span>
    </h1>
    <p class="hero-desc">
      AFAMA est un centre de formation dédié au développement technique, physique et humain des jeunes footballeurs. De l'U12 au Senior, chaque joueur est suivi individuellement.
    </p>
    <div class="hero-actions">
      <a href="#inscription" class="btn-primary">S'inscrire maintenant</a>
      <a href="#programme" class="btn-ghost">Voir le programme</a>
    </div>
  </div>
  <div class="hero-right">
    <div class="hero-stats">
      <div class="stat-card">
        <div class="stat-num">4</div>
        <div class="stat-label">Catégories</div>
      </div>
      <div class="stat-card">
        <div class="stat-num">12+</div>
        <div class="stat-label">Entraîneurs</div>
      </div>
      <div class="stat-card">
        <div class="stat-num">200+</div>
        <div class="stat-label">Joueurs formés</div>
      </div>
      <div class="stat-card">
        <div class="stat-num">5×</div>
        <div class="stat-label">Séances / semaine</div>
      </div>
    </div>
    <div class="hero-badge">
      <div class="badge-icon">⚽</div>
      <div class="badge-text"><strong>Suivi individuel garanti</strong><br/>Chaque joueur dispose d'un profil complet avec statistiques et progression.</div>
    </div>
    <div class="hero-badge">
      <div class="badge-icon">📊</div>
      <div class="badge-text"><strong>Tableaux de bord en temps réel</strong><br/>Performances, absences et cotisations suivis par notre app dédiée.</div>
    </div>
  </div>
</section>

<!-- TICKER -->
<div class="ticker">
  <div class="ticker-inner" id="ticker-inner"></div>
</div>

<!-- CATÉGORIES -->
<section class="section" id="categories">
  <div class="section-tag">Nos équipes</div>
  <h2>4 Catégories,<br/><em>1 Vision</em></h2>
  <div class="cat-grid">
    <div class="cat-card u12">
      <div class="cat-label">U12</div>
      <div class="cat-age">Moins de 12 ans</div>
      <p class="cat-desc">Initiation au football, développement ludique des fondamentaux techniques dans un cadre bienveillant et stimulant.</p>
      <div class="cat-num">Cotisation <span>150 € / saison</span></div>
    </div>
    <div class="cat-card u15">
      <div class="cat-label">U15</div>
      <div class="cat-age">Moins de 15 ans</div>
      <p class="cat-desc">Consolidation technique et début de la formation tactique. Compétitions régionales et tournois inter-clubs.</p>
      <div class="cat-num">Cotisation <span>200 € / saison</span></div>
    </div>
    <div class="cat-card u17">
      <div class="cat-label">U17</div>
      <div class="cat-age">Moins de 17 ans</div>
      <p class="cat-desc">Formation complète : technique, physique, mental et tactique. Préparation aux exigences du football de haut niveau.</p>
      <div class="cat-num">Cotisation <span>250 € / saison</span></div>
    </div>
    <div class="cat-card senior">
      <div class="cat-label">SEN.</div>
      <div class="cat-age">18 ans et plus</div>
      <p class="cat-desc">Programme élite pour joueurs confirmés. Entraînements intensifs, matchs officiels et suivi de performance avancé.</p>
      <div class="cat-num">Cotisation <span>300 € / saison</span></div>
    </div>
  </div>
</section>

<div class="divider"></div>

<!-- VALEURS -->
<section class="section" id="valeurs">
  <div class="section-tag">Notre ADN</div>
  <h2>Ce qui nous<br/><em>Définit</em></h2>
  <div class="valeurs-grid">
    <div class="valeur-card">
      <div class="valeur-num">01</div>
      <div class="valeur-icon">🎯</div>
      <div class="valeur-title">Excellence Technique</div>
      <p class="valeur-desc">Un programme d'entraînement structuré, conçu par des professionnels pour développer les compétences techniques de chaque joueur au maximum de son potentiel.</p>
    </div>
    <div class="valeur-card">
      <div class="valeur-num">02</div>
      <div class="valeur-icon">🤝</div>
      <div class="valeur-title">Esprit d'Équipe</div>
      <p class="valeur-desc">Le collectif avant tout. Nous cultivons la cohésion, le respect et la solidarité comme piliers fondamentaux du développement de chaque joueur.</p>
    </div>
    <div class="valeur-card">
      <div class="valeur-num">03</div>
      <div class="valeur-icon">📈</div>
      <div class="valeur-title">Progression Continue</div>
      <p class="valeur-desc">Chaque joueur est suivi individuellement. Des évaluations régulières et un outil de suivi numérique permettent de mesurer et d'accélérer les progrès.</p>
    </div>
    <div class="valeur-card">
      <div class="valeur-num">04</div>
      <div class="valeur-icon">💪</div>
      <div class="valeur-title">Préparation Physique</div>
      <p class="valeur-desc">Un suivi physique rigoureux adapté à chaque tranche d'âge. Endurance, vitesse, force et explosivité travaillées de manière scientifique.</p>
    </div>
    <div class="valeur-card">
      <div class="valeur-num">05</div>
      <div class="valeur-icon">🧠</div>
      <div class="valeur-title">Intelligence de Jeu</div>
      <p class="valeur-desc">Comprendre le jeu autant que le pratiquer. Nos entraîneurs développent la vision tactique, la prise de décision rapide et le leadership sur le terrain.</p>
    </div>
    <div class="valeur-card">
      <div class="valeur-num">06</div>
      <div class="valeur-icon">🌟</div>
      <div class="valeur-title">Développement Humain</div>
      <p class="valeur-desc">Le sport comme école de vie. Discipline, ambition, humilité et travail sont les valeurs que nous transmettons bien au-delà du terrain.</p>
    </div>
  </div>
</section>

<!-- PROGRAMME -->
<section class="section programme-bg" id="programme">
  <div class="section-tag">Organisation</div>
  <h2>Un Programme<br/><em>Structuré</em></h2>
  <div class="programme-grid">
    <div class="programme-list">
      <div class="prog-item">
        <div class="prog-icon">⚽</div>
        <div>
          <div class="prog-title">Entraînement Technique</div>
          <p class="prog-desc">Dribble, contrôle, passe, frappe. Les fondamentaux travaillés quotidiennement avec des exercices progressifs et ciblés.</p>
        </div>
      </div>
      <div class="prog-item">
        <div class="prog-icon">🏃</div>
        <div>
          <div class="prog-title">Préparation Physique</div>
          <p class="prog-desc">Séances dédiées à la condition physique, adaptées à chaque catégorie d'âge, pour développer endurance et explosivité.</p>
        </div>
      </div>
      <div class="prog-item">
        <div class="prog-icon">🗺️</div>
        <div>
          <div class="prog-title">Travail Tactique</div>
          <p class="prog-desc">Analyse vidéo, schémas de jeu, phases de set-piece. Comprendre et anticiper pour dominer le terrain.</p>
        </div>
      </div>
      <div class="prog-item">
        <div class="prog-icon">📋</div>
        <div>
          <div class="prog-title">Matchs & Tournois</div>
          <p class="prog-desc">Participation à des compétitions officielles et tournois amicaux tout au long de la saison pour mettre en pratique la formation.</p>
        </div>
      </div>
      <div class="prog-item">
        <div class="prog-icon">📊</div>
        <div>
          <div class="prog-title">Suivi & Évaluation</div>
          <p class="prog-desc">Bilan individuel mensuel, rapport aux parents, objectifs personnalisés. Chaque joueur connaît ses axes de progression.</p>
        </div>
      </div>
    </div>

    <div class="programme-aside">
      <div class="aside-card">
        <div class="aside-title">Calendrier des séances</div>
        <div class="aside-sub">Saison 2024–2025</div>
        <div class="aside-schedule">
          <div class="sch-row"><span class="sch-day">Lundi</span><span class="sch-time">18h00 – 20h00</span></div>
          <div class="sch-row"><span class="sch-day">Mercredi</span><span class="sch-time">15h00 – 17h30</span></div>
          <div class="sch-row"><span class="sch-day">Jeudi</span><span class="sch-time">18h00 – 20h00</span></div>
          <div class="sch-row"><span class="sch-day">Samedi</span><span class="sch-time">09h00 – 12h00</span></div>
          <div class="sch-row" style="border-bottom:none"><span class="sch-day">Dimanche</span><span class="sch-time">Matchs officiels</span></div>
        </div>
      </div>
      <div class="aside-card">
        <div class="aside-title">Infrastructure</div>
        <div class="aside-sub">Équipements de qualité professionnelle</div>
        <div style="display:flex;flex-direction:column;gap:10px">
          <div style="display:flex;gap:12px;align-items:center;font-size:13px;color:#aaa;font-weight:300">
            <span style="color:var(--green);font-size:10px;font-family:'Space Mono',monospace">→</span> 2 terrains en gazon naturel
          </div>
          <div style="display:flex;gap:12px;align-items:center;font-size:13px;color:#aaa;font-weight:300">
            <span style="color:var(--green);font-size:10px;font-family:'Space Mono',monospace">→</span> 1 terrain synthétique couvert
          </div>
          <div style="display:flex;gap:12px;align-items:center;font-size:13px;color:#aaa;font-weight:300">
            <span style="color:var(--green);font-size:10px;font-family:'Space Mono',monospace">→</span> Salle de musculation
          </div>
          <div style="display:flex;gap:12px;align-items:center;font-size:13px;color:#aaa;font-weight:300">
            <span style="color:var(--green);font-size:10px;font-family:'Space Mono',monospace">→</span> Vestiaires et salle de récupération
          </div>
          <div style="display:flex;gap:12px;align-items:center;font-size:13px;color:#aaa;font-weight:300">
            <span style="color:var(--green);font-size:10px;font-family:'Space Mono',monospace">→</span> Application de suivi numérique
          </div>
        </div>
      </div>
    </div>
  </div>
</section>

<!-- INSCRIPTION -->
<section class="section" id="inscription">
  <div class="inscription-inner">
    <div class="insc-info">
      <div class="section-tag">Rejoindre AFAMA</div>
      <h2>Prêt à <em>Démarrer</em> ?</h2>
      <div class="info-item">
        <div class="info-dot"></div>
        <div>
          <div class="info-title">Inscription en ligne</div>
          <p class="info-desc">Remplissez le formulaire et notre équipe vous contacte sous 48h pour finaliser l'inscription de votre joueur.</p>
        </div>
      </div>
      <div class="info-item">
        <div class="info-dot"></div>
        <div>
          <div class="info-title">Documents requis</div>
          <p class="info-desc">Certificat médical de non contre-indication à la pratique sportive, photo d'identité et pièce d'identité.</p>
        </div>
      </div>
      <div class="info-item">
        <div class="info-dot"></div>
        <div>
          <div class="info-title">Paiement flexible</div>
          <p class="info-desc">La cotisation peut être réglée en 1, 2 ou 3 fois selon les catégories. Aucun frais supplémentaire.</p>
        </div>
      </div>
      <div class="info-item">
        <div class="info-dot"></div>
        <div>
          <div class="info-title">Contact direct</div>
          <p class="info-desc">Une question ? Appelez-nous au <strong style="color:var(--white)">+33 (0)1 XX XX XX XX</strong> ou écrivez à <strong style="color:var(--white)">contact@afama.fr</strong></p>
        </div>
      </div>
    </div>

    <div class="form-wrap">
      <div class="form-title">Formulaire d'inscription</div>
      <div class="form-row">
        <div class="form-group">
          <label class="form-label">Prénom du joueur</label>
          <input type="text" class="form-input" placeholder="Mohamed"/>
        </div>
        <div class="form-group">
          <label class="form-label">Nom</label>
          <input type="text" class="form-input" placeholder="Diallo"/>
        </div>
      </div>
      <div class="form-group">
        <label class="form-label">Date de naissance</label>
        <input type="date" class="form-input"/>
      </div>
      <div class="form-group">
        <label class="form-label">Catégorie souhaitée</label>
        <select class="form-select">
          <option value="">Sélectionner une catégorie</option>
          <option>U12 — Moins de 12 ans</option>
          <option>U15 — Moins de 15 ans</option>
          <option>U17 — Moins de 17 ans</option>
          <option>Senior — 18 ans et plus</option>
        </select>
      </div>
      <div class="form-group">
        <label class="form-label">Poste de prédilection</label>
        <select class="form-select">
          <option value="">Sélectionner un poste</option>
          <option>Gardien</option>
          <option>Défenseur</option>
          <option>Milieu</option>
          <option>Attaquant</option>
        </select>
      </div>
      <div class="form-group">
        <label class="form-label">Email du responsable</label>
        <input type="email" class="form-input" placeholder="parent@email.com"/>
      </div>
      <div class="form-group">
        <label class="form-label">Téléphone</label>
        <input type="tel" class="form-input" placeholder="+33 6 XX XX XX XX"/>
      </div>
      <button class="form-submit" onclick="this.textContent='✓ Demande envoyée !';this.style.background='#333';this.style.color='#22c55e';setTimeout(()=>{this.textContent='S\'inscrire au centre AFAMA';this.style.background='';this.style.color='';},3000)">
        S'inscrire au centre AFAMA
      </button>
    </div>
  </div>
</section>

<!-- FOOTER -->
<footer>
  <div class="footer-top">
    <div class="footer-brand">
      <div class="footer-logo">AF<span>A</span>MA</div>
      <p class="footer-tagline">Former les champions de demain. Un centre dédié à l'excellence footballistique et au développement humain.</p>
    </div>
    <div>
      <div class="footer-col-title">Navigation</div>
      <ul class="footer-links">
        <li><a href="#categories">Catégories</a></li>
        <li><a href="#programme">Programme</a></li>
        <li><a href="#valeurs">Nos valeurs</a></li>
        <li><a href="#inscription">Inscription</a></li>
      </ul>
    </div>
    <div>
      <div class="footer-col-title">Catégories</div>
      <ul class="footer-links">
        <li><a href="#">U12 — 150€/saison</a></li>
        <li><a href="#">U15 — 200€/saison</a></li>
        <li><a href="#">U17 — 250€/saison</a></li>
        <li><a href="#">Senior — 300€/saison</a></li>
      </ul>
    </div>
    <div>
      <div class="footer-col-title">Contact</div>
      <ul class="footer-links">
        <li><a href="#">contact@afama.fr</a></li>
        <li><a href="#">+33 (0)1 XX XX XX XX</a></li>
        <li><a href="#">Terrain municipal</a></li>
        <li><a href="#">Lun–Sam · 8h–21h</a></li>
      </ul>
    </div>
  </div>
  <div class="footer-bottom">
    <div class="footer-copy">© 2025 AFAMA · Centre de Formation Football · Tous droits réservés</div>
    <div class="footer-copy">Fait avec ❤️ pour le football</div>
  </div>
</footer>

<script>
// Ticker
const items = [
  "Formation football","U12 · U15 · U17 · Senior","Suivi individuel","Saison 2024–2025",
  "Excellence technique","Esprit d'équipe","Rejoindre AFAMA","200+ joueurs formés",
  "5 séances par semaine","Compétitions officielles","Développement humain","Inscriptions ouvertes"
];
const inner = document.getElementById('ticker-inner');
const doubled = [...items, ...items];
inner.innerHTML = doubled.map(t => `<span class="ticker-item"><span>⚽</span>${t}</span>`).join('');

// Scroll reveal
const observer = new IntersectionObserver((entries) => {
  entries.forEach(e => {
    if (e.isIntersecting) {
      e.target.style.opacity = '1';
      e.target.style.transform = 'translateY(0)';
    }
  });
}, { threshold: 0.1 });

document.querySelectorAll('.cat-card, .valeur-card, .prog-item, .stat-card').forEach(el => {
  el.style.opacity = '0';
  el.style.transform = 'translateY(20px)';
  el.style.transition = 'opacity 0.5s ease, transform 0.5s ease';
  observer.observe(el);
});
</script>
</body>
</html>
