<!DOCTYPE html>
<html lang="en">
<head>
<meta charset="UTF-8" />
<meta name="viewport" content="width=device-width, initial-scale=1.0"/>
<title>Bangla Book Recommendation Dataset</title>
<link href="https://fonts.googleapis.com/css2?family=DM+Serif+Display:ital@0;1&family=DM+Mono:wght@400;500&family=Nunito:wght@400;600;700&display=swap" rel="stylesheet"/>
<style>
  :root {
    --bg: #0d1117;
    --surface: #161b22;
    --border: #30363d;
    --accent: #58a6ff;
    --accent2: #3fb950;
    --text: #e6edf3;
    --muted: #8b949e;
    --tab-active-bg: #1f6feb;
    --tab-hover-bg: #21262d;
    --radius: 10px;
  }

  * { box-sizing: border-box; margin: 0; padding: 0; }

  body {
    background: var(--bg);
    color: var(--text);
    font-family: 'Nunito', sans-serif;
    padding: 2.5rem 1.5rem;
    max-width: 860px;
    margin: 0 auto;
    line-height: 1.7;
  }

  h1 {
    font-family: 'DM Serif Display', serif;
    font-size: 2rem;
    color: var(--text);
    margin-bottom: 0.4rem;
    letter-spacing: -0.3px;
  }

  .divider {
    border: none;
    border-top: 1px solid var(--border);
    margin: 1.5rem 0;
  }

  .summary-text {
    color: var(--muted);
    font-size: 0.97rem;
  }

  .summary-text a {
    color: var(--accent);
    text-decoration: none;
  }

  .summary-text a:hover { text-decoration: underline; }

  h2 {
    font-family: 'DM Serif Display', serif;
    font-size: 1.4rem;
    margin-bottom: 1rem;
    color: var(--text);
  }

  /* ── Menu bar ── */
  .model-menu {
    display: flex;
    flex-wrap: wrap;
    gap: 0.5rem;
    background: var(--surface);
    border: 1px solid var(--border);
    border-radius: var(--radius);
    padding: 0.6rem 0.75rem;
    margin-bottom: 1.25rem;
    align-items: center;
  }

  .model-tab {
    font-family: 'Nunito', sans-serif;
    font-size: 0.88rem;
    font-weight: 600;
    color: var(--muted);
    background: transparent;
    border: none;
    border-radius: 6px;
    padding: 0.42rem 0.85rem;
    cursor: pointer;
    transition: background 0.18s, color 0.18s;
    white-space: nowrap;
  }

  .model-tab:hover {
    background: var(--tab-hover-bg);
    color: var(--text);
  }

  .model-tab.active {
    background: var(--tab-active-bg);
    color: #fff;
  }

  /* ── Download card ── */
  .download-card {
    background: var(--surface);
    border: 1px solid var(--border);
    border-radius: var(--radius);
    padding: 1.4rem 1.6rem;
    display: none;
    animation: fadeIn 0.22s ease;
  }

  .download-card.visible { display: block; }

  @keyframes fadeIn {
    from { opacity: 0; transform: translateY(6px); }
    to   { opacity: 1; transform: translateY(0); }
  }

  .card-title {
    font-size: 1.1rem;
    font-weight: 700;
    color: var(--text);
    margin-bottom: 0.4rem;
  }

  .card-desc {
    font-size: 0.9rem;
    color: var(--muted);
    margin-bottom: 1.1rem;
  }

  .colab-btn {
    display: inline-flex;
    align-items: center;
    gap: 0.5rem;
    background: #1f6feb;
    color: #fff;
    text-decoration: none;
    font-weight: 700;
    font-size: 0.88rem;
    padding: 0.5rem 1.1rem;
    border-radius: 6px;
    transition: background 0.15s;
    font-family: 'DM Mono', monospace;
  }

  .colab-btn:hover { background: #388bfd; }

  .colab-btn svg { flex-shrink: 0; }

  /* ── Note box ── */
  .note {
    background: #161b22;
    border-left: 3px solid #d29922;
    border-radius: 0 6px 6px 0;
    padding: 0.75rem 1rem;
    font-size: 0.88rem;
    color: #d29922;
    margin-top: 1.5rem;
  }

  /* ── Citation ── */
  .citation-block {
    background: #0d1117;
    border: 1px solid var(--border);
    border-radius: var(--radius);
    padding: 1rem 1.2rem;
    font-family: 'DM Mono', monospace;
    font-size: 0.82rem;
    color: #adbac7;
    overflow-x: auto;
    white-space: pre;
    line-height: 1.6;
    margin-top: 0.75rem;
  }
</style>
</head>
<body>

<h1>📚 Bangla Book Recommendation Dataset</h1>
<hr class="divider"/>

<p class="summary-text">
  This repository contains the dataset and code for the paper
  <a href="https://arxiv.org/abs/2602.12129">Towards Personalized Bangla Book Recommendation: A Large-Scale Multi-Entity Book Graph Dataset</a>.
  We introduce a large-scale multi-entity heterogeneous graph dataset integrating users, books, authors, publishers, and categories —
  enabling sophisticated graph-based recommendation systems for Bangla literature.
</p>

<hr class="divider"/>

<h2>🚀 Baseline Models</h2>

<!-- ── Menu bar ── -->
<nav class="model-menu" role="tablist" aria-label="Baseline Models">
  <button class="model-tab active" onclick="selectTab(this, 'global')" role="tab">Global Popularity</button>
  <button class="model-tab" onclick="selectTab(this, 'category')" role="tab">Category-Aware Popularity</button>
  <button class="model-tab" onclick="selectTab(this, 'user_cf')" role="tab">User-Based CF</button>
  <button class="model-tab" onclick="selectTab(this, 'item_cf')" role="tab">Item-Based CF</button>
  <button class="model-tab" onclick="selectTab(this, 'als')" role="tab">Implicit MF (ALS)</button>
  <button class="model-tab" onclick="selectTab(this, 'svd')" role="tab">Explicit MF (SVD)</button>
</nav>

<!-- ── Cards ── -->
<div id="global" class="download-card visible">
  <div class="card-title">Global Popularity</div>
  <div class="card-desc">Recommends books based on overall popularity scores across all users. A simple but effective non-personalized baseline.</div>
  <a class="colab-btn" href="colabnotebooks/global_popularity_colab.ipynb">
    <svg width="16" height="16" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2"><path d="M12 2L2 7l10 5 10-5-10-5z"/><path d="M2 17l10 5 10-5"/><path d="M2 12l10 5 10-5"/></svg>
    Download Notebook
  </a>
</div>

<div id="category" class="download-card">
  <div class="card-title">Category-Aware Popularity</div>
  <div class="card-desc">Extends global popularity by ranking books within their respective categories, giving genre-sensitive recommendations.</div>
  <a class="colab-btn" href="colabnotebooks/category_aware_popularity_colab.ipynb">
    <svg width="16" height="16" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2"><path d="M12 2L2 7l10 5 10-5-10-5z"/><path d="M2 17l10 5 10-5"/><path d="M2 12l10 5 10-5"/></svg>
    Download Notebook
  </a>
</div>

<div id="user_cf" class="download-card">
  <div class="card-title">User-Based Collaborative Filtering</div>
  <div class="card-desc">Finds similar users based on rating patterns and recommends books that like-minded readers have enjoyed.</div>
  <a class="colab-btn" href="colabnotebooks/user_based_cf_colab.ipynb">
    <svg width="16" height="16" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2"><path d="M12 2L2 7l10 5 10-5-10-5z"/><path d="M2 17l10 5 10-5"/><path d="M2 12l10 5 10-5"/></svg>
    Download Notebook
  </a>
</div>

<div id="item_cf" class="download-card">
  <div class="card-title">Item-Based Collaborative Filtering</div>
  <div class="card-desc">Computes item-to-item similarity from user interaction data to surface books similar to ones a user already likes.</div>
  <a class="colab-btn" href="colabnotebooks/item_based_cf_colab.ipynb">
    <svg width="16" height="16" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2"><path d="M12 2L2 7l10 5 10-5-10-5z"/><path d="M2 17l10 5 10-5"/><path d="M2 12l10 5 10-5"/></svg>
    Download Notebook
  </a>
</div>

<div id="als" class="download-card">
  <div class="card-title">Implicit Matrix Factorization (ALS)</div>
  <div class="card-desc">Uses Alternating Least Squares to decompose the implicit feedback matrix into latent user and item factors.</div>
  <a class="colab-btn" href="colabnotebooks/implicit_mf_als_colab.ipynb">
    <svg width="16" height="16" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2"><path d="M12 2L2 7l10 5 10-5-10-5z"/><path d="M2 17l10 5 10-5"/><path d="M2 12l10 5 10-5"/></svg>
    Download Notebook
  </a>
</div>

<div id="svd" class="download-card">
  <div class="card-title">Explicit Matrix Factorization (SVD)</div>
  <div class="card-desc">Applies Singular Value Decomposition on explicit ratings for latent factor-based personalized recommendations.</div>
  <a class="colab-btn" href="colabnotebooks/explicit_mf_svd_colab.ipynb">
    <svg width="16" height="16" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2"><path d="M12 2L2 7l10 5 10-5-10-5z"/><path d="M2 17l10 5 10-5"/><path d="M2 12l10 5 10-5"/></svg>
    Download Notebook
  </a>
</div>

<div class="note">
  ⚠️ The SVD notebook requires a one-time kernel restart after the first cell (NumPy version fix). All others run with a single <strong>Runtime → Run all</strong>.
</div>

<hr class="divider"/>

<h2>📖 Citation</h2>
<p class="summary-text">If you use the code, dataset, or model checkpoints, please cite:</p>
<div class="citation-block">@misc{ahmed2026personalizedbanglabookrecommendation,
  title   = {Towards Personalized Bangla Book Recommendation: A Large-Scale Multi-Entity Book Graph Dataset},
  author  = {Rahin Arefin Ahmed and Md. Anik Chowdhury and Sakil Ahmed Sheikh Reza
             and Devnil Bhattacharjee and Muhammad Abdullah Adnan and Nafis Sadeq},
  year    = {2026},
  eprint  = {2602.12129},
  archivePrefix = {arXiv},
  primaryClass  = {cs.IR},
  url     = {https://arxiv.org/abs/2602.12129},
}</div>

<script>
  function selectTab(btn, id) {
    document.querySelectorAll('.model-tab').forEach(t => t.classList.remove('active'));
    document.querySelectorAll('.download-card').forEach(c => c.classList.remove('visible'));
    btn.classList.add('active');
    document.getElementById(id).classList.add('visible');
  }
</script>
</body>
</html>
