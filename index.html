<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>NewmannScan — Wallet Heritage Scanner</title>

  <!--
    ╔══════════════════════════════════════════════════════╗
    ║  NEWMANNSCAN — Single-File Edition                   ║
    ║  Deploy: push this file to GitHub root as index.html ║
    ║  Then import the repo on vercel.com — done.          ║
    ╚══════════════════════════════════════════════════════╝

    FREE API KEYS NEEDED (tap ⚙️ in the app):
    • Etherscan  → https://etherscan.io/myapikey   (EVM history)
    • Helius     → https://dashboard.helius.dev    (Solana history)
    Keys are stored only in your browser — never sent anywhere.
  -->

  <link rel="preconnect" href="https://fonts.googleapis.com">
  <link href="https://fonts.googleapis.com/css2?family=Bebas+Neue&family=JetBrains+Mono:wght@400;600&family=DM+Sans:ital,wght@0,400;0,500;0,600;1,400&display=swap" rel="stylesheet">
  <script src="https://cdn.tailwindcss.com"></script>
  <script src="https://cdnjs.cloudflare.com/ajax/libs/ethers/5.7.2/ethers.umd.min.js"></script>
  <script>
    tailwind.config = { darkMode: 'class' }
  </script>

  <style>
    *, *::before, *::after { box-sizing: border-box; }

    :root {
      --amber:   #f59e0b;
      --emerald: #10b981;
      --bg:      #080808;
      --card:    #111111;
      --border:  #1f1f1f;
      --muted:   #6b7280;
      --text:    #e5e7eb;
      --font-d: 'Bebas Neue', cursive;
      --font-m: 'JetBrains Mono', monospace;
      --font-u: 'DM Sans', sans-serif;
    }

    body {
      font-family: var(--font-u);
      background: var(--bg);
      color: var(--text);
      min-height: 100vh;
      overflow-x: hidden;
    }

    /* ── Subtle dot-grid background ── */
    body::before {
      content: '';
      position: fixed; inset: 0; z-index: 0; pointer-events: none;
      background-image: radial-gradient(circle, rgba(255,255,255,0.04) 1px, transparent 1px);
      background-size: 28px 28px;
    }

    /* ── Light mode overrides ── */
    body.light {
      --bg:     #f5f0e8;
      --card:   #fffdf7;
      --border: #d9d0be;
      --muted:  #7c7060;
      --text:   #1a1612;
    }
    body.light::before {
      background-image: radial-gradient(circle, rgba(0,0,0,0.05) 1px, transparent 1px);
    }
    body.light .ns-header {
      background: rgba(245,240,232,0.88) !important;
      border-color: var(--border) !important;
    }
    body.light .ns-card  { background: var(--card); border-color: var(--border); }
    body.light .ns-inset { background: #f0ebe0 !important; border-color: #d4c9b0 !important; }
    body.light .ns-input {
      background: #fff !important; border-color: var(--border) !important; color: var(--text) !important;
    }
    body.light .ns-modal-panel { background: #fff; border-color: var(--border); }
    body.light .ns-ghost-btn { border-color: var(--border); color: var(--muted); }
    body.light .ns-badge   { background: rgba(245,158,11,0.08); border-color: rgba(245,158,11,0.25); }
    body.light .ns-stat    { background: #f0ebe0; border-color: #d4c9b0; }
    body.light .ns-version { background: #e8e0d0 !important; border-color: #d4c9b0 !important; color: #7c7060 !important; }
    body.light .ns-shimmer {
      background: linear-gradient(90deg,#e8e0d0 25%,#f5f0e8 50%,#e8e0d0 75%) !important;
    }

    /* ── Typography ── */
    .font-d { font-family: var(--font-d); }
    .font-m { font-family: var(--font-m); }

    /* ── Card ── */
    .ns-card   { background: var(--card); border: 1px solid var(--border); border-radius: 16px; }
    .ns-inset  { background: #0d0d0d; border: 1px solid var(--border); border-radius: 12px; }
    .ns-stat   { background: #0d0d0d; border: 1px solid var(--border); border-radius: 12px; padding: 14px; }
    .ns-badge  { background: rgba(245,158,11,0.08); border: 1px solid rgba(245,158,11,0.22); border-radius: 12px; }
    .ns-input  {
      background: #111; border: 1px solid var(--border);
      color: var(--text); border-radius: 12px; font-family: var(--font-m);
      font-size: 14px; padding: 14px 110px 14px 16px; width: 100%;
      transition: border-color .2s, box-shadow .2s;
    }
    .ns-input::placeholder { color: var(--muted); }
    .ns-input:focus {
      outline: none;
      border-color: var(--amber);
      box-shadow: 0 0 0 3px rgba(245,158,11,.12);
    }
    .ns-btn-amber {
      background: var(--amber); color: #000; font-weight: 600; font-size: 13px;
      border-radius: 8px; padding: 10px 16px; transition: filter .15s, transform .1s;
      position: absolute; right: 8px; top: 50%; transform: translateY(-50%);
      white-space: nowrap;
    }
    .ns-btn-amber:hover { filter: brightness(1.1); }
    .ns-btn-amber:active { filter: brightness(0.95); }
    .ns-ghost-btn {
      border: 1px solid var(--border); color: var(--muted); border-radius: 12px;
      padding: 10px 14px; font-size: 13px; font-weight: 500; transition: background .15s;
    }
    .ns-ghost-btn:hover { background: rgba(255,255,255,.04); }

    /* ── Rank gradients (applied to text via -webkit-background-clip) ── */
    .rg-ancient  { background: linear-gradient(130deg, #fde68a, #f59e0b, #b45309); }
    .rg-og       { background: linear-gradient(130deg, #c4b5fd, #7c3aed, #4c1d95); }
    .rg-veteran  { background: linear-gradient(130deg, #6ee7b7, #059669, #064e3b); }
    .rg-survivor { background: linear-gradient(130deg, #93c5fd, #3b82f6, #1e3a8a); }
    .rg-newborn  { background: linear-gradient(130deg, #d1d5db, #9ca3af, #4b5563); }
    .rg-unknown  { background: linear-gradient(130deg, #374151, #6b7280); }

    /* ── Shimmer skeleton ── */
    .ns-shimmer {
      background: linear-gradient(90deg, #1a1a1a 25%, #252525 50%, #1a1a1a 75%);
      background-size: 200% 100%;
      animation: shimmer 1.6s ease-in-out infinite;
      border-radius: 8px;
    }

    /* ── Scan line on skeleton ── */
    .ns-scan-wrap { position: relative; overflow: hidden; }
    .ns-scan-wrap::after {
      content: '';
      position: absolute; left: 0; right: 0; height: 2px;
      background: linear-gradient(90deg, transparent, var(--amber), transparent);
      animation: scanline 2s ease-in-out infinite;
    }

    /* ── Animations ── */
    @keyframes shimmer   { to { background-position: -200% 0; } }
    @keyframes scanline  { 0%{top:0;opacity:.9} 100%{top:100%;opacity:0} }
    @keyframes fadeUp    { from{opacity:0;transform:translateY(18px)} to{opacity:1;transform:translateY(0)} }
    @keyframes badgePop  { 0%{transform:scale(0) rotate(-15deg);opacity:0} 65%{transform:scale(1.12) rotate(2deg)} 100%{transform:scale(1) rotate(0);opacity:1} }

    .anim-fadeup   { animation: fadeUp   .55s cubic-bezier(.22,1,.36,1) forwards; }
    .anim-badgepop { animation: badgePop .75s cubic-bezier(.34,1.56,.64,1) forwards; }

    /* ── Header glass ── */
    .ns-header {
      background: rgba(8,8,8,.88);
      backdrop-filter: blur(14px);
      -webkit-backdrop-filter: blur(14px);
      border-bottom: 1px solid var(--border);
    }

    /* ── Scrollbar ── */
    ::-webkit-scrollbar { width: 6px; }
    ::-webkit-scrollbar-track { background: transparent; }
    ::-webkit-scrollbar-thumb { background: var(--border); border-radius: 3px; }

    /* ── Toast ── */
    #toast {
      position: fixed; bottom: 24px; left: 50%; transform: translateX(-50%);
      background: #1a1a1a; border: 1px solid #2a2a2a; color: #e5e7eb;
      padding: 8px 20px; border-radius: 99px; font-size: 13px;
      z-index: 999; transition: opacity .25s; white-space: nowrap;
    }
    #toast.hidden { opacity: 0; pointer-events: none; }

    /* ── Modal bottom-sheet on mobile ── */
    @media (max-width: 640px) {
      #settings-panel {
        border-radius: 20px 20px 0 0;
        position: fixed; bottom: 0; left: 0; right: 0;
        max-height: 90vh; overflow-y: auto;
      }
    }
  </style>
</head>

<body>

  <!-- ══════════════════════════════════════
       SETTINGS MODAL
  ══════════════════════════════════════ -->
  <div id="settings-modal"
       class="hidden fixed inset-0 z-50 flex sm:items-center items-end justify-center sm:p-4 p-0"
       style="background: rgba(0,0,0,.72); backdrop-filter: blur(4px);"
       onclick="if(event.target===this) closeSettings()">

    <div id="settings-panel" class="ns-card ns-modal-panel w-full sm:max-w-md p-6">
      <div class="flex items-center justify-between mb-4">
        <h2 class="font-semibold text-base">API Keys</h2>
        <button onclick="closeSettings()"
                class="text-2xl leading-none w-8 h-8 flex items-center justify-center rounded-lg"
                style="color: var(--muted);">×</button>
      </div>

      <div class="text-xs mb-5 px-3 py-2.5 rounded-xl"
           style="background: rgba(245,158,11,.06); border: 1px solid rgba(245,158,11,.2); color: #d97706; line-height: 1.6;">
        🔒 Stored in your browser only — never sent to any server.
      </div>

      <div class="space-y-5">
        <div>
          <label class="text-sm font-medium block mb-2" style="color: var(--muted);">Etherscan API Key</label>
          <input id="key-etherscan" type="password" autocomplete="off"
                 placeholder="Paste your Etherscan key…"
                 class="ns-input" style="padding: 12px 16px; position: static; width: 100%;">
          <div class="flex justify-between mt-2 text-xs" style="color: var(--muted);">
            <span>For Ethereum transaction history</span>
            <a href="https://etherscan.io/myapikey" target="_blank" rel="noopener"
               style="color: var(--amber); text-decoration: underline;">Get free key →</a>
          </div>
        </div>

        <div>
          <label class="text-sm font-medium block mb-2" style="color: var(--muted);">Helius API Key</label>
          <input id="key-helius" type="password" autocomplete="off"
                 placeholder="Paste your Helius key…"
                 class="ns-input" style="padding: 12px 16px; position: static; width: 100%;">
          <div class="flex justify-between mt-2 text-xs" style="color: var(--muted);">
            <span>For Solana transaction history</span>
            <a href="https://dashboard.helius.dev" target="_blank" rel="noopener"
               style="color: var(--amber); text-decoration: underline;">Get free key →</a>
          </div>
        </div>
      </div>

      <button onclick="saveSettings()"
              class="ns-btn-amber w-full mt-6 rounded-xl py-3"
              style="position: static; transform: none; font-size: 14px;">
        Save Keys
      </button>

      <p id="save-ok" class="hidden text-center text-xs mt-3" style="color: var(--emerald);">
        ✓ Keys saved!
      </p>
    </div>
  </div>

  <!-- ══════════════════════════════════════
       HEADER
  ══════════════════════════════════════ -->
  <header class="ns-header sticky top-0 z-40 px-4 py-3" style="position: relative; z-index: 40;">
    <div class="max-w-xl mx-auto flex items-center justify-between">
      <div class="flex items-center gap-2.5">
        <!-- Logo mark -->
        <div class="w-7 h-7 rounded-lg flex items-center justify-center font-d text-black text-sm leading-none"
             style="background: var(--amber); padding-top: 2px;">N</div>
        <span class="font-semibold tracking-tight">NewmannScan</span>
        <span class="ns-version hidden sm:block text-xs px-2 py-0.5 rounded-full font-m"
              style="background: #1a1a1a; color: var(--muted); border: 1px solid var(--border);">v2</span>
      </div>

      <div class="flex items-center gap-0.5">
        <button onclick="toggleTheme()" title="Toggle theme"
                class="p-2.5 rounded-lg text-base transition-colors hover:bg-white/5" id="theme-btn">🌙</button>
        <button onclick="openSettings()" title="API Keys"
                class="p-2.5 rounded-lg text-base transition-colors hover:bg-white/5">⚙️</button>
      </div>
    </div>
  </header>

  <!-- ══════════════════════════════════════
       MAIN
  ══════════════════════════════════════ -->
  <main class="max-w-xl mx-auto px-4 pb-20" style="position: relative; z-index: 1;">

    <!-- Hero text -->
    <div class="text-center pt-10 pb-8">
      <h1 class="font-d tracking-wide leading-none mb-3"
          style="font-size: clamp(2.8rem, 10vw, 4.5rem);
                 background: linear-gradient(135deg, #fde68a, #f59e0b, #d97706);
                 -webkit-background-clip: text; -webkit-text-fill-color: transparent; background-clip: text;">
        WALLET HERITAGE
      </h1>
      <p class="text-sm" style="color: var(--muted);">
        Discover your on-chain legacy across EVM + Solana
      </p>
    </div>

    <!-- Search -->
    <div class="relative mb-3">
      <input id="wallet-input"
             type="text"
             class="ns-input"
             placeholder="0x... Ethereum  or  Solana address"
             onkeydown="if(event.key==='Enter') scanWallet()">
      <button onclick="scanWallet()" class="ns-btn-amber">SCAN ⚡</button>
    </div>

    <!-- Error -->
    <div id="error-msg" class="hidden mb-4 px-4 py-3 rounded-xl text-sm text-center"
         style="background: rgba(239,68,68,.1); border: 1px solid rgba(239,68,68,.25); color: #f87171;"></div>

    <!-- No-key hint -->
    <div id="no-key-hint" class="hidden mb-4 px-4 py-3 rounded-xl text-xs text-center"
         style="background: rgba(245,158,11,.05); border: 1px solid rgba(245,158,11,.2); color: #d97706;">
      ⚠️ No API keys set — results will be limited.
      <button onclick="openSettings()" class="underline font-semibold ml-1">Add keys →</button>
    </div>

    <!-- ── Loading skeleton ── -->
    <div id="loading-state" class="hidden ns-card ns-scan-wrap p-5 space-y-4">
      <div class="flex items-center gap-3">
        <div class="w-10 h-10 rounded-full ns-shimmer flex-shrink-0"></div>
        <div class="flex-1 space-y-2">
          <div class="h-4 ns-shimmer w-2/5"></div>
          <div class="h-3 ns-shimmer w-3/5"></div>
        </div>
        <div class="w-14 h-14 rounded-xl ns-shimmer flex-shrink-0"></div>
      </div>
      <div class="h-[84px] ns-shimmer rounded-xl"></div>
      <div class="grid grid-cols-2 gap-2.5">
        <div class="h-16 ns-shimmer"></div>
        <div class="h-16 ns-shimmer"></div>
        <div class="h-16 ns-shimmer"></div>
        <div class="h-16 ns-shimmer"></div>
      </div>
      <p id="scan-status" class="text-center text-xs" style="color: var(--amber);">Initialising scan…</p>
    </div>

    <!-- ── Results card ── -->
    <div id="results-card" class="hidden anim-fadeup">
      <div class="ns-card overflow-hidden">

        <!-- Rank colour bar -->
        <div id="rank-bar" class="h-0.5 w-full"></div>

        <div class="p-5 sm:p-6">

          <!-- Identity row -->
          <div class="flex items-start justify-between gap-4 mb-5">
            <div class="min-w-0 flex-1">
              <div id="ens-name" class="hidden font-semibold truncate mb-0.5"
                   style="color: var(--amber); font-size: 15px;"></div>
              <div class="flex items-center gap-1.5">
                <span id="addr-display" class="font-m text-xs truncate" style="color: var(--muted);"></span>
                <button onclick="copyAddress()" title="Copy address"
                        class="flex-shrink-0 px-1.5 py-1 rounded text-xs transition-colors hover:bg-white/5"
                        style="color: var(--muted);">📋</button>
              </div>
              <div id="chain-badge"
                   class="inline-flex items-center gap-1 mt-2 px-2.5 py-1 rounded-full text-xs font-medium"
                   style="background: #1a1a1a; border: 1px solid var(--border);"></div>
            </div>

            <!-- Prestige badge -->
            <div id="prestige-badge" class="ns-badge anim-badgepop flex-shrink-0 px-3 py-3 text-center"
                 style="min-width: 68px;">
              <div id="prestige-icon" class="text-2xl leading-none"></div>
              <div id="prestige-label" class="text-xs font-semibold mt-1 leading-tight"
                   style="color: var(--amber);"></div>
              <div id="prestige-lvl" class="text-xs mt-0.5" style="color: var(--muted); font-size: 11px;"></div>
            </div>
          </div>

          <!-- RANK HERO -->
          <div id="rank-hero" class="ns-inset text-center py-6 mb-5">
            <div class="text-xs tracking-widest mb-1.5 font-medium uppercase" style="color: var(--muted);">Primary Rank</div>
            <div id="rank-title" class="font-d tracking-wide" style="font-size: clamp(3.5rem,14vw,5.5rem); line-height: 1;"></div>
            <div id="rank-sub" class="text-xs mt-2" style="color: var(--muted);"></div>
          </div>

          <!-- Stats grid -->
          <div class="grid grid-cols-2 gap-2.5 mb-5">
            <div class="ns-stat">
              <div class="text-xs font-medium mb-1.5" style="color: var(--muted);">Genesis</div>
              <div id="stat-genesis" class="font-m text-xs font-semibold" style="font-size: 12px;"></div>
            </div>
            <div class="ns-stat">
              <div class="text-xs font-medium mb-1.5" style="color: var(--muted);">Wallet Age</div>
              <div id="stat-age" class="text-sm font-semibold"></div>
            </div>
            <div class="ns-stat">
              <div class="text-xs font-medium mb-1.5" style="color: var(--muted);">Transactions</div>
              <div id="stat-txcount" class="font-m text-sm font-semibold"></div>
            </div>
            <div class="ns-stat">
              <div class="text-xs font-medium mb-1.5" style="color: var(--muted);">Gas Spent (est.)</div>
              <div id="stat-gas" class="text-sm font-semibold" style="color: var(--amber);"></div>
              <div id="stat-gas-note" class="hidden text-xs mt-0.5" style="color: #4b5563; font-size: 10px;"></div>
            </div>
          </div>

          <!-- Actions -->
          <div class="flex gap-2">
            <button onclick="shareResult()" class="ns-ghost-btn flex-1">Share link 🔗</button>
            <button onclick="clearResults()" class="ns-ghost-btn" style="padding: 10px 18px;">Clear</button>
          </div>
        </div>
      </div>
      <p class="text-center mt-3 text-xs" style="color: #374151;">
        Gas is estimated from sampled transactions · Prices via CoinGecko
      </p>
    </div>

    <!-- Footer hint -->
    <div id="footer-hint" class="mt-10 text-center text-xs space-y-1.5" style="color: #374151;">
      <p>Supports Ethereum mainnet + Solana</p>
      <p>Tap ⚙️ to add your free API keys</p>
    </div>

  </main>

  <!-- Toast -->
  <div id="toast" class="hidden">Copied!</div>

  <!-- ═══════════════════════════════════════════════════════
       JAVASCRIPT
  ═══════════════════════════════════════════════════════ -->
  <script>
  'use strict';

  /* ─── THEME ─────────────────────────────────────────── */
  let isDark = localStorage.getItem('ns_theme') !== 'light';

  function applyTheme() {
    document.body.classList.toggle('light', !isDark);
    document.getElementById('theme-btn').textContent = isDark ? '🌙' : '☀️';
  }

  function toggleTheme() {
    isDark = !isDark;
    localStorage.setItem('ns_theme', isDark ? 'dark' : 'light');
    applyTheme();
  }

  applyTheme();

  /* ─── SETTINGS ───────────────────────────────────────── */
  function openSettings() {
    document.getElementById('key-etherscan').value = localStorage.getItem('ns_etherscan') || '';
    document.getElementById('key-helius').value    = localStorage.getItem('ns_helius')    || '';
    document.getElementById('save-ok').classList.add('hidden');
    document.getElementById('settings-modal').classList.remove('hidden');
    document.body.style.overflow = 'hidden';
  }

  function closeSettings() {
    document.getElementById('settings-modal').classList.add('hidden');
    document.body.style.overflow = '';
  }

  function sav
