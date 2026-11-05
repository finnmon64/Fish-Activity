<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8" />
  <meta name="viewport" content="width=device-width, initial-scale=1.0, maximum-scale=1.0, user-scalable=no" />
  <meta name="theme-color" content="#1362c6" />
  <meta name="apple-mobile-web-app-capable" content="yes" />
  <meta name="apple-mobile-web-app-status-bar-style" content="black-translucent" />
  <title>Fish Activity</title>
  <script src="https://cdn.jsdelivr.net/npm/astronomy-engine@2.1.19/astronomy.browser.min.js"></script>
  <style>
    :root {
      --bg-top: #115ec1;
      --bg-bottom: #186bd4;
      --text-main: #ffffff;
      --text-muted: rgba(255, 255, 255, 0.68);
      --grid-line: rgba(255, 255, 255, 0.14);
    }
    * { box-sizing: border-box; margin: 0; padding: 0; -webkit-tap-highlight-color: transparent; font-family: -apple-system, BlinkMacSystemFont, "Roboto", "Segoe UI", sans-serif; }
    body {
      background: linear-gradient(180deg, var(--bg-top) 0%, var(--bg-bottom) 100%);
      color: var(--text-main);
      min-height: 100vh;
      display: flex;
      flex-direction: column;
      align-items: center;
      user-select: none;
    }
    .app-shell { width: 100%; max-width: 440px; min-height: 100vh; display: flex; flex-direction: column; position: relative; padding-bottom: 80px; }

    /* Top Bar */
    header { display: flex; align-items: center; justify-content: space-between; padding: 16px 18px 8px; }
    header h1 { font-size: 1.25rem; font-weight: 500; letter-spacing: 0.2px; }
    .header-icons { display: flex; gap: 14px; align-items: center; }
    .icon-btn { background: none; border: none; color: #fff; cursor: pointer; font-size: 1.15rem; opacity: 0.9; padding: 4px; }

    /* Date Strip */
    .date-strip { display: grid; grid-template-columns: repeat(7, 1fr); padding: 8px 10px 4px; text-align: center; }
    .date-item { padding: 6px 0 8px; cursor: pointer; color: var(--text-muted); border-bottom: 2.5px solid transparent; transition: all 0.15s; }
    .date-item.active { color: #fff; border-bottom-color: #fff; }
    .date-item .day-num { font-size: 1.15rem; font-weight: 400; margin-bottom: 3px; }
    .date-item.active .day-num { font-weight: 600; }
    .date-item .day-name { font-size: 0.72rem; font-weight: 500; letter-spacing: 0.4px; text-transform: uppercase; }

    /* Location Row */
    .loc-row { display: flex; justify-content: flex-end; padding: 6px 18px 0; }
    .loc-select {
      background: rgba(0, 0, 0, 0.15);
      color: #fff;
      border: 1px solid rgba(255, 255, 255, 0.25);
      border-radius: 16px;
      padding: 4px 10px;
      font-size: 0.82rem;
      font-weight: 500;
      outline: none;
      cursor: pointer;
    }
    .loc-select option { background: #115ec1; color: #fff; }

    /* Radial Score Gauge */
    .score-section { display: flex; flex-direction: column; align-items: center; margin: 10px 0 14px; }
    .gauge-box { width: 126px; height: 126px; position: relative; display: flex; flex-direction: column; align-items: center; justify-content: center; }
    .gauge-svg { position: absolute; inset: 0; width: 100%; height: 100%; transform: rotate(-90deg); }
    .score-val { font-size: 2.85rem; font-weight: 500; line-height: 1; margin-top: -4px; }
    .stars-val { font-size: 0.82rem; letter-spacing: 3px; min-height: 16px; margin-top: 4px; color: #fff; }
    .label-val { font-size: 1.2rem; font-weight: 500; margin-top: 12px; letter-spacing: 0.2px; }

    /* 24h Curve Chart */
    .chart-container { position: relative; width: 100%; height: 220px; margin-top: 4px; }
    .band-label { position: absolute; left: 8px; font-size: 0.68rem; font-weight: 500; color: rgba(255,255,255,0.75); letter-spacing: 0.4px; pointer-events: none; }
    .band-high { top: 24px; }
    .band-med { top: 88px; }
    .band-low { top: 152px; }
    #curve-svg { width: 100%; height: 100%; display: block; }

    /* Major / Minor Times */
    .times-grid { display: grid; grid-template-columns: 1fr 1fr; padding: 18px 16px 24px; gap: 12px; text-align: center; }
    .times-col h3 { font-size: 0.78rem; font-weight: 500; color: var(--text-muted); text-transform: uppercase; letter-spacing: 0.5px; margin-bottom: 10px; }
    .time-entry { font-size: 0.92rem; font-weight: 500; margin-bottom: 8px; line-height: 1.25; }
    .day-offset { display: block; font-size: 0.68rem; font-weight: 400; font-style: italic; color: var(--text-muted); margin-top: 1px; }

    /* Floating Calendar Button */
    .fab-cal {
      position: fixed;
      bottom: 22px;
      right: max(22px, calc(50vw - 198px));
      width: 54px;
      height: 54px;
      border-radius: 50%;
      background: #ffffff;
      color: #1362c6;
      border: none;
      box-shadow: 0 4px 12px rgba(0,0,0,0.3);
      font-size: 1.35rem;
      display: flex;
      align-items: center;
      justify-content: center;
      cursor: pointer;
    }
    #date-picker { position: absolute; opacity: 0; pointer-events: none; width: 0; height: 0; }
  </style>
</head>
<body>
  <div class="app-shell">
    <header>
      <h1>Fish activity</h1>
      <div class="header-icons">
        <button class="icon-btn" id="gps-btn" title="Use GPS Location">📍</button>
      </div>
    </header>

    <div class="date-strip" id="date-strip"></div>

    <div class="loc-row">
      <select class="loc-select" id="loc-select">
        <option value="-41.2866,174.7756,Pacific/Auckland">Wellington Region</option>
        <option value="-38.9897,175.8080,Pacific/Auckland">Tūrangi (Lake Taupō)</option>
        <option value="-43.5320,172.6306,Pacific/Auckland">Christchurch Region</option>
        <option value="49.2827,-123.1207,America/Vancouver">Vancouver, BC</option>
        <option value="21.3069,-157.8583,Pacific/Honolulu">Honolulu, HI</option>
      </select>
    </div>

    <div class="score-section">
      <div class="gauge-box">
        <svg class="gauge-svg" viewBox="0 0 120 120">
          <!-- Background 60-tick ring -->
          <circle cx="60" cy="60" r="48" fill="none" stroke="rgba(255,255,255,0.22)" stroke-width="10" stroke-dasharray="2.2 2.826" />
          <!-- Active 60-tick ring -->
          <circle id="gauge-ticks" cx="60" cy="60" r="48" fill="none" stroke="#ffffff" stroke-width="10" stroke-dasharray="2.2 2.826" stroke-dashoffset="301.6" />
        </svg>
        <div class="score-val" id="score-val">--</div>
        <div class="stars-val" id="stars-val"></div>
      </div>
      <div class="label-val" id="label-val">Loading...</div>
    </div>

    <div class="chart-container">
      <span class="band-label band-high">HIGH</span>
      <span class="band-label band-med">MEDIUM</span>
      <span class="band-label band-low">LOW</span>
      <svg id="curve-svg" viewBox="0 0 440 220" preserveAspectRatio="none"></svg>
    </div>

    <div class="times-grid">
      <div class="times-col">
        <h3>Major Times</h3>
        <div id="major-list"></div>
      </div>
      <div class="times-col">
        <h3>Minor Times</h3>
        <div id="minor-list"></div>
      </div>
    </div>

    <button class="fab-cal" id="cal-btn" title="Pick Date">📅</button>
    <input type="date" id="date-picker" />
  </div>

  <script>
    let currentLocation = { lat: -41.2866, lon: 174.7756, tz: 'Pacific/Auckland', label: 'Wellington Region' };
    let selectedDate = new Date();
    selectedDate.setHours(12, 0, 0, 0);

    // Format helper in target timezone
    function getTzParts(date, timeZone) {
      const fmt = new Intl.DateTimeFormat('en-US', {
        timeZone, year: 'numeric', month: 'numeric', day: 'numeric',
        hour: 'numeric', minute: 'numeric', second: 'numeric', hour12: false
      });
      const parts = {};
      fmt.formatToParts(date).forEach(p => { if (p.type !== 'literal') parts[p.type] = parseInt(p.value, 10); });
      if (parts.hour === 24) parts.hour = 0;
      return parts;
    }

    // Build exact UTC Date corresponding to 00:00:00 local time in target timezone
    function getStartOfLocalDayUTC(year, month, day, timeZone) {
      const approx = new Date(Date.UTC(year, month - 1, day, 0, 0, 0));
      const parts = getTzParts(approx, timeZone);
      const asUTC = Date.UTC(parts.year, parts.month - 1, parts.day, parts.hour, parts.minute, parts.second);
      const offsetMs = asUTC - approx.getTime();
      return new Date(Date.UTC(year, month - 1, day, 0, 0, 0) - offsetMs);
    }

    function computeSolunar(year, month, day, loc) {
      const observer = new Astronomy.Observer(loc.lat, loc.lon, 0);
      const dayStartUTC = getStartOfLocalDayUTC(year, month, day, loc.tz);
      const dayEndUTC = new Date(dayStartUTC.getTime() + 24 * 3600000);
      const dayMidUTC = new Date(dayStartUTC.getTime() + 12 * 3600000);

      // 1. Calibrated Phase Score with ~11 deg (~22h) post-syzygy inertia lag
      const phaseDeg = Astronomy.MoonPhase(dayMidUTC);
      const laggedRad = ((phaseDeg - 11.0) * Math.PI) / 180.0;
      const rawScore = 54.5 + 42.5 * Math.cos(2 * laggedRad);
      const score = Math.max(5, Math.min(100, Math.round(rawScore)));

      // 2. Collect all Major (Upper/Lower Transit) and Minor (Rise/Set) events near this 24h window
      const searchStart = new Date(dayStartUTC.getTime() - 14 * 3600000);
      const searchEnd = new Date(dayEndUTC.getTime() + 14 * 3600000);

      const majors = [];
      const minors = [];

      [0, 12].forEach(hourAngle => {
        let t = searchStart;
        while (t < searchEnd) {
          const ev = Astronomy.SearchHourAngle(Astronomy.Body.Moon, observer, hourAngle, t);
          if (!ev || ev.time.date >= searchEnd) break;
          majors.push({ time: ev.time.date, hourAngle });
          t = new Date(ev.time.date.getTime() + 18 * 3600000);
        }
      });

      [+1, -1].forEach(dir => {
        let t = searchStart;
        while (t < searchEnd) {
          const ev = Astronomy.SearchRiseSet(Astronomy.Body.Moon, observer, dir, t, 2);
          if (!ev || ev.date >= searchEnd) break;
          minors.push({ time: ev.date, dir });
          t = new Date(ev.date.getTime() + 18 * 3600000);
        }
      });

      majors.sort((a, b) => a.time - b.time);
      minors.sort((a, b) => a.time - b.time);

      return { score, majors, minors, dayStartUTC, dayEndUTC };
    }

    function formatClock(utcDate, tz) {
      const p = getTzParts(utcDate, tz);
      const ampm = p.hour >= 12 ? 'pm' : 'am';
      const h12 = p.hour % 12 || 12;
      const mStr = p.minute < 10 ? '0' + p.minute : p.minute;
      return `${h12}:${mStr} ${ampm}`;
    }

    function formatWindowHTML(centerUTC, halfWidthHours, dayStartUTC, dayEndUTC, tz) {
      const startUTC = new Date(centerUTC.getTime() - halfWidthHours * 3600000);
      const endUTC = new Date(centerUTC.getTime() + halfWidthHours * 3600000);
      let badge = '';
      if (startUTC < dayStartUTC) badge = '<span class="day-offset">previous day</span>';
      else if (endUTC >= dayEndUTC) badge = '<span class="day-offset">next day</span>';
      return `<div class="time-entry">${formatClock(startUTC, tz)} – ${formatClock(endUTC, tz)}${badge}</div>`;
    }

    function render() {
      const y = selectedDate.getFullYear();
      const m = selectedDate.getMonth() + 1;
      const d = selectedDate.getDate();

      const data = computeSolunar(y, m, d, currentLocation);
      const score = data.score;

      // Update Score & Stars
      document.getElementById('score-val').textContent = score;
      let stars = '';
      if (score >= 90) stars = '★★★';
      else if (score >= 40) stars = '★★';
      else if (score >= 20) stars = '★';
      document.getElementById('stars-val').textContent = stars;

      // Update Label
      let label = 'Very high fish activity';
      if (score < 20) label = 'Very low fish activity';
      else if (score < 40) label = 'Low fish activity';
      else if (score < 70) label = 'Average fish activity';
      else if (score < 85) label = 'High fish activity';
      document.getElementById('label-val').textContent = label;

      // Update 60-tick segmented gauge (circumference = 2 * pi * 48 = 301.59)
      const circumference = 301.59;
      const dashOffset = circumference * (1 - score / 100);
      document.getElementById('gauge-ticks').style.strokeDashoffset = dashOffset.toFixed(2);

      // Filter windows: ONLY events whose center falls within [00:00, 24:00) local day
      const activeMajors = data.majors.filter(e => e.time >= data.dayStartUTC && e.time < data.dayEndUTC);
      const activeMinors = data.minors.filter(e => e.time >= data.dayStartUTC && e.time < data.dayEndUTC);

      document.getElementById('major-list').innerHTML = activeMajors.map(
        e => formatWindowHTML(e.time, 1.25, data.dayStartUTC, data.dayEndUTC, currentLocation.tz)
      ).join('') || '<div class="time-entry">–</div>';

      document.getElementById('minor-list').innerHTML = activeMinors.map(
        e => formatWindowHTML(e.time, 0.75, data.dayStartUTC, data.dayEndUTC, currentLocation.tz)
      ).join('') || '<div class="time-entry">–</div>';

      renderChart(data);
    }

    function renderChart(data) {
      const svg = document.getElementById('curve-svg');
      const W = 440, H = 220;
      const topPad = 24, botPad = 34;
      const plotH = H - topPad - botPad;
      const startMs = data.dayStartUTC.getTime();
      const score = data.score;

      // Baseline rises with daily score
      const baseLevel = 12 + (score / 100) * 38;
      const majorAmp = 26 + (score / 100) * 18;
      const minorAmp = 15 + (score / 100) * 10;

      function sampleCurve(hr) {
        const tMs = startMs + hr * 3600000;
        let v = baseLevel;

        data.majors.forEach(m => {
          const dt = (tMs - m.time.getTime()) / 3600000;
          // Raised cosine main lobe + gentle shoulder ripple matching app's waveform
          if (Math.abs(dt) <= 2.2) {
            const w = Math.cos((Math.PI * dt) / 2.2);
            v += majorAmp * Math.pow(Math.max(0, w), 1.6);
          }
          if (Math.abs(dt) > 1.4 && Math.abs(dt) <= 3.2) {
            v -= 3.5 * Math.sin(((Math.abs(dt) - 1.4) / 1.8) * Math.PI);
          }
        });

        data.minors.forEach(m => {
          const dt = (tMs - m.time.getTime()) / 3600000;
          if (Math.abs(dt) <= 1.55) {
            const w = Math.cos((Math.PI * dt) / 1.55);
            v += minorAmp * Math.pow(Math.max(0, w), 1.7);
          }
        });

        return Math.max(4, Math.min(96, v));
      }

      const pts = [];
      const steps = 120;
      for (let i = 0; i <= steps; i++) {
        const hr = (i / steps) * 24;
        const x = (hr / 24) * W;
        const val = sampleCurve(hr);
        const y = topPad + plotH * (1 - val / 100);
        pts.push({ x, y, hr });
      }

      const linePath = pts.map((p, idx) => `${idx === 0 ? 'M' : 'L'} ${p.x.toFixed(1)},${p.y.toFixed(1)}`).join(' ');
      const areaPath = `${linePath} L ${W},${H - botPad} L 0,${H - botPad} Z`;

      // Horizontal dashed bands & vertical 4-hour gridlines
      const yHigh = topPad + plotH * 0.22;
      const yMed = topPad + plotH * 0.54;
      const yLow = topPad + plotH * 0.86;

      let gridHTML = `
        <defs>
          <linearGradient id="areaGrad" x1="0" y1="0" x2="0" y2="1">
            <stop offset="0%" stop-color="#ffffff" stop-opacity="0.38"/>
            <stop offset="100%" stop-color="#ffffff" stop-opacity="0.02"/>
          </linearGradient>
        </defs>
        <line x1="0" y1="${yHigh}" x2="${W}" y2="${yHigh}" stroke="var(--grid-line)" stroke-dasharray="3,3" />
        <line x1="0" y1="${yMed}" x2="${W}" y2="${yMed}" stroke="var(--grid-line)" stroke-dasharray="3,3" />
        <line x1="0" y1="${yLow}" x2="${W}" y2="${yLow}" stroke="var(--grid-line)" stroke-dasharray="3,3" />
      `;

      const labels = ['4:00 am', '8:00 am', '12:00 pm', '4:00 pm', '8:00 pm'];
      [4, 8, 12, 16, 20].forEach((hr, i) => {
        const x = (hr / 24) * W;
        gridHTML += `
          <line x1="${x}" y1="${topPad - 10}" x2="${x}" y2="${H - botPad}" stroke="var(--grid-line)" />
          <text x="${x}" y="${H - 10}" fill="rgba(255,255,255,0.7)" font-size="11" text-anchor="middle">${labels[i]}</text>
        `;
      });

      // Red dot current time indicator if viewing Today
      let dotHTML = '';
      const now = new Date();
      if (now >= data.dayStartUTC && now < data.dayEndUTC) {
        const curHr = (now.getTime() - startMs) / 3600000;
        const cx = (curHr / 24) * W;
        const cy = topPad + plotH * (1 - sampleCurve(curHr) / 100);
        dotHTML = `<circle cx="${cx.toFixed(1)}" cy="${cy.toFixed(1)}" r="6" fill="#e53935" stroke="#ffffff" stroke-width="2" />`;
      }

      svg.innerHTML = `
        ${gridHTML}
        <path d="${areaPath}" fill="url(#areaGrad)" stroke="none" />
        <path d="${linePath}" fill="none" stroke="#ffffff" stroke-width="3" stroke-linecap="round" stroke-linejoin="round" />
        ${dotHTML}
      `;
    }

    function renderDateStrip() {
      const strip = document.getElementById('date-strip');
      strip.innerHTML = '';
      const dayNames = ['SUN', 'MON', 'TUE', 'WED', 'THU', 'FRI', 'SAT'];
      const todayParts = getTzParts(new Date(), currentLocation.tz);

      for (let offset = -3; offset <= 3; offset++) {
        const d = new Date(selectedDate);
        d.setDate(selectedDate.getDate() + offset);
        const isToday = d.getFullYear() === todayParts.year && (d.getMonth() + 1) === todayParts.month && d.getDate() === todayParts.day;

        const cell = document.createElement('div');
        cell.className = `date-item ${offset === 0 ? 'active' : ''}`;
        cell.innerHTML = `
          <div class="day-num">${d.getDate()}</div>
          <div class="day-name">${isToday ? 'TODAY' : dayNames[d.getDay()]}</div>
        `;
        cell.addEventListener('click', () => {
          selectedDate = d;
          renderDateStrip();
          render();
        });
        strip.appendChild(cell);
      }
    }

    // Controls Setup
    document.getElementById('loc-select').addEventListener('change', (e) => {
      const [lat, lon, tz] = e.target.value.split(',');
      currentLocation = { lat: parseFloat(lat), lon: parseFloat(lon), tz };
      renderDateStrip();
      render();
    });

    document.getElementById('gps-btn').addEventListener('click', () => {
      if (!navigator.geolocation) return;
      navigator.geolocation.getCurrentPosition(pos => {
        const tz = Intl.DateTimeFormat().resolvedOptions().timeZone;
        currentLocation = { lat: pos.coords.latitude, lon: pos.coords.longitude, tz };
        const sel = document.getElementById('loc-select');
        const opt = document.createElement('option');
        opt.value = `${ currentLocation.lat },${ currentLocation.lon },${ tz }`;
        opt.textContent = `GPS (${currentLocation.lat.toFixed(2)}°, ${currentLocation.lon.toFixed(2)}°)`;
        sel.appendChild(opt);
        sel.value = opt.value;
        renderDateStrip();
        render();
      });
    });

    const picker = document.getElementById('date-picker');
    document.getElementById('cal-btn').addEventListener('click', () => {
      if (picker.showPicker) picker.showPicker();
      else picker.click();
    });
    picker.addEventListener('change', (e) => {
      if (!e.target.value) return;
      const [y, m, d] = e.target.value.split('-').map(Number);
      selectedDate = new Date(y, m - 1, d, 12, 0, 0);
      renderDateStrip();
      render();
    });

    renderDateStrip();
    render();
  </script>
</body>
</html>
