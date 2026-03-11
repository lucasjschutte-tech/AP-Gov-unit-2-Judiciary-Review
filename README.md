<!DOCTYPE html>
<html lang="en">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>AP Gov Unit 2 · The Judiciary</title>
<link href="https://fonts.googleapis.com/css2?family=Playfair+Display:wght@700;900&family=IBM+Plex+Mono:wght@400;600&family=Source+Serif+4:ital,wght@0,300;0,400;1,300&display=swap" rel="stylesheet">
<style>
  :root {
    --ink: #0f0e0c;
    --parchment: #f5f0e8;
    --cream: #faf7f2;
    --gold: #c9973a;
    --gold-light: #e8c97a;
    --red: #8b2020;
    --blue: #1a3a5c;
    --blue-light: #2e5f8a;
    --muted: #7a7060;
    --border: #d4c9b0;
    --module-1: #1a3a5c;
    --module-2: #2d5a27;
    --module-3: #6b2020;
    --module-4: #4a2d6b;
    --module-5: #5a3a0d;
  }

  * { box-sizing: border-box; margin: 0; padding: 0; }

  body {
    background: var(--cream);
    color: var(--ink);
    font-family: 'Source Serif 4', Georgia, serif;
    min-height: 100vh;
  }

  /* MASTHEAD */
  .masthead {
    background: var(--ink);
    color: var(--parchment);
    padding: 0;
    border-bottom: 3px solid var(--gold);
    position: relative;
    overflow: hidden;
  }

  .masthead::before {
    content: '';
    position: absolute;
    inset: 0;
    background: 
      repeating-linear-gradient(0deg, transparent, transparent 40px, rgba(201,151,58,0.04) 40px, rgba(201,151,58,0.04) 41px),
      repeating-linear-gradient(90deg, transparent, transparent 40px, rgba(201,151,58,0.04) 40px, rgba(201,151,58,0.04) 41px);
    pointer-events: none;
  }

  .masthead-inner {
    max-width: 1100px;
    margin: 0 auto;
    padding: 32px 40px 28px;
  }

  .masthead-label {
    font-family: 'IBM Plex Mono', monospace;
    font-size: 10px;
    letter-spacing: 0.25em;
    color: var(--gold);
    text-transform: uppercase;
    margin-bottom: 10px;
  }

  .masthead-title {
    font-family: 'Playfair Display', serif;
    font-size: clamp(32px, 5vw, 52px);
    font-weight: 900;
    line-height: 1.05;
    color: var(--parchment);
    margin-bottom: 8px;
  }

  .masthead-title span {
    color: var(--gold-light);
  }

  .masthead-sub {
    font-family: 'Source Serif 4', serif;
    font-style: italic;
    font-weight: 300;
    font-size: 15px;
    color: #a09880;
    letter-spacing: 0.02em;
  }

  .masthead-meta {
    display: flex;
    gap: 24px;
    margin-top: 20px;
    flex-wrap: wrap;
  }

  .meta-pill {
    font-family: 'IBM Plex Mono', monospace;
    font-size: 10px;
    letter-spacing: 0.15em;
    color: var(--gold);
    border: 1px solid rgba(201,151,58,0.4);
    padding: 4px 10px;
    text-transform: uppercase;
  }

  /* PROGRESS BAR */
  .progress-bar-wrap {
    background: var(--ink);
    padding: 0 40px 16px;
    max-width: 1100px;
    margin: 0 auto;
  }

  .progress-track {
    height: 3px;
    background: rgba(255,255,255,0.1);
    border-radius: 0;
    overflow: visible;
    position: relative;
  }

  .progress-fill {
    height: 100%;
    background: linear-gradient(90deg, var(--gold), var(--gold-light));
    transition: width 0.5s ease;
    position: relative;
  }

  .progress-text {
    font-family: 'IBM Plex Mono', monospace;
    font-size: 10px;
    color: var(--muted);
    margin-top: 6px;
    letter-spacing: 0.1em;
  }

  /* LAYOUT */
  .layout {
    max-width: 1100px;
    margin: 0 auto;
    padding: 40px 40px 80px;
    display: grid;
    grid-template-columns: 260px 1fr;
    gap: 40px;
    align-items: start;
  }

  /* SIDEBAR */
  .sidebar {
    position: sticky;
    top: 24px;
  }

  .sidebar-label {
    font-family: 'IBM Plex Mono', monospace;
    font-size: 10px;
    letter-spacing: 0.2em;
    color: var(--muted);
    text-transform: uppercase;
    margin-bottom: 12px;
  }

  .module-nav {
    list-style: none;
    display: flex;
    flex-direction: column;
    gap: 4px;
  }

  .module-nav-item {
    cursor: pointer;
    border: 1px solid transparent;
    transition: all 0.2s;
    position: relative;
  }

  .module-nav-item:hover .nav-inner {
    background: white;
    border-color: var(--border);
  }

  .module-nav-item.active .nav-inner {
    background: white;
    border-left: 3px solid var(--gold);
    box-shadow: 2px 2px 12px rgba(0,0,0,0.06);
  }

  .nav-inner {
    padding: 12px 14px;
    border: 1px solid var(--border);
    transition: all 0.2s;
    background: transparent;
  }

  .nav-number {
    font-family: 'IBM Plex Mono', monospace;
    font-size: 9px;
    letter-spacing: 0.15em;
    margin-bottom: 3px;
  }

  .nav-title {
    font-family: 'Playfair Display', serif;
    font-size: 13px;
    font-weight: 700;
    line-height: 1.2;
  }

  .nav-status {
    font-family: 'IBM Plex Mono', monospace;
    font-size: 9px;
    margin-top: 4px;
    letter-spacing: 0.1em;
  }

  .status-dot {
    display: inline-block;
    width: 6px;
    height: 6px;
    border-radius: 50%;
    margin-right: 5px;
    vertical-align: middle;
  }

  /* MAIN CONTENT */
  .content {
    min-width: 0;
  }

  .module-card {
    display: none;
    animation: fadeSlide 0.3s ease;
  }

  .module-card.visible {
    display: block;
  }

  @keyframes fadeSlide {
    from { opacity: 0; transform: translateY(8px); }
    to { opacity: 1; transform: translateY(0); }
  }

  .card-header {
    padding: 28px 32px;
    margin-bottom: 0;
    position: relative;
    overflow: hidden;
  }

  .card-header::after {
    content: '';
    position: absolute;
    right: -20px;
    top: -20px;
    width: 120px;
    height: 120px;
    border-radius: 50%;
    background: rgba(255,255,255,0.07);
  }

  .card-eyebrow {
    font-family: 'IBM Plex Mono', monospace;
    font-size: 10px;
    letter-spacing: 0.25em;
    text-transform: uppercase;
    color: rgba(255,255,255,0.6);
    margin-bottom: 8px;
  }

  .card-title {
    font-family: 'Playfair Display', serif;
    font-size: 28px;
    font-weight: 900;
    color: white;
    line-height: 1.15;
    margin-bottom: 6px;
  }

  .card-subtitle {
    font-family: 'Source Serif 4', serif;
    font-style: italic;
    font-size: 14px;
    color: rgba(255,255,255,0.7);
  }

  /* TABS */
  .tab-row {
    display: flex;
    gap: 0;
    border-bottom: 2px solid var(--border);
    background: white;
    flex-wrap: wrap;
  }

  .tab-btn {
    font-family: 'IBM Plex Mono', monospace;
    font-size: 11px;
    letter-spacing: 0.12em;
    text-transform: uppercase;
    padding: 12px 20px;
    border: none;
    background: transparent;
    color: var(--muted);
    cursor: pointer;
    border-bottom: 2px solid transparent;
    margin-bottom: -2px;
    transition: all 0.15s;
  }

  .tab-btn:hover {
    color: var(--ink);
    background: var(--cream);
  }

  .tab-btn.active {
    color: var(--ink);
    border-bottom-color: var(--gold);
    background: white;
  }

  /* TAB PANELS */
  .tab-panel {
    display: none;
    background: white;
    padding: 28px 32px;
  }

  .tab-panel.active {
    display: block;
    animation: fadeSlide 0.2s ease;
  }

  /* OVERVIEW */
  .overview-grid {
    display: grid;
    grid-template-columns: 1fr 1fr;
    gap: 20px;
    margin-bottom: 24px;
  }

  .overview-box {
    border: 1px solid var(--border);
    padding: 16px 20px;
    background: var(--cream);
  }

  .overview-box-label {
    font-family: 'IBM Plex Mono', monospace;
    font-size: 9px;
    letter-spacing: 0.2em;
    color: var(--muted);
    text-transform: uppercase;
    margin-bottom: 8px;
  }

  .big-idea {
    font-family: 'Source Serif 4', serif;
    font-size: 14px;
    line-height: 1.6;
    color: var(--ink);
  }

  .vocab-chips {
    display: flex;
    flex-wrap: wrap;
    gap: 8px;
    margin-top: 8px;
  }

  .vocab-chip {
    font-family: 'IBM Plex Mono', monospace;
    font-size: 10px;
    padding: 4px 10px;
    background: var(--ink);
    color: var(--parchment);
    letter-spacing: 0.05em;
    cursor: pointer;
    position: relative;
    border-bottom: 2px solid transparent;
    transition: background 0.15s, border-color 0.15s;
    user-select: none;
  }

  .vocab-chip:hover {
    background: #2a2520;
    border-bottom-color: var(--gold);
  }

  .vocab-chip.active {
    background: var(--gold);
    color: var(--ink);
    border-bottom-color: transparent;
  }

  .vocab-chip::after {
    content: ' ▾';
    font-size: 8px;
    opacity: 0.6;
  }

  .vocab-chip.active::after {
    content: ' ▴';
  }

  /* VOCAB DEFINITION POPOUT */
  .vocab-definition {
    display: none;
    width: 100%;
    margin-top: 10px;
    background: white;
    border: 1px solid var(--border);
    border-left: 3px solid var(--gold);
    padding: 12px 16px;
    animation: fadeSlide 0.18s ease;
  }

  .vocab-definition.show {
    display: block;
  }

  .vocab-def-term {
    font-family: 'Playfair Display', serif;
    font-size: 14px;
    font-weight: 700;
    color: var(--ink);
    margin-bottom: 4px;
  }

  .vocab-def-text {
    font-family: 'Source Serif 4', serif;
    font-size: 13px;
    line-height: 1.65;
    color: #2a2520;
  }

  .vocab-def-example {
    font-family: 'Source Serif 4', serif;
    font-style: italic;
    font-size: 12px;
    color: var(--muted);
    margin-top: 5px;
  }

  .essential-qs {
    list-style: none;
    display: flex;
    flex-direction: column;
    gap: 10px;
  }

  .essential-qs li {
    font-family: 'Source Serif 4', serif;
    font-style: italic;
    font-size: 14px;
    line-height: 1.5;
    padding-left: 20px;
    position: relative;
    color: var(--ink);
  }

  .essential-qs li::before {
    content: '?';
    position: absolute;
    left: 0;
    font-family: 'Playfair Display', serif;
    font-weight: 700;
    color: var(--gold);
    font-style: normal;
  }

  /* CLICKABLE ESSENTIAL QUESTIONS */
  .eq-item {
    cursor: pointer;
    padding: 8px 10px 8px 24px !important;
    border: 1px solid transparent;
    transition: background 0.15s, border-color 0.15s;
    border-radius: 0;
  }

  .eq-item:hover {
    background: #fffbf2;
    border-color: var(--border) !important;
  }

  .eq-item.open {
    background: #fffbf2;
    border-color: var(--gold) !important;
  }

  .eq-item::after {
    content: ' ▾';
    font-style: normal;
    font-size: 10px;
    color: var(--gold);
    margin-left: 4px;
  }

  .eq-item.open::after {
    content: ' ▴';
  }

  .eq-answer {
    display: none;
    margin-top: 10px;
    padding: 12px 14px;
    background: white;
    border-left: 3px solid var(--gold);
    font-style: normal;
    font-size: 13px;
    line-height: 1.7;
    color: #2a2520;
    font-family: 'Source Serif 4', serif;
    animation: fadeSlide 0.18s ease;
  }

  .eq-answer.show {
    display: block;
  }

  /* CONTENT TEXT */
  .content-section {
    margin-bottom: 24px;
  }

  .content-section h3 {
    font-family: 'Playfair Display', serif;
    font-size: 17px;
    font-weight: 700;
    margin-bottom: 10px;
    padding-bottom: 6px;
    border-bottom: 1px solid var(--border);
    color: var(--ink);
  }

  .content-section p {
    font-size: 14px;
    line-height: 1.75;
    color: #2a2520;
    margin-bottom: 10px;
  }

  .callout {
    border-left: 3px solid var(--gold);
    background: #fffbf2;
    padding: 14px 18px;
    margin: 16px 0;
    font-size: 13.5px;
    line-height: 1.65;
    font-style: italic;
    color: var(--ink);
  }

  .callout strong {
    font-style: normal;
    font-family: 'IBM Plex Mono', monospace;
    font-size: 11px;
    letter-spacing: 0.1em;
    color: var(--gold);
    text-transform: uppercase;
    display: block;
    margin-bottom: 4px;
  }

  .two-col {
    display: grid;
    grid-template-columns: 1fr 1fr;
    gap: 16px;
    margin: 16px 0;
  }

  .mini-card {
    border: 1px solid var(--border);
    padding: 14px 16px;
    background: var(--cream);
  }

  .mini-card-title {
    font-family: 'Playfair Display', serif;
    font-size: 14px;
    font-weight: 700;
    margin-bottom: 8px;
  }

  .mini-card ul {
    list-style: none;
    display: flex;
    flex-direction: column;
    gap: 5px;
  }

  .mini-card ul li {
    font-size: 12.5px;
    line-height: 1.4;
    padding-left: 14px;
    position: relative;
    color: #2a2520;
  }

  .mini-card ul li::before {
    content: '—';
    position: absolute;
    left: 0;
    color: var(--muted);
    font-size: 11px;
  }

  /* CASES TABLE */
  .cases-table {
    width: 100%;
    border-collapse: collapse;
    font-size: 13px;
    margin-top: 12px;
  }

  .cases-table th {
    font-family: 'IBM Plex Mono', monospace;
    font-size: 9px;
    letter-spacing: 0.15em;
    text-transform: uppercase;
    background: var(--ink);
    color: var(--gold);
    padding: 10px 14px;
    text-align: left;
  }

  .cases-table td {
    padding: 11px 14px;
    border-bottom: 1px solid var(--border);
    vertical-align: top;
    line-height: 1.45;
  }

  .cases-table tr:nth-child(even) td {
    background: var(--cream);
  }

  .case-name {
    font-family: 'Source Serif 4', serif;
    font-style: italic;
    font-weight: 400;
    color: var(--blue);
  }

  .significance-tag {
    display: inline-block;
    font-family: 'IBM Plex Mono', monospace;
    font-size: 9px;
    padding: 2px 7px;
    letter-spacing: 0.1em;
    text-transform: uppercase;
    margin-top: 4px;
  }

  /* QUIZ */
  .quiz-container {
    display: flex;
    flex-direction: column;
    gap: 24px;
  }

  .quiz-q {
    border: 1px solid var(--border);
    background: var(--cream);
    overflow: hidden;
  }

  .quiz-q-text {
    padding: 16px 20px;
    font-size: 14px;
    line-height: 1.6;
    color: var(--ink);
    border-bottom: 1px solid var(--border);
    background: white;
    font-family: 'Source Serif 4', serif;
  }

  .quiz-q-num {
    font-family: 'IBM Plex Mono', monospace;
    font-size: 10px;
    color: var(--muted);
    margin-bottom: 4px;
    letter-spacing: 0.1em;
  }

  .quiz-choices {
    padding: 14px 20px;
    display: flex;
    flex-direction: column;
    gap: 8px;
  }

  .quiz-choice {
    display: flex;
    align-items: flex-start;
    gap: 10px;
    cursor: pointer;
    padding: 10px 12px;
    border: 1px solid transparent;
    transition: all 0.15s;
    background: white;
    font-size: 13.5px;
    line-height: 1.4;
    font-family: 'Source Serif 4', serif;
    text-align: left;
    width: 100%;
    border-radius: 0;
  }

  .quiz-choice:hover:not(.locked) {
    border-color: var(--border);
    background: #fffdf8;
  }

  .quiz-choice.selected { border-color: var(--blue); background: #f0f5fa; }
  .quiz-choice.correct { border-color: #2d7a27; background: #f0f8f0; }
  .quiz-choice.incorrect { border-color: var(--red); background: #fdf0f0; }

  .choice-letter {
    font-family: 'IBM Plex Mono', monospace;
    font-size: 11px;
    font-weight: 600;
    color: var(--muted);
    min-width: 18px;
    padding-top: 1px;
  }

  .quiz-choice.correct .choice-letter { color: #2d7a27; }
  .quiz-choice.incorrect .choice-letter { color: var(--red); }

  .quiz-feedback {
    display: none;
    padding: 12px 20px;
    font-size: 13px;
    line-height: 1.5;
    border-top: 1px solid var(--border);
    font-family: 'Source Serif 4', serif;
  }

  .quiz-feedback.show { display: block; }
  .quiz-feedback.correct-fb { background: #f0f8f0; color: #1a4a17; }
  .quiz-feedback.incorrect-fb { background: #fdf0f0; color: #6b1515; }

  .quiz-submit-row {
    padding: 0 20px 16px;
  }

  .btn-primary {
    font-family: 'IBM Plex Mono', monospace;
    font-size: 11px;
    letter-spacing: 0.15em;
    text-transform: uppercase;
    padding: 10px 20px;
    background: var(--ink);
    color: var(--parchment);
    border: none;
    cursor: pointer;
    transition: all 0.15s;
  }

  .btn-primary:hover { background: #2a2520; }
  .btn-primary:disabled { opacity: 0.4; cursor: not-allowed; }

  .btn-secondary {
    font-family: 'IBM Plex Mono', monospace;
    font-size: 11px;
    letter-spacing: 0.15em;
    text-transform: uppercase;
    padding: 10px 20px;
    background: white;
    color: var(--ink);
    border: 1px solid var(--border);
    cursor: pointer;
    transition: all 0.15s;
    margin-left: 8px;
  }

  .btn-secondary:hover { background: var(--cream); }

  /* COMPLETE BUTTON */
  .complete-section {
    margin-top: 28px;
    padding-top: 20px;
    border-top: 1px solid var(--border);
    display: flex;
    align-items: center;
    gap: 16px;
    flex-wrap: wrap;
  }

  .complete-btn {
    font-family: 'IBM Plex Mono', monospace;
    font-size: 11px;
    letter-spacing: 0.15em;
    text-transform: uppercase;
    padding: 12px 24px;
    border: 2px solid var(--gold);
    background: transparent;
    color: var(--gold);
    cursor: pointer;
    transition: all 0.2s;
  }

  .complete-btn:hover {
    background: var(--gold);
    color: white;
  }

  .complete-btn.done {
    background: var(--gold);
    color: white;
    cursor: default;
  }

  .complete-note {
    font-family: 'IBM Plex Mono', monospace;
    font-size: 10px;
    color: var(--muted);
    letter-spacing: 0.08em;
  }

  /* SCORE DISPLAY */
  .score-badge {
    display: none;
    font-family: 'IBM Plex Mono', monospace;
    font-size: 11px;
    letter-spacing: 0.1em;
    padding: 8px 14px;
    border: 1px solid var(--border);
    background: var(--cream);
    color: var(--ink);
  }

  .score-badge.show { display: inline-block; }

  /* NAV ARROWS */
  .nav-arrows {
    display: flex;
    gap: 10px;
    margin-top: 8px;
  }

  .nav-arrow {
    font-family: 'IBM Plex Mono', monospace;
    font-size: 11px;
    letter-spacing: 0.12em;
    text-transform: uppercase;
    padding: 10px 18px;
    border: 1px solid var(--border);
    background: white;
    cursor: pointer;
    transition: all 0.15s;
    color: var(--ink);
  }

  .nav-arrow:hover { background: var(--ink); color: var(--parchment); border-color: var(--ink); }

  /* FRQTYPE */
  .frq-prompt {
    background: var(--ink);
    color: var(--parchment);
    padding: 20px 24px;
    font-size: 14px;
    line-height: 1.7;
    font-family: 'Source Serif 4', serif;
    margin-bottom: 16px;
  }

  .frq-part {
    border: 1px solid var(--border);
    padding: 14px 18px;
    margin-bottom: 12px;
    background: var(--cream);
  }

  .frq-part-label {
    font-family: 'IBM Plex Mono', monospace;
    font-size: 10px;
    letter-spacing: 0.15em;
    color: var(--gold);
    text-transform: uppercase;
    margin-bottom: 6px;
  }

  .frq-part-q {
    font-size: 13.5px;
    line-height: 1.6;
    margin-bottom: 8px;
    font-family: 'Source Serif 4', serif;
  }

  .frq-toggle {
    font-family: 'IBM Plex Mono', monospace;
    font-size: 10px;
    letter-spacing: 0.1em;
    text-transform: uppercase;
    color: var(--blue);
    background: none;
    border: none;
    cursor: pointer;
    padding: 0;
    text-decoration: underline;
  }

  .frq-answer {
    display: none;
    margin-top: 8px;
    padding: 10px 14px;
    background: white;
    border: 1px solid var(--border);
    font-size: 13px;
    line-height: 1.6;
    font-family: 'Source Serif 4', serif;
    color: #1a3a1a;
  }

  .frq-answer.show { display: block; }

  @media (max-width: 768px) {
    .layout { grid-template-columns: 1fr; padding: 20px; }
    .sidebar { position: static; }
    .overview-grid, .two-col { grid-template-columns: 1fr; }
    .masthead-inner { padding: 20px; }
  }

  /* FRQ GRADER */
  .frq-select-btn {
    font-family: 'IBM Plex Mono', monospace;
    font-size: 10px;
    letter-spacing: 0.1em;
    text-transform: uppercase;
    padding: 7px 14px;
    border: 1px solid var(--border);
    background: white;
    color: var(--muted);
    cursor: pointer;
    transition: all 0.15s;
  }
  .frq-select-btn:hover { background: var(--cream); color: var(--ink); }
  .frq-select-btn.active { background: #b5540a; color: white; border-color: #b5540a; }

  .frq-score-box {
    border: 1px solid var(--border);
    padding: 12px 16px;
    text-align: center;
    min-width: 90px;
    background: var(--cream);
  }
  .frq-score-box .score-num {
    font-family: 'Playfair Display', serif;
    font-size: 26px;
    font-weight: 900;
    color: var(--ink);
    line-height: 1;
  }
  .frq-score-box .score-label {
    font-family: 'IBM Plex Mono', monospace;
    font-size: 9px;
    letter-spacing: 0.12em;
    color: var(--muted);
    text-transform: uppercase;
    margin-top: 4px;
  }
  .frq-score-box.good { border-color: #2d7a27; background: #f0f8f0; }
  .frq-score-box.good .score-num { color: #2d7a27; }
  .frq-score-box.mid { border-color: var(--gold); background: #fffbf0; }
  .frq-score-box.mid .score-num { color: #b5540a; }
  .frq-score-box.low { border-color: var(--red); background: #fdf0f0; }
  .frq-score-box.low .score-num { color: var(--red); }

  /* CASE EXPLORER */
  .case-quick-btn {
    font-family: 'IBM Plex Mono', monospace;
    font-size: 10px;
    letter-spacing: 0.08em;
    padding: 7px 13px;
    border: 1px solid var(--border);
    background: white;
    color: var(--ink);
    cursor: pointer;
    transition: all 0.15s;
  }
  .case-quick-btn:hover { background: #0f3b34; color: white; border-color: #0f3b34; }

  .case-answer-block {
    margin-bottom: 16px;
    padding-bottom: 16px;
    border-bottom: 1px solid var(--border);
  }
  .case-answer-block:last-child { border-bottom: none; margin-bottom: 0; }
  .case-q-label {
    font-family: 'IBM Plex Mono', monospace;
    font-size: 10px;
    letter-spacing: 0.1em;
    color: #1a5c52;
    text-transform: uppercase;
    margin-bottom: 6px;
  }

  .ai-loading {
    display: flex;
    align-items: center;
    gap: 10px;
    font-family: 'Source Serif 4', serif;
    font-style: italic;
    color: var(--muted);
    font-size: 14px;
    padding: 12px 0;
  }
  .ai-loading::before {
    content: '';
    width: 16px;
    height: 16px;
    border: 2px solid var(--border);
    border-top-color: var(--gold);
    border-radius: 50%;
    animation: spin 0.8s linear infinite;
    flex-shrink: 0;
  }
  @keyframes spin { to { transform: rotate(360deg); } }
</style>
</head>
<body>

<header class="masthead">
  <div class="masthead-inner">
    <div class="masthead-label">AP United States Government & Politics · Unit 2</div>
    <h1 class="masthead-title">The Federal <span>Judiciary</span></h1>
    <div class="masthead-sub">Structure, Power, and the Role of Courts in American Democracy</div>
    <div class="masthead-meta">
      <span class="meta-pill">5 Modules</span>
      <span class="meta-pill">AP Exam Focus</span>
      <span class="meta-pill">Required Cases Included</span>
      <span class="meta-pill">FRQ Practice</span>
    </div>
  </div>
</header>

<div style="background: var(--ink); border-top: 1px solid rgba(255,255,255,0.08);">
  <div class="progress-bar-wrap">
    <div class="progress-track">
      <div class="progress-fill" id="progressFill" style="width: 0%"></div>
    </div>
    <div class="progress-text" id="progressText">0 of 5 modules completed</div>
  </div>
</div>

<div class="layout">

  <!-- SIDEBAR -->
  <aside class="sidebar">
    <div class="sidebar-label">Modules</div>
    <ul class="module-nav" id="moduleNav">
      <li class="module-nav-item active" onclick="switchModule(0)" id="nav-0">
        <div class="nav-inner">
          <div class="nav-number" style="color: var(--module-1)">MODULE 01</div>
          <div class="nav-title">Structure of the Federal Courts</div>
          <div class="nav-status" id="status-0"><span class="status-dot" style="background:#ccc"></span>Not started</div>
        </div>
      </li>
      <li class="module-nav-item" onclick="switchModule(1)" id="nav-1">
        <div class="nav-inner">
          <div class="nav-number" style="color: var(--module-2)">MODULE 02</div>
          <div class="nav-title">Judicial Selection & Appointment</div>
          <div class="nav-status" id="status-1"><span class="status-dot" style="background:#ccc"></span>Not started</div>
        </div>
      </li>
      <li class="module-nav-item" onclick="switchModule(2)" id="nav-2">
        <div class="nav-inner">
          <div class="nav-number" style="color: var(--module-3)">MODULE 03</div>
          <div class="nav-title">Judicial Review & Constitutional Power</div>
          <div class="nav-status" id="status-2"><span class="status-dot" style="background:#ccc"></span>Not started</div>
        </div>
      </li>
      <li class="module-nav-item" onclick="switchModule(3)" id="nav-3">
        <div class="nav-inner">
          <div class="nav-number" style="color: var(--module-4)">MODULE 04</div>
          <div class="nav-title">Supreme Court Decision-Making</div>
          <div class="nav-status" id="status-3"><span class="status-dot" style="background:#ccc"></span>Not started</div>
        </div>
      </li>
      <li class="module-nav-item" onclick="switchModule(4)" id="nav-4">
        <div class="nav-inner">
          <div class="nav-number" style="color: var(--module-5)">MODULE 05</div>
          <div class="nav-title">Required Cases & FRQ Practice</div>
          <div class="nav-status" id="status-4"><span class="status-dot" style="background:#ccc"></span>Not started</div>
        </div>
      </li>
      <li class="module-nav-item" onclick="switchModule(5)" id="nav-5">
        <div class="nav-inner">
          <div class="nav-number" style="color: #b5540a">MODULE 06</div>
          <div class="nav-title">⚡ AI FRQ Grader</div>
          <div class="nav-status" id="status-5"><span class="status-dot" style="background:#ccc"></span>AI-powered</div>
        </div>
      </li>
      <li class="module-nav-item" onclick="switchModule(6)" id="nav-6">
        <div class="nav-inner">
          <div class="nav-number" style="color: #1a5c52">MODULE 07</div>
          <div class="nav-title">🔍 Case Explorer</div>
          <div class="nav-status" id="status-6"><span class="status-dot" style="background:#ccc"></span>AI-powered</div>
        </div>
      </li>
    </ul>

    <div class="nav-arrows" style="margin-top:20px">
      <button class="nav-arrow" onclick="prevModule()">← Prev</button>
      <button class="nav-arrow" onclick="nextModule()">Next →</button>
    </div>
  </aside>

  <!-- CONTENT AREA -->
  <main class="content">

    <!-- ===== MODULE 1 ===== -->
    <div class="module-card visible" id="module-0">
      <div class="card-header" style="background: var(--module-1)">
        <div class="card-eyebrow">Module 01 · Foundation</div>
        <div class="card-title">Structure of the Federal Courts</div>
        <div class="card-subtitle">How the judiciary is organized and what powers it holds</div>
      </div>
      <div class="tab-row" id="tabs-0">
        <button class="tab-btn active" onclick="switchTab(0,'overview')">Overview</button>
        <button class="tab-btn" onclick="switchTab(0,'content')">Content</button>
        <button class="tab-btn" onclick="switchTab(0,'quiz')">Check Your Knowledge</button>
      </div>

      <div class="tab-panel active" id="tab-0-overview">
        <div class="overview-grid">
          <div class="overview-box">
            <div class="overview-box-label">Big Idea</div>
            <p class="big-idea">The federal judiciary is a three-tiered system designed to be independent from political pressure, with the Supreme Court as the final interpreter of the Constitution.</p>
          </div>
          <div class="overview-box">
            <div class="overview-box-label">Essential Questions — <span style="font-size:9px; color:var(--gold); font-style:italic; text-transform:none; letter-spacing:0">click a question to reveal an AP answer</span></div>
            <ul class="essential-qs">
              <li class="eq-item" onclick="toggleEQ(this)">Why did the Framers create an independent judiciary?
                <div class="eq-answer">The Framers feared that a judiciary dependent on elected officials would bend to political majorities, threatening individual rights. In <em>Federalist No. 78</em>, Hamilton argued that life tenure and salary protection would insulate judges from pressure, allowing them to faithfully interpret the Constitution even when doing so was unpopular. An independent judiciary was also essential to enforce the separation of powers — someone had to check both Congress and the president when they exceeded their constitutional authority.</div>
              </li>
              <li class="eq-item" onclick="toggleEQ(this)">What is the difference between original and appellate jurisdiction?
                <div class="eq-answer">Original jurisdiction is the authority to hear a case <em>first</em> — as a trial court. The Supreme Court has original jurisdiction over a narrow category of cases (e.g., disputes between states). Appellate jurisdiction is the authority to <em>review</em> a lower court's decision. The Supreme Court exercises appellate jurisdiction over almost all of its cases, reviewing decisions from U.S. Courts of Appeals or state supreme courts. No new evidence is presented on appeal — only legal arguments about whether the lower court erred.</div>
              </li>
              <li class="eq-item" onclick="toggleEQ(this)">How does federalism shape the dual court system?
                <div class="eq-answer">Federalism creates two parallel court systems: state courts and federal courts. State courts handle the vast majority of cases — criminal, family, property — under state law. Federal courts hear cases involving federal law, the Constitution, or disputes between citizens of different states. When conflicts arise, the Supremacy Clause (Art. VI) establishes that federal law prevails. This division reflects the Framers' intent to preserve state sovereignty while granting the federal government authority over national matters.</div>
              </li>
            </ul>
          </div>
        </div>
        <div class="overview-box" style="margin-bottom:16px">
          <div class="overview-box-label">Key Vocabulary — <span style="font-size:9px; color:var(--gold); font-style:italic; text-transform:none; letter-spacing:0">click a term to see its definition</span></div>
          <div class="vocab-chips" id="vocab-0">
            <span class="vocab-chip" onclick="showDef(0,'Original Jurisdiction')">Original Jurisdiction</span>
            <span class="vocab-chip" onclick="showDef(0,'Appellate Jurisdiction')">Appellate Jurisdiction</span>
            <span class="vocab-chip" onclick="showDef(0,'Writ of Certiorari')">Writ of Certiorari</span>
            <span class="vocab-chip" onclick="showDef(0,'Article III')">Article III</span>
            <span class="vocab-chip" onclick="showDef(0,'Dual Court System')">Dual Court System</span>
            <span class="vocab-chip" onclick="showDef(0,'Stare Decisis')">Stare Decisis</span>
            <span class="vocab-chip" onclick="showDef(0,'Precedent')">Precedent</span>
          </div>
          <div class="vocab-definition" id="vocabdef-0">
            <div class="vocab-def-term" id="vocabdef-0-term"></div>
            <div class="vocab-def-text" id="vocabdef-0-text"></div>
            <div class="vocab-def-example" id="vocabdef-0-example"></div>
          </div>
        </div>
      </div>

      <div class="tab-panel" id="tab-0-content">
        <div class="content-section">
          <h3>Article III and the Constitutional Foundation</h3>
          <p>Article III of the Constitution establishes the federal judiciary, vesting "the judicial Power of the United States" in one Supreme Court and inferior courts created by Congress. The Framers deliberately made the judiciary the least powerful branch — Alexander Hamilton called it the "least dangerous" because it holds neither the sword (executive) nor the purse (legislative).</p>
          <p>Federal judges hold office "during good behavior" — effectively lifetime tenure — shielding them from political pressure. Their salaries cannot be reduced, another protection of independence.</p>
          <div class="callout">
            <strong>AP Exam Connection</strong>
            Federalist No. 78 by Hamilton is a required foundational document. Know his argument: judicial independence through life tenure protects rights better than elected courts.
          </div>
        </div>
        <div class="content-section">
          <h3>The Three-Tier Structure</h3>
          <div class="two-col">
            <div class="mini-card">
              <div class="mini-card-title">⚖️ District Courts (94)</div>
              <ul>
                <li>Trial courts of the federal system</li>
                <li>Original jurisdiction over most federal cases</li>
                <li>Hear both civil and criminal cases</li>
                <li>At least one per state</li>
              </ul>
            </div>
            <div class="mini-card">
              <div class="mini-card-title">📋 Courts of Appeals (13)</div>
              <ul>
                <li>Review district court decisions</li>
                <li>Appellate jurisdiction only</li>
                <li>12 regional circuits + D.C. Circuit</li>
                <li>No new evidence — only legal questions</li>
              </ul>
            </div>
          </div>
          <div class="two-col" style="margin-top:0">
            <div class="mini-card">
              <div class="mini-card-title">🏛️ Supreme Court (1)</div>
              <ul>
                <li>9 Justices — 1 Chief + 8 Associate</li>
                <li>Final arbiter of federal law</li>
                <li>Mostly appellate jurisdiction</li>
                <li>Original jurisdiction: suits between states</li>
              </ul>
            </div>
            <div class="mini-card">
              <div class="mini-card-title">🗺️ Dual Court System</div>
              <ul>
                <li>State courts handle most cases</li>
                <li>Federal courts: federal law, Constitution, diversity</li>
                <li>Some concurrent jurisdiction</li>
                <li>Federal supremacy when in conflict</li>
              </ul>
            </div>
          </div>
        </div>
        <div class="content-section">
          <h3>Writ of Certiorari & The Rule of Four</h3>
          <p>The Supreme Court controls its docket by granting or denying <em>certiorari</em> — a writ ordering a lower court to send up the record. If four of nine justices agree to hear a case ("Rule of Four"), cert is granted. The Court receives ~7,000–8,000 petitions per year but only grants about 70–80.</p>
          <p>Cases most likely to receive cert: circuit splits (Courts of Appeals disagree on the same issue), important constitutional questions, or the federal government requests it through the Solicitor General.</p>
        </div>
      </div>

      <div class="tab-panel" id="tab-0-quiz">
        <div class="quiz-container">
          <div class="quiz-q" id="q0-0">
            <div class="quiz-q-text"><div class="quiz-q-num">Question 1 of 3</div>Which of the following best describes the Supreme Court's <em>original jurisdiction</em>?</div>
            <div class="quiz-choices">
              <button class="quiz-choice" onclick="selectAnswer(0,0,0,false,'The Supreme Court has original jurisdiction over most federal criminal cases, which is why it is called the court of first resort.')"><span class="choice-letter">A</span>Cases involving federal crimes committed in U.S. territories</button>
              <button class="quiz-choice" onclick="selectAnswer(0,0,1,true,'Correct! Article III grants the Supreme Court original jurisdiction primarily over cases involving ambassadors, other public ministers and consuls, and cases in which a state is a party.')"><span class="choice-letter">B</span>Cases in which a state is a party or involving ambassadors</button>
              <button class="quiz-choice" onclick="selectAnswer(0,0,2,false,'This describes appellate jurisdiction — reviewing decisions from lower courts — not original jurisdiction.')"><span class="choice-letter">C</span>All cases appealed from U.S. Courts of Appeals</button>
              <button class="quiz-choice" onclick="selectAnswer(0,0,3,false,'Cases involving federal regulatory agencies fall under appellate review, not the Supreme Court\'s original jurisdiction.')"><span class="choice-letter">D</span>Cases involving federal regulatory agencies like the EPA</button>
            </div>
            <div class="quiz-feedback" id="fb0-0"></div>
            <div class="quiz-submit-row"><button class="btn-primary" onclick="checkAnswer(0,0)" id="check0-0">Check Answer</button></div>
          </div>
          <div class="quiz-q" id="q0-1">
            <div class="quiz-q-text"><div class="quiz-q-num">Question 2 of 3</div>In <em>Federalist No. 78</em>, Alexander Hamilton argues that judicial independence is best protected by:</div>
            <div class="quiz-choices">
              <button class="quiz-choice" onclick="selectAnswer(0,1,0,false,'Hamilton argued the opposite — popular elections would make judges dependent on political majorities, which would threaten individual rights.')"><span class="choice-letter">A</span>Popular election of federal judges every six years</button>
              <button class="quiz-choice" onclick="selectAnswer(0,1,1,false,'Congressional removal authority would undermine independence, making judges politically dependent on the legislature.')"><span class="choice-letter">B</span>Congressional authority to remove judges by majority vote</button>
              <button class="quiz-choice" onclick="selectAnswer(0,1,2,true,'Exactly right. Hamilton called life tenure the best safeguard of judicial independence, protecting judges from political pressure so they could faithfully interpret the Constitution.')"><span class="choice-letter">C</span>Life tenure during good behavior</button>
              <button class="quiz-choice" onclick="selectAnswer(0,1,3,false,'While Hamilton valued the judiciary, he did not argue for giving courts legislative powers — he sought to protect their independence, not expand their function.')"><span class="choice-letter">D</span>Granting courts power to pass legislation</button>
            </div>
            <div class="quiz-feedback" id="fb0-1"></div>
            <div class="quiz-submit-row"><button class="btn-primary" onclick="checkAnswer(0,1)" id="check0-1">Check Answer</button></div>
          </div>
          <div class="quiz-q" id="q0-2">
            <div class="quiz-q-text"><div class="quiz-q-num">Question 3 of 3</div>The "Rule of Four" refers to which Supreme Court practice?</div>
            <div class="quiz-choices">
              <button class="quiz-choice" onclick="selectAnswer(0,2,0,false,'Four justices do not constitute a majority. Decisions require a majority of participating justices — usually five or more.')"><span class="choice-letter">A</span>Four justices must agree to form a majority opinion</button>
              <button class="quiz-choice" onclick="selectAnswer(0,2,1,false,'Unanimous decisions require all nine justices to agree — not just four.')"><span class="choice-letter">B</span>Four justices must write concurring opinions before a decision is published</button>
              <button class="quiz-choice" onclick="selectAnswer(0,2,2,true,'That\'s correct. The Rule of Four means that if at least four justices vote to grant certiorari, the case is accepted for oral argument and full review.')"><span class="choice-letter">C</span>At least four justices must agree to grant certiorari</button>
              <button class="quiz-choice" onclick="selectAnswer(0,2,3,false,'The Rule of Four has nothing to do with recusals. It refers specifically to the threshold for granting review of a lower court decision.')"><span class="choice-letter">D</span>Four justices must recuse themselves for a case to proceed</button>
            </div>
            <div class="quiz-feedback" id="fb0-2"></div>
            <div class="quiz-submit-row"><button class="btn-primary" onclick="checkAnswer(0,2)" id="check0-2">Check Answer</button></div>
          </div>
        </div>
        <div class="complete-section">
          <button class="complete-btn" id="completebtn-0" onclick="completeModule(0)">Mark Module Complete</button>
          <span class="score-badge" id="score-0"></span>
          <span class="complete-note">Complete the quiz before marking done</span>
        </div>
      </div>
    </div>

    <!-- ===== MODULE 2 ===== -->
    <div class="module-card" id="module-1">
      <div class="card-header" style="background: var(--module-2)">
        <div class="card-eyebrow">Module 02 · Process</div>
        <div class="card-title">Judicial Selection & Appointment</div>
        <div class="card-subtitle">How judges reach the bench and what that means for the law</div>
      </div>
      <div class="tab-row" id="tabs-1">
        <button class="tab-btn active" onclick="switchTab(1,'overview')">Overview</button>
        <button class="tab-btn" onclick="switchTab(1,'content')">Content</button>
        <button class="tab-btn" onclick="switchTab(1,'quiz')">Check Your Knowledge</button>
      </div>

      <div class="tab-panel active" id="tab-1-overview">
        <div class="overview-grid">
          <div class="overview-box">
            <div class="overview-box-label">Big Idea</div>
            <p class="big-idea">The nomination and confirmation process is highly political, giving presidents a powerful tool to shape judicial interpretation for generations beyond their term in office.</p>
          </div>
          <div class="overview-box">
            <div class="overview-box-label">Essential Questions — <span style="font-size:9px; color:var(--gold); font-style:italic; text-transform:none; letter-spacing:0">click a question to reveal an AP answer</span></div>
            <ul class="essential-qs">
              <li class="eq-item" onclick="toggleEQ(this)">How does the appointment process reflect checks and balances?
                <div class="eq-answer">Article II grants the president power to nominate federal judges, but Article II also requires Senate "Advice and Consent." This two-step process is a classic example of checks and balances: the executive nominates, the legislative confirms. Neither branch has unilateral control. Presidents may use recess appointments to bypass the Senate temporarily, but the Senate can refuse to hold hearings (as in 2016 with Merrick Garland) or vote down nominees. This shared power prevents either branch from dominating the composition of the judiciary.</div>
              </li>
              <li class="eq-item" onclick="toggleEQ(this)">What factors influence presidential nominees?
                <div class="eq-answer">Presidents weigh multiple factors: (1) <strong>Ideology</strong> — nominees typically share the president's judicial philosophy (originalism vs. living constitutionalism); (2) <strong>Confirmability</strong> — nominees must be able to secure Senate votes, so extreme candidates are often avoided; (3) <strong>Demographics</strong> — presidents consider race, gender, and religion to build coalitions and reflect the diversity of the country; (4) <strong>Professional credentials</strong> — judicial experience, academic pedigree, and ABA ratings matter; (5) <strong>Political loyalty</strong> — past rulings and associations signal future behavior on the bench.</div>
              </li>
              <li class="eq-item" onclick="toggleEQ(this)">How has judicial confirmation changed over time?
                <div class="eq-answer">Confirmations have become increasingly partisan and contentious. Through most of U.S. history, nominees were confirmed quickly with little opposition. This changed in 1987 when Robert Bork was rejected after intense ideological scrutiny — "borking" entered the political lexicon. Since then, hearings have become highly politicized, nominees are more guarded in their testimony, filibusters were used to block nominees, and the Senate eliminated the 60-vote threshold for lower court nominees (2013) and Supreme Court nominees (2017), enabling simple majority confirmations.</div>
              </li>
            </ul>
          </div>
        </div>
        <div class="overview-box">
          <div class="overview-box-label">Key Vocabulary — <span style="font-size:9px; color:var(--gold); font-style:italic; text-transform:none; letter-spacing:0">click a term to see its definition</span></div>
          <div class="vocab-chips" id="vocab-1">
            <span class="vocab-chip" onclick="showDef(1,'Nomination')">Nomination</span>
            <span class="vocab-chip" onclick="showDef(1,'Senate Confirmation')">Senate Confirmation</span>
            <span class="vocab-chip" onclick="showDef(1,'Senatorial Courtesy')">Senatorial Courtesy</span>
            <span class="vocab-chip" onclick="showDef(1,'Judicial Ideology')">Judicial Ideology</span>
            <span class="vocab-chip" onclick="showDef(1,'Originalism')">Originalism</span>
            <span class="vocab-chip" onclick="showDef(1,'Living Constitution')">Living Constitution</span>
            <span class="vocab-chip" onclick="showDef(1,'Litmus Test')">Litmus Test</span>
          </div>
          <div class="vocab-definition" id="vocabdef-1">
            <div class="vocab-def-term" id="vocabdef-1-term"></div>
            <div class="vocab-def-text" id="vocabdef-1-text"></div>
            <div class="vocab-def-example" id="vocabdef-1-example"></div>
          </div>
        </div>
      </div>

      <div class="tab-panel" id="tab-1-content">
        <div class="content-section">
          <h3>The Nomination & Confirmation Process</h3>
          <p>Article II grants the president power to nominate federal judges "with the Advice and Consent of the Senate." In practice, this creates a two-step process: presidential nomination followed by Senate Judiciary Committee hearings and a full Senate floor vote.</p>
          <p>For lower federal courts, <strong>senatorial courtesy</strong> gives home-state senators informal veto power over nominees — the president typically consults them before nominating district and circuit judges.</p>
          <div class="callout">
            <strong>AP Exam Connection</strong>
            Know that the process shows checks and balances: presidential appointment power is checked by Senate confirmation. This is a key institutional design feature from the Framers.
          </div>
        </div>
        <div class="content-section">
          <h3>What Presidents Consider</h3>
          <div class="two-col">
            <div class="mini-card">
              <div class="mini-card-title">Political Factors</div>
              <ul>
                <li>Ideological alignment with the president</li>
                <li>Party loyalty and record</li>
                <li>Prior judicial or political service</li>
                <li>Likelihood of Senate confirmation</li>
              </ul>
            </div>
            <div class="mini-card">
              <div class="mini-card-title">Demographic Factors</div>
              <ul>
                <li>Race, gender, ethnicity</li>
                <li>Geographic representation</li>
                <li>Religious background</li>
                <li>Coalition building/reward</li>
              </ul>
            </div>
          </div>
        </div>
        <div class="content-section">
          <h3>Judicial Philosophy: Originalism vs. Living Constitutionalism</h3>
          <p><strong>Originalism</strong> holds that the Constitution should be interpreted as the Framers understood it. <strong>Textualists</strong> (a variant) focus on the plain meaning of the text. Justice Scalia was the most famous proponent.</p>
          <p><strong>Living Constitutionalism</strong> holds that the Constitution's meaning evolves with society. Justices apply constitutional principles to contemporary circumstances not foreseen by the Framers.</p>
          <p>These philosophies often — though not always — align with conservative and liberal judicial outcomes respectively, making them a major factor in confirmation battles.</p>
        </div>
      </div>

      <div class="tab-panel" id="tab-1-quiz">
        <div class="quiz-container">
          <div class="quiz-q" id="q1-0">
            <div class="quiz-q-text"><div class="quiz-q-num">Question 1 of 3</div>"Senatorial courtesy" in the federal judicial nomination process refers to:</div>
            <div class="quiz-choices">
              <button class="quiz-choice" onclick="selectAnswer(1,0,0,false,'This describes a courtesy extended to the nominee, not senatorial courtesy. The norm actually involves deference to senators from the nominee\'s home state.')"><span class="choice-letter">A</span>The tradition of senators addressing nominees with formal titles</button>
              <button class="quiz-choice" onclick="selectAnswer(1,0,1,true,'Correct. Senatorial courtesy is the norm where the president defers to the home-state senator(s) — especially those of the president\'s party — before nominating judges to district courts in that state.')"><span class="choice-letter">B</span>The norm that the president consults home-state senators before nominating district court judges</button>
              <button class="quiz-choice" onclick="selectAnswer(1,0,2,false,'The Senate Judiciary Committee holds hearings and debates, but senatorial courtesy specifically refers to informal deference to home-state senators, not to committee procedures.')"><span class="choice-letter">C</span>The requirement that the Senate Judiciary Committee hold public hearings for all nominees</button>
              <button class="quiz-choice" onclick="selectAnswer(1,0,3,false,'Senators may personally oppose nominees, but "senatorial courtesy" is a norm about consultation before nomination, not a formal veto power over any federal judge.')"><span class="choice-letter">D</span>The rule that any senator can formally veto a Supreme Court nominee</button>
            </div>
            <div class="quiz-feedback" id="fb1-0"></div>
            <div class="quiz-submit-row"><button class="btn-primary" onclick="checkAnswer(1,0)" id="check1-0">Check Answer</button></div>
          </div>
          <div class="quiz-q" id="q1-1">
            <div class="quiz-q-text"><div class="quiz-q-num">Question 2 of 3</div>A judge who believes the Constitution should be interpreted based on how it was originally understood by the Framers is best described as a(n):</div>
            <div class="quiz-choices">
              <button class="quiz-choice" onclick="selectAnswer(1,1,0,false,'An "activist" judge is one who freely uses judicial review to strike down laws — this is a behavioral description, not a philosophical one like originalism.')"><span class="choice-letter">A</span>Judicial activist</button>
              <button class="quiz-choice" onclick="selectAnswer(1,1,1,false,'Living constitutionalists believe the meaning of the Constitution evolves over time — the opposite of interpreting it based on original understanding.')"><span class="choice-letter">B</span>Living constitutionalist</button>
              <button class="quiz-choice" onclick="selectAnswer(1,1,2,true,'Yes. Originalism holds that judges should interpret the Constitution according to the original intent or original public meaning at the time it was written.')"><span class="choice-letter">C</span>Originalist</button>
              <button class="quiz-choice" onclick="selectAnswer(1,1,3,false,'Judicial restraint means deferring to elected branches and avoiding striking down laws — it\'s about how often courts intervene, not how they interpret the text.')"><span class="choice-letter">D</span>Judicial restraintist</button>
            </div>
            <div class="quiz-feedback" id="fb1-1"></div>
            <div class="quiz-submit-row"><button class="btn-primary" onclick="checkAnswer(1,1)" id="check1-1">Check Answer</button></div>
          </div>
          <div class="quiz-q" id="q1-2">
            <div class="quiz-q-text"><div class="quiz-q-num">Question 3 of 3</div>Which constitutional provision establishes the process for appointing federal judges?</div>
            <div class="quiz-choices">
              <button class="quiz-choice" onclick="selectAnswer(1,2,0,false,'Article I establishes Congress and its powers — it does not address the appointment of judges.')"><span class="choice-letter">A</span>Article I — the legislative vesting clause</button>
              <button class="quiz-choice" onclick="selectAnswer(1,2,1,true,'Correct. Article II, Section 2 grants the president the power to nominate judges with the "Advice and Consent of the Senate."')"><span class="choice-letter">B</span>Article II — the president's appointment power</button>
              <button class="quiz-choice" onclick="selectAnswer(1,2,2,false,'Article III establishes the judicial branch and judges\' life tenure, but the appointment process itself is found in Article II.')"><span class="choice-letter">C</span>Article III — the judicial vesting clause</button>
              <button class="quiz-choice" onclick="selectAnswer(1,2,3,false,'The 14th Amendment addresses equal protection and citizenship — it has no role in the judicial appointment process.')"><span class="choice-letter">D</span>The 14th Amendment equal protection clause</button>
            </div>
            <div class="quiz-feedback" id="fb1-2"></div>
            <div class="quiz-submit-row"><button class="btn-primary" onclick="checkAnswer(1,2)" id="check1-2">Check Answer</button></div>
          </div>
        </div>
        <div class="complete-section">
          <button class="complete-btn" id="completebtn-1" onclick="completeModule(1)">Mark Module Complete</button>
          <span class="score-badge" id="score-1"></span>
          <span class="complete-note">Complete the quiz before marking done</span>
        </div>
      </div>
    </div>

    <!-- ===== MODULE 3 ===== -->
    <div class="module-card" id="module-2">
      <div class="card-header" style="background: var(--module-3)">
        <div class="card-eyebrow">Module 03 · Power</div>
        <div class="card-title">Judicial Review & Constitutional Power</div>
        <div class="card-subtitle">From Marbury to modern controversies</div>
      </div>
      <div class="tab-row" id="tabs-2">
        <button class="tab-btn active" onclick="switchTab(2,'overview')">Overview</button>
        <button class="tab-btn" onclick="switchTab(2,'content')">Content</button>
        <button class="tab-btn" onclick="switchTab(2,'quiz')">Check Your Knowledge</button>
      </div>

      <div class="tab-panel active" id="tab-2-overview">
        <div class="overview-grid">
          <div class="overview-box">
            <div class="overview-box-label">Big Idea</div>
            <p class="big-idea">Judicial review — the power to strike down unconstitutional acts — is the Court's most important power, yet it is nowhere explicitly stated in the Constitution. Its legitimacy remains contested.</p>
          </div>
          <div class="overview-box">
            <div class="overview-box-label">Essential Questions — <span style="font-size:9px; color:var(--gold); font-style:italic; text-transform:none; letter-spacing:0">click a question to reveal an AP answer</span></div>
            <ul class="essential-qs">
              <li class="eq-item" onclick="toggleEQ(this)">How did Marbury v. Madison establish judicial review?
                <div class="eq-answer">In 1803, Chief Justice Marshall faced a political trap: ordering Madison to deliver Marbury's commission would likely be ignored, undermining the Court's authority. Marshall's solution was masterful — he ruled Marbury deserved his commission <em>but</em> that the Supreme Court had no power to order it, because the law giving it that power (Section 13 of the Judiciary Act) conflicted with Article III's definition of the Court's original jurisdiction. By striking down that law, Marshall established that the Constitution is supreme over congressional statutes, and that the Court is the final arbiter of what the Constitution means — the essence of judicial review.</div>
              </li>
              <li class="eq-item" onclick="toggleEQ(this)">How do courts check the other branches?
                <div class="eq-answer">Courts check the legislative branch by striking down laws that violate the Constitution (judicial review). Courts check the executive branch by ruling executive actions unconstitutional — e.g., <em>Youngstown Sheet & Tube v. Sawyer</em> (1952) stopped Truman from seizing steel mills. Courts also enforce individual rights against both branches. However, courts are limited: they cannot initiate action, they depend on the executive to enforce their rulings, and Congress can strip appellate jurisdiction or propose constitutional amendments to override decisions.</div>
              </li>
              <li class="eq-item" onclick="toggleEQ(this)">What limits exist on judicial power?
                <div class="eq-answer">Several significant limits constrain the courts: (1) <strong>Passivity</strong> — courts cannot initiate cases, they must wait for disputes; (2) <strong>Enforcement</strong> — courts have no army or police; they depend on executive compliance (President Jackson reportedly ignored a ruling); (3) <strong>Constitutional amendments</strong> — Congress and the states can reverse court decisions by amending the Constitution (e.g., the 16th Amendment reversed a ruling on income taxes); (4) <strong>Congressional jurisdiction stripping</strong> — Congress can limit the Court's appellate jurisdiction; (5) <strong>Public legitimacy</strong> — the Court's power rests on public trust; deeply unpopular rulings risk defiance.</div>
              </li>
            </ul>
          </div>
        </div>
        <div class="overview-box">
          <div class="overview-box-label">Key Vocabulary — <span style="font-size:9px; color:var(--gold); font-style:italic; text-transform:none; letter-spacing:0">click a term to see its definition</span></div>
          <div class="vocab-chips" id="vocab-2">
            <span class="vocab-chip" onclick="showDef(2,'Judicial Review')">Judicial Review</span>
            <span class="vocab-chip" onclick="showDef(2,'Marbury v. Madison')">Marbury v. Madison</span>
            <span class="vocab-chip" onclick="showDef(2,'Unconstitutional')">Unconstitutional</span>
            <span class="vocab-chip" onclick="showDef(2,'Judicial Activism')">Judicial Activism</span>
            <span class="vocab-chip" onclick="showDef(2,'Judicial Restraint')">Judicial Restraint</span>
            <span class="vocab-chip" onclick="showDef(2,'Checks & Balances')">Checks & Balances</span>
            <span class="vocab-chip" onclick="showDef(2,'Counter-majoritarian')">Counter-majoritarian</span>
          </div>
          <div class="vocab-definition" id="vocabdef-2">
            <div class="vocab-def-term" id="vocabdef-2-term"></div>
            <div class="vocab-def-text" id="vocabdef-2-text"></div>
            <div class="vocab-def-example" id="vocabdef-2-example"></div>
          </div>
        </div>
      </div>

      <div class="tab-panel" id="tab-2-content">
        <div class="content-section">
          <h3>Marbury v. Madison (1803)</h3>
          <p>Chief Justice John Marshall established judicial review in <em>Marbury v. Madison</em>. The case arose when outgoing President Adams appointed "midnight judges" — including William Marbury — but Jefferson's Secretary of State James Madison refused to deliver Marbury's commission.</p>
          <p>Marshall's genius: he ruled against Marbury (avoiding a direct confrontation with Jefferson) but used the case to declare Section 13 of the Judiciary Act of 1789 unconstitutional. In doing so, he asserted: <em>"It is emphatically the province and duty of the Judicial Department to say what the law is."</em></p>
          <div class="callout">
            <strong>Required Supreme Court Case</strong>
            Marbury v. Madison is an AP-required case. Know: the facts, Marshall's reasoning, and the significance — the Court established judicial review while tactically avoiding a constitutional crisis.
          </div>
        </div>
        <div class="content-section">
          <h3>Judicial Activism vs. Judicial Restraint</h3>
          <div class="two-col">
            <div class="mini-card">
              <div class="mini-card-title">🔥 Judicial Activism</div>
              <ul>
                <li>Willing to strike down laws and precedents</li>
                <li>Courts as agents of social change</li>
                <li>Broader readings of constitutional protections</li>
                <li>Example: Brown v. Board overturning Plessy</li>
              </ul>
            </div>
            <div class="mini-card">
              <div class="mini-card-title">⚖️ Judicial Restraint</div>
              <ul>
                <li>Defer to elected branches when possible</li>
                <li>Overturn laws only when clearly unconstitutional</li>
                <li>Respect stare decisis / precedent</li>
                <li>Courts as interpreters, not policymakers</li>
              </ul>
            </div>
          </div>
        </div>
        <div class="content-section">
          <h3>Limits on Judicial Power</h3>
          <p>Courts are "passive" — they cannot initiate cases, they wait for disputes to come to them. Other constraints: Congress can amend the Constitution (overriding decisions), Congress controls appellate jurisdiction, presidents may refuse to enforce rulings, public opinion and legitimacy concerns constrain the Court.</p>
        </div>
      </div>

      <div class="tab-panel" id="tab-2-quiz">
        <div class="quiz-container">
          <div class="quiz-q" id="q2-0">
            <div class="quiz-q-text"><div class="quiz-q-num">Question 1 of 3</div>In <em>Marbury v. Madison</em> (1803), the Supreme Court ruled that:</div>
            <div class="quiz-choices">
              <button class="quiz-choice" onclick="selectAnswer(2,0,0,false,'This would be using judicial power aggressively to compel the executive — Marshall strategically avoided this to prevent a direct constitutional confrontation with Jefferson.')"><span class="choice-letter">A</span>Madison must deliver Marbury's commission immediately</button>
              <button class="quiz-choice" onclick="selectAnswer(2,0,1,false,'The Court actually ruled in favor of Jefferson\'s administration in practical terms — but used the case to claim the larger power of judicial review.')"><span class="choice-letter">B</span>Jefferson's administration acted unconstitutionally and must be punished</button>
              <button class="quiz-choice" onclick="selectAnswer(2,0,2,true,'Exactly. Marshall struck down Section 13 of the Judiciary Act, which had expanded original jurisdiction. This established the Court\'s power to invalidate acts of Congress as unconstitutional.')"><span class="choice-letter">C</span>Part of the Judiciary Act of 1789 was unconstitutional, establishing judicial review</button>
              <button class="quiz-choice" onclick="selectAnswer(2,0,3,false,'The Court had no such power, and Marshall did not claim it. He actually ruled that Marbury was not entitled to a remedy from the Supreme Court.')"><span class="choice-letter">D</span>The President must consult the Supreme Court before issuing executive orders</button>
            </div>
            <div class="quiz-feedback" id="fb2-0"></div>
            <div class="quiz-submit-row"><button class="btn-primary" onclick="checkAnswer(2,0)" id="check2-0">Check Answer</button></div>
          </div>
          <div class="quiz-q" id="q2-1">
            <div class="quiz-q-text"><div class="quiz-q-num">Question 2 of 3</div>Which of the following is the best example of <em>judicial restraint</em>?</div>
            <div class="quiz-choices">
              <button class="quiz-choice" onclick="selectAnswer(2,1,0,false,'Striking down a federal law without clear constitutional violation would be judicial activism — using the Court\'s power expansively to override elected branches.')"><span class="choice-letter">A</span>A court strikes down a federal law because it disagrees with its policy outcome</button>
              <button class="quiz-choice" onclick="selectAnswer(2,1,1,false,'Using the Constitution to create new rights not explicitly stated is more consistent with a living constitution or activist approach, not restraint.')"><span class="choice-letter">B</span>A court uses the Constitution to create new rights not mentioned in the text</button>
              <button class="quiz-choice" onclick="selectAnswer(2,1,2,true,'This is a textbook example of judicial restraint — deferring to democratic majorities and the legislative process rather than substituting judicial judgment for the legislature\'s.')"><span class="choice-letter">C</span>A court upholds a controversial law, deferring to the legislature's democratic authority</button>
              <button class="quiz-choice" onclick="selectAnswer(2,1,3,false,'Overturning long-standing precedent is a hallmark of judicial activism — disturbing settled law rather than respecting stare decisis.')"><span class="choice-letter">D</span>A court overturns 50 years of precedent to reflect changing social values</button>
            </div>
            <div class="quiz-feedback" id="fb2-1"></div>
            <div class="quiz-submit-row"><button class="btn-primary" onclick="checkAnswer(2,1)" id="check2-1">Check Answer</button></div>
          </div>
          <div class="quiz-q" id="q2-2">
            <div class="quiz-q-text"><div class="quiz-q-num">Question 3 of 3</div>Which of the following is NOT a significant limitation on the power of the Supreme Court?</div>
            <div class="quiz-choices">
              <button class="quiz-choice" onclick="selectAnswer(2,2,0,false,'Constitutional amendments can indeed override Supreme Court decisions — for example, the 16th Amendment overruled a Court decision striking down the income tax.')"><span class="choice-letter">A</span>Congress can override Court decisions through constitutional amendments</button>
              <button class="quiz-choice" onclick="selectAnswer(2,2,1,false,'This is a real constraint — presidents who disagree with rulings can drag their feet on implementation, limiting the practical effect of Court decisions.')"><span class="choice-letter">B</span>Presidents can refuse to enforce Court decisions</button>
              <button class="quiz-choice" onclick="selectAnswer(2,2,2,true,'Correct — this is NOT a real power. The Supreme Court cannot be dissolved by Congress. It was established by Article III and can only be fundamentally altered through constitutional amendment.')"><span class="choice-letter">C</span>Congress can dissolve the Supreme Court by majority vote</button>
              <button class="quiz-choice" onclick="selectAnswer(2,2,3,false,'This is a real constitutional power — Article III gives Congress authority to define and limit the appellate jurisdiction of the Supreme Court.')"><span class="choice-letter">D</span>Congress can restrict the Court's appellate jurisdiction</button>
            </div>
            <div class="quiz-feedback" id="fb2-2"></div>
            <div class="quiz-submit-row"><button class="btn-primary" onclick="checkAnswer(2,2)" id="check2-2">Check Answer</button></div>
          </div>
        </div>
        <div class="complete-section">
          <button class="complete-btn" id="completebtn-2" onclick="completeModule(2)">Mark Module Complete</button>
          <span class="score-badge" id="score-2"></span>
          <span class="complete-note">Complete the quiz before marking done</span>
        </div>
      </div>
    </div>

    <!-- ===== MODULE 4 ===== -->
    <div class="module-card" id="module-3">
      <div class="card-header" style="background: var(--module-4)">
        <div class="card-eyebrow">Module 04 · Process</div>
        <div class="card-title">Supreme Court Decision-Making</div>
        <div class="card-subtitle">From oral arguments to published opinions</div>
      </div>
      <div class="tab-row" id="tabs-3">
        <button class="tab-btn active" onclick="switchTab(3,'overview')">Overview</button>
        <button class="tab-btn" onclick="switchTab(3,'content')">Content</button>
        <button class="tab-btn" onclick="switchTab(3,'quiz')">Check Your Knowledge</button>
      </div>

      <div class="tab-panel active" id="tab-3-overview">
        <div class="overview-grid">
          <div class="overview-box">
            <div class="overview-box-label">Big Idea</div>
            <p class="big-idea">Supreme Court decisions result from a complex process shaped by legal arguments, judicial ideology, external political factors, and the dynamics of coalition-building among nine justices.</p>
          </div>
          <div class="overview-box">
            <div class="overview-box-label">Essential Questions — <span style="font-size:9px; color:var(--gold); font-style:italic; text-transform:none; letter-spacing:0">click a question to reveal an AP answer</span></div>
            <ul class="essential-qs">
              <li class="eq-item" onclick="toggleEQ(this)">What happens between cert and a final decision?
                <div class="eq-answer">After granting certiorari, the Court follows a structured process: (1) Both parties file written <strong>briefs</strong> laying out their legal arguments; interested third parties may file <strong>amicus curiae</strong> briefs; (2) <strong>Oral arguments</strong> are scheduled — each side typically gets 30 minutes; justices interrupt frequently with questions; (3) After argument, justices meet privately in <strong>conference</strong> to discuss and take a preliminary vote; (4) The Chief Justice (if in the majority) or the most senior majority justice <strong>assigns opinion writing</strong>; (5) Justices draft and circulate opinions; coalitions may shift; (6) Final opinions — majority, concurring, dissenting — are published and announced from the bench.</div>
              </li>
              <li class="eq-item" onclick="toggleEQ(this)">What factors influence how justices vote?
                <div class="eq-answer">Justices are influenced by both legal and extra-legal factors. <strong>Legal factors</strong> include: constitutional text, precedent (stare decisis), legislative history, and lower court reasoning. <strong>Extra-legal (attitudinal) factors</strong> include: personal ideology and values, public opinion (indirectly — the Court is sensitive to its legitimacy), the Solicitor General's position (government wins ~70% of the time), interest group amicus briefs, and the dynamics of coalition-building with fellow justices. Research by political scientists consistently finds that judicial ideology is the single strongest predictor of Supreme Court votes.</div>
              </li>
              <li class="eq-item" onclick="toggleEQ(this)">How do majority, concurring, and dissenting opinions differ?
                <div class="eq-answer"><strong>Majority opinion</strong>: Joined by at least 5 justices; announces the decision AND the legal reasoning; constitutes binding precedent that all lower courts must follow. <strong>Concurring opinion</strong>: A justice agrees with the <em>outcome</em> but writes separately to offer different or additional reasoning; does not carry the full precedential weight of the majority rationale. <strong>Dissenting opinion</strong>: Written by justices who disagree with the outcome; legally non-binding but historically important — dissents often foreshadow future majority positions (e.g., Harlan's dissent in Plessy, Ginsburg's dissents on gender discrimination). <strong>Plurality opinion</strong>: When no single rationale commands a majority; announces the result but establishes limited precedent.</div>
              </li>
            </ul>
          </div>
        </div>
        <div class="overview-box">
          <div class="overview-box-label">Key Vocabulary — <span style="font-size:9px; color:var(--gold); font-style:italic; text-transform:none; letter-spacing:0">click a term to see its definition</span></div>
          <div class="vocab-chips" id="vocab-3">
            <span class="vocab-chip" onclick="showDef(3,'Oral Argument')">Oral Argument</span>
            <span class="vocab-chip" onclick="showDef(3,'Conference')">Conference</span>
            <span class="vocab-chip" onclick="showDef(3,'Majority Opinion')">Majority Opinion</span>
            <span class="vocab-chip" onclick="showDef(3,'Concurring Opinion')">Concurring Opinion</span>
            <span class="vocab-chip" onclick="showDef(3,'Dissenting Opinion')">Dissenting Opinion</span>
            <span class="vocab-chip" onclick="showDef(3,'Amicus Curiae')">Amicus Curiae</span>
            <span class="vocab-chip" onclick="showDef(3,'Solicitor General')">Solicitor General</span>
          </div>
          <div class="vocab-definition" id="vocabdef-3">
            <div class="vocab-def-term" id="vocabdef-3-term"></div>
            <div class="vocab-def-text" id="vocabdef-3-text"></div>
            <div class="vocab-def-example" id="vocabdef-3-example"></div>
          </div>
        </div>
      </div>

      <div class="tab-panel" id="tab-3-content">
        <div class="content-section">
          <h3>The Path to a Decision</h3>
          <div class="two-col">
            <div class="mini-card">
              <div class="mini-card-title">📄 Before Oral Argument</div>
              <ul>
                <li>Certiorari granted (Rule of Four)</li>
                <li>Briefs filed by both sides</li>
                <li>Amicus curiae briefs filed by interested parties</li>
                <li>Law clerks research and prep justices</li>
              </ul>
            </div>
            <div class="mini-card">
              <div class="mini-card-title">🎤 Oral Argument</div>
              <ul>
                <li>Each side gets 30 minutes (usually)</li>
                <li>Justices ask pointed questions</li>
                <li>No new evidence — legal argument only</li>
                <li>Open to the public</li>
              </ul>
            </div>
          </div>
          <div class="two-col">
            <div class="mini-card">
              <div class="mini-card-title">🗳️ Conference & Vote</div>
              <ul>
                <li>Justices only — no clerks present</li>
                <li>Chief Justice speaks first, votes last</li>
                <li>Preliminary votes taken</li>
                <li>Opinion writing assigned</li>
              </ul>
            </div>
            <div class="mini-card">
              <div class="mini-card-title">✍️ Written Opinions</div>
              <ul>
                <li>Majority opinion: binding precedent</li>
                <li>Concurring: agrees with outcome, not reasoning</li>
                <li>Dissenting: disagrees — "appeals to history"</li>
                <li>Plurality: no single majority rationale</li>
              </ul>
            </div>
          </div>
        </div>
        <div class="content-section">
          <h3>Influences on Judicial Decision-Making</h3>
          <p><strong>Legal factors:</strong> precedent (stare decisis), constitutional text, legislative history, lower court rulings.</p>
          <p><strong>Extra-legal factors:</strong> judicial ideology/philosophy, public opinion (indirect), political context, interest group pressures via amicus briefs, and the Solicitor General's influence (the federal government's lawyer before the Court).</p>
          <div class="callout">
            <strong>AP Exam Tip</strong>
            Dissents matter — they often preview future majority positions. Ruth Bader Ginsburg's dissents in gender discrimination cases and John Marshall Harlan's solo dissent in Plessy v. Ferguson are famous examples.
          </div>
        </div>
      </div>

      <div class="tab-panel" id="tab-3-quiz">
        <div class="quiz-container">
          <div class="quiz-q" id="q3-0">
            <div class="quiz-q-text"><div class="quiz-q-num">Question 1 of 3</div>An <em>amicus curiae</em> brief is best described as:</div>
            <div class="quiz-choices">
              <button class="quiz-choice" onclick="selectAnswer(3,0,0,false,'This describes a brief filed by a party to the case. Amicus curiae briefs are filed by third parties who are not directly involved in the litigation.')"><span class="choice-letter">A</span>A brief filed by the party who lost in the lower court explaining why they deserve to win</button>
              <button class="quiz-choice" onclick="selectAnswer(3,0,1,true,'Correct. An amicus curiae ("friend of the court") brief is filed by a non-party — typically an interest group, advocacy organization, or government — to provide additional legal arguments or information relevant to the case.')"><span class="choice-letter">B</span>A brief filed by a non-party offering relevant legal arguments or information</button>
              <button class="quiz-choice" onclick="selectAnswer(3,0,2,false,'The majority opinion is written by the justice assigned by the Chief Justice after the conference vote — not by outside parties.')"><span class="choice-letter">C</span>A brief written by the Chief Justice summarizing the Court\'s majority view</button>
              <button class="quiz-choice" onclick="selectAnswer(3,0,3,false,'The Solicitor General is a specific government official who represents the U.S. before the Court — they are distinct from the general amicus curiae process.')"><span class="choice-letter">D</span>A brief written by the Solicitor General on behalf of the federal government</button>
            </div>
            <div class="quiz-feedback" id="fb3-0"></div>
            <div class="quiz-submit-row"><button class="btn-primary" onclick="checkAnswer(3,0)" id="check3-0">Check Answer</button></div>
          </div>
          <div class="quiz-q" id="q3-1">
            <div class="quiz-q-text"><div class="quiz-q-num">Question 2 of 3</div>Which type of Supreme Court opinion establishes binding legal precedent?</div>
            <div class="quiz-choices">
              <button class="quiz-choice" onclick="selectAnswer(3,1,0,false,'A dissenting opinion is written by justices who disagree with the outcome. While influential, it has no binding legal effect.')"><span class="choice-letter">A</span>Dissenting opinion</button>
              <button class="quiz-choice" onclick="selectAnswer(3,1,1,false,'A concurring opinion agrees with the outcome but for different reasons. It does not establish binding precedent on the reasoning, only the result.')"><span class="choice-letter">B</span>Concurring opinion</button>
              <button class="quiz-choice" onclick="selectAnswer(3,1,2,true,'The majority opinion, joined by at least five justices, is the binding legal precedent. It is the law of the land and must be followed by lower courts.')"><span class="choice-letter">C</span>Majority opinion</button>
              <button class="quiz-choice" onclick="selectAnswer(3,1,3,false,'A plurality opinion is one where no single rationale commands a majority. It announces the result but does not establish broad binding precedent in the same way a majority opinion does.')"><span class="choice-letter">D</span>Plurality opinion</button>
            </div>
            <div class="quiz-feedback" id="fb3-1"></div>
            <div class="quiz-submit-row"><button class="btn-primary" onclick="checkAnswer(3,1)" id="check3-1">Check Answer</button></div>
          </div>
          <div class="quiz-q" id="q3-2">
            <div class="quiz-q-text"><div class="quiz-q-num">Question 3 of 3</div>During Supreme Court conference, which of the following best describes the voting procedure?</div>
            <div class="quiz-choices">
              <button class="quiz-choice" onclick="selectAnswer(3,2,0,false,'The Chief Justice leads the discussion and speaks first to set the agenda, but they vote last — not first — in conference.')"><span class="choice-letter">A</span>The Chief Justice votes first and other justices follow in order of seniority</button>
              <button class="quiz-choice" onclick="selectAnswer(3,2,1,false,'Law clerks are not present at conference. Conferences are private meetings exclusively among the nine justices.')"><span class="choice-letter">B</span>Law clerks attend and record the vote before presenting a summary to the justices</button>
              <button class="quiz-choice" onclick="selectAnswer(3,2,2,true,'That\'s right. In conference, the Chief Justice speaks and leads discussion first, but votes last. The most junior justice speaks and votes first — a tradition meant to prevent undue influence from senior colleagues.')"><span class="choice-letter">C</span>The Chief Justice speaks first to frame the discussion but votes last; the most junior justice votes first</button>
              <button class="quiz-choice" onclick="selectAnswer(3,2,3,false,'Votes are not publicly disclosed during conference. The process is entirely secret — only the final published opinions are made public.')"><span class="choice-letter">D</span>All votes are publicly disclosed immediately after conference ends</button>
            </div>
            <div class="quiz-feedback" id="fb3-2"></div>
            <div class="quiz-submit-row"><button class="btn-primary" onclick="checkAnswer(3,2)" id="check3-2">Check Answer</button></div>
          </div>
        </div>
        <div class="complete-section">
          <button class="complete-btn" id="completebtn-3" onclick="completeModule(3)">Mark Module Complete</button>
          <span class="score-badge" id="score-3"></span>
          <span class="complete-note">Complete the quiz before marking done</span>
        </div>
      </div>
    </div>

    <!-- ===== MODULE 5 ===== -->
    <div class="module-card" id="module-4">
      <div class="card-header" style="background: var(--module-5)">
        <div class="card-eyebrow">Module 05 · AP Exam Prep</div>
        <div class="card-title">Required Cases & FRQ Practice</div>
        <div class="card-subtitle">Master the cases the College Board expects you to know</div>
      </div>
      <div class="tab-row" id="tabs-4">
        <button class="tab-btn active" onclick="switchTab(4,'overview')">Required Cases</button>
        <button class="tab-btn" onclick="switchTab(4,'content')">Case Details</button>
        <button class="tab-btn" onclick="switchTab(4,'quiz')">FRQ Practice</button>
      </div>

      <div class="tab-panel active" id="tab-4-overview">
        <div style="margin-bottom:16px; font-family:'IBM Plex Mono',monospace; font-size:10px; letter-spacing:0.15em; color:var(--muted); text-transform:uppercase;">AP Required Foundational Documents & Cases (Judiciary Focus)</div>
        <table class="cases-table">
          <thead>
            <tr>
              <th>Case</th>
              <th>Year</th>
              <th>Core Issue</th>
              <th>Outcome / Significance</th>
            </tr>
          </thead>
          <tbody>
            <tr>
              <td><span class="case-name">Marbury v. Madison</span><br><span class="significance-tag" style="background:#1a3a5c;color:white">Foundational</span></td>
              <td>1803</td>
              <td>Can the Court strike down acts of Congress?</td>
              <td>Established judicial review; Section 13 of Judiciary Act unconstitutional</td>
            </tr>
            <tr>
              <td><span class="case-name">McCulloch v. Maryland</span><br><span class="significance-tag" style="background:#2d5a27;color:white">Federalism</span></td>
              <td>1819</td>
              <td>Federal vs. state power; necessary & proper clause</td>
              <td>Broad federal power; states cannot tax federal institutions</td>
            </tr>
            <tr>
              <td><span class="case-name">United States v. Lopez</span><br><span class="significance-tag" style="background:#6b2020;color:white">Commerce Clause</span></td>
              <td>1995</td>
              <td>Does the Gun-Free School Zones Act exceed Commerce Clause?</td>
              <td>Reined in congressional power; gun possession at school ≠ commerce</td>
            </tr>
            <tr>
              <td><span class="case-name">District of Columbia v. Heller</span><br><span class="significance-tag" style="background:#4a2d6b;color:white">2nd Amendment</span></td>
              <td>2008</td>
              <td>Individual right to bear arms?</td>
              <td>2nd Amendment protects individual right to own firearms for self-defense</td>
            </tr>
            <tr>
              <td><span class="case-name">McDonald v. Chicago</span><br><span class="significance-tag" style="background:#4a2d6b;color:white">Incorporation</span></td>
              <td>2010</td>
              <td>Does Heller apply to state/local governments?</td>
              <td>2nd Amendment incorporated to states via 14th Amendment</td>
            </tr>
            <tr>
              <td><span class="case-name">New York Times Co. v. United States</span><br><span class="significance-tag" style="background:#5a3a0d;color:white">1st Amendment</span></td>
              <td>1971</td>
              <td>Can the gov't engage in prior restraint on the press?</td>
              <td>Rejected prior restraint; "Pentagon Papers" could be published</td>
            </tr>
            <tr>
              <td><span class="case-name">Engel v. Vitale</span><br><span class="significance-tag" style="background:#5a3a0d;color:white">Establishment</span></td>
              <td>1962</td>
              <td>School-sponsored prayer constitutional?</td>
              <td>State-sponsored prayer in public schools violates Establishment Clause</td>
            </tr>
          </tbody>
        </table>
      </div>

      <div class="tab-panel" id="tab-4-content">
        <div class="content-section">
          <h3>Deep Dive: Marbury v. Madison (1803)</h3>
          <p><strong>Facts:</strong> William Marbury was appointed as a Justice of the Peace by outgoing President Adams. Secretary of State John Marshall (the same Marshall who later wrote the opinion) failed to deliver the commission. Incoming Secretary of State James Madison, under President Jefferson, refused to deliver it.</p>
          <p><strong>Legal Question:</strong> Did the Supreme Court have jurisdiction to issue a writ of mandamus forcing Madison to deliver the commission?</p>
          <p><strong>Marshall's Holding:</strong> Marbury had a right to his commission, but the Supreme Court couldn't help him because Section 13 of the Judiciary Act, which purported to give the Court original jurisdiction to issue writs of mandamus, was unconstitutional — it conflicted with Article III.</p>
          <div class="callout">
            <strong>The Genius Move</strong>
            Marshall gave Jefferson the practical victory (no mandamus) while claiming the far more important power of judicial review. Jefferson couldn't object without undermining the Court he wanted to defeat.
          </div>
        </div>
        <div class="content-section">
          <h3>Deep Dive: McCulloch v. Maryland (1819)</h3>
          <p><strong>Facts:</strong> Maryland tried to tax the Second Bank of the United States. McCulloch, the bank's cashier, refused to pay. The question: could Congress create a national bank, and could states tax it?</p>
          <p><strong>Marshall's Holding:</strong> Yes to the bank (the Necessary and Proper Clause gives Congress implied powers) and no to the tax ("the power to tax is the power to destroy"). Established supremacy of federal law.</p>
          <p><strong>Legacy:</strong> This case is the foundation for broad federal power under the Necessary and Proper Clause. It is essential to understanding how Congress's enumerated powers have expanded over time.</p>
        </div>
      </div>

      <div class="tab-panel" id="tab-4-quiz">
        <div style="margin-bottom:20px; font-family:'IBM Plex Mono',monospace; font-size:10px; letter-spacing:0.2em; color:var(--muted); text-transform:uppercase; border-bottom:1px solid var(--border); padding-bottom:12px;">FRQ Practice — Judicial Review & Court Structure</div>

        <div class="frq-prompt">
          <strong style="font-family:'IBM Plex Mono',monospace; font-size:10px; letter-spacing:0.2em; text-transform:uppercase; color:var(--gold-light); display:block; margin-bottom:8px;">Concept Application FRQ</strong>
          The Supreme Court's power of judicial review has been called "counter-majoritarian" — meaning it allows an unelected Court to strike down decisions made by democratically elected officials. Critics argue this undermines democracy; defenders argue it protects constitutional rights from majority tyranny.
        </div>

        <div class="frq-part">
          <div class="frq-part-label">Part A — 1 point</div>
          <div class="frq-part-q">Describe what is meant by judicial review and identify the case that established this power.</div>
          <button class="frq-toggle" onclick="toggleAnswer('frq-a')">Show sample answer ↓</button>
          <div class="frq-answer" id="frq-a">
            <strong>Sample Answer:</strong> Judicial review is the power of the Supreme Court (and lower federal courts) to examine laws passed by Congress or actions taken by the executive branch and declare them unconstitutional and therefore void. This power was established in <em>Marbury v. Madison</em> (1803), in which Chief Justice John Marshall ruled that Section 13 of the Judiciary Act of 1789 conflicted with Article III of the Constitution, and that "it is emphatically the province and duty of the Judicial Department to say what the law is."
          </div>
        </div>

        <div class="frq-part">
          <div class="frq-part-label">Part B — 2 points</div>
          <div class="frq-part-q">Explain one argument in favor of judicial review as protecting democracy, and one argument that judicial review is anti-democratic.</div>
          <button class="frq-toggle" onclick="toggleAnswer('frq-b')">Show sample answer ↓</button>
          <div class="frq-answer" id="frq-b">
            <strong>Pro-democracy argument:</strong> Judicial review protects individual rights and minority groups from "tyranny of the majority." Democracy is not just majority rule — it also requires protection of fundamental rights. Without judicial review, simple majorities could pass laws stripping civil liberties (e.g., speech, religion). The Court's independence allows it to enforce constitutional limits even when doing so is politically unpopular.
            <br><br>
            <strong>Anti-democratic argument:</strong> Nine unelected, life-tenured justices can strike down laws passed by elected representatives who are accountable to voters. This is counter-majoritarian — the will of the people, expressed through their elected officials, is overridden by judges who face no electoral consequence. Critics argue this concentrates too much power in the least democratic branch.
          </div>
        </div>

        <div class="frq-part">
          <div class="frq-part-label">Part C — 2 points</div>
          <div class="frq-part-q">Explain how the constitutional design of the federal judiciary (Article III) attempts to balance judicial independence with democratic accountability.</div>
          <button class="frq-toggle" onclick="toggleAnswer('frq-c')">Show sample answer ↓</button>
          <div class="frq-answer" id="frq-c">
            <strong>Sample Answer:</strong> The Framers attempted to balance these values in several ways. First, federal judges are appointed by the president and confirmed by the Senate — elected officials — which provides an initial democratic check (Art. II, §2). Second, life tenure "during good behavior" insulates judges from political pressure once confirmed, allowing independent judgment. Third, Congress retains power over the Court's appellate jurisdiction and can propose constitutional amendments to override decisions, preserving ultimate democratic authority. Additionally, the process of nomination and confirmation allows public opinion to shape the Court's ideological composition over time, even if individual justices cannot be voted out.
          </div>
        </div>

        <div class="complete-section">
          <button class="complete-btn" id="completebtn-4" onclick="completeModule(4)">Mark Module Complete</button>
          <span class="score-badge" id="score-4"></span>
          <span class="complete-note">Review the FRQ answers and mark done when ready</span>
        </div>
      </div>
    </div>

    <!-- ===== MODULE 6: AI FRQ GRADER ===== -->
    <div class="module-card" id="module-5">
      <div class="card-header" style="background: linear-gradient(135deg, #b5540a, #8a3a06)">
        <div class="card-eyebrow">Module 06 · AI-Powered</div>
        <div class="card-title">FRQ Practice Grader</div>
        <div class="card-subtitle">Write a real FRQ response and get instant AP-style feedback</div>
      </div>

      <div style="background:white; padding: 24px 32px; border-bottom: 1px solid var(--border);">
        <div style="font-family:'IBM Plex Mono',monospace; font-size:10px; letter-spacing:0.15em; color:var(--muted); text-transform:uppercase; margin-bottom:14px;">Select an FRQ Prompt</div>
        <div style="display:flex; flex-wrap:wrap; gap:8px; margin-bottom:18px;" id="frqPromptBtns">
          <button class="frq-select-btn active" onclick="selectFRQ(0)">Judicial Review</button>
          <button class="frq-select-btn" onclick="selectFRQ(1)">Court Structure</button>
          <button class="frq-select-btn" onclick="selectFRQ(2)">Judicial Appointments</button>
          <button class="frq-select-btn" onclick="selectFRQ(3)">Checks on Courts</button>
        </div>

        <div id="frqPromptDisplay" style="background:var(--ink); color:var(--parchment); padding:18px 22px; font-size:13.5px; line-height:1.75; font-family:'Source Serif 4',serif; margin-bottom:18px;">
        </div>

        <div style="font-family:'IBM Plex Mono',monospace; font-size:10px; letter-spacing:0.15em; color:var(--muted); text-transform:uppercase; margin-bottom:8px;">Your Response</div>
        <textarea id="frqStudentAnswer" placeholder="Write your FRQ response here. Aim for complete sentences with specific evidence — just like the real AP exam..." style="width:100%; min-height:180px; padding:14px 16px; border:1px solid var(--border); background:var(--cream); font-family:'Source Serif 4',serif; font-size:13.5px; line-height:1.7; resize:vertical; outline:none; color:var(--ink);"></textarea>

        <div style="display:flex; align-items:center; gap:12px; margin-top:14px; flex-wrap:wrap;">
          <button class="btn-primary" id="frqSubmitBtn" onclick="gradeFRQ()">⚡ Grade My Response</button>
          <button class="btn-secondary" onclick="clearFRQ()">Clear</button>
          <span id="frqCharCount" style="font-family:'IBM Plex Mono',monospace; font-size:10px; color:var(--muted); letter-spacing:0.08em;">0 words</span>
        </div>
      </div>

      <div id="frqFeedbackArea" style="display:none; padding:28px 32px; background:white;">
        <div style="font-family:'IBM Plex Mono',monospace; font-size:10px; letter-spacing:0.2em; color:var(--muted); text-transform:uppercase; margin-bottom:16px; padding-bottom:10px; border-bottom:1px solid var(--border);">AI Feedback — AP Exam Style</div>
        <div id="frqLoadingMsg" style="font-family:'Source Serif 4',serif; font-style:italic; color:var(--muted); font-size:14px; padding:20px 0;">Analyzing your response against AP scoring criteria...</div>
        <div id="frqFeedbackContent" style="display:none;">
          <div id="frqScoreRow" style="display:flex; gap:16px; flex-wrap:wrap; margin-bottom:20px;"></div>
          <div id="frqFeedbackText" style="font-family:'Source Serif 4',serif; font-size:14px; line-height:1.75; color:#2a2520;"></div>
        </div>
      </div>
    </div>

    <!-- ===== MODULE 7: CASE EXPLORER ===== -->
    <div class="module-card" id="module-6">
      <div class="card-header" style="background: linear-gradient(135deg, #1a5c52, #0f3b34)">
        <div class="card-eyebrow">Module 07 · AI-Powered</div>
        <div class="card-title">Supreme Court Case Explorer</div>
        <div class="card-subtitle">Ask anything about any judiciary case — AP-focused answers</div>
      </div>

      <div style="background:white; padding:24px 32px; border-bottom:1px solid var(--border);">
        <div style="font-family:'IBM Plex Mono',monospace; font-size:10px; letter-spacing:0.15em; color:var(--muted); text-transform:uppercase; margin-bottom:12px;">Quick Case Buttons</div>
        <div style="display:flex; flex-wrap:wrap; gap:8px; margin-bottom:20px;" id="caseQuickBtns">
          <button class="case-quick-btn" onclick="quickCase('Marbury v. Madison')">Marbury v. Madison</button>
          <button class="case-quick-btn" onclick="quickCase('McCulloch v. Maryland')">McCulloch v. Maryland</button>
          <button class="case-quick-btn" onclick="quickCase('United States v. Lopez')">U.S. v. Lopez</button>
          <button class="case-quick-btn" onclick="quickCase('District of Columbia v. Heller')">D.C. v. Heller</button>
          <button class="case-quick-btn" onclick="quickCase('Engel v. Vitale')">Engel v. Vitale</button>
          <button class="case-quick-btn" onclick="quickCase('New York Times v. United States')">NYT v. United States</button>
        </div>

        <div style="font-family:'IBM Plex Mono',monospace; font-size:10px; letter-spacing:0.15em; color:var(--muted); text-transform:uppercase; margin-bottom:8px;">Ask a Question About Any Case</div>
        <div style="display:flex; gap:10px;">
          <input id="caseQuestion" type="text" placeholder="e.g. Why does Marbury v. Madison matter for the AP exam? What did the Court decide in Heller?" style="flex:1; padding:11px 14px; border:1px solid var(--border); background:var(--cream); font-family:'Source Serif 4',serif; font-size:13.5px; outline:none; color:var(--ink);" onkeydown="if(event.key==='Enter') exploreCase()" />
          <button class="btn-primary" onclick="exploreCase()">Ask →</button>
        </div>
      </div>

      <div id="caseAnswerArea" style="display:none; padding:28px 32px; background:white;">
        <div style="font-family:'IBM Plex Mono',monospace; font-size:10px; letter-spacing:0.2em; color:var(--muted); text-transform:uppercase; margin-bottom:16px; padding-bottom:10px; border-bottom:1px solid var(--border);">Case Explorer — AI Response</div>
        <div id="caseLoadingMsg" style="font-family:'Source Serif 4',serif; font-style:italic; color:var(--muted); font-size:14px; padding:16px 0;">Looking up case information...</div>
        <div id="caseAnswerContent" style="display:none; font-family:'Source Serif 4',serif; font-size:14px; line-height:1.8; color:#2a2520;"></div>
      </div>

      <div id="caseChatHistory" style="padding:0 32px 8px; background:white; display:none;">
        <div style="font-family:'IBM Plex Mono',monospace; font-size:10px; letter-spacing:0.15em; color:var(--muted); text-transform:uppercase; padding:10px 0 8px; border-top:1px solid var(--border);">Follow-up Questions</div>
        <div style="display:flex; gap:10px; padding-bottom:20px;">
          <input id="caseFollowup" type="text" placeholder="Ask a follow-up..." style="flex:1; padding:10px 14px; border:1px solid var(--border); background:var(--cream); font-family:'Source Serif 4',serif; font-size:13px; outline:none; color:var(--ink);" onkeydown="if(event.key==='Enter') followUpCase()" />
          <button class="btn-secondary" onclick="followUpCase()">Ask</button>
        </div>
      </div>
    </div>

  </main>
</div>

<script>
  let currentModule = 0;
  const totalModules = 7;
  const completedModules = new Array(totalModules).fill(false);
  const moduleScores = new Array(totalModules).fill(null);
  const moduleAnswers = {};
  const moduleColors = ['var(--module-1)','var(--module-2)','var(--module-3)','var(--module-4)','var(--module-5)'];

  // ── VOCABULARY DEFINITIONS ────────────────────────────────────────────────
  const vocabDefs = {
    // Module 0
    'Original Jurisdiction': {
      def: 'The authority of a court to hear a case for the first time, before any other court has reviewed it.',
      ex: 'Ex: The Supreme Court has original jurisdiction in cases where a U.S. state is a party.'
    },
    'Appellate Jurisdiction': {
      def: 'The authority of a court to review and revise decisions made by a lower court. No new evidence is presented — only legal arguments.',
      ex: 'Ex: The U.S. Courts of Appeals exercise appellate jurisdiction over federal district court decisions.'
    },
    'Writ of Certiorari': {
      def: 'An order issued by a higher court (usually the Supreme Court) directing a lower court to send up the record of a case for review.',
      ex: 'Ex: Each year the Supreme Court receives ~8,000 cert petitions but grants only about 70–80.'
    },
    'Article III': {
      def: 'The section of the U.S. Constitution that establishes the federal judiciary, creating the Supreme Court and authorizing Congress to create inferior courts. It also grants judges life tenure.',
      ex: 'Ex: Article III states judges hold office "during good behavior," protecting their independence.'
    },
    'Dual Court System': {
      def: 'The coexistence of separate federal and state court systems, each with its own jurisdiction. Most cases are handled in state courts.',
      ex: 'Ex: A robbery case goes to state court; a federal drug trafficking case goes to federal district court.'
    },
    'Stare Decisis': {
      def: 'Latin for "to stand by things decided." The legal principle requiring courts to follow precedent established in prior cases.',
      ex: 'Ex: Because of stare decisis, lower courts are bound to apply Supreme Court rulings to similar cases.'
    },
    'Precedent': {
      def: 'A prior court decision that serves as a rule or guide for deciding later cases with similar facts or legal issues.',
      ex: 'Ex: Brown v. Board of Education (1954) set precedent that racial segregation in public schools is unconstitutional.'
    },
    // Module 1
    'Nomination': {
      def: 'The formal presidential selection of a candidate for a federal judgeship. The nominee must then be confirmed by the Senate.',
      ex: 'Ex: The president nominates Supreme Court justices; recent nominees have faced intense Senate scrutiny.'
    },
    'Senate Confirmation': {
      def: 'The process by which the Senate approves or rejects a presidential nominee to a federal court position, exercising its "Advice and Consent" role under Article II.',
      ex: 'Ex: The Senate Judiciary Committee holds hearings before a full Senate floor vote on confirmation.'
    },
    'Senatorial Courtesy': {
      def: 'An informal tradition where the president consults senators from a nominee\'s home state — especially those of the president\'s party — before nominating federal district court judges.',
      ex: 'Ex: If a senator objects to a nominee from their state, the president typically withdraws that nominee.'
    },
    'Judicial Ideology': {
      def: 'A judge\'s personal legal philosophy and values that shape how they interpret the Constitution and laws. Presidents often seek nominees whose ideology aligns with their own.',
      ex: 'Ex: Conservative presidents tend to nominate judges with originalist ideologies; liberal presidents favor living constitutionalists.'
    },
    'Originalism': {
      def: 'A judicial philosophy holding that the Constitution should be interpreted based on its original meaning at the time it was written or ratified.',
      ex: 'Ex: Justice Scalia was a prominent originalist, arguing courts should not read new rights into the Constitution.'
    },
    'Living Constitution': {
      def: 'A judicial philosophy holding that the Constitution\'s meaning evolves over time to reflect changing societal values and circumstances.',
      ex: 'Ex: Living constitutionalists argue that the 8th Amendment\'s ban on "cruel and unusual punishment" should be interpreted by modern standards.'
    },
    'Litmus Test': {
      def: 'An informal political term for a single decisive issue used to evaluate whether a judicial nominee is acceptable — e.g., their likely stance on abortion or gun rights.',
      ex: 'Ex: Critics accused both parties of applying ideological litmus tests during recent Supreme Court confirmation hearings.'
    },
    // Module 2
    'Judicial Review': {
      def: 'The power of courts to examine laws and executive actions and declare them unconstitutional. Established in Marbury v. Madison (1803).',
      ex: 'Ex: When the Supreme Court struck down DOMA in United States v. Windsor, it exercised judicial review.'
    },
    'Marbury v. Madison': {
      def: 'The landmark 1803 Supreme Court case in which Chief Justice John Marshall established the doctrine of judicial review, declaring part of the Judiciary Act of 1789 unconstitutional.',
      ex: 'Ex: Marshall wrote: "It is emphatically the province and duty of the Judicial Department to say what the law is."'
    },
    'Unconstitutional': {
      def: 'A description for any law, government action, or policy that violates or conflicts with the U.S. Constitution. Unconstitutional acts are void and have no legal force.',
      ex: 'Ex: In Texas v. Johnson (1989), the Court ruled laws banning flag burning were unconstitutional violations of the 1st Amendment.'
    },
    'Judicial Activism': {
      def: 'A judicial philosophy characterized by a willingness to use judicial review broadly to strike down laws and shape public policy, sometimes departing from precedent.',
      ex: 'Ex: Brown v. Board overturned Plessy v. Ferguson — a landmark example of judicial activism reshaping civil rights law.'
    },
    'Judicial Restraint': {
      def: 'A judicial philosophy that courts should defer to the elected branches of government whenever possible and only strike down laws when they are clearly unconstitutional.',
      ex: 'Ex: A restrained court might uphold a controversial law and say: "This is for Congress to fix, not the courts."'
    },
    'Checks & Balances': {
      def: 'The constitutional system by which each branch of government has powers that limit and oversee the other branches, preventing any one branch from becoming too powerful.',
      ex: 'Ex: Senate confirmation of judicial nominees is a check on presidential appointment power.'
    },
    'Counter-majoritarian': {
      def: 'Describes an institution or action that can override or limit the will of the democratic majority. Courts are often called counter-majoritarian because unelected judges can strike down laws passed by elected majorities.',
      ex: 'Ex: When the Supreme Court struck down popular state laws defining marriage, critics called the decision counter-majoritarian.'
    },
    // Module 3
    'Oral Argument': {
      def: 'The formal presentation of legal arguments before the Supreme Court, where each side typically has 30 minutes and justices ask questions. No new evidence — only legal reasoning.',
      ex: 'Ex: Oral arguments at the Supreme Court are open to the public and transcripts are released online.'
    },
    'Conference': {
      def: 'The private meeting of the nine Supreme Court justices (no clerks or staff) where they discuss cases and take preliminary votes after oral arguments.',
      ex: 'Ex: At conference, the Chief Justice speaks first to frame discussion but votes last; the most junior justice votes first.'
    },
    'Majority Opinion': {
      def: 'The official opinion of the Supreme Court joined by at least five justices. It announces the decision and legal reasoning, establishing binding precedent for lower courts.',
      ex: 'Ex: Chief Justice Warren\'s majority opinion in Brown v. Board declared segregated schools unconstitutional.'
    },
    'Concurring Opinion': {
      def: 'An opinion written by a justice who agrees with the majority\'s outcome but for different or additional reasons. It does not carry the same binding weight as the majority opinion.',
      ex: 'Ex: A justice might concur in the judgment but write separately to limit how broadly the ruling should be interpreted.'
    },
    'Dissenting Opinion': {
      def: 'An opinion written by a justice or justices who disagree with the majority\'s decision. Though not legally binding, dissents can influence future cases.',
      ex: 'Ex: Justice Harlan\'s solo dissent in Plessy v. Ferguson (1896) argued "our Constitution is color-blind" — vindicated 58 years later in Brown.'
    },
    'Amicus Curiae': {
      def: 'Latin for "friend of the court." A brief filed by a non-party (often an interest group, government, or organization) offering information or arguments relevant to a case.',
      ex: 'Ex: In major civil rights cases, the NAACP and ACLU frequently file amicus briefs to influence the Court\'s reasoning.'
    },
    'Solicitor General': {
      def: 'The federal government\'s top lawyer before the Supreme Court, responsible for representing the U.S. government\'s interests and deciding which cases the government will appeal.',
      ex: 'Ex: The Solicitor General\'s office is so influential it\'s sometimes called the "tenth justice."'
    }
  };

  function showDef(moduleIdx, term) {
    const def = vocabDefs[term];
    if (!def) return;

    const container = document.getElementById(`vocabdef-${moduleIdx}`);
    const termEl = document.getElementById(`vocabdef-${moduleIdx}-term`);
    const textEl = document.getElementById(`vocabdef-${moduleIdx}-text`);
    const exEl = document.getElementById(`vocabdef-${moduleIdx}-example`);

    // Toggle off if same chip clicked again
    const chips = document.querySelectorAll(`#vocab-${moduleIdx} .vocab-chip`);
    const activeChip = [...chips].find(c => c.classList.contains('active'));

    if (activeChip && activeChip.textContent.trim().replace(' ▴','').replace(' ▾','') === term && container.classList.contains('show')) {
      container.classList.remove('show');
      chips.forEach(c => c.classList.remove('active'));
      return;
    }

    // Show definition
    termEl.textContent = term;
    textEl.textContent = def.def;
    exEl.textContent = def.ex || '';
    container.classList.add('show');

    // Highlight active chip
    chips.forEach(c => {
      const label = c.textContent.trim().replace(' ▴','').replace(' ▾','');
      c.classList.toggle('active', label === term);
    });
  }

  // Initialize answer state
  for(let m=0; m<4; m++) {
    moduleAnswers[m] = {};
    for(let q=0; q<3; q++) {
      moduleAnswers[m][q] = { selected: null, checked: false, correct: false };
    }
  }

  function toggleEQ(el) {
    const answer = el.querySelector('.eq-answer');
    const isOpen = el.classList.contains('open');
    el.classList.toggle('open', !isOpen);
    answer.classList.toggle('show', !isOpen);
  }


  function switchModule(idx) {
    document.getElementById('module-' + currentModule).classList.remove('visible');
    document.querySelectorAll('.module-nav-item').forEach(el => el.classList.remove('active'));
    currentModule = idx;
    document.getElementById('module-' + idx).classList.add('visible');
    document.getElementById('nav-' + idx).classList.add('active');
  }

  function nextModule() {
    if(currentModule < totalModules - 1) switchModule(currentModule + 1);
  }

  function prevModule() {
    if(currentModule > 0) switchModule(currentModule - 1);
  }

  function switchTab(moduleIdx, tabName) {
    const panels = document.querySelectorAll(`#module-${moduleIdx} .tab-panel`);
    const buttons = document.querySelectorAll(`#tabs-${moduleIdx} .tab-btn`);
    const tabMap = { overview: 0, content: 1, quiz: 2 };
    panels.forEach(p => p.classList.remove('active'));
    buttons.forEach(b => b.classList.remove('active'));
    panels[tabMap[tabName]].classList.add('active');
    buttons[tabMap[tabName]].classList.add('active');
  }

  function selectAnswer(moduleIdx, qIdx, choiceIdx, isCorrect, feedback) {
    if(moduleAnswers[moduleIdx][qIdx].checked) return;
    moduleAnswers[moduleIdx][qIdx].selected = choiceIdx;
    moduleAnswers[moduleIdx][qIdx].correctness = isCorrect;
    moduleAnswers[moduleIdx][qIdx].feedback = feedback;
    
    const qEl = document.getElementById(`q${moduleIdx}-${qIdx}`);
    qEl.querySelectorAll('.quiz-choice').forEach((btn, i) => {
      btn.classList.remove('selected');
      if(i === choiceIdx) btn.classList.add('selected');
    });
  }

  function checkAnswer(moduleIdx, qIdx) {
    const state = moduleAnswers[moduleIdx][qIdx];
    if(state.selected === null) { alert('Please select an answer first.'); return; }
    if(state.checked) return;
    state.checked = true;

    const qEl = document.getElementById(`q${moduleIdx}-${qIdx}`);
    const choices = qEl.querySelectorAll('.quiz-choice');
    const fb = document.getElementById(`fb${moduleIdx}-${qIdx}`);
    const checkBtn = document.getElementById(`check${moduleIdx}-${qIdx}`);

    choices[state.selected].classList.remove('selected');
    choices[state.selected].classList.add(state.correctness ? 'correct' : 'incorrect');
    choices[state.selected].classList.add('locked');

    fb.textContent = state.feedback;
    fb.classList.add('show', state.correctness ? 'correct-fb' : 'incorrect-fb');
    checkBtn.disabled = true;

    // Mark all as locked
    choices.forEach(c => c.classList.add('locked'));

    // Calculate score for this module
    updateScore(moduleIdx);
  }

  function updateScore(moduleIdx) {
    if(moduleIdx >= 4) return;
    const answers = moduleAnswers[moduleIdx];
    let correct = 0;
    let total = 0;
    for(let q in answers) {
      if(answers[q].checked) { total++; if(answers[q].correctness) correct++; }
    }
    if(total === 3) {
      moduleScores[moduleIdx] = correct;
      const scoreBadge = document.getElementById(`score-${moduleIdx}`);
      scoreBadge.textContent = `Quiz: ${correct}/3 correct`;
      scoreBadge.classList.add('show');
    }
  }

  function completeModule(idx) {
    completedModules[idx] = true;
    const btn = document.getElementById(`completebtn-${idx}`);
    btn.textContent = '✓ Completed';
    btn.classList.add('done');

    const statusEl = document.getElementById(`status-${idx}`);
    statusEl.innerHTML = `<span class="status-dot" style="background:var(--gold)"></span><span style="color:var(--gold); font-family:'IBM Plex Mono',monospace; font-size:9px; letter-spacing:0.1em;">Completed</span>`;

    updateProgress();
  }

  function updateProgress() {
    const done = completedModules.filter(Boolean).length;
    const pct = (done / totalModules) * 100;
    document.getElementById('progressFill').style.width = pct + '%';
    document.getElementById('progressText').textContent = `${done} of ${totalModules} modules completed`;
  }

  function toggleAnswer(id) {
    const el = document.getElementById(id);
    el.classList.toggle('show');
    const btn = el.previousElementSibling;
    btn.textContent = el.classList.contains('show') ? 'Hide answer ↑' : 'Show sample answer ↓';
  }

  // ── FRQ GRADER ─────────────────────────────────────────────────────────────
  const frqPrompts = [
    {
      label: 'Judicial Review',
      text: `The Supreme Court's power of judicial review has been described as both essential to constitutional democracy and as a threat to it.\n\n(A) Define judicial review and identify the case in which this power was established. (1 pt)\n(B) Explain one argument that judicial review protects democracy AND one argument that it threatens democracy. (2 pts)\n(C) Explain how the constitutional design of the federal judiciary attempts to balance judicial independence with democratic accountability. (2 pts)`
    },
    {
      label: 'Court Structure',
      text: `The federal court system is organized as a three-tier hierarchy.\n\n(A) Describe the structure of the federal court system, identifying the role of each level. (1 pt)\n(B) Explain the difference between original and appellate jurisdiction and give one example of each. (2 pts)\n(C) Explain how the Founders' goal of judicial independence is reflected in Article III of the Constitution. (2 pts)`
    },
    {
      label: 'Judicial Appointments',
      text: `The process by which federal judges are selected is highly political and has become increasingly contentious.\n\n(A) Describe the constitutional process for appointing Supreme Court justices. (1 pt)\n(B) Explain how a president's choice of judicial nominees reflects their policy priorities AND how the Senate uses the confirmation process to check presidential power. (2 pts)\n(C) Explain two factors — one legal/professional and one political/demographic — that presidents typically consider when selecting nominees. (2 pts)`
    },
    {
      label: 'Checks on Courts',
      text: `While judicial review gives the Supreme Court enormous power, the Constitution and political system impose meaningful limits on that power.\n\n(A) Identify and explain one formal constitutional mechanism that limits Supreme Court power. (1 pt)\n(B) Explain how the concept of stare decisis both constrains AND empowers the Supreme Court. (2 pts)\n(C) Using a specific Supreme Court case, explain how the Court's decision affected the balance of power between the federal government and the states OR between branches of the federal government. (2 pts)`
    }
  ];

  let selectedFRQ = 0;

  function selectFRQ(idx) {
    selectedFRQ = idx;
    document.querySelectorAll('.frq-select-btn').forEach((b,i) => b.classList.toggle('active', i===idx));
    document.getElementById('frqPromptDisplay').textContent = frqPrompts[idx].text;
    document.getElementById('frqFeedbackArea').style.display = 'none';
    document.getElementById('frqStudentAnswer').value = '';
    document.getElementById('frqCharCount').textContent = '0 words';
  }

  document.addEventListener('DOMContentLoaded', () => {
    selectFRQ(0);
    document.getElementById('frqStudentAnswer').addEventListener('input', function() {
      const words = this.value.trim().split(/\s+/).filter(Boolean).length;
      document.getElementById('frqCharCount').textContent = words + ' word' + (words !== 1 ? 's' : '');
    });
  });

  // Init on load since DOMContentLoaded may already have fired
  setTimeout(() => { if (document.getElementById('frqPromptDisplay')) selectFRQ(0); }, 100);

  async function gradeFRQ() {
    const answer = document.getElementById('frqStudentAnswer').value.trim();
    if (!answer || answer.length < 20) { alert('Please write a response before grading.'); return; }
    const prompt = frqPrompts[selectedFRQ];

    document.getElementById('frqFeedbackArea').style.display = 'block';
    document.getElementById('frqLoadingMsg').style.display = 'block';
    document.getElementById('frqLoadingMsg').className = 'ai-loading';
    document.getElementById('frqLoadingMsg').textContent = 'Analyzing your response against AP scoring criteria...';
    document.getElementById('frqFeedbackContent').style.display = 'none';
    document.getElementById('frqSubmitBtn').disabled = true;

    const systemPrompt = `You are an AP US Government & Politics FRQ grader. Grade student responses against College Board rubric criteria. Be specific, constructive, and encouraging. Always respond ONLY with valid JSON — no markdown, no backticks, no preamble.`;

    const userMsg = `FRQ PROMPT:\n${prompt.text}\n\nSTUDENT RESPONSE:\n${answer}\n\nGrade this response and return ONLY this JSON (no markdown):\n{\n  "scoreA": <0 or 1>,\n  "scoreB": <0, 1, or 2>,\n  "scoreC": <0, 1, or 2>,\n  "totalScore": <0-5>,\n  "maxScore": 5,\n  "partAFeedback": "...",\n  "partBFeedback": "...",\n  "partCFeedback": "...",\n  "strengths": "...",\n  "improvements": "...",\n  "apTip": "..."\n}`;

    try {
      const res = await fetch('https://api.anthropic.com/v1/messages', {
        method: 'POST',
        headers: { 'Content-Type': 'application/json' },
        body: JSON.stringify({
          model: 'claude-sonnet-4-20250514',
          max_tokens: 1000,
          system: systemPrompt,
          messages: [{ role: 'user', content: userMsg }]
        })
      });
      const data = await res.json();
      const raw = data.content.map(b => b.text || '').join('');
      const clean = raw.replace(/```json|```/g, '').trim();
      const result = JSON.parse(clean);
      renderFRQFeedback(result);
    } catch(e) {
      document.getElementById('frqLoadingMsg').className = '';
      document.getElementById('frqLoadingMsg').textContent = 'Error getting feedback. Please try again.';
    }
    document.getElementById('frqSubmitBtn').disabled = false;
  }

  function renderFRQFeedback(r) {
    document.getElementById('frqLoadingMsg').style.display = 'none';
    document.getElementById('frqFeedbackContent').style.display = 'block';

    const pct = r.totalScore / r.maxScore;
    const cls = pct >= 0.8 ? 'good' : pct >= 0.5 ? 'mid' : 'low';

    document.getElementById('frqScoreRow').innerHTML = `
      <div class="frq-score-box ${cls}">
        <div class="score-num">${r.totalScore}/${r.maxScore}</div>
        <div class="score-label">Total Score</div>
      </div>
      <div class="frq-score-box ${r.scoreA===1?'good':'low'}">
        <div class="score-num">${r.scoreA}/1</div>
        <div class="score-label">Part A</div>
      </div>
      <div class="frq-score-box ${r.scoreB>=1?(r.scoreB===2?'good':'mid'):'low'}">
        <div class="score-num">${r.scoreB}/2</div>
        <div class="score-label">Part B</div>
      </div>
      <div class="frq-score-box ${r.scoreC>=1?(r.scoreC===2?'good':'mid'):'low'}">
        <div class="score-num">${r.scoreC}/2</div>
        <div class="score-label">Part C</div>
      </div>`;

    document.getElementById('frqFeedbackText').innerHTML = `
      <div style="margin-bottom:18px;">
        <div style="font-family:'IBM Plex Mono',monospace;font-size:10px;letter-spacing:0.15em;color:#b5540a;text-transform:uppercase;margin-bottom:6px;">Part A Feedback</div>
        <p>${r.partAFeedback}</p>
      </div>
      <div style="margin-bottom:18px;">
        <div style="font-family:'IBM Plex Mono',monospace;font-size:10px;letter-spacing:0.15em;color:#b5540a;text-transform:uppercase;margin-bottom:6px;">Part B Feedback</div>
        <p>${r.partBFeedback}</p>
      </div>
      <div style="margin-bottom:20px;">
        <div style="font-family:'IBM Plex Mono',monospace;font-size:10px;letter-spacing:0.15em;color:#b5540a;text-transform:uppercase;margin-bottom:6px;">Part C Feedback</div>
        <p>${r.partCFeedback}</p>
      </div>
      <div style="display:grid;grid-template-columns:1fr 1fr;gap:14px;margin-bottom:18px;">
        <div style="background:#f0f8f0;border:1px solid #c0dfc0;padding:14px 16px;">
          <div style="font-family:'IBM Plex Mono',monospace;font-size:9px;letter-spacing:0.15em;color:#2d7a27;text-transform:uppercase;margin-bottom:6px;">✓ Strengths</div>
          <p style="font-size:13px;line-height:1.6;">${r.strengths}</p>
        </div>
        <div style="background:#fff8f0;border:1px solid #e0c090;padding:14px 16px;">
          <div style="font-family:'IBM Plex Mono',monospace;font-size:9px;letter-spacing:0.15em;color:#b5540a;text-transform:uppercase;margin-bottom:6px;">↑ To Improve</div>
          <p style="font-size:13px;line-height:1.6;">${r.improvements}</p>
        </div>
      </div>
      <div style="background:var(--ink);color:var(--parchment);padding:14px 18px;border-left:3px solid var(--gold);">
        <div style="font-family:'IBM Plex Mono',monospace;font-size:9px;letter-spacing:0.15em;color:var(--gold);text-transform:uppercase;margin-bottom:5px;">AP Exam Tip</div>
        <p style="font-size:13px;line-height:1.6;">${r.apTip}</p>
      </div>`;
  }

  function clearFRQ() {
    document.getElementById('frqStudentAnswer').value = '';
    document.getElementById('frqCharCount').textContent = '0 words';
    document.getElementById('frqFeedbackArea').style.display = 'none';
  }

  // ── OFFLINE FRQ GRADER ─────────────────────────────────────────────────────
  async function gradeFRQ() {
    const answer = document.getElementById('frqStudentAnswer').value.trim();
    if (!answer || answer.split(/\s+/).filter(Boolean).length < 15) {
      alert('Please write a more complete response before grading (at least a few sentences).');
      return;
    }
    const prompt = frqPrompts[selectedFRQ];
    document.getElementById('frqFeedbackArea').style.display = 'block';
    document.getElementById('frqLoadingMsg').style.display = 'block';
    document.getElementById('frqLoadingMsg').className = 'ai-loading';
    document.getElementById('frqLoadingMsg').textContent = 'Analyzing your response against AP scoring criteria...';
    document.getElementById('frqFeedbackContent').style.display = 'none';

    // Simulate brief analysis delay for UX
    await new Promise(r => setTimeout(r, 900));

    const result = scoreOfflineFRQ(selectedFRQ, answer);
    renderFRQFeedback(result);

    document.getElementById('frqLoadingMsg').style.display = 'none';
    document.getElementById('frqFeedbackContent').style.display = 'block';
  }

  // Offline rubric-based scoring
  const frqRubrics = [
    { // 0 - Judicial Review
      partA: {
        keywords: [['judicial review','power to strike down','declare unconstitutional','court to invalidate'],['marbury','1803','marshall']],
        hint: 'Part A requires (1) a definition of judicial review AND (2) naming Marbury v. Madison (1803). Make sure both are clearly stated.',
        full: 'Strong work on Part A — you correctly defined judicial review and identified Marbury v. Madison (1803) as the establishing case.',
        partial: 'You addressed part of Part A. To earn full credit, you need both: a clear definition of judicial review AND an explicit identification of Marbury v. Madison (1803).',
        miss: 'Part A: Define judicial review as the power of courts to examine laws/actions and declare them unconstitutional, then identify Marbury v. Madison (1803) as the case that established it.'
      },
      partB: {
        keywordsFor: [['protect','minority','rights','individual','tyranny of majority','majority rule','constitution','fundamental','civil liberties']],
        keywordsAgainst: [['unelected','counter-majoritarian','anti-democratic','no electoral','life tenure','democratic majority','will of the people','elected representatives']],
        hint: 'Part B needs TWO distinct arguments — one FOR (protects rights/minority from majority) and one AGAINST (unelected judges override democratic majorities). Label each clearly.',
        full: 'Excellent Part B — you clearly articulated both the pro-democracy argument (protecting minority rights/individual liberties from majority tyranny) and the anti-democratic critique (unelected, life-tenured judges overriding elected officials).',
        partial: 'You made one strong argument in Part B but the second argument needs more development. Clearly label and distinguish both perspectives — one defending judicial review as protective of rights, one critiquing it as counter-majoritarian.',
        miss: 'Part B: PRO: Judicial review protects individual/minority rights from majority tyranny — democracy requires more than majority rule. CON: Unelected life-tenured judges can strike down laws passed by democratically elected officials — this is counter-majoritarian.'
      },
      partC: {
        keywords: [['article iii','life tenure','good behavior','salary','appointment','confirmation','senate','advice and consent','checks','independence'],['balance','democratic','accountability','elected','amendment','jurisdiction']],
        hint: 'Part C should discuss specific Article III mechanisms — life tenure, salary protection, the appointment/confirmation process — and how they balance independence with accountability.',
        full: 'Strong Part C — you effectively connected Article III\'s design features (life tenure, salary protection, Senate confirmation) to the balance between judicial independence and democratic accountability.',
        partial: 'Your Part C analysis is on the right track. Strengthen it by citing specific Article III provisions (life tenure "during good behavior," salary protection, Senate confirmation process) and explicitly linking each to the independence/accountability tension.',
        miss: 'Part C: Article III balances independence (life tenure "during good behavior," salary protection from Congress) with accountability (presidential appointment + Senate confirmation means elected officials shape the Court\'s composition, and Congress can propose constitutional amendments to override decisions).'
      },
      apTip: 'On the real AP exam, always cite specific constitutional provisions (Article III, Article II §2) and case names. Labeling your parts clearly (A, B, C) and using precise language like "counter-majoritarian" signals AP-level thinking.'
    },
    { // 1 - Court Structure
      partA: {
        keywords: [['district','trial','original','first'],['appeals','circuit','appellate','review'],['supreme','final','highest']],
        hint: 'Part A must describe all three tiers: District Courts (trial/original jurisdiction), Courts of Appeals (appellate review), and the Supreme Court (final arbiter). Name each level.',
        full: 'Great Part A — you accurately described all three tiers of the federal court system: district courts as the trial courts, courts of appeals reviewing lower court decisions, and the Supreme Court as the final arbiter.',
        partial: 'You identified some levels of the federal court system. For full credit, describe all three tiers and each one\'s specific role: 94 district courts (trial), 13 courts of appeals (appellate review), and 1 Supreme Court (final arbiter).',
        miss: 'Part A: The federal court system has three levels — (1) 94 District Courts: trial courts with original jurisdiction; (2) 13 Courts of Appeals: review district court decisions, appellate jurisdiction only; (3) The Supreme Court: final arbiter of federal law, mostly appellate jurisdiction.'
      },
      partB: {
        keywordsFor: [['original','first time','trial','hear','initial']],
        keywordsAgainst: [['appellate','review','appeal','lower court','decision']],
        hint: 'Part B needs a clear definition of BOTH original jurisdiction (court of first instance) AND appellate jurisdiction (reviewing lower court decisions), each with a concrete example.',
        full: 'Excellent Part B — you correctly distinguished original jurisdiction (first to hear the case) from appellate jurisdiction (reviewing lower court decisions) and provided strong examples for each.',
        partial: 'You defined the jurisdiction types but your examples need to be more specific. Try: original = Supreme Court hearing a dispute between two states; appellate = Court of Appeals reviewing a district court criminal conviction.',
        miss: 'Part B: Original jurisdiction = authority to hear a case first (ex: Supreme Court hears suits between states). Appellate jurisdiction = authority to review a lower court\'s decision (ex: Courts of Appeals review district court rulings — no new evidence, only legal questions).'
      },
      partC: {
        keywords: [['life tenure','good behavior','salary','independent','political pressure','federalist','hamilton','78'],['independence','insulate','impartial','neutral']],
        hint: 'Part C should directly cite Article III features — life tenure "during good behavior" and salary protection — and connect them to the Founders\' goal of judicial independence (Federalist No. 78 is a bonus).',
        full: 'Strong Part C — you clearly connected Article III\'s structural features (life tenure, salary protection) to the Founders\' goal of judicial independence from political pressure.',
        partial: 'Your Part C mentions independence but needs stronger connection to specific Article III provisions. Cite life tenure ("during good behavior") and salary protection explicitly — these are the textual features that operationalize the independence goal.',
        miss: 'Part C: Article III reflects the independence goal through: (1) life tenure "during good behavior" — judges cannot be removed for unpopular rulings; (2) salary protection — Congress cannot reduce judicial pay to punish judges. Hamilton argued in Federalist No. 78 these features make the judiciary a reliable guardian of constitutional rights.'
      },
      apTip: 'The AP exam frequently asks you to connect structural features to their purpose. Always ask: WHY was this design choice made? Life tenure isn\'t just a fact — it\'s a deliberate tool for independence. Show you understand the "why."'
    },
    { // 2 - Judicial Appointments
      partA: {
        keywords: [['article ii','president','nominate','senate','advice and consent','confirmation','two','steps']],
        hint: 'Part A must cite Article II and describe both steps: presidential nomination AND Senate advice and consent (confirmation). Both steps are required for full credit.',
        full: 'Great Part A — you correctly described the two-step constitutional process: presidential nomination under Article II and Senate confirmation through advice and consent.',
        partial: 'Your Part A describes the general process but needs to explicitly cite Article II and name both steps: (1) presidential nomination and (2) Senate advice and consent.',
        miss: 'Part A: Article II, Section 2 gives the president power to nominate federal judges, but nominees must be confirmed by the Senate through "Advice and Consent." This two-step process reflects checks and balances between the executive and legislative branches.'
      },
      partB: {
        keywordsFor: [['policy','ideology','philosophy','originalism','living','shape','legacy','future']],
        keywordsAgainst: [['senate','hearings','reject','refuse','filibuster','check','balance','veto','accountability']],
        hint: 'Part B needs TWO things: (1) how nominees reflect presidential priorities (ideology/policy goals), and (2) how the Senate checks presidential power (hearings, rejection, holds). Be specific about both.',
        full: 'Excellent Part B — you clearly explained both how presidents use nominations to advance policy goals (ideological alignment, legacy) and how the Senate exercises its checking function (confirmation hearings, rejection power, holds).',
        partial: 'You addressed one side of Part B well. Develop the other: if you explained presidential motivations, also explain Senate checking mechanisms (hearings, rejections, the Bork precedent), and vice versa.',
        miss: 'Part B: Presidential priorities: Presidents nominate ideologically aligned judges to shape jurisprudence for decades (legacy). Senate check: The Senate Judiciary Committee holds public hearings, can vote down nominees (e.g., Bork 1987), and has even refused to hold hearings (Garland 2016) — all powerful checks on presidential appointment power.'
      },
      partC: {
        keywords: [['experience','aba','credentials','circuit','legal','professional','judge'],['race','gender','diversity','coalition','demographic','religion','geography','political','party']],
        hint: 'Part C requires TWO distinct factors — one legal/professional (judicial experience, ABA rating, credentials) and one political/demographic (race, gender, party loyalty, geographic balance). Name both explicitly.',
        full: 'Strong Part C — you effectively identified both a professional/legal factor and a political/demographic factor with clear explanations of why each matters in the selection process.',
        partial: 'Your Part C identifies factors but blurs the distinction. Make sure one factor is explicitly professional/legal (e.g., prior federal judicial experience, ABA rating) and one is explicitly political/demographic (e.g., gender, race, party loyalty, coalition-building).',
        miss: 'Part C: Legal/professional factor: prior judicial experience (circuit court service signals predictable judicial temperament and reduces confirmation risk). Political/demographic factor: race and gender — presidents consider demographic representation to build political coalitions and signal commitment to diversity (e.g., first Black woman Justice).'
      },
      apTip: 'When the FRQ asks you to "explain," you need more than just naming something — you need a because/therefore chain. "Presidents nominate ideologically aligned judges BECAUSE they want to shape jurisprudence BEYOND their term, THEREFORE nominations are highly political." That structure earns points.'
    },
    { // 3 - Checks on Courts
      partA: {
        keywords: [['amend','amendment','constitutional amendment','overturn','override','congress','jurisdiction','impeach','court packing','enforce','executive'],],
        hint: 'Part A requires naming ONE specific constitutional mechanism (constitutional amendment process, congressional jurisdiction-stripping, impeachment of judges, presidential enforcement power) AND explaining how it limits the Court.',
        full: 'Good Part A — you correctly identified a formal constitutional mechanism limiting the Supreme Court and explained how it operates as a check.',
        partial: 'Your Part A names a limitation but needs a fuller explanation of the constitutional mechanism behind it. How exactly does it work? Which article/amendment authorizes it?',
        miss: 'Part A example: Congress and the states can pass constitutional amendments to override Supreme Court decisions (Art. V). For example, the 16th Amendment reversed Pollock v. Farmers\' Loan (1895) which struck down the income tax. This is the most direct constitutional check on judicial interpretation.'
      },
      partB: {
        keywordsFor: [['constrain','limit','precedent','stare decisis','consistency','stability','predictability','prior','bound']],
        keywordsAgainst: [['overturn','overrule','change','evolve','empower','expand','strike down','reverse','brown','plessy']],
        hint: 'Part B requires BOTH: how stare decisis CONSTRAINS the Court (must follow precedent, promotes stability) AND how it EMPOWERS the Court (precedents accumulate authority; ability to overturn gives the Court policy-making power).',
        full: 'Excellent Part B — you captured both the constraining function of stare decisis (binding precedent promotes consistency and limits discretion) and its empowering dimension (the ability to set and overturn precedent gives the Court enormous policy influence).',
        partial: 'Your Part B addresses one direction well. Make sure you explain the constraining side (lower courts must follow precedent; the Court itself feels pressure not to overturn without strong justification) AND the empowering side (precedents become authoritative law; strategic overturning reshapes policy for generations).',
        miss: 'Part B: Constrains: stare decisis requires courts to follow precedent, promoting stability and predictability — the Court cannot simply reverse course without strong justification (e.g., it took 58 years to overturn Plessy). Empowers: once the Court sets precedent, it becomes the law of the land binding all lower courts, and the power to overturn (as in Brown v. Board) makes the Court a powerful policy-making institution.'
      },
      partC: {
        keywords: [['marbury','mcculloch','lopez','heller','engel','nyt','times','brown','plessy','tinker','gideon','miranda','roe','dobbs','obergefell'],['federal','state','branch','congress','president','executive','legislature','balance','power','federalism']],
        hint: 'Part C requires naming a SPECIFIC case AND explaining how it shifted power between federal/state governments OR between branches. Be precise: name the case, describe the holding, and explain the power shift.',
        full: 'Strong Part C — you correctly named a specific case, described its holding, and clearly explained how the decision affected the balance of power in the constitutional system.',
        partial: 'Your Part C references a case but needs a more explicit explanation of the power shift. State: what was the holding? And how did that directly affect federal vs. state power OR the balance among the three branches?',
        miss: 'Part C example: In McCulloch v. Maryland (1819), the Court ruled states cannot tax federal institutions (affirming federal supremacy) AND that the Necessary and Proper Clause gives Congress broad implied powers. This dramatically expanded federal power over states, establishing the constitutional foundation for most modern federal programs.'
      },
      apTip: 'The AP exam loves "both sides" questions about judicial power. Practice framing stare decisis, judicial review, and judicial independence as having both limits AND strengths — showing nuance earns top scores on FRQs.'
    }
  ];

  function scoreOfflineFRQ(promptIdx, answer) {
    const rubric = frqRubrics[promptIdx];
    const a = answer.toLowerCase();

    // Score Part A: need both keyword groups present
    let scoreA = 0;
    const aGroups = rubric.partA.keywords;
    const aHits = aGroups.filter(group => group.some(kw => a.includes(kw)));
    if (aHits.length >= aGroups.length) scoreA = 1;
    else if (aHits.length >= 1) scoreA = 0; // partial but still 0 for AP scoring

    // Score Part B
    let scoreB = 0;
    if (rubric.partB.keywordsFor && rubric.partB.keywordsAgainst) {
      const bFor = rubric.partB.keywordsFor[0].some(kw => a.includes(kw));
      const bAgainst = rubric.partB.keywordsAgainst[0].some(kw => a.includes(kw));
      if (bFor && bAgainst) scoreB = 2;
      else if (bFor || bAgainst) scoreB = 1;
    }

    // Score Part C
    let scoreC = 0;
    const cGroups = rubric.partC.keywords;
    const cHits = cGroups.filter(group => group.some(kw => a.includes(kw)));
    if (cHits.length >= 2) scoreC = 2;
    else if (cHits.length === 1) scoreC = 1;

    const total = scoreA + scoreB + scoreC;
    const wordCount = answer.trim().split(/\s+/).filter(Boolean).length;

    // Build feedback text per part
    const partAFeedback = scoreA === 1 ? rubric.partA.full :
      aHits.length > 0 ? rubric.partA.partial : rubric.partA.miss;

    let partBFeedback;
    if (rubric.partB.keywordsFor) {
      const bFor = rubric.partB.keywordsFor[0].some(kw => a.includes(kw));
      const bAgainst = rubric.partB.keywordsAgainst[0].some(kw => a.includes(kw));
      partBFeedback = (bFor && bAgainst) ? rubric.partB.hint.replace('needs TWO distinct','has ✓') :
        (bFor || bAgainst) ? rubric.partB.partial : rubric.partB.miss;
      if (scoreB === 2) partBFeedback = rubric.partB.full || rubric.partB.hint;
      if (scoreB === 1) partBFeedback = rubric.partB.partial;
      if (scoreB === 0) partBFeedback = rubric.partB.miss;
    }

    const partCFeedback = scoreC === 2 ? rubric.partC.full :
      scoreC === 1 ? rubric.partC.partial : rubric.partC.miss;

    // Strengths
    const strengths = wordCount >= 100
      ? 'Your response is well-developed with sufficient detail. ' + (total >= 3 ? 'You demonstrated knowledge of key concepts and AP terminology.' : 'You engaged substantively with the prompt.')
      : 'You identified relevant concepts. For the AP exam, aim for 120–180 words minimum — more developed responses earn more points.';

    // Improvements
    const missedParts = [];
    if (scoreA < 1) missedParts.push('Part A (definition + case identification)');
    if (scoreB < 2) missedParts.push('Part B (both perspectives clearly labeled)');
    if (scoreC < 2) missedParts.push('Part C (specific evidence + power analysis)');
    const improvements = missedParts.length === 0
      ? 'Excellent work — focus on using precise AP vocabulary (e.g., "counter-majoritarian," "stare decisis," "original jurisdiction") to signal exam readiness.'
      : 'To improve: ' + missedParts.join('; ') + '. Always label your parts clearly (A, B, C) and use specific case names and constitutional articles as evidence.';

    return { scoreA, scoreB, scoreC, totalScore: total, maxScore: 5,
      partAFeedback, partBFeedback, partCFeedback, strengths, improvements, apTip: rubric.apTip };
  }

  // ── OFFLINE CASE EXPLORER ──────────────────────────────────────────────────
  const caseDatabase = {
    'marbury': {
      name: 'Marbury v. Madison (1803)',
      year: 1803, topic: 'Judicial Review',
      facts: 'Outgoing President Adams appointed William Marbury as a Justice of the Peace in the final hours of his presidency. His Secretary of State (John Marshall, who later wrote the opinion) failed to deliver the commission. When Jefferson took office, his Secretary of State James Madison refused to deliver it.',
      question: 'Did Marbury have a right to his commission, and could the Supreme Court order its delivery?',
      holding: 'Chief Justice Marshall ruled that while Marbury was entitled to his commission, the Supreme Court lacked jurisdiction to order its delivery because the provision of the Judiciary Act of 1789 granting that power was unconstitutional — it conflicted with Article III\'s definition of the Court\'s original jurisdiction.',
      significance: 'Established the doctrine of <strong>judicial review</strong> — the power of courts to strike down laws that conflict with the Constitution. Marshall\'s famous line: "It is emphatically the province and duty of the Judicial Department to say what the law is."',
      apConnection: 'This is the single most important case in AP Gov. Know: (1) how Marshall established judicial review without directly confronting Jefferson, (2) the political genius of ruling against Marbury while claiming a larger power, (3) its connection to Federalist No. 78 (Hamilton\'s defense of judicial independence), and (4) that judicial review is NOT explicitly in the Constitution.',
      frqTip: 'Any FRQ on judicial review, checks and balances, or the judiciary\'s role WILL likely reference this case. Be ready to explain both the facts AND the strategic reasoning behind Marshall\'s decision.'
    },
    'mcculloch': {
      name: 'McCulloch v. Maryland (1819)',
      year: 1819, topic: 'Federalism / Implied Powers',
      facts: 'Maryland imposed a tax on the Second Bank of the United States. James McCulloch, the bank\'s cashier, refused to pay. Maryland argued Congress had no authority to create a national bank because it wasn\'t listed in the Constitution\'s enumerated powers.',
      question: '(1) Did Congress have the power to create a national bank? (2) Could a state tax a federal institution?',
      holding: '(1) YES — Congress has implied powers under the Necessary and Proper Clause to carry out its enumerated powers. Creating a bank is a legitimate means to execute powers like taxing, borrowing money, and regulating commerce. (2) NO — "the power to tax involves the power to destroy." States cannot tax federal institutions because federal law is supreme.',
      significance: 'Established broad <strong>implied powers</strong> for Congress under the Necessary and Proper Clause and reinforced federal supremacy over states under the Supremacy Clause. Foundation for nearly all modern expansions of federal power.',
      apConnection: 'Key for federalism FRQs. Know: (1) the Necessary and Proper Clause (Art. I §8) gives Congress implied powers beyond its enumerated list; (2) "the power to tax is the power to destroy" — states cannot interfere with federal functions; (3) this case is the constitutional basis for the modern federal government\'s extensive authority.',
      frqTip: 'When asked about federalism or congressional power, cite McCulloch and connect it to the Necessary and Proper Clause. Example: "Congress\'s power to [regulate health care / create the Federal Reserve / etc.] derives from implied powers established in McCulloch v. Maryland."'
    },
    'lopez': {
      name: 'United States v. Lopez (1995)',
      year: 1995, topic: 'Commerce Clause / Federalism',
      facts: 'Alfonso Lopez, a 12th-grader, brought a handgun to his San Antonio high school in violation of the federal Gun-Free School Zones Act. The federal government prosecuted under the Commerce Clause, arguing guns near schools affect interstate commerce.',
      question: 'Did the Gun-Free School Zones Act exceed Congress\'s Commerce Clause power?',
      holding: 'YES — the Supreme Court (5-4) struck down the Act. Gun possession at a school is a non-economic, local activity that does not "substantially affect" interstate commerce. For the first time in 60 years, the Court limited congressional Commerce Clause authority.',
      significance: 'Reaffirmed that Congress\'s Commerce Clause power has <strong>limits</strong>. The Court identified three categories of activity Congress can regulate: (1) channels of interstate commerce, (2) instrumentalities of interstate commerce, (3) activities that substantially affect interstate commerce. Gun possession in school zones fell into none of these.',
      apConnection: 'Critical for federalism balance-of-power questions. Shows the Court acting as a check on congressional power. Contrast with McCulloch (broad federal power) — Lopez shows the pendulum can swing back toward state authority. Know the "substantial effects" test.',
      frqTip: 'Lopez is often paired with McCulloch on federalism FRQs. Use Lopez to show that federal power, while broad, is not unlimited — and that the Court will enforce those limits.'
    },
    'heller': {
      name: 'District of Columbia v. Heller (2008)',
      year: 2008, topic: '2nd Amendment / Individual Rights',
      facts: 'Dick Heller, a D.C. special police officer, applied to register a handgun to keep at home and was denied. D.C. law banned handgun possession and required all firearms to be kept unloaded and disassembled. He challenged the law as a violation of the 2nd Amendment.',
      question: 'Does the 2nd Amendment protect an individual\'s right to possess a firearm for traditionally lawful purposes, such as self-defense?',
      holding: 'YES — the 2nd Amendment protects an <strong>individual right</strong> to possess firearms independent of service in a militia, particularly for self-defense in the home. D.C.\'s handgun ban violated this right.',
      significance: 'Settled a long-standing debate: the 2nd Amendment protects individual gun ownership, not just militia service. However, the Court also noted that the right is not unlimited — regulations on carrying in certain places, by certain people, or of certain weapons remain constitutional.',
      apConnection: 'Key for civil liberties and incorporation questions. Know: (1) Heller applied to federal law (D.C. is federal territory); (2) McDonald v. Chicago (2010) extended Heller to states via 14th Amendment incorporation; (3) this is an example of the Court using originalism to interpret the Constitution.',
      frqTip: 'Always connect Heller to McDonald v. Chicago — together they establish the full scope of 2nd Amendment protections. Also note this as an example of originalist interpretation (Justice Scalia wrote the majority opinion).'
    },
    'mcdonald': {
      name: 'McDonald v. City of Chicago (2010)',
      year: 2010, topic: '2nd Amendment / Incorporation',
      facts: 'Otis McDonald challenged Chicago\'s handgun ban following the Heller decision, arguing the 2nd Amendment should apply to states just as it applies to the federal government.',
      question: 'Does the 2nd Amendment apply to state and local governments through the 14th Amendment?',
      holding: 'YES — the 2nd Amendment is incorporated against state and local governments via the Due Process Clause of the 14th Amendment. States cannot ban handguns.',
      significance: 'Extended Heller to all 50 states, completing the nationalization of the individual right to bear arms. Part of the broader <strong>selective incorporation</strong> doctrine through which most Bill of Rights protections have been applied to states.',
      apConnection: 'Critical for understanding selective incorporation. Know that the 14th Amendment\'s Due Process Clause is the vehicle through which the Bill of Rights applies to states. McDonald + Heller together = complete 2nd Amendment framework for AP.',
      frqTip: 'On incorporation questions, walk through the logic: the Bill of Rights originally applied only to the federal government (Barron v. Baltimore, 1833); the 14th Amendment changed this; McDonald illustrates how that process works.'
    },
    'engel': {
      name: 'Engel v. Vitale (1962)',
      year: 1962, topic: 'Establishment Clause / Religion in Schools',
      facts: 'The New York State Board of Regents composed a brief nondenominational prayer for recitation in public schools: "Almighty God, we acknowledge our dependence upon Thee." The parents of 10 students sued, arguing it violated the Establishment Clause.',
      question: 'Does state-sponsored prayer in public schools violate the Establishment Clause of the 1st Amendment?',
      holding: 'YES — school-sponsored prayer violates the Establishment Clause even if it is nondenominational and student participation is voluntary. Government officials composing an official prayer constitutes an unconstitutional establishment of religion.',
      significance: 'Established that the <strong>Establishment Clause</strong> prohibits government-sponsored religious activity in public schools. One of the most controversial decisions in Court history — launched decades of debate about religion\'s role in public life.',
      apConnection: 'Key for 1st Amendment / civil liberties FRQs. Know the Establishment Clause test and how Engel is applied. Also understand that the Court incorporated the Establishment Clause to states (the school was a state institution). Contrast: students can still pray privately.',
      frqTip: 'When discussing the Establishment Clause, use Engel to show the principle: government cannot sponsor, organize, or encourage religious practice — even nondenominationally. This comes up on both civil liberties FRQs and court power questions.'
    },
    'nyt': {
      name: 'New York Times Co. v. United States (1971)',
      year: 1971, topic: '1st Amendment / Prior Restraint / Free Press',
      facts: 'The Nixon administration sought to stop the New York Times and Washington Post from publishing the "Pentagon Papers" — a classified Defense Department study of U.S. involvement in Vietnam. The government argued publication would endanger national security.',
      question: 'Could the government prevent publication of the Pentagon Papers through prior restraint?',
      holding: 'NO — the government failed to meet the heavy burden required to justify prior restraint. In a 6-3 per curiam decision, the Court ruled the injunction violated the 1st Amendment\'s protections for freedom of the press.',
      significance: 'Strongly reaffirmed the presumption against <strong>prior restraint</strong> — government censorship of expression before it is published. The press has broad freedom to publish even sensitive government information unless the government can prove certain, direct, and immediate harm.',
      apConnection: 'Essential for 1st Amendment FRQs on press freedom. Know: (1) prior restraint is the most serious 1st Amendment violation; (2) government bears an extremely heavy burden to justify it; (3) national security arguments alone are insufficient without proof of direct, immediate harm.',
      frqTip: 'Pair NYT v. U.S. with the concept of "prior restraint" — governments may be able to punish speech after the fact, but they face a nearly insurmountable presumption against preventing it beforehand. This distinction is AP-exam gold.'
    }
  };

  // Question answering logic
  function answerCaseQuestion(q) {
    const ql = q.toLowerCase();

    // Find which case(s) are being asked about
    const caseMatches = {
      'marbury': ['marbury','1803'],
      'mcculloch': ['mcculloch','maryland','implied power','necessary and proper','1819'],
      'lopez': ['lopez','gun-free','school zone','1995'],
      'heller': ['heller','district of columbia','d.c.','2008','second amendment','2nd amendment'],
      'mcdonald': ['mcdonald','chicago','2010','incorporation'],
      'engel': ['engel','vitale','prayer','school prayer','1962','establishment'],
      'nyt': ['new york times','pentagon papers','prior restraint','1971','nyt']
    };

    let matchedKey = null;
    for (const [key, keywords] of Object.entries(caseMatches)) {
      if (keywords.some(kw => ql.includes(kw))) { matchedKey = key; break; }
    }

    if (!matchedKey) {
      // Generic AP-focused answer
      return `<p>I don't have a specific case matching your question in my database, but here are the <strong>AP Required Cases for the Judiciary</strong> I can help you with:</p>
        <ul style="margin:10px 0 0 16px; line-height:2;">
          <li><em>Marbury v. Madison</em> (1803) — Judicial Review</li>
          <li><em>McCulloch v. Maryland</em> (1819) — Implied Powers / Federalism</li>
          <li><em>United States v. Lopez</em> (1995) — Commerce Clause Limits</li>
          <li><em>District of Columbia v. Heller</em> (2008) — 2nd Amendment</li>
          <li><em>McDonald v. Chicago</em> (2010) — Incorporation</li>
          <li><em>Engel v. Vitale</em> (1962) — Establishment Clause</li>
          <li><em>New York Times v. United States</em> (1971) — Prior Restraint</li>
        </ul>
        <p style="margin-top:12px;">Click one of the quick buttons above or rephrase your question to include the case name.</p>`;
    }

    const c = caseDatabase[matchedKey];

    // Determine question type and return targeted answer
    const isFacts = ql.includes('fact') || ql.includes('what happened') || ql.includes('background') || ql.includes('story');
    const isHolding = ql.includes('hold') || ql.includes('decide') || ql.includes('rule') || ql.includes('outcome') || ql.includes('result');
    const isSignificance = ql.includes('significant') || ql.includes('matter') || ql.includes('important') || ql.includes('impact') || ql.includes('why');
    const isFRQ = ql.includes('frq') || ql.includes('exam') || ql.includes('ap') || ql.includes('test') || ql.includes('write') || ql.includes('essay');
    const isAll = ql.includes('everything') || ql.includes('all') || ql.includes('tell me about') || ql.includes('need to know') || ql.includes('overview') || ql.includes('summary');

    if (isAll || (!isFacts && !isHolding && !isSignificance && !isFRQ)) {
      return `
        <div style="margin-bottom:14px;"><strong style="font-size:16px;">${c.name}</strong> &nbsp;<span style="font-family:'IBM Plex Mono',monospace;font-size:10px;letter-spacing:0.1em;color:var(--muted);text-transform:uppercase;">${c.topic}</span></div>
        <div style="margin-bottom:12px;"><span style="font-family:'IBM Plex Mono',monospace;font-size:10px;color:#b5540a;text-transform:uppercase;letter-spacing:0.1em;display:block;margin-bottom:4px;">Background</span>${c.facts}</div>
        <div style="margin-bottom:12px;"><span style="font-family:'IBM Plex Mono',monospace;font-size:10px;color:#b5540a;text-transform:uppercase;letter-spacing:0.1em;display:block;margin-bottom:4px;">Constitutional Question</span><em>${c.question}</em></div>
        <div style="margin-bottom:12px;"><span style="font-family:'IBM Plex Mono',monospace;font-size:10px;color:#b5540a;text-transform:uppercase;letter-spacing:0.1em;display:block;margin-bottom:4px;">Holding</span>${c.holding}</div>
        <div style="margin-bottom:12px;"><span style="font-family:'IBM Plex Mono',monospace;font-size:10px;color:#b5540a;text-transform:uppercase;letter-spacing:0.1em;display:block;margin-bottom:4px;">Significance</span>${c.significance}</div>
        <div style="margin-bottom:12px;"><span style="font-family:'IBM Plex Mono',monospace;font-size:10px;color:var(--blue);text-transform:uppercase;letter-spacing:0.1em;display:block;margin-bottom:4px;">AP Exam Connection</span>${c.apConnection}</div>
        <div style="background:var(--ink);color:var(--parchment);padding:12px 16px;border-left:3px solid var(--gold);margin-top:4px;"><span style="font-family:'IBM Plex Mono',monospace;font-size:9px;color:var(--gold);text-transform:uppercase;letter-spacing:0.1em;display:block;margin-bottom:4px;">FRQ Tip</span>${c.frqTip}</div>`;
    }
    if (isFacts) return `<strong>${c.name} — Background</strong><p style="margin-top:8px;">${c.facts}</p><p style="margin-top:8px;"><em>Constitutional question: ${c.question}</em></p>`;
    if (isHolding) return `<strong>${c.name} — Holding</strong><p style="margin-top:8px;">${c.holding}</p>`;
    if (isSignificance) return `<strong>${c.name} — Significance</strong><p style="margin-top:8px;">${c.significance}</p><p style="margin-top:10px;">${c.apConnection}</p>`;
    if (isFRQ) return `<strong>${c.name} — AP Exam & FRQ Guide</strong><p style="margin-top:8px;">${c.apConnection}</p><div style="background:var(--ink);color:var(--parchment);padding:12px 16px;border-left:3px solid var(--gold);margin-top:12px;"><span style="font-family:'IBM Plex Mono',monospace;font-size:9px;color:var(--gold);text-transform:uppercase;letter-spacing:0.1em;display:block;margin-bottom:4px;">FRQ Tip</span>${c.frqTip}</div>`;
  }

  function quickCase(caseName) {
    document.getElementById('caseQuestion').value = `Tell me everything I need to know about ${caseName} for the AP exam`;
    exploreCase();
  }

  function exploreCase() {
    const q = document.getElementById('caseQuestion').value.trim();
    if (!q) return;

    document.getElementById('caseAnswerArea').style.display = 'block';
    document.getElementById('caseLoadingMsg').style.display = 'none';
    document.getElementById('caseAnswerContent').style.display = 'block';
    document.getElementById('caseChatHistory').style.display = 'block';

    const answer = answerCaseQuestion(q);
    document.getElementById('caseAnswerContent').innerHTML = `
      <div class="case-answer-block">
        <div class="case-q-label">Q: ${q}</div>
        <div>${answer}</div>
      </div>`;
  }

  function followUpCase() {
    const q = document.getElementById('caseFollowup').value.trim();
    if (!q) return;
    document.getElementById('caseFollowup').value = '';

    const answer = answerCaseQuestion(q);
    const newBlock = document.createElement('div');
    newBlock.className = 'case-answer-block';
    newBlock.innerHTML = `<div class="case-q-label">Follow-up: ${q}</div><div>${answer}</div>`;
    document.getElementById('caseAnswerContent').appendChild(newBlock);
    newBlock.scrollIntoView({ behavior: 'smooth', block: 'nearest' });
  }
</script>
</body>
</html>
