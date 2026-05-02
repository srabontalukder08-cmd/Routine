<!DOCTYPE html>
<html lang="bn">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>১ মাসের Video Editing Routine</title>
<style>
  @import url('https://fonts.googleapis.com/css2?family=Tiro+Bangla&family=Bebas+Neue&family=DM+Mono:wght@400;500&display=swap');

  :root {
    --bg: #0a0a0f;
    --surface: #12121a;
    --card: #1a1a26;
    --border: #2a2a3d;
    --pr: #9b59f5;
    --ae: #00c8ff;
    --gold: #f5c842;
    --text: #e8e8f0;
    --muted: #6b6b8a;
    --week1: #9b59f5;
    --week2: #00c8ff;
    --week3: #f5c842;
    --week4: #ff6b6b;
  }

  * { margin: 0; padding: 0; box-sizing: border-box; }

  body {
    background: var(--bg);
    color: var(--text);
    font-family: 'Tiro Bangla', serif;
    line-height: 1.7;
    min-height: 100vh;
    overflow-x: hidden;
  }

  /* Animated background */
  body::before {
    content: '';
    position: fixed;
    inset: 0;
    background:
      radial-gradient(ellipse 60% 40% at 20% 10%, rgba(155,89,245,0.12) 0%, transparent 60%),
      radial-gradient(ellipse 50% 50% at 80% 80%, rgba(0,200,255,0.08) 0%, transparent 60%),
      radial-gradient(ellipse 40% 30% at 60% 30%, rgba(245,200,66,0.05) 0%, transparent 50%);
    pointer-events: none;
    z-index: 0;
  }

  .container {
    max-width: 860px;
    margin: 0 auto;
    padding: 40px 20px 80px;
    position: relative;
    z-index: 1;
  }

  /* HEADER */
  header {
    text-align: center;
    margin-bottom: 60px;
  }

  .badge {
    display: inline-block;
    background: linear-gradient(135deg, rgba(155,89,245,0.2), rgba(0,200,255,0.2));
    border: 1px solid rgba(155,89,245,0.4);
    padding: 6px 18px;
    border-radius: 100px;
    font-family: 'DM Mono', monospace;
    font-size: 11px;
    letter-spacing: 3px;
    text-transform: uppercase;
    color: var(--ae);
    margin-bottom: 20px;
    animation: fadeSlideDown 0.6s ease both;
  }

  h1 {
    font-family: 'Bebas Neue', sans-serif;
    font-size: clamp(42px, 8vw, 72px);
    line-height: 1;
    letter-spacing: 2px;
    background: linear-gradient(135deg, #9b59f5 0%, #00c8ff 50%, #f5c842 100%);
    -webkit-background-clip: text;
    -webkit-text-fill-color: transparent;
    background-clip: text;
    animation: fadeSlideDown 0.7s ease 0.1s both;
  }

  .subtitle {
    font-family: 'Tiro Bangla', serif;
    color: var(--muted);
    font-size: 15px;
    margin-top: 12px;
    animation: fadeSlideDown 0.7s ease 0.2s both;
  }

  /* GOAL STRIP */
  .goal-strip {
    display: grid;
    grid-template-columns: repeat(3, 1fr);
    gap: 12px;
    margin-bottom: 50px;
    animation: fadeSlideDown 0.7s ease 0.3s both;
  }

  .goal-item {
    background: var(--card);
    border: 1px solid var(--border);
    border-radius: 12px;
    padding: 16px;
    text-align: center;
  }

  .goal-item .icon {
    font-size: 22px;
    margin-bottom: 6px;
  }

  .goal-item .label {
    font-family: 'DM Mono', monospace;
    font-size: 10px;
    letter-spacing: 2px;
    text-transform: uppercase;
    color: var(--muted);
    margin-bottom: 4px;
  }

  .goal-item .value {
    font-size: 13px;
    color: var(--text);
  }

  /* WEEK SECTION */
  .week-section {
    margin-bottom: 40px;
    animation: fadeSlideUp 0.6s ease both;
  }

  .week-header {
    display: flex;
    align-items: center;
    gap: 14px;
    margin-bottom: 20px;
    padding-bottom: 12px;
    border-bottom: 1px solid var(--border);
  }

  .week-number {
    font-family: 'Bebas Neue', sans-serif;
    font-size: 48px;
    line-height: 1;
    opacity: 0.15;
    min-width: 60px;
  }

  .week-info {}

  .week-tag {
    font-family: 'DM Mono', monospace;
    font-size: 10px;
    letter-spacing: 3px;
    text-transform: uppercase;
    padding: 3px 10px;
    border-radius: 4px;
    display: inline-block;
    margin-bottom: 4px;
  }

  .week-title {
    font-family: 'Tiro Bangla', serif;
    font-size: 17px;
    font-weight: 700;
    color: var(--text);
  }

  /* DAY CARDS */
  .days-grid {
    display: flex;
    flex-direction: column;
    gap: 8px;
  }

  .day-card {
    background: var(--card);
    border: 1px solid var(--border);
    border-radius: 12px;
    overflow: hidden;
    transition: border-color 0.2s, transform 0.2s;
  }

  .day-card:hover {
    transform: translateX(4px);
  }

  .day-card-inner {
    display: grid;
    grid-template-columns: 80px 1fr auto;
    align-items: center;
    gap: 16px;
    padding: 14px 18px;
  }

  .day-label {
    font-family: 'DM Mono', monospace;
    font-size: 11px;
    letter-spacing: 1px;
    text-transform: uppercase;
  }

  .day-name {
    font-size: 12px;
    color: var(--muted);
    margin-top: 2px;
  }

  .day-content {}

  .day-title {
    font-size: 14px;
    color: var(--text);
    margin-bottom: 2px;
  }

  .day-details {
    font-size: 12px;
    color: var(--muted);
    font-family: 'DM Mono', monospace;
  }

  .day-duration {
    font-family: 'DM Mono', monospace;
    font-size: 11px;
    padding: 4px 10px;
    border-radius: 6px;
    white-space: nowrap;
  }

  .rest-day {
    background: rgba(107,107,138,0.05);
  }

  .rest-day .day-title {
    color: var(--muted);
    font-style: italic;
  }

  /* COLOR THEMES PER WEEK */
  .w1 .week-number { color: var(--week1); }
  .w1 .week-tag { background: rgba(155,89,245,0.15); color: var(--week1); border: 1px solid rgba(155,89,245,0.3); }
  .w1 .day-card:hover { border-color: rgba(155,89,245,0.4); }
  .w1 .day-label { color: var(--week1); }
  .w1 .day-duration { background: rgba(155,89,245,0.12); color: var(--week1); }

  .w2 .week-number { color: var(--week2); }
  .w2 .week-tag { background: rgba(0,200,255,0.12); color: var(--week2); border: 1px solid rgba(0,200,255,0.3); }
  .w2 .day-card:hover { border-color: rgba(0,200,255,0.4); }
  .w2 .day-label { color: var(--week2); }
  .w2 .day-duration { background: rgba(0,200,255,0.10); color: var(--week2); }

  .w3 .week-number { color: var(--week3); }
  .w3 .week-tag { background: rgba(245,200,66,0.12); color: var(--week3); border: 1px solid rgba(245,200,66,0.3); }
  .w3 .day-card:hover { border-color: rgba(245,200,66,0.4); }
  .w3 .day-label { color: var(--week3); }
  .w3 .day-duration { background: rgba(245,200,66,0.10); color: var(--week3); }

  .w4 .week-number { color: var(--week4); }
  .w4 .week-tag { background: rgba(255,107,107,0.12); color: var(--week4); border: 1px solid rgba(255,107,107,0.3); }
  .w4 .day-card:hover { border-color: rgba(255,107,107,0.4); }
  .w4 .day-label { color: var(--week4); }
  .w4 .day-duration { background: rgba(255,107,107,0.10); color: var(--week4); }

  /* TIPS SECTION */
  .tips-section {
    margin-top: 50px;
    animation: fadeSlideUp 0.6s ease 0.4s both;
  }

  .tips-title {
    font-family: 'Bebas Neue', sans-serif;
    font-size: 28px;
    letter-spacing: 2px;
    color: var(--gold);
    margin-bottom: 16px;
  }

  .tips-grid {
    display: grid;
    grid-template-columns: 1fr 1fr;
    gap: 10px;
  }

  .tip-card {
    background: var(--card);
    border: 1px solid var(--border);
    border-radius: 10px;
    padding: 14px 16px;
    display: flex;
    gap: 10px;
    align-items: flex-start;
  }

  .tip-icon {
    font-size: 18px;
    flex-shrink: 0;
    margin-top: 2px;
  }

  .tip-text {
    font-size: 13px;
    color: var(--muted);
    line-height: 1.6;
  }

  .tip-text strong {
    color: var(--text);
    display: block;
    margin-bottom: 2px;
    font-size: 13px;
  }

  /* DAILY SCHEDULE */
  .schedule-box {
    background: var(--card);
    border: 1px solid rgba(155,89,245,0.3);
    border-radius: 14px;
    padding: 24px;
    margin-bottom: 40px;
    animation: fadeSlideUp 0.6s ease 0.35s both;
  }

  .schedule-title {
    font-family: 'Bebas Neue', sans-serif;
    font-size: 22px;
    letter-spacing: 2px;
    color: var(--pr);
    margin-bottom: 16px;
  }

  .schedule-row {
    display: grid;
    grid-template-columns: 110px 1fr;
    gap: 12px;
    padding: 8px 0;
    border-bottom: 1px solid rgba(255,255,255,0.04);
    align-items: center;
  }

  .schedule-row:last-child { border-bottom: none; }

  .sched-time {
    font-family: 'DM Mono', monospace;
    font-size: 11px;
    color: var(--pr);
    letter-spacing: 1px;
  }

  .sched-act {
    font-size: 13px;
    color: var(--text);
  }

  /* FOOTER */
  .footer {
    text-align: center;
    margin-top: 60px;
    padding-top: 30px;
    border-top: 1px solid var(--border);
  }

  .footer-motto {
    font-family: 'Bebas Neue', sans-serif;
    font-size: 32px;
    letter-spacing: 3px;
    background: linear-gradient(90deg, var(--pr), var(--ae));
    -webkit-background-clip: text;
    -webkit-text-fill-color: transparent;
    background-clip: text;
  }

  .footer-sub {
    font-size: 13px;
    color: var(--muted);
    margin-top: 8px;
  }

  /* ANIMATIONS */
  @keyframes fadeSlideDown {
    from { opacity: 0; transform: translateY(-20px); }
    to { opacity: 1; transform: translateY(0); }
  }

  @keyframes fadeSlideUp {
    from { opacity: 0; transform: translateY(20px); }
    to { opacity: 1; transform: translateY(0); }
  }

  .week-section:nth-child(1) { animation-delay: 0.3s; }
  .week-section:nth-child(2) { animation-delay: 0.4s; }
  .week-section:nth-child(3) { animation-delay: 0.5s; }
  .week-section:nth-child(4) { animation-delay: 0.6s; }

  @media (max-width: 600px) {
    .tips-grid { grid-template-columns: 1fr; }
    .goal-strip { grid-template-columns: 1fr 1fr; }
    .day-card-inner { grid-template-columns: 60px 1fr; }
    .day-duration { display: none; }
  }
</style>
</head>
<body>
<div class="container">

  <!-- HEADER -->
  <header>
    <div class="badge">🎬 1 Month Mastery Plan</div>
    <h1>VIDEO EDITING<br>PRO ROUTINE</h1>
    <p class="subtitle">Adobe Premiere Pro + After Effects · ৩০ দিনে Freelancer হওয়ার রোডম্যাপ</p>
  </header>

  <!-- GOAL STRIP -->
  <div class="goal-strip">
    <div class="goal-item">
      <div class="icon">🎯</div>
      <div class="label">লক্ষ্য</div>
      <div class="value">১ মাসে Pro Skill</div>
    </div>
    <div class="goal-item">
      <div class="icon">⏱️</div>
      <div class="label">দৈনিক সময়</div>
      <div class="value">৫–৬ ঘণ্টা</div>
    </div>
    <div class="goal-item">
      <div class="icon">💼</div>
      <div class="label">২য় মাস থেকে</div>
      <div class="value">Client Work শুরু</div>
    </div>
  </div>

  <!-- DAILY SCHEDULE -->
  <div class="schedule-box">
    <div class="schedule-title">⚡ প্রতিদিনের টাইম টেবিল</div>
    <div class="schedule-row">
      <span class="sched-time">সকাল ৮টা</span>
      <span class="sched-act">ঘুম থেকে উঠুন, ফ্রেশ হন, হালকা নাস্তা করুন</span>
    </div>
    <div class="schedule-row">
      <span class="sched-time">৯টা – ১১টা</span>
      <span class="sched-act">📺 Tutorial দেখুন (নোট নিন)</span>
    </div>
    <div class="schedule-row">
      <span class="sched-time">১১টা – ১টা</span>
      <span class="sched-act">💻 Practice করুন (যা দেখলেন সেটা বানান)</span>
    </div>
    <div class="schedule-row">
      <span class="sched-time">১টা – ৩টা</span>
      <span class="sched-act">🍽️ লাঞ্চ + বিশ্রাম + ঘুরে আসুন</span>
    </div>
    <div class="schedule-row">
      <span class="sched-time">৩টা – ৫টা</span>
      <span class="sched-act">🔁 আজকের কাজ Review করুন + Project বানান</span>
    </div>
    <div class="schedule-row">
      <span class="sched-time">৫টা – ৬টা</span>
      <span class="sched-act">📱 YouTube Shorts / Reels দেখুন inspiration এর জন্য</span>
    </div>
    <div class="schedule-row">
      <span class="sched-time">রাত ৯টা</span>
      <span class="sched-act">📓 কাল কী শিখবেন লিখে রাখুন</span>
    </div>
  </div>

  <!-- WEEK 1 -->
  <div class="week-section w1">
    <div class="week-header">
      <div class="week-number">01</div>
      <div class="week-info">
        <span class="week-tag">Premiere Pro Foundation</span>
        <div class="week-title">🎬 সপ্তাহ ১ — Premiere Pro এর ভিত তৈরি</div>
      </div>
    </div>
    <div class="days-grid">
      <div class="day-card">
        <div class="day-card-inner">
          <div><div class="day-label">Day 1</div><div class="day-name">রবিবার</div></div>
          <div class="day-content">
            <div class="day-title">Interface, Project Setup, Import & Workspace</div>
            <div class="day-details">Panel চেনা · Sequence Settings · Bin organize করা</div>
          </div>
          <div class="day-duration">৫ ঘণ্টা</div>
        </div>
      </div>
      <div class="day-card">
        <div class="day-card-inner">
          <div><div class="day-label">Day 2</div><div class="day-name">সোমবার</div></div>
          <div class="day-content">
            <div class="day-title">Basic Cutting — Timeline Editing</div>
            <div class="day-details">Razor Tool · Trim · Ripple Edit · Slip & Slide</div>
          </div>
          <div class="day-duration">৫ ঘণ্টা</div>
        </div>
      </div>
      <div class="day-card">
        <div class="day-card-inner">
          <div><div class="day-label">Day 3</div><div class="day-name">মঙ্গলবার</div></div>
          <div class="day-content">
            <div class="day-title">Audio Editing + Transitions</div>
            <div class="day-details">Audio Mixer · Fade in/out · Jump Cut · Cross Dissolve</div>
          </div>
          <div class="day-duration">৫ ঘণ্টা</div>
        </div>
      </div>
      <div class="day-card">
        <div class="day-card-inner">
          <div><div class="day-label">Day 4</div><div class="day-name">বুধবার</div></div>
          <div class="day-content">
            <div class="day-title">Color Correction — Lumetri Color</div>
            <div class="day-details">Exposure · Contrast · White Balance · Curves</div>
          </div>
          <div class="day-duration">৫ ঘণ্টা</div>
        </div>
      </div>
      <div class="day-card">
        <div class="day-card-inner">
          <div><div class="day-label">Day 5</div><div class="day-name">বৃহস্পতিবার</div></div>
          <div class="day-content">
            <div class="day-title">Color Grading + LUT Apply</div>
            <div class="day-details">Cinematic look · Free LUT download · Custom grading</div>
          </div>
          <div class="day-duration">৫ ঘণ্টা</div>
        </div>
      </div>
      <div class="day-card">
        <div class="day-card-inner">
          <div><div class="day-label">Day 6</div><div class="day-name">শুক্রবার</div></div>
          <div class="day-content">
            <div class="day-title">Text, Titles & Lower Thirds</div>
            <div class="day-details">Essential Graphics · Animated Title · Caption</div>
          </div>
          <div class="day-duration">৫ ঘণ্টা</div>
        </div>
      </div>
      <div class="day-card rest-day">
        <div class="day-card-inner">
          <div><div class="day-label">Day 7</div><div class="day-name">শনিবার</div></div>
          <div class="day-content">
            <div class="day-title">🔁 Week Review + ১টা পুরো ভিডিও এডিট করুন</div>
            <div class="day-details">Export Settings · YouTube/Instagram Format</div>
          </div>
          <div class="day-duration">৪ ঘণ্টা</div>
        </div>
      </div>
    </div>
  </div>

  <!-- WEEK 2 -->
  <div class="week-section w2">
    <div class="week-header">
      <div class="week-number">02</div>
      <div class="week-info">
        <span class="week-tag">After Effects Basics</span>
        <div class="week-title">✨ সপ্তাহ ২ — After Effects এ প্রবেশ</div>
      </div>
    </div>
    <div class="days-grid">
      <div class="day-card">
        <div class="day-card-inner">
          <div><div class="day-label">Day 8</div><div class="day-name">রবিবার</div></div>
          <div class="day-content">
            <div class="day-title">AE Interface + Composition Setup</div>
            <div class="day-details">Layer types · Timeline · Keyframe basics</div>
          </div>
          <div class="day-duration">৫ ঘণ্টা</div>
        </div>
      </div>
      <div class="day-card">
        <div class="day-card-inner">
          <div><div class="day-label">Day 9</div><div class="day-name">সোমবার</div></div>
          <div class="day-content">
            <div class="day-title">Motion Graphics — Text Animation</div>
            <div class="day-details">Position · Scale · Rotation · Opacity animate</div>
          </div>
          <div class="day-duration">৫ ঘণ্টা</div>
        </div>
      </div>
      <div class="day-card">
        <div class="day-card-inner">
          <div><div class="day-label">Day 10</div><div class="day-name">মঙ্গলবার</div></div>
          <div class="day-content">
            <div class="day-title">Masking + Shape Layers</div>
            <div class="day-details">Track Matte · Mask Path animation · Reveal effects</div>
          </div>
          <div class="day-duration">৫ ঘণ্টা</div>
        </div>
      </div>
      <div class="day-card">
        <div class="day-card-inner">
          <div><div class="day-label">Day 11</div><div class="day-name">বুধবার</div></div>
          <div class="day-content">
            <div class="day-title">Transitions & Effects in AE</div>
            <div class="day-details">Zoom Blur · Whip Pan · Glitch Effects</div>
          </div>
          <div class="day-duration">৫ ঘণ্টা</div>
        </div>
      </div>
      <div class="day-card">
        <div class="day-card-inner">
          <div><div class="day-label">Day 12</div><div class="day-name">বৃহস্পতিবার</div></div>
          <div class="day-content">
            <div class="day-title">Logo Animation + Intro Bumper</div>
            <div class="day-details">Shape morph · Stroke effect · Trim Paths</div>
          </div>
          <div class="day-duration">৫ ঘণ্টা</div>
        </div>
      </div>
      <div class="day-card">
        <div class="day-card-inner">
          <div><div class="day-label">Day 13</div><div class="day-name">শুক্রবার</div></div>
          <div class="day-content">
            <div class="day-title">Expressions — Wiggle, Loop, Time</div>
            <div class="day-details">wiggle() · loopOut() · Basic Expression logic</div>
          </div>
          <div class="day-duration">৫ ঘণ্টা</div>
        </div>
      </div>
      <div class="day-card rest-day">
        <div class="day-card-inner">
          <div><div class="day-label">Day 14</div><div class="day-name">শনিবার</div></div>
          <div class="day-content">
            <div class="day-title">🔁 একটা Logo Intro + Short Bumper বানান</div>
            <div class="day-details">Portfolio এর জন্য প্রথম piece তৈরি</div>
          </div>
          <div class="day-duration">৪ ঘণ্টা</div>
        </div>
      </div>
    </div>
  </div>

  <!-- WEEK 3 -->
  <div class="week-section w3">
    <div class="week-header">
      <div class="week-number">03</div>
      <div class="week-info">
        <span class="week-tag">Advanced Skills</span>
        <div class="week-title">🚀 সপ্তাহ ৩ — Advanced Techniques</div>
      </div>
    </div>
    <div class="days-grid">
      <div class="day-card">
        <div class="day-card-inner">
          <div><div class="day-label">Day 15</div><div class="day-name">রবিবার</div></div>
          <div class="day-content">
            <div class="day-title">Speed Ramp + Slow Motion (Premiere)</div>
            <div class="day-details">Time Remapping · Frame Blending · Speed Ramp tutorial</div>
          </div>
          <div class="day-duration">৫ ঘণ্টা</div>
        </div>
      </div>
      <div class="day-card">
        <div class="day-card-inner">
          <div><div class="day-label">Day 16</div><div class="day-name">সোমবার</div></div>
          <div class="day-content">
            <div class="day-title">Motion Tracking (AE)</div>
            <div class="day-details">Point Tracker · Text on moving object · Camera track</div>
          </div>
          <div class="day-duration">৫ ঘণ্টা</div>
        </div>
      </div>
      <div class="day-card">
        <div class="day-card-inner">
          <div><div class="day-label">Day 17</div><div class="day-name">মঙ্গলবার</div></div>
          <div class="day-content">
            <div class="day-title">Green Screen / Chroma Key</div>
            <div class="day-details">Keylight · Spill Suppressor · Background replace</div>
          </div>
          <div class="day-duration">৫ ঘণ্টা</div>
        </div>
      </div>
      <div class="day-card">
        <div class="day-card-inner">
          <div><div class="day-label">Day 18</div><div class="day-name">বুধবার</div></div>
          <div class="day-content">
            <div class="day-title">Cinematic Color Grade + Film Look</div>
            <div class="day-details">Teal & Orange · Film grain · Vignette · Glow</div>
          </div>
          <div class="day-duration">৫ ঘণ্টা</div>
        </div>
      </div>
      <div class="day-card">
        <div class="day-card-inner">
          <div><div class="day-label">Day 19</div><div class="day-name">বৃহস্পতিবার</div></div>
          <div class="day-content">
            <div class="day-title">YouTube / Reels / Short Form Editing</div>
            <div class="day-details">Jump cut rhythm · Hook editing · Subtitle style</div>
          </div>
          <div class="day-duration">৫ ঘণ্টা</div>
        </div>
      </div>
      <div class="day-card">
        <div class="day-card-inner">
          <div><div class="day-label">Day 20</div><div class="day-name">শুক্রবার</div></div>
          <div class="day-content">
            <div class="day-title">Sound Design + Music Sync</div>
            <div class="day-details">SFX add · Beat sync cut · Ambient sound · Ducking</div>
          </div>
          <div class="day-duration">৫ ঘণ্টা</div>
        </div>
      </div>
      <div class="day-card rest-day">
        <div class="day-card-inner">
          <div><div class="day-label">Day 21</div><div class="day-name">শনিবার</div></div>
          <div class="day-content">
            <div class="day-title">🔁 একটা Cinematic Travel / Product Reel বানান</div>
            <div class="day-details">সব skill একসাথে ব্যবহার করুন</div>
          </div>
          <div class="day-duration">৬ ঘণ্টা</div>
        </div>
      </div>
    </div>
  </div>

  <!-- WEEK 4 -->
  <div class="week-section w4">
    <div class="week-header">
      <div class="week-number">04</div>
      <div class="week-info">
        <span class="week-tag">Client Ready</span>
        <div class="week-title">💼 সপ্তাহ ৪ — Portfolio + Freelance Prep</div>
      </div>
    </div>
    <div class="days-grid">
      <div class="day-card">
        <div class="day-card-inner">
          <div><div class="day-label">Day 22</div><div class="day-name">রবিবার</div></div>
          <div class="day-content">
            <div class="day-title">Real Client-Style Project #1</div>
            <div class="day-details">YouTube Vlog Edit · Full workflow practice</div>
          </div>
          <div class="day-duration">৬ ঘণ্টা</div>
        </div>
      </div>
      <div class="day-card">
        <div class="day-card-inner">
          <div><div class="day-label">Day 23</div><div class="day-name">সোমবার</div></div>
          <div class="day-content">
            <div class="day-title">Real Client-Style Project #2</div>
            <div class="day-details">Product Ad / Brand Video · Social Media format</div>
          </div>
          <div class="day-duration">৬ ঘণ্টা</div>
        </div>
      </div>
      <div class="day-card">
        <div class="day-card-inner">
          <div><div class="day-label">Day 24</div><div class="day-name">মঙ্গলবার</div></div>
          <div class="day-content">
            <div class="day-title">Real Client-Style Project #3</div>
            <div class="day-details">Wedding / Event Highlight Video</div>
          </div>
          <div class="day-duration">৬ ঘণ্টা</div>
        </div>
      </div>
      <div class="day-card">
        <div class="day-card-inner">
          <div><div class="day-label">Day 25</div><div class="day-name">বুধবার</div></div>
          <div class="day-content">
            <div class="day-title">Freelance Platform Setup</div>
            <div class="day-details">Fiverr / Upwork Gig তৈরি · Pricing · Service package</div>
          </div>
          <div class="day-duration">৪ ঘণ্টা</div>
        </div>
      </div>
      <div class="day-card">
        <div class="day-card-inner">
          <div><div class="day-label">Day 26</div><div class="day-name">বৃহস্পতিবার</div></div>
          <div class="day-content">
            <div class="day-title">Portfolio Showreel তৈরি</div>
            <div class="day-details">Best কাজগুলো দিয়ে ১–২ মিনিটের reel বানান</div>
          </div>
          <div class="day-duration">৫ ঘণ্টা</div>
        </div>
      </div>
      <div class="day-card">
        <div class="day-card-inner">
          <div><div class="day-label">Day 27-29</div><div class="day-name">শুক্র-রবি</div></div>
          <div class="day-content">
            <div class="day-title">Mock Client Project — Feedback Loop</div>
            <div class="day-details">বন্ধু/পরিচিতকে দিয়ে কাজ করান · Revision শিখুন</div>
          </div>
          <div class="day-duration">৫–৬ ঘণ্টা</div>
        </div>
      </div>
      <div class="day-card rest-day">
        <div class="day-card-inner">
          <div><div class="day-label">Day 30</div><div class="day-name">সোমবার</div></div>
          <div class="day-content">
            <div class="day-title">🏆 Final Day — Review, Polish & Launch</div>
            <div class="day-details">Portfolio upload · Social media post · ২য় মাস পরিকল্পনা</div>
          </div>
          <div class="day-duration">৪ ঘণ্টা</div>
        </div>
      </div>
    </div>
  </div>

  <!-- TIPS -->
  <div class="tips-section">
    <div class="tips-title">⚡ Pro Tips</div>
    <div class="tips-grid">
      <div class="tip-card">
        <div class="tip-icon">📺</div>
        <div class="tip-text"><strong>সেরা Tutorial Sources</strong>Premiere Gal · Justin Odisho · Premiere Basics · VFX Bro (YouTube)</div>
      </div>
      <div class="tip-card">
        <div class="tip-icon">💾</div>
        <div class="tip-text"><strong>Free Assets ডাউনলোড করুন</strong>Mixkit · Pexels · Motion Array Free · Envato Elements</div>
      </div>
      <div class="tip-card">
        <div class="tip-icon">📁</div>
        <div class="tip-text"><strong>Project Organize করুন</strong>প্রতিটা project আলাদা folder এ রাখুন। Footage · Audio · Export আলাদা করুন।</div>
      </div>
      <div class="tip-card">
        <div class="tip-icon">🔥</div>
        <div class="tip-text"><strong>Shortcuts মুখস্থ করুন</strong>C (Razor) · V (Select) · I/O (In/Out) · J/K/L (Play speed)</div>
      </div>
      <div class="tip-card">
        <div class="tip-icon">💰</div>
        <div class="tip-text"><strong>Fiverr Gig Ideas</strong>YouTube Video Editing · Reels Editing · Logo Animation · Product Ad</div>
      </div>
      <div class="tip-card">
        <div class="tip-icon">🧠</div>
        <div class="tip-text"><strong>সবচেয়ে গুরুত্বপূর্ণ নিয়ম</strong>Tutorial দেখলেই হবে না। প্রতিদিন নিজে Practice করতে হবে।</div>
      </div>
    </div>
  </div>

  <!-- FOOTER -->
  <div class="footer">
    <div class="footer-motto">CONSISTENCY BEATS TALENT</div>
    <div class="footer-sub">৩০ দিন ধৈর্য রাখুন · ২য় মাসে Client নিন · সাফল্য নিশ্চিত 🚀</div>
  </div>

</div>
</body>
</html>
