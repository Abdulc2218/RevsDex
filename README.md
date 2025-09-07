<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8" />
  <meta name="viewport" content="width=device-width, initial-scale=1.0"/>
  <title>Revs Dex – Discord Bot</title>
  <meta name="description" content="Revs Dex – The ultimate Discord car collection bot. Catch, trade, and complete your Dex with friends!"/>
  <link rel="preconnect" href="https://fonts.googleapis.com">
  <link rel="preconnect" href="https://fonts.gstatic.com" crossorigin>
  <link href="https://fonts.googleapis.com/css2?family=Inter:wght@300;400;500;600;700;800;900&display=swap" rel="stylesheet">

  <style>
    :root {
      --bg: #0b0f19;
      --fg: #ffffff;
      --muted: #a0a4ad;
      --accent: #34ebb1;
      --accent-dark: #34dbeb;
      --card: #161b29;
      --border: #1f2433;
      --radius: 12px;
      --transition: 0.2s ease;
    }
    * { box-sizing: border-box; margin:0; padding:0; }
    body {
      font-family: 'Inter', sans-serif;
      background: var(--bg);
      color: var(--fg);
      line-height: 1.6;
    }
    a { text-decoration:none; color:inherit; transition:color var(--transition); }
    a:hover { color: var(--accent); }
    header {
      background: linear-gradient(to bottom, #34ebb1, #34dbeb);
      border-bottom: 1px solid var(--border);
      padding: 16px 0;
      position: sticky;
      top: 0;
      z-index: 50;
    }
    .container {
      width: min(1100px, 90%);
      margin: 0 auto;
    }
    .nav {
      display:flex;
      align-items:center;
      justify-content:space-between;
    }
    .brand { display:flex; align-items:center; gap:8px; font-weight:700; font-size:1.2rem; }
    .logo {
      width:28px; height:28px; background:var(--fg); border-radius:50%;
    }
    nav { display:flex; gap:18px; font-size:0.95rem; }
    .btn {
      display:inline-block; padding:10px 18px; border-radius:var(--radius);
      font-weight:600; transition:background var(--transition);
    }
    .btn-primary {
      background:var(--accent); color:var(--bg);
    }
    .btn-primary:hover { background:var(--accent-dark); }
    .btn-ghost {
      background:transparent; border:1px solid var(--border); color:var(--fg);
    }
    .btn-ghost:hover { background:var(--card); }
    main { padding-top:40px; }
    .hero {
      display:grid; grid-template-columns:1fr; text-align:center; gap:18px;
      padding:60px 0;
    }
    .hero h1 { font-size:2.5rem; line-height:1.2; }
    .accent { color: var(--accent); }
    .lead { color: var(--muted); font-size:1.2rem; margin-top:12px; }
    .cta { display:flex; justify-content:center; gap:16px; margin-top:22px; }
    .section { padding:60px 0; }
    .eyebrow { text-transform:uppercase; color:var(--accent); font-weight:600; font-size:0.9rem; }
    .title { font-size:2rem; margin-top:6px; }
    .subtitle { color: var(--muted); margin-top:6px; font-size:1.05rem; max-width:60ch; }
    .grid {
      display:grid; gap:22px;
    }
    .steps { grid-template-columns:repeat(auto-fit,minmax(260px,1fr)); margin-top:24px; }
    .card {
      background:var(--card); padding:22px; border-radius:var(--radius);
      border:1px solid var(--border); transition:transform var(--transition);
    }
    .card:hover { transform:translateY(-4px); }
    .icon { font-size:1.8rem; margin-bottom:8px; }
    .logos {
      display:grid; grid-template-columns:repeat(auto-fit,minmax(120px,1fr));
      text-align:center; gap:12px; color:var(--muted);
    }
    .pricing { grid-template-columns:repeat(auto-fit,minmax(280px,1fr)); }
    .price-card {
      position:relative; background:var(--card); border:1px solid var(--border);
      border-radius:var(--radius); padding:26px; display:flex; flex-direction:column; gap:14px;
    }
    .price { font-size:1.8rem; }
    .features { list-style:none; color:var(--muted); font-size:0.95rem; display:grid; gap:6px; }
    .highlight { border:2px solid var(--accent); }
    .badge {
      background:var(--accent); color:var(--bg); font-size:0.8rem; padding:2px 8px;
      border-radius:6px; font-weight:600;
    }
    .blog { grid-template-columns:repeat(auto-fit,minmax(300px,1fr)); }
    .post {
      background:var(--card); border-radius:var(--radius); overflow:hidden;
      border:1px solid var(--border); transition:transform var(--transition);
    }
    .post:hover { transform:translateY(-4px); }
    .thumb { height:160px; background-size:cover; background-position:center; }
    .meta { padding:14px; }
    .cta-banner {
      display:grid; grid-template-columns:1fr 1fr; align-items:center;
      background:var(--card); border-radius:var(--radius); border:1px solid var(--border);
      overflow:hidden;
    }
    .blob {
      background: radial-gradient(circle at 30% 30%, var(--accent), var(--accent-dark));
      width:100%; height:100%; min-height:200px;
    }
    footer {
      background:#0a0e15; border-top:1px solid var(--border); padding:40px 0; margin-top:60px;
    }
    .foot { display:flex; justify-content:space-between; flex-wrap:wrap; gap:28px; }
    .links { display:flex; gap:40px; }
    .links div { display:flex; flex-direction:column; gap:6px; font-size:0.95rem; }
    .links strong { margin-bottom:6px; }
    @media(max-width:768px) {
      .cta-banner { grid-template-columns:1fr; }
      .hero h1 { font-size:2rem; }
    }
  </style>
</head>
<body>
  <header>
    <div class="container nav">
      <div class="brand">
        <div class="logo" aria-hidden="true"></div>
        <span>Revs Dex</span>
      </div>
      <nav>
        <a href="#features">Features</a>
        <a href="#pricing">Premium</a>
        <a href="#insights">Updates</a>
      </nav>
      <div style="display:flex; gap:10px">
        <a href="#pricing" class="btn btn-primary">Invite Bot</a>
      </div>
    </div>
  </header>

  <main>
    <!-- Hero -->
    <section class="container hero">
      <div>
        <h1>The Ultimate <span class="accent">Car Dex</span><br/> Discord Bot</h1>
        <p class="lead">Catch cars, build collections, trade with friends, and climb the leaderboard. Revs Dex brings the thrill of collecting straight into your Discord server.</p>
        <div class="cta">
          <a class="btn btn-primary" href="#pricing">Invite Now</a>
          <a class="btn btn-ghost" href="#insights">Learn More</a>
        </div>
      </div>
    </section>

    <!-- Logos -->
    <section class="container section">
      <div class="logos">
        <div>Discord</div>
        <div>Gaming</div>
        <div>Community</div>
        <div>Collectors</div>
        <div>Servers</div>
        <div>Friends</div>
      </div>
    </section>

    <!-- Features -->
    <section id="features" class="container section">
      <div>
        <div class="eyebrow">How it Works</div>
        <h2 class="title">Collect, Trade & <span class="accent">Show Off</span></h2>
        <p class="subtitle">Revs Dex makes your Discord server more fun. Collect rare cars, complete your Dex, and trade with others to become the ultimate car collector.</p>
      </div>
      <div class="grid steps">
        <article class="card">
          <div class="icon">🚗</div>
          <h3>Catch Cars</h3>
          <p>Cars randomly spawn in chat. Be fast and claim them before others!</p>
        </article>
        <article class="card">
          <div class="icon">📦</div>
          <h3>Build Your Dex</h3>
          <p>Fill up your collection with common, rare, and even hyper-rare cars.</p>
        </article>
        <article class="card">
          <div class="icon">🤝</div>
          <h3>Trade with Friends</h3>
          <p>Missing a car? Trade with other collectors and complete your Dex.</p>
        </article>
      </div>
    </section>

    <!-- Pricing -->
    <section id="pricing" class="container section">
      <div style="display:flex; align-items:flex-end; justify-content:space-between; gap:18px; flex-wrap:wrap">
        <div>
          <div class="eyebrow">Premium</div>
          <h2 class="title">Upgrade Your <span class="accent">Experience</span></h2>
          <p class="subtitle">Revs Dex is free to play, but premium unlocks powerful features and exclusive rewards.</p>
        </div>
      </div>
      <div class="grid pricing">
        <article class="price-card">
          <h3>Free</h3>
          <div class="price"><strong>$0</strong><span>/m</span></div>
          <ul class="features">
            <li>✔ Catch and collect cars</li>
            <li>✔ Trade with friends</li>
            <li>✔ Basic Dex features</li>
            <li>✔ Join leaderboards</li>
          </ul>
          <a href="#" class="btn btn-ghost" style="width:100%">Invite Free</a>
        </article>

        <article class="price-card highlight">
          <div class="badge">Most Popular</div>
          <h3>Premium</h3>
          <div class="price"><strong>$4.99</strong><span>/m</span></div>
          <ul class="features">
            <li>✔ Access to rare & hypercar spawns</li>
            <li>✔ Special premium-only events</li>
            <li>✔ Extra trading slots</li>
            <li>✔ Priority support</li>
          </ul>
          <a href="#" class="btn btn-primary" style="width:100%">Upgrade</a>
        </article>

        <article class="price-card">
          <h3>Pro Guild</h3>
          <div class="price"><strong>$9.99</strong><span>/m</span></div>
          <ul class="features">
            <li>✔ Everything in Premium</li>
            <li>✔ Server-wide bonuses</li>
            <li>✔ Increased spawn rates</li>
            <li>✔ Custom events & giveaways</li>
          </ul>
          <a href="#" class="btn btn-ghost" style="width:100%">Upgrade</a>
        </article>
      </div>
    </section>

    <!-- Updates -->
    <section id="insights" class="container section">
      <div>
        <div class="eyebrow">Updates</div>
        <h2 class="title">Stay Updated with <span class="accent">Revs Dex</span></h2>
        <p class="subtitle">Get the latest news, features, and updates about your favorite car collecting Discord bot.</p>
      </div>
      <div class="grid blog">
        <article class="post">
          <div class="thumb" style="background-image:url('https://images.unsplash.com/photo-1502877338535-766e1452684a?q=80&w=1200&auto=format&fit=crop')"></div>
          <div class="meta">
            <small>Aug 2025 • Update</small>
            <h3>Hypercar Event Released!</h3>
          </div>
        </article>
        <article class="post">
          <div class="thumb" style="background-image:url('https://images.unsplash.com/photo-1525609004556-c46c7d6cf023?q=80&w=1200&auto=format&fit=crop')"></div>
          <div class="meta">
            <small>Jul 2025 • Blog</small>
            <h3>Tips to Complete Your Dex Faster</h3>
          </div>
        </article>
      </div>
    </section>

    <!-- CTA -->
    <section class="container section">
      <div class="cta-banner">
        <div style="padding:26px">
          <h2 class="title">Start Collecting <span class="accent">Today</span></h2>
          <p class="subtitle">Invite Revs Dex to your Discord server and begin your car collection journey!</p>
          <div class="cta" style="margin-top:18px">
            <a class="btn btn-primary" href="#pricing">Invite Now</a>
          </div>
        </div>
        <div class="art"><div class="blob"></div></div>
      </div>
    </section>
  </main>

  <footer>
    <div class="container foot">
      <div>
        <div class="brand"><div class="logo"></div><strong>Revs Dex</strong></div>
        <p style="color:var(--muted); max-width:50ch">Catch, collect, and trade cars on Discord. Revs Dex brings the fun of collecting right into your server.</p>
      </div>
      <div class="links">
        <div>
          <strong>Bot</strong>
          <a href="#features">Features</a>
          <a href="#pricing">Premium</a>
          <a href="#">Commands</a>
        </div>
        <div>
          <strong>Community</strong>
          <a href="#">Support</a>
          <a href="#">Leaderboard</a>
          <a href="#">Invite</a>
        </div>
        <div>
          <strong>Resources</strong>
          <a href="#insights">Updates</a>
          <a href="#">Docs</a>
          <a href="#">Discord</a>
        </div>
      </div>
    </div>
  </footer>
</body>
</html>
