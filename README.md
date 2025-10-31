<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="utf-8" />
  <meta name="viewport" content="width=device-width,initial-scale=1" />
  <title>Embrace Community Care — Empowering Independence</title>
  <meta name="description" content="Participant-centred community supports promoting dignity, independence and inclusion.">
  <link href="https://fonts.googleapis.com/css2?family=Inter:wght@400;600;700&display=swap" rel="stylesheet">

  <style>
    /* ===== ROOT & BASE ===== */
    :root {
      --accent:#27e68d;      /* Deep red to match logo */
      --accent-2:#5b2874;    /* Lighter red accent */
      --light-accent:#fff5f5;
      --muted:#555;
      --bg:#ffffff;
      --radius:12px;
      --max-width:1100px;
      font-family:'Inter',system-ui,sans-serif;
    }

    * { box-sizing:border-box; margin:0; padding:0; }
    body { background:var(--bg); color:#222; line-height:1.6; -webkit-font-smoothing:antialiased; }
    img { max-width:100%; display:block; }
    a { text-decoration:none; color:inherit; }
    .container { max-width:var(--max-width); margin:0 auto; padding:1.25rem; }

    /* ===== HEADER ===== */
    header {
      position: sticky;
      top: 0;
      z-index: 100;
      background: var(--accent);
      box-shadow: 0 2px 6px rgba(0,0,0,0.15);
    }
    .header-inner {
      display: flex;
      align-items: center;
      justify-content: space-between;
      padding: 0.8rem 1.25rem;
      max-width: var(--max-width);
      margin: auto;
    }
    .brand {
      display: flex;
      align-items: center;
      gap: 0.6rem;
      color: #fff;
      font-size: 1.3rem;
      font-weight: 700;
    }
    .logo {
      height: 70px;
      width: auto;
      background: transparent;
      border-radius: 8px;
      filter: drop-shadow(0 0 4px rgba(0,0,0,0.4)); /* makes white hand visible on green */
    }
    nav.primary {
      display: flex;
      gap: 1.2rem;
    }
    nav.primary a {
      color: #fff;
      font-weight: 600;
      padding: 0.5rem 0.7rem;
      border-radius: 8px;
      transition: background 0.2s ease;
    }
    nav.primary a:hover { background: rgba(255,255,255,0.2); }
    .nav-toggle {
      display: none;
      background: none;
      border: 1px solid rgba(255,255,255,0.4);
      color: #fff;
      font-size: 1.4rem;
      border-radius: 8px;
      padding: .3rem .6rem;
    }

    /* ===== HERO ===== */
    .hero {
      background: url('https://images.unsplash.com/photo-1556761175-5973dc0f32e7?auto=format&fit=crop&w=1200&q=80') center/cover no-repeat;
      color: #fff;
      position: relative;
      padding: 6rem 1rem;
    }
    .hero::after {
      content: '';
      position: absolute;
      inset: 0;
      background: rgba(0,0,0,0.55);
    }
    .hero-content {
      position: relative;
      z-index: 1;
      max-width: var(--max-width);
      margin: auto;
      text-align: center;
    }
    .hero h1 {
      font-size: 2.6rem;
      margin-bottom: 1rem;
    }
    .hero p {
      font-size: 1.15rem;
      max-width: 700px;
      margin: 0 auto 1.6rem;
    }
    .hero .btn {
      background: var(--accent-2);
      color: #fff;
      padding: .8rem 1.4rem;
      border-radius: 10px;
      font-weight: 700;
      display: inline-block;
      transition: background .3s ease;
    }
    .hero .btn:hover { background: #e1c4c4; }

    /* ===== SECTION BASE ===== */
    section { padding: 3rem 0; }
    h2 {
      font-size: 1.9rem;
      margin-bottom: .5rem;
      text-align: center;
    }
    .section-header p {
      text-align: center;
      color: var(--muted);
      margin-bottom: 2rem;
    }

    /* ===== GRID CARDS ===== */
    .grid {
      display: grid;
      grid-template-columns: repeat(auto-fit, minmax(260px, 1fr));
      gap: 1.25rem;
    }
    .card {
      background: #fff;
      padding: 1.4rem;
      border-radius: var(--radius);
      box-shadow: 0 6px 20px rgba(0,0,0,0.06);
      transition: transform .3s, box-shadow .3s;
    }
    .card:hover {
      transform: translateY(-5px);
      box-shadow: 0 10px 25px rgba(0,0,0,0.08);
    }
    .card h3 { margin-bottom: .5rem; color: var(--accent); }
    .muted { color: var(--muted); }

    /* ===== ABOUT ===== */
    #about .card { background: var(--light-accent); }

    /* ===== LOCATIONS ===== */
    .locations-list {
      list-style: none;
      display: grid;
      grid-template-columns: repeat(auto-fit, minmax(200px, 1fr));
      gap: .8rem;
    }
    .locations-list li {
      background: #f8f8f8;
      padding: .9rem;
      border-radius: 10px;
      border: 1px dashed #ccc;
      text-align: center;
    }

    /* ===== CONTACT ===== */
    .contact-grid {
      display: grid;
      grid-template-columns: 1fr 320px;
      gap: 1.4rem;
      align-items: start;
      margin-top: 1.5rem;
    }
    label { display:block; font-weight:600; margin-bottom:.4rem; }
    input, textarea {
      width:100%; border:1px solid #ccc; border-radius:8px;
      padding:.6rem; font-size:1rem; margin-bottom:.9rem;
    }
    button[type="submit"] {
      background: var(--accent-2); color:#fff; font-weight:700;
      border:none; border-radius:8px; padding:.7rem 1.2rem; cursor:pointer;
    }
    button:hover { background:#b12626; }

    /* ===== FOOTER ===== */
    footer {
      border-top: 1px solid #eee;
      text-align: center;
      padding: 1.5rem 0;
      color: var(--muted);
      font-size: .9rem;
      margin-top: 3rem;
    }

    /* ===== ANIMATIONS ===== */
    .fade-up { opacity: 0; transform: translateY(20px); transition: opacity .6s ease, transform .6s ease; }
    .fade-up.visible { opacity: 1; transform: none; }

    /* ===== RESPONSIVE ===== */
    @media (max-width:960px) { .contact-grid { grid-template-columns:1fr; } }
    @media (max-width:720px) {
      nav.primary { display:none; }
      .nav-toggle { display:inline-block; }
      .mobile-nav {
        display:none; position:absolute; top:70px; right:1rem; background:#fff; color:#222;
        border-radius:10px; box-shadow:0 10px 25px rgba(0,0,0,0.1); padding:1rem;
      }
      .mobile-nav.open { display:block; }
      .mobile-nav a { display:block; padding:.6rem 0; color:var(--accent); font-weight:600; }
    }
  </style>
</head>

<body>
  <!-- ===== HEADER ===== -->
  <header>
    <div class="header-inner">
      <a href="#" class="brand">
        <img src="embrace logo.png" alt="Embrace Community Care Logo" class="logo">
        Embrace Community Care
      </a>
      <button class="nav-toggle" id="navToggle" aria-label="Toggle navigation">☰</button>
      <nav class="primary" aria-label="Main navigation">
        <a href="#home">Home</a>
        <a href="#about">About</a>
        <a href="#services">Services</a>
        <a href="#locations">Locations</a>
        <a href="#news">News</a>
        <a href="#contact">Contact</a>
      </nav>
    </div>

  </header>

  <!-- ===== HERO ===== -->
  <section id="home" class="hero">
    <div class="hero-content fade-up">
      <h1>Empowering people through participant-centred community supports</h1>
      <p>We provide compassionate, tailored disability and community programs that promote dignity, inclusion and independence.</p>
      <a href="#contact" class="btn">Get in Touch</a>
    </div>
  </section>

  <main>
    <!-- ===== ABOUT ===== -->
    <section id="about" class="fade-up">
      <div class="container">
        <div class="section-header">
          <h2>About Our Approach</h2>
          <p>We partner with participants to design personalised support plans that reflect their strengths, goals and preferences.</p>
        </div>
        <div class="grid">
          <div class="card"><h3>Person-centred Planning</h3><p>Collaborative, goal-oriented plans developed with participants and their families.</p></div>
          <div class="card"><h3>Qualified Support Workforce</h3><p>Trained professionals experienced in positive behaviour and safeguarding practices.</p></div>
          <div class="card"><h3>Inclusive Community Programs</h3><p>Encouraging participation, confidence and connection through meaningful activities.</p></div>
        </div>
      </div>
    </section>

    <!-- ===== SERVICES ===== -->
    <section id="services" class="fade-up">
      <div class="container">
        <div class="section-header">
          <h2>Our Services</h2>
          <p>Comprehensive supports designed around individual needs and aspirations.</p>
        </div>
        <div class="grid">
          <div class="card"><h3>Personal Care Assistance(SIL)</h3><p>Compassionate support with daily activities like bathing, dressing, mobility, and medication reminders to promote comfort and dignity at home.</p></div>
          <div class="card"><h3>Companionship & Social Support</h3><p>Friendly caregivers offering conversation, activities, and outings to keep seniors engaged, happy, and connected.</p></div>
          <div class="card"><h3>Home Help & Meal Preparation</h3><p>Reliable help with cleaning, laundry, shopping, and healthy meal preparation for a safe and comfortable living space</p></div>
          <div class="card"><h3>Specialized & Respite Care</h3><p>Tailored care for seniors with medical or special needs, plus short-term relief for family caregivers.</p></div>
        </div>
      </div>
    </section>

    <!-- ===== LOCATIONS ===== -->
    <section id="locations" class="fade-up">
      <div class="container">
        <div class="section-header">
          <h2>Our Locations</h2>
          <p>Accessible services across Nepal — contact us for availability.</p>
        </div>
        <ul class="locations-list">
          <li>Kathmandu — Head Office</li>
          <li>Butwal — Supported Living</li>
          
        </ul>
      </div>
    </section>

    <!-- ===== NEWS ===== -->
    <section id="news" class="fade-up">
      <div class="container">
        <div class="section-header">
          <h2>Latest News</h2>
          <p>Friendly & Warm.</p>
        </div>
        <div class="grid">
          <div class="card"><h3>We’re Opening Soon!</h3><p>We’re excited to announce that our compassionate in-home aged care services will be launching soon! Our team is dedicated to helping seniors live safely, comfortably, and independently in their own homes. Stay tuned for our official opening date — we can’t wait to start caring for your loved ones</p></div>
          <div class="card"><h3>Coming Soon: Quality Care at Home</h3><p>Our new aged care service is set to open soon, offering professional, reliable, and heartfelt support for seniors who wish to remain in the comfort of their own homes. From personal care to companionship, we’re here to make every day easier and brighter.</p></div>
        </div>
      </div>
    </section>

    <!-- ===== CONTACT ===== -->
    <section id="contact" class="fade-up">
      <div class="container">
        <div class="section-header">
          <h2>Contact Us</h2>
          <p>We’d love to hear from you — reach out for service enquiries or collaboration.</p>
        </div>
        <div class="contact-grid">
          <form id="contactForm" action="https://formspree.io/f/your-id-here" method="POST">
            <label>Full name<input type="text" name="name" required></label>
            <label>Email<input type="email" name="email" required></label>
            <label>Phone<input type="tel" name="phone"></label>
            <label>Message<textarea name="message" rows="5" required></textarea></label>
            <button type="submit">Send Message</button>
            <div id="formStatus" class="muted small"></div>
          </form>
          <aside class="card">
            <h3>Head Office</h3>
            <p> New Baneshwor, Kathmandu</p>
            <p>Phone: <a href="tel:+9779883232233">+977 988-323-2233</a></p>
            <p>Email: <a href="mailto:info@embracecommunitycare.com">info@embracecommunitycare.com</a></p>
            <p><strong>Hours:</strong><br>Mon–Fri 10:00–16:00</p>
          </aside>
        </div>
      </div>
    </section>
  </main>

  <footer>© <span id="year"></span> Embrace Community Care. All rights reserved.</footer>

  <script>
    // Dynamic year
    document.getElementById('year').textContent = new Date().getFullYear();

    // Mobile menu toggle
    const navToggle=document.getElementById('navToggle');
    const mobileNav=document.getElementById('mobileNav');
    navToggle.addEventListener('click',()=>{
      mobileNav.classList.toggle('open');
      mobileNav.setAttribute('aria-hidden', !mobileNav.classList.contains('open'));
    });

    // Fade-up animation
    const observer=new IntersectionObserver((entries)=>{
      entries.forEach(e=>{ if(e.isIntersecting) e.target.classList.add('visible'); });
    },{threshold:0.15});
    document.querySelectorAll('.fade-up').forEach(el=>observer.observe(el));

    // Contact form (Formspree)
    const form=document.getElementById('contactForm');
    const status=document.getElementById('formStatus');
    form?.addEventListener('submit',async(e)=>{
      e.preventDefault();status.textContent='Sending...';
      try{
        const res=await fetch(form.action,{method:'POST',body:new FormData(form),headers:{Accept:'application/json'}});
        if(res.ok){status.textContent='Message sent!';form.reset();}
        else status.textContent='Error sending message.';
      }catch{status.textContent='Network error. Try again.';}
    });
  </script>
</body>
</html>

