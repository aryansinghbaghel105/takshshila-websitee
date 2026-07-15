# takshshila-websitee
<!DOCTYPE html>
<html lang="en">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>Takshshila Institute of Engineering & Technology</title>
<link rel="preconnect" href="https://fonts.googleapis.com">
<link href="https://fonts.googleapis.com/css2?family=Sora:wght@400;500;600;700;800&family=Inter:wght@400;500;600&family=JetBrains+Mono:wght@400;500&display=swap" rel="stylesheet">
<style>
  :root{
    --ink:#000000;
    --panel:#0A0A0A;
    --panel-2:#151515;
    --line:rgba(255,255,255,0.16);
    --line-bright:rgba(255,255,255,0.34);
    --cyan:#FFFFFF;
    --cyan-dim:rgba(255,255,255,0.12);
    --gold:#D9D9D9;
    --gold-dim:rgba(255,255,255,0.08);
    --text:#F5F5F5;
    --sub:#A8A8A8;
    --sub-dim:#6B6B6B;
  }
  *{margin:0;padding:0;box-sizing:border-box;}
  html{scroll-behavior:smooth;}
  body{
    background:var(--ink);
    color:var(--text);
    font-family:'Inter',sans-serif;
    font-style:italic;
    line-height:1.6;
    overflow-x:hidden;
  }
  @media (prefers-reduced-motion: reduce){
    *{animation-duration:0.01ms !important; animation-iteration-count:1 !important; transition-duration:0.01ms !important; scroll-behavior:auto !important;}
  }
  h1,h2,h3,h4{font-family:'Sora',sans-serif; letter-spacing:-0.01em;}
  .mono{font-family:'JetBrains Mono',monospace;}
  a{color:inherit; text-decoration:none;}
  img{max-width:100%; display:block;}
  ::selection{background:var(--cyan); color:var(--ink);}

  .wrap{max-width:1180px; margin:0 auto; padding:0 32px;}

  /* Blueprint grid background */
  .blueprint{
    position:absolute; inset:0;
    background-image:
      linear-gradient(var(--line) 1px, transparent 1px),
      linear-gradient(90deg, var(--line) 1px, transparent 1px);
    background-size:56px 56px;
    -webkit-mask-image:radial-gradient(ellipse 80% 60% at 50% 30%, black 40%, transparent 85%);
    mask-image:radial-gradient(ellipse 80% 60% at 50% 30%, black 40%, transparent 85%);
    pointer-events:none;
  }

  /* NAV */
  header{
    position:sticky; top:0; z-index:100;
    background:rgba(8,11,18,0.82);
    backdrop-filter:blur(14px);
    border-bottom:1px solid var(--line);
  }
  nav{
    display:flex; align-items:center; justify-content:space-between;
    height:76px;
  }
  .brand{display:flex; align-items:center; gap:12px;}
  .brand-mark{
    width:38px; height:38px; border:1px solid var(--cyan);
    display:flex; align-items:center; justify-content:center;
    position:relative; flex-shrink:0;
  }
  .brand-mark::before, .brand-mark::after{
    content:''; position:absolute; width:6px; height:6px; background:var(--cyan);
  }
  .brand-mark::before{top:-1px; left:-1px;}
  .brand-mark::after{bottom:-1px; right:-1px;}
  .brand-mark span{font-family:'Sora'; font-weight:800; color:var(--cyan); font-size:15px;}
  .brand-text .name{font-family:'Sora'; font-weight:700; font-size:15.5px; letter-spacing:0.02em; line-height:1.15;}
  .brand-text .tag{font-family:'JetBrains Mono'; font-size:10px; color:var(--sub-dim); letter-spacing:0.08em; text-transform:uppercase;}
  .nav-links{display:flex; gap:34px; font-size:14px; color:var(--sub);}
  .nav-links a{transition:color .2s;}
  .nav-links a:hover{color:var(--cyan);}
  .nav-cta{
    font-family:'JetBrains Mono'; font-size:12.5px; padding:10px 20px;
    border:1px solid var(--cyan); color:var(--cyan);
    transition:all .2s;
  }
  .nav-cta:hover{background:var(--cyan); color:var(--ink);}
  .nav-toggle{display:none;}

  /* HERO */
  .hero{position:relative; padding:120px 0 90px; overflow:hidden;}
  .hero-inner{position:relative; z-index:2;}
  .eyebrow{
    font-family:'JetBrains Mono'; font-size:12px; color:var(--cyan);
    letter-spacing:0.14em; text-transform:uppercase; display:flex; align-items:center; gap:10px; margin-bottom:26px;
  }
  .eyebrow::before{content:''; width:26px; height:1px; background:var(--cyan);}
  .hero h1{
    font-size:clamp(38px, 5.6vw, 68px); font-weight:700; line-height:1.05; max-width:900px;
  }
  .hero h1 em{
    font-style:normal; color:var(--cyan);
    background:linear-gradient(180deg, transparent 62%, var(--cyan-dim) 62%);
  }
  .hero p.lede{
    max-width:560px; margin-top:26px; color:var(--sub); font-size:17px;
  }
  .hero-ctas{display:flex; gap:16px; margin-top:40px; flex-wrap:wrap;}
  .btn-primary{
    background:var(--cyan); color:var(--ink); font-weight:600; font-size:14.5px;
    padding:15px 28px; display:inline-flex; align-items:center; gap:10px;
    transition:transform .2s, box-shadow .2s;
  }
  .btn-primary:hover{transform:translateY(-2px); box-shadow:0 8px 24px rgba(63,232,208,0.25);}
  .btn-ghost{
    border:1px solid var(--line-bright); color:var(--text); font-weight:500; font-size:14.5px;
    padding:15px 28px; display:inline-flex; align-items:center; gap:10px; transition:border-color .2s, background .2s;
  }
  .btn-ghost:hover{border-color:var(--cyan); background:rgba(63,232,208,0.05);}

  .readout{
    margin-top:76px; display:grid; grid-template-columns:repeat(4,1fr);
    border-top:1px solid var(--line); border-left:1px solid var(--line);
  }
  .readout div{
    border-right:1px solid var(--line); border-bottom:1px solid var(--line);
    padding:22px 24px;
  }
  .readout .num{font-family:'JetBrains Mono'; font-size:30px; color:var(--cyan); font-weight:500;}
  .readout .lbl{font-size:12.5px; color:var(--sub); margin-top:6px; letter-spacing:0.02em;}

  /* SECTION shared */
  section{padding:100px 0; position:relative; border-bottom:1px solid var(--line);}
  .section-head{max-width:640px; margin-bottom:56px;}
  .section-head .eyebrow{margin-bottom:16px;}
  .section-head h2{font-size:clamp(28px,3.4vw,40px); font-weight:700;}
  .section-head p{color:var(--sub); margin-top:16px; font-size:16px;}

  /* ABOUT */
  .about-grid{display:grid; grid-template-columns:1fr 1fr; gap:64px; align-items:start;}
  .about-grid p{color:var(--sub); font-size:15.5px; margin-bottom:18px;}
  .about-grid .lead-line{color:var(--text); font-size:19px; font-weight:500; margin-bottom:22px; line-height:1.5;}
  .about-panel{
    background:var(--panel); border:1px solid var(--line); padding:34px;
  }
  .about-panel .row{display:flex; justify-content:space-between; padding:16px 0; border-bottom:1px solid var(--line); font-size:14px;}
  .about-panel .row:last-child{border-bottom:none;}
  .about-panel .row .k{color:var(--sub-dim); font-family:'JetBrains Mono'; font-size:12px; text-transform:uppercase; letter-spacing:0.05em;}
  .about-panel .row .v{color:var(--text); font-weight:500; text-align:right;}

  /* PROGRAMMES */
  .prog-grid{display:grid; grid-template-columns:repeat(4,1fr); gap:1px; background:var(--line); border:1px solid var(--line);}
  .prog-card{background:var(--panel); padding:32px 26px; transition:background .25s;}
  .prog-card:hover{background:var(--panel-2);}
  .prog-card .idx{font-family:'JetBrains Mono'; color:var(--gold); font-size:12px; letter-spacing:0.08em;}
  .prog-card h3{font-size:19px; margin:14px 0 12px;}
  .prog-card ul{list-style:none; font-size:13.5px; color:var(--sub);}
  .prog-card ul li{padding:5px 0; border-top:1px dashed var(--line);}
  .prog-card ul li:first-child{border-top:none;}

  /* DEPARTMENTS */
  .dept-grid{display:grid; grid-template-columns:repeat(3,1fr); gap:22px;}
  .dept-card{
    border:1px solid var(--line); padding:30px 26px; position:relative; overflow:hidden;
    transition:border-color .25s, transform .25s;
  }
  .dept-card:hover{border-color:var(--cyan); transform:translateY(-4px);}
  .dept-card .icon{width:40px; height:40px; margin-bottom:20px; color:var(--cyan);}
  .dept-card h3{font-size:17px; margin-bottom:10px;}
  .dept-card p{color:var(--sub); font-size:13.5px;}
  .dept-card a.more{display:inline-block; margin-top:16px; font-family:'JetBrains Mono'; font-size:11.5px; color:var(--cyan); letter-spacing:0.04em;}

  /* WHY / FEATURES */
  .feat-grid{display:grid; grid-template-columns:repeat(3,1fr); gap:1px; background:var(--line); border:1px solid var(--line);}
  .feat-card{background:var(--ink); padding:36px 30px;}
  .feat-card .num{font-family:'JetBrains Mono'; color:var(--sub-dim); font-size:13px;}
  .feat-card h3{font-size:19px; margin:16px 0 10px;}
  .feat-card p{color:var(--sub); font-size:14px;}

  /* CHAIRMAN */
  .chairman{display:grid; grid-template-columns:0.9fr 1.4fr; gap:60px; align-items:center;}
  .chairman-img{
    border:1px solid var(--line); aspect-ratio:4/4.6; overflow:hidden; background:var(--panel);
  }
  .chairman-img img{width:100%; height:100%; object-fit:cover;}
  blockquote{
    font-family:'Sora'; font-size:clamp(19px,2.1vw,25px); font-weight:500; line-height:1.55; color:var(--text);
    position:relative; padding-left:28px; border-left:2px solid var(--cyan);
  }
  .chairman-name{margin-top:26px; font-family:'JetBrains Mono'; font-size:13px; color:var(--gold);}
  .chairman-name span{display:block; color:var(--sub-dim); margin-top:4px; font-size:12px;}

  /* PLACEMENTS */
  .place-grid{display:grid; grid-template-columns:1fr 1fr; gap:60px; align-items:center;}
  .place-stats{display:grid; grid-template-columns:1fr 1fr; gap:1px; background:var(--line); border:1px solid var(--line); margin-top:30px;}
  .place-stats div{background:var(--panel); padding:24px;}
  .place-stats .num{font-family:'JetBrains Mono'; font-size:26px; color:var(--gold);}
  .place-stats .lbl{font-size:12px; color:var(--sub); margin-top:4px;}
  .recruiters{
    display:flex; flex-wrap:wrap; gap:12px; margin-top:32px;
  }
  .recruiters span{
    font-family:'JetBrains Mono'; font-size:12px; color:var(--sub); border:1px solid var(--line);
    padding:8px 14px;
  }

  /* TESTIMONIALS */
  .test-grid{display:grid; grid-template-columns:repeat(3,1fr); gap:24px;}
  .test-card{border:1px solid var(--line); padding:28px; background:var(--panel);}
  .test-card p{font-size:14.5px; color:var(--sub); margin-bottom:22px;}
  .test-card .who{display:flex; align-items:center; gap:12px;}
  .test-card .avatar{
    width:38px; height:38px; border:1px solid var(--cyan); display:flex; align-items:center; justify-content:center;
    font-family:'JetBrains Mono'; color:var(--cyan); font-size:13px;
  }
  .test-card .who .n{font-size:13.5px; font-weight:600; color:var(--text);}
  .test-card .who .r{font-size:11.5px; color:var(--sub-dim);}

  /* CTA BAND */
  .cta-band{
    padding:90px 0; text-align:center; position:relative; border-bottom:1px solid var(--line);
  }
  .cta-band h2{font-size:clamp(28px,4vw,44px); max-width:700px; margin:0 auto 28px;}
  .cta-row{display:flex; gap:16px; justify-content:center; flex-wrap:wrap;}

  /* FOOTER */
  footer{padding:70px 0 30px;}
  .foot-grid{display:grid; grid-template-columns:1.6fr 1fr 1fr 1.2fr; gap:40px; padding-bottom:50px; border-bottom:1px solid var(--line);}
  .foot-grid h4{font-size:13px; color:var(--sub-dim); font-family:'JetBrains Mono'; letter-spacing:0.06em; text-transform:uppercase; margin-bottom:18px;}
  .foot-grid ul{list-style:none;}
  .foot-grid ul li{margin-bottom:11px; font-size:14px; color:var(--sub);}
  .foot-grid ul li a:hover{color:var(--cyan);}
  .foot-about p{color:var(--sub); font-size:14px; max-width:340px; margin-top:14px;}
  .foot-bottom{
    display:flex; justify-content:space-between; align-items:center; padding-top:26px;
    font-size:12.5px; color:var(--sub-dim); flex-wrap:wrap; gap:12px;
  }

  /* Reveal on scroll */
  .reveal{opacity:0; transform:translateY(18px); transition:opacity .6s ease, transform .6s ease;}
  .reveal.in{opacity:1; transform:translateY(0);}

  @media(max-width:900px){
    .nav-links{display:none;}
    .about-grid, .chairman, .place-grid{grid-template-columns:1fr; gap:36px;}
    .prog-grid{grid-template-columns:repeat(2,1fr);}
    .dept-grid{grid-template-columns:repeat(2,1fr);}
    .feat-grid{grid-template-columns:1fr;}
    .readout{grid-template-columns:repeat(2,1fr);}
    .test-grid{grid-template-columns:1fr;}
    .foot-grid{grid-template-columns:1fr 1fr;}
  }
  @media(max-width:560px){
    .prog-grid, .dept-grid{grid-template-columns:1fr;}
    .readout{grid-template-columns:1fr 1fr;}
    .foot-grid{grid-template-columns:1fr;}
    .wrap{padding:0 20px;}
  }
</style>
</head>
<body>

<header>
  <div class="wrap">
    <nav>
      <a href="#" class="brand">
        <div class="brand-mark"><span>T</span></div>
        <div class="brand-text">
          <div class="name">TAKSHSHILA</div>
          <div class="tag">Institute of Engg &amp; Technology</div>
        </div>
      </a>
      <div class="nav-links">
        <a href="#about">About</a>
        <a href="#programmes">Programmes</a>
        <a href="#departments">Departments</a>
        <a href="#placements">Placements</a>
        <a href="#contact">Contact</a>
      </div>
      <a href="#contact" class="nav-cta">ADMISSION_ENQUIRY &gt;</a>
    </nav>
  </div>
</header>

<section class="hero">
  <div class="blueprint"></div>
  <div class="wrap hero-inner">
    <div class="eyebrow">AICTE Approved &middot; Est. 2004 &middot; Jabalpur, M.P.</div>
    <h1>Engineering minds built for <em>precision</em> and scale.</h1>
    <p class="lede">A self-financing institute affiliated to RGPV Bhopal &amp; RDVV Jabalpur, run by RNK Educational Society — training engineers, managers and technologists across six disciplines.</p>
    <div class="hero-ctas">
      <a href="#programmes" class="btn-primary">Explore Programmes →</a>
      <a href="#contact" class="btn-ghost">Admission Enquiry</a>
    </div>

    <div class="readout reveal">
      <div><div class="num">21+</div><div class="lbl">Years of History</div></div>
      <div><div class="num">30,000+</div><div class="lbl">Students Trained</div></div>
      <div><div class="num">85%</div><div class="lbl">Placement Rate</div></div>
      <div><div class="num">30+</div><div class="lbl">Programmes Offered</div></div>
    </div>
  </div>
</section>

<section id="about">
  <div class="wrap about-grid">
    <div class="reveal">
      <div class="eyebrow">About the institute</div>
      <p class="lead-line">"Fostering innovation, skill development and academic excellence with modern infrastructure, expert faculty and industry-focused education for future engineers."</p>
      <p>Takshshila Institute of Engineering &amp; Technology is a self-financing institution approved by AICTE, New Delhi, affiliated to Rajiv Gandhi Proudyogiki Vishwavidhyalaya, Bhopal, and R.D.V.V., Jabalpur. Established in 2004, the institute is managed by the RNK Educational Society.</p>
      <p>Known for a state-of-the-art campus and a strategic teaching-learning process, the institute pairs advanced facilities with industry-oriented training to shape well-rounded, career-ready professionals.</p>
    </div>
    <div class="about-panel reveal">
      <div class="row"><div class="k">Founded</div><div class="v">2004</div></div>
      <div class="row"><div class="k">Managed by</div><div class="v">RNK Educational Society</div></div>
      <div class="row"><div class="k">Approval</div><div class="v">AICTE, New Delhi</div></div>
      <div class="row"><div class="k">Affiliation</div><div class="v">RGPV Bhopal &amp; RDVV Jabalpur</div></div>
      <div class="row"><div class="k">Degrees</div><div class="v">B.Tech · M.Tech · MBA · Diploma</div></div>
      <div class="row"><div class="k">Campus</div><div class="v">Sharda Mandir Road, Jabalpur</div></div>
    </div>
  </div>
</section>

<section id="programmes">
  <div class="wrap">
    <div class="section-head reveal">
      <div class="eyebrow">Programmes at a glance</div>
      <h2>Four degrees, one direction — forward.</h2>
      <p>From diploma to postgraduate, every track is built around the same industry-facing curriculum.</p>
    </div>
    <div class="prog-grid reveal">
      <div class="prog-card">
        <div class="idx">01 / B.TECH</div>
        <h3>Bachelor of Technology</h3>
        <ul>
          <li>Computer Science &amp; Engg — 120</li>
          <li>Mechanical Engineering — 90</li>
          <li>Civil Engineering — 60</li>
          <li>Electronics &amp; Comm. — 60</li>
          <li>Electrical &amp; Electronics — 60</li>
          <li>CSE (AI &amp; ML)</li>
        </ul>
      </div>
      <div class="prog-card">
        <div class="idx">02 / M.TECH</div>
        <h3>Master of Technology</h3>
        <ul>
          <li>Computer Science &amp; Engg — 24</li>
          <li>Digital Communication — 24</li>
          <li>Structural Engineering</li>
          <li>Energy Technology — 18</li>
          <li>Industrial Engg &amp; Mgmt — 18</li>
        </ul>
      </div>
      <div class="prog-card">
        <div class="idx">03 / MBA</div>
        <h3>Business Administration</h3>
        <ul>
          <li>Finance — 120 seats total</li>
          <li>Marketing</li>
          <li>Human Resource Management</li>
          <li>Information Technology</li>
          <li>Operations Management</li>
        </ul>
      </div>
      <div class="prog-card">
        <div class="idx">04 / POLY</div>
        <h3>Polytechnic Diploma</h3>
        <ul>
          <li>Computer Science &amp; Engg — 60</li>
          <li>Civil Engineering — 60</li>
          <li>Mechanical Engineering — 120</li>
          <li>Electrical &amp; Electronics</li>
        </ul>
      </div>
    </div>
  </div>
</section>

<section id="departments">
  <div class="wrap">
    <div class="section-head reveal">
      <div class="eyebrow">Departments</div>
      <h2>Shaping future engineers, discipline by discipline.</h2>
    </div>
    <div class="dept-grid reveal">
      <div class="dept-card">
        <svg class="icon" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="1.4"><path d="M3 21h18M5 21V9l7-5 7 5v12M9 21v-6h6v6"/></svg>
        <h3>Civil Engineering</h3>
        <p>Designing, constructing and maintaining infrastructure — buildings, roads, bridges and water systems for sustainable development.</p>
      </div>
      <div class="dept-card">
        <svg class="icon" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="1.4"><rect x="4" y="4" width="16" height="16" rx="1"/><path d="M9 9h6v6H9z"/><path d="M4 9H2M4 15H2M22 9h-2M22 15h-2M9 4V2M15 4V2M9 22v-2M15 22v-2"/></svg>
        <h3>Computer Science</h3>
        <p>Developing innovative software, algorithms and systems that solve complex problems and drive global technological advancement.</p>
      </div>
      <div class="dept-card">
        <svg class="icon" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="1.4"><circle cx="12" cy="12" r="3"/><path d="M12 2v4M12 18v4M4.9 4.9l2.8 2.8M16.3 16.3l2.8 2.8M2 12h4M18 12h4M4.9 19.1l2.8-2.8M16.3 7.7l2.8-2.8"/></svg>
        <h3>Electronics &amp; Comm.</h3>
        <p>Building electronic systems, communication networks and embedded technologies for global connectivity.</p>
      </div>
      <div class="dept-card">
        <svg class="icon" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="1.4"><path d="M13 2 3 14h7l-1 8 10-12h-7l1-8z"/></svg>
        <h3>Electrical &amp; Electronics</h3>
        <p>Advanced electrical systems, power distribution, automation and cutting-edge electronic technologies.</p>
      </div>
      <div class="dept-card">
        <svg class="icon" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="1.4"><circle cx="12" cy="12" r="3"/><path d="M19.4 15a1.65 1.65 0 0 0 .33 1.82l.06.06a2 2 0 1 1-2.83 2.83l-.06-.06a1.65 1.65 0 0 0-1.82-.33 1.65 1.65 0 0 0-1 1.51V21a2 2 0 1 1-4 0v-.09A1.65 1.65 0 0 0 9 19.4a1.65 1.65 0 0 0-1.82.33l-.06.06a2 2 0 1 1-2.83-2.83l.06-.06A1.65 1.65 0 0 0 4.68 15a1.65 1.65 0 0 0-1.51-1H3a2 2 0 1 1 0-4h.09A1.65 1.65 0 0 0 4.6 9a1.65 1.65 0 0 0-.33-1.82l-.06-.06a2 2 0 1 1 2.83-2.83l.06.06A1.65 1.65 0 0 0 9 4.68 1.65 1.65 0 0 0 10 3.17V3a2 2 0 1 1 4 0v.09A1.65 1.65 0 0 0 15 4.6a1.65 1.65 0 0 0 1.82-.33l.06-.06a2 2 0 1 1 2.83 2.83l-.06.06A1.65 1.65 0 0 0 19.4 9a1.65 1.65 0 0 0 1.51 1H21a2 2 0 1 1 0 4h-.09a1.65 1.65 0 0 0-1.51 1z"/></svg>
        <h3>Mechanical Engineering</h3>
        <p>Designing, analysing and manufacturing machines, systems and structures with advanced automation.</p>
      </div>
      <div class="dept-card">
        <svg class="icon" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="1.4"><path d="M12 2v6M12 22v-6M4 12H2M22 12h-2M6 6l2 2M18 18l-2-2M6 18l2-2M18 6l-2 2"/><circle cx="12" cy="12" r="3"/></svg>
        <h3>CSE — AI &amp; ML</h3>
        <p>A dedicated specialization track in artificial intelligence and machine learning within the CSE department.</p>
      </div>
    </div>
  </div>
</section>

<section>
  <div class="wrap">
    <div class="section-head reveal">
      <div class="eyebrow">Why Takshshila</div>
      <h2>Learning, faculty and outcomes — aligned.</h2>
    </div>
    <div class="feat-grid reveal">
      <div class="feat-card">
        <div class="num">01</div>
        <h3>Innovative Learning</h3>
        <p>Modern teaching methods that enhance creativity, applied skills and technical knowledge.</p>
      </div>
      <div class="feat-card">
        <div class="num">02</div>
        <h3>Experienced Faculty</h3>
        <p>Expert professors delivering quality, industry-focused education and hands-on training.</p>
      </div>
      <div class="feat-card">
        <div class="num">03</div>
        <h3>Excellent Placements</h3>
        <p>Top recruitment opportunities with high-paying and diverse career options across sectors.</p>
      </div>
    </div>
  </div>
</section>

<section>
  <div class="wrap chairman reveal">
    <div class="chairman-img">
      <img src="https://takshshila.ac.in/wp-content/uploads/2025/02/dir-1024x846.png" alt="Chairman Shri R. N. Paharia" loading="lazy">
    </div>
    <div>
      <div class="eyebrow">Chairman's message</div>
      <blockquote>
        Education is the cornerstone of a prosperous society. Our mission is to equip students with the knowledge, skills and ethical values required to excel in their careers and contribute meaningfully to society.
      </blockquote>
      <div class="chairman-name">SHRI R. N. PAHARIA
        <span>Chairman, Takshshila Institute of Engineering &amp; Technology</span>
      </div>
    </div>
  </div>
</section>

<section id="placements">
  <div class="wrap place-grid">
    <div class="reveal">
      <div class="eyebrow">Training &amp; Placement Cell</div>
      <h2 style="font-size:clamp(26px,3.2vw,36px); font-weight:700; margin-bottom:18px;">Bridging students with top industries.</h2>
      <p style="color:var(--sub); font-size:15px;">Active since 2007–08, the T&amp;P Cell runs year-round campus interviews under a full-time placement officer, preparing students to be industry-ready from day one.</p>
      <div class="place-stats">
        <div><div class="num">85%</div><div class="lbl">Overall placement rate</div></div>
        <div><div class="num">30k+</div><div class="lbl">Students placed &amp; trained</div></div>
      </div>
    </div>
    <div class="reveal">
      <div class="eyebrow">Our recruiters</div>
      <div class="recruiters">
        <span>Wipro</span><span>Infosys</span><span>Adobe</span><span>Maruti Suzuki</span>
        <span>CEAT</span><span>Aditya Birla Group</span><span>Zensar</span><span>Hexaware</span>
      </div>
    </div>
  </div>
</section>

<section>
  <div class="wrap">
    <div class="section-head reveal">
      <div class="eyebrow">Testimonials</div>
      <h2>What our students say.</h2>
    </div>
    <div class="test-grid reveal">
      <div class="test-card">
        <p>"I thoroughly enjoyed the courses here and hope to expand on what I've learned about building apps. Well presented, easy to follow, and engaging."</p>
        <div class="who"><div class="avatar">TW</div><div><div class="n">Tony Walker</div><div class="r">Apps Developer</div></div></div>
      </div>
      <div class="test-card">
        <p>"The courses exceeded my expectations, especially in depth of information. In a non-threatening environment I learned design principles I could apply immediately."</p>
        <div class="who"><div class="avatar">MB</div><div><div class="n">Martin Brian</div><div class="r">UI Designer</div></div></div>
      </div>
      <div class="test-card">
        <p>"Excellent content and assignments that build on your knowledge and expand it. I secured new employment in PHP thanks to the Web Development courses."</p>
        <div class="who"><div class="avatar">DF</div><div><div class="n">David Fahim</div><div class="r">Web Developer</div></div></div>
      </div>
    </div>
  </div>
</section>

<section class="cta-band">
  <div class="blueprint"></div>
  <div class="wrap reveal" style="position:relative; z-index:2;">
    <div class="eyebrow" style="justify-content:center;">Admissions open</div>
    <h2>Ready to start building your career?</h2>
    <div class="cta-row">
      <a href="#contact" class="btn-primary">Admission Enquiry →</a>
      <a href="tel:9589038220" class="btn-ghost">Call 9589038220</a>
    </div>
  </div>
</section>

<footer id="contact">
  <div class="wrap">
    <div class="foot-grid">
      <div class="foot-about">
        <div class="brand">
          <div class="brand-mark"><span>T</span></div>
          <div class="brand-text">
            <div class="name">TAKSHSHILA</div>
            <div class="tag">TIET Jabalpur</div>
          </div>
        </div>
        <p>A self-financing institution approved by AICTE, New Delhi, affiliated to RGPV Bhopal &amp; R.D.V.V. Jabalpur. Managed by RNK Educational Society since 2004.</p>
      </div>
      <div>
        <h4>Quick Links</h4>
        <ul>
          <li><a href="#about">About Us</a></li>
          <li><a href="#programmes">Admission Procedure</a></li>
          <li><a href="#">Latest Updates</a></li>
          <li><a href="#placements">Our Placements</a></li>
          <li><a href="#">Photo Gallery</a></li>
        </ul>
      </div>
      <div>
        <h4>Important Links</h4>
        <ul>
          <li><a href="https://www.rgpv.ac.in/" target="_blank" rel="noopener">RGPV Bhopal</a></li>
          <li><a href="https://www.aicte-india.org/" target="_blank" rel="noopener">AICTE</a></li>
          <li><a href="https://www.rgpvdiploma.in/" target="_blank" rel="noopener">RGPV Diploma</a></li>
          <li><a href="https://www.antiragging.in/" target="_blank" rel="noopener">Anti-Ragging</a></li>
        </ul>
      </div>
      <div>
        <h4>Quick Contact</h4>
        <ul>
          <li>Sharda Mandir Road, Sharda Chowk,<br>Madan Mahal, Jabalpur</li>
          <li>8461811104 · 7987107850</li>
          <li>takshshila.ac.in@gmail.com</li>
        </ul>
      </div>
    </div>
    <div class="foot-bottom">
      <div>© 2026 Takshshila Institute of Engineering &amp; Technology. All rights reserved.</div>
      <div class="mono">JABALPUR, MADHYA PRADESH</div>
    </div>
  </div>
</footer>

<script>
  const revealEls = document.querySelectorAll('.reveal');
  const io = new IntersectionObserver((entries)=>{
    entries.forEach(e=>{
      if(e.isIntersecting){ e.target.classList.add('in'); io.unobserve(e.target); }
    });
  }, {threshold:0.12});
  revealEls.forEach(el=>io.observe(el));
</script>

</body>
</html>
