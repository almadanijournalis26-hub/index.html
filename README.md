<!DOCTYPE html>
<html lang="id">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>AL-MANAR — Jurnalisme yang Mencerahkan</title>
<style>
  @import url('https://fonts.googleapis.com/css2?family=Playfair+Display:ital,wght@0,400;0,700;0,900;1,400&family=UnifrakturMaguntia&family=Libre+Baskerville:ital,wght@0,400;0,700;1,400&display=swap');

  :root{
    --ink:#1a1a1a;
    --paper:#f7f4ec;
    --paper-dark:#efe9dc;
    --rule:#c9c2b3;
    --accent:#8b0000;
    --muted:#5a5348;
  }

  *{box-sizing:border-box;margin:0;padding:0;}

  body{
    font-family:'Libre Baskerville', Georgia, serif;
    background-color:var(--paper);
    /* Suasana kertas koran New York Times: tekstur halus + garis samar */
    background-image:
      radial-gradient(circle at 20% 30%, rgba(0,0,0,0.015) 0%, transparent 60%),
      radial-gradient(circle at 80% 70%, rgba(0,0,0,0.02) 0%, transparent 60%),
      repeating-linear-gradient(0deg, rgba(0,0,0,0.012) 0px, rgba(0,0,0,0.012) 1px, transparent 1px, transparent 3px),
      url("data:image/svg+xml,%3Csvg xmlns='http://www.w3.org/2000/svg' width='120' height='120'%3E%3Cfilter id='n'%3E%3CfeTurbulence type='fractalNoise' baseFrequency='0.9' numOctaves='2'/%3E%3CfeColorMatrix values='0 0 0 0 0 0 0 0 0 0 0 0 0 0 0 0 0 0 0.03 0'/%3E%3C/filter%3E%3Crect width='120' height='120' filter='url(%23n)'/%3E%3C/svg%3E");
    color:var(--ink);
    line-height:1.6;
    min-height:100vh;
  }

  /* ============ HEADER NEWSPAPER ============ */
  header.masthead{
    border-bottom:3px double var(--ink);
    padding:14px 20px 0;
    background:rgba(247,244,236,0.92);
    position:relative;
  }
  .topline{
    display:flex;
    justify-content:space-between;
    align-items:center;
    font-size:11px;
    letter-spacing:1.5px;
    text-transform:uppercase;
    border-bottom:1px solid var(--rule);
    padding-bottom:6px;
    margin-bottom:10px;
    color:var(--muted);
    flex-wrap:wrap;
    gap:8px;
  }
  .topline .left, .topline .right{display:flex;gap:16px;flex-wrap:wrap;}
  .masthead-title{
    font-family:'UnifrakturMaguntia', 'Playfair Display', serif;
    font-size:clamp(48px, 11vw, 108px);
    text-align:center;
    letter-spacing:4px;
    line-height:1;
    padding:6px 0 10px;
    text-shadow:1px 1px 0 rgba(0,0,0,0.08);
    animation:inkReveal 1.4s ease-out;
  }
  @keyframes inkReveal{
    from{opacity:0; transform:translateY(-12px); filter:blur(4px);}
    to{opacity:1; transform:translateY(0); filter:blur(0);}
  }
  .tagline{
    text-align:center;
    font-size:12px;
    letter-spacing:3px;
    text-transform:uppercase;
    color:var(--muted);
    padding-bottom:8px;
    border-bottom:1px solid var(--rule);
    margin-bottom:4px;
  }

  /* ============ MASKOT OJAN ============ */
  .mascot-zone{
    display:flex;
    justify-content:center;
    align-items:flex-end;
    gap:16px;
    padding:18px 20px 6px;
    position:relative;
  }
  .ojan{
    width:110px;
    height:130px;
    position:relative;
    animation:floaty 3.2s ease-in-out infinite;
    cursor:pointer;
    flex-shrink:0;
  }
  @keyframes floaty{
    0%,100%{transform:translateY(0) rotate(-1deg);}
    50%{transform:translateY(-9px) rotate(1.5deg);}
  }
  .ojan svg{width:100%;height:100%;display:block;filter:drop-shadow(2px 3px 2px rgba(0,0,0,0.15));}

  /* kedipan mata Ojan */
  .eye-lid{transition:transform .12s ease;}
  .ojan.blink .eye-lid{transform:scaleY(0.08);}
  .ojan.blink .eye-lid{transform-origin:center;}

  .bubble{
    position:relative;
    background:#fffef9;
    border:1.5px solid var(--ink);
    padding:10px 14px;
    font-size:12px;
    font-style:italic;
    max-width:220px;
    line-height:1.45;
    margin-bottom:34px;
    box-shadow:3px 3px 0 rgba(0,0,0,0.08);
  }
  .bubble::after{
    content:"";
    position:absolute;
    left:-9px;
    bottom:14px;
    width:0;height:0;
    border:8px solid transparent;
    border-right-color:var(--ink);
  }
  .bubble::before{
    content:"";
    position:absolute;
    left:-6px;
    bottom:15px;
    width:0;height:0;
    border:7px solid transparent;
    border-right-color:#fffef9;
    z-index:1;
  }

  /* ============ NAV ============ */
  nav.section-nav{
    border-top:1px solid var(--ink);
    border-bottom:1px solid var(--ink);
    background:rgba(239,233,220,0.7);
    padding:9px 20px;
    display:flex;
    justify-content:center;
    gap:26px;
    font-size:11.5px;
    letter-spacing:2px;
    text-transform:uppercase;
    flex-wrap:wrap;
    position:sticky;
    top:0;
    z-index:50;
    backdrop-filter:blur(2px);
  }
  nav.section-nav a{
    color:var(--ink);
    text-decoration:none;
    padding-bottom:2px;
    border-bottom:1px solid transparent;
    transition:border-color .2s, color .2s;
    cursor:pointer;
  }
  nav.section-nav a:hover{color:var(--accent);border-bottom-color:var(--accent);}

  /* ============ LAYOUT ============ */
  main{
    max-width:1180px;
    margin:0 auto;
    padding:26px 20px 60px;
  }

  .toolbar{
    display:flex;
    justify-content:space-between;
    align-items:center;
    gap:14px;
    flex-wrap:wrap;
    border-bottom:1px solid var(--rule);
    padding-bottom:14px;
    margin-bottom:26px;
  }
  .toolbar h2{
    font-family:'Playfair Display', serif;
    font-size:22px;
    letter-spacing:1px;
    text-transform:uppercase;
  }
  .toolbar h2 span{color:var(--accent);}

  button.btn{
    font-family:'Libre Baskerville', serif;
    font-size:12px;
    letter-spacing:1.5px;
    text-transform:uppercase;
    padding:10px 20px;
    background:var(--ink);
    color:var(--paper);
    border:1px solid var(--ink);
    cursor:pointer;
    transition:all .2s;
  }
  button.btn:hover{background:var(--accent);border-color:var(--accent);}
  button.btn.ghost{
    background:transparent;color:var(--ink);
  }
  button.btn.ghost:hover{background:var(--ink);color:var(--paper);}
  button.btn.danger{background:transparent;color:var(--accent);border-color:var(--accent);padding:6px 12px;font-size:10px;}
  button.btn.danger:hover{background:var(--accent);color:#fff;}

  /* ============ ARTIKEL GRID ============ */
  #articles{
    display:grid;
    grid-template-columns:repeat(auto-fill, minmax(300px,1fr));
    gap:0;
    border-top:1px solid var(--ink);
  }
  article.card{
    padding:22px 22px 24px;
    border-bottom:1px solid var(--rule);
    border-right:1px solid var(--rule);
    background:rgba(255,255,255,0.15);
    transition:background .25s;
    position:relative;
    animation:fadeUp .5s ease both;
  }
  article.card:hover{background:rgba(255,255,255,0.55);}
  @keyframes fadeUp{
    from{opacity:0;transform:translateY(14px);}
    to{opacity:1;transform:translateY(0);}
  }

  .kategori{
    display:inline-block;
    font-size:10px;
    letter-spacing:2px;
    text-transform:uppercase;
    color:var(--accent);
    border-bottom:1px solid var(--accent);
    padding-bottom:2px;
    margin-bottom:10px;
    font-weight:700;
  }
  article.card h3{
    font-family:'Playfair Display', serif;
    font-size:22px;
    line-height:1.25;
    margin-bottom:10px;
    font-weight:700;
  }
  article.card h3 a{
    color:var(--ink);
    text-decoration:none;
    background-image:linear-gradient(var(--ink),var(--ink));
    background-size:0% 1px;
    background-repeat:no-repeat;
    background-position:0 100%;
    transition:background-size .3s;
  }
  article.card h3 a:hover{background-size:100% 1px;}

  .meta{
    font-size:11px;
    letter-spacing:1px;
    text-transform:uppercase;
    color:var(--muted);
    margin-bottom:12px;
  }
  .excerpt{
    font-size:14px;
    color:#33302a;
    line-height:1.65;
    margin-bottom:14px;
    white-space:pre-wrap;
  }
  .card-actions{
    display:flex;
    gap:8px;
    justify-content:flex-end;
    border-top:1px dotted var(--rule);
    padding-top:10px;
    margin-top:auto;
  }

  /* empty state */
  .empty-state{
    grid-column:1/-1;
    text-align:center;
    padding:70px 20px;
    border-bottom:1px solid var(--rule);
  }
  .empty-state .big{
    font-family:'Playfair Display',serif;
    font-size:26px;
    margin-bottom:10px;
    font-style:italic;
  }
  .empty-state p{color:var(--muted);font-size:14px;}

  /* ============ MODAL EDITOR ============ */
  .modal-overlay{
    position:fixed;inset:0;
    background:rgba(20,18,14,0.55);
    backdrop-filter:blur(3px);
    display:none;
    align-items:center;
    justify-content:center;
    z-index:200;
    padding:20px;
  }
  .modal-overlay.open{display:flex;}
  .modal{
    background:var(--paper);
    border:2px solid var(--ink);
    max-width:640px;
    width:100%;
    max-height:92vh;
    overflow-y:auto;
    padding:30px 30px 26px;
    box-shadow:8px 8px 0 rgba(0,0,0,0.18);
    animation:popIn .3s ease;
    position:relative;
  }
  @keyframes popIn{
    from{opacity:0;transform:scale(.95) translateY(10px);}
    to{opacity:1;transform:scale(1) translateY(0);}
  }
  .modal h3{
    font-family:'Playfair Display',serif;
    font-size:26px;
    border-bottom:3px double var(--ink);
    padding-bottom:10px;
    margin-bottom:20px;
  }
  .modal label{
    display:block;
    font-size:11px;
    letter-spacing:1.5px;
    text-transform:uppercase;
    margin-bottom:6px;
    color:var(--muted);
    font-weight:700;
  }
  .modal input, .modal textarea, .modal select{
    width:100%;
    font-family:'Libre Baskerville',serif;
    font-size:14px;
    padding:10px 12px;
    border:1px solid var(--rule);
    background:#fffef9;
    color:var(--ink);
    margin-bottom:16px;
    transition:border-color .2s;
  }
  .modal input:focus, .modal textarea:focus, .modal select:focus{
    outline:none;border-color:var(--ink);
    box-shadow:0 0 0 2px rgba(139,0,0,0.1);
  }
  .modal textarea{resize:vertical;min-height:110px;line-height:1.5;}
  .modal-actions{
    display:flex;gap:10px;justify-content:flex-end;
    border-top:1px solid var(--rule);padding-top:18px;margin-top:6px;
  }

  /* ============ FOOTER ============ */
  footer{
    border-top:3px double var(--ink);
    margin-top:20px;
    padding:30px 20px 40px;
    text-align:center;
    font-size:11px;
    letter-spacing:1.5px;
    text-transform:uppercase;
    color:var(--muted);
  }
  footer .f-title{
    font-family:'UnifrakturMaguntia',serif;
    font-size:34px;
    color:var(--ink);
    letter-spacing:3px;
    margin-bottom:6px;
    text-transform:none;
  }
  footer .f-links{
    display:flex;justify-content:center;gap:20px;flex-wrap:wrap;
    margin:12px 0;
  }
  footer .f-links span{cursor:pointer;transition:color .2s;}
  footer .f-links span:hover{color:var(--accent);}

  /* toast */
  .toast{
    position:fixed;bottom:24px;left:50%;transform:translateX(-50%) translateY(80px);
    background:var(--ink);color:var(--paper);
    padding:12px 24px;font-size:12px;letter-spacing:1px;
    text-transform:uppercase;z-index:300;
    opacity:0;transition:all .35s ease;
    border-left:4px solid var(--accent);
  }
  .toast.show{transform:translateX(-50%) translateY(0);opacity:1;}

  /* divider kolom koran pada desktop */
  @media(min-width:900px){
    #articles{
      grid-template-columns:repeat(3,1fr);
    }
    article.card:nth-child(3n){border-right:none;}
    article.card:nth-child(3n+1){padding-left:0;}
  }
  @media(max-width:899px) and (min-width:600px){
    #articles{grid-template-columns:repeat(2,1fr);}
    article.card:nth-child(2n){border-right:none;}
    article.card:nth-child(2n+1){padding-left:0;}
  }
  @media(max-width:599px){
    #articles{grid-template-columns:1fr;}
    article.card{border-right:none;padding-left:0;padding-right:0;}
    .mascot-zone{flex-direction:column;align-items:center;}
    .bubble{margin-bottom:0;margin-top:6px;}
    .bubble::after{left:50%;bottom:auto;top:-9px;transform:translateX(-50%) rotate(90deg);}
    .bubble::before{left:50%;bottom:auto;top:-6px;transform:translateX(-50%) rotate(90deg);}
  }
</style>
</head>
<body>

<!-- ==================== MASTHEAD ==================== -->
<header class="masthead">
  <div class="topline">
    <div class="left">
      <span id="todayDate"></span>
    </div>
    <div class="right">
      <span>Edisi Digital</span>
      <span>Jakarta, Indonesia</span>
      <span>Rp 0,—</span>
    </div>
  </div>

  <h1 class="masthead-title">AL-MANAR</h1>
  <div class="tagline">Jurnalisme yang Mencerahkan &nbsp;•&nbsp; Sejak 2024</div>
</header>

<!-- ==================== MASKOT OJAN ==================== -->
<div class="mascot-zone">
  <div class="ojan" id="ojan" title="Ojan — Maskot AL-MANAR">
    <svg viewBox="0 0 120 140" xmlns="http://www.w3.org/2000/svg">
      <!-- badan / jas -->
      <path d="M30 130 Q28 95 38 84 L82 84 Q92 95 90 130 Z" fill="#2b2b2b"/>
      <!-- kerah kemeja -->
      <path d="M48 84 L60 100 L72 84 Z" fill="#f7f4ec" stroke="#1a1a1a" stroke-width="1.5"/>
      <path d="M52 84 L60 93 L68 84" fill="none" stroke="#8b0000" stroke-width="2.5"/>
      <!-- dasi -->
      <path d="M60 93 L55 108 L60 118 L65 108 Z" fill="#8b0000"/>
      <!-- leher -->
      <rect x="53" y="72" width="14" height="14" rx="4" fill="#e8c9a0"/>
      <!-- kepala -->
      <ellipse cx="60" cy="52" rx="30" ry="30" fill="#f0d2a8"/>
      <!-- rambut -->
      <path d="M30 46 Q32 20 60 18 Q88 20 90 46 Q85 34 74 34 Q64 26 54 34 Q42 32 30 46 Z" fill="#2b1d12"/>
      <!-- telinga -->
      <ellipse cx="30" cy="54" rx="5" ry="8" fill="#e8c9a0"/>
      <ellipse cx="90" cy="54" rx="5" ry="8" fill="#e8c9a0"/>
      <!-- alis -->
      <path d="M42 42 Q48 38 54 42" stroke="#2b1d12" stroke-width="2.5" fill="none" stroke-linecap="round"/>
      <path d="M66 42 Q72 38 78 42" stroke="#2b1d12" stroke-width="2.5" fill="none" stroke-linecap="round"/>
      <!-- mata -->
      <g class="eye">
        <ellipse cx="48" cy="52" rx="6.5" ry="7" fill="#fff"/>
        <circle cx="48.5" cy="52.5" r="3.4" fill="#2b1d12"/>
        <circle cx="49.5" cy="51" r="1.1" fill="#fff"/>
      </g>
      <g class="eye">
        <ellipse cx="72" cy="52" rx="6.5" ry="7" fill="#fff"/>
        <circle cx="72.5" cy="52.5" r="3.4" fill="#2b1d12"/>
        <circle cx="73.5" cy="51" r="1.1" fill="#fff"/>
      </g>
      <!-- kelopak mata (untuk animasi kedip) -->
      <g class="eye-lid">
        <rect x="40" y="45" width="16" height="14" fill="#f0d2a8"/>
        <rect x="64" y="45" width="16" height="14" fill="#f0d2a8"/>
      </g>
      <!-- KACAMATA -->
      <g stroke="#1a1a1a" stroke-width="2.4" fill="none">
        <rect x="38" y="43" width="20" height="18" rx="5" fill="rgba(255,255,255,0.25)"/>
        <rect x="62" y="43" width="20" height="18" rx="5" fill="rgba(255,255,255,0.25)"/>
        <line x1="58" y1="52" x2="62" y2="52"/>
        <line x1="38" y1="50" x2="28" y2="48"/>
        <line x1="82" y1="50" x2="92" y2="48"/>
      </g>
      <!-- pantulan kacamata -->
      <path d="M42 46 L50 46 L44 58 Z" fill="rgba(255,255,255,0.45)"/>
      <path d="M66 46 L74 46 L68 58 Z" fill="rgba(255,255,255,0.45)"/>
      <!-- hidung -->
      <path d="M58 56 Q60 62 62 56" stroke="#c9a678" stroke-width="2" fill="none" stroke-linecap="round"/>
      <!-- kumis tipis jurnalis -->
      <path d="M50 67 Q60 64 70 67" stroke="#2b1d12" stroke-width="2.4" fill="none" stroke-linecap="round"/>
      <!-- mulut -->
      <path d="M53 72 Q60 77 67 72" stroke="#8b5a3c" stroke-width="2.2" fill="none" stroke-linecap="round"/>
      <!-- pipi -->
      <circle cx="40" cy="62" r="4" fill="rgba(220,120,100,0.25)"/>
      <circle cx="80" cy="62" r="4" fill="rgba(220,120,100,0.25)"/>
      <!-- mic / pena di tangan -->
      <rect x="86" y="100" width="5" height="22" rx="2" fill="#c9a678" transform="rotate(18 88 110)"/>
      <circle cx="96" cy="99" r="4.5" fill="#1a1a1a"/>
    </svg>
  </div>

  <div class="bubble" id="bubbleText">"Selamat datang di AL-MANAR! Klik saya untuk sapaan."</div>
</div>

<!-- ==================== NAV ==================== -->
<nav class="section-nav">
  <a data-filter="Semua">Semua</a>
  <a data-filter="Nasional">Nasional</a>
  <a data-filter="Ekonomi">Ekonomi</a>
  <a data-filter="Politik">Politik</a>
  <a data-filter="Budaya">Budaya</a>
  <a data-filter="Olahraga">Olahraga</a>
  <a data-filter="Teknologi">Teknologi</a>
</nav>

<!-- ==================== MAIN ==================== -->
<main>
  <div class="toolbar">
    <h2>Beranda <span>Redaksi</span> <span id="countLabel" style="font-size:13px;color:var(--muted);text-transform:none;letter-spacing:0;">— 0 artikel</span></h2>
    <div style="display:flex;gap:10px;flex-wrap:wrap;">
      <button class="btn ghost" id="exportBtn">Ekspor JSON</button>
      <button class="btn" id="addBtn">+ Tambah Artikel</button>
    </div>
  </div>

  <section id="articles">
    <!-- kartu artikel dirender di sini -->
  </section>
</main>

<!-- ==================== MODAL EDITOR ==================== -->
<div class="modal-overlay" id="modalOverlay">
  <div class="modal" role="dialog" aria-modal="true">
    <h3 id="modalTitle">Tambah Artikel Baru</h3>
    <input type="hidden" id="editId">

    <label for="fKategori">Kategori</label>
    <select id="fKategori">
      <option>Nasional</option>
      <option>Ekonomi</option>
      <option>Politik</option>
      <option>Budaya</option>
      <option>Olahraga</option>
      <option>Teknologi</option>
    </select>

    <label for="fJudul">Judul Artikel</label>
    <input type="text" id="fJudul" placeholder="Tulis judul yang tajam dan informatif...">

    <label for="fPenulis">Penulis</label>
    <input type="text" id="fPenulis" placeholder="Nama jurnalis">

    <label for="fTanggal">Tanggal</label>
    <input type="date" id="fTanggal">

    <label for="fRingkasan">Ringkasan / Isi</label>
    <textarea id="fRingkasan" placeholder="Tulis ringkasan atau isi artikel di sini..."></textarea>

    <div class="modal-actions">
      <button class="btn ghost" id="cancelBtn">Batal</button>
      <button class="btn" id="saveBtn">Simpan Artikel</button>
    </div>
  </div>
</div>

<div class="toast" id="toast"></div>

<!-- ==================== FOOTER ==================== -->
<footer>
  <div class="f-title">AL-MANAR</div>
  <div>Jurnalisme yang Mencerahkan &nbsp;•&nbsp; Kebenaran di Atas Kepentingan</div>
  <div class="f-links">
    <span>Tentang Kami</span>
    <span>Redaksi</span>
    <span>Pedoman Media Siber</span>
    <span>Kontak</span>
  </div>
  <div style="font-size:10px;opacity:.7;">&copy; <span id="year"></span> AL-MANAR. Seluruh hak cipta dilindungi.</div>
</footer>

<script>
/* ==========================================================
   AL-MANAR — Sistem Artikel Manual (localStorage)
   ========================================================== */
const STORAGE_KEY = 'almanar_articles_v1';
let articles = [];
let activeFilter = 'Semua';

/* ---------- util ---------- */
const $ = (s) => document.querySelector(s);
const uid = () => 'a_' + Date.now() + '_' + Math.random().toString(36).slice(2, 7);

function toast(msg){
  const t = $('#toast');
  t.textContent = msg;
  t.classList.add('show');
  clearTimeout(t._tm);
  t._tm = setTimeout(()=>t.classList.remove('show'), 2200);
}

function load(){
  try{
    const raw = localStorage.getItem(STORAGE_KEY);
    articles = raw ? JSON.parse(raw) : [];
  }catch(e){ articles = []; }
  if(!Array.isArray(articles)) articles = [];
}
function save(){
  localStorage.setItem(STORAGE_KEY, JSON.stringify(articles));
}

function formatDate(iso){
  if(!iso) return '—';
  const d = new Date(iso + 'T00:00:00');
  if(isNaN(d)) return iso;
  return d.toLocaleDateString('id-ID', {day:'numeric', month:'long', year:'numeric'});
}

/* ---------- render ---------- */
function render(){
  const wrap = $('#articles');
  const list = activeFilter === 'Semua'
    ? articles
    : articles.filter(a => a.kategori === activeFilter);

  // urutkan terbaru dulu
  list.sort((a,b)=> (b.tanggal||'').localeCompare(a.tanggal||'') );

  $('#countLabel').textContent = `— ${list.length} artikel`;

  if(list.length === 0){
    wrap.innerHTML = `
      <div class="empty-state">
        <div class="big">"Belum ada kabar yang dicatat."</div>
        <p>Klik <strong>+ Tambah Artikel</strong> untuk menulis berita pertama Anda.<br>
        Semua artikel tersimpan otomatis di perangkat ini.</p>
      </div>`;
    return;
  }

  wrap.innerHTML = list.map(a => `
    <article class="card" data-id="${a.id}">
      <span class="kategori">${escapeHtml(a.kategori||'Umum')}</span>
      <h3><a href="#" data-act="view">${escapeHtml(a.judul||'(Tanpa judul)')}</a></h3>
      <div class="meta">Oleh ${escapeHtml(a.penulis||'Anonim')} &nbsp;•&nbsp; ${formatDate(a.tanggal)}</div>
      <div class="excerpt">${escapeHtml(a.ringkasan||'')}</div>
      <div class="card-actions">
        <button class="btn danger" data-act="edit">Edit</button>
        <button class="btn danger" data-act="delete">Hapus</button>
      </div>
    </article>
  `).join('');
}

function escapeHtml(str){
  return String(str)
    .replace(/&/g,'&amp;').replace(/</g,'&lt;').replace(/>/g,'&gt;')
    .replace(/"/g,'&quot;').replace(/'/g,'&#039;');
}

/* ---------- modal ---------- */
const overlay = $('#modalOverlay');

function openModal(article){
  $('#modalTitle').textContent = article ? 'Edit Artikel' : 'Tambah Artikel Baru';
  $('#editId').value = article ? article.id : '';
  $('#fKategori').value = article ? article.kategori : 'Nasional';
  $('#fJudul').value = article ? article.judul : '';
  $('#fPenulis').value = article ? article.penulis : '';
  $('#fTanggal').value = article ? article.tanggal : new Date().toISOString().slice(0,10);
  $('#fRingkasan').value = article ? article.ringkasan : '';
  overlay.classList.add('open');
  setTimeout(()=>$('#fJudul').focus(), 50);
}
function closeModal(){ overlay.classList.remove('open'); }

$('#addBtn').addEventListener('click', ()=>openModal(null));
$('#cancelBtn').addEventListener('click', closeModal);
overlay.addEventListener('click', (e)=>{ if(e.target === overlay) closeModal(); });
document.addEventListener('keydown', (e)=>{ if(e.key === 'Escape') closeModal(); });

$('#saveBtn').addEventListener('click', ()=>{
  const id = $('#editId').value;
  const judul = $('#fJudul').value.trim();
  const penulis = $('#fPenulis').value.trim();
  const kategori = $('#fKategori').value;
  const tanggal = $('#fTanggal').value;
  const ringkasan = $('#fRingkasan').value.trim();

  if(!judul){
    toast('Judul tidak boleh kosong');
    $('#fJudul').focus();
    return;
  }

  if(id){
    const idx = articles.findIndex(a=>a.id === id);
    if(idx > -1){
      articles[idx] = {...articles[idx], judul, penulis, kategori, tanggal, ringkasan};
      toast('Artikel diperbarui');
    }
  }else{
    articles.push({
      id: uid(),
      judul, penulis, kategori, tanggal, ringkasan,
      dibuat: new Date().toISOString()
    });
    toast('Artikel ditambahkan');
  }
  save();
  render();
  closeModal();
});

/* ---------- event delegation kartu ---------- */
$('#articles').addEventListener('click', (e)=>{
  const btn = e.target.closest('[data-act]');
  if(!btn) return;
  e.preventDefault();
  const card = e.target.closest('article.card');
  const id = card?.dataset.id;
  const art = articles.find(a=>a.id === id);
  if(!art) return;

  const act = btn.dataset.act;
  if(act === 'edit') openModal(art);
  if(act === 'view') openModal(art);
  if(act === 'delete'){
    if(confirm(`Hapus artikel "${art.judul}"?`)){
      articles = articles.filter(a=>a.id !== id);
      save(); render(); toast('Artikel dihapus');
    }
  }
});

/* ---------- filter nav ---------- */
document.querySelectorAll('nav.section-nav a').forEach(a=>{
  a.addEventListener('click', ()=>{
    activeFilter = a.dataset.filter;
    render();
    window.scrollTo({top:0, behavior:'smooth'});
  });
});

/* ---------- export ---------- */
$('#exportBtn').addEventListener('click', ()=>{
  if(articles.length === 0){ toast('Belum ada artikel untuk diekspor'); return; }
  const blob = new Blob([JSON.stringify(articles, null, 2)], {type:'application/json'});
  const url = URL.createObjectURL(blob);
  const a = document.createElement('a');
  a.href = url;
  a.download = `al-manar-articles-${new Date().toISOString().slice(0,10)}.json`;
  a.click();
  URL.revokeObjectURL(url);
  toast('Ekspor berhasil');
});

/* ---------- maskot Ojan ---------- */
const ojan = $('#ojan');
const bubble = $('#bubbleText');
const sapaan = [
  '"Halo, saya Ojan! Siap menemani Anda membaca."',
  '"Berita hari ini sudah dicek faktanya, kan?"',
  '"Jurnalisme yang baik dimulai dari rasa ingin tahu."',
  '"Klik artikel untuk membacanya. Saya jaga di sini!"',
  '"Ingat: verifikasi sebelum viralkan!"',
  '"Kacamata saya tipis, tapi catatan saya tajam."'
];
let sapIdx = 0;

ojan.addEventListener('click', ()=>{
  ojan.classList.add('blink');
  setTimeout(()=>ojan.classList.remove('blink'), 160);
  bubble.textContent = sapaan[sapIdx % sapaan.length];
 
