---
layout: default
title: "From Business Analyst to Data Analyst: Skills Roadmap"
description: "A six-stage roadmap I wish I had when I started — what to learn, in what order, and why it matters once you are inside an enterprise data team."
date: 2026-04-19
extra_css: '<link rel="preconnect" href="https://fonts.googleapis.com"><link rel="preconnect" href="https://fonts.gstatic.com" crossorigin><link href="https://fonts.googleapis.com/css2?family=Fraunces:opsz,wght@9..144,500;9..144,600;9..144,700&family=Inter:wght@400;500;600&display=swap" rel="stylesheet">'
---

<style>
  body { background: #f5f2ec; }

  .post {
    --ink:       #15140f;
    --ink-2:     #3a3833;
    --ink-3:     #6f6c64;
    --ink-4:     #a7a49b;
    --rule:      #d9d4c8;
    --rule-soft: #e6e1d4;
    --lnk:       #2a4cd2;
    --serif:     'Fraunces', 'Times New Roman', serif;
    --sans:      'Inter', system-ui, -apple-system, sans-serif;
    max-width: 1240px;
    margin: 0 auto;
    padding: calc(var(--nav-h, 64px) + 48px) 40px 80px;
    font-family: var(--sans);
  }

  .intro { max-width: 760px; }

  .intro__eyebrow {
    display: flex; gap: 10px; align-items: center;
    color: var(--lnk); font-size: 12px; font-weight: 500;
    letter-spacing: 0.14em; text-transform: uppercase; margin-bottom: 28px;
  }
  .intro__sep { color: var(--ink-4); }

  .intro__title {
    font-family: var(--serif); font-weight: 600;
    font-size: clamp(40px, 5.2vw, 72px); line-height: 1.04;
    letter-spacing: -0.02em; margin: 0 0 28px; color: var(--ink);
  }

  .intro__lede {
    font-size: 18px; line-height: 1.65; color: var(--ink-2);
    margin: 0 0 36px; max-width: 640px;
  }

  .intro__meta {
    display: flex; align-items: center; gap: 24px; flex-wrap: wrap;
    padding-top: 24px; border-top: 1px solid var(--rule-soft);
  }

  .intro__progress {
    display: flex; align-items: center; gap: 14px;
    flex: 1 1 auto; min-width: 280px;
  }

  .intro__bar {
    flex: 1 1 auto; max-width: 280px; height: 4px;
    background: var(--rule-soft); border-radius: 999px; overflow: hidden;
  }

  .intro__bar-fill {
    height: 100%; width: 0%; background: var(--ink);
    border-radius: 999px; transition: width 280ms ease;
  }

  .intro__progress-text {
    font-size: 13px; color: var(--ink-3);
    font-variant-numeric: tabular-nums; white-space: nowrap;
  }

  .intro__reset {
    font-family: var(--sans); font-size: 13px; color: var(--ink-2);
    background: transparent; border: 1px solid var(--rule);
    padding: 8px 16px; border-radius: 999px; cursor: pointer;
    transition: border-color 160ms ease, color 160ms ease;
  }
  .intro__reset:hover { border-color: var(--ink-2); color: var(--ink); }

  .legend {
    margin: 48px 0 28px; display: flex; align-items: center;
    gap: 18px; flex-wrap: wrap; padding: 14px 0;
    border-top: 1px solid var(--rule-soft);
    border-bottom: 1px solid var(--rule-soft);
  }
  .legend__label {
    font-size: 11px; text-transform: uppercase; letter-spacing: 0.18em;
    color: var(--ink-3); margin-right: 4px;
  }
  .legend__items { display: flex; gap: 4px; flex-wrap: wrap; flex: 1 1 auto; }
  .legend__item {
    display: inline-flex; align-items: center; gap: 7px;
    padding: 5px 11px 5px 9px; border-radius: 999px;
    font-family: var(--sans); color: var(--ink-2); font-size: 13.5px;
  }
  .legend__dot {
    width: 8px; height: 8px; border-radius: 50%;
    flex: 0 0 8px; background: var(--ldot);
  }
  .legend__step { font-size: 11px; color: var(--ink-3); font-variant-numeric: tabular-nums; }

  .canvas-wrap {
    width: 100%; overflow-x: auto; overflow-y: hidden; position: relative;
  }
  .canvas-wrap::after {
    content: ''; position: absolute; top: 0; right: 0; bottom: 0;
    width: 48px; background: linear-gradient(to right, transparent, #f5f2ec);
    pointer-events: none;
  }
  @media (min-width: 1540px) { .canvas-wrap::after { display: none; } }

  .canvas {
    position: relative; width: 1480px; height: 900px;
    background: radial-gradient(1200px 600px at 50% 50%, rgba(255,255,255,0.5), transparent 70%), #f5f2ec;
  }
  .canvas-edges {
    position: absolute; inset: 0; width: 100%; height: 100%; pointer-events: none;
  }

  .center-node {
    position: absolute; background: #fff; border: 1px solid #d9d4c8;
    border-radius: 14px; display: flex; flex-direction: column;
    align-items: center; justify-content: center; text-align: center;
    z-index: 3; box-sizing: border-box; padding: 0 16px;
    box-shadow: 0 1px 0 rgba(21,20,15,.02), 0 8px 24px -16px rgba(21,20,15,.18);
  }
  .center-node__title {
    font-family: 'Fraunces', Georgia, serif; font-size: 20px; font-weight: 600;
    letter-spacing: -0.01em; color: #15140f;
  }
  .center-node__sub {
    font-size: 11px; text-transform: uppercase; letter-spacing: 0.18em;
    color: #6f6c64; margin-top: 5px;
  }

  .mn {
    position: absolute; width: 200px; height: 64px;
    background: #fff; border: 1px solid #d9d4c8;
    border-left: 3px solid var(--accent, #ccc); border-radius: 6px;
    display: flex; flex-direction: column; align-items: flex-start;
    justify-content: center; padding: 9px 14px 9px 12px;
    z-index: 2; box-sizing: border-box; cursor: pointer;
    transition: opacity 200ms ease, box-shadow 200ms ease;
  }
  .mn.is-active {
    box-shadow: 0 1px 0 rgba(21,20,15,.04), 0 10px 28px -14px rgba(21,20,15,.22);
  }
  .mn.is-dim { opacity: 0.22; }
  .sn { transition: opacity 200ms ease, border-color 160ms ease; }
  .sn.is-dim { opacity: 0.22; }
  .mn-step {
    position: absolute; top: 6px; right: 10px; font-size: 10px;
    color: #6f6c64; font-variant-numeric: tabular-nums; letter-spacing: 0.1em;
  }
  .mn-t {
    font-family: 'Fraunces', Georgia, serif; font-size: 16px; font-weight: 600;
    color: #15140f; line-height: 1.2; letter-spacing: -0.005em;
  }
  .mn-b { font-size: 12px; margin-top: 3px; color: var(--accent, #999); line-height: 1.2; }

  .sn {
    position: absolute; width: 200px; height: 36px;
    background: #fff; border: 1px solid #d9d4c8;
    border-left: 3px solid var(--accent, #ccc); border-radius: 4px;
    display: flex; align-items: center; gap: 6px; padding: 0 8px 0 7px;
    font-size: 12.5px; color: #3a3833; box-sizing: border-box;
    cursor: pointer; user-select: none; transition: border-color 160ms ease;
  }
  .sn:hover { border-color: color-mix(in oklab, var(--accent) 60%, #d9d4c8); }
  .sn-check {
    width: 14px; height: 14px; border: 1px solid #d9d4c8; border-radius: 3px;
    flex: 0 0 14px; display: flex; align-items: center; justify-content: center;
    font-size: 9px; color: transparent; background: transparent;
    transition: background 160ms ease, border-color 160ms ease, color 160ms ease;
  }
  .sn-check.is-done { background: var(--accent); border-color: var(--accent); color: #fff; }
  .sn-label { overflow: hidden; text-overflow: ellipsis; white-space: nowrap; flex: 1; }

  .post-foot { margin-top: 56px; }
  .post-foot__line { height: 1px; background: var(--rule-soft); margin-bottom: 28px; }
  .post-foot__row {
    display: flex; justify-content: space-between; align-items: flex-end;
    gap: 32px; flex-wrap: wrap;
  }
  .post-foot__label {
    font-size: 11px; text-transform: uppercase; letter-spacing: 0.18em;
    color: var(--ink-3); margin-bottom: 8px;
  }
  .post-foot__name {
    font-family: var(--serif); font-weight: 600; font-size: 18px; color: var(--ink);
  }
  .post-foot__meta { font-size: 13px; color: var(--ink-3); margin-top: 4px; }
  .post-foot__links { display: flex; gap: 20px; }
  .post-foot__links a {
    color: var(--lnk); font-size: 14px; text-decoration: none;
    border-bottom: 1px solid color-mix(in oklab, #2a4cd2 30%, transparent);
    padding-bottom: 1px; transition: border-color 160ms ease;
  }
  .post-foot__links a:hover { border-bottom-color: var(--lnk); }

  /* ── Section nav ─────────────────────────────── */
  .sec-nav {
    margin: 56px 0 0; display: flex; gap: 0; flex-wrap: wrap;
    border-top: 1px solid var(--rule-soft);
    border-bottom: 1px solid var(--rule-soft);
    overflow-x: auto; -webkit-overflow-scrolling: touch;
  }
  .sec-nav__item {
    display: inline-flex; align-items: center; gap: 7px;
    padding: 12px 18px; font-size: 13px; color: var(--ink-3);
    text-decoration: none; white-space: nowrap;
    border-bottom: 2px solid transparent; margin-bottom: -1px;
    transition: color 160ms ease, border-color 160ms ease;
  }
  .sec-nav__item:hover { color: var(--ink); border-bottom-color: var(--ink-4); }
  .sec-nav__dot {
    width: 7px; height: 7px; border-radius: 50%; flex: 0 0 7px;
    background: var(--dot);
  }

  /* ── Skill sections ───────────────────────────── */
  .skill-section {
    max-width: 760px; padding-top: 72px;
  }
  .skill-section__eyebrow {
    font-size: 11px; text-transform: uppercase; letter-spacing: 0.18em;
    color: var(--ink-3); margin-bottom: 16px;
  }
  .skill-section__title {
    font-family: var(--serif); font-weight: 600;
    font-size: clamp(28px, 3.6vw, 42px); line-height: 1.1;
    letter-spacing: -0.015em; color: var(--ink); margin: 0 0 20px;
  }
  .skill-section__lede {
    font-size: 16px; line-height: 1.7; color: var(--ink-2);
    margin: 0 0 36px; border-bottom: 1px solid var(--rule-soft); padding-bottom: 32px;
  }
  .skill-list { display: flex; flex-direction: column; gap: 0; }
  .skill-row {
    display: grid; grid-template-columns: 220px 1fr;
    gap: 0 32px; padding: 20px 0;
    border-bottom: 1px solid var(--rule-soft);
    align-items: baseline;
  }
  .skill-row:last-child { border-bottom: none; }
  .skill-row__name {
    font-size: 14px; font-weight: 500; color: var(--ink);
    padding-right: 16px;
  }
  .skill-row__desc {
    font-size: 14px; line-height: 1.65; color: var(--ink-2);
  }
  .skill-back {
    display: inline-block; margin-top: 36px; font-size: 13px;
    color: var(--ink-3); text-decoration: none;
    transition: color 160ms ease;
  }
  .skill-back:hover { color: var(--ink); }
  @media (max-width: 600px) {
    .skill-row { grid-template-columns: 1fr; gap: 6px 0; }
    .skill-row__name { padding-right: 0; }
  }
</style>

<div class="post">

  <section class="intro">
    <div class="intro__eyebrow">
      <span>BLOG</span>
      <span class="intro__sep">·</span>
      <span>LEARNING ROADMAP</span>
      <span class="intro__sep">·</span>
      <span>2026</span>
    </div>
    <h1 class="intro__title">From Business Analyst<br>to Data Analyst.</h1>
    <p class="intro__lede">A six-stage roadmap I wish I had when I started — what to learn, in what order, and why it matters once you are inside an enterprise data team. Tap any topic to mark it done; your progress is saved on this device.</p>
    <div class="intro__meta">
      <div class="intro__progress">
        <div class="intro__bar"><div class="intro__bar-fill" id="progress-bar"></div></div>
        <span class="intro__progress-text" id="progress-text">0 of 22 topics marked as learned</span>
      </div>
      <button class="intro__reset" id="reset-btn" type="button">Reset progress</button>
    </div>
  </section>

  <div class="legend">
    <span class="legend__label">Stages</span>
    <div class="legend__items">
      <div class="legend__item" style="--ldot:oklch(0.58 0.09 155);"><span class="legend__dot"></span><span class="legend__step">01</span> Data Basics</div>
      <div class="legend__item" style="--ldot:oklch(0.58 0.09 155);"><span class="legend__dot"></span><span class="legend__step">02</span> Analytics</div>
      <div class="legend__item" style="--ldot:oklch(0.58 0.09 245);"><span class="legend__dot"></span><span class="legend__step">03</span> Data Platform</div>
      <div class="legend__item" style="--ldot:oklch(0.58 0.09 305);"><span class="legend__dot"></span><span class="legend__step">04</span> Data Modeling</div>
      <div class="legend__item" style="--ldot:oklch(0.62 0.09 65);"><span class="legend__dot"></span><span class="legend__step">05</span> ETL &amp; ELT</div>
      <div class="legend__item" style="--ldot:oklch(0.58 0.09 305);"><span class="legend__dot"></span><span class="legend__step">06</span> Data Governance</div>
    </div>
  </div>

  <div class="canvas-wrap">
    <div class="canvas" id="mm">
      <svg class="canvas-edges" id="mmsvg" width="1480" height="900"></svg>

      <div class="center-node" style="left:630px;top:412px;width:220px;height:96px;cursor:pointer;" onclick="focusBranch(null)">
        <div class="center-node__title">BA → Data Analyst</div>
        <div class="center-node__sub">Learning Roadmap</div>
      </div>

      <!-- Data Basics -->
      <div class="mn" data-branch="basics" onclick="focusBranch('basics')" style="left:260px;top:148px;--accent:oklch(0.58 0.09 155);"><span class="mn-step">01</span><span class="mn-t">Data Basics</span><span class="mn-b">understand the landscape</span></div>
      <div class="sn" data-branch="basics" style="left:20px;top:62px; --accent:oklch(0.58 0.09 155);" onclick="toggleLeaf('oltp')" ><div class="sn-check" id="c-oltp">✓</div><span class="sn-label">OLTP vs OLAP</span></div>
      <div class="sn" data-branch="basics" style="left:20px;top:129px;--accent:oklch(0.58 0.09 155);" onclick="toggleLeaf('csv')"  ><div class="sn-check" id="c-csv">✓</div><span class="sn-label">Structured (CSV, tables)</span></div>
      <div class="sn" data-branch="basics" style="left:20px;top:195px;--accent:oklch(0.58 0.09 155);" onclick="toggleLeaf('json')" ><div class="sn-check" id="c-json">✓</div><span class="sn-label">Semi-structured (JSON, Parquet)</span></div>
      <div class="sn" data-branch="basics" style="left:20px;top:262px;--accent:oklch(0.58 0.09 155);" onclick="toggleLeaf('docs')" ><div class="sn-check" id="c-docs">✓</div><span class="sn-label">Unstructured (docs, logs)</span></div>

      <!-- Data Platform -->
      <div class="mn" data-branch="platform" onclick="focusBranch('platform')" style="left:260px;top:428px;--accent:oklch(0.58 0.09 245);"><span class="mn-step">03</span><span class="mn-t">Data Platform</span><span class="mn-b">where you practice</span></div>
      <div class="sn" data-branch="platform" style="left:20px;top:360px;--accent:oklch(0.58 0.09 245);" onclick="toggleLeaf('snow')"><div class="sn-check" id="c-snow">✓</div><span class="sn-label">Snowflake</span></div>
      <div class="sn" data-branch="platform" style="left:20px;top:442px;--accent:oklch(0.58 0.09 245);" onclick="toggleLeaf('dbx')" ><div class="sn-check" id="c-dbx">✓</div><span class="sn-label">Databricks</span></div>
      <div class="sn" data-branch="platform" style="left:20px;top:524px;--accent:oklch(0.58 0.09 245);" onclick="toggleLeaf('bq')"  ><div class="sn-check" id="c-bq">✓</div><span class="sn-label">BigQuery</span></div>

      <!-- ETL & ELT -->
      <div class="mn" data-branch="etl" onclick="focusBranch('etl')" style="left:260px;top:708px;--accent:oklch(0.62 0.09 65);"><span class="mn-step">05</span><span class="mn-t">ETL &amp; ELT</span><span class="mn-b">how data moves</span></div>
      <div class="sn" data-branch="etl" style="left:20px;top:640px;--accent:oklch(0.62 0.09 65);" onclick="toggleLeaf('dbt')"><div class="sn-check" id="c-dbt">✓</div><span class="sn-label">dbt</span></div>
      <div class="sn" data-branch="etl" style="left:20px;top:722px;--accent:oklch(0.62 0.09 65);" onclick="toggleLeaf('adf')"><div class="sn-check" id="c-adf">✓</div><span class="sn-label">Azure Data Factory</span></div>
      <div class="sn" data-branch="etl" style="left:20px;top:804px;--accent:oklch(0.62 0.09 65);" onclick="toggleLeaf('air')"><div class="sn-check" id="c-air">✓</div><span class="sn-label">Airflow</span></div>

      <!-- Analytics -->
      <div class="mn" data-branch="analytics" onclick="focusBranch('analytics')" style="left:1020px;top:148px;--accent:oklch(0.58 0.09 155);"><span class="mn-step">02</span><span class="mn-t">Analytics</span><span class="mn-b">learn this first</span></div>
      <div class="sn" data-branch="analytics" style="left:1260px;top:52px; --accent:oklch(0.58 0.09 155);" onclick="toggleLeaf('sql')"   ><div class="sn-check" id="c-sql">✓</div><span class="sn-label">SQL Fundamentals</span></div>
      <div class="sn" data-branch="analytics" style="left:1260px;top:107px;--accent:oklch(0.58 0.09 155);" onclick="toggleLeaf('win')"   ><div class="sn-check" id="c-win">✓</div><span class="sn-label">Window Functions / CTEs</span></div>
      <div class="sn" data-branch="analytics" style="left:1260px;top:162px;--accent:oklch(0.58 0.09 155);" onclick="toggleLeaf('pandas')"><div class="sn-check" id="c-pandas">✓</div><span class="sn-label">Python (Pandas)</span></div>
      <div class="sn" data-branch="analytics" style="left:1260px;top:217px;--accent:oklch(0.58 0.09 155);" onclick="toggleLeaf('stats')" ><div class="sn-check" id="c-stats">✓</div><span class="sn-label">Statistical Thinking</span></div>
      <div class="sn" data-branch="analytics" style="left:1260px;top:272px;--accent:oklch(0.58 0.09 155);" onclick="toggleLeaf('bi')"    ><div class="sn-check" id="c-bi">✓</div><span class="sn-label">Power BI / Tableau</span></div>

      <!-- Data Modeling -->
      <div class="mn" data-branch="modeling" onclick="focusBranch('modeling')" style="left:1020px;top:428px;--accent:oklch(0.58 0.09 305);"><span class="mn-step">04</span><span class="mn-t">Data Modeling</span><span class="mn-b">design skills</span></div>
      <div class="sn" data-branch="modeling" style="left:1260px;top:342px;--accent:oklch(0.58 0.09 305);" onclick="toggleLeaf('norm')" ><div class="sn-check" id="c-norm">✓</div><span class="sn-label">Normalized vs Denormalized</span></div>
      <div class="sn" data-branch="modeling" style="left:1260px;top:409px;--accent:oklch(0.58 0.09 305);" onclick="toggleLeaf('dim')"  ><div class="sn-check" id="c-dim">✓</div><span class="sn-label">Dimensional Modeling</span></div>
      <div class="sn" data-branch="modeling" style="left:1260px;top:475px;--accent:oklch(0.58 0.09 305);" onclick="toggleLeaf('star')" ><div class="sn-check" id="c-star">✓</div><span class="sn-label">Star Schema</span></div>
      <div class="sn" data-branch="modeling" style="left:1260px;top:542px;--accent:oklch(0.58 0.09 305);" onclick="toggleLeaf('snowS')"><div class="sn-check" id="c-snowS">✓</div><span class="sn-label">Snowflake Schema</span></div>

      <!-- Data Governance -->
      <div class="mn" data-branch="gov" onclick="focusBranch('gov')" style="left:1020px;top:708px;--accent:oklch(0.58 0.09 305);"><span class="mn-step">06</span><span class="mn-t">Data Governance</span><span class="mn-b">trust &amp; compliance</span></div>
      <div class="sn" data-branch="gov" style="left:1260px;top:640px;--accent:oklch(0.58 0.09 305);" onclick="toggleLeaf('mdm')" ><div class="sn-check" id="c-mdm">✓</div><span class="sn-label">MDM</span></div>
      <div class="sn" data-branch="gov" style="left:1260px;top:722px;--accent:oklch(0.58 0.09 305);" onclick="toggleLeaf('sec')" ><div class="sn-check" id="c-sec">✓</div><span class="sn-label">Data Security &amp; Privacy</span></div>
      <div class="sn" data-branch="gov" style="left:1260px;top:804px;--accent:oklch(0.58 0.09 305);" onclick="toggleLeaf('qual')"><div class="sn-check" id="c-qual">✓</div><span class="sn-label">Data Quality Framework</span></div>

    </div>
  </div>

  <!-- ── Jump navigation ─────────────────────────── -->
  <nav class="sec-nav" aria-label="Explore stages">
    <a class="sec-nav__item" href="#stage-basics"><span class="sec-nav__dot" style="--dot:oklch(0.58 0.09 155);"></span>Data Basics</a>
    <a class="sec-nav__item" href="#stage-analytics"><span class="sec-nav__dot" style="--dot:oklch(0.58 0.09 155);"></span>Analytics</a>
    <a class="sec-nav__item" href="#stage-platform"><span class="sec-nav__dot" style="--dot:oklch(0.58 0.09 245);"></span>Data Platform</a>
    <a class="sec-nav__item" href="#stage-modeling"><span class="sec-nav__dot" style="--dot:oklch(0.58 0.09 305);"></span>Data Modeling</a>
    <a class="sec-nav__item" href="#stage-etl"><span class="sec-nav__dot" style="--dot:oklch(0.62 0.09 65);"></span>ETL &amp; ELT</a>
    <a class="sec-nav__item" href="#stage-gov"><span class="sec-nav__dot" style="--dot:oklch(0.58 0.09 305);"></span>Data Governance</a>
  </nav>

  <!-- ── 01 Data Basics ─────────────────────────── -->
  <section class="skill-section" id="stage-basics">
    <div class="skill-section__eyebrow">01 · DATA BASICS</div>
    <h2 class="skill-section__title">Data Basics</h2>
    <p class="skill-section__lede">Before you analyze data, you need to understand what shape it comes in and where it lives. These four concepts appear in nearly every data conversation — knowing them helps you ask the right questions from day one.</p>
    <div class="skill-list">
      <div class="skill-row">
        <div class="skill-row__name">OLTP vs OLAP</div>
        <div class="skill-row__desc">OLTP (e.g., Salesforce) databases handle live operations — each write is a fixed type at a fixed position. OLAP (analytical) databases store historical data optimized for aggregated queries. Always ask which one you're querying before you optimize anything; the two behave very differently.</div>
      </div>
      <div class="skill-row">
        <div class="skill-row__name">Structured (CSV, tables)</div>
        <div class="skill-row__desc">Structured data lives in rows and columns — spreadsheets, SQL tables, CSV files. Every field has a fixed type and position. The easiest format to search and work with, and the one analysts do most of their analysis work in.</div>
      </div>
      <div class="skill-row">
        <div class="skill-row__name">Semi-structured (JSON, Parquet)</div>
        <div class="skill-row__desc">Semi-structured: flexible structure with key-value pairs. JSON (APIs, event logs), Parquet (the data-warehouse pivot format). Has fields and values, but the structure can vary between records — you cannot treat it like a CSV until you parse it.</div>
      </div>
      <div class="skill-row">
        <div class="skill-row__name">Unstructured (docs, logs)</div>
        <div class="skill-row__desc">Raw: free text, logs, images, PDFs. No fixed schema. Requires significant pre-processing — usually NLP or ML — before it becomes usable for analysis.</div>
      </div>
    </div>
    <a class="skill-back" href="#mm">↑ Back to map</a>
  </section>

  <!-- ── 02 Analytics ───────────────────────────── -->
  <section class="skill-section" id="stage-analytics">
    <div class="skill-section__eyebrow">02 · ANALYTICS</div>
    <h2 class="skill-section__title">Analytics</h2>
    <p class="skill-section__lede">This is the core toolkit. SQL is the language of data — nothing else matters as much in day-to-day work. You don't need to be a data engineer, but you do need to be able to answer questions yourself without depending on others for every query.</p>
    <div class="skill-list">
      <div class="skill-row">
        <div class="skill-row__name">SQL Fundamentals</div>
        <div class="skill-row__desc">SELECT, FROM, WHERE, JOIN, GROUP BY, row aggregates — the core of analytics work. You cannot do this without it. Know it well and don't rely on someone else for every query.</div>
      </div>
      <div class="skill-row">
        <div class="skill-row__name">Window Functions / CTEs</div>
        <div class="skill-row__desc">Window functions calculate rankings, running totals, and moving averages without collapsing your data. CTEs (WITH clause) break complex queries into readable, sequential steps. Together they replace most subquery spaghetti.</div>
      </div>
      <div class="skill-row">
        <div class="skill-row__name">Python (Pandas)</div>
        <div class="skill-row__desc">Python specifically for loading and reshaping data. Not for ML pipelines. Pandas puts you one <code>read_csv()</code> away from a full DataFrame so you can quickly inspect it, then pass you to a much stronger position alongside familiar BI tooling.</div>
      </div>
      <div class="skill-row">
        <div class="skill-row__name">Statistical Thinking</div>
        <div class="skill-row__desc">Mean, median, distribution, correlation. SQL tells you what the data says; statistics helps you understand whether that answer is meaningful. Understanding variation prevents you from drawing too much insight from noise.</div>
      </div>
      <div class="skill-row">
        <div class="skill-row__name">Power BI / Tableau</div>
        <div class="skill-row__desc">Knowing how to build a dashboard and tell the underlying data story. The goal is decision-making findings, not just charts. Pick one tool and go deep — breadth here matters less than depth.</div>
      </div>
    </div>
    <a class="skill-back" href="#mm">↑ Back to map</a>
  </section>

  <!-- ── 03 Data Platform ───────────────────────── -->
  <section class="skill-section" id="stage-platform">
    <div class="skill-section__eyebrow">03 · DATA PLATFORM</div>
    <h2 class="skill-section__title">Data Platform</h2>
    <p class="skill-section__lede">The cloud warehouses are where you will spend most of your time querying and building. You don't need to administer them — but knowing their architecture helps you write better queries and ask smarter questions of the engineers around you.</p>
    <div class="skill-list">
      <div class="skill-row">
        <div class="skill-row__name">Snowflake</div>
        <div class="skill-row__desc">A cloud data warehouse purpose-built for analytics. Separates storage and compute so teams can scale independently. The most common place BAs find themselves querying production data in enterprise environments.</div>
      </div>
      <div class="skill-row">
        <div class="skill-row__name">Databricks</div>
        <div class="skill-row__desc">A Lakehouse platform built on Apache Spark, purpose-built for data engineering and ML pipelines. Increasingly the engine behind enterprise data transformations — if your company has a large data science team, you will encounter it.</div>
      </div>
      <div class="skill-row">
        <div class="skill-row__name">BigQuery</div>
        <div class="skill-row__desc">Google's serverless analytics warehouse. Pay-per-query pricing and native integration with GCP services. Often the entry point for teams already invested in Google Workspace or using Google Analytics data.</div>
      </div>
    </div>
    <a class="skill-back" href="#mm">↑ Back to map</a>
  </section>

  <!-- ── 04 Data Modeling ───────────────────────── -->
  <section class="skill-section" id="stage-modeling">
    <div class="skill-section__eyebrow">04 · DATA MODELING</div>
    <h2 class="skill-section__title">Data Modeling</h2>
    <p class="skill-section__lede">Data modeling is how analysts and engineers agree on what the data means before it's built. Getting this wrong makes every downstream report inconsistent. Getting it right makes the warehouse easy to query for years.</p>
    <div class="skill-list">
      <div class="skill-row">
        <div class="skill-row__name">Normalized vs Denormalized</div>
        <div class="skill-row__desc">Normalization removes data redundancy by splitting tables; denormalization trades storage for query speed. Knowing when to apply which is a core design decision that determines how easy — or painful — your data is to query downstream.</div>
      </div>
      <div class="skill-row">
        <div class="skill-row__name">Dimensional Modeling</div>
        <div class="skill-row__desc">A technique for organizing data warehouses into fact tables (measurements) and dimension tables (context). It is the standard mental model for analytical databases — understanding this unlocks how real enterprise data is structured and why.</div>
      </div>
      <div class="skill-row">
        <div class="skill-row__name">Star Schema</div>
        <div class="skill-row__desc">The simplest dimensional model: one fact table in the centre, dimension tables radiating outward. Easy to query, easy to explain to stakeholders, and what most BI tools are optimized to consume.</div>
      </div>
      <div class="skill-row">
        <div class="skill-row__name">Snowflake Schema</div>
        <div class="skill-row__desc">An extension of the star schema where dimension tables are further normalized. More storage-efficient but more complex to query. Knowing when to choose one over the other separates junior data analysts from senior ones.</div>
      </div>
    </div>
    <a class="skill-back" href="#mm">↑ Back to map</a>
  </section>

  <!-- ── 05 ETL & ELT ───────────────────────────── -->
  <section class="skill-section" id="stage-etl">
    <div class="skill-section__eyebrow">05 · ETL &amp; ELT</div>
    <h2 class="skill-section__title">ETL &amp; ELT</h2>
    <p class="skill-section__lede">Data doesn't arrive analysis-ready. Understanding how it moves — from source systems into the warehouse — helps you trace data quality issues, contribute to pipeline design conversations, and avoid requesting reports built on broken data.</p>
    <div class="skill-list">
      <div class="skill-row">
        <div class="skill-row__name">dbt</div>
        <div class="skill-row__desc">The de-facto tool for transforming raw data into analytics-ready models, in SQL. Version-controlled data transformations with built-in testing and documentation. If your team isn't using dbt, someone is spending time solving a problem it has already solved.</div>
      </div>
      <div class="skill-row">
        <div class="skill-row__name">Azure Data Factory</div>
        <div class="skill-row__desc">Microsoft's cloud ETL service for ingesting and moving data at scale. The standard connector between source systems and the warehouse in most enterprise Microsoft stacks. Knowing it means you can trace where data comes from without asking an engineer every time.</div>
      </div>
      <div class="skill-row">
        <div class="skill-row__name">Airflow</div>
        <div class="skill-row__desc">An orchestration platform that schedules and monitors data pipelines as code. When pipelines grow complex enough that "run this after that finishes" needs to be reliable and auditable, Airflow is the standard choice.</div>
      </div>
    </div>
    <a class="skill-back" href="#mm">↑ Back to map</a>
  </section>

  <!-- ── 06 Data Governance ─────────────────────── -->
  <section class="skill-section" id="stage-gov">
    <div class="skill-section__eyebrow">06 · DATA GOVERNANCE</div>
    <h2 class="skill-section__title">Data Governance</h2>
    <p class="skill-section__lede">Trust is slow to build and fast to lose. Governance is the set of practices that keeps data trustworthy — who can access it, what it means, and how good it is. In enterprise environments, this is non-negotiable from day one.</p>
    <div class="skill-list">
      <div class="skill-row">
        <div class="skill-row__name">MDM</div>
        <div class="skill-row__desc">Master Data Management — the practice of creating a single, authoritative record for key business entities (customers, products, accounts). Without MDM, "customer count" returns a different number in every system, and every report becomes a negotiation.</div>
      </div>
      <div class="skill-row">
        <div class="skill-row__name">Data Security &amp; Privacy</div>
        <div class="skill-row__desc">Defining who can see what, how long sensitive data is retained, and how it is classified. GDPR, CCPA, and internal compliance policies all fall here. Non-negotiable in any regulated industry — and increasingly standard everywhere else.</div>
      </div>
      <div class="skill-row">
        <div class="skill-row__name">Data Quality Framework</div>
        <div class="skill-row__desc">The systematic process for measuring, monitoring, and improving data quality — completeness, accuracy, consistency, timeliness. Bad data is the most common reason analytics projects lose stakeholder trust long before the insight is ever acted on.</div>
      </div>
    </div>
    <a class="skill-back" href="#mm">↑ Back to map</a>
  </section>

  <footer class="post-foot">
    <div class="post-foot__line"></div>
    <div class="post-foot__row">
      <div>
        <div class="post-foot__label">Written by</div>
        <div class="post-foot__name">Dzianis Kuziomkin</div>
        <div class="post-foot__meta">Lead BA Analyst · CBAP &amp; CBDA · 8 years in enterprise data</div>
      </div>
      <div class="post-foot__links">
        <a href="/">→ Read the full essay</a>
        <a href="https://www.linkedin.com/in/dzianis-kuziomkin/" target="_blank" rel="noopener">→ Discuss on LinkedIn</a>
      </div>
    </div>
  </footer>

</div>

<script>
(function () {
  const svg = document.getElementById('mmsvg');
  function c(x1, y1, x2, y2, col, w, op) {
    const mx = (x1 + x2) / 2;
    const p = document.createElementNS('http://www.w3.org/2000/svg', 'path');
    p.setAttribute('d', `M${x1} ${y1} C${mx} ${y1},${mx} ${y2},${x2} ${y2}`);
    p.setAttribute('stroke', col);
    p.setAttribute('stroke-width', String(w || 2));
    p.setAttribute('fill', 'none');
    p.setAttribute('stroke-linecap', 'round');
    p.setAttribute('opacity', String(op || 0.65));
    svg.appendChild(p);
  }
  const CL = 630, CR = 850, CY = 460;
  c(CL,CY, 460, 180, 'oklch(0.58 0.09 155)', 2, 0.7);
  c(CL,CY, 460, 460, 'oklch(0.58 0.09 245)', 2, 0.7);
  c(CL,CY, 460, 740, 'oklch(0.62 0.09 65)',  2, 0.7);
  c(CR,CY, 1020,180, 'oklch(0.58 0.09 155)', 2, 0.7);
  c(CR,CY, 1020,460, 'oklch(0.58 0.09 305)', 2, 0.7);
  c(CR,CY, 1020,740, 'oklch(0.58 0.09 305)', 2, 0.7);
  [80,147,213,280].forEach(y => c(260,180, 220,y, 'oklch(0.58 0.09 155)', 1, 0.4));
  [378,460,542].forEach(y    => c(260,460, 220,y, 'oklch(0.58 0.09 245)', 1, 0.4));
  [658,740,822].forEach(y    => c(260,740, 220,y, 'oklch(0.62 0.09 65)',  1, 0.4));
  [70,125,180,235,290].forEach(y => c(1220,180, 1260,y, 'oklch(0.58 0.09 155)', 1, 0.4));
  [360,427,493,560].forEach(y    => c(1220,460, 1260,y, 'oklch(0.58 0.09 305)', 1, 0.4));
  [658,740,822].forEach(y        => c(1220,740, 1260,y, 'oklch(0.58 0.09 305)', 1, 0.4));
})();

function focusBranch(branch) {
  document.querySelectorAll('.mn, .sn').forEach(el => {
    if (!branch) { el.classList.remove('is-active','is-dim'); return; }
    const b = el.dataset.branch;
    if (b === branch) { el.classList.add('is-active'); el.classList.remove('is-dim'); }
    else              { el.classList.add('is-dim');    el.classList.remove('is-active'); }
  });
  if (branch) {
    const map = { basics:'stage-basics', analytics:'stage-analytics', platform:'stage-platform', modeling:'stage-modeling', etl:'stage-etl', gov:'stage-gov' };
    const target = document.getElementById(map[branch]);
    if (target) target.scrollIntoView({ behavior:'smooth', block:'start' });
  }
}

const TOTAL = 22;
const STORE_KEY = 'ba-to-data-done';
const done = new Set(JSON.parse(localStorage.getItem(STORE_KEY) || '[]'));

function refreshProgress() {
  const n = done.size;
  document.getElementById('progress-bar').style.width = `${(n / TOTAL) * 100}%`;
  document.getElementById('progress-text').textContent = `${n} of ${TOTAL} topics marked as learned`;
}

function toggleLeaf(id) {
  const el = document.getElementById('c-' + id);
  if (!el) return;
  if (done.has(id)) { done.delete(id); el.classList.remove('is-done'); }
  else              { done.add(id);    el.classList.add('is-done'); }
  localStorage.setItem(STORE_KEY, JSON.stringify([...done]));
  refreshProgress();
}

document.getElementById('reset-btn').addEventListener('click', () => {
  done.clear();
  localStorage.removeItem(STORE_KEY);
  document.querySelectorAll('.sn-check').forEach(el => el.classList.remove('is-done'));
  refreshProgress();
});

done.forEach(id => { const el = document.getElementById('c-' + id); if (el) el.classList.add('is-done'); });
refreshProgress();
</script>
