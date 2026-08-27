# Janet
My Virtual Assistant 
#!/usr/bin/env bash
set -e
echo 'Writing Command Post repo files...'

cat > 'index.html' <<'CPEOF_MARKER_UNIQUE_9f3a'
<!doctype html>
<html lang="en">
<head>
<meta charset="utf-8">
<title>Command Post</title>
<meta name="viewport" content="width=device-width, initial-scale=1">
<link rel="preconnect" href="https://fonts.googleapis.com">
<link rel="preconnect" href="https://fonts.gstatic.com" crossorigin>
<link href="https://fonts.googleapis.com/css2?family=Fraunces:ital,opsz,wght@0,9..144,400;0,9..144,500;0,9..144,600;0,9..144,700;1,9..144,500&family=IBM+Plex+Sans:wght@400;500;600;700&family=IBM+Plex+Mono:wght@400;500;600&display=swap" rel="stylesheet">
<style>
  /* ============ TOKENS ============ */
  :root, [data-palette="earth"] {
    --coral:#C97B3D; --gold:#B08D3E; --teal:#6F8F63; --lavender:#8A6A45;
    --good:#4C8C5B; --warn:#B5811F; --crit:#BD4632;
    --ground:#FAF6EF; --surface:#FFFFFF; --surface-2:#F3ECDD;
    --ink:#2A241C; --ink-soft:#564C3D; --muted:#8C8071; --line:#E4D9C4;
    --shadow: rgba(42,36,28,0.10);
    --mh-bg: linear-gradient(135deg,#2A241C 0%,#4A3F2E 100%);
    --mh-ink:#FAF6EF; --mh-sub:#D8CBAE; --mh-accent: var(--coral);
  }
  @media (prefers-color-scheme: dark) {
    :root:not([data-theme="light"]), [data-palette="earth"]:not([data-theme="light"]) {
      --coral:#E0965A; --gold:#D2AC5C; --teal:#8FAF80; --lavender:#B08F63;
      --good:#6FAE7E; --warn:#D6A23F; --crit:#E37360;
      --ground:#1B1712; --surface:#241F18; --surface-2:#2E271D;
      --ink:#F3ECDD; --ink-soft:#C9BCA2; --muted:#8F8371; --line:#3B3327;
      --shadow: rgba(0,0,0,0.35);
      --mh-bg: linear-gradient(135deg,#100D09 0%,#2E271D 100%);
      --mh-ink:#F3ECDD; --mh-sub:#B0A38A;
    }
  }
  :root[data-theme="dark"], [data-palette="earth"][data-theme="dark"] {
    --coral:#E0965A; --gold:#D2AC5C; --teal:#8FAF80; --lavender:#B08F63;
    --good:#6FAE7E; --warn:#D6A23F; --crit:#E37360;
    --ground:#1B1712; --surface:#241F18; --surface-2:#2E271D;
    --ink:#F3ECDD; --ink-soft:#C9BCA2; --muted:#8F8371; --line:#3B3327;
    --shadow: rgba(0,0,0,0.35);
    --mh-bg: linear-gradient(135deg,#100D09 0%,#2E271D 100%);
    --mh-ink:#F3ECDD; --mh-sub:#B0A38A;
  }

  [data-palette="strip"] {
    --coral:#2FA8E0; --gold:#E3A544; --teal:#1D7CA6; --lavender:#F0C179;
    --good:#4FAE6D; --warn:#E3A544; --crit:#E1614F;
    --ground:#0A0E16; --surface:#12192A; --surface-2:#182036;
    --ink:#F2F4F8; --ink-soft:#B9C2D4; --muted:#7C879E; --line:#22304A;
    --shadow: rgba(0,0,0,0.5);
    --mh-bg: linear-gradient(135deg,#0A0E16 0%,#182036 100%);
    --mh-ink:#F2F4F8; --mh-sub:#8FA3C2; --mh-accent: var(--gold);
  }

  [data-palette="redrock"] {
    --coral:#D14A22; --gold:#C99A4A; --teal:#217A5B; --lavender:#8C3B22;
    --good:#2F8F5B; --warn:#C98A2E; --crit:#B93A26;
    --ground:#FCF3E8; --surface:#FFFFFF; --surface-2:#F5E4CC;
    --ink:#3A2418; --ink-soft:#6B4A36; --muted:#9C7C63; --line:#E9D2B4;
    --shadow: rgba(58,36,24,0.10);
    --mh-bg: linear-gradient(135deg,#3A2418 0%,#6B3323 100%);
    --mh-ink:#FCF3E8; --mh-sub:#E3B98D; --mh-accent: var(--teal);
  }
  @media (prefers-color-scheme: dark) {
    [data-palette="redrock"]:not([data-theme="light"]) {
      --coral:#F0733E; --gold:#D9AE68; --teal:#3FCB9C; --lavender:#C46A47;
      --good:#4FB37F; --warn:#E0A94C; --crit:#E36B54;
      --ground:#221510; --surface:#2C1C15; --surface-2:#38271C;
      --ink:#F5E6D3; --ink-soft:#D3B79B; --muted:#9C8267; --line:#4A3527;
      --shadow: rgba(0,0,0,0.4);
      --mh-bg: linear-gradient(135deg,#160E0A 0%,#38271C 100%);
      --mh-ink:#F5E6D3; --mh-sub:#D9A574;
    }
  }
  [data-palette="redrock"][data-theme="dark"] {
    --coral:#F0733E; --gold:#D9AE68; --teal:#3FCB9C; --lavender:#C46A47;
    --good:#4FB37F; --warn:#E0A94C; --crit:#E36B54;
    --ground:#221510; --surface:#2C1C15; --surface-2:#38271C;
    --ink:#F5E6D3; --ink-soft:#D3B79B; --muted:#9C8267; --line:#4A3527;
    --shadow: rgba(0,0,0,0.4);
    --mh-bg: linear-gradient(135deg,#160E0A 0%,#38271C 100%);
    --mh-ink:#F5E6D3; --mh-sub:#D9A574;
  }

  [data-palette="mountain"] {
    --coral:#D98A2E; --gold:#2E7FB8; --teal:#2E7FB8; --lavender:#64707D;
    --good:#3E9C6E; --warn:#D99A3E; --crit:#C1443A;
    --ground:#F3F6F9; --surface:#FFFFFF; --surface-2:#E6EEF4;
    --ink:#1E2A33; --ink-soft:#48586A; --muted:#8695A3; --line:#D5E0E8;
    --shadow: rgba(20,40,60,0.08);
    --mh-bg: linear-gradient(135deg,#1E2A33 0%,#2E4A5E 100%);
    --mh-ink:#F3F6F9; --mh-sub:#AFC8DA; --mh-accent: var(--coral);
  }
  @media (prefers-color-scheme: dark) {
    [data-palette="mountain"]:not([data-theme="light"]) {
      --coral:#E4A34F; --gold:#5FB4E8; --teal:#5FB4E8; --lavender:#8695A3;
      --good:#5CB584; --warn:#E0B15A; --crit:#DD6C61;
      --ground:#0D1620; --surface:#13202C; --surface-2:#1A2A38;
      --ink:#EAF1F7; --ink-soft:#B7C7D6; --muted:#75879A; --line:#28394A;
      --shadow: rgba(0,0,0,0.4);
      --mh-bg: linear-gradient(135deg,#080D13 0%,#1A2A38 100%);
      --mh-ink:#EAF1F7; --mh-sub:#8FB3CE;
    }
  }
  [data-palette="mountain"][data-theme="dark"] {
    --coral:#E4A34F; --gold:#5FB4E8; --teal:#5FB4E8; --lavender:#8695A3;
    --good:#5CB584; --warn:#E0B15A; --crit:#DD6C61;
    --ground:#0D1620; --surface:#13202C; --surface-2:#1A2A38;
    --ink:#EAF1F7; --ink-soft:#B7C7D6; --muted:#75879A; --line:#28394A;
    --shadow: rgba(0,0,0,0.4);
    --mh-bg: linear-gradient(135deg,#080D13 0%,#1A2A38 100%);
    --mh-ink:#EAF1F7; --mh-sub:#8FB3CE;
  }

  /* ============ BASE ============ */
  * { box-sizing: border-box; }
  html { -webkit-text-size-adjust: 100%; }
  body {
    margin:0; background:var(--ground); color:var(--ink);
    font-family:"IBM Plex Sans", system-ui, sans-serif;
    line-height:1.5; -webkit-font-smoothing:antialiased;
  }
  h1,h2,h3 { font-family:"Fraunces", Georgia, serif; text-wrap:balance; margin:0; }
  .mono { font-family:"IBM Plex Mono", ui-monospace, monospace; font-variant-numeric:tabular-nums; }
  a { color:inherit; }
  :focus-visible { outline:2px solid var(--coral); outline-offset:2px; }
  @media (prefers-reduced-motion: reduce) { * { animation:none !important; transition:none !important; } }

  .wrap { max-width:1180px; margin:0 auto; padding:0 20px 64px; }

  /* ---- switcher ---- */
  .switcher-bar { background:var(--surface-2); border-bottom:1px solid var(--line); }
  .switcher {
    max-width:1180px; margin:0 auto; padding:10px 20px; display:flex; gap:8px;
    flex-wrap:wrap; align-items:center;
  }
  .switcher span { font-size:11px; text-transform:uppercase; letter-spacing:.08em; color:var(--muted); margin-right:4px; }
  .switcher button {
    font-family:"IBM Plex Sans"; font-size:12.5px; font-weight:600; letter-spacing:.01em;
    padding:6px 13px; border-radius:100px; border:1px solid var(--line); background:var(--surface);
    color:var(--ink-soft); cursor:pointer; transition:all .15s ease;
  }
  .switcher button:hover { border-color:var(--coral); color:var(--ink); }
  .switcher button.active { background:var(--ink); color:var(--ground); border-color:var(--ink); }
  [data-palette="strip"] .switcher button.active { background:var(--gold); color:#0A0E16; border-color:var(--gold); }

  /* ---- masthead ---- */
  .masthead { background:var(--mh-bg); color:var(--mh-ink); padding:36px 20px 30px; }
  .mh-inner { max-width:1180px; margin:0 auto; display:flex; justify-content:space-between; align-items:flex-end; gap:24px; flex-wrap:wrap; }
  .mh-title { font-size:clamp(28px,4vw,42px); font-weight:600; letter-spacing:-.01em; }
  .mh-title em { font-style:italic; color:var(--mh-accent); font-weight:500; }
  .mh-sub { color:var(--mh-sub); font-size:14.5px; margin-top:8px; max-width:52ch; }
  .mh-right { text-align:right; }
  .mh-clock { font-family:"IBM Plex Mono"; font-size:15px; color:var(--mh-sub); }
  .sync-pill {
    display:inline-flex; align-items:center; gap:7px; margin-top:10px; padding:6px 13px;
    border-radius:100px; background:rgba(255,255,255,0.08); border:1px solid rgba(255,255,255,0.16);
    font-size:12px; color:var(--mh-sub); font-family:"IBM Plex Mono";
  }
  .sync-dot { width:7px; height:7px; border-radius:50%; background:var(--good); box-shadow:0 0 0 3px rgba(76,140,91,.25); }

  /* ---- section shell ---- */
  .section { padding-top:38px; }
  .section-head { display:flex; align-items:baseline; justify-content:space-between; gap:16px; margin-bottom:16px; flex-wrap:wrap; }
  .section-head h2 { font-size:22px; font-weight:600; }
  .section-eyebrow { font-size:11px; text-transform:uppercase; letter-spacing:.1em; color:var(--coral); font-weight:600; margin-bottom:4px; }
  .section-note { font-size:13px; color:var(--muted); max-width:46ch; }

  /* ---- month ahead scroller ---- */
  .month-scroll { display:flex; gap:14px; overflow-x:auto; padding:4px 4px 14px; scroll-snap-type:x proximity; }
  .month-scroll::-webkit-scrollbar { height:6px; }
  .month-scroll::-webkit-scrollbar-thumb { background:var(--line); border-radius:3px; }
  .m-card {
    scroll-snap-align:start; flex:0 0 250px; background:var(--surface); border:1px solid var(--line);
    border-radius:14px; padding:16px; box-shadow:0 1px 2px var(--shadow); display:flex; flex-direction:column; gap:8px;
  }
  .m-card.urgent { border-color:var(--crit); box-shadow:0 0 0 1px var(--crit); }
  .m-date { font-family:"IBM Plex Mono"; font-size:11px; text-transform:uppercase; letter-spacing:.06em; color:var(--muted); }
  .m-date.today { color:var(--crit); font-weight:600; }
  .m-card h3 { font-size:16px; font-weight:600; line-height:1.25; }
  .m-card p { font-size:13px; color:var(--ink-soft); margin:0; line-height:1.45; }
  .m-tag { align-self:flex-start; font-size:10.5px; font-weight:600; text-transform:uppercase; letter-spacing:.05em; padding:3px 9px; border-radius:100px; }
  .tag-crit { background:color-mix(in srgb, var(--crit) 16%, transparent); color:var(--crit); }
  .tag-warn { background:color-mix(in srgb, var(--warn) 18%, transparent); color:var(--warn); }
  .tag-good { background:color-mix(in srgb, var(--good) 18%, transparent); color:var(--good); }
  .tag-info { background:color-mix(in srgb, var(--teal) 16%, transparent); color:var(--teal); }

  /* ---- stat strip ---- */
  .stat-strip { display:grid; grid-template-columns:repeat(4,1fr); gap:12px; }
  .stat { background:var(--surface); border:1px solid var(--line); border-radius:14px; padding:18px 18px 16px; }
  .stat-num { font-family:"Fraunces"; font-size:34px; font-weight:600; line-height:1; }
  .stat-num.crit { color:var(--crit); }
  .stat-label { font-size:12.5px; color:var(--muted); margin-top:6px; }

  /* ---- timeline ---- */
  .timeline-grid { display:grid; grid-template-columns:repeat(3,1fr); gap:14px; align-items:start; }
  .day-card { background:var(--surface); border:1px solid var(--line); border-radius:14px; padding:16px; }
  .day-head { display:flex; justify-content:space-between; align-items:baseline; margin-bottom:10px; padding-bottom:10px; border-bottom:1px solid var(--line); }
  .day-head h3 { font-size:16px; font-weight:600; }
  .day-head span { font-size:11px; color:var(--muted); font-family:"IBM Plex Mono"; }
  .ev { display:flex; gap:10px; padding:8px 0; border-bottom:1px dashed var(--line); }
  .ev:last-child { border-bottom:none; }
  .ev-time { font-family:"IBM Plex Mono"; font-size:11.5px; color:var(--muted); flex:0 0 68px; padding-top:1px; }
  .ev-body strong { font-size:13.5px; font-weight:600; display:block; }
  .ev-body span.meta { font-size:12px; color:var(--muted); }
  .ev.conflict { background:color-mix(in srgb, var(--crit) 8%, transparent); margin:0 -8px; padding:8px; border-radius:8px; border-bottom:1px dashed transparent; }
  .ev.conflict .ev-time, .ev.conflict strong { color:var(--crit); }
  .empty-day { font-size:13px; color:var(--muted); font-style:italic; padding:12px 0; }

  /* ---- signal feed ---- */
  .feed { display:flex; flex-direction:column; gap:10px; }
  .feed-item { display:flex; gap:12px; background:var(--surface); border:1px solid var(--line); border-radius:12px; padding:13px 15px; }
  .feed-tag { flex:0 0 auto; font-size:10.5px; font-weight:700; text-transform:uppercase; letter-spacing:.05em; padding:4px 9px; border-radius:6px; height:fit-content; }
  .feed-item p { margin:0; font-size:13.5px; color:var(--ink-soft); }
  .feed-item strong { color:var(--ink); }
  .feed-src { font-size:11px; color:var(--muted); margin-top:3px; display:block; }
  .tag-legal { background:color-mix(in srgb, var(--lavender) 22%, transparent); color:var(--lavender); }
  .tag-bizdev { background:color-mix(in srgb, var(--teal) 20%, transparent); color:var(--teal); }
  .tag-ops { background:color-mix(in srgb, var(--gold) 24%, transparent); color:var(--gold); }
  .tag-team { background:color-mix(in srgb, var(--coral) 18%, transparent); color:var(--coral); }

  /* ---- radar table ---- */
  .radar-wrap { overflow-x:auto; border:1px solid var(--line); border-radius:14px; background:var(--surface); }
  table.radar { width:100%; border-collapse:collapse; font-size:13px; min-width:640px; }
  table.radar th { text-align:left; font-size:11px; text-transform:uppercase; letter-spacing:.06em; color:var(--muted); padding:12px 14px; border-bottom:1px solid var(--line); }
  table.radar td { padding:12px 14px; border-bottom:1px solid var(--line); vertical-align:top; }
  table.radar tr:last-child td { border-bottom:none; }
  .radar-name { font-weight:600; }
  .new-badge { font-size:9.5px; font-weight:700; background:var(--coral); color:var(--surface); padding:2px 6px; border-radius:5px; margin-left:6px; vertical-align:middle; letter-spacing:.03em; }

  /* ---- prep cards ---- */
  .prep-grid { display:grid; grid-template-columns:repeat(2,1fr); gap:14px; }
  .prep-card { background:var(--surface); border:1px solid var(--line); border-left:4px solid var(--coral); border-radius:10px; padding:15px 17px; }
  .prep-card h3 { font-size:15px; font-weight:600; margin-bottom:6px; }
  .prep-card p { font-size:13.5px; color:var(--ink-soft); margin:0; }
  .prep-card.high { border-left-color:var(--crit); }

  /* ---- blind spots ---- */
  .blind-panel { background:var(--surface-2); border:1px solid var(--line); border-radius:16px; padding:24px 26px; }
  .blind-panel .section-eyebrow { color:var(--lavender); }
  .blind-grid { display:grid; grid-template-columns:repeat(2,1fr); gap:16px; margin-top:14px; }
  .blind-item { background:var(--surface); border-radius:10px; padding:14px 16px; border:1px solid var(--line); }
  .blind-item h4 { font-size:13.5px; font-weight:700; margin:0 0 5px; font-family:"IBM Plex Sans"; }
  .blind-item p { font-size:13px; color:var(--ink-soft); margin:0; }

  /* ---- marks corner ---- */
  .marks-corner { display:flex; gap:16px; align-items:center; background:var(--surface); border:1px solid var(--line); border-radius:14px; padding:16px 20px; flex-wrap:wrap; }
  .mc-badge { font-family:"Fraunces"; font-style:italic; font-size:18px; color:var(--coral); flex:0 0 auto; }
  .mc-list { font-size:12.5px; color:var(--ink-soft); }
  .mc-list b { color:var(--ink); }

  footer.cp-footer { text-align:center; font-size:11.5px; color:var(--muted); padding-top:30px; font-family:"IBM Plex Mono"; }
  footer.cp-footer a { text-decoration:underline; }

  @media (max-width: 880px) {
    .timeline-grid, .stat-strip, .blind-grid, .prep-grid { grid-template-columns:1fr; }
    .mh-right { text-align:left; }
  }
</style>
</head>
<body>


<div class="switcher-bar">
  <div class="switcher">
    <span>Theme</span>
    <button data-p="earth">Earth &amp; Stone</button>
    <button data-p="strip">Vegas Strip</button>
    <button data-p="redrock">Red Rock Canyon</button>
    <button data-p="mountain">Mountain</button>
  </div>
</div>

<header class="masthead">
  <div class="mh-inner">
    <div>
      <div class="mh-title">Command Post <em>for Theresa</em></div>
      <div class="mh-sub">Mark's live working view — calendars, inbox, and Theresa's own AI ops brief, rolled into one board.</div>
      <div class="sync-pill"><span class="sync-dot"></span> Synced Thu Aug 27 · 9:14 AM PT — next refresh ~12:00 PM PT</div>
    </div>
    <div class="mh-right">
      <div class="mh-clock mono" id="cp-clock">9:14 AM PT</div>
      <div class="mh-clock mono" style="font-size:13px;opacity:.75" id="cp-date">Thursday, August 27, 2026</div>
    </div>
  </div>
</header>

<div class="wrap">

  <!-- MONTH AHEAD -->
  <section class="section">
    <div class="section-head">
      <div>
        <div class="section-eyebrow">Next 30 days</div>
        <h2>The month ahead</h2>
      </div>
      <div class="section-note">Trips, recurring cadences, and the dates most likely to bite if nobody's watching them.</div>
    </div>
    <div class="month-scroll">
      <div class="m-card urgent">
        <span class="m-tag tag-crit">Today</span>
        <div class="m-date today">Thu Aug 27</div>
        <h3>Litigation crunch + triple-booked afternoon</h3>
        <p>AoC Huddle (8–9am) is closing the AREAM/witness-list question before Friday's TFE filing. Then 3–5:30pm stacks three holds on top of each other.</p>
      </div>
      <div class="m-card urgent">
        <span class="m-tag tag-crit">Tomorrow</span>
        <div class="m-date">Fri Aug 28</div>
        <h3>TFE disclosures file + Mark meets Aristocrat</h3>
        <p>Disclosure deadline and YPO board nominations both close today. Mark's first sit-down with Jen Ilsley (VP HR, Aristocrat) is 12:30–2pm.</p>
      </div>
      <div class="m-card">
        <span class="m-tag tag-warn">Mon Aug 31</span>
        <div class="m-date">Aug 31</div>
        <h3>LED Audit Process Finalization</h3>
        <p>9am–1pm, 4-hour block — same week as the still-unverified LED Connection LLC collaboration invite.</p>
      </div>
      <div class="m-card urgent">
        <span class="m-tag tag-crit">Tue Sept 1</span>
        <div class="m-date">Sept 1</div>
        <h3>Estate planning signs, zero buffer before it</h3>
        <p>Noon signing at Theresa's House (Miranda, Rebecca, Mark) starts the instant the 11:30 Copper Cow Coffee call ends.</p>
      </div>
      <div class="m-card urgent">
        <span class="m-tag tag-crit">Sept 2–8</span>
        <div class="m-date">Cabo trip</div>
        <h3>Departure date still contested</h3>
        <p>Theresa's own Southwest ticket says Sept 2 out. The hotel, tixr tickets, and Dan's flight all say Sept 4–8. Same contradiction as last pull.</p>
      </div>
      <div class="m-card">
        <span class="m-tag tag-warn">Fri Sept 4</span>
        <div class="m-date">Sept 4</div>
        <h3>YPO Forum overlaps the Cabo flight window</h3>
        <p>Forum runs 9:15–11:15am; Dan and Joe's outbound flight window is 7:15–11am the same morning — only matters if Sept 4 is the real departure.</p>
      </div>
      <div class="m-card">
        <span class="m-tag tag-info">Tue Sept 8</span>
        <div class="m-date">Sept 8</div>
        <h3>NTG training + YPO, same evening</h3>
        <p>NTG Structure Training Class at LED Connection (11:30am–3pm) and YPO State of the Chapter that night at the Doberman Drawing Room.</p>
      </div>
      <div class="m-card">
        <span class="m-tag tag-good">Sept 9–17</span>
        <div class="m-date">8-day window</div>
        <h3>Comms blackout — no calls, no Zoom</h3>
        <p>Theresa's blocked herself off entirely. A JSX flight to CA and a San Diego laser appointment both sit inside it. Land anything time-sensitive before Sept 9.</p>
      </div>
    </div>
  </section>

  <!-- STAT STRIP -->
  <section class="section">
    <div class="stat-strip">
      <div class="stat"><div class="stat-num">11</div><div class="stat-label">Meetings on Theresa's calendar, next 3 days</div></div>
      <div class="stat"><div class="stat-num crit">4</div><div class="stat-label">Scheduling conflicts today alone</div></div>
      <div class="stat"><div class="stat-num">12</div><div class="stat-label">Unread emails in Mark's inbox needing a look</div></div>
      <div class="stat"><div class="stat-num">5</div><div class="stat-label">Active legal threads in flight</div></div>
    </div>
  </section>

  <!-- TIMELINE -->
  <section class="section">
    <div class="section-head">
      <div>
        <div class="section-eyebrow">Theresa's calendar</div>
        <h2>Next 3 days</h2>
      </div>
      <div class="section-note">Overlapping holds are flagged red — help her pick one before the block arrives.</div>
    </div>
    <div class="timeline-grid">
      <div class="day-card">
        <div class="day-head"><h3>Today · Thu Aug 27</h3><span>4 conflicts</span></div>
        <div class="ev"><div class="ev-time">8:00 AM</div><div class="ev-body"><strong>AoC Huddle</strong><span class="meta">Doug, Aaron, Dawson, Ogden — closing the AREAM witness-list question</span></div></div>
        <div class="ev"><div class="ev-time">9:40 AM</div><div class="ev-body"><strong>Family Conference — Mason</strong><span class="meta">Tyler (Prisma), Zoom, 15 min</span></div></div>
        <div class="ev conflict"><div class="ev-time">1:00 PM</div><div class="ev-body"><strong>Luminous Connect</strong><span class="meta">Magnus, Eric, Sergei, David W. — overlaps Goldman below</span></div></div>
        <div class="ev conflict"><div class="ev-time">1:30 PM</div><div class="ev-body"><strong>Tax/insurance strategy — Goldman</strong><span class="meta">David Hoese, Rebecca — this one can't be delegated</span></div></div>
        <div class="ev conflict"><div class="ev-time">3:00 PM</div><div class="ev-body"><strong>Drinks — Vincent Aiello</strong><span class="meta">Panevino — overlaps ortho + a second drinks hold</span></div></div>
        <div class="ev conflict"><div class="ev-time">3:30 PM</div><div class="ev-body"><strong>Ortho — Mason</strong><span class="meta">Leslee, Dan — overlaps Vincent</span></div></div>
        <div class="ev"><div class="ev-time">4:30 PM</div><div class="ev-body"><strong>Drinks (unlabeled)</strong><span class="meta">No attendees listed — likely stale, worth clearing</span></div></div>
      </div>
      <div class="day-card">
        <div class="day-head"><h3>Fri Aug 28</h3><span>clean</span></div>
        <div class="ev"><div class="ev-time">10:00 AM</div><div class="ev-body"><strong>Coffee with Daniel</strong><span class="meta">Le Cafe Du Sud</span></div></div>
        <div class="ev"><div class="ev-time">12:00 PM</div><div class="ev-body"><strong>Lunch with Bethany</strong><span class="meta">Wynn Las Vegas</span></div></div>
        <div class="ev"><div class="ev-time">1:30 PM</div><div class="ev-body"><strong>No appts block</strong><span class="meta">Open through 4:30pm</span></div></div>
        <div class="ev"><div class="ev-time">6:00 PM</div><div class="ev-body"><strong>Hold — dinner w/ Marina</strong><span class="meta">Through 8:30pm</span></div></div>
        <div class="ev"><div class="ev-time">—</div><div class="ev-body"><strong>Mark: Jen Ilsley, Aristocrat</strong><span class="meta">12:30–2pm, VP of HR — lead with the Leadership Flywheel</span></div></div>
      </div>
      <div class="day-card">
        <div class="day-head"><h3>Sat–Sun Aug 29–30</h3><span>open</span></div>
        <div class="empty-day">Nothing on Theresa's calendar this pull — a genuinely clear weekend. Worth protecting from last-minute adds.</div>
      </div>
    </div>
  </section>

  <!-- SIGNAL FEED -->
  <section class="section">
    <div class="section-head">
      <div>
        <div class="section-eyebrow">Inbox + Slack, last 48–72h</div>
        <h2>Signal feed</h2>
      </div>
      <div class="section-note">Pulled from Mark's inbox and Theresa's own AI ops brief in #theresa-ops.</div>
    </div>
    <div class="feed">
      <div class="feed-item">
        <span class="feed-tag tag-legal">Legal</span>
        <div><p><strong>AREAM witness-list question</strong> — Dawson's overnight question is what today's 8am huddle exists to close; TFE initial disclosures file tomorrow with under 24 hours of runway.</p><span class="feed-src">Theresa's AI briefing, #theresa-ops · today 6:01am</span></div>
      </div>
      <div class="feed-item">
        <span class="feed-tag tag-legal">Legal</span>
        <div><p><strong>GT Law returned final estate-planning docs</strong> with open points flagged in bold italic — Miranda is coordinating signature logistics for Tuesday's signing.</p><span class="feed-src">Theresa's AI briefing · today; email thread w/ Rebecca &amp; Mark, Aug 26</span></div>
      </div>
      <div class="feed-item">
        <span class="feed-tag tag-legal">Legal</span>
        <div><p><strong>Ticket #8424125</strong> (Mark's delegate access to Theresa's mailbox/calendar) is still "Response Needed" — open since Aug 24, unresolved five pulls running now.</p><span class="feed-src">help@itsasap.com · Aug 24, unread</span></div>
      </div>
      <div class="feed-item">
        <span class="feed-tag tag-legal">Legal</span>
        <div><p><strong>Burdecki/Intrepid — "Next steps"</strong> scheduling email from Fisher Phillips is still sitting unread in Mark's inbox.</p><span class="feed-src">rahmadi@fisherphillips.com · Aug 24, unread</span></div>
      </div>
      <div class="feed-item">
        <span class="feed-tag tag-bizdev">Bizdev</span>
        <div><p><strong>New — Debbie, Copper Cow Coffee</strong>, introduced by Linda. Rebecca booked a Zoom for Sept 1, 11:30am — it now backs directly into the estate-planning signing.</p><span class="feed-src">rebecca@nevadataxgroup.com · Aug 26</span></div>
      </div>
      <div class="feed-item">
        <span class="feed-tag tag-bizdev">Bizdev</span>
        <div><p><strong>retired.com → Jefferies intro</strong> (Camilo, Janelle Aispuro, Sam Schwartz) still hasn't landed on a calendar — three-plus days since the warm intro went out.</p><span class="feed-src">theresa@nevadataxgroup.com · Aug 24</span></div>
      </div>
      <div class="feed-item">
        <span class="feed-tag tag-bizdev">Bizdev</span>
        <div><p><strong>Whisper Capital's 100–130% FMV claim</strong> is still unsubstantiated — do not treat the real-estate distribution material as cleared until actuarial backing is in writing.</p><span class="feed-src">Recurring across three briefings, #theresa-ops</span></div>
      </div>
      <div class="feed-item">
        <span class="feed-tag tag-ops">Ops</span>
        <div><p><strong>Two meetings vanished</strong> from Theresa's calendar this week with no rebooking: "Meeting w/Lauren re. Podcast" and "Hold for coffee w/Dave Sanghera and Pashcale." Worth a quick confirm.</p><span class="feed-src">Outlook notifications · Aug 26</span></div>
      </div>
      <div class="feed-item">
        <span class="feed-tag tag-ops">Ops</span>
        <div><p><strong>New — Mark's own "MEET MARK" call</strong> with Alex Sumual (Disrupt Media) was canceled with no reschedule visible; was set for Sept 2, 10am.</p><span class="feed-src">Outlook · canceled</span></div>
      </div>
      <div class="feed-item">
        <span class="feed-tag tag-ops">Ops</span>
        <div><p><strong>LED Connection LLC collaboration invite</strong> (Aug 24) is still unverified — worth confirming legitimacy before Monday's audit block.</p><span class="feed-src">invites@ledconnection.com · Aug 24</span></div>
      </div>
      <div class="feed-item">
        <span class="feed-tag tag-team">Team</span>
        <div><p><strong>Rippling: health insurance election</strong> due Sept 30, and a Harassment Prevention course due Sept 25 — both still open on Mark's own task list.</p><span class="feed-src">Rippling · Aug 26–27</span></div>
      </div>
      <div class="feed-item">
        <span class="feed-tag tag-team">Team</span>
        <div><p><strong>Rebecca's weekly-agenda template</strong> (notes + wins/could-improve sections) is still worth Mark formally adopting for his own Theresa check-ins.</p><span class="feed-src">rebecca@nevadataxgroup.com · Aug 24</span></div>
      </div>
    </div>
  </section>

  <!-- RELATIONSHIP RADAR -->
  <section class="section">
    <div class="section-head">
      <div>
        <div class="section-eyebrow">Who's active right now</div>
        <h2>Relationship radar</h2>
      </div>
      <div class="section-note">People newly showing up in this pull are flagged NEW.</div>
    </div>
    <div class="radar-wrap">
      <table class="radar">
        <thead><tr><th>Person</th><th>Org / role</th><th>Why they're on the board</th></tr></thead>
        <tbody>
          <tr><td class="radar-name">Debbie<span class="new-badge">NEW</span></td><td>Copper Cow Coffee</td><td>Intro via Linda — Zoom booked Sept 1, 11:30am, right before estate planning.</td></tr>
          <tr><td class="radar-name">Jen Ilsley<span class="new-badge">NEW</span></td><td>VP of HR, Aristocrat</td><td>Mark's first meeting with her tomorrow, 12:30pm — leadership-development conversation.</td></tr>
          <tr><td class="radar-name">Alex Sumual<span class="new-badge">NEW</span></td><td>Disrupt Media</td><td>Canceled "MEET MARK" call, Sept 2 — no reschedule yet.</td></tr>
          <tr><td class="radar-name">Michael Rivlin</td><td>GT Law</td><td>Returned final estate-planning package with open points for the Sept 1 signing.</td></tr>
          <tr><td class="radar-name">Robert Dawson</td><td>AoC principal</td><td>Raised the unresolved AREAM/witness-list question this morning's huddle needs to close.</td></tr>
          <tr><td class="radar-name">Vincent Aiello</td><td>Spencer Fane</td><td>Catch-up drinks today, 3–5pm — useful informal read on litigation posture.</td></tr>
          <tr><td class="radar-name">David Hoese</td><td>Goldman Sachs</td><td>Tax/insurance strategy call today, 1:30pm — can't be delegated.</td></tr>
          <tr><td class="radar-name">Sharif Nesheiwat</td><td>retired.com / Project Lynx</td><td>NDA executed; VDR access still gated on Intralinks account setup.</td></tr>
          <tr><td class="radar-name">Miranda Zimmerman</td><td>NTG</td><td>Coordinating signature logistics for Tuesday's estate-planning execution.</td></tr>
        </tbody>
      </table>
    </div>
  </section>

  <!-- ANTICIPATE & PREP -->
  <section class="section">
    <div class="section-head">
      <div>
        <div class="section-eyebrow">Ahead of the moment</div>
        <h2>Anticipate &amp; prep</h2>
      </div>
      <div class="section-note">What's worth doing before it becomes urgent, based on this pull.</div>
    </div>
    <div class="prep-grid">
      <div class="prep-card high">
        <h3>Confirm the huddle actually closed the witness list</h3>
        <p>The AoC Huddle (8–9am) was the only forum today for the AREAM/Dawson question before tomorrow's TFE filing. Get a one-line confirmation it landed, not just that the meeting happened.</p>
      </div>
      <div class="prep-card high">
        <h3>Triage the 3–5:30pm pileup before 3pm</h3>
        <p>Vincent drinks, ortho for Mason, and an unlabeled Drinks hold all overlap. Help Theresa pick one now and quietly clear the other two rather than let it collide live.</p>
      </div>
      <div class="prep-card high">
        <h3>Build a buffer before Tuesday's signing</h3>
        <p>The 11:30am Copper Cow call ends the exact minute the estate-planning signing starts at Theresa's House. Ask Rebecca to trim the call or push the signing 10–15 minutes.</p>
      </div>
      <div class="prep-card high">
        <h3>Get a real answer on the Cabo date</h3>
        <p>Same contradiction as last pull: Theresa's own ticket says Sept 2, everything else says Sept 4. One line from her or Rebecca resolves whether the YPO Forum conflict is even real.</p>
      </div>
      <div class="prep-card">
        <h3>Prep for Jen Ilsley tomorrow</h3>
        <p>First meeting with Aristocrat's VP of HR, 12:30pm. Lead with the Leadership Flywheel framing — Communication → Relationships → Alignment → Execution → Capacity — not curriculum.</p>
      </div>
      <div class="prep-card">
        <h3>Escalate ticket #8424125 directly</h3>
        <p>Five straight pulls with no movement on delegate mailbox/calendar access. A direct call to ITS ASAP will likely outrun the queue at this point.</p>
      </div>
      <div class="prep-card">
        <h3>Nudge the retired.com/Jefferies intro</h3>
        <p>A warm introduction is going cold after three-plus days unscheduled. A short note to Rebecca or Camilo keeps the Sam Schwartz relationship active.</p>
      </div>
      <div class="prep-card">
        <h3>Close the loop on two vanished meetings</h3>
        <p>The podcast meeting with Lauren and coffee with Dave Sanghera both disappeared with no rebooking. A quick check with Theresa avoids either one falling through for good.</p>
      </div>
    </div>
  </section>

  <!-- BLIND SPOTS -->
  <section class="section">
    <div class="blind-panel">
      <div class="section-eyebrow">For Mark, not Theresa</div>
      <h2>Blind spots AI is watching for you</h2>
      <p class="section-note" style="margin-top:6px;max-width:70ch;">Built from your CliftonStrengths (Ideation, Woo, Futuristic, Strategic, Positivity — with Discipline dead last at #34) and your GiANT 5 Voices order (Connector → Creative → Pioneer, Guardian as your nemesis voice).</p>
      <div class="blind-grid">
        <div class="blind-item">
          <h4>Guardian gap</h4>
          <p>Today's afternoon stacked three overlapping holds without anyone defending the calendar boundary. That's the Guardian voice's job — not natural for you, but exactly the muscle this role is asking you to build.</p>
        </div>
        <div class="blind-item">
          <h4>Discipline, #34 of 34</h4>
          <p>The small logistics — a 15-minute buffer before a signing, a stale hold cleared before it collides — are where your lowest strength shows up. Build a checklist habit rather than trusting it to memory.</p>
        </div>
        <div class="blind-item">
          <h4>Over-promise risk</h4>
          <p>Woo and Positivity make it easy to say yes in the room. Before committing Theresa's time or yours, run it past the calendar first — this week's pileups are the cost of skipping that step.</p>
        </div>
        <div class="blind-item">
          <h4>1st-Gear reboot</h4>
          <p>Futuristic and Ideation pull you toward the next big thing. Protect a deliberate slow-start ritual each morning before the inbox and Slack briefing pull you into reactive mode.</p>
        </div>
        <div class="blind-item">
          <h4>Uber Successful book project</h4>
          <p>Strategic and Ideation are assets here — but Discipline #34 means the project needs externally imposed structure (a co-writer, a deadline, an accountability call) to actually ship.</p>
        </div>
        <div class="blind-item">
          <h4>HMT — qualifying discipline</h4>
          <p>The one place Discipline is non-negotiable. Treat it as a separate system from the rest of your work, not something Positivity and Woo can talk you through informally.</p>
        </div>
      </div>
    </div>
  </section>

  <!-- MARK'S CORNER -->
  <section class="section">
    <div class="marks-corner">
      <div class="mc-badge">Mark's corner</div>
      <div class="mc-list">Where you naturally win this week: <b>Woo</b> — the Jen Ilsley meeting and the Debbie/Copper Cow intro are both first-touch relationship work. <b>Strategic + Futuristic</b> — the Cabo date contradiction and the Cabo/YPO overlap need someone thinking two steps ahead, which is exactly your default setting.</div>
    </div>
  </section>

</div>

<footer class="cp-footer">
  Sources: Outlook (Theresa + Mark, delegated) · Slack (#theresa-ops, #all-nevada-tax-group) · Wispr Flow (0 upcoming meetings synced) · Gmail (needs re-authorization in claude.ai connector settings — pending, not reflected this pull)<br>
  Command Post · refreshes weekdays 7am / 12pm / 4pm PT
</footer>

<script>
(function(){
  var root = document.documentElement;
  var KEY = 'cp-palette';
  var buttons = document.querySelectorAll('.switcher button');
  function apply(p){
    root.setAttribute('data-palette', p);
    buttons.forEach(function(b){ b.classList.toggle('active', b.dataset.p === p); });
  }
  var saved = 'earth';
  try { saved = localStorage.getItem(KEY) || 'earth'; } catch(e) {}
  apply(saved);
  buttons.forEach(function(b){
    b.addEventListener('click', function(){
      apply(b.dataset.p);
      try { localStorage.setItem(KEY, b.dataset.p); } catch(e) {}
    });
  });
})();
</script>

</body>
</html>

CPEOF_MARKER_UNIQUE_9f3a

cat > 'Dockerfile' <<'CPEOF_MARKER_UNIQUE_9f3a'
FROM nginx:alpine
COPY index.html /usr/share/nginx/html/index.html
COPY nginx.conf /etc/nginx/conf.d/default.conf
EXPOSE 8080

CPEOF_MARKER_UNIQUE_9f3a

cat > 'nginx.conf' <<'CPEOF_MARKER_UNIQUE_9f3a'
server {
    listen 8080;
    server_name _;
    root /usr/share/nginx/html;
    index index.html;

    location / {
        try_files $uri $uri/ /index.html;
        add_header Cache-Control "no-store, must-revalidate";
    }
}

CPEOF_MARKER_UNIQUE_9f3a

cat > 'fly.toml' <<'CPEOF_MARKER_UNIQUE_9f3a'
# Fly.io app config for Command Post
# App name must be globally unique on Fly — change it if 'command-post-mt' is taken:
#   fly apps create command-post-mt
app = "command-post-mt"
primary_region = "sjc"

[build]

[http_service]
  internal_port = 8080
  force_https = true
  auto_stop_machines = false
  auto_start_machines = true
  min_machines_running = 1

[[vm]]
  size = "shared-cpu-1x"
  memory = "256mb"

CPEOF_MARKER_UNIQUE_9f3a

mkdir -p ".github/workflows"
cat > '.github/workflows/deploy.yml' <<'CPEOF_MARKER_UNIQUE_9f3a'
name: Deploy to Fly.io

on:
  push:
    branches: [main]
  workflow_dispatch:

jobs:
  deploy:
    runs-on: ubuntu-latest
    concurrency: deploy-group
    steps:
      - uses: actions/checkout@v4
      - uses: superfly/flyctl-actions/setup-flyctl@master
      - run: flyctl deploy --remote-only
        env:
          FLY_API_TOKEN: ${{ secrets.FLY_API_TOKEN }}

CPEOF_MARKER_UNIQUE_9f3a

cat > '.gitignore' <<'CPEOF_MARKER_UNIQUE_9f3a'
.DS_Store
*.log
fly.toml.bak

CPEOF_MARKER_UNIQUE_9f3a

cat > 'README.md' <<'CPEOF_MARKER_UNIQUE_9f3a'
# Command Post

Mark's live EA dashboard for Theresa — a static snapshot of the Command Post, containerized and deployed to Fly.io so it has its own always-on URL, independent of Claude.

**Important — read this first:** this repo serves a *snapshot* of the dashboard, not a self-refreshing one. The version with live Outlook/Slack/Wispr data that actually refreshes itself (weekdays 7am/12pm/4pm PT) is the Claude-published artifact:
https://claude.ai/code/artifact/7b0135db-07df-4bb3-8583-a189fdad0dbf
— that link already works 24/7 from your phone with no setup below.

Deploy this repo to Fly.io if you want an independent URL/custom domain you control. Each time Claude refreshes the dashboard content, it can also push the updated `index.html` here, which redeploys automatically via the GitHub Action below — so this stays current too, just one push-and-redeploy behind rather than truly real-time.

## One-time setup (do this once, from a computer)

1. **Install flyctl** and sign in:
   ```
   curl -L https://fly.io/install.sh | sh
   fly auth login
   ```
2. **Create the Fly app** (from inside this repo folder):
   ```
   fly launch --no-deploy --copy-config --name command-post-mt
   ```
   If that name is taken, pick another and update `app = "..."` in `fly.toml` to match.
3. **Create a deploy token** and add it to GitHub so Actions can deploy on your behalf:
   ```
   fly tokens create deploy
   ```
   Copy the output token, then in the GitHub repo: **Settings → Secrets and variables → Actions → New repository secret**
   - Name: `FLY_API_TOKEN`
   - Value: (the token you copied)
4. **First deploy** — either push to `main` (the Action will run automatically) or run it yourself once:
   ```
   fly deploy
   ```

After that, every push to `main` redeploys automatically via `.github/workflows/deploy.yml`.

## Files

- `index.html` — the dashboard page (static snapshot)
- `Dockerfile` / `nginx.conf` — serves it on port 8080
- `fly.toml` — Fly app config, set to stay on 24/7 (`min_machines_running = 1`, no auto-stop)
- `.github/workflows/deploy.yml` — GitHub Action that deploys to Fly on every push to `main`

## Updating the content

Ask Claude to push a fresh `index.html` to this repo's `main` branch after the next Command Post refresh, or replace the file yourself and push — either way the Action redeploys it.

CPEOF_MARKER_UNIQUE_9f3a

git add -A
git commit -m "Command Post: static site + Fly.io deploy config" || echo "nothing to commit"
git branch -M main
git push -u origin main
echo 'Done. Pushed to origin/main.'
