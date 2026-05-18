# ardhi
Tempat makan murah di UNDIP
<!DOCTYPE html>
<html lang="id">
<head>
  <meta charset="UTF-8" />
  <meta name="viewport" content="width=device-width, initial-scale=1.0" />
  <title>Makan Murah UNDIP – Peta Kuliner Mahasiswa</title>
  <link rel="preconnect" href="https://fonts.googleapis.com" />
  <link href="https://fonts.googleapis.com/css2?family=Plus+Jakarta+Sans:wght@400;500;600;700&display=swap" rel="stylesheet" />
  <link rel="stylesheet" href="https://cdn.jsdelivr.net/npm/@tabler/icons-webfont@3.31.0/dist/tabler-icons.min.css" />
  <style>
    /* ─── Reset & Base ─────────────────────────────────────────── */
    *, *::before, *::after { box-sizing: border-box; margin: 0; padding: 0; }

    :root {
      --green-50:  #EAF3DE;
      --green-100: #C0DD97;
      --green-200: #97C459;
      --green-400: #639922;
      --green-600: #3B6D11;
      --green-800: #27500A;
      --teal-50:   #E1F5EE;
      --teal-400:  #1D9E75;
      --teal-600:  #0F6E56;
      --teal-800:  #085041;
      --amber-50:  #FAEEDA;
      --amber-200: #EF9F27;
      --amber-400: #BA7517;
      --amber-600: #854F0B;
      --blue-50:   #E6F1FB;
      --blue-400:  #378ADD;
      --blue-600:  #185FA5;
      --coral-50:  #FAECE7;
      --coral-400: #D85A30;
      --coral-600: #993C1D;
      --gray-50:   #F1EFE8;
      --gray-100:  #D3D1C7;
      --gray-200:  #B4B2A9;
      --gray-400:  #888780;
      --gray-600:  #5F5E5A;
      --gray-800:  #444441;
      --red-50:    #FCEBEB;
      --red-400:   #E24B4A;
      --red-600:   #A32D2D;

      --bg:        #FAFAF8;
      --bg2:       #F1EFE8;
      --bg3:       #E8E6DD;
      --surface:   #FFFFFF;
      --border:    rgba(60,60,50,0.12);
      --border2:   rgba(60,60,50,0.22);
      --text:      #1A1A18;
      --text2:     #5F5E5A;
      --text3:     #888780;
      --accent:    #3B6D11;
      --accent-bg: #EAF3DE;
      --shadow-sm: 0 1px 3px rgba(0,0,0,0.08), 0 1px 2px rgba(0,0,0,0.06);
      --shadow-md: 0 4px 16px rgba(0,0,0,0.10), 0 2px 6px rgba(0,0,0,0.06);
      --shadow-lg: 0 12px 32px rgba(0,0,0,0.13), 0 4px 12px rgba(0,0,0,0.08);
      --radius-sm: 8px;
      --radius-md: 12px;
      --radius-lg: 16px;
      --radius-xl: 24px;
      --font: 'Plus Jakarta Sans', system-ui, sans-serif;
      --sidebar-w: 380px;
      --header-h: 64px;
    }

    @media (prefers-color-scheme: dark) {
      :root {
        --bg:      #1A1A18;
        --bg2:     #222220;
        --bg3:     #2A2A28;
        --surface: #2C2C2A;
        --border:  rgba(255,255,240,0.10);
        --border2: rgba(255,255,240,0.18);
        --text:    #EEEEE8;
        --text2:   #B4B2A9;
        --text3:   #888780;
        --accent:  #97C459;
        --accent-bg: #27500A;
        --shadow-sm: 0 1px 3px rgba(0,0,0,0.3);
        --shadow-md: 0 4px 16px rgba(0,0,0,0.35);
        --shadow-lg: 0 12px 32px rgba(0,0,0,0.45);
      }
    }

    html, body {
      height: 100%;
      font-family: var(--font);
      background: var(--bg);
      color: var(--text);
      overflow: hidden;
    }

    /* ─── Layout ────────────────────────────────────────────────── */
    .app {
      display: grid;
      grid-template-rows: var(--header-h) 1fr;
      grid-template-columns: var(--sidebar-w) 1fr;
      height: 100vh;
    }

    /* ─── Header ────────────────────────────────────────────────── */
    .header {
      grid-column: 1 / -1;
      display: flex;
      align-items: center;
      justify-content: space-between;
      padding: 0 24px;
      background: var(--surface);
      border-bottom: 1px solid var(--border);
      box-shadow: var(--shadow-sm);
      z-index: 20;
      gap: 16px;
    }

    .header-brand {
      display: flex;
      align-items: center;
      gap: 10px;
      flex-shrink: 0;
    }

    .brand-icon {
      width: 36px;
      height: 36px;
      background: var(--accent);
      border-radius: 10px;
      display: flex;
      align-items: center;
      justify-content: center;
      color: #fff;
      font-size: 18px;
    }

    .brand-text h1 {
      font-size: 16px;
      font-weight: 700;
      color: var(--text);
      letter-spacing: -0.3px;
    }

    .brand-text p {
      font-size: 11px;
      color: var(--text3);
      margin-top: 1px;
    }

    .header-search {
      flex: 1;
      max-width: 360px;
      position: relative;
    }

    .header-search i {
      position: absolute;
      left: 12px;
      top: 50%;
      transform: translateY(-50%);
      color: var(--text3);
      font-size: 16px;
    }

    .header-search input {
      width: 100%;
      height: 38px;
      padding: 0 12px 0 38px;
      border: 1px solid var(--border2);
      border-radius: 999px;
      background: var(--bg2);
      font-family: var(--font);
      font-size: 13px;
      color: var(--text);
      outline: none;
      transition: border-color 0.15s, box-shadow 0.15s;
    }

    .header-search input:focus {
      border-color: var(--accent);
      box-shadow: 0 0 0 3px rgba(59,109,17,0.12);
    }

    .header-search input::placeholder { color: var(--text3); }

    .header-stats {
      display: flex;
      gap: 20px;
      flex-shrink: 0;
    }

    .stat-pill {
      display: flex;
      align-items: center;
      gap: 6px;
      font-size: 12px;
      color: var(--text2);
    }

    .stat-pill b { color: var(--text); font-weight: 600; }

    /* ─── Sidebar ───────────────────────────────────────────────── */
    .sidebar {
      background: var(--surface);
      border-right: 1px solid var(--border);
      display: flex;
      flex-direction: column;
      overflow: hidden;
      z-index: 10;
    }

    .filters {
      padding: 14px 16px;
      border-bottom: 1px solid var(--border);
      display: flex;
      flex-direction: column;
      gap: 10px;
    }

    .filter-row {
      display: flex;
      align-items: center;
      gap: 6px;
      flex-wrap: wrap;
    }

    .filter-label {
      font-size: 11px;
      font-weight: 600;
      color: var(--text3);
      text-transform: uppercase;
      letter-spacing: 0.5px;
      min-width: 48px;
    }

    .chip {
      font-size: 12px;
      padding: 4px 10px;
      border-radius: 999px;
      border: 1px solid var(--border2);
      background: transparent;
      color: var(--text2);
      cursor: pointer;
      font-family: var(--font);
      font-weight: 500;
      transition: all 0.15s;
    }

    .chip:hover { background: var(--bg2); }

    .chip.active {
      background: var(--accent);
      border-color: var(--accent);
      color: #fff;
    }

    @media (prefers-color-scheme: dark) {
      .chip.active { background: var(--green-600); border-color: var(--green-600); color: #fff; }
    }

    .sort-row {
      display: flex;
      align-items: center;
      gap: 8px;
    }

    .sort-row select {
      flex: 1;
      height: 32px;
      padding: 0 10px;
      border: 1px solid var(--border2);
      border-radius: var(--radius-sm);
      background: var(--bg2);
      color: var(--text);
      font-family: var(--font);
      font-size: 12px;
      cursor: pointer;
      outline: none;
    }

    .result-info {
      font-size: 12px;
      color: var(--text3);
      padding: 8px 16px 6px;
      border-bottom: 1px solid var(--border);
      display: flex;
      align-items: center;
      justify-content: space-between;
    }

    /* ─── Card List ─────────────────────────────────────────────── */
    .list {
      flex: 1;
      overflow-y: auto;
      padding: 10px;
      display: flex;
      flex-direction: column;
      gap: 8px;
    }

    .list::-webkit-scrollbar { width: 4px; }
    .list::-webkit-scrollbar-track { background: transparent; }
    .list::-webkit-scrollbar-thumb { background: var(--border2); border-radius: 2px; }

    .place-card {
      background: var(--bg);
      border: 1px solid var(--border);
      border-radius: var(--radius-md);
      padding: 13px 14px;
      cursor: pointer;
      transition: all 0.15s;
      position: relative;
    }

    .place-card:hover {
      border-color: var(--border2);
      box-shadow: var(--shadow-sm);
      transform: translateY(-1px);
    }

    .place-card.active {
      border-color: var(--accent);
      background: var(--accent-bg);
      box-shadow: 0 0 0 2px rgba(59,109,17,0.15);
    }

    .card-header {
      display: flex;
      align-items: flex-start;
      justify-content: space-between;
      gap: 8px;
    }

    .card-name {
      font-size: 14px;
      font-weight: 600;
      color: var(--text);
      line-height: 1.3;
    }

    .place-card.active .card-name { color: var(--accent); }

    .card-type-badge {
      font-size: 10px;
      font-weight: 600;
      padding: 2px 7px;
      border-radius: 999px;
      white-space: nowrap;
      flex-shrink: 0;
      margin-top: 2px;
    }

    .badge-kantin  { background: var(--blue-50);  color: var(--blue-600); }
    .badge-warteg  { background: var(--teal-50);  color: var(--teal-600); }
    .badge-warung  { background: var(--coral-50); color: var(--coral-600); }

    @media (prefers-color-scheme: dark) {
      .badge-kantin  { background: #0C447C; color: #B5D4F4; }
      .badge-warteg  { background: #085041; color: #9FE1CB; }
      .badge-warung  { background: #712B13; color: #F5C4B3; }
    }

    .card-meta {
      display: flex;
      flex-wrap: wrap;
      gap: 10px;
      margin-top: 8px;
    }

    .meta-item {
      display: flex;
      align-items: center;
      gap: 4px;
      font-size: 12px;
      color: var(--text2);
    }

    .meta-item i { font-size: 13px; }

    .rating-val { color: var(--amber-400); font-weight: 600; }

    .price-tag {
      font-size: 11px;
      font-weight: 600;
      padding: 2px 8px;
      border-radius: 999px;
    }

    .price-cheap  { background: var(--green-50); color: var(--green-600); }
    .price-mid    { background: var(--amber-50); color: var(--amber-600); }

    @media (prefers-color-scheme: dark) {
      .price-cheap { background: #27500A; color: #C0DD97; }
      .price-mid   { background: #633806; color: #FAC775; }
    }

    .card-desc {
      font-size: 12px;
      color: var(--text2);
      margin-top: 7px;
      line-height: 1.55;
      display: -webkit-box;
      -webkit-line-clamp: 2;
      -webkit-box-orient: vertical;
      overflow: hidden;
    }

    .badge-open24 {
      display: inline-flex;
      align-items: center;
      gap: 3px;
      font-size: 10px;
      font-weight: 600;
      background: var(--teal-50);
      color: var(--teal-600);
      padding: 2px 6px;
      border-radius: 999px;
    }

    @media (prefers-color-scheme: dark) {
      .badge-open24 { background: #085041; color: #9FE1CB; }
    }

    .empty-state {
      text-align: center;
      padding: 48px 20px;
      color: var(--text3);
    }

    .empty-state i { font-size: 40px; display: block; margin-bottom: 12px; }
    .empty-state p { font-size: 14px; }

    /* ─── Map Panel ─────────────────────────────────────────────── */
    .map-panel {
      position: relative;
      overflow: hidden;
      background: #d8e8d0;
    }

    @media (prefers-color-scheme: dark) {
      .map-panel { background: #1e2a1e; }
    }

    #map-canvas {
      width: 100%;
      height: 100%;
    }

    /* ─── Detail Drawer ─────────────────────────────────────────── */
    .drawer-overlay {
      display: none;
      position: fixed;
      inset: 0;
      background: rgba(0,0,0,0.35);
      z-index: 30;
      backdrop-filter: blur(2px);
    }

    .drawer-overlay.open { display: block; }

    .drawer {
      position: fixed;
      bottom: 0;
      left: 0;
      right: 0;
      max-height: 70vh;
      background: var(--surface);
      border-radius: var(--radius-xl) var(--radius-xl) 0 0;
      box-shadow: var(--shadow-lg);
      z-index: 40;
      transform: translateY(100%);
      transition: transform 0.3s cubic-bezier(0.32,0.72,0,1);
      overflow: hidden;
      display: flex;
      flex-direction: column;
    }

    .drawer.open { transform: translateY(0); }

    .drawer-handle {
      width: 40px;
      height: 4px;
      background: var(--border2);
      border-radius: 2px;
      margin: 14px auto 0;
      flex-shrink: 0;
    }

    .drawer-body {
      overflow-y: auto;
      padding: 16px 24px 32px;
      flex: 1;
    }

    .drawer-body::-webkit-scrollbar { width: 4px; }
    .drawer-body::-webkit-scrollbar-thumb { background: var(--border2); border-radius: 2px; }

    .drawer-top {
      display: flex;
      align-items: flex-start;
      justify-content: space-between;
      gap: 12px;
      margin-bottom: 16px;
    }

    .drawer-name {
      font-size: 20px;
      font-weight: 700;
      color: var(--text);
      line-height: 1.2;
    }

    .btn-close-drawer {
      width: 32px;
      height: 32px;
      border-radius: 50%;
      border: 1px solid var(--border2);
      background: var(--bg2);
      cursor: pointer;
      display: flex;
      align-items: center;
      justify-content: center;
      color: var(--text2);
      font-size: 16px;
      flex-shrink: 0;
      transition: background 0.15s;
    }

    .btn-close-drawer:hover { background: var(--bg3); }

    .drawer-stats {
      display: grid;
      grid-template-columns: repeat(3, 1fr);
      gap: 10px;
      margin-bottom: 16px;
    }

    .dstat {
      background: var(--bg2);
      border-radius: var(--radius-md);
      padding: 12px;
      text-align: center;
    }

    .dstat-val {
      font-size: 20px;
      font-weight: 700;
      color: var(--text);
    }

    .dstat-lbl {
      font-size: 11px;
      color: var(--text3);
      margin-top: 2px;
    }

    .drawer-section {
      background: var(--bg2);
      border-radius: var(--radius-md);
      padding: 12px 14px;
      margin-bottom: 10px;
    }

    .drawer-section-title {
      font-size: 11px;
      font-weight: 700;
      color: var(--text3);
      text-transform: uppercase;
      letter-spacing: 0.6px;
      margin-bottom: 6px;
    }

    .drawer-section p {
      font-size: 13px;
      color: var(--text);
      line-height: 1.6;
    }

    .drawer-section .highlight {
      background: var(--accent-bg);
      color: var(--accent);
      border-radius: var(--radius-sm);
      padding: 8px 12px;
      font-size: 13px;
      line-height: 1.55;
    }

    @media (prefers-color-scheme: dark) {
      .drawer-section .highlight { background: var(--green-800); color: var(--green-100); }
    }

    .drawer-actions {
      display: flex;
      gap: 10px;
      margin-top: 16px;
    }

    .btn-maps {
      flex: 1;
      height: 44px;
      background: var(--accent);
      color: #fff;
      border: none;
      border-radius: var(--radius-md);
      font-family: var(--font);
      font-size: 14px;
      font-weight: 600;
      cursor: pointer;
      display: flex;
      align-items: center;
      justify-content: center;
      gap: 8px;
      transition: opacity 0.15s, transform 0.1s;
    }

    .btn-maps:hover { opacity: 0.88; }
    .btn-maps:active { transform: scale(0.98); }

    .btn-share {
      height: 44px;
      width: 44px;
      background: var(--bg2);
      border: 1px solid var(--border2);
      border-radius: var(--radius-md);
      font-size: 20px;
      color: var(--text2);
      cursor: pointer;
      display: flex;
      align-items: center;
      justify-content: center;
      transition: background 0.15s;
    }

    .btn-share:hover { background: var(--bg3); }

    /* ─── Map Tooltip ───────────────────────────────────────────── */
    .map-tooltip {
      position: absolute;
      background: var(--surface);
      border: 1px solid var(--border2);
      border-radius: var(--radius-md);
      padding: 10px 14px;
      box-shadow: var(--shadow-md);
      font-size: 13px;
      pointer-events: none;
      opacity: 0;
      transition: opacity 0.15s;
      z-index: 15;
      max-width: 200px;
    }

    .map-tooltip.visible { opacity: 1; }
    .map-tooltip strong { display: block; font-weight: 600; font-size: 13px; color: var(--text); }
    .map-tooltip span { font-size: 12px; color: var(--text2); }

    /* ─── Legend ────────────────────────────────────────────────── */
    .map-legend {
      position: absolute;
      bottom: 20px;
      right: 20px;
      background: var(--surface);
      border: 1px solid var(--border);
      border-radius: var(--radius-md);
      padding: 12px 14px;
      box-shadow: var(--shadow-md);
      font-size: 12px;
      color: var(--text2);
      z-index: 10;
    }

    .legend-title {
      font-size: 11px;
      font-weight: 700;
      color: var(--text3);
      text-transform: uppercase;
      letter-spacing: 0.5px;
      margin-bottom: 8px;
    }

    .legend-item {
      display: flex;
      align-items: center;
      gap: 8px;
      margin-bottom: 6px;
    }

    .legend-dot {
      width: 12px;
      height: 12px;
      border-radius: 50%;
      flex-shrink: 0;
      border: 2px solid rgba(255,255,255,0.6);
    }

    /* ─── Map zoom controls ─────────────────────────────────────── */
    .map-controls {
      position: absolute;
      top: 16px;
      right: 16px;
      display: flex;
      flex-direction: column;
      gap: 4px;
      z-index: 10;
    }

    .map-ctrl-btn {
      width: 36px;
      height: 36px;
      background: var(--surface);
      border: 1px solid var(--border2);
      border-radius: var(--radius-sm);
      box-shadow: var(--shadow-sm);
      cursor: pointer;
      display: flex;
      align-items: center;
      justify-content: center;
      font-size: 18px;
      color: var(--text2);
      transition: background 0.12s;
    }

    .map-ctrl-btn:hover { background: var(--bg2); }

    /* ─── Responsive ────────────────────────────────────────────── */
    @media (max-width: 768px) {
      :root { --sidebar-w: 100vw; --header-h: 56px; }

      .app {
        grid-template-rows: var(--header-h) 260px 1fr;
        grid-template-columns: 1fr;
      }

      .header-stats { display: none; }
      .map-panel { grid-row: 2; }
      .sidebar { grid-row: 3; border-right: none; border-top: 1px solid var(--border); }
      .map-legend { bottom: 10px; right: 10px; padding: 8px 10px; font-size: 11px; }
    }
  </style>
</head>
<body>

<div class="app">
  <!-- ── Header ── -->
  <header class="header">
    <div class="header-brand">
      <div class="brand-icon"><i class="ti ti-map-pin"></i></div>
      <div class="brand-text">
        <h1>Makan Murah UNDIP</h1>
        <p>Peta Kuliner Mahasiswa Tembalang</p>
      </div>
    </div>

    <div class="header-search">
      <i class="ti ti-search"></i>
      <input type="text" id="search-input" placeholder="Cari nama tempat atau menu…" oninput="onSearch(this.value)" />
    </div>

    <div class="header-stats">
      <div class="stat-pill"><i class="ti ti-building-store"></i> <span><b id="stat-total">11</b> lokasi</span></div>
      <div class="stat-pill"><i class="ti ti-clock-24"></i> <span><b>1</b> buka 24 jam</span></div>
      <div class="stat-pill"><i class="ti ti-map"></i> <span>Tembalang, Semarang</span></div>
    </div>
  </header>

  <!-- ── Map ── -->
  <section class="map-panel">
    <canvas id="map-canvas"></canvas>

    <div class="map-controls">
      <button class="map-ctrl-btn" onclick="zoom(1.2)" title="Zoom in"><i class="ti ti-plus"></i></button>
      <button class="map-ctrl-btn" onclick="zoom(0.8)" title="Zoom out"><i class="ti ti-minus"></i></button>
      <button class="map-ctrl-btn" onclick="resetView()" title="Reset view"><i class="ti ti-focus-centered"></i></button>
    </div>

    <div class="map-legend">
      <div class="legend-title">Jenis Tempat</div>
      <div class="legend-item"><div class="legend-dot" style="background:#185FA5"></div> Kantin Kampus</div>
      <div class="legend-item"><div class="legend-dot" style="background:#0F6E56"></div> Warteg</div>
      <div class="legend-item"><div class="legend-dot" style="background:#993C1D"></div> Warung Makan</div>
    </div>

    <div class="map-tooltip" id="map-tooltip">
      <strong id="tt-name">—</strong>
      <span id="tt-info">—</span>
    </div>
  </section>

  <!-- ── Sidebar ── -->
  <aside class="sidebar">
    <div class="filters">
      <div class="filter-row">
        <span class="filter-label">Harga</span>
        <button class="chip active" data-price="all"  onclick="setFilterPrice('all',this)">Semua</button>
        <button class="chip"        data-price="cheap" onclick="setFilterPrice('cheap',this)">≤ Rp15rb</button>
        <button class="chip"        data-price="mid"   onclick="setFilterPrice('mid',this)">≤ Rp25rb</button>
      </div>
      <div class="filter-row">
        <span class="filter-label">Jenis</span>
        <button class="chip active" data-type="all"    onclick="setFilterType('all',this)">Semua</button>
        <button class="chip"        data-type="kantin" onclick="setFilterType('kantin',this)">Kantin</button>
        <button class="chip"        data-type="warteg" onclick="setFilterType('warteg',this)">Warteg</button>
        <button class="chip"        data-type="warung" onclick="setFilterType('warung',this)">Warung</button>
      </div>
      <div class="sort-row">
        <i class="ti ti-arrows-sort" style="color:var(--text3);font-size:16px"></i>
        <select onchange="setSort(this.value)">
          <option value="distance">Urut berdasarkan: Jarak terdekat</option>
          <option value="rating">Urut berdasarkan: Rating tertinggi</option>
          <option value="price">Urut berdasarkan: Harga termurah</option>
          <option value="name">Urut berdasarkan: Nama (A–Z)</option>
        </select>
      </div>
    </div>

    <div class="result-info">
      <span id="result-count">Menampilkan 11 lokasi</span>
      <span id="dist-ref" style="font-size:11px;color:var(--text3)">📍 dari Gerbang UNDIP</span>
    </div>

    <div class="list" id="place-list"></div>
  </aside>
</div>

<!-- ── Drawer Overlay ── -->
<div class="drawer-overlay" id="drawer-overlay" onclick="closeDrawer()"></div>

<!-- ── Detail Drawer ── -->
<div class="drawer" id="detail-drawer">
  <div class="drawer-handle"></div>
  <div class="drawer-body" id="drawer-body"></div>
</div>

<script>
/* ═══════════════════════════════════════════════════════
   DATA
═══════════════════════════════════════════════════════ */
const UNDIP_REF = { lat: -7.0525, lng: 110.4377, name: 'Gerbang UNDIP' };

const PLACES = [
  {
    id: 1, name: 'Kantin FISIP UNDIP', type: 'kantin',
    lat: -7.0529, lng: 110.4377, maxPrice: 15000,
    rating: 4.2, ratingCount: 36,
    hours: 'Sen–Jum 07.00–16.00', closed: 'Sabtu & Minggu',
    desc: 'Kantin dalam kampus FISIP dengan 10–12 stan makanan. Ada nasi ayam, katsu, mie, bakso, gado-gado.',
    tip: 'Stan nasi ayam saus cabe hijau di pojok kanan sangat direkomendasikan. Datang sebelum jam 12 agar tidak kehabisan!',
    address: 'Jl. Prof. Soedarto, Tembalang, FISIP UNDIP',
    phone: null,
    menu: ['Nasi Ayam', 'Nasi Katsu', 'Bakso', 'Mie Ayam', 'Gado-gado', 'Jus & Minuman'],
    isOpen24: false,
  },
  {
    id: 2, name: 'Kantin FPIK UNDIP', type: 'kantin',
    lat: -7.0502, lng: 110.4433, maxPrice: 15000,
    rating: 4.3, ratingCount: 134,
    hours: 'Sen–Jum 08.00–16.00', closed: 'Sabtu & Minggu',
    desc: 'Kantin dalam kampus FPIK. Menu lengkap untuk sarapan dan makan siang mahasiswa.',
    tip: 'Porsi besar untuk harganya. Datang sebelum jam 12 agar menu masih lengkap. Parkir luas dan gratis.',
    address: 'Jl. Prof. Soedarto, Tembalang, FPIK UNDIP',
    phone: null,
    menu: ['Nasi Campur', 'Nasi Goreng', 'Mie', 'Soto', 'Pecel', 'Es Teh'],
    isOpen24: false,
  },
  {
    id: 3, name: 'Warteg Citra Muncul', type: 'warteg',
    lat: -7.0597, lng: 110.4385, maxPrice: 18000,
    rating: 4.5, ratingCount: 168,
    hours: 'Setiap hari 05.30–21.00', closed: '–',
    desc: 'Warteg favorit mahasiswa di Banjarsari. Pilihan lauk lengkap, nasi bisa tambah, harga sangat terjangkau.',
    tip: 'Salah satu warteg terbaik di Tembalang. Buka pagi jadi cocok untuk sarapan. Pelayanan cepat dan ramah.',
    address: 'Jl. Banjarsari Raya Tembalang, Tembalang',
    phone: '+62 877-0014-0504',
    menu: ['Nasi Lauk Pauk', 'Tempe', 'Tahu', 'Ayam Goreng', 'Ikan', 'Sayur'],
    isOpen24: false,
  },
  {
    id: 4, name: 'Warteg Ibu Dewi UNDIP', type: 'warteg',
    lat: -7.0563, lng: 110.4406, maxPrice: 15000,
    rating: 4.5, ratingCount: 117,
    hours: 'Setiap hari 05.00–21.30', closed: '–',
    desc: 'Warteg khas Jawa dekat area UNDIP. Banyak pilihan sayur, tempe, tahu, dan lauk-pauk rumahan.',
    tip: 'Harga sangat terjangkau. Suasana seperti masak sendiri di rumah. Ada kucing peliharaan jika tidak nyaman pertimbangkan.',
    address: 'Jl. Prof. Soedarto No.12i, Sumurboto',
    phone: null,
    menu: ['Nasi Sayur', 'Tempe Kering', 'Tahu', 'Jengkol', 'Spinach', 'Ayam', 'Telur'],
    isOpen24: false,
  },
  {
    id: 5, name: 'Warteg Kharisma Bahari', type: 'warteg',
    lat: -7.0557, lng: 110.4364, maxPrice: 20000,
    rating: 4.4, ratingCount: 280,
    hours: 'Buka 24 jam, 7 hari seminggu', closed: '–',
    desc: 'Satu-satunya warteg buka 24 jam di Tembalang! Solusi makan malam terlambat atau dini hari saat begadang.',
    tip: 'Penyelamat saat deadline mepet tengah malam. Menu standar warteg tapi konsisten enak. Paling ramai jam 22.00–02.00.',
    address: 'Jl. KH. Sirojudin No.1G, Tembalang',
    phone: '+62 882-2682-8803',
    menu: ['Nasi Campur', 'Lauk Pauk', 'Tempe Tahu', 'Sayur', 'Minuman Dingin'],
    isOpen24: true,
  },
  {
    id: 6, name: 'Penyet Bu Nur', type: 'warung',
    lat: -7.0668, lng: 110.4404, maxPrice: 20000,
    rating: 4.7, ratingCount: 1862,
    hours: 'Sen–Sab 06.00–21.00', closed: 'Minggu',
    desc: 'Warung penyet legendaris di Tembalang. Ayam bakar, lele goreng, orak-arik dengan sambal khas rumahan.',
    tip: 'Siap antri 20–30 menit di jam makan siang! Sambal-nya pedas luar biasa. Gongso dan orak-arik sangat direkomendasikan.',
    address: 'Jl. Mulawarman Utara Dalam II, Bulusan',
    phone: '+62 813-2844-8929',
    menu: ['Ayam Bakar', 'Lele Goreng', 'Orak-arik', 'Gongso', 'Nasi Goreng', 'Sambal Khas'],
    isOpen24: false,
  },
  {
    id: 7, name: 'Penyet Kuah Timoho', type: 'warung',
    lat: -7.0605, lng: 110.4438, maxPrice: 15000,
    rating: 4.7, ratingCount: 1304,
    hours: 'Sen–Sab 17.00–22.00', closed: 'Minggu',
    desc: 'Penyet berkuah rempah dengan kemangi! Menu unik: ayam, lele, nila, atau tempe direbus dalam kuah pedas segar.',
    tip: 'Hanya Rp12rb sudah dapat nasi + ayam penyet kuah! Buka sore saja. Level kepedasan bisa diminta sesuai selera.',
    address: 'Jl. Timoho Raya No.32, Bulusan, Tembalang',
    phone: '+62 895-0281-5252',
    menu: ['Ayam Penyet Kuah', 'Lele Penyet', 'Nila Penyet', 'Tempe Penyet', 'Nasi'],
    isOpen24: false,
  },
  {
    id: 8, name: 'Sowak (Sop Iwak)', type: 'warung',
    lat: -7.0612, lng: 110.4356, maxPrice: 25000,
    rating: 4.4, ratingCount: 4603,
    hours: 'Sen–Sab 10.00–21.00, Min 09.00–21.00', closed: '–',
    desc: 'Sop ikan dengan kuah asam-segar yang khas. NASI BEBAS ambil sepuasnya! Rating ribuan, terbukti enak.',
    tip: 'Nasi unlimited! Pilih level kepedasan 1–5. Sering ramai jam makan siang — siapkan mental antri. Hotplate ayam juga recommended.',
    address: 'Jl. Banjarsari Selatan No.18, Pedalangan',
    phone: '+62 812-2575-3337',
    menu: ['Sop Ikan (Iwak)', 'Hotplate Ayam', 'Nasi Unlimited', 'Aneka Gorengan', 'Minuman'],
    isOpen24: false,
  },
  {
    id: 9, name: 'Warteg Citra Rasa', type: 'warteg',
    lat: -7.0594, lng: 110.4367, maxPrice: 18000,
    rating: 4.1, ratingCount: 116,
    hours: 'Setiap hari 07.00–21.00', closed: '–',
    desc: 'Warteg dengan cita rasa khas Sumatera. Lauk sayur papaya, tumis taoge, dan nasi melimpah di Banjarsari.',
    tip: 'Porsi nasi ekstra besar! Harga mulai Rp16rb sudah kenyang. Tempat luas dan sejuk, parkir gratis.',
    address: 'Jl. Banjarsari Raya Tembalang No.5',
    phone: '+62 858-8922-3009',
    menu: ['Nasi Campur', 'Sayur Papaya', 'Tumis Taoge', 'Omelet', 'Bakso', 'Kale'],
    isOpen24: false,
  },
  {
    id: 10, name: 'Warteg Pulang Pagi Gondang', type: 'warteg',
    lat: -7.0653, lng: 110.4405, maxPrice: 18000,
    rating: 4.7, ratingCount: 50,
    hours: 'Setiap hari 06.00–22.00', closed: '–',
    desc: 'Warteg baru di Gondang dengan suasana nyaman dan bersih. Masakan terasa seperti masakan rumah.',
    tip: 'Menu pagi–siang lebih bervariasi dibanding sore. Balado kentang-nya enak banget! Tempat bersih dan pelayanan ramah.',
    address: 'Jl. Gondang Raya No.30, Bulusan',
    phone: '+62 816-756-776',
    menu: ['Nasi Lauk', 'Balado Kentang', 'Usus Goreng', 'Taoge Tumis', 'Sayur', 'Es Teh'],
    isOpen24: false,
  },
  {
    id: 11, name: 'Kantin Tembalang', type: 'kantin',
    lat: -7.0634, lng: 110.4398, maxPrice: 15000,
    rating: 4.7, ratingCount: 35,
    hours: 'Sen–Sab 08.00–23.00', closed: 'Minggu',
    desc: 'Kantin area Gondang Barat. Makanan enak, porsi besar, parkir luas tanpa biaya parkir.',
    tip: 'Tempat adem dan sangat lega. Cocok untuk makan sambil mengerjakan tugas kelompok. Buka sampai larut.',
    address: 'Jl. Gondang Barat II, Bulusan',
    phone: '+62 817-171-999',
    menu: ['Nasi Campur', 'Mie', 'Bakso', 'Ayam Goreng', 'Soto', 'Minuman'],
    isOpen24: false,
  },
];

/* ═══════════════════════════════════════════════════════
   DISTANCE CALCULATION
═══════════════════════════════════════════════════════ */
function haversine(lat1, lon1, lat2, lon2) {
  const R = 6371000;
  const dLat = (lat2 - lat1) * Math.PI / 180;
  const dLon = (lon2 - lon1) * Math.PI / 180;
  const a = Math.sin(dLat/2)**2 + Math.cos(lat1*Math.PI/180)*Math.cos(lat2*Math.PI/180)*Math.sin(dLon/2)**2;
  return Math.round(R * 2 * Math.atan2(Math.sqrt(a), Math.sqrt(1-a)));
}

PLACES.forEach(p => {
  p.distance = haversine(UNDIP_REF.lat, UNDIP_REF.lng, p.lat, p.lng);
});

/* ═══════════════════════════════════════════════════════
   STATE
═══════════════════════════════════════════════════════ */
let filterPrice = 'all';
let filterType  = 'all';
let sortBy      = 'distance';
let searchQuery = '';
let selectedId  = null;

/* ═══════════════════════════════════════════════════════
   MAP CANVAS
═══════════════════════════════════════════════════════ */
const canvas = document.getElementById('map-canvas');
const ctx    = canvas.getContext('2d');

let mapView = { offsetX: 0, offsetY: 0, scale: 1 };
let isDragging = false, dragStart = { x: 0, y: 0 };

/* Coordinate ranges of our data */
const LAT_MIN = -7.070, LAT_MAX = -7.048;
const LNG_MIN = 110.432, LNG_MAX = 110.448;

function latLngToCanvas(lat, lng, w, h) {
  const nx = (lng - LNG_MIN) / (LNG_MAX - LNG_MIN);
  const ny = (lat - LAT_MIN) / (LAT_MAX - LAT_MIN);
  return {
    x: nx * w,
    y: (1 - ny) * h,
  };
}

function isDarkMode() {
  return window.matchMedia && window.matchMedia('(prefers-color-scheme: dark)').matches;
}

function drawMap() {
  const W = canvas.width, H = canvas.height;
  ctx.clearRect(0, 0, W, H);
  ctx.save();
  ctx.translate(mapView.offsetX, mapView.offsetY);
  ctx.scale(mapView.scale, mapView.scale);

  const dark = isDarkMode();

  /* Background */
  ctx.fillStyle = dark ? '#1e2a1e' : '#d8e8d0';
  ctx.fillRect(-mapView.offsetX/mapView.scale, -mapView.offsetY/mapView.scale, W/mapView.scale, H/mapView.scale);

  /* Grid-like campus block */
  const campus = [
    { lat: -7.046, lng: 110.433 },
    { lat: -7.046, lng: 110.444 },
    { lat: -7.058, lng: 110.444 },
    { lat: -7.058, lng: 110.433 },
  ];
  ctx.beginPath();
  campus.forEach((pt, i) => {
    const { x, y } = latLngToCanvas(pt.lat, pt.lng, W, H);
    if (i === 0) ctx.moveTo(x, y); else ctx.lineTo(x, y);
  });
  ctx.closePath();
  ctx.fillStyle = dark ? 'rgba(39,80,10,0.25)' : 'rgba(144,188,70,0.25)';
  ctx.strokeStyle = dark ? '#3B6D11' : '#5a9e20';
  ctx.lineWidth = 1 / mapView.scale;
  ctx.fill();
  ctx.stroke();

  /* Campus label */
  const campusCenter = latLngToCanvas(-7.052, 110.4385, W, H);
  ctx.fillStyle = dark ? '#97C459' : '#3B6D11';
  ctx.font = `${Math.max(10, 13/mapView.scale)}px 'Plus Jakarta Sans', sans-serif`;
  ctx.textAlign = 'center';
  ctx.fillText('Kampus UNDIP', campusCenter.x, campusCenter.y - 6/mapView.scale);
  ctx.fillStyle = dark ? '#639922' : '#5a9e20';
  ctx.font = `${Math.max(8, 11/mapView.scale)}px 'Plus Jakarta Sans', sans-serif`;
  ctx.fillText('Tembalang', campusCenter.x, campusCenter.y + 10/mapView.scale);

  /* Roads */
  const roads = [
    { from: { lat: -7.046, lng: 110.433 }, to: { lat: -7.072, lng: 110.433 }, label: 'Jl. Banjarsari', w: 6 },
    { from: { lat: -7.046, lng: 110.437 }, to: { lat: -7.072, lng: 110.437 }, label: '', w: 4 },
    { from: { lat: -7.046, lng: 110.444 }, to: { lat: -7.072, lng: 110.444 }, label: 'Jl. Timoho', w: 4 },
    { from: { lat: -7.052, lng: 110.432 }, to: { lat: -7.052, lng: 110.448 }, label: 'Jl. Prof. Soedarto', w: 8 },
    { from: { lat: -7.060, lng: 110.432 }, to: { lat: -7.060, lng: 110.448 }, label: '', w: 4 },
    { from: { lat: -7.066, lng: 110.432 }, to: { lat: -7.066, lng: 110.448 }, label: 'Jl. Gondang', w: 4 },
  ];

  roads.forEach(r => {
    const a = latLngToCanvas(r.from.lat, r.from.lng, W, H);
    const b = latLngToCanvas(r.to.lat, r.to.lng, W, H);
    ctx.beginPath();
    ctx.moveTo(a.x, a.y);
    ctx.lineTo(b.x, b.y);
    ctx.strokeStyle = dark ? '#3a3a38' : '#ffffff';
    ctx.lineWidth = r.w / mapView.scale;
    ctx.lineCap = 'round';
    ctx.stroke();
    /* Road center line */
    ctx.beginPath();
    ctx.moveTo(a.x, a.y);
    ctx.lineTo(b.x, b.y);
    ctx.strokeStyle = dark ? '#555553' : '#d0d0c0';
    ctx.lineWidth = 1 / mapView.scale;
    ctx.setLineDash([6/mapView.scale, 6/mapView.scale]);
    ctx.stroke();
    ctx.setLineDash([]);

    if (r.label) {
      const mx = (a.x + b.x) / 2, my = (a.y + b.y) / 2;
      ctx.fillStyle = dark ? '#888780' : '#888';
      ctx.font = `${Math.max(7, 9/mapView.scale)}px sans-serif`;
      ctx.textAlign = 'center';
      ctx.fillText(r.label, mx, my - 5/mapView.scale);
    }
  });

  /* UNDIP reference marker */
  const ref = latLngToCanvas(UNDIP_REF.lat, UNDIP_REF.lng, W, H);
  const r = 10 / mapView.scale;
  ctx.beginPath();
  ctx.arc(ref.x, ref.y, r, 0, Math.PI*2);
  ctx.fillStyle = dark ? '#97C459' : '#3B6D11';
  ctx.fill();
  ctx.beginPath();
  ctx.arc(ref.x, ref.y, r, 0, Math.PI*2);
  ctx.strokeStyle = '#fff';
  ctx.lineWidth = 2/mapView.scale;
  ctx.stroke();
  ctx.fillStyle = '#fff';
  ctx.font = `bold ${Math.max(8, 9/mapView.scale)}px sans-serif`;
  ctx.textAlign = 'center';
  ctx.textBaseline = 'middle';
  ctx.fillText('U', ref.x, ref.y);
  ctx.textBaseline = 'alphabetic';
  ctx.fillStyle = dark ? '#97C459' : '#3B6D11';
  ctx.font = `${Math.max(7, 9/mapView.scale)}px 'Plus Jakarta Sans', sans-serif`;
  ctx.fillText('Gerbang UNDIP', ref.x, ref.y + 16/mapView.scale);

  /* Place pins */
  const filteredIds = new Set(getFiltered().map(p => p.id));
  const colors = { kantin: '#185FA5', warteg: '#0F6E56', warung: '#993C1D' };

  PLACES.forEach(p => {
    const { x, y } = latLngToCanvas(p.lat, p.lng, W, H);
    const isActive = p.id === selectedId;
    const isFiltered = filteredIds.has(p.id);
    const pinR = (isActive ? 12 : 8) / mapView.scale;
    const color = colors[p.type];

    ctx.globalAlpha = isFiltered ? 1 : 0.2;

    /* Pulse ring for active */
    if (isActive) {
      ctx.beginPath();
      ctx.arc(x, y, (pinR + 7/mapView.scale), 0, Math.PI*2);
      ctx.strokeStyle = color;
      ctx.lineWidth = 1.5/mapView.scale;
      ctx.globalAlpha = 0.35;
      ctx.stroke();
      ctx.globalAlpha = 1;
    }

    /* Shadow */
    ctx.beginPath();
    ctx.arc(x, y + 1.5/mapView.scale, pinR, 0, Math.PI*2);
    ctx.fillStyle = 'rgba(0,0,0,0.2)';
    ctx.fill();

    /* Pin */
    ctx.beginPath();
    ctx.arc(x, y, pinR, 0, Math.PI*2);
    ctx.fillStyle = color;
    ctx.fill();
    ctx.beginPath();
    ctx.arc(x, y, pinR, 0, Math.PI*2);
    ctx.strokeStyle = '#fff';
    ctx.lineWidth = 2/mapView.scale;
    ctx.stroke();

    /* ID label */
    ctx.fillStyle = '#fff';
    ctx.font = `bold ${Math.max(7, 9/mapView.scale)}px sans-serif`;
    ctx.textAlign = 'center';
    ctx.textBaseline = 'middle';
    ctx.fillText(p.id, x, y);
    ctx.textBaseline = 'alphabetic';
    ctx.globalAlpha = 1;
  });

  ctx.restore();
}

function resizeCanvas() {
  const panel = canvas.parentElement;
  canvas.width  = panel.clientWidth;
  canvas.height = panel.clientHeight;
  resetView();
}

function resetView() {
  const W = canvas.width, H = canvas.height;
  /* Fit all points */
  const margin = 60;
  mapView.scale = Math.min(
    (W - margin*2) / W,
    (H - margin*2) / H
  );
  mapView.offsetX = 0;
  mapView.offsetY = 0;
  mapView.scale = 1;
  drawMap();
}

function zoom(factor) {
  const cx = canvas.width / 2, cy = canvas.height / 2;
  mapView.offsetX = cx - factor * (cx - mapView.offsetX);
  mapView.offsetY = cy - factor * (cy - mapView.offsetY);
  mapView.scale  *= factor;
  mapView.scale   = Math.min(Math.max(mapView.scale, 0.4), 6);
  drawMap();
}

/* Map drag */
canvas.addEventListener('mousedown', e => {
  isDragging = true;
  dragStart = { x: e.clientX - mapView.offsetX, y: e.clientY - mapView.offsetY };
});

canvas.addEventListener('mousemove', e => {
  if (isDragging) {
    mapView.offsetX = e.clientX - dragStart.x;
    mapView.offsetY = e.clientY - dragStart.y;
    drawMap();
    return;
  }
  /* Hover tooltip */
  const W = canvas.width, H = canvas.height;
  const mx = (e.offsetX - mapView.offsetX) / mapView.scale;
  const my = (e.offsetY - mapView.offsetY) / mapView.scale;
  let hovered = null;
  PLACES.forEach(p => {
    const { x, y } = latLngToCanvas(p.lat, p.lng, W, H);
    const dist = Math.hypot(mx - x, my - y);
    if (dist < 14) hovered = p;
  });
  const tt = document.getElementById('map-tooltip');
  if (hovered) {
    document.getElementById('tt-name').textContent = hovered.name;
    document.getElementById('tt-info').textContent = `${hovered.distance}m • ≤ Rp${(hovered.maxPrice/1000).toFixed(0)}rb • ⭐ ${hovered.rating}`;
    tt.style.left = (e.offsetX + 14) + 'px';
    tt.style.top  = (e.offsetY - 10) + 'px';
    tt.classList.add('visible');
    canvas.style.cursor = 'pointer';
  } else {
    tt.classList.remove('visible');
    canvas.style.cursor = isDragging ? 'grabbing' : 'grab';
  }
});

canvas.addEventListener('mouseup', e => {
  if (!isDragging) return;
  isDragging = false;
  canvas.style.cursor = 'grab';
});

canvas.addEventListener('mouseleave', () => {
  isDragging = false;
  document.getElementById('map-tooltip').classList.remove('visible');
});

canvas.addEventListener('wheel', e => {
  e.preventDefault();
  const factor = e.deltaY < 0 ? 1.15 : 0.87;
  const rx = e.offsetX, ry = e.offsetY;
  mapView.offsetX = rx - factor * (rx - mapView.offsetX);
  mapView.offsetY = ry - factor * (ry - mapView.offsetY);
  mapView.scale  *= factor;
  mapView.scale   = Math.min(Math.max(mapView.scale, 0.4), 6);
  drawMap();
}, { passive: false });

canvas.addEventListener('click', e => {
  const W = canvas.width, H = canvas.height;
  const mx = (e.offsetX - mapView.offsetX) / mapView.scale;
  const my = (e.offsetY - mapView.offsetY) / mapView.scale;
  let clicked = null;
  PLACES.forEach(p => {
    const { x, y } = latLngToCanvas(p.lat, p.lng, W, H);
    if (Math.hypot(mx - x, my - y) < 14) clicked = p;
  });
  if (clicked) openDrawer(clicked.id);
});

/* Touch support */
let lastTouchDist = null;
canvas.addEventListener('touchstart', e => {
  if (e.touches.length === 1) {
    isDragging = true;
    dragStart = { x: e.touches[0].clientX - mapView.offsetX, y: e.touches[0].clientY - mapView.offsetY };
  }
  if (e.touches.length === 2) {
    lastTouchDist = Math.hypot(e.touches[0].clientX - e.touches[1].clientX, e.touches[0].clientY - e.touches[1].clientY);
  }
});

canvas.addEventListener('touchmove', e => {
  e.preventDefault();
  if (e.touches.length === 1 && isDragging) {
    mapView.offsetX = e.touches[0].clientX - dragStart.x;
    mapView.offsetY = e.touches[0].clientY - dragStart.y;
    drawMap();
  }
  if (e.touches.length === 2 && lastTouchDist) {
    const d = Math.hypot(e.touches[0].clientX - e.touches[1].clientX, e.touches[0].clientY - e.touches[1].clientY);
    const factor = d / lastTouchDist;
    const cx = (e.touches[0].clientX + e.touches[1].clientX)/2 - canvas.getBoundingClientRect().left;
    const cy = (e.touches[0].clientY + e.touches[1].clientY)/2 - canvas.getBoundingClientRect().top;
    mapView.offsetX = cx - factor*(cx - mapView.offsetX);
    mapView.offsetY = cy - factor*(cy - mapView.offsetY);
    mapView.scale   = Math.min(Math.max(mapView.scale*factor, 0.4), 6);
    lastTouchDist = d;
    drawMap();
  }
}, { passive: false });

canvas.addEventListener('touchend', () => { isDragging = false; lastTouchDist = null; });

/* ═══════════════════════════════════════════════════════
   FILTER / SORT / SEARCH
═══════════════════════════════════════════════════════ */
function getFiltered() {
  let result = PLACES.filter(p => {
    if (filterPrice === 'cheap' && p.maxPrice > 15000) return false;
    if (filterPrice === 'mid'   && p.maxPrice > 25000) return false;
    if (filterType  !== 'all'  && p.type !== filterType) return false;
    if (searchQuery) {
      const q = searchQuery.toLowerCase();
      if (!p.name.toLowerCase().includes(q) && !p.desc.toLowerCase().includes(q) && !p.menu.join(' ').toLowerCase().includes(q)) return false;
    }
    return true;
  });

  result.sort((a, b) => {
    if (sortBy === 'distance') return a.distance - b.distance;
    if (sortBy === 'rating')   return b.rating - a.rating;
    if (sortBy === 'price')    return a.maxPrice - b.maxPrice;
    if (sortBy === 'name')     return a.name.localeCompare(b.name, 'id');
    return 0;
  });
  return result;
}

function setFilterPrice(val, btn) {
  filterPrice = val;
  document.querySelectorAll('[data-price]').forEach(b => b.classList.remove('active'));
  btn.classList.add('active');
  render();
}

function setFilterType(val, btn) {
  filterType = val;
  document.querySelectorAll('[data-type]').forEach(b => b.classList.remove('active'));
  btn.classList.add('active');
  render();
}

function setSort(val) { sortBy = val; render(); }

function onSearch(val) { searchQuery = val.trim(); render(); }

/* ═══════════════════════════════════════════════════════
   RENDER CARDS
═══════════════════════════════════════════════════════ */
function priceClass(max) { return max <= 15000 ? 'price-cheap' : 'price-mid'; }
function priceText(max)  { return `≤ Rp${(max/1000).toFixed(0)}rb`; }
function typeLabel(t)    { return { kantin: 'Kantin', warteg: 'Warteg', warung: 'Warung' }[t]; }
function typeBadge(t)    { return { kantin: 'badge-kantin', warteg: 'badge-warteg', warung: 'badge-warung' }[t]; }

function render() {
  const filtered = getFiltered();
  document.getElementById('result-count').textContent = `${filtered.length} dari ${PLACES.length} lokasi`;
  document.getElementById('stat-total').textContent = filtered.length;

  const listEl = document.getElementById('place-list');
  if (filtered.length === 0) {
    listEl.innerHTML = `<div class="empty-state"><i class="ti ti-search-off"></i><p>Tidak ada tempat makan yang cocok dengan filter kamu</p></div>`;
    drawMap(); return;
  }

  listEl.innerHTML = filtered.map(p => `
    <div class="place-card${p.id === selectedId ? ' active' : ''}" onclick="openDrawer(${p.id})">
      <div class="card-header">
        <div>
          <div class="card-name">${highlight(p.name)}</div>
        </div>
        <span class="card-type-badge ${typeBadge(p.type)}">${typeLabel(p.type)}</span>
      </div>
      <div class="card-meta">
        <span class="meta-item"><i class="ti ti-map-pin"></i> ${p.distance}m</span>
        <span class="meta-item"><i class="ti ti-star-filled" style="color:#EF9F27"></i> <span class="rating-val">${p.rating}</span> <span>(${p.ratingCount.toLocaleString('id')})</span></span>
        <span class="price-tag ${priceClass(p.maxPrice)}">${priceText(p.maxPrice)}</span>
        ${p.isOpen24 ? '<span class="badge-open24"><i class="ti ti-clock-24" style="font-size:11px"></i> 24 jam</span>' : ''}
      </div>
      <div class="card-desc">${highlight(p.desc)}</div>
    </div>
  `).join('');

  drawMap();
}

function highlight(text) {
  if (!searchQuery) return text;
  const escaped = searchQuery.replace(/[.*+?^${}()|[\]\\]/g, '\\$&');
  return text.replace(new RegExp(escaped, 'gi'), m => `<mark style="background:var(--amber-50);color:var(--amber-400);border-radius:3px;padding:0 2px">${m}</mark>`);
}

/* ═══════════════════════════════════════════════════════
   DETAIL DRAWER
═══════════════════════════════════════════════════════ */
function openDrawer(id) {
  selectedId = id;
  const p = PLACES.find(x => x.id === id);

  const menuHtml = p.menu.map(m => `<span style="display:inline-block;font-size:11px;padding:3px 9px;border-radius:999px;background:var(--bg3);color:var(--text2);margin:2px;font-weight:500">${m}</span>`).join('');

  document.getElementById('drawer-body').innerHTML = `
    <div class="drawer-top">
      <div>
        <div style="margin-bottom:6px"><span class="card-type-badge ${typeBadge(p.type)}">${typeLabel(p.type)}</span></div>
        <div class="drawer-name">${p.name}</div>
        <div style="font-size:13px;color:var(--text3);margin-top:4px"><i class="ti ti-map-pin" style="font-size:13px"></i> ${p.address}</div>
      </div>
      <button class="btn-close-drawer" onclick="closeDrawer()"><i class="ti ti-x"></i></button>
    </div>

    <div class="drawer-stats">
      <div class="dstat">
        <div class="dstat-val">${p.distance}m</div>
        <div class="dstat-lbl">dari gerbang</div>
      </div>
      <div class="dstat">
        <div class="dstat-val" style="color:var(--amber-400)">⭐ ${p.rating}</div>
        <div class="dstat-lbl">${p.ratingCount.toLocaleString('id')} ulasan</div>
      </div>
      <div class="dstat">
        <div class="dstat-val" style="color:var(--green-400)">${priceText(p.maxPrice)}</div>
        <div class="dstat-lbl">estimasi biaya</div>
      </div>
    </div>

    <div class="drawer-section">
      <div class="drawer-section-title">Deskripsi</div>
      <p>${p.desc}</p>
    </div>

    <div class="drawer-section">
      <div class="drawer-section-title">💡 Tips Mahasiswa</div>
      <div class="highlight">${p.tip}</div>
    </div>

    <div class="drawer-section">
      <div class="drawer-section-title">Jam Buka</div>
      <p><strong>${p.hours}</strong>${p.closed !== '–' ? `<br><span style="color:var(--text3)">Tutup: ${p.closed}</span>` : ''}</p>
    </div>

    <div class="drawer-section">
      <div class="drawer-section-title">Menu Tersedia</div>
      <div style="margin-top:4px">${menuHtml}</div>
    </div>

    ${p.phone ? `<div class="drawer-section"><div class="drawer-section-title">Kontak</div><p><a href="tel:${p.phone}" style="color:var(--accent);font-weight:500;text-decoration:none">${p.phone}</a></p></div>` : ''}

    <div class="drawer-actions">
      <button class="btn-maps" onclick="openMaps(${p.lat},${p.lng})">
        <i class="ti ti-map-2"></i> Buka di Google Maps
      </button>
      <button class="btn-share" title="Bagikan" onclick="sharePlace(${p.id})">
        <i class="ti ti-share"></i>
      </button>
    </div>
  `;

  document.getElementById('detail-drawer').classList.add('open');
  document.getElementById('drawer-overlay').classList.add('open');
  render();

  /* Scroll card into view */
  setTimeout(() => {
    const card = document.querySelector(`.place-card.active`);
    if (card) card.scrollIntoView({ behavior: 'smooth', block: 'nearest' });
  }, 50);
}

function closeDrawer() {
  selectedId = null;
  document.getElementById('detail-drawer').classList.remove('open');
  document.getElementById('drawer-overlay').classList.remove('open');
  render();
}

function openMaps(lat, lng) {
  window.open(`https://www.google.com/maps/search/?api=1&query=${lat},${lng}`, '_blank');
}

function sharePlace(id) {
  const p = PLACES.find(x => x.id === id);
  const text = `${p.name}\n📍 ${p.address}\n⭐ ${p.rating} | 💰 ${priceText(p.maxPrice)} | 📏 ${p.distance}m dari UNDIP\n\nDari app Makan Murah UNDIP`;
  if (navigator.share) {
    navigator.share({ title: p.name, text }).catch(() => {});
  } else {
    navigator.clipboard.writeText(text).then(() => alert('Info tempat makan disalin ke clipboard!')).catch(() => {});
  }
}

/* ═══════════════════════════════════════════════════════
   INIT
═══════════════════════════════════════════════════════ */
window.addEventListener('resize', () => { resizeCanvas(); render(); });
window.matchMedia('(prefers-color-scheme: dark)').addEventListener('change', () => drawMap());

resizeCanvas();
render();
canvas.style.cursor = 'grab';
</script>
</body>
</html>
