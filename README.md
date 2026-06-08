
<style>
  @import url('https://fonts.googleapis.com/css2?family=Space+Mono:ital,wght@0,400;0,700;1,400&family=Syne:wght@400;700;800&display=swap');

  * { box-sizing: border-box; margin: 0; padding: 0; }

  :root {
    --cyan: #00f5d4;
    --blue: #4361ee;
    --pink: #f72585;
    --gold: #ffd60a;
    --dark: #0a0a0f;
    --card: #0f0f1a;
    --border: rgba(0,245,212,0.18);
    --text: #e8e8f0;
    --muted: #6b6b8a;
  }

  .wrap {
    font-family: 'Space Mono', monospace;
    background: var(--dark);
    color: var(--text);
    padding: 2rem 1.5rem 3rem;
    border-radius: 16px;
    overflow: hidden;
    position: relative;
  }

  .bg-grid {
    position: absolute; inset: 0; z-index: 0;
    background-image:
      linear-gradient(rgba(0,245,212,0.04) 1px, transparent 1px),
      linear-gradient(90deg, rgba(0,245,212,0.04) 1px, transparent 1px);
    background-size: 32px 32px;
    pointer-events: none;
  }

  .content { position: relative; z-index: 1; }

  .hero {
    text-align: center;
    padding: 2rem 0 2.5rem;
    border-bottom: 1px solid var(--border);
    margin-bottom: 2rem;
  }

  .hero-label {
    font-size: 11px;
    letter-spacing: 0.3em;
    color: var(--cyan);
    text-transform: uppercase;
    margin-bottom: 0.75rem;
    animation: fadeUp 0.6s ease both;
  }

  .hero-name {
    font-family: 'Syne', sans-serif;
    font-size: clamp(2.2rem, 6vw, 3.8rem);
    font-weight: 800;
    line-height: 1;
    letter-spacing: -0.02em;
    margin-bottom: 1rem;
    animation: fadeUp 0.7s ease 0.1s both;
    background: linear-gradient(135deg, #fff 0%, var(--cyan) 50%, var(--blue) 100%);
    -webkit-background-clip: text;
    -webkit-text-fill-color: transparent;
    background-clip: text;
  }

  .hero-role {
    font-size: 13px;
    color: var(--muted);
    animation: fadeUp 0.7s ease 0.2s both;
    margin-bottom: 1.5rem;
  }

  .hero-role span { color: var(--cyan); }

  .typing-bar {
    display: inline-flex;
    align-items: center;
    gap: 8px;
    background: rgba(0,245,212,0.06);
    border: 1px solid var(--border);
    border-radius: 4px;
    padding: 8px 16px;
    font-size: 13px;
    color: var(--cyan);
    animation: fadeUp 0.7s ease 0.3s both;
  }

  .cursor {
    display: inline-block;
    width: 2px; height: 14px;
    background: var(--cyan);
    animation: blink 1s steps(1) infinite;
    vertical-align: middle;
  }

  .quote-bar {
    background: rgba(67,97,238,0.08);
    border-left: 3px solid var(--blue);
    padding: 0.75rem 1rem;
    margin-bottom: 2rem;
    border-radius: 0 8px 8px 0;
    font-size: 12px;
    color: var(--muted);
    font-style: italic;
    animation: fadeUp 0.7s ease 0.35s both;
  }

  .quote-bar strong { color: var(--text); font-style: normal; }

  .section-label {
    font-size: 10px;
    letter-spacing: 0.25em;
    color: var(--blue);
    text-transform: uppercase;
    margin-bottom: 1rem;
    display: flex;
    align-items: center;
    gap: 8px;
  }

  .section-label::after {
    content: '';
    flex: 1;
    height: 1px;
    background: var(--border);
  }

  .stack-grid {
    display: grid;
    grid-template-columns: repeat(auto-fill, minmax(120px, 1fr));
    gap: 8px;
    margin-bottom: 2rem;
  }

  .tech-chip {
    background: var(--card);
    border: 1px solid var(--border);
    border-radius: 6px;
    padding: 8px 10px;
    font-size: 12px;
    display: flex;
    align-items: center;
    gap: 7px;
    transition: border-color 0.2s, transform 0.2s;
    cursor: default;
    animation: fadeUp 0.5s ease both;
  }

  .tech-chip:hover {
    border-color: var(--cyan);
    transform: translateY(-2px);
  }

  .tech-chip .dot {
    width: 7px; height: 7px;
    border-radius: 50%;
    flex-shrink: 0;
  }

  .dot-js { background: #f7df1e; }
  .dot-ts { background: #3178c6; }
  .dot-node { background: #6da55f; }
  .dot-nest { background: #e0234e; }
  .dot-express { background: #61dafb; }
  .dot-mongo { background: #4ea94b; }
  .dot-socket { background: #fff; }
  .dot-git { background: #f05033; }
  .dot-rabbit { background: #ff6600; }
  .dot-kafka { background: #231f20; border: 1px solid #555; }

  .wip-grid {
    display: grid;
    gap: 8px;
    margin-bottom: 2rem;
  }

  .wip-item {
    background: var(--card);
    border: 1px solid var(--border);
    border-radius: 8px;
    padding: 10px 14px;
    display: flex;
    align-items: flex-start;
    gap: 10px;
    font-size: 13px;
    animation: fadeUp 0.5s ease both;
    transition: border-color 0.2s;
  }

  .wip-item:hover { border-color: rgba(247,37,133,0.4); }

  .wip-icon {
    font-size: 15px;
    line-height: 1.4;
    flex-shrink: 0;
    width: 22px;
    text-align: center;
  }

  .wip-text { color: var(--muted); line-height: 1.5; }
  .wip-text strong { color: var(--text); font-weight: 700; }

  .stats-row {
    display: grid;
    grid-template-columns: 1fr 1fr;
    gap: 10px;
    margin-bottom: 2rem;
  }

  .stat-card {
    background: var(--card);
    border: 1px solid var(--border);
    border-radius: 10px;
    padding: 14px;
    text-align: center;
    transition: border-color 0.2s, transform 0.2s;
    animation: fadeUp 0.5s ease both;
    cursor: default;
  }

  .stat-card:hover {
    border-color: var(--cyan);
    transform: translateY(-3px);
  }

  .stat-value {
    font-family: 'Syne', sans-serif;
    font-size: 1.8rem;
    font-weight: 800;
    color: var(--cyan);
    display: block;
    line-height: 1;
    margin-bottom: 4px;
  }

  .stat-label {
    font-size: 11px;
    color: var(--muted);
    letter-spacing: 0.1em;
  }

  .connect-row {
    display: flex;
    gap: 10px;
    justify-content: center;
    flex-wrap: wrap;
    margin-bottom: 2rem;
  }

  .connect-btn {
    display: inline-flex;
    align-items: center;
    gap: 8px;
    padding: 10px 20px;
    border-radius: 6px;
    font-family: 'Space Mono', monospace;
    font-size: 12px;
    font-weight: 700;
    text-decoration: none;
    border: 1px solid;
    transition: transform 0.2s, box-shadow 0.2s;
    cursor: pointer;
    letter-spacing: 0.05em;
    animation: fadeUp 0.5s ease both;
  }

  .connect-btn:hover {
    transform: translateY(-2px);
    box-shadow: 0 4px 20px -4px currentColor;
  }

  .btn-li { background: rgba(0,119,181,0.1); border-color: rgba(0,119,181,0.5); color: #0ea5e9; }
  .btn-gh { background: rgba(200,200,200,0.06); border-color: rgba(200,200,200,0.25); color: var(--text); }
  .btn-ww { background: rgba(247,37,133,0.08); border-color: rgba(247,37,133,0.4); color: var(--pink); }

  .footer-line {
    text-align: center;
    font-size: 11px;
    color: var(--muted);
    padding-top: 1.5rem;
    border-top: 1px solid var(--border);
    letter-spacing: 0.05em;
  }

  .footer-line span { color: var(--cyan); }

  @keyframes fadeUp {
    from { opacity: 0; transform: translateY(12px); }
    to   { opacity: 1; transform: translateY(0); }
  }

  @keyframes blink {
    0%, 100% { opacity: 1; }
    50%       { opacity: 0; }
  }

  @keyframes pulse-border {
    0%, 100% { border-color: var(--border); }
    50%       { border-color: rgba(0,245,212,0.35); }
  }
</style>

<div class="wrap">
  <div class="bg-grid"></div>
  <div class="content">

    <div class="hero">
      <div class="hero-label">// backend engineer</div>
      <div class="hero-name">Mohamed A. Fouad</div>
      <div class="hero-role">Node.js &amp; TypeScript <span>·</span> NestJS <span>·</span> Distributed Systems</div>
      <div class="typing-bar">
        <span id="typed-text"></span><span class="cursor"></span>
      </div>
    </div>

    <div class="quote-bar">
      <strong>"Clean code always looks like it was written by someone who cares."</strong> — Michael Feathers
    </div>

    <div class="section-label">// tech stack</div>
    <div class="stack-grid">
      <div class="tech-chip" style="animation-delay:.05s"><span class="dot dot-js"></span>JavaScript</div>
      <div class="tech-chip" style="animation-delay:.1s"><span class="dot dot-ts"></span>TypeScript</div>
      <div class="tech-chip" style="animation-delay:.15s"><span class="dot dot-node"></span>Node.js</div>
      <div class="tech-chip" style="animation-delay:.2s"><span class="dot dot-nest"></span>NestJS</div>
      <div class="tech-chip" style="animation-delay:.25s"><span class="dot dot-express"></span>Express</div>
      <div class="tech-chip" style="animation-delay:.3s"><span class="dot dot-mongo"></span>MongoDB</div>
      <div class="tech-chip" style="animation-delay:.35s"><span class="dot dot-socket"></span>Socket.io</div>
      <div class="tech-chip" style="animation-delay:.4s"><span class="dot dot-git"></span>Git</div>
      <div class="tech-chip" style="animation-delay:.45s"><span class="dot dot-rabbit"></span>RabbitMQ</div>
      <div class="tech-chip" style="animation-delay:.5s"><span class="dot dot-kafka"></span>Kafka</div>
    </div>

    <div class="section-label">// currently building</div>
    <div class="wip-grid">
      <div class="wip-item" style="animation-delay:.1s">
        <div class="wip-icon">🏗</div>
        <div class="wip-text"><strong>Scalable distributed systems</strong> — architecting high-performance backend infrastructure</div>
      </div>
      <div class="wip-item" style="animation-delay:.15s">
        <div class="wip-icon">⚡</div>
        <div class="wip-text"><strong>Enterprise REST APIs</strong> — production-ready NestJS services at scale</div>
      </div>
      <div class="wip-item" style="animation-delay:.2s">
        <div class="wip-icon">🌐</div>
        <div class="wip-text"><strong>Microservices + Message Brokers</strong> — deep-diving RabbitMQ &amp; Kafka patterns</div>
      </div>
      <div class="wip-item" style="animation-delay:.25s">
        <div class="wip-icon">🔒</div>
        <div class="wip-text"><strong>API Security</strong> — advanced auth, OAuth flows, and data encryption protocols</div>
      </div>
    </div>

    <div class="section-label">// github stats</div>
    <div class="stats-row">
      <div class="stat-card" style="animation-delay:.1s">
        <span class="stat-value" id="commits-val">0</span>
        <span class="stat-label">total commits</span>
      </div>
      <div class="stat-card" style="animation-delay:.15s">
        <span class="stat-value" id="streak-val">0</span>
        <span class="stat-label">day streak</span>
      </div>
      <div class="stat-card" style="animation-delay:.2s">
        <span class="stat-value" id="repos-val">0</span>
        <span class="stat-label">repositories</span>
      </div>
      <div class="stat-card" style="animation-delay:.25s">
        <span class="stat-value" id="stars-val">0</span>
        <span class="stat-label">stars earned</span>
      </div>
    </div>

    <div class="section-label">// connect</div>
    <div class="connect-row">
      <a class="connect-btn btn-li" href="https://linkedin.com/in/mohamed-fouad-16a93831b" target="_blank" style="animation-delay:.1s">
        <i class="ti ti-brand-linkedin" aria-hidden="true"></i> LinkedIn
      </a>
      <a class="connect-btn btn-gh" href="https://github.com/MohamedFouad22" target="_blank" style="animation-delay:.15s">
        <i class="ti ti-brand-github" aria-hidden="true"></i> GitHub
      </a>
      <a class="connect-btn btn-ww" href="https://mohamed-ahmed-fouad.vercel.app/" target="_blank" style="animation-delay:.2s">
        <i class="ti ti-world" aria-hidden="true"></i> Portfolio
      </a>
    </div>

    <div class="footer-line">
      ⭐ <span>star a repo</span> if you find it useful &nbsp;·&nbsp; mohmed.foouad@gmail.com
    </div>

  </div>
</div>

<script>
const phrases = [
  'Building scalable backend systems',
  'Developing Enterprise NestJS APIs',
  'Securing and optimizing data',
  'Deep-diving microservices...'
];
let pi = 0, ci = 0, deleting = false;
const el = document.getElementById('typed-text');
function type() {
  const phrase = phrases[pi];
  if (!deleting) {
    el.textContent = phrase.slice(0, ++ci);
    if (ci === phrase.length) { deleting = true; setTimeout(type, 1800); return; }
  } else {
    el.textContent = phrase.slice(0, --ci);
    if (ci === 0) { deleting = false; pi = (pi + 1) % phrases.length; }
  }
  setTimeout(type, deleting ? 40 : 70);
}
type();

function animCount(id, target, duration) {
  const el = document.getElementById(id);
  const start = performance.now();
  function frame(now) {
    const progress = Math.min((now - start) / duration, 1);
    const ease = 1 - Math.pow(1 - progress, 3);
    el.textContent = Math.round(ease * target);
    if (progress < 1) requestAnimationFrame(frame);
  }
  requestAnimationFrame(frame);
}

const observer = new IntersectionObserver(entries => {
  if (entries[0].isIntersecting) {
    animCount('commits-val', 847, 1800);
    animCount('streak-val', 42, 1600);
    animCount('repos-val', 31, 1400);
    animCount('stars-val', 128, 2000);
    observer.disconnect();
  }
}, { threshold: 0.3 });
observer.observe(document.querySelector('.stats-row'));
</script>
