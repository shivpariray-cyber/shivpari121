# shivpari121
html

<!DOCTYPE html>
<html lang="en">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>Shivpari Home Services</title>
<link href="https://fonts.googleapis.com/css2?family=Bebas+Neue&family=Nunito:wght@400;600;700;800&display=swap" rel="stylesheet">
<style>
  :root {
    --orange: #FF6B2B;
    --dark: #0D1117;
    --dark2: #161B22;
    --white: #F5F5F0;
    --gray: #8B949E;
    --light-orange: #FF8C55;
    --card-bg: #1C2333;
  }

  * { margin: 0; padding: 0; box-sizing: border-box; }

  html { scroll-behavior: smooth; }

  body {
    background: var(--dark);
    color: var(--white);
    font-family: 'Nunito', sans-serif;
    overflow-x: hidden;
  }

  /* ─── NAV ─── */
  nav {
    position: fixed; top: 0; left: 0; right: 0; z-index: 100;
    display: flex; align-items: center; justify-content: space-between;
    padding: 18px 6vw;
    background: rgba(13,17,23,0.85);
    backdrop-filter: blur(14px);
    border-bottom: 1px solid rgba(255,107,43,0.15);
  }
  .logo {
    font-family: 'Bebas Neue', sans-serif;
    font-size: 2rem; letter-spacing: 3px;
    color: var(--orange);
    text-shadow: 0 0 30px rgba(255,107,43,0.5);
  }
  .nav-links { display: flex; gap: 32px; list-style: none; }
  .nav-links a {
    color: var(--gray); text-decoration: none; font-weight: 600;
    font-size: 0.9rem; letter-spacing: 1px; text-transform: uppercase;
    transition: color 0.2s;
  }
  .nav-links a:hover { color: var(--orange); }
  .nav-cta {
    background: var(--orange); color: #fff;
    padding: 10px 24px; border-radius: 6px;
    font-weight: 800; font-size: 0.85rem; letter-spacing: 1px;
    text-decoration: none; transition: background 0.2s, transform 0.2s;
  }
  .nav-cta:hover { background: var(--light-orange); transform: translateY(-1px); }

  /* ─── HERO ─── */
  .hero {
    min-height: 100vh;
    display: flex; align-items: center;
    padding: 120px 6vw 80px;
    position: relative; overflow: hidden;
  }
  .hero::before {
    content: '';
    position: absolute; inset: 0;
    background:
      radial-gradient(ellipse 60% 70% at 70% 50%, rgba(255,107,43,0.12) 0%, transparent 70%),
      radial-gradient(ellipse 40% 40% at 20% 80%, rgba(255,107,43,0.06) 0%, transparent 70%);
  }
  .hero-grid {
    display: grid; grid-template-columns: 1fr 1fr;
    gap: 60px; align-items: center; max-width: 1200px; margin: 0 auto; width: 100%;
    position: relative; z-index: 1;
  }
  .hero-badge {
    display: inline-flex; align-items: center; gap: 8px;
    background: rgba(255,107,43,0.12); border: 1px solid rgba(255,107,43,0.3);
    padding: 6px 16px; border-radius: 50px; font-size: 0.8rem;
    font-weight: 700; letter-spacing: 2px; text-transform: uppercase;
    color: var(--orange); margin-bottom: 24px;
    animation: fadeUp 0.7s ease both;
  }
  .hero-badge span { width: 8px; height: 8px; background: var(--orange); border-radius: 50%; animation: pulse 1.5s infinite; }
  @keyframes pulse { 0%,100%{opacity:1;transform:scale(1)} 50%{opacity:0.5;transform:scale(1.4)} }

  h1 {
    font-family: 'Bebas Neue', sans-serif;
    font-size: clamp(3.5rem, 6vw, 5.5rem);
    line-height: 0.95; letter-spacing: 2px;
    animation: fadeUp 0.7s 0.1s ease both;
  }
  h1 em { color: var(--orange); font-style: normal; }
  .hero-sub {
    margin-top: 20px; font-size: 1.1rem; color: var(--gray);
    line-height: 1.7; max-width: 440px;
    animation: fadeUp 0.7s 0.2s ease both;
  }
  .hero-btns {
    display: flex; gap: 16px; margin-top: 36px;
    animation: fadeUp 0.7s 0.3s ease both;
  }
  .btn-primary {
    background: var(--orange); color: #fff;
    padding: 14px 32px; border-radius: 8px;
    font-weight: 800; font-size: 1rem;
    text-decoration: none; transition: all 0.25s;
    box-shadow: 0 8px 30px rgba(255,107,43,0.35);
  }
  .btn-primary:hover { transform: translateY(-3px); box-shadow: 0 14px 40px rgba(255,107,43,0.5); }
  .btn-secondary {
    border: 2px solid rgba(255,255,255,0.15); color: var(--white);
    padding: 14px 32px; border-radius: 8px;
    font-weight: 700; font-size: 1rem;
    text-decoration: none; transition: all 0.25s;
  }
  .btn-secondary:hover { border-color: var(--orange); color: var(--orange); }

  /* Hero visual */
  .hero-visual {
    display: grid; grid-template-columns: 1fr 1fr; gap: 16px;
    animation: fadeUp 0.8s 0.2s ease both;
  }
  .service-card-mini {
    background: var(--card-bg);
    border: 1px solid rgba(255,255,255,0.06);
    border-radius: 16px; padding: 24px 20px;
    transition: transform 0.3s, border-color 0.3s;
    cursor: default;
  }
  .service-card-mini:hover { transform: translateY(-6px); border-color: rgba(255,107,43,0.4); }
  .service-card-mini.featured { grid-column: span 2; display: flex; align-items: center; gap: 20px; }
  .icon-wrap {
    width: 52px; height: 52px; border-radius: 12px;
    background: rgba(255,107,43,0.15);
    display: flex; align-items: center; justify-content: center;
    font-size: 1.6rem; flex-shrink: 0;
  }
  .service-card-mini h3 { font-size: 1rem; font-weight: 800; margin-top: 14px; }
  .service-card-mini.featured h3 { margin-top: 0; font-size: 1.1rem; }
  .service-card-mini p { font-size: 0.82rem; color: var(--gray); margin-top: 6px; line-height: 1.5; }

  /* stats */
  .stats-row {
    display: flex; gap: 48px; margin-top: 48px;
    animation: fadeUp 0.7s 0.4s ease both;
  }
  .stat-item { }
  .stat-num {
    font-family: 'Bebas Neue', sans-serif;
    font-size: 2.4rem; color: var(--orange); line-height: 1;
  }
  .stat-label { font-size: 0.8rem; color: var(--gray); font-weight: 600; letter-spacing: 1px; margin-top: 4px; }

  @keyframes fadeUp {
    from { opacity: 0; transform: translateY(28px); }
    to   { opacity: 1; transform: translateY(0); }
  }

  /* ─── SERVICES ─── */
  section { padding: 100px 6vw; }
  .section-label {
    font-size: 0.8rem; font-weight: 700; letter-spacing: 3px;
    text-transform: uppercase; color: var(--orange); margin-bottom: 14px;
  }
  .section-title {
    font-family: 'Bebas Neue', sans-serif;
    font-size: clamp(2.5rem, 4vw, 3.5rem); line-height: 1;
    margin-bottom: 16px;
  }
  .section-sub { color: var(--gray); font-size: 1.05rem; line-height: 1.7; max-width: 520px; }

  .services-grid {
    display: grid; grid-template-columns: repeat(auto-fit, minmax(260px, 1fr));
    gap: 24px; margin-top: 56px;
  }
  .svc-card {
    background: var(--card-bg);
    border: 1px solid rgba(255,255,255,0.06);
    border-radius: 20px; padding: 36px 28px;
    position: relative; overflow: hidden;
    transition: transform 0.3s, border-color 0.3s, box-shadow 0.3s;
  }
  .svc-card::before {
    content: ''; position: absolute; top: 0; left: 0; right: 0; height: 3px;
    background: linear-gradient(90deg, var(--orange), transparent);
    opacity: 0; transition: opacity 0.3s;
  }
  .svc-card:hover { transform: translateY(-8px); border-color: rgba(255,107,43,0.3); box-shadow: 0 20px 60px rgba(0,0,0,0.4); }
  .svc-card:hover::before { opacity: 1; }
  .svc-icon { font-size: 2.4rem; margin-bottom: 20px; }
  .svc-card h3 { font-size: 1.25rem; font-weight: 800; margin-bottom: 12px; }
  .svc-card p { color: var(--gray); font-size: 0.92rem; line-height: 1.7; }
  .svc-list { list-style: none; margin-top: 18px; }
  .svc-list li {
    font-size: 0.85rem; color: var(--gray); padding: 6px 0;
    border-bottom: 1px solid rgba(255,255,255,0.05);
    display: flex; align-items: center; gap: 10px;
  }
  .svc-list li::before { content: '→'; color: var(--orange); font-weight: 800; }

  /* ─── WHY US ─── */
  .why-grid {
    display: grid; grid-template-columns: 1fr 1fr;
    gap: 80px; align-items: center; max-width: 1200px; margin: 0 auto;
  }
  .why-items { display: flex; flex-direction: column; gap: 32px; margin-top: 48px; }
  .why-item { display: flex; gap: 20px; align-items: flex-start; }
  .why-num {
    font-family: 'Bebas Neue', sans-serif; font-size: 3rem; color: rgba(255,107,43,0.2);
    line-height: 1; flex-shrink: 0;
  }
  .why-item h4 { font-size: 1.05rem; font-weight: 800; margin-bottom: 6px; }
  .why-item p { color: var(--gray); font-size: 0.9rem; line-height: 1.6; }

  .why-visual {
    background: var(--card-bg); border-radius: 24px;
    padding: 40px; border: 1px solid rgba(255,255,255,0.06);
    text-align: center;
  }
  .big-stat { margin-bottom: 40px; }
  .big-num {
    font-family: 'Bebas Neue', sans-serif; font-size: 5rem; color: var(--orange); line-height: 1;
    text-shadow: 0 0 40px rgba(255,107,43,0.4);
  }
  .big-label { color: var(--gray); font-size: 0.9rem; font-weight: 600; margin-top: 4px; }
  .divider { height: 1px; background: rgba(255,255,255,0.06); margin: 28px 0; }
  .mini-stats { display: flex; justify-content: space-around; }
  .mini-stat .num { font-family: 'Bebas Neue', sans-serif; font-size: 2.2rem; color: var(--white); }
  .mini-stat .lbl { font-size: 0.78rem; color: var(--gray); font-weight: 600; }

  /* ─── TESTIMONIALS ─── */
  .testimonials-bg { background: var(--dark2); }
  .test-grid { display: grid; grid-template-columns: repeat(auto-fit, minmax(280px, 1fr)); gap: 24px; margin-top: 56px; }
  .test-card {
    background: var(--card-bg); border-radius: 20px; padding: 32px;
    border: 1px solid rgba(255,255,255,0.06);
    transition: transform 0.3s;
  }
  .test-card:hover { transform: translateY(-6px); }
  .stars { color: var(--orange); font-size: 1rem; margin-bottom: 16px; }
  .test-card blockquote { font-size: 0.95rem; color: var(--gray); line-height: 1.7; font-style: italic; }
  .reviewer { display: flex; align-items: center; gap: 14px; margin-top: 24px; }
  .avatar {
    width: 44px; height: 44px; border-radius: 50%;
    background: linear-gradient(135deg, var(--orange), #ff3d00);
    display: flex; align-items: center; justify-content: center;
    font-weight: 800; font-size: 1rem;
  }
  .reviewer-info strong { display: block; font-weight: 800; font-size: 0.9rem; }
  .reviewer-info span { font-size: 0.78rem; color: var(--gray); }

  /* ─── CONTACT ─── */
  .contact-grid {
    display: grid; grid-template-columns: 1fr 1fr;
    gap: 80px; align-items: start; max-width: 1100px; margin: 0 auto;
  }
  .contact-items { display: flex; flex-direction: column; gap: 28px; margin-top: 40px; }
  .contact-item { display: flex; gap: 18px; align-items: flex-start; }
  .contact-icon {
    width: 48px; height: 48px; border-radius: 12px;
    background: rgba(255,107,43,0.12); border: 1px solid rgba(255,107,43,0.2);
    display: flex; align-items: center; justify-content: center;
    font-size: 1.3rem; flex-shrink: 0;
  }
  .contact-item h4 { font-weight: 800; font-size: 0.95rem; margin-bottom: 4px; }
  .contact-item p { color: var(--gray); font-size: 0.88rem; }

  .contact-form { display: flex; flex-direction: column; gap: 16px; margin-top: 40px; }
  .form-row { display: grid; grid-template-columns: 1fr 1fr; gap: 16px; }
  input, textarea, select {
    background: var(--card-bg); border: 1px solid rgba(255,255,255,0.08);
    border-radius: 10px; padding: 14px 18px; color: var(--white);
    font-family: 'Nunito', sans-serif; font-size: 0.95rem; width: 100%;
    transition: border-color 0.2s;
  }
  input::placeholder, textarea::placeholder { color: var(--gray); }
  input:focus, textarea:focus, select:focus {
    outline: none; border-color: rgba(255,107,43,0.5);
    box-shadow: 0 0 0 3px rgba(255,107,43,0.1);
  }
  select option { background: var(--dark2); }
  textarea { resize: vertical; min-height: 130px; }
  .form-submit {
    background: var(--orange); color: #fff; border: none;
    padding: 15px 32px; border-radius: 10px; font-weight: 800;
    font-size: 1rem; cursor: pointer; transition: all 0.25s;
    font-family: 'Nunito', sans-serif; letter-spacing: 0.5px;
    box-shadow: 0 8px 30px rgba(255,107,43,0.3);
  }
  .form-submit:hover { transform: translateY(-3px); box-shadow: 0 14px 40px rgba(255,107,43,0.5); }

  /* ─── FOOTER ─── */
  footer {
    background: var(--dark2); border-top: 1px solid rgba(255,255,255,0.06);
    padding: 40px 6vw; display: flex;
    align-items: center; justify-content: space-between;
    flex-wrap: wrap; gap: 20px;
  }
  footer .logo { font-size: 1.5rem; }
  footer p { color: var(--gray); font-size: 0.85rem; }
  .footer-links { display: flex; gap: 24px; list-style: none; }
  .footer-links a { color: var(--gray); text-decoration: none; font-size: 0.85rem; transition: color 0.2s; }
  .footer-links a:hover { color: var(--orange); }

  /* ─── RESPONSIVE ─── */
  @media (max-width: 900px) {
    .hero-grid, .why-grid, .contact-grid { grid-template-columns: 1fr; gap: 40px; }
    .hero-visual { display: none; }
    .nav-links { display: none; }
    .form-row { grid-template-columns: 1fr; }
    footer { flex-direction: column; text-align: center; }
  }
</style>
</head>
<body>

<!-- NAV -->
<nav>
  <div class="logo">SHIVPARI</div>
  <ul class="nav-links">
    <li><a href="#services">Services</a></li>
    <li><a href="#why">Why Us</a></li>
    <li><a href="#reviews">Reviews</a></li>
    <li><a href="#contact">Contact</a></li>
  </ul>
  <a href="#contact" class="nav-cta">Book Now</a>
</nav>

<!-- HERO -->
<section class="hero">
  <div class="hero-grid">
    <div>
      <div class="hero-badge"><span></span> Trusted Home Services</div>
      <h1>YOUR HOME,<br><em>EXPERTLY</em><br>CARED FOR</h1>
      <p class="hero-sub">AC repair, electrical wiring, plumbing, drainage, and carpentry — all under one roof. Fast, reliable, and affordable.</p>
      <div class="hero-btns">
        <a href="#contact" class="btn-primary">Book a Service</a>
        <a href="#services" class="btn-secondary">See Services</a>
      </div>
      <div class="stats-row">
        <div class="stat-item">
          <div class="stat-num">500+</div>
          <div class="stat-label">Happy Clients</div>
        </div>
        <div class="stat-item">
          <div class="stat-num">5+</div>
          <div class="stat-label">Years Experience</div>
        </div>
        <div class="stat-item">
          <div class="stat-num">24/7</div>
          <div class="stat-label">Emergency Support</div>
        </div>
      </div>
    </div>
    <div class="hero-visual">
      <div class="service-card-mini featured">
        <div class="icon-wrap">❄️</div>
        <div>
          <h3>AC Repair & Service</h3>
          <p>Quick diagnosis and repair by certified technicians.</p>
        </div>
      </div>
      <div class="service-card-mini">
        <div class="icon-wrap">⚡</div>
        <h3>House Wiring</h3>
        <p>Safe, code-compliant electrical installations.</p>
      </div>
      <div class="service-card-mini">
        <div class="icon-wrap">🔧</div>
        <h3>Plumbing</h3>
        <p>Leak fixes, drainage & pipe work.</p>
      </div>
    </div>
  </div>
</section>

<!-- SERVICES -->
<section id="services" style="background: var(--dark2);">
  <div style="max-width:1200px; margin:0 auto;">
    <div class="section-label">What We Offer</div>
    <h2 class="section-title">OUR SERVICES</h2>
    <p class="section-sub">Professional solutions for every corner of your home, delivered by skilled and experienced technicians.</p>
    <div class="services-grid">
      <div class="svc-card">
        <div class="svc-icon">❄️</div>
        <h3>AC Repair & Service</h3>
        <p>Complete air conditioner maintenance, repair, and installation for all brands.</p>
        <ul class="svc-list">
          <li>AC Installation & Setup</li>
          <li>Gas Refilling & Cleaning</li>
          <li>Fault Diagnosis & Repair</li>
          <li>Annual Maintenance Contract</li>
        </ul>
      </div>
      <div class="svc-card">
        <div class="svc-icon">⚡</div>
        <h3>House Wiring</h3>
        <p>Safe and reliable electrical work for new constructions and renovations.</p>
        <ul class="svc-list">
          <li>Full Home Wiring</li>
          <li>Switchboard & Panel Work</li>
          <li>Fan & Light Fitting</li>
          <li>Short Circuit Repair</li>
        </ul>
      </div>
      <div class="svc-card">
        <div class="svc-icon">🚿</div>
        <h3>Plumbing & Drainage</h3>
        <p>Expert plumbing for leaks, blockages, pipework, and complete drainage systems.</p>
        <ul class="svc-list">
          <li>Pipe Fitting & Repair</li>
          <li>Drain Cleaning & Unblocking</li>
          <li>Bathroom Fitting</li>
          <li>Water Tank Installation</li>
        </ul>
      </div>
      <div class="svc-card">
        <div class="svc-icon">🪵</div>
        <h3>Carpentry</h3>
        <p>Custom woodwork and furniture solutions crafted with precision and care.</p>
        <ul class="svc-list">
          <li>Door & Window Fitting</li>
          <li>Furniture Repair & Making</li>
          <li>Modular Wardrobe Work</li>
          <li>False Ceiling & Partitions</li>
        </ul>
      </div>
    </div>
  </div>
</section>

<!-- WHY US -->
<section id="why">
  <div class="why-grid">
    <div>
      <div class="section-label">Why Choose Us</div>
      <h2 class="section-title">QUALITY YOU CAN<br><span style="color:var(--orange)">COUNT ON</span></h2>
      <div class="why-items">
        <div class="why-item">
          <div class="why-num">01</div>
          <div>
            <h4>Certified & Experienced Technicians</h4>
            <p>All our workers are trained professionals with years of field experience across all services.</p>
          </div>
        </div>
        <div class="why-item">
          <div class="why-num">02</div>
          <div>
            <h4>On-Time, Every Time</h4>
            <p>We respect your time. Our team arrives on schedule and completes work with no unnecessary delays.</p>
          </div>
        </div>
        <div class="why-item">
          <div class="why-num">03</div>
          <div>
            <h4>Transparent Pricing</h4>
            <p>No hidden charges. You get a clear quote before work begins — what we say is what you pay.</p>
          </div>
        </div>
        <div class="why-item">
          <div class="why-num">04</div>
          <div>
            <h4>24/7 Emergency Support</h4>
            <p>Breakdowns don't wait for business hours. We're available round the clock for urgent calls.</p>
          </div>
        </div>
      </div>
    </div>
    <div class="why-visual">
      <div class="big-stat">
        <div class="big-num">98%</div>
        <div class="big-label">Customer Satisfaction Rate</div>
      </div>
      <div class="divider"></div>
      <div class="mini-stats">
        <div class="mini-stat">
          <div class="num">500+</div>
          <div class="lbl">Jobs Done</div>
        </div>
        <div class="mini-stat">
          <div class="num">5+</div>
          <div class="lbl">Years Active</div>
        </div>
        <div class="mini-stat">
          <div class="num">4</div>
          <div class="lbl">Services</div>
        </div>
      </div>
    </div>
  </div>
</section>

<!-- TESTIMONIALS -->
<section id="reviews" class="testimonials-bg">
  <div style="max-width:1200px; margin:0 auto;">
    <div class="section-label">Customer Reviews</div>
    <h2 class="section-title">WHAT PEOPLE SAY</h2>
    <div class="test-grid">
      <div class="test-card">
        <div class="stars">★★★★★</div>
        <blockquote>"My AC stopped working in peak summer. Shivpari sent a technician within 2 hours and it was fixed the same day. Excellent service!"</blockquote>
        <div class="reviewer">
          <div class="avatar">R</div>
          <div class="reviewer-info">
            <strong>Ramesh Kumar</strong>
            <span>AC Service Customer</span>
          </div>
        </div>
      </div>
      <div class="test-card">
        <div class="stars">★★★★★</div>
        <blockquote>"Got complete house wiring done for my new flat. Very professional team, clean work, and the pricing was very fair. Highly recommend!"</blockquote>
        <div class="reviewer">
          <div class="avatar">P</div>
          <div class="reviewer-info">
            <strong>Priya Sharma</strong>
            <span>Electrical Wiring Customer</span>
          </div>
        </div>
      </div>
      <div class="test-card">
        <div class="stars">★★★★★</div>
        <blockquote>"Had a major drainage blockage. Shivpari team came quickly, resolved it cleanly without making a big mess. Very satisfied with the work."</blockquote>
        <div class="reviewer">
          <div class="avatar">A</div>
          <div class="reviewer-info">
            <strong>Arvind Singh</strong>
            <span>Plumbing Customer</span>
          </div>
        </div>
      </div>
    </div>
  </div>
</section>

<!-- CONTACT -->
<section id="contact">
  <div class="contact-grid">
    <div>
      <div class="section-label">Get In Touch</div>
      <h2 class="section-title">BOOK A<br><span style="color:var(--orange)">SERVICE</span></h2>
      <p class="section-sub">Fill in the form or reach us directly. We'll get back to you within the hour.</p>
      <div class="contact-items">
        <div class="contact-item">
          <div class="contact-icon">📞</div>
          <div>
            <h4>Call / WhatsApp</h4>
            <p>+91 XXXXX XXXXX</p>
          </div>
        </div>
        <div class="contact-item">
          <div class="contact-icon">📍</div>
          <div>
            <h4>Location</h4>
            <p>Jamshedpur, Jharkhand</p>
          </div>
        </div>
        <div class="contact-item">
          <div class="contact-icon">🕐</div>
          <div>
            <h4>Working Hours</h4>
            <p>Mon–Sun: 7:00 AM – 10:00 PM<br>Emergency support: 24/7</p>
          </div>
        </div>
      </div>
    </div>
    <div>
      <form class="contact-form" onsubmit="handleSubmit(event)">
        <div class="form-row">
          <input type="text" placeholder="Your Name" required>
          <input type="tel" placeholder="Phone Number" required>
        </div>
        <select required>
          <option value="" disabled selected>Select Service</option>
          <option>AC Repair & Service</option>
          <option>House Wiring</option>
          <option>Plumbing & Drainage</option>
          <option>Carpentry</option>
          <option>Multiple Services</option>
        </select>
        <input type="text" placeholder="Your Address / Area">
        <textarea placeholder="Describe your problem (optional)"></textarea>
        <button type="submit" class="form-submit">📩 Send Booking Request</button>
      </form>
    </div>
  </div>
</section>

<!-- FOOTER -->
<footer>
  <div class="logo">SHIVPARI</div>
  <p>© 2026 Shivpari Home Services. All rights reserved.</p>
  <ul class="footer-links">
    <li><a href="#services">Services</a></li>
    <li><a href="#why">About</a></li>
    <li><a href="#contact">Contact</a></li>
  </ul>
</footer>

<script>
  function handleSubmit(e) {
    e.preventDefault();
    const btn = e.target.querySelector('.form-submit');
    btn.textContent = '✅ Request Sent! We\'ll call you shortly.';
    btn.style.background = '#22c55e';
    btn.disabled = true;
    setTimeout(() => {
      btn.textContent = '📩 Send Booking Request';
      btn.style.background = '';
      btn.disabled = false;
      e.target.reset();
    }, 4000);
  }

  // Scroll reveal
  const observer = new IntersectionObserver((entries) => {
    entries.forEach(e => {
      if (e.isIntersecting) {
        e.target.style.opacity = '1';
        e.target.style.transform = 'translateY(0)';
      }
    });
  }, { threshold: 0.1 });

  document.querySelectorAll('.svc-card, .test-card, .why-item, .contact-item').forEach(el => {
    el.style.opacity = '0';
    el.style.transform = 'translateY(30px)';
    el.style.transition = 'opacity 0.6s ease, transform 0.6s ease';
    observer.observe(el);
  });
</script>
</body>
</html>
