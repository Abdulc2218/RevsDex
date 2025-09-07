
<html>
<head>
  <title>AI Design Assistant – Landing Page</title>
  <meta name="description" content="Your AI‑Powered Design Assistant. Generate, customize, and perfect designs with cutting‑edge AI." />
  <link rel="preconnect" href="https://fonts.googleapis.com">
  <link rel="preconnect" href="https://fonts.gstatic.com" crossorigin>
  <link href="https://fonts.googleapis.com/css2?family=Inter:wght@300;400;500;600;700;800;900&display=swap" rel="stylesheet">
  <style>
    :root{
      --bg: #0b0c10;             
      --panel: #101218;          
      --card: #151827;           
      --muted: #a8b0c2;          
      --text: #f5f7ff;           
      --accent: #8b5cf6;         
      --accent-2: #b794f6;      
      --ring: rgba(139,92,246,.55);
      --grad: conic-gradient(from 160deg at 50% 50%, #8b5cf6 0%, #4f46e5 30%, #06b6d4 55%, #8b5cf6 100%);
      --radius-xl: 20px;
      --radius-2xl: 28px;
      --shadow-1: 0 10px 30px rgba(0,0,0,.45);
      --shadow-2: 0 24px 70px rgba(0,0,0,.6);
      --border: 1px solid rgba(255,255,255,.06);
    }

    *{box-sizing:border-box}
    html,body{height:100%}
    body{
      margin:0;
      font-family: Inter, system-ui, -apple-system, Segoe UI, Roboto, Helvetica, Arial, "Apple Color Emoji","Segoe UI Emoji";
      color:var(--text);
      background: radial-gradient(1200px 800px at 10% -10%, rgba(139,92,246,.07), transparent 50%),
                  radial-gradient(800px 600px at 110% 10%, rgba(79,70,229,.08), transparent 40%),
                  var(--bg);
      line-height:1.6;
    }

    a{color:inherit;text-decoration:none}
    .container{width:min(1200px, 92vw); margin-inline:auto}
    .section{padding:72px 0}
    .grid{display:grid; gap:24px}

    /* Header */
    header{
      position:sticky; top:0; z-index:50;
      backdrop-filter:saturate(160%) blur(12px);
      background:linear-gradient(to bottom, rgba(16,18,24,.9), rgba(16,18,24,.65));
      border-bottom:var(--border);
    }
    .nav{display:flex; align-items:center; justify-content:space-between; padding:16px 0}
    .brand{display:flex; align-items:center; gap:12px; font-weight:800; letter-spacing:.2px}
    .logo{
      width:36px; height:36px; border-radius:10px; position:relative; overflow:hidden; flex:0 0 auto;
      box-shadow: inset 0 0 0 1px rgba(255,255,255,.08), 0 8px 24px rgba(139,92,246,.25);
      background: radial-gradient(120% 120% at 10% 10%, #8b5cf6 0%, #4f46e5 40%, #0ea5e9 90%);
    }
    nav a{opacity:.9; font-weight:500; padding:10px 12px; border-radius:10px}
    nav a:hover{background:rgba(255,255,255,.04)}

    .btn{display:inline-flex; align-items:center; justify-content:center; gap:10px; font-weight:700; letter-spacing:.2px;
      padding:12px 18px; border-radius:14px; border:var(--border); position:relative; overflow:hidden}
    .btn-primary{
      background:linear-gradient(180deg, var(--accent), #5b3be6);
      box-shadow: 0 10px 24px rgba(139,92,246,.4);
      border-color: transparent;
    }
    .btn-ghost{background:rgba(255,255,255,.02)}

    /* Hero */
    .hero{display:grid; grid-template-columns: 1.15fr .85fr; gap:40px; align-items:center; padding:56px 0}
    .badge{display:inline-flex; align-items:center; gap:8px; padding:8px 12px; border-radius:999px; font-size:.85rem; background:rgba(139,92,246,.12); border:1px solid rgba(139,92,246,.25)}
    h1{font-size: clamp(36px, 4.2vw, 56px); line-height:1.05; margin:16px 0 18px; letter-spacing:-.5px}
    h1 .accent{background:linear-gradient(90deg, var(--accent), #4f46e5 55%, #06b6d4); -webkit-background-clip:text; background-clip:text; -webkit-text-fill-color:transparent}
    .lead{font-size: clamp(16px, 1.2vw, 18px); color:var(--muted); max-width:60ch}
    .cta{display:flex; gap:12px; flex-wrap:wrap; margin-top:24px}

    .hero-art{
      position:relative; isolation:isolate; aspect-ratio:1/1; border-radius:var(--radius-2xl);
      background: radial-gradient(120% 120% at 80% 20%, rgba(139,92,246,.18), transparent 60%), var(--panel);
      border:var(--border); box-shadow:var(--shadow-2);
      overflow:hidden;
    }
    .hero-swoosh{position:absolute; inset:10% 8% 8% 10%; background:url('https://images.unsplash.com/photo-1607644941052-d9f3bde2d9a9?q=80&w=1200&auto=format&fit=crop') center/cover no-repeat; filter:saturate(130%) hue-rotate(-10deg)}
    .hero-glow{position:absolute; inset:-20% -30% -30% -20%; background:radial-gradient(50% 50% at 60% 40%, rgba(139,92,246,.65), transparent 55%), radial-gradient(50% 50% at 40% 60%, rgba(6,182,212,.45), transparent 55%); filter: blur(60px); opacity:.55; z-index:-1}

    /* Logos */
    .logos{display:grid; grid-template-columns:repeat(6,1fr); gap:22px; opacity:.85}
    .logos div{height:40px; border-radius:12px; display:grid; place-items:center; background:rgba(255,255,255,.02); border:var(--border)}

    /* Section titles */
    .eyebrow{letter-spacing:.18em; text-transform:uppercase; font-weight:700; font-size:.85rem; color:#c4c9d7}
    .title{font-size: clamp(28px, 3.2vw, 42px); margin:10px 0 18px}
    .title .accent{color:var(--accent-2)}
    .subtitle{color:var(--muted); max-width:70ch}

    /* Feature steps */
    .steps{grid-template-columns: repeat(3, 1fr)}
    .card{background:linear-gradient(180deg, rgba(255,255,255,.04), rgba(255,255,255,.02)); border:var(--border); border-radius:var(--radius-xl); padding:24px; box-shadow:var(--shadow-1)}
    .icon{
      width:44px; height:44px; border-radius:12px; display:grid; place-items:center; background:radial-gradient(60% 60% at 30% 30%, #8b5cf6, #4f46e5); box-shadow: inset 0 0 0 1px rgba(255,255,255,.18), 0 10px 20px rgba(139,92,246,.35)
    }
    .card h3{margin:16px 0 8px}
    .card p{color:var(--muted)}

    /* Pricing */
    .pricing{grid-template-columns: repeat(3, 1fr)}
    .price-card{position:relative; padding:26px; border-radius:22px; background:linear-gradient(180deg, rgba(255,255,255,.04), rgba(255,255,255,.02)); border:var(--border); box-shadow:var(--shadow-2)}
    .price-card.highlight{background:linear-gradient(180deg, rgba(139,92,246,.18), rgba(255,255,255,.03)); outline: 1px solid rgba(139,92,246,.5)}
    .price{display:flex; align-items:flex-end; gap:10px; margin:10px 0}
    .price strong{font-size:38px}
    .billing{display:flex; align-items:center; gap:12px; margin:14px 0 26px}
    .switch{position:relative; width:56px; height:32px; background:rgba(255,255,255,.12); border-radius:999px; cursor:pointer}
    .switch::after{content:""; position:absolute; top:3px; left:3px; width:26px; height:26px; border-radius:50%; background:#fff; transition: transform .25s ease}
    .switch.active{background:linear-gradient(90deg, var(--accent), #4f46e5)}
    .switch.active::after{transform: translateX(24px)}
    .badge-save{font-size:.75rem; padding:6px 10px; border-radius:999px; background:rgba(16,185,129,.16); border:1px solid rgba(16,185,129,.35); color:#a7f3d0}
    .features{display:grid; gap:10px; margin:14px 0 20px; color:var(--muted)}
    .features li{display:flex; gap:10px}

    /* Blog */
    .blog{grid-template-columns: repeat(4, 1fr)}
    .post{overflow:hidden; border-radius:18px; background:var(--panel); border:var(--border)}
    .post .thumb{aspect-ratio: 16/10; background:#111; background-size:cover; background-position:center}
    .post .meta{padding:14px 16px}
    .post small{opacity:.75}

    /* CTA banner */
    .cta-banner{position:relative; overflow:hidden; border-radius:26px; border:var(--border); background:linear-gradient(180deg, rgba(255,255,255,.04), rgba(255,255,255,.02)); min-height:220px; display:grid; grid-template-columns: 1.1fr .9fr; align-items:center; box-shadow:var(--shadow-2)}
    .cta-banner .art{position:relative; height:100%;}
    .cta-banner .blob{position:absolute; inset:10% 8% 10% 10%; background:url('https://images.unsplash.com/photo-1614851099131-31bd732ff9b6?q=80&w=1200&auto=format&fit=crop') center/cover no-repeat; filter:saturate(140%)}

    /* Footer */
    footer{border-top:var(--border); padding:36px 0 60px; color:#c5cad6}
    .foot{display:grid; grid-template-columns: 1.1fr .9fr; gap:24px}
    .links{display:grid; grid-template-columns: repeat(3, 1fr); gap:16px}
    .links a{display:block; padding:6px 0; opacity:.85}
    .links a:hover{opacity:1}

    /* Responsive */
    @media (max-width: 1024px){
      .hero{grid-template-columns: 1fr; gap:28px}
      .cta-banner{grid-template-columns: 1fr}
      .foot{grid-template-columns: 1fr}
    }
    @media (max-width: 900px){
      .logos{grid-template-columns: repeat(3,1fr)}
      .steps{grid-template-columns: 1fr}
      .pricing{grid-template-columns: 1fr}
      .blog{grid-template-columns: 1fr 1fr}
    }
  </style>
</head>
<body>
  <header>
    <div class="container nav">
      <div class="brand">
        <div class="logo" aria-hidden="true"></div>
        <span>ArcCraft</span>
      </div>
      <nav aria-label="Primary">
        <a href="#features">Features</a>
        <a href="#pricing">Pricing</a>
        <a href="#insights">Insights</a>
      </nav>
      <div style="display:flex; gap:10px">
        <a href="#pricing" class="btn btn-primary">Get Started</a>
      </div>
    </div>
  </header>

  <main>
    <section class="container hero">
      <div>
        <h1>Your <span class="accent">AI‑Powered</span><br/> Design Assistant</h1>
        <p class="lead">Unlock your creative potential. Seamlessly generate, customize, and perfect your designs with cutting‑edge AI technology.</p>
        <div class="cta">
          <a class="btn btn-primary" href="#pricing">Get Started</a>
          <a class="btn btn-ghost" href="#insights">Learn More</a>
        </div>
      </div>

    </section>

    <!-- Logos -->
    <section class="container section" aria-label="Trusted by">
      <div class="logos">
        <div>Logoipsum</div>
        <div>Logoipsum</div>
        <div>Logoipsum</div>
        <div>Logoipsum</div>
        <div>Logoipsum</div>
        <div>Logoipsum</div>
      </div>
    </section>

    <!-- Features / Steps -->
    <section id="features" class="container section">
      <div>
        <div class="eyebrow">Workflow</div>
        <h2 class="title">Unleash Your <span class="accent">Creativity</span></h2>
        <p class="subtitle">Discover how our AI‑Powered Design Assistant transforms your ideas into stunning designs effortlessly. Follow these simple steps to turn your vision into reality.</p>
      </div>
      <div class="grid steps" style="margin-top:24px">
        <article class="card">
          <div class="icon" aria-hidden="true">
            <svg width="22" height="22" viewBox="0 0 24 24" fill="none" xmlns="http://www.w3.org/2000/svg">
              <path d="M4 7a3 3 0 0 1 3-3h10a3 3 0 0 1 3 3v10a3 3 0 0 1-3 3H7a3 3 0 0 1-3-3V7Z" stroke="white" opacity=".9" stroke-width="1.5"/>
              <path d="M8 15l3-3 3 3 3-4 2 3" stroke="white" stroke-width="1.5" stroke-linecap="round"/>
            </svg>
          </div>
          <h3>Upload Brief</h3>
          <p>Share your project details and let our AI grasp your vision.</p>
        </article>
        <article class="card">
          <div class="icon" aria-hidden="true">
            <svg width="22" height="22" viewBox="0 0 24 24" fill="none" xmlns="http://www.w3.org/2000/svg">
              <circle cx="12" cy="12" r="8" stroke="white" stroke-width="1.5"/>
              <path d="M9.5 9.5l5 5m0-5l-5 5" stroke="white" stroke-width="1.5" stroke-linecap="round"/>
            </svg>
          </div>
          <h3>Generate Designs</h3>
          <p>Watch as ArcCraft’s unique design ideas surface for you.</p>
        </article>
        <article class="card">
          <div class="icon" aria-hidden="true">
            <svg width="22" height="22" viewBox="0 0 24 24" fill="none" xmlns="http://www.w3.org/2000/svg">
              <path d="M7 17l10-10" stroke="white" stroke-width="1.5" stroke-linecap="round"/>
              <path d="M14 6l4 4" stroke="white" stroke-width="1.5" stroke-linecap="round"/>
              <rect x="3" y="15" width="6" height="6" rx="2" stroke="white" stroke-width="1.5"/>
            </svg>
          </div>
          <h3>Refine Creation</h3>
          <p>Perfect your chosen concept with easy‑to‑use AI tools.</p>
        </article>
      </div>
    </section>

    <!-- Pricing -->
    <section id="pricing" class="container section">
      <div style="display:flex; align-items:flex-end; justify-content:space-between; gap:18px; flex-wrap:wrap">
        <div>
          <div class="eyebrow">Plans</div>
          <h2 class="title">Affordable Plans for <span class="accent">Every Need</span></h2>
          <p class="subtitle">Choose the perfect plan for your design projects, from startups to enterprises. Designed for flexibility and value.</p>
        </div>
        <div class="billing" aria-label="Billing toggle">
          <span>Monthly</span>
          <div class="switch" id="billingSwitch" role="switch" aria-checked="false" tabindex="0"></div>
          <span>Yearly</span>
          <span class="badge-save" id="saveBadge">Save 20%</span>
        </div>
      </div>

      <div class="grid pricing" style="margin-top:18px">
        <!-- Free -->
        <article class="price-card">
          <h3>Free</h3>
          <div class="price"><strong id="p-free">$0</strong><span>/m</span></div>
          <ul class="features">
            <li>✔ Basic AI‑generated designs</li>
            <li>✔ Access to customization tools</li>
            <li>✔ Standard templates library</li>
            <li>✔ 5 projects per month</li>
          </ul>
          <a href="#" class="btn btn-ghost" style="width:100%">Get Started</a>
        </article>

        <!-- Basic -->
        <article class="price-card highlight">
          <div class="badge" style="position:absolute; top:18px; right:18px">Most Popular</div>
          <h3>Basic</h3>
          <div class="price"><strong id="p-basic">$14.99</strong><span>/m</span></div>
          <ul class="features">
            <li>✔ Advanced AI‑generated designs</li>
            <li>✔ Full access to customization tools</li>
            <li>✔ Premium templates library</li>
            <li>✔ Unlimited previews</li>
            <li>✔ Real‑time collaboration</li>
            <li>✔ Priority email support</li>
          </ul>
          <a href="#" class="btn btn-primary" style="width:100%">Get Started</a>
        </article>

        <!-- Pro -->
        <article class="price-card">
          <h3>Pro</h3>
          <div class="price"><strong id="p-pro">$29.99</strong><span>/m</span></div>
          <ul class="features">
            <li>✔ All features included in Basic</li>
            <li>✔ Dedicated account manager</li>
            <li>✔ Custom AI solutions and designs</li>
            <li>✔ Co‑branding and handoff</li>
            <li>✔ 24/7 priority support</li>
            <li>✔ Advanced analytics and reporting</li>
            <li>✔ Secure cloud storage</li>
          </ul>
          <a href="#" class="btn btn-ghost" style="width:100%">Get Started</a>
        </article>
      </div>
    </section>

    <!-- Insights / Blog -->
    <section id="insights" class="container section">
      <div>
        <div class="eyebrow">Resources</div>
        <h2 class="title">Stay Inspired with Our <span class="accent">Latest Insights</span></h2>
        <p class="subtitle">Dive into our blog for fresh trends, tips, and insights in the world of design and AI technology.</p>
      </div>

      <div class="grid blog" style="margin-top:24px">
        <article class="post">
          <div class="thumb" style="background-image:url('https://images.unsplash.com/photo-1517694712202-14dd9538aa97?q=80&w=1200&auto=format&fit=crop')"></div>
          <div class="meta">
            <small>Apr 8, 2022 • 6 min read</small>
            <h3 style="margin:8px 0 6px">Starting and Growing a Career in Web Design</h3>
          </div>
        </article>
        <article class="post">
          <div class="thumb" style="background-image:url('https://images.unsplash.com/photo-1551281044-8b29d77f6ca0?q=80&w=1200&auto=format&fit=crop')"></div>
          <div class="meta">
            <small>Mar 15, 2022 • 5 min read</small>
            <h3 style="margin:8px 0 6px">Create a Landing Page That Performs Great</h3>
          </div>
        </article>
        <article class="post">
          <div class="thumb" style="background-image:url('https://images.unsplash.com/photo-1547658719-da2b51169166?q=80&w=1200&auto=format&fit=crop')"></div>
          <div class="meta">
            <small>Feb 28, 2022 • 7 min read</small>
            <h3 style="margin:8px 0 6px">How Can Designers Prepare for the Future?</h3>
          </div>
        </article>
        <article class="post">
          <div class="thumb" style="background-image:url('https://images.unsplash.com/photo-1552084117-56a987666449?q=80&w=1200&auto=format&fit=crop')"></div>
          <div class="meta">
            <small>Jan 21, 2022 • 4 min read</small>
            <h3 style="margin:8px 0 6px">A Practical Guide to AI‑assisted Branding</h3>
          </div>
        </article>
      </div>

      <div style="display:flex; justify-content:center; margin-top:18px">
        <a class="btn btn-ghost" href="#">Read More</a>
      </div>
    </section>

    <!-- CTA Banner -->
    <section class="container section">
      <div class="cta-banner">
        <div style="padding:26px 26px 32px">
          <h2 class="title" style="margin-top:6px">Start Your Design <span class="accent">Journey</span> Today</h2>
          <p class="subtitle">Sign up now and experience the power of AI‑driven design without any commitment.</p>
          <div class="cta" style="margin-top:18px"><a class="btn btn-primary" href="#pricing">Get Started</a></div>
        </div>
        <div class="art">
          <div class="blob" role="img" aria-label="Purple 3D fluid art"></div>
        </div>
      </div>
    </section>
  </main>

  <!-- Footer -->
  <footer>
    <div class="container foot">
      <div>
        <div class="brand" style="margin-bottom:8px">
          <div class="logo" aria-hidden="true"></div>
          <strong>ArcCraft</strong>
        </div>
        <p style="color:var(--muted); max-width:50ch">Design faster with intelligent assistance. ArcCraft helps teams explore, iterate, and ship standout creative work.</p>
      </div>
      <div class="links">
        <div>
          <strong>Product</strong>
          <a href="#features">Features</a>
          <a href="#pricing">Pricing</a>
          <a href="#">Templates</a>
        </div>
        <div>
          <strong>Company</strong>
          <a href="#">About</a>
          <a href="#">Careers</a>
          <a href="#">Contact</a>
        </div>
        <div>
          <strong>Resources</strong>
          <a href="#insights">Blog</a>
          <a href="#">Docs</a>
          <a href="#">Community</a>
        </div>
      </div>
    </div>
  </footer>

  <script>
    // Smooth in‑page links
    document.querySelectorAll('a[href^="#"]').forEach(a=>{
      a.addEventListener('click', e=>{
        const id = a.getAttribute('href');
        if(id.length>1){
          const el = document.querySelector(id);
          if(el){ e.preventDefault(); el.scrollIntoView({behavior:'smooth'}); }
        }
      });
    });

    // Pricing toggle (Monthly / Yearly with 20% off applied to yearly)
    const switchEl = document.getElementById('billingSwitch');
    const prices = {
      monthly: { basic: 14.99, pro: 29.99 },
      yearly:  { basic: 14.99*12*0.8, pro: 29.99*12*0.8 } // 20% savings
    };
    const fmt = v => '$' + v.toFixed(2).replace(/\.00$/,'');
    const updatePrices = yearly => {
      const tier = yearly ? 'yearly' : 'monthly';
      document.getElementById('p-basic').textContent = fmt(prices[tier].basic) + (yearly ? '' : '');
      document.getElementById('p-pro').textContent   = fmt(prices[tier].pro) + (yearly ? '' : '');
      document.getElementById('saveBadge').style.opacity = yearly ? 1 : .6;
    };
    const toggle = () => {
      switchEl.classList.toggle('active');
      const yearly = switchEl.classList.contains('active');
      switchEl.setAttribute('aria-checked', yearly ? 'true' : 'false');
      updatePrices(yearly);
    };
    switchEl.addEventListener('click', toggle);
    switchEl.addEventListener('keydown', e=>{ if(e.key==='Enter' || e.key===' ') { e.preventDefault(); toggle(); }});
    updatePrices(false);
  </script>
</body>
</html>

