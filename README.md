<!DOCTYPE html>
<html lang="ar" dir="rtl">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>نظام مبيعات الهاتف والصيانة المتكامل | Morfy</title>
<link href="https://fonts.googleapis.com/css2?family=Cairo:wght@300;400;600;700;900&family=Tajawal:wght@300;400;500;700;900&display=swap" rel="stylesheet">
<style>
  :root {
    --gold: #c8a96e;
    --gold-light: #e8c98e;
    --gold-dark: #a07840;
    --dark: #0e0e0e;
    --dark2: #161616;
    --dark3: #1e1e1e;
    --dark4: #252525;
    --text: #e8e8e8;
    --text-muted: #888;
    --red: #8b2020;
  }

  * { margin: 0; padding: 0; box-sizing: border-box; }

  html { scroll-behavior: smooth; }

  body {
    background: var(--dark);
    color: var(--text);
    font-family: 'Cairo', 'Tajawal', sans-serif;
    overflow-x: hidden;
  }

  /* ── خلفية متحركة ── */
  body::before {
    content: '';
    position: fixed;
    inset: 0;
    background:
      radial-gradient(ellipse 800px 600px at 20% 20%, rgba(200,169,110,0.06) 0%, transparent 60%),
      radial-gradient(ellipse 600px 400px at 80% 80%, rgba(139,32,32,0.04) 0%, transparent 60%);
    pointer-events: none;
    z-index: 0;
  }

  /* ══════════════ HEADER ══════════════ */
  header {
    position: fixed;
    top: 0; left: 0; right: 0;
    z-index: 100;
    padding: 16px 60px;
    display: flex;
    align-items: center;
    justify-content: space-between;
    background: rgba(14,14,14,0.9);
    backdrop-filter: blur(20px);
    border-bottom: 1px solid rgba(200,169,110,0.15);
  }

  .logo {
    display: flex;
    align-items: center;
    gap: 12px;
    text-decoration: none;
  }

  .logo-icon {
    width: 40px; height: 40px;
    background: linear-gradient(135deg, var(--gold), var(--gold-dark));
    border-radius: 10px;
    display: flex; align-items: center; justify-content: center;
    font-size: 20px;
  }

  .logo-text {
    font-size: 18px;
    font-weight: 700;
    color: var(--gold);
    letter-spacing: 1px;
  }

  nav { display: flex; gap: 32px; }
  nav a {
    color: var(--text-muted);
    text-decoration: none;
    font-size: 15px;
    font-weight: 500;
    transition: color .2s;
  }
  nav a:hover { color: var(--gold); }

  .header-cta {
    background: linear-gradient(135deg, var(--gold), var(--gold-dark));
    color: #1a1a1a;
    border: none;
    padding: 10px 24px;
    border-radius: 8px;
    font-family: inherit;
    font-size: 14px;
    font-weight: 700;
    cursor: pointer;
    transition: transform .2s, box-shadow .2s;
    text-decoration: none;
    display: inline-block;
  }
  .header-cta:hover {
    transform: translateY(-2px);
    box-shadow: 0 8px 24px rgba(200,169,110,0.3);
  }

  /* ══════════════ HERO ══════════════ */
  .hero {
    position: relative;
    min-height: 100vh;
    display: flex;
    align-items: center;
    padding: 120px 60px 80px;
    overflow: hidden;
  }

  .hero-content {
    position: relative;
    z-index: 2;
    max-width: 640px;
  }

  .hero-badge {
    display: inline-flex;
    align-items: center;
    gap: 8px;
    background: rgba(200,169,110,0.1);
    border: 1px solid rgba(200,169,110,0.3);
    border-radius: 100px;
    padding: 6px 16px;
    font-size: 13px;
    color: var(--gold);
    margin-bottom: 28px;
    animation: fadeInDown .6s ease;
  }

  .hero-badge span { font-size: 16px; }

  h1 {
    font-size: 58px;
    font-weight: 900;
    line-height: 1.15;
    margin-bottom: 24px;
    animation: fadeInUp .7s ease .1s both;
  }

  h1 .highlight {
    background: linear-gradient(135deg, var(--gold-light), var(--gold));
    -webkit-background-clip: text;
    -webkit-text-fill-color: transparent;
    background-clip: text;
  }

  .hero-desc {
    font-size: 18px;
    color: var(--text-muted);
    line-height: 1.8;
    margin-bottom: 40px;
    animation: fadeInUp .7s ease .2s both;
  }

  .hero-btns {
    display: flex;
    gap: 16px;
    flex-wrap: wrap;
    animation: fadeInUp .7s ease .3s both;
  }

  .btn-primary {
    background: linear-gradient(135deg, var(--gold), var(--gold-dark));
    color: #1a1a1a;
    border: none;
    padding: 16px 36px;
    border-radius: 10px;
    font-family: inherit;
    font-size: 16px;
    font-weight: 700;
    cursor: pointer;
    transition: transform .2s, box-shadow .2s;
    text-decoration: none;
    display: inline-flex;
    align-items: center;
    gap: 8px;
  }
  .btn-primary:hover {
    transform: translateY(-3px);
    box-shadow: 0 12px 32px rgba(200,169,110,0.35);
  }

  .btn-secondary {
    background: transparent;
    color: var(--text);
    border: 1px solid rgba(255,255,255,0.15);
    padding: 16px 36px;
    border-radius: 10px;
    font-family: inherit;
    font-size: 16px;
    font-weight: 600;
    cursor: pointer;
    transition: all .2s;
    text-decoration: none;
    display: inline-flex;
    align-items: center;
    gap: 8px;
  }
  .btn-secondary:hover {
    border-color: var(--gold);
    color: var(--gold);
  }

  .hero-stats {
    display: flex;
    gap: 40px;
    margin-top: 60px;
    animation: fadeInUp .7s ease .4s both;
  }

  .stat {
    display: flex;
    flex-direction: column;
    gap: 4px;
  }

  .stat-num {
    font-size: 32px;
    font-weight: 900;
    color: var(--gold);
  }

  .stat-label {
    font-size: 13px;
    color: var(--text-muted);
  }

  /* صورة Hero */
  .hero-visual {
    position: absolute;
    left: 0;
    top: 50%;
    transform: translateY(-50%);
    width: 55%;
    animation: fadeInLeft .8s ease .3s both;
  }

  .screen-mockup {
    background: var(--dark3);
    border: 1px solid rgba(200,169,110,0.2);
    border-radius: 16px;
    overflow: hidden;
    box-shadow:
      0 40px 80px rgba(0,0,0,0.6),
      0 0 0 1px rgba(200,169,110,0.1),
      inset 0 1px 0 rgba(255,255,255,0.05);
    padding: 20px;
  }

  .screen-bar {
    display: flex;
    align-items: center;
    gap: 8px;
    margin-bottom: 16px;
  }

  .dot { width: 12px; height: 12px; border-radius: 50%; }
  .dot-r { background: #ff5f57; }
  .dot-y { background: #ffbd2e; }
  .dot-g { background: #28c840; }

  .screen-title {
    font-size: 13px;
    color: var(--text-muted);
    margin-right: auto;
  }

  .screen-content {
    display: grid;
    grid-template-columns: repeat(2, 1fr);
    gap: 10px;
  }

  .screen-card {
    background: var(--dark4);
    border: 1px solid rgba(255,255,255,0.06);
    border-radius: 10px;
    padding: 16px;
    transition: border-color .3s;
  }
  .screen-card:hover { border-color: rgba(200,169,110,0.3); }

  .screen-card-icon { font-size: 24px; margin-bottom: 8px; }
  .screen-card-title { font-size: 14px; font-weight: 700; color: var(--text); }
  .screen-card-sub { font-size: 12px; color: var(--text-muted); margin-top: 4px; }

  .screen-stat {
    font-size: 22px;
    font-weight: 900;
    color: var(--gold);
    margin-top: 8px;
  }

  /* ══════════════ FEATURES ══════════════ */
  section {
    position: relative;
    z-index: 1;
    padding: 100px 60px;
  }

  .section-label {
    text-align: center;
    color: var(--gold);
    font-size: 13px;
    font-weight: 700;
    letter-spacing: 3px;
    text-transform: uppercase;
    margin-bottom: 16px;
  }

  .section-title {
    text-align: center;
    font-size: 42px;
    font-weight: 900;
    margin-bottom: 16px;
  }

  .section-desc {
    text-align: center;
    color: var(--text-muted);
    font-size: 17px;
    max-width: 600px;
    margin: 0 auto 64px;
    line-height: 1.8;
  }

  .features-grid {
    display: grid;
    grid-template-columns: repeat(3, 1fr);
    gap: 24px;
    max-width: 1100px;
    margin: 0 auto;
  }

  .feature-card {
    background: var(--dark3);
    border: 1px solid rgba(255,255,255,0.06);
    border-radius: 16px;
    padding: 32px;
    transition: all .3s;
    position: relative;
    overflow: hidden;
  }

  .feature-card::before {
    content: '';
    position: absolute;
    top: 0; left: 0; right: 0;
    height: 2px;
    background: linear-gradient(90deg, transparent, var(--gold), transparent);
    opacity: 0;
    transition: opacity .3s;
  }

  .feature-card:hover {
    border-color: rgba(200,169,110,0.2);
    transform: translateY(-4px);
    box-shadow: 0 20px 40px rgba(0,0,0,0.3);
  }

  .feature-card:hover::before { opacity: 1; }

  .feature-icon {
    width: 52px; height: 52px;
    background: rgba(200,169,110,0.1);
    border: 1px solid rgba(200,169,110,0.2);
    border-radius: 12px;
    display: flex;
    align-items: center;
    justify-content: center;
    font-size: 24px;
    margin-bottom: 20px;
  }

  .feature-title {
    font-size: 18px;
    font-weight: 700;
    margin-bottom: 10px;
    color: var(--text);
  }

  .feature-desc {
    font-size: 14px;
    color: var(--text-muted);
    line-height: 1.8;
  }

  /* ══════════════ SCREENSHOTS ══════════════ */
  .screenshots {
    background: var(--dark2);
    border-top: 1px solid rgba(255,255,255,0.04);
    border-bottom: 1px solid rgba(255,255,255,0.04);
  }

  .screenshots-grid {
    display: grid;
    grid-template-columns: repeat(2, 1fr);
    gap: 24px;
    max-width: 1100px;
    margin: 0 auto;
  }

  .screenshot-item {
    background: var(--dark3);
    border: 1px solid rgba(255,255,255,0.08);
    border-radius: 16px;
    overflow: hidden;
    transition: all .3s;
  }

  .screenshot-item:hover {
    border-color: rgba(200,169,110,0.3);
    transform: scale(1.01);
    box-shadow: 0 20px 50px rgba(0,0,0,0.4);
  }

  .screenshot-header {
    background: var(--dark4);
    padding: 12px 16px;
    display: flex;
    align-items: center;
    gap: 8px;
    border-bottom: 1px solid rgba(255,255,255,0.06);
  }

  .screenshot-body {
    padding: 20px;
  }

  .screenshot-title {
    font-size: 14px;
    font-weight: 700;
    color: var(--gold);
    margin-right: auto;
  }

  /* محاكاة واجهة البرنامج */
  .ui-row {
    display: flex;
    gap: 10px;
    margin-bottom: 10px;
  }

  .ui-btn {
    background: var(--dark4);
    border: 1px solid rgba(255,255,255,0.08);
    border-radius: 8px;
    padding: 10px 18px;
    font-size: 13px;
    color: var(--text-muted);
    flex: 1;
    text-align: center;
  }

  .ui-btn.gold {
    background: rgba(200,169,110,0.15);
    border-color: rgba(200,169,110,0.3);
    color: var(--gold);
  }

  .ui-table {
    width: 100%;
    border-collapse: collapse;
    font-size: 13px;
  }

  .ui-table th {
    background: var(--dark);
    color: var(--gold);
    padding: 10px 12px;
    text-align: right;
    font-weight: 600;
  }

  .ui-table td {
    padding: 10px 12px;
    border-bottom: 1px solid rgba(255,255,255,0.04);
    color: var(--text-muted);
  }

  .ui-table tr:hover td { background: rgba(255,255,255,0.02); color: var(--text); }

  .badge {
    display: inline-block;
    padding: 3px 10px;
    border-radius: 100px;
    font-size: 11px;
    font-weight: 600;
  }
  .badge-green { background: rgba(40,200,100,0.15); color: #28c864; }
  .badge-red   { background: rgba(200,50,50,0.15);  color: #e05050; }
  .badge-gold  { background: rgba(200,169,110,0.15); color: var(--gold); }

  /* ══════════════ PRICING ══════════════ */
  .pricing-grid {
    display: grid;
    grid-template-columns: repeat(3, 1fr);
    gap: 24px;
    max-width: 900px;
    margin: 0 auto;
  }

  .price-card {
    background: var(--dark3);
    border: 1px solid rgba(255,255,255,0.08);
    border-radius: 20px;
    padding: 36px 28px;
    text-align: center;
    position: relative;
    transition: all .3s;
  }

  .price-card.featured {
    border-color: rgba(200,169,110,0.4);
    background: linear-gradient(135deg, rgba(200,169,110,0.08), var(--dark3));
    transform: scale(1.05);
    box-shadow: 0 20px 60px rgba(200,169,110,0.15);
  }

  .price-card:hover:not(.featured) {
    border-color: rgba(200,169,110,0.2);
    transform: translateY(-4px);
  }

  .price-badge {
    position: absolute;
    top: -14px;
    left: 50%;
    transform: translateX(-50%);
    background: linear-gradient(135deg, var(--gold), var(--gold-dark));
    color: #1a1a1a;
    font-size: 12px;
    font-weight: 700;
    padding: 4px 16px;
    border-radius: 100px;
    white-space: nowrap;
  }

  .price-plan { font-size: 16px; color: var(--text-muted); margin-bottom: 16px; }

  .price-amount {
    font-size: 52px;
    font-weight: 900;
    color: var(--gold);
    line-height: 1;
  }

  .price-currency { font-size: 18px; vertical-align: super; }
  .price-period { font-size: 14px; color: var(--text-muted); margin: 8px 0 28px; }

  .price-features { list-style: none; text-align: right; margin-bottom: 32px; }
  .price-features li {
    padding: 8px 0;
    font-size: 14px;
    color: var(--text-muted);
    border-bottom: 1px solid rgba(255,255,255,0.04);
    display: flex;
    align-items: center;
    gap: 10px;
  }
  .price-features li::before {
    content: '✓';
    color: var(--gold);
    font-weight: 700;
    flex-shrink: 0;
  }

  .price-btn {
    width: 100%;
    padding: 14px;
    border-radius: 10px;
    font-family: inherit;
    font-size: 15px;
    font-weight: 700;
    cursor: pointer;
    transition: all .2s;
    border: none;
  }

  .price-btn-outline {
    background: transparent;
    border: 1px solid rgba(200,169,110,0.4);
    color: var(--gold);
  }
  .price-btn-outline:hover {
    background: rgba(200,169,110,0.1);
  }

  .price-btn-fill {
    background: linear-gradient(135deg, var(--gold), var(--gold-dark));
    color: #1a1a1a;
  }
  .price-btn-fill:hover {
    box-shadow: 0 8px 24px rgba(200,169,110,0.35);
    transform: translateY(-2px);
  }

  /* ══════════════ SCRIPT SECTION ══════════════ */
  .script-section {
    max-width: 900px;
    margin: 0 auto;
  }

  .script-block {
    background: var(--dark3);
    border: 1px solid rgba(200,169,110,0.15);
    border-radius: 16px;
    padding: 40px;
    position: relative;
    margin-bottom: 32px;
  }

  .script-block::before {
    content: attr(data-time);
    position: absolute;
    top: -12px;
    right: 24px;
    background: linear-gradient(135deg, var(--gold), var(--gold-dark));
    color: #1a1a1a;
    font-size: 12px;
    font-weight: 700;
    padding: 3px 14px;
    border-radius: 100px;
  }

  .script-heading {
    font-size: 20px;
    font-weight: 700;
    color: var(--gold);
    margin-bottom: 16px;
  }

  .script-text {
    font-size: 15px;
    color: var(--text-muted);
    line-height: 2;
  }

  .script-text strong { color: var(--text); }

  .script-note {
    background: rgba(200,169,110,0.07);
    border-right: 3px solid var(--gold);
    padding: 14px 18px;
    border-radius: 0 8px 8px 0;
    font-size: 13px;
    color: var(--text-muted);
    margin-top: 14px;
  }

  /* ══════════════ CTA ══════════════ */
  .cta-section {
    text-align: center;
    background: linear-gradient(135deg, rgba(200,169,110,0.08), rgba(139,32,32,0.06));
    border-top: 1px solid rgba(200,169,110,0.1);
    border-bottom: 1px solid rgba(200,169,110,0.1);
  }

  .cta-title { font-size: 44px; font-weight: 900; margin-bottom: 20px; }
  .cta-desc { color: var(--text-muted); font-size: 18px; max-width: 500px; margin: 0 auto 40px; line-height: 1.8; }

  .contact-cards {
    display: flex;
    gap: 24px;
    justify-content: center;
    flex-wrap: wrap;
    margin-top: 48px;
  }

  .contact-card {
    background: var(--dark3);
    border: 1px solid rgba(255,255,255,0.08);
    border-radius: 14px;
    padding: 20px 32px;
    display: flex;
    align-items: center;
    gap: 14px;
    transition: all .2s;
    text-decoration: none;
    color: var(--text);
  }
  .contact-card:hover {
    border-color: rgba(200,169,110,0.3);
    transform: translateY(-2px);
  }

  .contact-icon { font-size: 24px; }
  .contact-label { font-size: 12px; color: var(--text-muted); }
  .contact-value { font-size: 16px; font-weight: 700; color: var(--gold); }

  /* ══════════════ FOOTER ══════════════ */
  footer {
    padding: 32px 60px;
    display: flex;
    align-items: center;
    justify-content: space-between;
    border-top: 1px solid rgba(255,255,255,0.06);
  }

  .footer-copy { font-size: 13px; color: var(--text-muted); }
  .footer-by { font-size: 14px; color: var(--gold); font-weight: 700; }

  /* ══════════════ ANIMATIONS ══════════════ */
  @keyframes fadeInUp {
    from { opacity: 0; transform: translateY(30px); }
    to   { opacity: 1; transform: translateY(0); }
  }

  @keyframes fadeInDown {
    from { opacity: 0; transform: translateY(-20px); }
    to   { opacity: 1; transform: translateY(0); }
  }

  @keyframes fadeInLeft {
    from { opacity: 0; transform: translateX(60px) translateY(-50%); }
    to   { opacity: 1; transform: translateX(0) translateY(-50%); }
  }

  @keyframes float {
    0%, 100% { transform: translateY(-50%); }
    50% { transform: translateY(calc(-50% - 12px)); }
  }

  .hero-visual { animation: float 4s ease-in-out infinite; }

  /* ══════════════ RESPONSIVE ══════════════ */
  @media (max-width: 900px) {
    header { padding: 14px 24px; }
    nav { display: none; }
    .hero { padding: 100px 24px 60px; flex-direction: column; min-height: auto; }
    .hero-visual { display: none; }
    h1 { font-size: 36px; }
    .hero-stats { gap: 24px; }
    section { padding: 60px 24px; }
    .features-grid, .screenshots-grid, .pricing-grid { grid-template-columns: 1fr; }
    .price-card.featured { transform: none; }
    .section-title { font-size: 28px; }
    footer { flex-direction: column; gap: 12px; text-align: center; }
  }
</style>
</head>
<body>

<!-- ══ HEADER ══ -->
<header>
  <a href="#" class="logo">
    <div class="logo-icon">📱</div>
    <span class="logo-text">Morfy POS</span>
  </a>
  <nav>
    <a href="#features">المميزات</a>
    <a href="#screenshots">الواجهة</a>
    <a href="#pricing">الأسعار</a>
    <a href="#contact">تواصل معنا</a>
  </nav>
  <a href="#contact" class="header-cta">ابدأ الآن</a>
</header>

<!-- ══ HERO ══ -->
<div class="hero">
  <div class="hero-content">
    <div class="hero-badge">
      <span>🏆</span>
      النظام الأول لمحلات الجوال في السعودية
    </div>

    <h1>نظام <span class="highlight">متكامل</span><br>لمحلات الجوال<br>والصيانة</h1>

    <p class="hero-desc">
      إدارة المبيعات، المخزون، الصيانة، والمرتجعات — كل شيء في مكان واحد.
      واجهة سهلة، تقارير ذكية، وترخيص احترافي.
    </p>

    <div class="hero-btns">
      <a href="#pricing" class="btn-primary">🚀 ابدأ التجربة المجانية</a>
      <a href="#screenshots" class="btn-secondary">👁 شاهد البرنامج</a>
    </div>

    <div class="hero-stats">
      <div class="stat">
        <span class="stat-num">7</span>
        <span class="stat-label">أيام تجريبية مجانية</span>
      </div>
      <div class="stat">
        <span class="stat-num">2</span>
        <span class="stat-label">لغة (عربي / English)</span>
      </div>
      <div class="stat">
        <span class="stat-num">∞</span>
        <span class="stat-label">عمليات بيع يومية</span>
      </div>
    </div>
  </div>

  <!-- محاكاة شاشة البرنامج -->
  <div class="hero-visual">
    <div class="screen-mockup">
      <div class="screen-bar">
        <div class="dot dot-r"></div>
        <div class="dot dot-y"></div>
        <div class="dot dot-g"></div>
        <span class="screen-title">نظام مبيعات الهاتف والصيانة المتكامل</span>
      </div>
      <div class="screen-content">
        <div class="screen-card">
          <div class="screen-card-icon">🛒</div>
          <div class="screen-card-title">بيع جديد</div>
          <div class="screen-card-sub">نقطة البيع</div>
          <div class="screen-stat">12 فاتورة</div>
        </div>
        <div class="screen-card">
          <div class="screen-card-icon">📦</div>
          <div class="screen-card-title">المخزن</div>
          <div class="screen-card-sub">إدارة المنتجات</div>
          <div class="screen-stat">48 صنف</div>
        </div>
        <div class="screen-card">
          <div class="screen-card-icon">🛠️</div>
          <div class="screen-card-title">الصيانة</div>
          <div class="screen-card-sub">طلبات الإصلاح</div>
          <div class="screen-stat">7 طلبات</div>
        </div>
        <div class="screen-card">
          <div class="screen-card-icon">💰</div>
          <div class="screen-card-title">الأرباح اليومية</div>
          <div class="screen-card-sub">اليوم</div>
          <div class="screen-stat" style="font-size:16px">3,450 ريال</div>
        </div>
      </div>
    </div>
  </div>
</div>

<!-- ══ FEATURES ══ -->
<section id="features">
  <div class="section-label">المميزات</div>
  <h2 class="section-title">كل ما يحتاجه محلك في نظام واحد</h2>
  <p class="section-desc">مصمم خصيصاً لمحلات الجوال والصيانة في السوق السعودي</p>

  <div class="features-grid">
    <div class="feature-card">
      <div class="feature-icon">🛒</div>
      <h3 class="feature-title">نقطة بيع سريعة</h3>
      <p class="feature-desc">أضف منتجات للسلة بسرعة، طباعة فاتورة فورية، ودعم الماسح الضوئي IMEI</p>
    </div>
    <div class="feature-card">
      <div class="feature-icon">📦</div>
      <h3 class="feature-title">إدارة المخزون</h3>
      <p class="feature-desc">تتبع جميع المنتجات بالكمية والسعر، تنبيه تلقائي عند نفاد المخزون</p>
    </div>
    <div class="feature-card">
      <div class="feature-icon">🛠️</div>
      <h3 class="feature-title">إدارة الصيانة</h3>
      <p class="feature-desc">استقبال طلبات الصيانة، تتبع الحالة، وإشعار العميل عند الانتهاء</p>
    </div>
    <div class="feature-card">
      <div class="feature-icon">🔄</div>
      <h3 class="feature-title">نظام المرتجعات</h3>
      <p class="feature-desc">إرجاع المنتجات بسهولة مع الحفاظ على السجل التاريخي الكامل</p>
    </div>
    <div class="feature-card">
      <div class="feature-icon">📊</div>
      <h3 class="feature-title">تقارير ذكية</h3>
      <p class="feature-desc">تقرير شهري، تقرير الموظفين، الأرباح، وتصدير CSV لكل البيانات</p>
    </div>
    <div class="feature-card">
      <div class="feature-icon">👥</div>
      <h3 class="feature-title">إدارة الموظفين</h3>
      <p class="feature-desc">صلاحيات مختلفة لكل موظف، سجل العمليات، وتقرير الأداء الشهري</p>
    </div>
    <div class="feature-card">
      <div class="feature-icon">💾</div>
      <h3 class="feature-title">نسخ احتياطي تلقائي</h3>
      <p class="feature-desc">نسخ يومي تلقائي للبيانات مع الاحتفاظ بآخر 30 نسخة</p>
    </div>
    <div class="feature-card">
      <div class="feature-icon">🌐</div>
      <h3 class="feature-title">ثنائي اللغة</h3>
      <p class="feature-desc">تبديل فوري بين العربية والإنجليزية بضغطة واحدة</p>
    </div>
    <div class="feature-card">
      <div class="feature-icon">🔑</div>
      <h3 class="feature-title">ترخيص احترافي</h3>
      <p class="feature-desc">نظام ترخيص آمن بخوارزمية تشفير متقدمة، لكل جهاز ترخيص مستقل</p>
    </div>
  </div>
</section>

<!-- ══ SCREENSHOTS ══ -->
<section id="screenshots" class="screenshots">
  <div class="section-label">الواجهة</div>
  <h2 class="section-title">واجهة نظيفة واحترافية</h2>
  <p class="section-desc">تصميم داكن أنيق مع ألوان واضحة سهلة على العين</p>

  <div class="screenshots-grid">
    <!-- شاشة الدخول -->
    <div class="screenshot-item">
      <div class="screenshot-header">
        <div class="dot dot-r"></div>
        <div class="dot dot-y"></div>
        <div class="dot dot-g"></div>
        <span class="screenshot-title">🔐 شاشة الدخول</span>
      </div>
      <div class="screenshot-body">
        <div style="text-align:center; padding: 20px 0;">
          <div style="font-size:36px; margin-bottom:8px;">📱</div>
          <div style="font-size:18px; font-weight:900; color:var(--gold); margin-bottom:20px;">نظام مبيعات الهاتف والصيانة</div>
          <div style="background:var(--dark4); border:1px solid rgba(255,255,255,0.08); border-radius:10px; padding:20px; max-width:300px; margin:0 auto;">
            <div style="font-size:14px; color:var(--text-muted); margin-bottom:8px;">اسم المستخدم:</div>
            <div style="background:var(--dark2); border:1px solid rgba(200,169,110,0.3); border-radius:8px; height:38px; margin-bottom:12px;"></div>
            <div style="font-size:14px; color:var(--text-muted); margin-bottom:8px;">كلمة المرور:</div>
            <div style="background:var(--dark2); border:1px solid rgba(255,255,255,0.08); border-radius:8px; height:38px; margin-bottom:16px;"></div>
            <div style="background:linear-gradient(135deg,var(--gold),var(--gold-dark)); color:#1a1a1a; font-weight:700; text-align:center; padding:10px; border-radius:8px; font-size:15px;">دخول</div>
          </div>
        </div>
      </div>
    </div>

    <!-- شاشة القائمة الرئيسية -->
    <div class="screenshot-item">
      <div class="screenshot-header">
        <div class="dot dot-r"></div>
        <div class="dot dot-y"></div>
        <div class="dot dot-g"></div>
        <span class="screenshot-title">🏠 القائمة الرئيسية</span>
      </div>
      <div class="screenshot-body">
        <div style="font-size:11px; color:var(--text-muted); padding:8px 0; margin-bottom:12px; border-bottom:1px solid rgba(255,255,255,0.05);">
          👤 admin | مدير &nbsp;&nbsp; 🔑 الاشتراك: 364 يوم متبقي
        </div>
        <div style="display:grid; grid-template-columns:1fr 1fr; gap:10px; margin-bottom:14px;">
          <div style="background:var(--dark4); border:1px solid rgba(255,255,255,0.08); border-radius:10px; padding:20px; text-align:center;">
            <div style="font-size:22px;">🛒</div>
            <div style="font-size:13px; margin-top:6px; font-weight:700;">بيع جديد</div>
          </div>
          <div style="background:var(--dark4); border:1px solid rgba(255,255,255,0.08); border-radius:10px; padding:20px; text-align:center;">
            <div style="font-size:22px;">📦</div>
            <div style="font-size:13px; margin-top:6px; font-weight:700;">المخزن</div>
          </div>
          <div style="background:var(--dark4); border:1px solid rgba(255,255,255,0.08); border-radius:10px; padding:20px; text-align:center;">
            <div style="font-size:22px;">🛠️</div>
            <div style="font-size:13px; margin-top:6px; font-weight:700;">الصيانة</div>
          </div>
          <div style="background:var(--dark4); border:1px solid rgba(255,255,255,0.08); border-radius:10px; padding:20px; text-align:center;">
            <div style="font-size:22px;">🔄</div>
            <div style="font-size:13px; margin-top:6px; font-weight:700;">المرتجع</div>
          </div>
        </div>
      </div>
    </div>

    <!-- سجل المبيعات -->
    <div class="screenshot-item">
      <div class="screenshot-header">
        <div class="dot dot-r"></div>
        <div class="dot dot-y"></div>
        <div class="dot dot-g"></div>
        <span class="screenshot-title">📊 سجل المبيعات</span>
      </div>
      <div class="screenshot-body">
        <table class="ui-table">
          <thead>
            <tr>
              <th>رقم الفاتورة</th>
              <th>الأصناف</th>
              <th>الإجمالي</th>
              <th>الحالة</th>
            </tr>
          </thead>
          <tbody>
            <tr>
              <td style="color:var(--gold);font-size:11px">20260319001</td>
              <td>2 صنف</td>
              <td>6,500 ريال</td>
              <td><span class="badge badge-green">مباع</span></td>
            </tr>
            <tr>
              <td style="color:var(--gold);font-size:11px">20260318005</td>
              <td>1 صنف</td>
              <td>3,200 ريال</td>
              <td><span class="badge badge-green">مباع</span></td>
            </tr>
            <tr>
              <td style="color:var(--gold);font-size:11px">20260317003</td>
              <td>3 صنف</td>
              <td>8,100 ريال</td>
              <td><span class="badge badge-red">مُرجع جزئياً</span></td>
            </tr>
            <tr>
              <td style="color:var(--gold);font-size:11px">20260316008</td>
              <td>1 صنف</td>
              <td>2,800 ريال</td>
              <td><span class="badge badge-green">مباع</span></td>
            </tr>
          </tbody>
        </table>
        <div style="margin-top:10px; font-size:13px; color:var(--text-muted); text-align:left;">
          الإجمالي: <span style="color:var(--gold); font-weight:700;">20,500 ريال</span> | 4 فواتير
        </div>
      </div>
    </div>

    <!-- التقرير الشهري -->
    <div class="screenshot-item">
      <div class="screenshot-header">
        <div class="dot dot-r"></div>
        <div class="dot dot-y"></div>
        <div class="dot dot-g"></div>
        <span class="screenshot-title">📈 التقرير الشهري</span>
      </div>
      <div class="screenshot-body">
        <div style="display:grid; grid-template-columns:1fr 1fr; gap:8px; margin-bottom:12px;">
          <div style="background:var(--dark4); border-radius:8px; padding:14px;">
            <div style="font-size:11px; color:var(--text-muted); margin-bottom:4px;">إجمالي المبيعات</div>
            <div style="font-size:20px; font-weight:900; color:var(--gold);">85,200</div>
            <div style="font-size:11px; color:var(--text-muted);">ريال</div>
          </div>
          <div style="background:var(--dark4); border-radius:8px; padding:14px;">
            <div style="font-size:11px; color:var(--text-muted); margin-bottom:4px;">صافي الربح</div>
            <div style="font-size:20px; font-weight:900; color:#28c864;">12,400</div>
            <div style="font-size:11px; color:var(--text-muted);">ريال</div>
          </div>
          <div style="background:var(--dark4); border-radius:8px; padding:14px;">
            <div style="font-size:11px; color:var(--text-muted); margin-bottom:4px;">عدد الفواتير</div>
            <div style="font-size:20px; font-weight:900; color:var(--text);">147</div>
            <div style="font-size:11px; color:var(--text-muted);">فاتورة</div>
          </div>
          <div style="background:var(--dark4); border-radius:8px; padding:14px;">
            <div style="font-size:11px; color:var(--text-muted); margin-bottom:4px;">طلبات الصيانة</div>
            <div style="font-size:20px; font-weight:900; color:var(--text);">23</div>
            <div style="font-size:11px; color:var(--text-muted);">طلب</div>
          </div>
        </div>
      </div>
    </div>
  </div>
</section>

<!-- ══ PRICING ══ -->
<section id="pricing">
  <div class="section-label">الأسعار</div>
  <h2 class="section-title">اختر الباقة المناسبة</h2>
  <p class="section-desc">جميع الباقات تشمل جميع المميزات بدون أي قيود</p>

  <div class="pricing-grid">
    <div class="price-card">
      <div class="price-plan">🗓️ الباقة الشهرية</div>
      <div class="price-amount"><span class="price-currency">﷼</span>200</div>
      <div class="price-period">في الشهر</div>
      <ul class="price-features">
        <li>جميع المميزات</li>
        <li>دعم فني</li>
        <li>تحديثات مجانية</li>
        <li>نسخ احتياطي يومي</li>
      </ul>
      <button class="price-btn price-btn-outline" onclick="document.getElementById('contact').scrollIntoView()">اشترك الآن</button>
    </div>

    <div class="price-card featured">
      <div class="price-badge">⭐ الأكثر طلباً</div>
      <div class="price-plan">📅 الباقة السنوية</div>
      <div class="price-amount"><span class="price-currency">﷼</span>1200</div>
      <div class="price-period">في السنة · وفر 1200 ريال</div>
      <ul class="price-features">
        <li>جميع المميزات</li>
        <li>دعم فني أولوية</li>
        <li>تحديثات مجانية</li>
        <li>نسخ احتياطي يومي</li>
        <li>تقارير متقدمة</li>
      </ul>
      <button class="price-btn price-btn-fill" onclick="document.getElementById('contact').scrollIntoView()">اشترك الآن</button>
    </div>

    <div class="price-card">
      <div class="price-plan">📆 باقة 6 شهور</div>
      <div class="price-amount"><span class="price-currency">﷼</span>800</div>
      <div class="price-period">6 أشهر · وفر 400 ريال</div>
      <ul class="price-features">
        <li>جميع المميزات</li>
        <li>دعم فني</li>
        <li>تحديثات مجانية</li>
        <li>نسخ احتياطي يومي</li>
      </ul>
      <button class="price-btn price-btn-outline" onclick="document.getElementById('contact').scrollIntoView()">اشترك الآن</button>
    </div>
  </div>

  <div style="text-align:center; margin-top:40px; padding:20px; background:rgba(200,169,110,0.06); border-radius:12px; max-width:500px; margin:40px auto 0;">
    <div style="font-size:16px; font-weight:700; margin-bottom:8px;">🎁 جرب مجاناً</div>
    <div style="font-size:14px; color:var(--text-muted);">7 أيام تجريبية مجانية بدون الحاجة لبطاقة ائتمان</div>
  </div>
</section>

<!-- ══ VIDEO SCRIPT ══ -->
<section>
  <div class="section-label">سكريبت الفيديو التسويقي</div>
  <h2 class="section-title">فيديو تعريفي جاهز للتصوير</h2>
  <p class="section-desc">سكريبت فيديو 90 ثانية لنشره على انستغرام وتيك توك</p>

  <div class="script-section">
    <div class="script-block" data-time="0:00 - 0:08">
      <h4 class="script-heading">🎬 المقدمة — Hook قوي</h4>
      <p class="script-text">
        <strong>على الشاشة:</strong> صورة فوضى — ورق، دفاتر، حسابات يدوية<br><br>
        <strong>الصوت:</strong> "لو محلك لا يزال يحسب المبيعات يدوي... أنت تخسر وقتك ومالك كل يوم."
      </p>
      <div class="script-note">⚡ Hook قوي يستهدف نقطة الألم المباشرة</div>
    </div>

    <div class="script-block" data-time="0:08 - 0:20">
      <h4 class="script-heading">📱 عرض البرنامج</h4>
      <p class="script-text">
        <strong>على الشاشة:</strong> تصوير شاشة البرنامج — صفحة البيع<br><br>
        <strong>الصوت:</strong> "هذا نظام مبيعات الهاتف والصيانة المتكامل. في ثوانٍ تسجل البيع، تطبع الفاتورة، وتحدث المخزون تلقائياً."
      </p>
    </div>

    <div class="script-block" data-time="0:20 - 0:40">
      <h4 class="script-heading">⚡ عرض المميزات السريع</h4>
      <p class="script-text">
        <strong>على الشاشة:</strong> انتقالات سريعة بين الصفحات<br><br>
        <strong>الصوت:</strong> "إدارة المخزون... تتبع الصيانة... استقبال المرتجعات... تقارير الأرباح الشهرية... كل شيء في مكان واحد."
      </p>
      <div class="script-note">🎵 موسيقى خلفية سريعة وحماسية خلال هذا المقطع</div>
    </div>

    <div class="script-block" data-time="0:40 - 0:55">
      <h4 class="script-heading">🌟 المميز الفريد</h4>
      <p class="script-text">
        <strong>على الشاشة:</strong> ضغط زر تبديل اللغة<br><br>
        <strong>الصوت:</strong> "البرنامج يدعم العربية والإنجليزية بضغطة واحدة. وتقدر تعطيه لموظفيك بصلاحيات مختلفة."
      </p>
    </div>

    <div class="script-block" data-time="0:55 - 1:10">
      <h4 class="script-heading">💰 السعر والـ CTA</h4>
      <p class="script-text">
        <strong>على الشاشة:</strong> شاشة الأسعار<br><br>
        <strong>الصوت:</strong> "ابدأ مجاناً 7 أيام. إذا أعجبك، الاشتراك السنوي بـ 1200 ريال فقط. يعني أقل من 3 ريال في اليوم لإدارة محلك بالكامل."
      </p>
      <div class="script-note">💡 حساب القيمة اليومية يجعل السعر يبدو أرخص جداً</div>
    </div>

    <div class="script-block" data-time="1:10 - 1:20">
      <h4 class="script-heading">📞 الختام</h4>
      <p class="script-text">
        <strong>على الشاشة:</strong> رقم الواتساب والإيميل<br><br>
        <strong>الصوت:</strong> "تواصل معنا على الواتساب للحصول على نسختك. الرابط في البايو."
      </p>
      <div class="script-note">👆 اختم بـ CTA واضح — "الرابط في البايو" أو "راسلنا على الواتساب"</div>
    </div>
  </div>
</section>

<!-- ══ CTA ══ -->
<section id="contact" class="cta-section">
  <div class="cta-title">جاهز تبدأ؟ 🚀</div>
  <p class="cta-desc">7 أيام تجريبية مجانية. لا حاجة لبطاقة ائتمان. ابدأ الآن.</p>

  <div style="display:flex; gap:16px; justify-content:center; flex-wrap:wrap; margin-bottom:20px;">
    <a class="btn-primary" href="https://wa.me/966570347437" target="_blank">
      📱 واتساب الآن
    </a>
    <a class="btn-secondary" href="mailto:morfeuse71@gmail.com">
      📧 راسلنا بالإيميل
    </a>
  </div>

  <div class="contact-cards">
    <a class="contact-card" href="https://wa.me/966570347437" target="_blank">
      <span class="contact-icon">📱</span>
      <div>
        <div class="contact-label">واتساب</div>
        <div class="contact-value">+966 570 347 437</div>
      </div>
    </a>
    <a class="contact-card" href="mailto:morfeuse71@gmail.com">
      <span class="contact-icon">📧</span>
      <div>
        <div class="contact-label">البريد الإلكتروني</div>
        <div class="contact-value">morfeuse71@gmail.com</div>
      </div>
    </a>
  </div>
</section>

<!-- ══ FOOTER ══ -->
<footer>
  <span class="footer-copy">© 2026 Morfy POS — جميع الحقوق محفوظة</span>
  <span class="footer-by">صُنع بـ ❤️ بواسطة morfy</span>
</footer>

</body>
</html>
