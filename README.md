<!DOCTYPE html>
<html lang="id">
<head>
  <meta charset="UTF-8" />
  <meta name="viewport" content="width=device-width, initial-scale=1.0"/>
  <title>CV - Muhammad Itsar Bashirah</title>
  <style>
    /* ===== CSS untuk layout dan styling ===== */
    * { margin: 0; padding: 0; box-sizing: border-box; }

    body {
      font-family: 'Segoe UI', sans-serif;
      background: #f0f4f8;
      color: #333;
    }

    header {
      background: #1a1a2e;
      color: white;
      padding: 40px 20px;
      text-align: center;
    }

    header h1 { font-size: 2.5rem; }
    header p  { font-size: 1rem; margin-top: 8px; color: #aaa; }

    nav {
      display: flex;
      justify-content: center;
      gap: 16px;
      background: #16213e;
      padding: 12px;
    }

    nav button {
      background: transparent;
      color: #eee;
      border: 1px solid #eee;
      padding: 6px 18px;
      border-radius: 20px;
      cursor: pointer;
      font-size: 0.9rem;
      transition: all 0.3s;
    }

    nav button:hover, nav button.active {
      background: #e94560;
      border-color: #e94560;
    }

    .container {
      max-width: 800px;
      margin: 30px auto;
      padding: 0 20px;
    }

    .section {
      display: none;
      background: white;
      border-radius: 12px;
      padding: 30px;
      margin-bottom: 20px;
      box-shadow: 0 2px 10px rgba(0,0,0,0.08);
    }

    .section.active { display: block; }

    h2 {
      color: #1a1a2e;
      border-left: 4px solid #e94560;
      padding-left: 12px;
      margin-bottom: 20px;
    }

    .item { margin-bottom: 16px; }
    .item h3 { font-size: 1rem; color: #e94560; }
    .item p  { font-size: 0.9rem; color: #555; margin-top: 4px; }

    .skill-bar {
      background: #eee;
      border-radius: 10px;
      margin: 8px 0 14px;
      height: 10px;
    }

    .skill-fill {
      height: 10px;
      border-radius: 10px;
      background: linear-gradient(to right, #e94560, #1a1a2e);
      width: 0;
      transition: width 1s ease;
    }

    #darkToggle {
      display: block;
      margin: 10px auto 30px;
      padding: 8px 20px;
      background: #1a1a2e;
      color: white;
      border: none;
      border-radius: 20px;
      cursor: pointer;
    }

    body.dark { background: #111; color: #eee; }
    body.dark .section { background: #1e1e1e; }
    body.dark h2 { color: #eee; }
  </style>
</head>
<body>

<header>
  <h1>Muhammad Itsar Bashirah</h1>
  <p>Mahasiswa Ilmu Komputer | Web Dev</p>
</header>

<nav>
  <button class="active" onclick="showSection('tentang', this)">Tentang</button>
  <button onclick="showSection('pendidikan', this)">Pendidikan</button>
  <button onclick="showSection('keahlian', this)">Keahlian</button>
  <button onclick="showSection('kontak', this)">Kontak</button>
</nav>

<div class="container">
  <button id="darkToggle" onclick="toggleDark()">🌙 Dark Mode</button>

  <!-- TENTANG -->
  <div id="tentang" class="section active">
    <h2>Tentang Saya</h2>
    <p>Perkenalkan saya lelaki bujangan dari kendari .</p>
  </div>

  <!-- PENDIDIKAN -->
  <div id="pendidikan" class="section">
    <h2>Pendidikan</h2>
    <div class="item">
      <h3>Universitas Halu Oleo — S1 Teknik Informatika</h3>
      <p>2024 – Sekarang | IPK: 3.7</p>
    </div>
    <div class="item">
      <h3>SMA Negeri 5 Kendari</h3>
      <p>Lulus: 2023 | Jurusan IPS</p>
    </div>
  </div>

  <!-- KEAHLIAN -->
  <div id="keahlian" class="section">
    <h2>Keahlian</h2>
    <p><strong>HTML/CSS</strong></p>
    <div class="skill-bar"><div class="skill-fill" data-width="85%"></div></div>
    <p><strong>JavaScript</strong></p>
    <div class="skill-bar"><div class="skill-fill" data-width="75%"></div></div>
    <p><strong>Python</strong></p>
    <div class="skill-bar"><div class="skill-fill" data-width="70%"></div></div>
    <p><strong>Java</strong></p>
    <div class="skill-bar"><div class="skill-fill" data-width="60%"></div></div>
  </div>

  <!-- KONTAK -->
  <div id="kontak" class="section">
    <h2>Kontak</h2>
    <div class="item">
      <h3>Email</h3><p>iksarbasiroh@gmail.com</p>
    </div>
    <div class="item">
      <h3>GitHub</h3><p>github.com/isarBas</p>
    </div>
  </div>
</div>

<script>
  // ===== JavaScript untuk use case CV =====

  // 1. Navigasi antar section (tab switching)
  function showSection(id, btn) {
    document.querySelectorAll('.section').forEach(s => s.classList.remove('active'));
    document.querySelectorAll('nav button').forEach(b => b.classList.remove('active'));
    document.getElementById(id).classList.add('active');
    btn.classList.add('active');

    // Animasi skill bar saat tab keahlian dibuka
    if (id === 'keahlian') animateSkills();
  }

  // 2. Animasi skill bar
  function animateSkills() {
    document.querySelectorAll('.skill-fill').forEach(bar => {
      bar.style.width = bar.getAttribute('data-width');
    });
  }

  // 3. Dark mode toggle
  function toggleDark() {
    document.body.classList.toggle('dark');
    const btn = document.getElementById('darkToggle');
    btn.textContent = document.body.classList.contains('dark')
      ? '☀️ Light Mode' : '🌙 Dark Mode';
  }
</script>

</body>
</html>
