# effective-octo-engine
<!DOCTYPE html>
<html lang="ko">
<head>
<meta charset="UTF-8" />
<meta name="viewport" content="width=device-width, initial-scale=1.0" />
<title>FTJ Lab v13 — MFS semiconductor electrode · depletion / λ_TF · Bending · PUND</title>
<link rel="stylesheet" href="https://cdn.jsdelivr.net/npm/katex@0.16.9/dist/katex.min.css">
<script defer src="https://cdn.jsdelivr.net/npm/katex@0.16.9/dist/katex.min.js"></script>
<script defer src="https://cdn.jsdelivr.net/npm/katex@0.16.9/dist/contrib/auto-render.min.js"
  onload="renderMathInElement(document.body,{delimiters:[{left:'$$',right:'$$',display:true},{left:'$',right:'$',display:false}],throwOnError:false});"></script>
<style>
:root{
  --bg:#07111f; --bg2:#0b1628; --panel:#101c31; --panel2:#0b1324; --line:#2d3c59;
  --ink:#eef5ff; --muted:#b7c5df; --card:#ffffff; --cardInk:#0f172a;
  --blue:#2563eb; --cyan:#0891b2; --green:#16a34a; --red:#dc2626; --orange:#f59e0b;
  --violet:#7c3aed; --pink:#db2777; --slate:#475569;
}
*{box-sizing:border-box}
html,body{margin:0;min-height:100%;font-family:Inter,system-ui,-apple-system,BlinkMacSystemFont,"Segoe UI",sans-serif;background:linear-gradient(135deg,var(--bg),#0d1729 55%,#111d34);color:var(--ink)}
body{overflow:hidden}
.app{height:100vh;display:grid;grid-template-columns:440px minmax(900px,1fr)}
.sidebar{background:linear-gradient(180deg,#111c32,#07101e);border-right:1px solid #263653;overflow:auto;padding:18px;box-shadow:16px 0 38px rgba(0,0,0,.22)}
.main{overflow:auto;padding:20px 22px 28px}
.sidebar::-webkit-scrollbar,.main::-webkit-scrollbar{width:10px;height:10px}.sidebar::-webkit-scrollbar-thumb,.main::-webkit-scrollbar-thumb{background:#334766;border-radius:999px}
.brand{padding:8px 4px 16px;border-bottom:1px solid #283954;margin-bottom:14px}
.brand h1{font-size:28px;line-height:1.05;margin:0;letter-spacing:-.035em}
.brand .sub{font-size:12.5px;line-height:1.55;color:#c7d6ef;margin-top:9px}
.badges{display:flex;flex-wrap:wrap;gap:7px;margin-top:12px}
.badge{background:#13213a;border:1px solid #31425f;border-radius:999px;color:#dbeafe;padding:5px 9px;font-size:11px;font-weight:850}
.badge.fix{background:#062e1a;border-color:#14532d;color:#bbf7d0}
.box{background:rgba(16,28,49,.9);border:1px solid #2b3a58;border-radius:18px;padding:14px;margin-bottom:12px;box-shadow:0 18px 38px rgba(0,0,0,.19)}
.box h2{font-size:15px;margin:0 0 10px;display:flex;align-items:center;justify-content:space-between;gap:10px}
.box h2 small{font-size:10px;text-transform:uppercase;letter-spacing:.08em;color:#7dd3fc}
.helper{font-size:12px;color:#b7c5dd;line-height:1.48;margin:0 0 10px}
.tiny{font-size:11px;color:#9fb2d2;line-height:1.45}
button,select,textarea,input{font:inherit}
.btn{cursor:pointer;border:0;border-radius:12px;padding:10px 10px;background:#dbeafe;color:#0f172a;font-weight:880}
.btn.secondary{background:#0b1220;color:#e5efff;border:1px solid #334766}
.btn.warn{background:#fee2e2;color:#7f1d1d}
.btn.good{background:#dcfce7;color:#14532d}
.btn:hover{filter:brightness(1.08)}
.grid2{display:grid;grid-template-columns:1fr 1fr;gap:8px}
.grid3{display:grid;grid-template-columns:1fr 1fr 1fr;gap:8px}
.grid4{display:grid;grid-template-columns:repeat(4,1fr);gap:8px}
select,textarea,input[type=number],input[type=text]{width:100%;background:#0b1220;color:#eef4ff;border:1px solid #334766;border-radius:12px;padding:10px}
.num label,label{font-size:12px;color:#cfe0f8}
.num{display:grid;grid-template-columns:1fr 1fr;gap:8px}
.num label{display:block;margin-bottom:4px}
.num input{font-size:12px;padding:9px}
.slider{margin:9px 0}
.sliderHead{display:grid;grid-template-columns:1fr auto;gap:10px;align-items:end}
.sliderHead label{line-height:1.25}
.val{font-variant-numeric:tabular-nums;color:#93c5fd;font-size:12px;font-weight:850}
input[type=range]{width:100%;accent-color:#60a5fa}
textarea{min-height:108px;resize:vertical;font-size:12px;line-height:1.45}
.quickVolt{display:grid;grid-template-columns:repeat(4,1fr);gap:7px;margin-top:9px}
.quickVolt button{font-size:12px;padding:8px 6px;border-radius:10px;background:#0b1220;color:#dbeafe;border:1px solid #334766;cursor:pointer}
.quickVolt button:hover{background:#13213a}
.filelike{font-size:12px}
.hr{height:1px;background:#2b3a58;margin:10px 0}
.top{display:flex;justify-content:space-between;gap:16px;align-items:flex-start;margin-bottom:16px}
.top h2{font-size:30px;line-height:1.08;letter-spacing:-.035em;margin:0}
.top p{margin:8px 0 0;color:#d1ddf0;line-height:1.5;font-size:13px;max-width:1100px}
.actions{display:flex;gap:8px;flex-wrap:wrap;justify-content:flex-end;min-width:260px}
.kpis{display:grid;grid-template-columns:repeat(8,minmax(118px,1fr));gap:10px;margin-bottom:16px}
.kpi{background:linear-gradient(180deg,#101b30,#0b1322);border:1px solid #293a5a;border-radius:16px;padding:12px;box-shadow:0 16px 34px rgba(0,0,0,.18)}
.kpi .k{font-size:10px;color:#9eb1d1;text-transform:uppercase;letter-spacing:.08em}
.kpi .v{font-size:20px;font-weight:950;margin-top:6px}
.kpi .s{font-size:11px;color:#d0d9ea;margin-top:4px;line-height:1.35}
.board{display:grid;grid-template-columns:1fr 1fr;gap:16px}
.card{background:var(--card);color:var(--cardInk);border:1px solid #dbe3ef;border-radius:22px;padding:16px;box-shadow:0 18px 40px rgba(0,0,0,.18)}
.card.wide{grid-column:1/-1}
.card h3{margin:0;font-size:18px;display:flex;justify-content:space-between;gap:10px;align-items:center}
.card h3 small{font-size:11px;border-radius:999px;background:#eff6ff;color:#1d4ed8;border:1px solid #bfdbfe;padding:5px 9px;white-space:nowrap}
.desc{font-size:13px;color:#475569;line-height:1.5;margin:8px 0 12px}
.canvasBox{border-radius:14px;overflow:hidden;background:#fff;border:1px solid #e5eaf3}
canvas{display:block;width:100%;background:#fff;border-radius:12px}
.panelText{font-size:13px;line-height:1.6;color:#243044}
.panelText b{color:#0f172a}
.pill{display:inline-block;border:1px solid #334766;border-radius:999px;padding:3px 9px;margin:0 6px 6px 0;background:#111c31;color:#dbeafe;font-size:11px;font-weight:850}
.pill.good{background:#052e1a;color:#bbf7d0;border-color:#14532d}
.pill.warn{background:#451a03;color:#fed7aa;border-color:#92400e}
.pill.bad{background:#450a0a;color:#fecaca;border-color:#991b1b}
table{border-collapse:collapse;width:100%;font-size:12px}
th,td{border-bottom:1px solid #e2e8f0;padding:7px 8px;text-align:right}
th:first-child,td:first-child{text-align:left}
th{color:#334155;background:#f8fafc;font-size:11px;text-transform:uppercase;letter-spacing:.06em}
.footer{display:flex;justify-content:space-between;gap:14px;margin-top:14px;color:#aebbd6;font-size:12px}
@media(max-width:1180px){
  body{overflow:auto}.app{height:auto;display:block}
  .sidebar{max-height:none}.main{overflow:visible}
  .kpis{grid-template-columns:repeat(2,1fr)}.board{grid-template-columns:1fr}
  .top{display:block}.actions{justify-content:flex-start;margin-top:12px}
}
/* === v9 additions === */
.cardHeadRow{display:flex;justify-content:space-between;align-items:flex-start;gap:10px}
.cardTitleBlock{flex:1;min-width:0}
.subQ{font-size:12.5px;color:#1d4ed8;margin-top:4px;font-style:italic;line-height:1.4}
.whyBtn{cursor:pointer;border:1px solid #c7d4ec;background:#eff6ff;color:#1d4ed8;border-radius:999px;padding:5px 11px;font-size:11px;font-weight:880;white-space:nowrap;transition:all .15s}
.whyBtn:hover{background:#dbeafe;border-color:#93c5fd}
.whyBtn.open{background:#1d4ed8;color:#fff;border-color:#1d4ed8}
.whyBox{display:none;margin-top:10px;background:linear-gradient(180deg,#f8fafc,#eef4fb);border:1px solid #cbd5e1;border-left:4px solid #1d4ed8;border-radius:10px;padding:12px 14px;font-size:12.5px;line-height:1.65;color:#1e293b}
.whyBox.open{display:block}
.whyBox h4{margin:0 0 6px;font-size:12px;text-transform:uppercase;letter-spacing:.06em;color:#1d4ed8;font-weight:900}
.whyBox h4:not(:first-child){margin-top:10px}
.whyBox .formula{background:#fff;border:1px solid #e2e8f0;border-radius:8px;padding:8px 12px;margin:5px 0;font-size:13px;overflow-x:auto}
.whyBox ul{margin:4px 0;padding-left:20px}.whyBox li{margin:2px 0}
.whyBox .warn{background:#fef3c7;border:1px solid #fcd34d;border-left:3px solid #d97706;border-radius:6px;padding:7px 10px;margin-top:8px;color:#78350f;font-size:12px;line-height:1.55}
.whyBox .warn b{color:#92400e}
.apparent{display:inline-block;background:#fef3c7;color:#78350f;border:1px solid #fcd34d;border-radius:6px;padding:1px 6px;font-size:10px;font-weight:850;letter-spacing:.04em;margin-left:5px;vertical-align:1px}
.polGrid{display:grid;grid-template-columns:1fr 1fr;gap:12px;margin-top:6px}
.polCell{background:#f8fafc;border:1px solid #e2e8f0;border-radius:10px;padding:10px}
.polCell h5{margin:0 0 6px;font-size:11px;text-transform:uppercase;letter-spacing:.07em;color:#475569;font-weight:880;display:flex;justify-content:space-between;align-items:center}
.polCell h5 .tag{font-size:10px;background:#e0e7ff;color:#3730a3;padding:2px 7px;border-radius:999px;letter-spacing:.04em}
.polCell h5 .tag.neg{background:#fee2e2;color:#991b1b}
.polCell canvas{height:160px}
.polNote{font-size:11.5px;color:#64748b;margin-top:8px;line-height:1.45}
.legendInline{display:flex;gap:14px;flex-wrap:wrap;font-size:11.5px;color:#475569;margin-top:6px}
.legendInline .dot{display:inline-block;width:10px;height:10px;border-radius:2px;margin-right:5px;vertical-align:-1px}
</style>
</head>
<body>
<div class="app">
<aside class="sidebar">
  <div class="brand">
    <h1>FTJ Lab v13<br><span style="font-size:14px;font-weight:700;letter-spacing:.05em">MFS · Depletion · λ_TF</span></h1>
    <div class="sub">v12 위에 <b>MFS (Metal–Ferroelectric–Semiconductor)</b> 추가: 하부 전극에 <b>InGaAs:p++</b> 등 축퇴 반도체 선택 가능. MFM/MFIM과 달리 <b>극성 의존 공핍층(W) 전압분배</b>, <b>긴 screening length(λ_TF)에 의한 depol field 잔존</b>, <b>write-voltage penalty</b>를 모델·시각화. Band·V/E/Charge profile에 공핍 tail과 ionized-acceptor 전하가 그려진다.</div>
    <div class="badges">
      <span class="badge fix">Bending visible</span>
      <span class="badge fix">PUND + Transient I-V</span>
      <span class="badge fix">Tunneling direction flip</span>
      <span class="badge">v10 BIL physics</span>
      <span class="badge">v9 Why? toggles</span>
    </div>
  </div>

  <div class="box">
    <h2>Preset &amp; Stack <small>device</small></h2>
    <div class="grid2">
      <button class="btn" id="pUser">HZO Mo/TiN</button>
      <button class="btn secondary" id="pMfm">Sym MFM</button>
      <button class="btn secondary" id="pMfis">MFIS / BIL</button>
      <button class="btn secondary" id="pLeak">Leaky / TAT</button>
    </div>
    <div style="height:8px"></div>
    <button class="btn" id="pMfs" style="width:100%;background:#0e7490">MFS · Mo / HZO / InGaAs:p++</button>
    <div style="height:10px"></div>
    <div class="grid2">
      <div><label>Top electrode</label><select id="te"></select></div>
      <div><label>Bottom electrode</label><select id="be"></select></div>
    </div>
    <div class="num" style="margin-top:8px">
      <div><label>Area (µm²)</label><input type="number" id="area" min="0.001" max="100000" step="0.01" value="100"></div>
      <div><label>Temperature (K)</label><input type="number" id="temp" min="4" max="700" step="1" value="300"></div>
    </div>
    <div style="height:8px"></div>
    <label>Energy-band view mode</label>
    <select id="mode">
      <option value="live">Live applied-voltage band</option>
      <option value="compare">OFF / ON comparison</option>
      <option value="mfm">MFM-like (no BIL)</option>
      <option value="mfis">MFIS / BIL emphasis</option>
      <option value="mfs">MFS / semiconductor electrode</option>
    </select>
    <p class="helper" style="margin-top:10px">면적·온도가 J = I/A, Schottky·PF의 T-dependent 항, noise floor에 같이 들어간다.</p>
  </div>

  <div class="box">
    <h2>Applied Voltage <small>live</small></h2>
    <p class="helper">Vapp 슬라이더가 band tilt와 V/E/Charge profile을 직접 움직인다. 정의: V<sub>app</sub> = V<sub>TE</sub> − V<sub>BE</sub>.</p>
    <div id="vappSlider"></div>
    <div class="quickVolt">
      <button data-v="0">0 V</button><button data-v="0.3">+0.3 V</button><button data-v="-0.3">−0.3 V</button><button data-v="1">+1 V</button>
      <button data-v="-1">−1 V</button><button data-v="2">+2 V</button><button data-v="-2">−2 V</button><button data-v="set">SET</button>
    </div>
  </div>

  <div class="box"><h2>Stack Physics <small>nm / eV / εr</small></h2><div id="stackSliders"></div></div>
  <div class="box">
    <h2>Semiconductor (MFS) <small>depletion / λ_TF</small></h2>
    <p class="helper">하부 전극을 <b>InGaAs:p++</b> 같은 축퇴 반도체로 고르면 활성화. 금속과 달리 polarization·field가 표면 <b>공핍층(W)</b>을 만들어 전압을 먹고(직렬 capacitance), screening length가 길어 depol field가 잔존한다. 극성에 따라 depletion↔accumulation이 뒤집힌다.</p>
    <div id="mfsSliders"></div>
  </div>
  <div class="box"><h2>Defect &amp; FE State <small>charge</small></h2><div id="defectSliders"></div></div>
  <div class="box"><h2>Measurement Knobs <small>V / pulse</small></h2><div id="measSliders"></div></div>

  <div class="box">
    <h2>Joshua Multi-Read <small>4 V scan</small></h2>
    <p class="helper">독립적인 read 4점. 우측 카드 "Multi-Read"에서 window·BER·disturb를 동시 비교하고 best read를 자동 추천.</p>
    <div id="readMultiSliders"></div>
  </div>

  <div class="box">
    <h2>CSV Data Import <small>V , I</small></h2>
    <p class="helper">전압·전류 두 열만 있으면 됨. 단위 선택 후 Analyze. mechanism fit, F-N plot, regime map에 검은 점으로 overlay된다.</p>
    <select id="dataUnit"><option value="I">column 2 = Current (A)</option><option value="J">column 2 = Current density (A/cm²)</option></select>
    <div style="height:8px"></div>
    <textarea id="csvIn" placeholder="V,I&#10;-2.0,-1.2e-8&#10;-1.5,-4.0e-9&#10;...&#10;2.0,1.8e-8"></textarea>
    <div class="grid3" style="margin-top:8px">
      <button class="btn good" id="sampleBtn">Sample</button>
      <button class="btn" id="parseBtn">Analyze</button>
      <button class="btn warn" id="clearBtn">Clear</button>
    </div>
    <p class="tiny" id="dataStatus">No external data. Synthetic curve is being used.</p>
  </div>

  <div class="box">
    <h2>Export / Import <small>config / report</small></h2>
    <div class="grid2">
      <button class="btn" id="exportConfig">Export config</button>
      <button class="btn secondary" id="exportCsv">Export report CSV</button>
    </div>
    <div style="height:8px"></div>
    <input class="filelike" type="file" id="importConfig" accept="application/json,.json" />
  </div>
</aside>

<main class="main">
  <div class="top">
    <div>
      <h2>HZO FTJ Lab v8 — Neamen × Quant Remaster</h2>
      <p>왼쪽에서 stack/defect/measurement를 바꾸면 11개 패널(band, V/E/charge, IV+components, mechanism fit, F-N plot, multi-read, regime, PUND, reliability, 32-state, summary)이 동시에 갱신된다. v7의 자기참조 F-N과 toy unit은 제거됐고, F-N φ는 R²와 함께 정직하게 보고된다.</p>
    </div>
    <div class="actions">
      <button class="btn secondary" id="copySummary">Copy summary</button>
      <button class="btn" id="autoRead">Auto-read</button>
    </div>
  </div>

  <section class="kpis">
    <div class="kpi"><div class="k">Vapp</div><div class="v" id="kVapp">-</div><div class="s" id="kVappS">live</div></div>
    <div class="kpi"><div class="k">TER / Read</div><div class="v" id="kRatio">-</div><div class="s" id="kRatioS">-</div></div>
    <div class="kpi"><div class="k">Best Read</div><div class="v" id="kBestRead">-</div><div class="s" id="kBestReadS">-</div></div>
    <div class="kpi"><div class="k">Dominant</div><div class="v" id="kMech">-</div><div class="s" id="kMechS">-</div></div>
    <div class="kpi"><div class="k">F-N φ (fit)</div><div class="v" id="kPhi">-</div><div class="s" id="kPhiS">-</div></div>
    <div class="kpi"><div class="k">PUND Qsw</div><div class="v" id="kQsw">-</div><div class="s" id="kQswS">-</div></div>
    <div class="kpi"><div class="k">32-state</div><div class="v" id="kStates">-</div><div class="s" id="kStatesS">-</div></div>
    <div class="kpi"><div class="k">Risk</div><div class="v" id="kRisk">-</div><div class="s" id="kRiskS">-</div></div>
  </section>

  <section class="board">
    <article class="card wide" id="card1"><div class="cardHeadRow">
      <div class="cardTitleBlock"><h3>1) Live energy band <small>Neamen-style, Vapp interactive</small></h3>
        <div class="subQ">분극이 바뀌면 밴드는 어디로, 얼마나 휘는가?</div></div>
      <button class="whyBtn" data-why="why1">Why?</button></div>
      <div class="whyBox" id="why1">
        <h4>핵심 인과 chain (이 도구가 보여주는 것)</h4>
        <ol style="margin:4px 0 8px;padding-left:20px">
          <li>분극 P_r → HZO 양 표면에 bound charge ±σ_P</li>
          <li>전극에서 imperfect screening → 잔여 charge가 HZO/BIL 계면에 남음</li>
          <li>잔여 charge가 BIL 양단에 internal voltage <b>V_int</b> 만듦</li>
          <li>같은 Vapp이라도 ON/OFF에서 BIL이 흡수하는 V가 ±V_int만큼 다름</li>
          <li>HZO 안 effective field가 ON/OFF에서 다름 → barrier 모양 다름</li>
          <li>WKB 적분값이 ON/OFF에서 다름 → tunneling current가 다름 → <b>TER</b></li>
        </ol>
        <h4>식</h4>
        <div class="formula">$$V_{int} = \dfrac{\sigma_{residual} \cdot t_{BIL}}{\varepsilon_0 \varepsilon_r^{BIL}} = \dfrac{P_r(1-f_{screen})\,t_{BIL}}{\varepsilon_0 \varepsilon_r^{BIL}}$$</div>
        <div class="formula">$$V_{BIL}^{ON/OFF} = V_{app}\cdot\dfrac{C_{HZO}}{C_{HZO}+C_{BIL}} \;\pm\; V_{int}$$</div>
        <div class="formula">$$\Delta\phi_P = \pm\,V_{int}\,\text{(barrier shift, ON↔OFF)}$$</div>
        <h4>BIL trade-off (FTJ 디자인의 핵심)</h4>
        <ul>
          <li><b>BIL 두꺼움</b> → V_int 크고 비대칭 강함 → <b>TER ↑</b></li>
          <li>그러나 같은 Vapp으로 HZO에 걸리는 V 줄어듦 → switching 어려움 → <b>memory window ↓</b></li>
          <li>그래서 BIL 두께는 sweet spot 존재 (1~3 nm 통상)</li>
        </ul>
        <h4>가정</h4>
        <ul>
          <li>Linear dielectric BIL — trap charge 미반영</li>
          <li>Bound charge가 sheet로 균일 분포</li>
          <li>Screening 효율 f_screen ∈ [0,1]로 metal-by-metal 균일</li>
        </ul>
        <h4>한계</h4>
        <ul>
          <li>Poisson-Schrödinger self-consistent 아님 (TCAD 아님)</li>
          <li>BIL 안 trap이 V_int를 동적으로 흔드는 효과 없음</li>
        </ul>
        <div class="warn"><b>compare mode 보는 법:</b> 양쪽 panel 모두 같은 Vapp 인가. 다른 건 분극 방향뿐. ON에서 BIL이 더 많이/덜 흡수하는지 보세요. 그것이 본인이 손으로 그렸던 그 trade-off의 시각적 증거입니다.</div>
      </div>
      <div class="canvasBox"><canvas id="band" height="500"></canvas></div></article>

    <article class="card wide" id="card2"><div class="cardHeadRow">
      <div class="cardTitleBlock"><h3>2) V(x) / E(x) / Charge(x) profile <small>MOS-style</small></h3>
        <div class="subQ">전압이 어디서 가장 많이 떨어지는가? BIL이 voltage divider로 얼마나 잡아먹는가?</div></div>
      <button class="whyBtn" data-why="why2">Why?</button></div>
      <div class="whyBox" id="why2">
        <h4>식 (capacitive divider)</h4>
        <div class="formula">$V_{HZO} = V_{app} \cdot \dfrac{C_{BIL}}{C_{BIL}+C_{HZO}}, \quad C_i = \dfrac{\varepsilon_0 \varepsilon_{r,i}}{t_i}$</div>
        <div class="formula">$E_{HZO} = V_{HZO}/t_{HZO} \quad [\mathrm{MV/cm}]$, bound charge $\sigma_P = \pm P_r$</div>
        <h4>가정</h4>
        <ul>
          <li>Linear dielectric — trap charge feedback 없음</li>
          <li>Interface charge는 sheet charge로만 처리</li>
        </ul>
        <h4>한계</h4>
        <ul>
          <li>분극 switching 중 transient field redistribution 미반영</li>
          <li>실측에서는 BIL 두께 1nm 차이로 voltage drop이 30% 이상 변할 수 있음</li>
        </ul>
        <div class="warn"><b>MFIS 핵심:</b> BIL이 1nm 늘어나면 HZO에 걸리는 전계가 줄어 switching이 약해진다. 이게 MFIS FTJ가 두께 조절에 민감한 이유. <b>Mo/TiN 비대칭</b>이면 +V와 −V에서 voltage drop도 달라짐.</div>
      </div>
      <div class="canvasBox"><canvas id="profile" height="540"></canvas></div></article>

    <article class="card wide" id="card3"><div class="cardHeadRow">
      <div class="cardTitleBlock"><h3>3) I–V with transport components <small>real units, decomposed</small></h3>
        <div class="subQ">총 전류 안에 어떤 메커니즘이 얼마나 섞여 있는가?</div></div>
      <button class="whyBtn" data-why="why3">Why?</button></div>
      <div class="whyBox" id="why3">
        <h4>6 transport mechanisms (additive)</h4>
        <div class="formula">Direct/WKB: $J_D \propto \exp(-2t\sqrt{2m^*\phi}/\hbar)$</div>
        <div class="formula">Fowler-Nordheim: $J_{FN} = \dfrac{q^2}{8\pi h \phi} E^2 \exp\!\left(-\dfrac{B \phi^{3/2}}{E}\right)$, $\;B=6.83\times10^7\sqrt{m^*}$ (in V/m, eV)</div>
        <div class="formula">Schottky: $J_S = A^* T^2 \exp\!\left(-\dfrac{\phi - \sqrt{qE/(4\pi\varepsilon)}}{kT}\right)$, $\;A^*=120\,T^2\,\mathrm{A\,cm^{-2}\,K^{-2}}$</div>
        <div class="formula">Poole-Frenkel: $J_{PF} = q\mu N_C E \exp\!\left(-\dfrac{\phi_t - \beta\sqrt{E}}{kT}\right)$, $\;\beta=\sqrt{q^3/\pi\varepsilon_0\varepsilon_r}$</div>
        <div class="formula">Ohmic: $J = \sigma E$ (저전계 trap-free)</div>
        <div class="formula">SCLC: $J \propto V^2/t^3$ (trap-filled limit 위)</div>
        <h4>가정</h4>
        <ul>
          <li>각 메커니즘이 독립적·additive — 실제는 coupled (예: PF로 trap이 채워진 후 F-N이 켜짐)</li>
          <li>Series resistance 미반영</li>
          <li>각 메커니즘의 prefactor 일부는 nominal 값</li>
        </ul>
        <h4>한계</h4>
        <ul>
          <li>Trap-Assisted Tunneling (TAT)은 이 도구에서 PF + Direct의 조합으로 근사. 본격 multi-trap TAT 모델 아님</li>
          <li>온도 의존성은 PF·Schottky에만 명시적 (Direct/F-N은 T=0K 근사)</li>
        </ul>
      </div>
      <div class="canvasBox"><canvas id="iv" height="470"></canvas></div></article>

    <article class="card wide" id="card3b"><div class="cardHeadRow">
      <div class="cardTitleBlock"><h3>3b) Polarity 4-grid <small>Mo/TiN asymmetric · ON±/OFF±</small></h3>
        <div class="subQ">+V와 −V에서 ON/OFF window가 같은가? 어느 쪽 polarity에서 어떤 메커니즘이 우세한가?</div></div>
      <button class="whyBtn" data-why="why3b">Why?</button></div>
      <div class="whyBox" id="why3b">
        <h4>왜 폴라리티 분리가 필수인가?</h4>
        <p>Mo (work function ~4.6 eV)와 TiN (~4.5 eV)이 다르므로 같은 HZO라도 +V 인가 (V<sub>TE</sub> &gt; V<sub>BE</sub>)와 −V 인가에서 injection barrier·built-in field·screening이 다릅니다. 또한 분극 방향(ON/OFF)도 +V일 때와 −V일 때 다른 barrier shift를 만듭니다.</p>
        <h4>4가지 조합</h4>
        <ul>
          <li><b>ON+ </b>: 분극 TE 방향, V<sub>TE</sub>&gt;V<sub>BE</sub> → 전자 BE → TE</li>
          <li><b>ON−</b>: 분극 TE 방향, V<sub>TE</sub>&lt;V<sub>BE</sub> → 전자 TE → BE</li>
          <li><b>OFF+</b>: 분극 BE 방향, V<sub>TE</sub>&gt;V<sub>BE</sub></li>
          <li><b>OFF−</b>: 분극 BE 방향, V<sub>TE</sub>&lt;V<sub>BE</sub></li>
        </ul>
        <div class="warn"><b>측정 규칙:</b> 4 조합을 절대 같이 fitting하지 마세요. 한 곡선으로 합치면 비대칭 정보가 평균화되어 사라집니다 ("평균 괴물"). 각각 따로 mechanism fit을 돌려야 set/reset asymmetry, imprint, electrode-limited vs bulk-limited 구분이 가능합니다.</div>
      </div>
      <div class="polGrid">
        <div class="polCell"><h5>+V bias (TE positive) <span class="tag">SET / Read+</span></h5>
          <canvas id="polPos" height="170"></canvas></div>
        <div class="polCell"><h5>−V bias (TE negative) <span class="tag neg">RESET / Read−</span></h5>
          <canvas id="polNeg" height="170"></canvas></div>
      </div>
      <div class="legendInline">
        <span><span class="dot" style="background:#dc2626"></span>ON state</span>
        <span><span class="dot" style="background:#2563eb"></span>OFF state</span>
        <span><span class="dot" style="background:#94a3b8"></span>imported CSV</span>
      </div>
      <div class="polNote" id="polNote"></div></article>

    <article class="card" id="card4"><div class="cardHeadRow">
      <div class="cardTitleBlock"><h3>4) Mechanism fit matrix <small>R² / score</small></h3>
        <div class="subQ">이 데이터가 정말 어떤 메커니즘인가? F-N 외에도 후보가 있지 않은가?</div></div>
      <button class="whyBtn" data-why="why4">Why?</button></div>
      <div class="whyBox" id="why4">
        <h4>각 메커니즘의 linearization</h4>
        <ul>
          <li>Ohmic: $\ln J$ vs $\ln V$, slope ≈ 1</li>
          <li>SCLC: $\ln J$ vs $\ln V$, slope ≈ 2</li>
          <li>Schottky: $\ln J$ vs $\sqrt{E}$ (electrode-limited)</li>
          <li>Poole-Frenkel: $\ln(J/E)$ vs $\sqrt{E}$ (bulk trap-limited)</li>
          <li>F-N: $\ln(J/E^2)$ vs $1/E$ (slope &lt; 0)</li>
          <li>Direct: $\ln J$ vs $V$ (저전계)</li>
        </ul>
        <h4>Score = R² × penalty</h4>
        <p>Penalty는 각 메커니즘 고유 sanity check (예: F-N은 negative slope만 인정, PF는 β값이 ε<sub>r</sub>과 일관되어야 함).</p>
        <div class="warn"><b>R² 트로피 사냥 함정:</b> 가장 R²가 높은 게 "진실"이 아닙니다. fit window를 좁게 잡으면 거의 모든 메커니즘이 R²&gt;0.95 만들 수 있어요. <b>온도 의존성·두께 scaling·polarity 분리</b>로 cross-check 필수. PF와 Schottky는 둘 다 √E 계열이라 단일 plot으로 구분 안 됩니다.</div>
      </div>
      <div class="canvasBox"><canvas id="fitBar" height="400"></canvas></div></article>

    <article class="card" id="card5"><div class="cardHeadRow">
      <div class="cardTitleBlock"><h3>5) F-N plot <small>ln(J/E²) vs 1/E, honest fit</small></h3>
        <div class="subQ">F-N 직선성이 정말 신뢰할 만한가? φ_eff는 진짜 barrier인가, 아니면 apparent value인가?</div></div>
      <button class="whyBtn" data-why="why5">Why?</button></div>
      <div class="whyBox" id="why5">
        <h4>WKB 도출 (Step-by-step) — DT와 F-N은 같은 식의 두 극한</h4>
        <p><b>Step 1.</b> 1D Schrödinger, 장벽 안 (U > E):</p>
        <div class="formula">$$\frac{d^2\psi}{dx^2} = \kappa^2(x)\psi, \quad \kappa(x)=\frac{\sqrt{2m^*(U(x)-E)}}{\hbar}$$</div>
        <p><b>Step 2.</b> WKB — 장벽을 얇게 잘라 감쇠 누적:</p>
        <div class="formula">$$T \approx \exp\!\left[-\frac{2}{\hbar}\int_{x_1}^{x_2}\sqrt{2m^*(U(x)-E)}\,dx\right]$$</div>
        <p><b>Step 3 (Case A).</b> Trapezoidal barrier (qV &lt; φ_b): 평균 barrier로 단순화 → DT</p>
        <div class="formula">$$\boxed{\;D_{DT} \approx \exp\!\left[-\frac{2d}{\hbar}\sqrt{2m^*\bar\phi}\,\right]\;}$$</div>
        <p><b>Step 4 (Case B).</b> Triangular barrier (qV &gt; φ_b): turning point $x_2 = \phi_b/q\mathcal{E}$</p>
        <div class="formula">$$\alpha\!\int_0^{\phi_b/q\mathcal{E}}\!\!\sqrt{\phi_b - q\mathcal{E}x}\,dx = \frac{2\alpha\,\phi_b^{3/2}}{3q\mathcal{E}}$$</div>
        <div class="formula">$$\boxed{\;J_{FN} = A\mathcal{E}^2\exp\!\left(-\dfrac{B\phi_b^{3/2}}{\mathcal{E}}\right)\;}, \quad B=\dfrac{4\sqrt{2m^*q}}{3\hbar} \approx 6.83\!\times\!10^7\sqrt{m^*/m_0}\;[\mathrm{V/cm}]$$</div>
        <h4>F-N plot: 왜 ln(J/V²) vs 1/V?</h4>
        <div class="formula">$$\ln\!\frac{J}{\mathcal{E}^2} = \ln A - \dfrac{B\phi_b^{3/2}}{\mathcal{E}} \;\Rightarrow\; \text{slope}=-B\phi_b^{3/2} \;\Rightarrow\; \phi_b = \left(\dfrac{|\text{slope}|}{B}\right)^{2/3}$$</div>
        <h4>R² verdict (이 도구의 안전장치)</h4>
        <ul>
          <li>R² &gt; 0.97 → <b>credible</b> (그래도 apparent value)</li>
          <li>R² &gt; 0.90 → <b>marginal</b> — PF/Schottky 후보 같이 봐야 함</li>
          <li>R² &lt; 0.90 → <b>unreliable</b> — F-N 단독 해석 금지</li>
        </ul>
        <h4>두 식 비교 (한 줄 통찰)</h4>
        <ul>
          <li>지수항에 t는 DT만 직접 포함 → DT는 두께에 미친 듯이 민감</li>
          <li>지수항에 φ는 DT는 √φ, F-N은 φ^(3/2) → F-N이 분극 Δφ_P에 훨씬 강한 modulation</li>
          <li>같은 분극이 read regime에선 DT 변조 → TER, write regime에선 F-N 변조 → switching</li>
        </ul>
        <div class="warn"><b>핵심 함정 — Multi-solution:</b> 같은 I-V 곡선이 (m*↑, φ↓)와 (m*↓, φ↑)로 모두 fit 가능. φ만 고정하면 안 되고 두께·면적·온도 다른 측정에서 일관된 (m*, φ) 조합 찾아야 진짜. 그래서 추출된 φ는 항상 <span class="apparent">apparent</span> 표시.</div>
        <div class="warn"><b>또 하나:</b> FTJ에서 φ_eff는 분극 state·polarity·thickness·field partition·trap mixture에 따라 달라지는 apparent value. "그 bias range, 그 state, 그 stack에서의 유효값"으로만 보고하세요.</div>
      </div>
      <div class="canvasBox"><canvas id="fnPlot" height="400"></canvas></div></article>

    <article class="card" id="card6"><div class="cardHeadRow">
      <div class="cardTitleBlock"><h3>6) Multi-Read overlay <small>Joshua scan</small></h3>
        <div class="subQ">어느 read voltage가 window 크고, disturb 작고, BER 낮은 sweet spot인가?</div></div>
      <button class="whyBtn" data-why="why6">Why?</button></div>
      <div class="whyBox" id="why6">
        <h4>식</h4>
        <div class="formula">window $= I_{ON}/I_{OFF}$ at $V_{read}$</div>
        <div class="formula">separation $\sigma_s = (I_{ON}-I_{OFF})/\sigma_{noise}$</div>
        <div class="formula">BER $= \dfrac{1}{2}\,\mathrm{erfc}\!\left(\dfrac{\sigma_s}{\sqrt{2}}\right)$ (Gaussian noise 가정)</div>
        <div class="formula">disturb index $\propto \int_0^{t_{read}} (V_{read}/V_c)^n \cdot \mathrm{cycles} \;dt$</div>
        <h4>가정</h4>
        <ul>
          <li>Gaussian read noise — 실제는 1/f flicker noise, RTN 섞임</li>
          <li>One-shot read — averaging으로 BER은 줄일 수 있음</li>
        </ul>
        <h4>한계</h4>
        <ul>
          <li>Read disturb 모델은 phenomenological (실제는 partial switching + trap fill의 복합)</li>
        </ul>
        <div class="warn"><b>실험 팁:</b> Best read voltage가 V<sub>c</sub>의 30-50% 범위면 안전. V<sub>c</sub>에 가까우면 read 자체가 state를 흔듭니다 (read disturb).</div>
      </div>
      <div class="canvasBox"><canvas id="multiRead" height="430"></canvas></div></article>

    <article class="card" id="card7"><div class="cardHeadRow">
      <div class="cardTitleBlock"><h3>7) Transport regime map <small>log|J|–|V|</small></h3>
        <div class="subQ">전압 구간마다 어떤 메커니즘이 dominant인가? Crossover는 어디서?</div></div>
      <button class="whyBtn" data-why="why7">Why?</button></div>
      <div class="whyBox" id="why7">
        <h4>구분</h4>
        <ul>
          <li>저전계 (V &lt; ~Vc/3): Ohmic, PF (trap-dominated)</li>
          <li>중전계 (~Vc/3 ~ ~Vc): Direct tunneling, Schottky</li>
          <li>고전계 (V &gt; ~Vc): Fowler-Nordheim</li>
        </ul>
        <h4>가정</h4>
        <ul>
          <li>각 메커니즘 독립적·additive</li>
          <li>Crossover voltage는 디바이스마다 다름 (이 도구는 nominal stack 기준)</li>
        </ul>
        <div class="warn"><b>판독 팁:</b> Total과 component를 비교해서 regime 경계가 본인 슬라이더 설정과 맞는지 보세요. low-field tail이 올라가면 leakage·soft breakdown 의심.</div>
      </div>
      <div class="canvasBox"><canvas id="regime" height="430"></canvas></div></article>

    <article class="card wide" id="card8"><div class="cardHeadRow">
      <div class="cardTitleBlock"><h3>8) PUND + Transient I–V <small>switching evidence, two views</small></h3>
        <div class="subQ">Switchable polarization이 진짜 있는가? 같은 펄스 시퀀스를 시간축과 V축 두 가지로 본다.</div></div>
      <button class="whyBtn" data-why="why8">Why?</button></div>
      <div class="whyBox" id="why8">
        <h4>두 view의 차이 (왜 둘 다 봐야 하나)</h4>
        <ul>
          <li><b>PUND time-domain (좌):</b> 시간축으로 P/U/N/D 4 펄스 input과 그 transient current response. P/N에선 switching peak (큰 transient), U/D에선 capacitive + leak baseline만. 차이 = Q<sub>sw</sub></li>
          <li><b>Transient I-V (우):</b> 같은 sweep을 V축으로 다시 그림. Ferroelectric switching이 +V/−V 양쪽에서 sharp current peak로 보이며, 사이가 hysteresis loop. 본인이 측정해본 그 형태.</li>
        </ul>
        <h4>PUND 식</h4>
        <div class="formula">$$Q_P = \int I_P\,dt \;\;\text{(switching + leak + cap)}$$</div>
        <div class="formula">$$Q_U = \int I_U\,dt \;\;\text{(leak + cap only — 두 번째 same-direction)}$$</div>
        <div class="formula">$$\boxed{\;Q_{sw} = (Q_P - Q_U) - (Q_N - Q_D)\;}$$</div>
        <h4>가정·한계</h4>
        <ul>
          <li>Pulse가 충분히 길어 switching 완료 — 짧으면 partial switching</li>
          <li>Linear leakage (실제는 highly non-linear)</li>
          <li>고주파 (&lt; μs) PUND에서는 RC delay가 P-V loop 왜곡</li>
          <li>Q<sub>leak</sub> &gt; 0.3·Q<sub>sw</sub>면 진짜 P<sub>r</sub> 추출 어려움</li>
        </ul>
        <div class="warn"><b>중요 분리:</b> PUND가 좋아도 TER가 작을 수 있고, TER가 커도 PUND가 빈약할 수 있음. PUND = switching charge, TER = readout transport. 다른 물리량.</div>
        <div class="warn"><b>실측 비교 팁:</b> 본인이 본 transient I-V (V vs I)에서 +V 쪽 큰 peak와 −V 쪽 음의 peak가 보이면 ferroelectric switching의 직접 증거. peak 면적 = Q<sub>sw</sub>.</div>
      </div>
      <div class="polGrid">
        <div class="polCell"><h5>PUND time-domain <span class="tag">P/U/N/D</span></h5>
          <canvas id="pund" height="220"></canvas></div>
        <div class="polCell"><h5>Transient I–V (hysteresis) <span class="tag">V vs I</span></h5>
          <canvas id="pundIV" height="220"></canvas></div>
      </div>
      <div class="polNote" id="pundNote"></div></article>

    <article class="card wide" id="card9"><div class="cardHeadRow">
      <div class="cardTitleBlock"><h3>9) Reliability budget <small>retention · fatigue · read-disturb</small></h3>
        <div class="subQ">이 디바이스가 10년 (~3×10⁸ s) retention과 10⁵+ cycle endurance를 만족할까?</div></div>
      <button class="whyBtn" data-why="why9">Why?</button></div>
      <div class="whyBox" id="why9">
        <h4>모델</h4>
        <div class="formula">Retention (KWW): $P(t)/P_0 = \exp\!\left(-(t/\tau)^\beta\right)$, $0 < \beta \le 1$</div>
        <div class="formula">Fatigue (Weibull): $P_r(N) = P_{r,0} \cdot (1 - (N/N_{50\%})^\alpha)$</div>
        <div class="formula">Read-disturb (cumulative): $\Delta P \propto \int_0^t (V_r/V_c)^n \,dt$</div>
        <h4>가정</h4>
        <ul>
          <li>Phenomenological — domain nucleation/growth (NLS, KAI 모델) 미반영</li>
          <li>τ, β, α는 슬라이더 nominal 값 (실측 calibration 필요)</li>
        </ul>
        <h4>한계 (heuristic)</h4>
        <ul>
          <li>이 패널은 "지도"이지 "증거"가 아닙니다. 실측 retention/endurance 데이터로 calibration 필수</li>
          <li>HZO retention loss는 oxygen vacancy accumulation, internal bias, domain structure 모두 영향</li>
          <li>Wake-up은 모델링 안 됨 (별도 측정 필요)</li>
        </ul>
        <div class="warn"><b>실험 팁:</b> Retention 측정은 log-spaced delay (10ms, 100ms, 1s, 10s, 100s) 필수. Fatigue도 decade 단위 (10², 10³, 10⁴, ...).</div>
      </div>
      <div class="canvasBox"><canvas id="reliability" height="430"></canvas></div></article>

    <article class="card wide" id="card10"><div class="cardHeadRow">
      <div class="cardTitleBlock"><h3>10) 32-state LTP / LTD <small>seeded noise · BER</small></h3>
        <div class="subQ">Multi-bit/analog memory로 쓸 때 몇 개 level까지 안정적으로 구분되는가?</div></div>
      <button class="whyBtn" data-why="why10">Why?</button></div>
      <div class="whyBox" id="why10">
        <h4>식</h4>
        <div class="formula">$G_n = G_{min} + n \cdot \Delta G + \mathcal{N}(0, \sigma) \cdot \mathrm{seed}(n)$</div>
        <div class="formula">usable states $= \lfloor \Delta G_{total}/(k\sigma) \rfloor$, $k$ = separation factor</div>
        <h4>가정</h4>
        <ul>
          <li>Identical pulse shape — 실제는 LTP/LTD 비대칭 + nonlinearity</li>
          <li>Noise = seeded (deterministic) — Math.random 미사용 → 슬라이더 만져도 흔들리지 않음</li>
        </ul>
        <h4>한계</h4>
        <ul>
          <li>Domain nucleation kinetics 미반영 — 실제 HZO의 LTP/LTD는 nucleation-limited switching이라 step size가 V·t에 비선형으로 의존</li>
          <li>Drift·decay 미반영 (각 level이 시간 지나면서 이동)</li>
        </ul>
        <div class="warn"><b>학습 팁:</b> 이 패널은 ideal한 "낙관적 상한". 실측에서는 보통 추정치의 50-70% 정도가 진짜 usable.</div>
      </div>
      <div class="canvasBox"><canvas id="states" height="450"></canvas></div></article>

    <article class="card wide" id="card11"><div class="cardHeadRow">
      <div class="cardTitleBlock"><h3>11) Read-out summary &amp; lab notes <small>actionable</small></h3>
        <div class="subQ">현재 condition에서 측정 직전·직후 무엇을 체크해야 하는가?</div></div>
      <button class="whyBtn" data-why="why11">Why?</button></div>
      <div class="whyBox" id="why11">
        <h4>해석 방식</h4>
        <p>각 pill의 색은 슬라이더 nominal 값 + 추출된 fit 결과 기반 heuristic. <b>green = 무난, orange = 주의, red = 적신호</b>. 실측 calibration 전에는 hypothesis generator로만 사용하세요.</p>
        <h4>워크플로우</h4>
        <ul>
          <li>측정 <b>직전</b>: 이 패널의 권고 read V·pulse 조건을 세팅에 반영</li>
          <li>측정 <b>직후</b>: imported CSV의 fit table을 보고 어디가 model과 어긋나는지 확인 → 그 항목이 "현재 알아야 할 물리"</li>
        </ul>
        <div class="warn"><b>경고:</b> 이 패널의 numeric value를 보고/논문에 그대로 인용하지 마세요. synthetic + heuristic 결과입니다. 실측 fit 결과만 인용하세요.</div>
      </div>
      <div class="panelText" id="fitTable"></div>
      <div class="hr"></div>
      <div class="panelText" id="notes"></div></article>
  </section>
  <div class="footer">
    <span>v13 = v12 + MFS semiconductor electrode (InGaAs/Si/Ge:p++): polarity-dependent depletion/accumulation series capacitance, Thomas–Fermi screening length, depolarization-field boost, write-voltage penalty, and depletion band-bending + V/E/charge tail in panels 1–2. v12 canvas runaway fix retained. Quantitative-assist model.</span>
    <span id="stamp">ready</span>
  </div>
</main>
</div>

<script>
"use strict";
// ============================================================
//  PHYSICAL CONSTANTS  (SI unless noted)
// ============================================================
const Q = 1.602176634e-19;            // C
const EPS0 = 8.8541878128e-12;        // F/m
const KB = 1.380649e-23;              // J/K
const KB_EV = 8.617333262e-5;         // eV/K

// Electrode work functions (eV) - lambda is mean-free-path proxy (unused but kept)
// sc:true entries are DEGENERATE SEMICONDUCTORS (MFS electrode):
//   type "p"/"n", epsS = static εr, Eg [eV], chi = electron affinity [eV].
//   Φ(degenerate p) ≈ chi + Eg (E_F pinned at/below E_V).
const MAT = {
  Mo:{wf:4.60}, TiN:{wf:4.70}, Au:{wf:5.10}, Co:{wf:5.00}, Pt:{wf:5.60},
  Al:{wf:4.20}, Ru:{wf:4.71}, W:{wf:4.55}, LSMO:{wf:4.80},
  // ---- degenerate p-type semiconductor electrodes (MFS) ----
  "InGaAs:p++":{wf:5.24, sc:true, type:"p", epsS:13.9, Eg:0.74, chi:4.50},
  "Si:p++":{wf:5.17, sc:true, type:"p", epsS:11.7, Eg:1.12, chi:4.05},
  "Ge:p++":{wf:4.66, sc:true, type:"p", epsS:16.0, Eg:0.66, chi:4.00}
};

// ============================================================
//  STATE
// ============================================================
let S = {
  // Stack
  te:"Mo", be:"TiN", area:100, temp:300, mode:"compare",
  hzoT:5.5, bilT:1.0, hzoPhi:1.85, bilPhi:2.55,
  hzoEg:5.7, bilEg:4.6,
  epsHzo:28, epsBil:14, mEff:0.32,
  // FE / defect
  Pr:24, screen:0.72, ifc:0.62, ovac:0.55, depol:0.38, trap:0.28, leak:0.12,
  // Measurement
  Rs:250, Vapp:0.3, Vmax:2.5, readV:0.30,
  pulseV:2.2, resetV:-2.2, pulseW:1.0, setV:2.4,
  // Multi-read
  rA:0.30, rB:0.40, rC:0.50, rD:0.60,
  // Multilevel & noise
  nStates:32, noisePct:2.0,
  // Reliability targets
  retentionGoal:1e4, enduranceN:1e5,
  // ---- MFS semiconductor electrode (v13) ----
  NaLog:20.0,      // log10(acceptor doping, cm^-3) → 1e20
  tDead:0.4,       // interfacial dead layer thickness (nm)
  epsDead:8,       // dead-layer εr (low-κ interfacial oxide)
  preset:"user"
};

let DATA = [];
let lastReport = {};
const E = {};
const $ = id => document.getElementById(id);
[
  "te","be","area","temp","mode","stackSliders","defectSliders","measSliders","vappSlider","readMultiSliders","mfsSliders",
  "csvIn","dataUnit","dataStatus","sampleBtn","parseBtn","clearBtn",
  "exportConfig","exportCsv","importConfig","copySummary","autoRead",
  "band","profile","iv","fitBar","fnPlot","multiRead","regime","pund","pundIV","pundNote","reliability","states",
  "polPos","polNeg","polNote",
  "fitTable","notes","stamp",
  "kVapp","kVappS","kRatio","kRatioS","kBestRead","kBestReadS","kMech","kMechS",
  "kPhi","kPhiS","kQsw","kQswS","kStates","kStatesS","kRisk","kRiskS",
  "pUser","pMfm","pMfis","pLeak","pMfs"
].forEach(id => E[id] = $(id));

// ============================================================
//  SLIDER DEFS
// ============================================================
const vappDef = [
  ["Vapp","Live applied voltage Vapp (V)",-4,4,0.05,2]
];
const stackDefs = [
  ["hzoT","HZO thickness (nm)",2,12,0.1,1],
  ["bilT","BIL thickness (nm)",0,3,0.05,2],
  ["hzoPhi","HZO barrier ΦB (eV)",0.6,3.5,0.05,2],
  ["bilPhi","BIL barrier ΦB (eV)",0.8,4.2,0.05,2],
  ["hzoEg","HZO bandgap (eV)",4.8,6.4,0.05,2],
  ["bilEg","BIL bandgap (eV)",3.0,6.0,0.05,2],
  ["epsHzo","HZO εr",8,55,1,0],
  ["epsBil","BIL εr",3,45,1,0],
  ["mEff","Tunneling m*/m0",0.08,1.2,0.01,2]
];
const defectDefs = [
  ["Pr","Polarization Pr (µC/cm²)",3,45,0.5,1],
  ["screen","Screening efficiency",0.10,1.0,0.01,2],
  ["ifc","Interface charge index",0,1.4,0.01,2],
  ["ovac","O-vacancy index",0,1.4,0.01,2],
  ["depol","Depolarization index",0,1.3,0.01,2],
  ["trap","Trap / PF activity",0,1.3,0.01,2],
  ["leak","Soft-BD leakage index",0,1.3,0.01,2]
];
const measDefs = [
  ["Vmax","I–V Vmax (V)",0.5,5,0.05,2],
  ["readV","Read voltage (V)",0.03,1.0,0.01,2],
  ["pulseV","SET / PUND amplitude (V)",0.5,5,0.05,2],
  ["resetV","RESET amplitude (V)",-5,-0.5,0.05,2],
  ["setV","SET pulse V (V)",0.5,5,0.05,2],
  ["pulseW","Pulse width (µs)",0.05,50,0.05,2],
  ["noisePct","Read noise σ (%)",0.1,20,0.1,1],
  ["Rs","Series R (Ω)",0,5000,10,0],
  ["retentionGoal","Retention target (s)",1,1e6,1,0],
  ["enduranceN","Endurance cycles",10,1e7,10,0]
];
const readMultiDefs = [
  ["rA","Read V #1 (V)",0.03,1.0,0.01,2],
  ["rB","Read V #2 (V)",0.03,1.0,0.01,2],
  ["rC","Read V #3 (V)",0.03,1.0,0.01,2],
  ["rD","Read V #4 (V)",0.03,1.0,0.01,2],
  ["nStates","Target states (LTP/LTD)",4,64,1,0]
];
const mfsDefs = [
  ["NaLog","SC doping log₁₀(N_A / cm⁻³)",18,20.7,0.05,2],
  ["tDead","Interfacial dead layer t (nm)",0,1.0,0.05,2],
  ["epsDead","Dead layer εr",3,25,0.5,1]
];

// ============================================================
//  UI: sliders
// ============================================================
function makeSliders(defs, parent){
  defs.forEach(d => {
    const [id,lab,min,max,step,dig] = d;
    const wrap = document.createElement("div");
    wrap.className = "slider";
    wrap.innerHTML =
      `<div class="sliderHead"><label>${lab}</label><div class="val" id="${id}Val"></div></div>`+
      `<input id="${id}" type="range" min="${min}" max="${max}" step="${step}" value="${S[id]}">`;
    parent.appendChild(wrap);
    E[id] = wrap.querySelector("input");
    E[id+"Val"] = wrap.querySelector(".val");
    E[id].addEventListener("input", ev => {
      S[id] = Number(ev.target.value);
      updateVal(id);
      render();
    });
    updateVal(id);
  });
}
function findDef(id){
  return [...vappDef,...stackDefs,...defectDefs,...measDefs,...readMultiDefs,...mfsDefs].find(d => d[0]===id);
}
function updateVal(id){
  if(!E[id+"Val"]) return;
  const def = findDef(id);
  const dig = def ? def[5] : 2;
  const v = Number(S[id]);
  let text;
  if(id==="retentionGoal"||id==="enduranceN") text = sci(v);
  else if(id==="NaLog") text = sci(Math.pow(10,v))+" cm⁻³";
  else if(id==="nStates") text = String(Math.round(v));
  else if(dig===0) text = String(Math.round(v));
  else text = v.toFixed(dig);
  E[id+"Val"].textContent = text;
}
function syncAll(){
  E.te.value = S.te; E.be.value = S.be;
  E.area.value = S.area; E.temp.value = S.temp;
  E.mode.value = S.mode;
  [...vappDef,...stackDefs,...defectDefs,...measDefs,...readMultiDefs,...mfsDefs].forEach(d => {
    const id = d[0];
    if(E[id]){ E[id].value = S[id]; updateVal(id); }
  });
}
function syncOne(id){
  if(E[id]){ E[id].value = S[id]; updateVal(id); }
}

// ============================================================
//  UTILITIES
// ============================================================
function cl(x,a,b){ return Math.min(b,Math.max(a,x)); }
function fmt(x,d=2){ return Number(x).toFixed(d); }
function sci(x){
  const a = Math.abs(x);
  if(a===0) return "0";
  if(a>=1e4 || a<1e-2) return Number(x).toExponential(1);
  return Number(x).toFixed(a>=100?0:a>=10?1:2);
}
function sigmoid(x){ return 1/(1+Math.exp(-x)); }
function safeLog(x){ return Math.log(Math.max(x,1e-300)); }
function safeLog10(x){ return Math.log10(Math.max(x,1e-300)); }
function tauFmt(t){
  if(!Number.isFinite(t)) return "—";
  if(t<60) return t.toFixed(1)+" s";
  if(t<3600) return (t/60).toFixed(1)+" min";
  if(t<86400) return (t/3600).toFixed(1)+" h";
  if(t<86400*365) return (t/86400).toFixed(1)+" d";
  return (t/(86400*365)).toFixed(1)+" yr";
}
// erf / erfc — Abramowitz & Stegun 7.1.26
function erf(x){
  const sign = x<0 ? -1 : 1;
  x = Math.abs(x);
  const a1=0.254829592, a2=-0.284496736, a3=1.421413741, a4=-1.453152027, a5=1.061405429, p=0.3275911;
  const t = 1/(1+p*x);
  const y = 1 - (((((a5*t+a4)*t)+a3)*t+a2)*t+a1)*t*Math.exp(-x*x);
  return sign*y;
}
function erfc(x){ return 1 - erf(x); }

// Deterministic seeded noise — depends on index AND key state vars,
// so it stays stable when sliders that don't affect the channel are moved.
function seedNoise(i, salt=0){
  const x = Math.sin((i+1)*12.9898 + S.hzoT*78.233 + S.Pr*31.7 + S.bilT*17.13 + salt*7.91)*43758.5453;
  return (x - Math.floor(x))*2 - 1;   // in [-1, +1]
}

// ============================================================
//  v13: MFS (Metal–Ferroelectric–Semiconductor) physics module
//  Bottom (or top) electrode is a DEGENERATE semiconductor, not a metal.
//  Three effects absent in MFM / MFIM:
//   1. Bias-polarity-dependent series capacitance (depletion vs accumulation)
//      → the voltage-divider ratio FLIPS with sign(V_app + P-bias).
//   2. Finite screening length λ_TF ~0.4–1 nm (metal ≈0.05 nm) → a "dead"
//      series capacitance survives even in accumulation, and bound charge
//      is screened over a longer distance → stronger depolarization field.
//   3. Both of the above force a larger write V_app to reach the coercive
//      field than an MFM cap of identical HZO thickness.
// ============================================================
function scProps(name){
  const e = MAT[name];
  return (e && e.sc) ? e : null;
}
// which side carries the semiconductor (physical device: BE). null if none.
function scSide(){
  if(scProps(S.be)) return "be";
  if(scProps(S.te)) return "te";
  return null;
}
function isMFS(){ return scSide() !== null; }

// Debye / Thomas–Fermi screening length [nm] for carrier density n [cm⁻³].
function debyeLenNm(epsS, n_cm3, T){
  const n = Math.max(n_cm3, 1e10) * 1e6;                 // m⁻³
  const LD = Math.sqrt(EPS0*epsS*KB*T / (Q*Q*n));        // m
  return LD * 1e9;                                       // nm
}
// Depletion width [nm] for surface band-bending ψ_s [V], doping N_A [cm⁻³].
//   W = sqrt(2 ε0 εs ψ_s / (q N_A))
function depletionWnm(psi_s, epsS, Na_cm3){
  const Na = Math.max(Na_cm3, 1e14) * 1e6;              // m⁻³
  const W = Math.sqrt(2*EPS0*epsS*Math.max(psi_s,0) / (Q*Na)); // m
  return W * 1e9;                                        // nm
}

// ============================================================
//  CORE MODEL (geometry, capacitance, polarization, Vc)
// ============================================================
function model(){
  const wfT = MAT[S.te].wf, wfB = MAT[S.be].wf, wd = wfB - wfT;
  const tTot = S.hzoT + S.bilT;                    // nm
  const areaCm2 = S.area * 1e-8;                   // µm² -> cm²
  // Capacitive voltage division: thicker / lower-εr layer drops more V
  // C_i = ε0·εr,i / t_i  →  V drop ∝ (t/εr)
  const sBil = S.bilT/Math.max(S.epsBil,1e-3);
  const sHzo = S.hzoT/Math.max(S.epsHzo,1e-3);
  const VbilFrac = S.bilT>0 ? sBil/(sHzo + sBil) : 0;
  const VhzoFrac = 1 - VbilFrac;
  // Depolarization field (toy index, MV/cm range)
  const Edep = cl(0.22*(S.Pr/30)*(1-S.screen)*(1+S.bilT*0.45)*(0.45+S.depol), 0, 2.2);
  // Average barrier (eV) - thickness-weighted, with WF-asymmetry & defect tweaks
  let phiBase = (S.hzoPhi*S.hzoT + S.bilPhi*S.bilT) / Math.max(tTot,1e-3);
  phiBase += 0.08*wd + 0.05*S.depol - 0.05*S.ifc;
  // Polarization-induced barrier shift Δφ(P)
  const dphi = cl(0.10 + 0.32*(S.Pr/30)*S.screen + 0.12*S.ifc - 0.07*S.depol, 0.03, 0.85);

  // ===== v10: Polarization-induced internal voltage across BIL =====
  // Bound charge σ_P at HZO surface ≈ P_r [μC/cm²].  After (1−f_screen)
  // imperfect screening, residual charge sits at the HZO/BIL interface
  // and drops voltage across the BIL: V_int = σ_residual · t_BIL / (ε0·εr_BIL)
  // = (P_r · (1−f_screen)) · t_BIL / (ε0·εr_BIL).  Sign flips with polarization.
  // Convert: P [μC/cm²] = 1e-2 C/m² ;  t [nm] = 1e-9 m
  const P_SI = (S.Pr*1e-2);                                    // C/m²
  const tBil_SI = S.bilT*1e-9;                                 // m
  const Vint_BIL = (P_SI*(1-S.screen)*tBil_SI) /
                   (EPS0*Math.max(S.epsBil,1e-3));             // V (positive magnitude)
  // For ON state (state=+1), polarization aids the externally-applied
  // direction; the same external Vapp causes BIL to absorb MORE.
  // For OFF, BIL absorbs LESS.  We expose this as an additive ±term.
  // (Capped to keep visual sane.)
  const Vint = cl(Vint_BIL, -3, 3);

  // Trap level for PF
  const trapE = cl(0.55 + 0.7*S.hzoPhi - 0.32*S.ovac - 0.25*S.trap, 0.08, 2.4);

  // ===== v13: MFS semiconductor electrode =====
  const side = scSide();
  const scMat = side ? MAT[side==="be" ? S.be : S.te] : null;
  const Na = Math.pow(10, S.NaLog);                 // cm⁻³
  let lambdaTF = 0, depolBoost = 0, scPolDrive = 0, scBuiltIn = 0;
  if(scMat){
    // Screening length of the degenerate SC (floor ~0.25 nm).  Metals would
    // be ~0.05 nm; this finite λ is the physical origin of incomplete screening.
    lambdaTF = cl(debyeLenNm(scMat.epsS, Na, S.temp), 0.25, 3.0);
    // Extra depolarization because the bound charge is screened over λ_TF
    // (plus the dead layer) instead of a metal's sub-Å.  Scales with (1−f).
    depolBoost = (1 - S.screen) * (S.Pr/30) * (0.18 + 0.10*(lambdaTF/0.4) + 0.20*S.tDead);
    // Polarization-induced surface drive on the SC (sets depletion/accum).
    scPolDrive = cl(0.45*(S.Pr/24)*(1 - S.screen) + 0.10, 0, 1.3);   // V
    // Built-in asymmetry from SC work function vs the metal electrode (eV).
    scBuiltIn = (side==="be") ? (scMat.wf - wfT) : (scMat.wf - wfB);
  }
  const EdepM = cl(Edep + depolBoost, 0, 3.2);

  // Coercive voltage proxy (V).  For MFS, depletion eats part of V_app and the
  // depolarization is stronger → a real WRITE-VOLTAGE PENALTY vs an MFM cap.
  let Vc = 0.65 + 0.11*S.hzoT + 0.25*S.bilT + 0.45*EdepM - 0.10*S.ovac + 0.05*Math.abs(wd);
  let writePenalty = 1;
  if(scMat){
    // representative depletion drop fraction at the write amplitude
    const wRep = depletionWnm(0.5*scPolDrive + 0.2*Math.abs(S.pulseV)*0.15, scMat.epsS, Na);
    const sHzoR = S.hzoT/Math.max(S.epsHzo,1e-3);
    const sBilR = S.bilT>0 ? S.bilT/Math.max(S.epsBil,1e-3) : 0;
    const sDeadR = S.tDead/Math.max(S.epsDead,1e-3);
    const sScR  = wRep/Math.max(scMat.epsS,1e-3);
    const fracLost = (sBilR + sDeadR + sScR) / (sHzoR + sBilR + sDeadR + sScR);
    writePenalty = 1 / Math.max(0.25, 1 - fracLost);   // >1: need higher Vapp
    Vc = Vc * writePenalty + 0.20*depolBoost*10;
  }
  Vc = cl(Vc, 0.35, 6.0);

  // Risk index
  const risk = cl(0.35*S.leak + 0.22*S.ovac + 0.22*S.trap + 0.18*S.depol +
                  0.12*Math.max(0,S.pulseV-Vc) +
                  (scMat ? 0.18 + 0.20*S.ovac : 0), 0, 2.0);   // SC interface Dit risk
  return {
    wfT, wfB, wd, tTot, areaCm2, VbilFrac, VhzoFrac,
    Edep:EdepM, phiBase, dphi, trapE, Vc, risk,
    Vint,                       // v10: polarization-induced BIL voltage (magnitude)
    epsEff: cl((S.epsHzo*S.hzoT + S.epsBil*S.bilT)/Math.max(tTot,1e-3), 3, 80),
    // ---- v13 MFS ----
    mfs: !!scMat, scMat, scSide: side, Na, lambdaTF,
    depolBoost, scPolDrive, scBuiltIn, writePenalty,
    tDead: S.tDead, epsDead: S.epsDead
  };
}

// v13: solve the semiconductor series element (depletion vs accumulation) by a
// short fixed-point iteration, returning the SC voltage drop & depletion width.
function semiSolve(Vapp, state, m){
  const sc = m.scMat;
  const epsS = sc.epsS;
  const lam = m.lambdaTF;                 // accumulation/dead floor [nm]
  const sHzo = S.hzoT/Math.max(S.epsHzo,1e-3);
  const sBil = S.bilT>0 ? S.bilT/Math.max(S.epsBil,1e-3) : 0;
  const sDead = m.tDead/Math.max(m.epsDead,1e-3);
  const polBias = state * m.scPolDrive;   // P-induced surface drive [V]
  let W = lam, Vsc = 0, Vhzo = 0, Vbil = 0, Vdead = 0, regime = "accumulation";
  for(let it=0; it<5; it++){
    const sSc = W/Math.max(epsS,1e-3);
    const sTot = sHzo + sBil + sDead + sSc;
    Vhzo  = Vapp * sHzo/sTot;
    Vbil  = Vapp * sBil/sTot;
    Vdead = Vapp * sDead/sTot;
    Vsc   = Vapp * sSc/sTot;
    const drive = Vsc + polBias;          // surface band-bending driver
    if(drive > 0){                        // p-type: holes pushed away → deplete
      W = cl(depletionWnm(Math.abs(drive), epsS, m.Na), lam, 12);
      regime = "depletion";
    } else {                              // accumulation: thin, metal-like
      W = lam;
      regime = "accumulation";
    }
  }
  return {Vhzo, Vbil, Vdead, Vsc, W, regime};
}

// v10 helper: state-dependent voltage split.  Returns {Vbil, Vhzo} (+MFS extras).
function voltageSplit(Vapp, state, m){
  if(!m) m = model();
  // ===== v13: MFS — semiconductor depletion eats part of V_app =====
  if(m.mfs){
    const s = semiSolve(Vapp, state, m);
    // Polarization redistribution between HZO and the rest (as in MFIM).
    const Vhzo = s.Vhzo - state*m.Vint*0.5;
    const Vbil = s.Vbil + state*m.Vint*0.5;
    return {Vbil, Vhzo, Vdead:s.Vdead, Vsc:s.Vsc, W:s.W, regime:s.regime};
  }
  // External capacitive division (legacy MFM / MFIM)
  const Vbil_ext = Vapp * m.VbilFrac;
  const Vhzo_ext = Vapp * m.VhzoFrac;
  // Polarization-induced internal voltage (state-dependent sign)
  // ON (+1) => BIL absorbs more, HZO absorbs less of the *effective* drop
  const Vbil = Vbil_ext + state*m.Vint;
  const Vhzo = Vhzo_ext - state*m.Vint;
  return {Vbil, Vhzo, Vdead:0, Vsc:0, W:0, regime:null};
}

// Image-force / Schottky-PF barrier lowering (eV)
function barrierLowering(EVm, epsr, kind){
  const denom = (kind==="pf" ? Math.PI : 4*Math.PI) * EPS0 * epsr;
  return Math.sqrt(Math.max(0, Q*EVm/denom));
}

// ============================================================
//  TRANSPORT COMPONENTS at given V (real units)
//   Returns J [A/cm²], I [A], and decomposed pieces.
// ============================================================
function componentsNoRs(V, state, m){
  const sign = V<0 ? -1 : 1;
  const aV = Math.abs(V) + 1e-9;
  const tNm = Math.max(0.3, m.tTot);
  const Ecm = aV / (tNm*1e-7);          // V/cm
  const EVm = aV / (tNm*1e-9);          // V/m
  const T = S.temp;
  const kT = KB_EV * T;                 // eV
  // Asymmetry from work-function difference & interface charge
  const asym = 1 + 0.08*sign*m.wd + 0.05*sign*S.ifc;
  // Effective barrier seen by carrier at this polarization state
  const phi = cl(m.phiBase - state*m.dphi + 0.06*sign*m.wd + 0.05*S.depol, 0.08, 4.5);
  const phiBil = cl(S.bilPhi + 0.10*S.depol - 0.08*S.ifc, 0.15, 4.8);

  // -------------- Fowler-Nordheim --------------
  // J_FN = A_FN * E² / φ * exp(-B_FN * φ^1.5 / E)
  // A_FN ≈ q³ / (8π h φ) → here parameterized via mEff
  // B_FN ≈ 6.83e7 * sqrt(m*) [V/cm * eV^-1.5]  (standard FN coefficient)
  const Bfn = 6.83e7 * Math.sqrt(S.mEff);
  const Afn = 1.54e-6 / Math.max(S.mEff, 0.05);
  const Jfn = Afn * Ecm*Ecm / Math.max(phi,0.05) *
              Math.exp(-Bfn * Math.pow(phi,1.5) / Math.max(Ecm,1));

  // -------------- Direct tunneling (WKB-like) --------------
  // J_DT ~ (V/t) * exp(-2 κ t),  κ ∝ sqrt(m* φ)
  const dtExp = -1.55*S.hzoT*Math.sqrt(Math.max(0.02, S.mEff*phi))
                -0.95*S.bilT*Math.sqrt(Math.max(0.02, S.mEff*phiBil));
  const Jdt = 2.0e2 * (aV/tNm) * Math.exp(dtExp) * Math.exp(0.16*aV) * (1 + 0.25*state);

  // -------------- Ohmic / hopping leakage --------------
  const sig = 2e-17 * (1 + 200*S.leak + 80*S.ovac + 35*S.trap);  // S/cm
  const Johm = sig * Ecm;

  // -------------- Schottky thermionic --------------
  const dS  = barrierLowering(EVm, m.epsEff, "schottky");      // eV
  const dPF = barrierLowering(EVm, m.epsEff, "pf");            // eV
  const A_RICH = 120;                                           // A/cm²/K² (Richardson)
  const Jsch = 1.2e-6 * A_RICH * T*T *
               Math.exp(-cl(phi - dS, 0.01, 5)/kT) * (1 + S.ifc);

  // -------------- Poole-Frenkel (trap-assisted hopping) --------------
  const Jpf = 2.2e-12 * (1 + 30*S.trap + 15*S.ovac) * Ecm *
              Math.exp(-cl(m.trapE - dPF, 0.01, 5)/kT);

  // -------------- TAT (trap-assisted tunneling) --------------
  const Jtat = 1e-5 * (S.trap + 0.15*S.ovac) * (1 + S.leak) *
               Math.sinh(aV/0.55) * Math.exp(-S.hzoT/2.8 - S.bilT/1.6);

  const Jleak = Johm + Jpf + Jsch + Jtat;
  const Jtot  = sign * asym * (Jdt + Jfn + Jleak);
  const Itot  = Jtot * m.areaCm2;

  return {
    V, Vapp:V, Ecm, EMV:Ecm/1e6, phi,
    Jdt, Jfn, Johm, Jpf, Jsch, Jtat, Jleak,
    Jtot, Itot
  };
}

// Self-consistent V_internal with series resistance
function componentsAt(V, state=1, includeRs=true){
  const m = model();
  let Vint = V;
  let ans = null;
  for(let i=0; i<(includeRs?3:1); i++){
    ans = componentsNoRs(Vint, state, m);
    const I = ans.Jtot * m.areaCm2;
    Vint = V - I*S.Rs;
    Vint = cl(Vint, -Math.abs(V)*1.2 - 0.02, Math.abs(V)*1.2 + 0.02);
  }
  return ans;
}

// I-V sweep array
function ivData(n=260){
  const arr = [];
  for(let i=0; i<=n; i++){
    const V = -S.Vmax + 2*S.Vmax*i/n;
    const on  = componentsAt(V,  1);
    const off = componentsAt(V, -1);
    arr.push({V, on, off});
  }
  return arr;
}

// Synthetic CSV-like data (for "Sample" button + when DATA is empty)
function syntheticData(noisy=false){
  const pts = [];
  const n = 96;
  for(let i=0; i<=n; i++){
    const V = -S.Vmax + 2*S.Vmax*i/n;
    if(Math.abs(V) < 0.015) continue;
    const c = componentsAt(V, V>=0 ? 1 : -1);
    const noise = noisy ? seedNoise(i,11)*S.noisePct/100 : 0;
    pts.push({ V, I: c.Itot*(1+noise), J: c.Jtot*(1+noise) });
  }
  return pts;
}

// ============================================================
//  MECHANISM FITTING (linear regression on transformed axes)
// ============================================================
function getFitInput(){
  const raw = DATA.length ? DATA : syntheticData(false);
  const m = model();
  return raw.map(p => ({
    V: p.V,
    I: p.I,
    J: (E.dataUnit && E.dataUnit.value==="J" && DATA.length) ? p.J : p.I/m.areaCm2,
    Ecm: Math.abs(p.V)/(m.tTot*1e-7),
    EVm: Math.abs(p.V)/(m.tTot*1e-9)
  })).filter(p =>
    Math.abs(p.V) > 0.025 &&
    Number.isFinite(p.I) && Math.abs(p.I) > 1e-30 &&
    p.Ecm > 0 && Number.isFinite(p.J)
  );
}
function linfit(xs, ys){
  const n = xs.length;
  if(n < 3) return {n,slope:NaN,intercept:NaN,r2:0,sse:Infinity};
  let sx=0, sy=0, sxx=0, sxy=0;
  for(let i=0; i<n; i++){
    sx+=xs[i]; sy+=ys[i]; sxx+=xs[i]*xs[i]; sxy+=xs[i]*ys[i];
  }
  const den = n*sxx - sx*sx;
  if(Math.abs(den) < 1e-30) return {n,slope:NaN,intercept:NaN,r2:0,sse:Infinity};
  const slope = (n*sxy - sx*sy) / den;
  const inter = (sy - slope*sx) / n;
  const ybar = sy/n;
  let sse=0, sst=0;
  for(let i=0; i<n; i++){
    const e = ys[i] - (slope*xs[i] + inter);
    sse += e*e;
    sst += (ys[i]-ybar)*(ys[i]-ybar);
  }
  const r2 = sst>0 ? cl(1 - sse/sst, 0, 1) : 0;
  return {n, slope, intercept:inter, r2, sse};
}
function fitMechanisms(){
  const pts = getFitInput();
  const vmax = Math.max(S.Vmax, ...pts.map(p=>Math.abs(p.V)));
  const all  = p => Math.abs(p.V) > 0.04;
  const low  = p => Math.abs(p.V) < Math.max(0.6, 0.35*vmax);
  const mid  = p => Math.abs(p.V) > 0.15 && Math.abs(p.V) < Math.max(1.5, 0.75*vmax);
  const high = p => Math.abs(p.V) > Math.max(0.45, 0.55*vmax);

  const mk = (name, range, transform, penaltyFn, phiFn) => {
    const sel = pts.filter(p => range(p) && Math.abs(p.J)>1e-300);
    const xs=[], ys=[];
    sel.forEach(p => {
      const r = transform(p);
      if(r && Number.isFinite(r.x) && Number.isFinite(r.y)){
        xs.push(r.x); ys.push(r.y);
      }
    });
    const f = linfit(xs, ys);
    const penalty = penaltyFn ? penaltyFn(f) : 0;
    const score = cl((f.r2||0) - penalty - (f.n<8 ? 0.25 : 0), 0, 1);
    const phi   = phiFn ? phiFn(f) : NaN;
    return {name, n:f.n, slope:f.slope, intercept:f.intercept, r2:f.r2, score, phi};
  };

  const fits = [];
  // Ohmic: ln(I) vs ln(V) at low V, slope ≈ 1
  fits.push(mk("Ohmic", low,
    p => ({x:Math.log(Math.abs(p.V)), y:Math.log(Math.abs(p.I))}),
    f => Math.min(0.35, Math.abs(f.slope-1)*0.18)
  ));
  // SCLC: slope ≈ 2
  fits.push(mk("SCLC", mid,
    p => ({x:Math.log(Math.abs(p.V)), y:Math.log(Math.abs(p.I))}),
    f => Math.min(0.35, Math.abs(f.slope-2)*0.15)
  ));
  // Schottky: ln(J) vs sqrt(E)  (slope must be positive)
  fits.push(mk("Schottky", all,
    p => ({x:Math.sqrt(p.EVm), y:Math.log(Math.abs(p.J))}),
    f => f.slope>0 ? 0 : 0.35
  ));
  // Poole-Frenkel: ln(J/E) vs sqrt(E)
  fits.push(mk("Poole-Frenkel", all,
    p => ({x:Math.sqrt(p.EVm), y:Math.log(Math.abs(p.J)/Math.max(p.Ecm,1))}),
    f => f.slope>0 ? 0 : 0.35
  ));
  // Fowler-Nordheim: ln(J/E²) vs 1/E (slope must be NEGATIVE)
  fits.push(mk("Fowler-Nordheim", high,
    p => ({x:1/p.Ecm, y:Math.log(Math.abs(p.J)/(p.Ecm*p.Ecm))}),
    f => f.slope<0 ? 0 : 0.40,
    f => {
      const B = 6.83e7 * Math.sqrt(S.mEff);
      // slope = -B * φ^1.5  →  φ = (-slope/B)^(2/3)
      return f.slope<0 ? Math.pow(-f.slope/Math.max(B,1), 2/3) : NaN;
    }
  ));
  // Direct/Brinkman: ln(J/V) vs V²
  fits.push(mk("Direct/Brinkman", mid,
    p => ({x:p.V*p.V, y:Math.log(Math.abs(p.J)/Math.max(Math.abs(p.V),1e-5))}),
    () => 0
  ));

  fits.sort((a,b) => b.score - a.score);
  return {fits, best:fits[0], pts};
}

// ============================================================
//  READ METRICS  (TER, sep, disturb, BER)
// ============================================================
function readMetrics(V, m){
  if(!m) m = model();
  const on  = componentsAt(V,  1);
  const off = componentsAt(V, -1);
  const Gon  = Math.abs(on.Itot  / Math.max(V, 1e-6));
  const Goff = Math.abs(off.Itot / Math.max(V, 1e-6));
  const ratio = Gon / Math.max(Goff, 1e-30);
  const sigma = Math.max(S.noisePct/100, 0.001) +
                0.018*S.leak + 0.012*S.trap + 0.010*S.ovac;
  const sep = Math.log(Math.max(ratio,1)) / Math.max(sigma, 1e-4);
  // Read disturb = sigmoid(V relative to ~Vc/3) × defect activity
  const disturb = sigmoid((V - 0.38*m.Vc)/0.10) *
                  (0.35 + 0.55*S.leak + 0.35*S.trap + 0.20*S.ovac);
  const ber = 0.5 * erfc(sep / (2*Math.sqrt(2)));
  const score = Math.log10(Math.max(ratio,1)) * Math.min(sep,50) / (1 + 7*disturb);
  return {V, Gon, Goff, ratio, sigma, sep, disturb, ber, score};
}
function scanRead(m){
  if(!m) m = model();
  const rows = [];
  for(let i=0; i<=70; i++){
    const V = 0.05 + i*(0.90 - 0.05)/70;
    rows.push(readMetrics(V, m));
  }
  const best = rows.reduce((a,b) => a.score>b.score ? a : b);
  return {rows, best};
}

// ============================================================
//  PUND CHARGE  (leak-subtracted Qsw)
// ============================================================
function pundMetrics(m){
  if(!m) m = model();
  // Switching factor: how cleanly pulse exceeds Vc, modulated by screening & leak
  let sw = sigmoid((S.pulseV - m.Vc)/0.16) * (1 - 0.25*S.leak) * (0.45 + 0.55*S.screen);
  sw = cl(sw, 0, 1.2);
  // Total switchable charge  Q_sw = 2 Pr * Area * sw
  const qsw = 2 * S.Pr * 1e-6 * m.areaCm2 * sw;     // C  (Pr in µC/cm² → ×1e-6)
  // Leakage current at pulse amplitude × pulse width
  const ileak = Math.abs(componentsAt(S.pulseV, 1).Itot) *
                (0.18 + 0.55*S.leak + 0.25*S.trap);
  const qLeak = ileak * S.pulseW * 1e-6;            // C  (pulseW in µs → ×1e-6)
  const qMeas = qsw + qLeak;
  return {sw, qsw, qLeak, qMeas,
          qswPc:qsw*1e12, qLeakPc:qLeak*1e12, qMeasPc:qMeas*1e12,
          ileak};
}

// ============================================================
//  RETENTION / FATIGUE / READ-DISTURB
// ============================================================
function retentionMetrics(m){
  if(!m) m = model();
  // tau (KWW-like time constant), grows with screening, shrinks with depol/leak/trap
  const tau = Math.pow(10, cl(
    3.0 + 1.55*S.screen + 0.55*(S.Pr/30)
       - 1.05*S.depol - 1.15*S.leak - 0.85*S.trap - 0.30*S.ovac, 0.2, 8));
  const read = readMetrics(S.readV, m);
  const rGoal = 1 + (read.ratio-1) * Math.exp(-Math.pow(S.retentionGoal/tau, 0.62));
  // Endurance characteristic cycle count
  const n0 = Math.pow(10, cl(5.2 + 1.4*S.screen - 1.4*S.leak - 0.8*S.trap - 0.6*S.ovac, 2, 9));
  const fatigueLoss = 1 - Math.exp(-Math.pow(S.enduranceN/n0, 0.55));
  const ratioAfter  = 1 + (read.ratio-1)*(1 - 0.72*fatigueLoss);
  // Cumulative read-disturb risk after enduranceN reads at readV
  const readDisturb = 1 - Math.exp(-read.disturb*S.enduranceN/2.5e6);
  return {tau, rGoal, n0, fatigueLoss, ratioAfter, readDisturb, read};
}

// ============================================================
//  32-state STATISTICS
// ============================================================
function stateMetrics(m){
  if(!m) m = model();
  const read = readMetrics(S.readV, m);
  const n = Math.max(2, Math.round(S.nStates));
  const gmin = Math.log(Math.max(read.Goff, 1e-30));
  const gmax = Math.log(Math.max(read.Gon,  read.Goff*1.01));
  const span = Math.max(gmax - gmin, 1e-9);
  const sigma = Math.max(S.noisePct/100, 0.002) +
                0.018*S.trap + 0.020*S.leak + 0.012*S.ovac +
                0.06*Math.pow(S.readV/Math.max(m.Vc,0.1), 1.8);
  const step = span / Math.max(n-1, 1);
  const sep  = step/sigma;
  const usable = Math.min(n, Math.max(1, Math.floor(span/(2*sigma))));
  const ber = 0.5 * erfc(sep / (2*Math.sqrt(2)));
  return {n, gmin, gmax, span, sigma, step, sep, usable, ber, read};
}

// ============================================================
//  RISK score (0–100)
// ============================================================
function gradeRisk(m, scan, sn, fit, pund, ret){
  let s = 0;
  s += m.risk * 30;
  s += scan.best.disturb * 25;
  s += sn.usable < sn.n ? 25*(1 - sn.usable/sn.n) : 0;
  const fn = fit.fits.find(f => f.name==="Fowler-Nordheim");
  s += fn.r2 < 0.95 ? 8 : 0;
  s += pund.qLeakPc > pund.qswPc*0.35 ? 12 : 0;
  s += ret.rGoal < Math.sqrt(ret.read.ratio) ? 10 : 0;
  return cl(s, 0, 100);
}

// ============================================================
//  CANVAS HELPERS
// ============================================================
function canvasCtx(c){
  // v12 fix: cache the *original* logical height once.
  // Reading c.getAttribute("height") each call is unsafe — setting c.height in JS
  // updates the same attribute, so the next call reads the DPR-scaled buffer
  // value and multiplies again → exponential vertical growth on HiDPI displays.
  if(!c.dataset.logicalH){
    c.dataset.logicalH = c.getAttribute("height") || "300";
  }
  const h = Number(c.dataset.logicalH);
  const d = window.devicePixelRatio||1;
  const r = c.getBoundingClientRect();
  const w = r.width;
  // Lock CSS-pixel display size so the canvas can never visually stretch,
  // regardless of how large the buffer (c.width/c.height) becomes.
  c.style.width  = w + "px";
  c.style.height = h + "px";
  // Backing buffer in device pixels for crisp HiDPI rendering.
  c.width  = Math.max(10, Math.round(w*d));
  c.height = Math.round(h*d);
  const g = c.getContext("2d");
  g.setTransform(d,0,0,d,0,0);
  return {g, w, h};
}
function line(g,x1,y1,x2,y2,c="#111",lw=1,dash=[]){
  g.save(); g.strokeStyle=c; g.lineWidth=lw; g.setLineDash(dash);
  g.beginPath(); g.moveTo(x1,y1); g.lineTo(x2,y2); g.stroke(); g.restore();
}
function fill(g,x,y,w,h,c,s){
  g.save(); g.fillStyle=c; g.fillRect(x,y,w,h);
  if(s){ g.strokeStyle=s; g.strokeRect(x,y,w,h); }
  g.restore();
}
function txt(g,t,x,y,c="#111",f="12px sans-serif",a="left",b="alphabetic"){
  g.save(); g.fillStyle=c; g.font=f; g.textAlign=a; g.textBaseline=b;
  g.fillText(t,x,y); g.restore();
}
function circ(g,x,y,r,c){
  g.save(); g.fillStyle=c; g.beginPath(); g.arc(x,y,r,0,Math.PI*2); g.fill(); g.restore();
}
function arrowH(g,x1,y1,x2,y2,c,lw,dash){
  line(g,x1,y1,x2,y2,c||"#111",lw||2,dash||[]);
  const a = Math.atan2(y2-y1, x2-x1), hh = 9 + (lw||2);
  g.save(); g.fillStyle = c||"#111"; g.beginPath();
  g.moveTo(x2,y2);
  g.lineTo(x2 - hh*Math.cos(a-Math.PI/6), y2 - hh*Math.sin(a-Math.PI/6));
  g.lineTo(x2 - hh*Math.cos(a+Math.PI/6), y2 - hh*Math.sin(a+Math.PI/6));
  g.closePath(); g.fill(); g.restore();
}
function tickFmt(v){
  const a = Math.abs(v);
  if(a>=1000 || (a<0.01 && v!==0)) return Number(v).toExponential(1);
  return Number(v).toFixed(a>=10 ? 0 : a>=1 ? 1 : 2);
}
function axes(g,x,y,w,h,o){
  const xmin=o.xmin, xmax=o.xmax, ymin=o.ymin, ymax=o.ymax;
  const xt=o.xticks||5, yt=o.yticks||5;
  fill(g,x,y,w,h,"#fff");
  for(let i=0; i<=xt; i++){ const xx=x+w*i/xt; line(g,xx,y,xx,y+h,"#e7edf5"); }
  for(let j=0; j<=yt; j++){ const yy=y+h*j/yt; line(g,x,yy,x+w,yy,"#e7edf5"); }
  line(g,x,y+h,x+w,y+h,"#24334a",1.2);
  line(g,x,y,x,y+h,"#24334a",1.2);
  for(let i=0; i<=xt; i++){
    const xx=x+w*i/xt, val=xmin+(xmax-xmin)*i/xt;
    line(g,xx,y+h,xx,y+h+5,"#24334a");
    txt(g,tickFmt(val),xx,y+h+9,"#334155","11px sans-serif","center","top");
  }
  for(let j=0; j<=yt; j++){
    const yy=y+h*j/yt, val=ymax-(ymax-ymin)*j/yt;
    line(g,x-5,yy,x,yy,"#24334a");
    txt(g,tickFmt(val),x-8,yy,"#334155","11px sans-serif","right","middle");
  }
  txt(g,o.xlabel||"",x+w/2,y+h+31,"#24344f","12px sans-serif","center");
  g.save(); g.translate(x-45, y+h/2); g.rotate(-Math.PI/2);
  txt(g,o.ylabel||"",0,0,"#24344f","12px sans-serif","center");
  g.restore();
  return {
    X: v => x + (v-xmin)/(xmax-xmin)*w,
    Y: v => y + h - (v-ymin)/(ymax-ymin)*h,
    x, y, w, h, xmin, xmax, ymin, ymax
  };
}

// ============================================================
//  DRAW: 1) Live energy band  (Neamen-style, Vapp interactive)
// ============================================================
function drawBand(){
  const {g,w,h} = canvasCtx(E.band);
  const m = model();
  g.clearRect(0,0,w,h);
  if(S.mode==="live"){
    bandPanel(g, 18, 30, w-36, h-58,
              "Live band @ Vapp = "+fmt(S.Vapp,2)+" V", 1, m, S.Vapp, true);
  } else if(S.mode==="compare"){
    // v10: BOTH panels at same Vapp, only polarization state differs.
    // This isolates the polarization contribution visually.
    const Vshow = S.Vapp;
    bandPanel(g, 18, 30, (w-56)/2, h-58,
              "OFF state @ Vapp = "+fmt(Vshow,2)+" V", -1, m, Vshow, false);
    bandPanel(g, 38+(w-56)/2, 30, (w-56)/2, h-58,
              "ON state @ Vapp = "+fmt(Vshow,2)+" V", +1, m, Vshow, false);
  } else {
    const t = S.mode==="mfm" ? "MFM-like (BIL ignored visually)"
            : S.mode==="mfs" ? "MFS — semiconductor electrode @ Vapp = "+fmt(S.Vapp,2)+" V"
            : "MFIS / BIL emphasis";
    bandPanel(g, 18, 30, w-36, h-58, t, 1, m, S.Vapp, true);
  }
}
function bandPanel(g,x,y,w,h,title,sg,m,V,live){
  const bilVis = (S.mode==="mfm") ? 0 : S.bilT;
  // v13: a semiconductor electrode gets a wider block so its depletion shows.
  const scBE = (m.mfs && m.scSide==="be") ? m.scMat : null;
  const scTE = (m.mfs && m.scSide==="te") ? m.scMat : null;
  const teW = scTE ? 4.2 : 2;
  const beW = scBE ? 4.2 : 2;
  const total = teW + beW + S.hzoT + bilVis;
  const ax = axes(g, x+62, y+34, w-84, h-76,
    {xmin:0, xmax:total, ymin:-8.6, ymax:3.0, xticks:6, yticks:6,
     xlabel:"Position (nm)", ylabel:"Energy (eV)"});
  const xTE=teW, xH=teW+S.hzoT, xB=xH+bilVis, xBE=xB+beW;
  const r0=ax.X(0), rTE=ax.X(xTE), rH=ax.X(xH), rB=ax.X(xB), rBE=ax.X(xBE);
  const top=ax.Y(3.0), bot=ax.Y(-8.6);

  txt(g,title,x+12,y+14, sg>0 ? "#1d4ed8" : "#0f172a","bold 16px sans-serif");

  // Layer fills
  fill(g, r0, top, rTE-r0,  bot-top, "rgba(37,99,235,.15)");
  fill(g, rTE,top, rH-rTE,  bot-top, "rgba(245,158,11,.18)");
  if(bilVis>0.05) fill(g, rH, top, rB-rH, bot-top, "rgba(148,163,184,.24)");
  fill(g, rB, top, rBE-rB,  bot-top, scBE ? "rgba(8,145,178,.12)" : "rgba(6,182,212,.16)");

  txt(g, S.te, (r0+rTE)/2, ax.Y(2.55), "#1d4ed8", "bold 13px sans-serif", "center");
  txt(g, "HZO",(rTE+rH)/2, ax.Y(2.55), "#b45309", "bold 13px sans-serif", "center");
  if(bilVis>0.05)
    txt(g, "BIL / TiOx", (rH+rB)/2, ax.Y(2.55), "#475569", "bold 12px sans-serif", "center");
  // semiconductor BE name sits higher (regime label uses 2.55 row)
  txt(g, S.be, (rB+rBE)/2, ax.Y(scBE ? 2.88 : 2.55), "#0e7490", "bold 12px sans-serif", "center");

  // ===== v10: state-dependent voltage split =====
  // Vapp = V_HZO + V_BIL.  Polarization adds ±Vint that flips with state.
  const split = voltageSplit(V, sg, m);
  const VhzoDrop = split.Vhzo;   // V across HZO  (positive → tilt down to right)
  const VbilDrop = split.Vbil;   // V across BIL

  // Fermi levels: V_TE − V_BE = V  →  E_F,TE = -V relative to E_F,BE = 0
  const EFbe = 0, EFte = -V;
  // E_vac dashed at +2.35 eV
  line(g, r0, ax.Y(2.35), rBE, ax.Y(2.35), "#6b7280", 1.4, [7,5]);
  txt(g,"E_vac", rBE-3, ax.Y(2.35)-8, "#4b5563","bold 11px sans-serif","right");
  // EF lines
  line(g, r0, ax.Y(EFte), rTE, ax.Y(EFte), "#111827", 2, [7,4]);
  txt(g,"E_F,TE", r0+8, ax.Y(EFte)-8, "#111827","bold 11px sans-serif");
  line(g, rB, ax.Y(EFbe), rBE, ax.Y(EFbe), "#111827", 2, [7,4]);
  txt(g,"E_F,BE", rBE-6, ax.Y(EFbe)-8, "#111827","bold 11px sans-serif","right");
  // qVapp arrow
  if(Math.abs(V)>0.05){
    arrowH(g, rTE+16, ax.Y(EFte), rTE+16, ax.Y(EFbe), "#dc2626", 2.3);
    txt(g,"qVapp", rTE+22, (ax.Y(EFte)+ax.Y(EFbe))/2, "#dc2626","bold 11px sans-serif","left","middle");
  }

  // ===== v10: Conduction band tilts using ACTUAL V drop per layer =====
  // Polarization shifts the *barrier height* (Δφ) AND modulates V split.
  // Both effects are now visible.
  const polShift = sg * m.dphi;

  // E_C entry on TE side: TE Fermi + φ_TE/HZO barrier - polarization shift
  const EcL = EFte + S.hzoPhi - polShift;
  // E_C exit on HZO/BIL boundary: TE side + V drop across HZO
  // (positive V drop means HZO right side is LOWER than left)
  const EcR_hzo = EcL - VhzoDrop;
  // BIL conduction band starts here (with BIL barrier offset)
  const Ebil_in = bilVis>0.05 ? EcR_hzo + (S.bilPhi - S.hzoPhi) : EcR_hzo;
  // BIL exit: V drop across BIL
  const Ebil_out = Ebil_in - VbilDrop;

  const EvL = EcL - S.hzoEg, EvR = EcR_hzo - S.hzoEg;
  const Bv_in = Ebil_in - S.bilEg, Bv_out = Ebil_out - S.bilEg;

  // ===== v11: Polarization-induced band bending (Image 7-style) =====
  // Inside HZO: bound polarization charge ±σ_P at the surfaces.
  // Inside BIL: residual screening charge sits at the HZO/BIL interface,
  // creating EXTRA field inside BIL.  Both effects bend the conduction band
  // away from a simple straight line.
  //
  // We sample E_C at N points along each layer with a quadratic correction:
  //   E_C(ξ) = E_left + (E_right − E_left)·ξ + α·ξ(1−ξ)
  // where α is the bending strength (positive = bowed downward, negative = upward).
  //
  // Bending magnitude scales with (1 − f_screen)·P_r.  Polarity sign matters.
  const screenIncomp = 1 - S.screen;        // imperfect screening fraction
  const bendMag = screenIncomp * (S.Pr/30) * 0.55;   // visual scale (eV)
  const bendHzo = sg * bendMag * 0.6;        // HZO interior bending
  const bendBil = sg * bendMag * 1.4;        // BIL interior bending (stronger)

  function sampleBand(N, eL, eR, alpha){
    const pts = [];
    for(let i=0; i<=N; i++){
      const xi = i/N;
      const e = eL + (eR-eL)*xi + alpha*xi*(1-xi);
      pts.push([xi, e]);
    }
    return pts;
  }
  const NSAMP = 24;

  // E_C (conduction band) — with bending
  g.save();
  g.strokeStyle = "#111827"; g.lineWidth = 3.2;
  g.beginPath();
  // HZO segment
  const hzoCB = sampleBand(NSAMP, EcL, EcR_hzo, bendHzo);
  hzoCB.forEach((p,i) => {
    const X = rTE + (rH-rTE)*p[0], Y = ax.Y(p[1]);
    if(i===0) g.moveTo(X,Y); else g.lineTo(X,Y);
  });
  if(bilVis>0.05){
    g.lineTo(rH,  ax.Y(Ebil_in));
    const bilCB = sampleBand(NSAMP, Ebil_in, Ebil_out, bendBil);
    bilCB.forEach((p,i) => {
      const X = rH + (rB-rH)*p[0], Y = ax.Y(p[1]);
      if(i===0) g.moveTo(X,Y); else g.lineTo(X,Y);
    });
  }
  g.stroke(); g.restore();

  // E_V (valence band) — same bending shape, shifted by Eg
  g.save();
  g.strokeStyle = "#64748b"; g.lineWidth = 2.4; g.setLineDash([8,4]);
  g.beginPath();
  const hzoVB = sampleBand(NSAMP, EvL, EvR, bendHzo);
  hzoVB.forEach((p,i) => {
    const X = rTE + (rH-rTE)*p[0], Y = ax.Y(p[1]);
    if(i===0) g.moveTo(X,Y); else g.lineTo(X,Y);
  });
  if(bilVis>0.05){
    g.lineTo(rH,  ax.Y(Bv_in));
    const bilVB = sampleBand(NSAMP, Bv_in, Bv_out, bendBil);
    bilVB.forEach((p,i) => {
      const X = rH + (rB-rH)*p[0], Y = ax.Y(p[1]);
      if(i===0) g.moveTo(X,Y); else g.lineTo(X,Y);
    });
  }
  g.stroke(); g.restore();

  // Bending annotation
  if(Math.abs(bendBil) > 0.05 && bilVis > 0.1){
    txt(g, "↶ band bending from imperfect screening",
        (rH+rB)/2, ax.Y(0.5), "#7c3aed","italic 10px sans-serif","center");
  }

  txt(g,"E_C", rH-6, ax.Y(Math.max(EcL,EcR_hzo))+14, "#0f172a","bold 12px sans-serif","right");
  txt(g,"E_V", rH-6, ax.Y(Math.min(EvL,EvR))-8, "#475569","bold 12px sans-serif","right");

  // ===== v10: Bound charge ±σ_P at HZO surfaces (visible!) =====
  // Sign convention: ON state (+1) means polarization points TE→BE
  // → HZO/TE surface has -σ_P, HZO/BE (or HZO/BIL) surface has +σ_P
  // OFF state flips. We exaggerate visually for pedagogy.
  if(S.Pr > 1){
    const yCharge = ax.Y(-1.5);
    const Pmag = Math.min(1, S.Pr/40);   // visual scale
    const chargeSize = 11 + Pmag*8;
    // TE/HZO interface
    const sgnL = -sg;   // polarization direction → opposite sign at TE side
    const sgnR = +sg;
    const colL = sgnL>0 ? "#dc2626" : "#1d4ed8";
    const colR = sgnR>0 ? "#dc2626" : "#1d4ed8";
    txt(g, sgnL>0?"⊕":"⊖", rTE+9, yCharge, colL, "bold "+chargeSize+"px sans-serif", "left", "middle");
    txt(g, sgnL>0?"⊕":"⊖", rTE+9+chargeSize*0.7, yCharge, colL, "bold "+chargeSize+"px sans-serif", "left", "middle");
    const rRcharge = bilVis>0.05 ? rH-9 : rH-9;
    txt(g, sgnR>0?"⊕":"⊖", rRcharge, yCharge, colR, "bold "+chargeSize+"px sans-serif", "right", "middle");
    txt(g, sgnR>0?"⊕":"⊖", rRcharge-chargeSize*0.7, yCharge, colR, "bold "+chargeSize+"px sans-serif", "right", "middle");
    txt(g, "σ_P="+(sg*S.Pr).toFixed(0)+" μC/cm²",
        (rTE+rH)/2, ax.Y(-1.05), "#7c3aed","bold 10px sans-serif","center");

    // ===== Screening charge in metal/BIL (imperfect screening visible) =====
    // f_screen ∈ [0,1].  Perfect screening → metal exactly cancels σ_P.
    // Imperfect → residual charge remains, drives Vint.
    const screenFrac = S.screen;       // how much is canceled
    const residual = 1 - screenFrac;   // visible residual
    if(screenFrac > 0.05){
      // Counter-charges in TE (opposite sign of σ_P) — proportional to screenFrac
      const countSize = chargeSize * (0.6 + 0.4*screenFrac);
      txt(g, sgnL>0?"⊖":"⊕", rTE-9, yCharge, sgnL>0?"#1d4ed8":"#dc2626",
          "bold "+countSize+"px sans-serif", "right", "middle");
      txt(g, sgnR>0?"⊖":"⊕", rRcharge+22+(bilVis>0.05?(rB-rH):0), yCharge,
          sgnR>0?"#1d4ed8":"#dc2626",
          "bold "+countSize+"px sans-serif", "left", "middle");
      txt(g, "screening "+(screenFrac*100).toFixed(0)+"%",
          (r0+rTE)/2-4, ax.Y(-2.3), "#0f172a","11px sans-serif","center");
    }
    if(residual > 0.05 && S.bilT > 0.1){
      // Residual charge stays at HZO/BIL → drives Vint across BIL
      txt(g, "residual ⇒ V_int across BIL",
          (rH+rB)/2, ax.Y(-2.3),
          "#b91c1c","bold 10px sans-serif","center");
    }
  }

  // ===== v10: V_HZO and V_BIL drop labels (the key new info!) =====
  if(Math.abs(V)>0.05 || S.Pr>1){
    const yLabel = ax.Y(-3.4);
    txt(g, "V_HZO = "+VhzoDrop.toFixed(2)+" V",
        (rTE+rH)/2, yLabel, "#b45309","bold 11px sans-serif","center");
    if(bilVis > 0.05){
      txt(g, "V_BIL = "+VbilDrop.toFixed(2)+" V",
          (rH+rB)/2, yLabel, "#475569","bold 11px sans-serif","center");
    }
    // Show the polarization-induced internal voltage explicitly
    if(S.Pr>1 && S.bilT>0.1){
      txt(g, "V_int = "+(sg*m.Vint).toFixed(2)+" V (from σ_P)",
          (rH+rB)/2, ax.Y(-4.0), sg>0?"#dc2626":"#1d4ed8",
          "bold 10px sans-serif","center");
    }
  }

  // ===== v11: Tunneling arrow direction flips with V_app sign =====
  // V_app > 0 (TE positive): electrons flow BE → TE  (arrow right→left)
  // V_app < 0 (TE negative): electrons flow TE → BE  (arrow left→right)
  // |V_app| ~ 0: faint, ambiguous direction
  if(Math.abs(V) > 0.05){
    const arrLen = Math.min(1, Math.abs(V)/2);   // visual scale
    const aw = 4 * (0.5 + 0.5*arrLen);
    if(V > 0){
      // electrons BE → TE (right to left)
      arrowH(g, rB+52, ax.Y(EFbe+0.95), rTE+20, ax.Y(EFte+0.95), "#ef4444", aw);
      txt(g,"e⁻ tunneling →←", (rTE+rB)/2, ax.Y((EFbe+EFte)/2 + 0.73),
          "#b91c1c","bold 12px sans-serif","center");
    } else {
      // electrons TE → BE (left to right)
      arrowH(g, rTE+20, ax.Y(EFte+0.95), rB+52, ax.Y(EFbe+0.95), "#ef4444", aw);
      txt(g,"e⁻ tunneling →", (rTE+rB)/2, ax.Y((EFbe+EFte)/2 + 0.73),
          "#b91c1c","bold 12px sans-serif","center");
    }
  } else {
    // V near zero — no net current
    txt(g,"V≈0 (no net tunneling)", (rTE+rB)/2, ax.Y((EFbe+EFte)/2 + 0.73),
        "#94a3b8","italic 11px sans-serif","center");
  }

  // Polarization arrow
  arrowH(g, (rTE+rH)/2 - 30, ax.Y(-7.25), (rTE+rH)/2 + 30*sg, ax.Y(-7.25), "#fff", 4);
  txt(g,"P", (rTE+rH)/2, ax.Y(-7.58), "#fff","bold 14px sans-serif","center");

  // E_dep arrow (opposes P)
  if(m.Edep > 0.03){
    arrowH(g, (rTE+rH)/2 + 28, ax.Y(-6.15), (rTE+rH)/2 - 28*sg, ax.Y(-6.15), "#0ea5e9", 3, [4,4]);
    txt(g,"E_dep "+m.Edep.toFixed(2)+" MV/cm",(rTE+rH)/2, ax.Y(-6.45), "#0284c7","bold 11px sans-serif","center");
  }

  // ===== v13: MFS — semiconductor BE band bending over depletion width =====
  if(scBE){
    const sp = semiSolve(V, sg, m);
    // Degenerate p-type: E_F pinned at/just inside E_V.  Reference E_F,SC = EFbe.
    const Ev_bulk = EFbe + 0.06;
    const Ec_bulk = Ev_bulk + scBE.Eg;
    const psi = Math.abs(sp.Vsc + sg*m.scPolDrive);          // surface band bending (V≈eV)
    const dep = (sp.regime === "depletion");
    const bendDir = dep ? +1 : -1;                            // p-type: deplete→up, accum→down
    // Map depletion width to block pixels (cap at block width).
    const Wpix = (rBE - rB) * cl(sp.W / Math.max(beW,0.1), 0.12, 1);
    // Shade the depletion (or accumulation) region near the interface.
    fill(g, rB, top, Wpix, bot-top, dep ? "rgba(220,38,38,.10)" : "rgba(16,185,129,.10)");
    line(g, rB+Wpix, top, rB+Wpix, bot, dep ? "#dc2626" : "#10b981", 1, [3,4]);

    function scBand(eBulk){
      const pts = [];
      const N = 26;
      for(let i=0;i<=N;i++){
        const X = rB + Wpix*(i/N);
        const xi = i/N;                                       // 0 at interface → 1 at W edge
        const e = eBulk + bendDir*psi*(1-xi)*(1-xi);
        pts.push([X, ax.Y(e)]);
      }
      // flat bulk from W edge to far contact
      pts.push([rBE, ax.Y(eBulk)]);
      return pts;
    }
    // E_C (semiconductor)
    g.save(); g.strokeStyle="#0e7490"; g.lineWidth=3.0; g.beginPath();
    scBand(Ec_bulk).forEach((p,i)=> i? g.lineTo(p[0],p[1]) : g.moveTo(p[0],p[1]));
    g.stroke(); g.restore();
    // E_V (semiconductor)
    g.save(); g.strokeStyle="#155e75"; g.lineWidth=2.4; g.setLineDash([7,4]); g.beginPath();
    scBand(Ev_bulk).forEach((p,i)=> i? g.lineTo(p[0],p[1]) : g.moveTo(p[0],p[1]));
    g.stroke(); g.restore();

    txt(g,"E_C,sc",(rB+rBE)/2+10, ax.Y(Ec_bulk)-7,"#0e7490","bold 10px sans-serif","center");
    txt(g,"E_V,sc",(rB+rBE)/2+10, ax.Y(Ev_bulk)+13,"#155e75","bold 10px sans-serif","center");
    txt(g, (dep?"DEPLETION":"ACCUMULATION")+" W="+sp.W.toFixed(2)+" nm",
        rB+4, ax.Y(2.55), dep?"#b91c1c":"#047857","bold 10px sans-serif","left");
    txt(g,"λ_TF="+m.lambdaTF.toFixed(2)+" nm (metal≈0.05)",
        (rB+rBE)/2, ax.Y(-3.0), "#7c3aed","italic 10px sans-serif","center");
    if(dep){
      txt(g,"↑ holes pushed away → barrier widens, ON current ↓",
          (rB+rBE)/2, ax.Y(-3.7),"#b91c1c","italic 9.5px sans-serif","center");
    }
  }

  // Work-function arrows
  arrowH(g, r0+30, ax.Y(2.35)-1, r0+30, ax.Y(EFte)+1, "#1d4ed8", 2.2);
  txt(g,"Φ_TE="+m.wfT.toFixed(2)+" eV", r0+38, (ax.Y(2.35)+ax.Y(EFte))/2, "#1d4ed8","bold 11px sans-serif","left","middle");
  arrowH(g, rBE-30, ax.Y(2.35)-1, rBE-30, ax.Y(EFbe)+1, "#0e7490", 2.2);
  txt(g,"Φ_BE="+m.wfB.toFixed(2)+" eV", rBE-38, (ax.Y(2.35)+ax.Y(EFbe))/2, "#0e7490","bold 11px sans-serif","right","middle");

  // Δφ(P) annotation
  txt(g,"Δφ(P) = "+(2*m.dphi).toFixed(2)+" eV (ON↔OFF)", rTE+10, y+14, "#7c3aed","bold 11px sans-serif");

  // ===== v10: regime indicator (DT vs F-N) =====
  const phiAvg = m.phiBase;
  const regime = Math.abs(V) > phiAvg ? "F-N (triangular)" : "DT (trapezoidal)";
  const regCol = Math.abs(V) > phiAvg ? "#dc2626" : "#059669";
  txt(g, "regime: "+regime, x+w-14, y+14, regCol,"bold 11px sans-serif","right");
}

// ============================================================
//  DRAW: 2) V(x) / E(x) / Charge(x) profile
// ============================================================
function drawProfile(){
  const {g,w,h} = canvasCtx(E.profile);
  const m = model();
  g.clearRect(0,0,w,h);
  const gap=32, ph=(h-82-2*gap)/3, left=78, pw=w-112;

  // v10: polarity-aware voltage split (ON state for single-state profile)
  const split2 = voltageSplit(S.Vapp, +1, m);
  const VbilDrop = split2.Vbil;
  const VhzoDrop = split2.Vhzo;

  // ===== v13: MFS geometry — widen BE region to show depletion =====
  const mfsBE = m.mfs && m.scSide==="be";
  const Wdep  = mfsBE ? split2.W : 0;
  const Vdead = mfsBE ? split2.Vdead : 0;
  const Vsc   = mfsBE ? split2.Vsc : 0;
  const tDeadV = mfsBE ? m.tDead : 0;
  const beW   = mfsBE ? cl(Math.max(2.4, Wdep*1.25), 2.4, 7) : 2;
  const xTE=2, xH=2+S.hzoT, xB=xH+S.bilT, xD=xB+tDeadV, xSC=xD+beW;
  const total = xSC;
  const Wend  = Math.min(xD+Wdep, total);   // depletion edge in x-units

  // V(x)
  const ax1 = axes(g, left, 24, pw, ph,
    {xmin:0, xmax:total, ymin:Math.min(-0.1, S.Vapp*1.1), ymax:Math.max(0.95, S.Vapp*1.1, 0.8),
     xticks:6, yticks:4, xlabel:"Position (nm)", ylabel:"V(x) [V]"});
  // E(x) [MV/cm]
  const Ehzo = (VhzoDrop/Math.max(S.hzoT,0.1)) * 10;   // V/nm → MV/cm
  const Ebil = S.bilT>0 ? (VbilDrop/Math.max(S.bilT,0.05)) * 10 : 0;
  const Edead = tDeadV>0 ? (Vdead/Math.max(tDeadV,0.02)) * 10 : 0;
  const Esurf = (mfsBE && Wdep>0.05) ? (2*Vsc/Math.max(Wdep,0.05))*10 : 0;  // triangular peak
  const Eabs = Math.max(2.0, Math.abs(Ehzo)*1.2, Math.abs(Ebil)*1.2, Math.abs(Esurf)*1.1);
  const ax2 = axes(g, left, 24+ph+gap, pw, ph,
    {xmin:0, xmax:total, ymin:-Eabs, ymax:Eabs,
     xticks:6, yticks:4, xlabel:"Position (nm)", ylabel:"E(x) [MV/cm]"});
  // Charge
  const ax3 = axes(g, left, 24+2*(ph+gap), pw, ph,
    {xmin:0, xmax:total, ymin:-1.5, ymax:1.5,
     xticks:6, yticks:4, xlabel:"Position (nm)", ylabel:"Charge [µC/cm²]"});

  // Layer shading
  [[ax1,24],[ax2,24+ph+gap],[ax3,24+2*(ph+gap)]].forEach(p => {
    const ax = p[0], yy = p[1];
    fill(g,ax.X(0),  yy, ax.X(xTE)-ax.X(0),   ph, "rgba(37,99,235,.10)");
    fill(g,ax.X(xTE),yy, ax.X(xH)-ax.X(xTE),  ph, "rgba(245,158,11,.13)");
    if(S.bilT>0.05) fill(g,ax.X(xH),yy, ax.X(xB)-ax.X(xH), ph, "rgba(148,163,184,.17)");
    if(tDeadV>0.02) fill(g,ax.X(xB),yy, ax.X(xD)-ax.X(xB), ph, "rgba(120,53,15,.16)");
    fill(g,ax.X(xD), yy, ax.X(total)-ax.X(xD), ph, "rgba(8,145,178,.11)");
    // depletion highlight
    if(mfsBE && Wdep>0.05)
      fill(g,ax.X(xD),yy, ax.X(Wend)-ax.X(xD), ph,
           split2.regime==="depletion" ? "rgba(220,38,38,.08)" : "rgba(16,185,129,.08)");
  });

  // --- V(x): TE flat, linear HZO, (BIL), (dead), parabolic SC depletion ---
  g.save(); g.strokeStyle="#2563eb"; g.lineWidth=2.6; g.beginPath();
  g.moveTo(ax1.X(0),   ax1.Y(0));
  g.lineTo(ax1.X(xTE), ax1.Y(0));
  g.lineTo(ax1.X(xH),  ax1.Y(VhzoDrop));
  let Vacc = VhzoDrop;
  if(S.bilT>0.05){ Vacc += VbilDrop; g.lineTo(ax1.X(xB), ax1.Y(Vacc)); }
  if(tDeadV>0.02){ Vacc += Vdead;    g.lineTo(ax1.X(xD), ax1.Y(Vacc)); }
  if(mfsBE && Wdep>0.05){
    // parabolic depletion tail over W:  V(ξ) = Vstart + Vsc·(2ξ − ξ²)
    const N=24;
    for(let i=0;i<=N;i++){
      const xi=i/N, xx = xD + (Wend-xD)*xi;
      g.lineTo(ax1.X(xx), ax1.Y(Vacc + Vsc*(2*xi - xi*xi)));
    }
    g.lineTo(ax1.X(total), ax1.Y(S.Vapp));   // flat bulk
  } else {
    g.lineTo(ax1.X(total), ax1.Y(S.Vapp));
  }
  g.stroke(); g.restore();
  const dropMsg = mfsBE
    ? `V_TE−V_BE = ${fmt(S.Vapp,2)} V  |  SC eats ${(Math.abs(Vsc)/Math.max(Math.abs(S.Vapp),1e-3)*100).toFixed(0)}% (${split2.regime})`
    : `V_TE − V_BE = ${fmt(S.Vapp,2)} V  |  BIL drop ${(m.VbilFrac*100).toFixed(0)}%`;
  txt(g, dropMsg, left, 16, "#1d4ed8","bold 12.5px sans-serif");

  // --- E(x): constant per dielectric layer, triangular in SC depletion ---
  line(g, ax2.X(0), ax2.Y(0), ax2.X(total), ax2.Y(0), "#64748b", 1, [4,4]);
  g.save(); g.strokeStyle="#dc2626"; g.lineWidth=2.6; g.beginPath();
  g.moveTo(ax2.X(0),    ax2.Y(0));
  g.lineTo(ax2.X(xTE),  ax2.Y(0));
  g.lineTo(ax2.X(xTE),  ax2.Y(Ehzo));
  g.lineTo(ax2.X(xH),   ax2.Y(Ehzo));
  if(S.bilT>0.05){ g.lineTo(ax2.X(xH), ax2.Y(Ebil)); g.lineTo(ax2.X(xB), ax2.Y(Ebil)); }
  if(tDeadV>0.02){ g.lineTo(ax2.X(xB), ax2.Y(Edead)); g.lineTo(ax2.X(xD), ax2.Y(Edead)); }
  if(mfsBE && Wdep>0.05){
    g.lineTo(ax2.X(xD),  ax2.Y(Esurf));     // jump to surface field
    g.lineTo(ax2.X(Wend),ax2.Y(0));         // linear decay to 0 (triangular)
    g.lineTo(ax2.X(total),ax2.Y(0));
  } else {
    g.lineTo(ax2.X(xD),  ax2.Y(0));
    g.lineTo(ax2.X(total),ax2.Y(0));
  }
  g.stroke(); g.restore();
  txt(g, mfsBE
        ? `E_HZO = ${Ehzo.toFixed(2)}  |  E_sc,surf = ${Esurf.toFixed(2)} MV/cm (→0 over W)`
        : `E_HZO = ${Ehzo.toFixed(2)} MV/cm   |   E_BIL = ${Ebil.toFixed(2)} MV/cm`,
    left, 24+ph+gap-8, "#b91c1c","bold 12px sans-serif");

  // --- Charge: bound σ_P, interface q, + depletion acceptor box for MFS ---
  const sigP = S.Pr * (1 - S.screen);
  const qIfc = S.ifc * (0.5 + 0.6*S.ovac);
  line(g, ax3.X(0), ax3.Y(0), ax3.X(total), ax3.Y(0), "#64748b", 1, [4,4]);
  [[xTE-0.04, -sigP, "#7c3aed"],
   [xTE+0.04,  sigP, "#7c3aed"],
   [xH -0.05, -sigP*0.75, "#f97316"],
   [xH +0.06,  qIfc, "#ef4444"]].forEach(a => {
    line(g, ax3.X(a[0]), ax3.Y(0), ax3.X(a[0]), ax3.Y(a[1]), a[2], 3);
    circ(g, ax3.X(a[0]), ax3.Y(a[1]), 3, a[2]);
  });
  txt(g,"σ_P = ±"+sigP.toFixed(1)+" µC/cm²", ax3.X(xTE)+18, ax3.Y(sigP)+12, "#7c3aed","12px sans-serif");
  txt(g,"interface q ≈ "+qIfc.toFixed(2), ax3.X(xH)+12, ax3.Y(qIfc)-8, "#ef4444","11px sans-serif");
  if(mfsBE && Wdep>0.05 && split2.regime==="depletion"){
    // ionized acceptor sheet charge  σ_dep = q·N_A·W   [µC/cm²]
    const sigDep = Q * m.Na * (Wdep*1e-7) * 1e6;   // C/cm² → µC/cm²
    const yBox = ax3.Y(-cl(0.25 + 0.5*Math.min(1, sigDep/5), 0.25, 1.15));
    fill(g, ax3.X(xD), ax3.Y(0), ax3.X(Wend)-ax3.X(xD), yBox-ax3.Y(0), "rgba(220,38,38,.30)", "#b91c1c");
    txt(g,"−qN_A·W = "+sigDep.toFixed(1)+" µC/cm² (ionized acceptors)",
        ax3.X(xD)+4, yBox+13, "#b91c1c","bold 10px sans-serif","left");
  }
}

// ============================================================
//  DRAW: 3) I-V with components
// ============================================================
function drawIV(){
  const {g,w,h} = canvasCtx(E.iv);
  const m = model();
  const arr = ivData();
  g.clearRect(0,0,w,h);
  fill(g,0,0,w,h,"#fff");

  // Build y-range from synthetic + imported data
  const vals = [];
  arr.forEach(d => {
    [d.on.Jtot, d.off.Jtot, d.on.Jdt, d.on.Jfn, d.on.Jpf, d.on.Jsch, d.on.Johm, d.on.Jtat]
      .forEach(v => vals.push(safeLog10(Math.abs(v))));
  });
  const data = getFitInput();
  data.forEach(p => vals.push(safeLog10(Math.abs(p.J))));
  let ymin = Math.max(-22, Math.min(...vals)-0.5);
  let ymax = Math.min(8,   Math.max(...vals)+0.5);
  if(!Number.isFinite(ymin) || !Number.isFinite(ymax) || ymin>=ymax){ ymin=-12; ymax=2; }

  const ax = axes(g, 70, 36, w-100, h-76,
    {xmin:-S.Vmax, xmax:S.Vmax, ymin, ymax,
     xticks:8, yticks:6, xlabel:"Voltage (V)", ylabel:"log10 |J| (A/cm²)"});

  function plot(keyFn, col, lw, dash){
    g.save(); g.strokeStyle=col; g.lineWidth=lw; g.setLineDash(dash||[]);
    g.beginPath();
    arr.forEach((d,i) => {
      const y = safeLog10(Math.abs(keyFn(d)));
      if(i) g.lineTo(ax.X(d.V), ax.Y(y));
      else  g.moveTo(ax.X(d.V), ax.Y(y));
    });
    g.stroke(); g.restore();
  }
  plot(d => d.on.Jtot,  "#dc2626", 2.6);
  plot(d => d.off.Jtot, "#2563eb", 2.4);
  plot(d => d.on.Jdt,   "#f59e0b", 1.5, [5,4]);
  plot(d => d.on.Jfn,   "#7c3aed", 1.5, [5,4]);
  plot(d => d.on.Jpf,   "#db2777", 1.5, [5,4]);
  plot(d => d.on.Jsch,  "#0891b2", 1.5, [5,4]);
  plot(d => d.on.Johm,  "#16a34a", 1.5, [5,4]);
  plot(d => d.on.Jtat,  "#475569", 1.5, [2,3]);
  data.forEach(p => circ(g, ax.X(p.V), ax.Y(safeLog10(Math.abs(p.J))), 2.3, "#111827"));

  // Legend
  const labs = [
    ["ON total","#dc2626"], ["OFF total","#2563eb"],
    ["DT","#f59e0b"], ["FN","#7c3aed"], ["PF","#db2777"],
    ["Schottky","#0891b2"], ["Ohmic","#16a34a"], ["TAT","#475569"],
    ["CSV","#111827"]
  ];
  fill(g, 84, 48, 166, 142, "rgba(255,255,255,.92)", "#cbd5e1");
  labs.forEach((l,i) => {
    if(i===8) circ(g, 96, 64+i*15, 3, l[1]);
    else line(g, 88, 64+i*15, 112, 64+i*15, l[1], i<2 ? 2.4 : 1.6, i<2 ? [] : [5,4]);
    txt(g, l[0], 120, 64+i*15, "#111827", "11px sans-serif", "left", "middle");
  });
  txt(g, DATA.length ? `Imported data: ${DATA.length} pts` : "Synthetic model only",
    w-24, 27, "#334155", "bold 12px sans-serif", "right");
}

// ============================================================
//  DRAW: 3b) Polarity 4-grid (ON±/OFF± mini I-V)
// ============================================================
function drawPolarityGrid(){
  drawPolarityCell(E.polPos, +1);  // positive bias
  drawPolarityCell(E.polNeg, -1);  // negative bias
  // Compute window asymmetry note
  const m = model();
  const Vr = Math.abs(S.readV);
  const onP  = componentsAt(+Vr,  1).Jtot;
  const offP = componentsAt(+Vr, -1).Jtot;
  const onN  = componentsAt(-Vr,  1).Jtot;
  const offN = componentsAt(-Vr, -1).Jtot;
  const winP = Math.abs(onP)/Math.max(Math.abs(offP), 1e-30);
  const winN = Math.abs(onN)/Math.max(Math.abs(offN), 1e-30);
  const asym = Math.max(winP,winN)/Math.max(Math.min(winP,winN),1e-12);
  let symPill, advice;
  if(asym < 1.5){
    symPill = `<span class="pill good">대칭 OK (asym×${asym.toFixed(2)})</span>`;
    advice = "+/− 양 polarity에서 비슷한 read window. set/reset도 비슷하게 동작 예상.";
  } else if(asym < 4){
    symPill = `<span class="pill warn">약한 비대칭 (asym×${asym.toFixed(2)})</span>`;
    advice = "Mo/TiN work-function 차이 + BIL voltage drop으로 보통 수준의 비대칭. polarity 분리 fit 필수.";
  } else {
    symPill = `<span class="pill bad">강한 비대칭 (asym×${asym.toFixed(2)})</span>`;
    advice = "한 쪽 polarity가 압도적으로 우세. 한 방향 electrode-limited (Schottky) 또는 dead layer 의심. ON+/ON−/OFF+/OFF− 4개 따로 측정·fit.";
  }
  E.polNote.innerHTML =
    `read |V| = ${Vr.toFixed(2)} V → win+ = ${winP.toExponential(1)}, win− = ${winN.toExponential(1)} ${symPill}<br><span style="color:#475569">${advice}</span>`;
}

function drawPolarityCell(canvasEl, sign){
  const {g,w,h} = canvasCtx(canvasEl);
  g.clearRect(0,0,w,h);
  fill(g,0,0,w,h,"#fff");
  // Sweep |V| from 0 to Vmax
  const n = 80;
  const Vmax = S.Vmax;
  const ptsOn = [], ptsOff = [];
  for(let i=1; i<=n; i++){
    const Vabs = Vmax*i/n;
    const V = sign*Vabs;
    const on  = componentsAt(V,  1).Jtot;
    const off = componentsAt(V, -1).Jtot;
    ptsOn.push({V:Vabs, J:Math.abs(on)});
    ptsOff.push({V:Vabs, J:Math.abs(off)});
  }
  // Imported CSV - filter by sign
  const csvPts = DATA.filter(p => sign>0 ? p.V > 0.05 : p.V < -0.05)
                     .map(p => ({V:Math.abs(p.V), J:Math.abs(p.J)}));

  const allJ = ptsOn.concat(ptsOff,csvPts).map(p => safeLog10(p.J));
  let ymin = Math.max(-22, Math.min(...allJ)-0.5);
  let ymax = Math.min(8, Math.max(...allJ)+0.5);
  if(!Number.isFinite(ymin)||!Number.isFinite(ymax)||ymin>=ymax){ ymin=-12; ymax=2; }

  const ax = axes(g, 50, 12, w-66, h-44,
    {xmin:0, xmax:Vmax, ymin, ymax, xticks:4, yticks:4,
     xlabel:"|V| (V)", ylabel:"log|J|"});

  function plotPts(pts, col, lw, dash){
    g.save(); g.strokeStyle=col; g.lineWidth=lw; g.setLineDash(dash||[]);
    g.beginPath();
    pts.forEach((p,i) => {
      const x = ax.X(p.V), y = ax.Y(safeLog10(p.J));
      if(i) g.lineTo(x,y); else g.moveTo(x,y);
    });
    g.stroke(); g.restore();
  }
  plotPts(ptsOn,  "#dc2626", 2.2);
  plotPts(ptsOff, "#2563eb", 2.0);
  csvPts.forEach(p => circ(g, ax.X(p.V), ax.Y(safeLog10(p.J)), 1.8, "#94a3b8"));

  // Annotate read voltage marker
  const Vr = Math.abs(S.readV);
  if(Vr <= Vmax){
    line(g, ax.X(Vr), ax.y, ax.X(Vr), ax.y+ax.h, "#f59e0b", 1.2, [4,3]);
    txt(g, "V_read", ax.X(Vr)+3, ax.y+8, "#b45309", "bold 10px sans-serif", "left");
  }
}

// ============================================================
//  DRAW: 4) Mechanism fit matrix
// ============================================================
function drawFitBar(fit){
  const {g,w,h} = canvasCtx(E.fitBar);
  g.clearRect(0,0,w,h);
  fill(g,0,0,w,h,"#fff");
  const rows = fit.fits.slice().reverse();
  const ax = axes(g, 110, 38, w-140, h-78,
    {xmin:0, xmax:1, ymin:0, ymax:rows.length,
     xticks:5, yticks:rows.length, xlabel:"Mechanism score (R² with penalties)", ylabel:""});
  rows.forEach((r,i) => {
    const y = ax.Y(i+0.5), x0 = ax.X(0), x1 = ax.X(r.score);
    const col = (r.name===fit.best.name) ? "#16a34a" : "#2563eb";
    fill(g, x0, y-10, x1-x0, 20, col);
    txt(g, r.name, x0-8, y, "#111827", "11px sans-serif", "right", "middle");
    txt(g, `${r.score.toFixed(2)} / R² ${r.r2.toFixed(2)}`,
      Math.min(x1+6, ax.X(0.98)), y, "#111827", "bold 11px sans-serif", "left", "middle");
  });
  txt(g, `winner: ${fit.best.name}`, 20, 24, "#111827", "bold 14px sans-serif");
}

// ============================================================
//  DRAW: 5) F-N plot — honest fit
// ============================================================
function drawFNPlot(fit){
  const {g,w,h} = canvasCtx(E.fnPlot);
  g.clearRect(0,0,w,h);
  fill(g,0,0,w,h,"#fff");
  const m = model();
  const pts = fit.pts;
  const high = pts.filter(p =>
    Math.abs(p.V) > Math.max(0.45, 0.55*S.Vmax) && Math.abs(p.J) > 1e-300);
  const data = high.map(p => ({
    x: 1/p.Ecm, y: Math.log(Math.abs(p.J)/(p.Ecm*p.Ecm))
  })).filter(p => Number.isFinite(p.x) && Number.isFinite(p.y));

  if(data.length < 3){
    txt(g, "Need more high-field points for honest F-N fit",
      w/2, h/2, "#b91c1c", "bold 14px sans-serif", "center");
    return;
  }

  const xs = data.map(p=>p.x), ys = data.map(p=>p.y);
  const xmin = Math.min(...xs), xmax = Math.max(...xs);
  const ymin = Math.min(...ys)-0.4, ymax = Math.max(...ys)+0.4;

  const ax = axes(g, 76, 36, w-104, h-76,
    {xmin, xmax, ymin, ymax, xticks:5, yticks:5,
     xlabel:"1/E (cm/V)", ylabel:"ln(J / E²)"});

  data.forEach(p => circ(g, ax.X(p.x), ax.Y(p.y), 2.5, "#7c3aed"));

  const fn = fit.fits.find(r => r.name==="Fowler-Nordheim");
  const y1 = fn.slope*xmin + fn.intercept;
  const y2 = fn.slope*xmax + fn.intercept;
  line(g, ax.X(xmin), ax.Y(y1), ax.X(xmax), ax.Y(y2), "#16a34a", 2.5);

  const hdr = `slope ${Number.isFinite(fn.slope)?fn.slope.toExponential(2):"—"}` +
              ` | R² ${fn.r2.toFixed(3)}` +
              ` | φ ${Number.isFinite(fn.phi)?fn.phi.toFixed(2):"—"} eV`;
  txt(g, hdr, 20, 24, "#111827", "bold 13px sans-serif");

  const credible = fn.r2 > 0.97;
  const partial  = fn.r2 > 0.90;
  const verdict = credible ? "F-N fit credible" :
                  partial  ? "marginal — check direct/leak mix" :
                             "mixed conduction — F-N φ NOT reliable";
  txt(g, verdict, w-20, 24,
    credible ? "#15803d" : partial ? "#b45309" : "#b91c1c",
    "bold 12px sans-serif", "right");
  txt(g, "(no self-referential extraction — fit slope is independent of model φ)",
    20, h-12, "#475569", "11px sans-serif");
}

// ============================================================
//  DRAW: 6) Multi-Read overlay
// ============================================================
function drawMultiRead(){
  const {g,w,h} = canvasCtx(E.multiRead);
  g.clearRect(0,0,w,h);
  fill(g,0,0,w,h,"#fff");
  const m = model();
  const Vs = [S.rA, S.rB, S.rC, S.rD].slice().sort((a,b)=>a-b);
  const rows = Vs.map(V => readMetrics(V, m));
  // 3 metrics: window (=ratio), disturb, BER  → bar groups
  const halfW = (w-120)/2, leftX = 56, rightX = leftX + halfW + 28;
  const maxW = Math.max(2, ...rows.map(r => r.ratio)) * 1.15;
  const axL = axes(g, leftX, 42, halfW-10, h-110,
    {xmin:0, xmax:rows.length, ymin:1, ymax:maxW,
     xticks:rows.length, yticks:5, xlabel:"Read V (V)", ylabel:"Window  G_ON / G_OFF"});
  rows.forEach((r,i) => {
    const x1 = axL.X(i+0.18), x2 = axL.X(i+0.82);
    const y0 = axL.Y(1),       y1 = axL.Y(r.ratio);
    fill(g, x1, y1, x2-x1, y0-y1, "#2563eb", "#1d4ed8");
    txt(g, r.ratio.toFixed(1)+"×", (x1+x2)/2, y1-6, "#1d4ed8","bold 11px sans-serif","center");
    txt(g, r.V.toFixed(2),         (x1+x2)/2, axL.Y(1)+15, "#334155","11px sans-serif","center");
  });
  txt(g, "Memory window per read V", leftX, 30, "#1d4ed8","bold 13px sans-serif");

  const maxD = Math.max(0.5, ...rows.map(r => r.disturb)) * 1.2;
  const axR = axes(g, rightX, 42, halfW-10, h-110,
    {xmin:0, xmax:rows.length, ymin:0, ymax:maxD,
     xticks:rows.length, yticks:5, xlabel:"Read V (V)", ylabel:"Disturb (with BER)"});
  rows.forEach((r,i) => {
    const x1 = axR.X(i+0.18), x2 = axR.X(i+0.82);
    const y0 = axR.Y(0),      y1 = axR.Y(r.disturb);
    const col = r.disturb > 0.4 ? "#dc2626" : r.disturb > 0.2 ? "#f59e0b" : "#16a34a";
    fill(g, x1, y1, x2-x1, y0-y1, col);
    txt(g, r.disturb.toFixed(2), (x1+x2)/2, y1-6, col,"bold 11px sans-serif","center");
    txt(g, r.V.toFixed(2),       (x1+x2)/2, axR.Y(0)+15, "#334155","11px sans-serif","center");
    txt(g, "BER "+(r.ber<1e-6 ? r.ber.toExponential(1) : r.ber.toFixed(3)),
      (x1+x2)/2, axR.Y(0)+30, "#475569","10px sans-serif","center");
  });
  txt(g, "Read disturb + BER per V", rightX, 30, "#b45309","bold 13px sans-serif");

  const best = rows.reduce((a,b) => a.score > b.score ? a : b);
  txt(g, `recommended: ${best.V.toFixed(2)} V  (window×SNR best, BER ${best.ber<1e-6?best.ber.toExponential(1):best.ber.toFixed(3)})`,
    w/2, h-14, "#0f172a", "bold 12px sans-serif", "center");
}

// ============================================================
//  DRAW: 7) Transport regime map
// ============================================================
function drawRegime(){
  const {g,w,h} = canvasCtx(E.regime);
  g.clearRect(0,0,w,h);
  fill(g,0,0,w,h,"#fff");
  const m = model();
  const ax = axes(g, 70, 36, w-100, h-76,
    {xmin:0, xmax:S.Vmax, ymin:-22, ymax:2, xticks:6, yticks:6,
     xlabel:"|V| (V)", ylabel:"log10 |J| (A/cm²)"});

  // Regime shading
  const v1 = Math.min(0.3, S.Vmax);
  const v2 = Math.min(1.4, S.Vmax);
  fill(g, ax.X(0),  36, ax.X(v1)-ax.X(0),  h-76, "rgba(34,197,94,.10)");
  fill(g, ax.X(v1), 36, ax.X(v2)-ax.X(v1), h-76, "rgba(245,158,11,.10)");
  fill(g, ax.X(v2), 36, ax.X(S.Vmax)-ax.X(v2), h-76, "rgba(220,38,38,.10)");
  txt(g, "Ohmic", ax.X(v1*0.5), 50, "#15803d", "bold 11px sans-serif", "center");
  txt(g, "Direct",ax.X((v1+v2)/2), 50, "#b45309", "bold 11px sans-serif", "center");
  txt(g, "F-N",   ax.X((v2+S.Vmax)/2), 50, "#b91c1c", "bold 11px sans-serif", "center");

  const data = [];
  for(let i=1; i<=260; i++){
    const V = S.Vmax*i/260;
    const on  = componentsAt(V,  1);
    const off = componentsAt(V, -1);
    data.push({
      V,
      onTot:  safeLog10(Math.abs(on.Jtot)),
      offTot: safeLog10(Math.abs(off.Jtot)),
      ohm:    safeLog10(Math.abs(on.Johm)),
      fn:     safeLog10(Math.abs(on.Jfn)),
      dt:     safeLog10(Math.abs(on.Jdt)),
      pf:     safeLog10(Math.abs(on.Jpf)),
      sch:    safeLog10(Math.abs(on.Jsch))
    });
  }
  function plot(key, col, lw, dash){
    g.save(); g.strokeStyle=col; g.lineWidth=lw; if(dash) g.setLineDash(dash);
    g.beginPath();
    data.forEach((d,i) => {
      if(i) g.lineTo(ax.X(d.V), ax.Y(d[key]));
      else  g.moveTo(ax.X(d.V), ax.Y(d[key]));
    });
    g.stroke(); g.restore();
  }
  plot("onTot",  "#dc2626", 2.5);
  plot("offTot", "#2563eb", 2.5);
  plot("dt",     "#f59e0b", 1.6, [5,4]);
  plot("fn",     "#7c3aed", 1.6, [5,4]);
  plot("ohm",    "#16a34a", 1.6, [5,4]);
  plot("pf",     "#db2777", 1.4, [3,3]);
  plot("sch",    "#0891b2", 1.4, [3,3]);

  // Legend
  fill(g, 84, 64, 196, 122, "rgba(255,255,255,.92)", "#cbd5e1");
  const labs = [
    ["ON total","#dc2626",false], ["OFF total","#2563eb",false],
    ["Direct","#f59e0b",true], ["F-N","#7c3aed",true],
    ["Ohmic","#16a34a",true], ["PF","#db2777",true], ["Schottky","#0891b2",true]
  ];
  labs.forEach((l,i) => {
    line(g, 94, 80+i*14, 118, 80+i*14, l[1], l[2] ? 1.6 : 2.5, l[2] ? [5,4] : []);
    txt(g, l[0], 124, 80+i*14, "#111827","11px sans-serif","left","middle");
  });

  if(m.Vc < S.Vmax){
    line(g, ax.X(m.Vc), 36, ax.X(m.Vc), h-40, "#0ea5e9", 1.6, [3,4]);
    txt(g, "Vc="+m.Vc.toFixed(2)+" V", ax.X(m.Vc), h-46, "#0284c7","bold 10px sans-serif","center");
  }
}

// ============================================================
//  DRAW: 8) PUND (leak-subtracted)
// ============================================================
function drawPUND(p){
  const {g,w,h} = canvasCtx(E.pund);
  g.clearRect(0,0,w,h);
  fill(g,0,0,w,h,"#fff");
  const total = 4*S.pulseW + 3*0.25*S.pulseW;
  const ax = axes(g, 50, 24, w-66, h-50,
    {xmin:0, xmax:total, ymin:-1.15, ymax:1.15,
     xticks:5, yticks:4, xlabel:"Time (µs)", ylabel:"Normalized I / V"});

  // Build P/U/N/D pulse shapes (trapezoidal V) and transient I response
  const seg = ["P","U","N","D"];
  let t0 = 0;
  const data = [];
  for(let s=0; s<4; s++){
    const start = t0, end = t0 + S.pulseW;
    const Vsign = (s<2 ? +1 : -1);                  // P,U positive ; N,D negative
    const isSwitch = (s===0 || s===2);              // P switches, U no; N switches, D no
    for(let k=0; k<=40; k++){
      const xi = k/40;
      // Trapezoidal V envelope: rise / hold / fall
      let Venv;
      if(xi < 0.18) Venv = xi/0.18;
      else if(xi > 0.82) Venv = (1-xi)/0.18;
      else Venv = 1;
      const V = Vsign * Venv;
      // Capacitive + leak baseline
      const baseI = Vsign * (0.10 + 0.20*S.leak) * Venv;
      // Switching peak — only on first crossing of each polarity (P and N)
      // Shaped as gaussian on rising edge
      const swPeak = isSwitch ? Vsign * p.sw * 0.85 *
                     Math.exp(-Math.pow((xi - 0.22)/0.10, 2)) : 0;
      data.push({t: start + (end-start)*xi, I: baseI + swPeak, V});
    }
    t0 = end + 0.25*S.pulseW;
  }

  // Voltage envelope (dashed blue) — drawn first so I sits on top
  g.save(); g.strokeStyle="#2563eb"; g.lineWidth=1.7; g.setLineDash([5,4]); g.beginPath();
  data.forEach((d,i) => {
    if(i) g.lineTo(ax.X(d.t), ax.Y(d.V*0.88));
    else  g.moveTo(ax.X(d.t), ax.Y(d.V*0.88));
  });
  g.stroke(); g.restore();

  // Current trace (black, solid)
  g.save(); g.strokeStyle="#111827"; g.lineWidth=2.4; g.beginPath();
  data.forEach((d,i) => {
    if(i) g.lineTo(ax.X(d.t), ax.Y(d.I));
    else  g.moveTo(ax.X(d.t), ax.Y(d.I));
  });
  g.stroke(); g.restore();

  // P/U/N/D segment labels
  let pos = 0;
  seg.forEach((s,i) => {
    txt(g, s, ax.X(pos+S.pulseW/2), 36,
        (s==="P"||s==="N") ? "#b91c1c" : "#94a3b8",
        "bold 13px sans-serif", "center");
    pos += S.pulseW + 0.25*S.pulseW;
  });
  // Legend
  txt(g, "— I", ax.X(total)-5, 36, "#111827","bold 11px sans-serif","right");
  txt(g, "-- V", ax.X(total)-5, 50, "#2563eb","bold 11px sans-serif","right");
}

// v11: Transient I-V hysteresis — same sweep, different x-axis (V instead of t)
function drawPUNDhyst(p){
  const {g,w,h} = canvasCtx(E.pundIV);
  g.clearRect(0,0,w,h);
  fill(g,0,0,w,h,"#fff");
  const Vmax = Math.max(Math.abs(S.pulseV), Math.abs(S.resetV), 1.5);
  const Iscale = p.sw * 0.85 + 0.30;
  const ax = axes(g, 50, 24, w-66, h-50,
    {xmin:-Vmax*1.05, xmax:Vmax*1.05, ymin:-Iscale*1.15, ymax:Iscale*1.15,
     xticks:5, yticks:4, xlabel:"V_app (V)", ylabel:"I (norm)"});

  // Generate triangular sweep: 0 → +Vmax → 0 → -Vmax → 0
  // Switching peak appears at +V_c on up-sweep and -V_c on down-sweep
  const Vc = Math.min(Vmax*0.55, S.pulseV*0.55);
  const N = 240;
  const sweep = [];
  for(let i=0; i<=N; i++){
    const phase = i/N * 4;        // 0..4 covers full triangle
    let V;
    if(phase < 1) V = Vmax * phase;
    else if(phase < 2) V = Vmax * (2 - phase);
    else if(phase < 3) V = -Vmax * (phase - 2);
    else V = -Vmax * (4 - phase);
    sweep.push({phase, V});
  }
  // Compute I along sweep — capacitive + leak + switching peak
  const data = sweep.map((s, idx) => {
    const dV = idx>0 ? s.V - sweep[idx-1].V : 0;
    const cap = 0.18 * Math.sign(dV) * Math.min(1, Math.abs(dV)*15);
    const leak = 0.12 * S.leak * s.V / Vmax;
    // Switching: gaussian peak when V crosses ±Vc on rising/falling edge
    let sw = 0;
    if(s.phase < 1 && s.V > Vc*0.6 && s.V < Vc*1.4){
      // up-sweep, positive switching
      sw = p.sw * 0.85 * Math.exp(-Math.pow((s.V - Vc)/(Vc*0.18), 2));
    } else if(s.phase >= 2 && s.phase < 3 && s.V < -Vc*0.6 && s.V > -Vc*1.4){
      // down-sweep into negative, negative switching
      sw = -p.sw * 0.85 * Math.exp(-Math.pow((s.V + Vc)/(Vc*0.18), 2));
    }
    return {V: s.V, I: cap + leak + sw, phase: s.phase};
  });

  // Plot up-sweep (red) and down-sweep (blue) separately
  g.save();
  g.strokeStyle = "#dc2626"; g.lineWidth = 2.0;
  g.beginPath();
  let started = false;
  data.forEach(d => {
    if(d.phase < 2){
      const X = ax.X(d.V), Y = ax.Y(d.I);
      if(!started){ g.moveTo(X,Y); started=true; } else g.lineTo(X,Y);
    }
  });
  g.stroke(); g.restore();

  g.save();
  g.strokeStyle = "#2563eb"; g.lineWidth = 2.0;
  g.beginPath();
  started = false;
  data.forEach(d => {
    if(d.phase >= 2){
      const X = ax.X(d.V), Y = ax.Y(d.I);
      if(!started){ g.moveTo(X,Y); started=true; } else g.lineTo(X,Y);
    }
  });
  g.stroke(); g.restore();

  // Mark switching peaks
  const peakUp = data.filter(d => d.phase<1).reduce((a,b) => Math.abs(b.I)>Math.abs(a.I)?b:a, {I:0,V:0});
  const peakDn = data.filter(d => d.phase>=2 && d.phase<3).reduce((a,b) => Math.abs(b.I)>Math.abs(a.I)?b:a, {I:0,V:0});
  if(Math.abs(peakUp.I) > 0.1){
    circ(g, ax.X(peakUp.V), ax.Y(peakUp.I), 4, "#dc2626");
    txt(g, "+V_c switching", ax.X(peakUp.V)+8, ax.Y(peakUp.I)-4,
        "#b91c1c","bold 10px sans-serif","left");
  }
  if(Math.abs(peakDn.I) > 0.1){
    circ(g, ax.X(peakDn.V), ax.Y(peakDn.I), 4, "#2563eb");
    txt(g, "−V_c switching", ax.X(peakDn.V)-8, ax.Y(peakDn.I)+12,
        "#1d4ed8","bold 10px sans-serif","right");
  }
  // Legend
  txt(g, "— up-sweep", ax.x+8, ax.y+12, "#dc2626","bold 10px sans-serif","left");
  txt(g, "— down-sweep", ax.x+8, ax.y+24, "#2563eb","bold 10px sans-serif","left");

  // Note below
  const leakFrac = p.qLeakPc / Math.max(p.qMeasPc, 1e-12);
  let pill;
  if(p.sw > 0.4 && leakFrac < 0.3){
    pill = `<span class="pill good">switching peak 명확, Q<sub>leak</sub>/Q<sub>sw</sub>=${(leakFrac*100).toFixed(0)}%</span>`;
  } else if(p.sw > 0.2){
    pill = `<span class="pill warn">switching 약함 또는 leak 큼 (${(leakFrac*100).toFixed(0)}%)</span>`;
  } else {
    pill = `<span class="pill bad">switching peak 미약 — partial switch / depinning fail / fatigue 의심</span>`;
  }
  E.pundNote.innerHTML =
    `Qsw = ${p.qswPc.toFixed(2)} pC | Qleak = ${p.qLeakPc.toFixed(2)} pC | switch index = ${p.sw.toFixed(2)} ${pill}<br>` +
    `<span style="color:#475569">+V_c와 −V_c 부근에서 sharp peak가 보이면 ferroelectric switching의 직접 증거. peak 사이 면적 = hysteresis loop = Q<sub>sw</sub>.</span>`;
}

// ============================================================
//  DRAW: 9) Reliability budget
// ============================================================
function drawReliability(r){
  const {g,w,h} = canvasCtx(E.reliability);
  g.clearRect(0,0,w,h);
  fill(g,0,0,w,h,"#fff");
  const ax = axes(g, 70, 36, w-100, h-82,
    {xmin:0, xmax:7, ymin:0, ymax:1.05,
     xticks:7, yticks:5, xlabel:"log10(time s / cycles N / reads)", ylabel:"Normalized window"});

  const ratio0 = Math.log10(Math.max(r.read.ratio, 1.01));
  // Retention
  g.save(); g.strokeStyle="#7c3aed"; g.lineWidth=2.5; g.beginPath();
  for(let i=0; i<=180; i++){
    const lx = 7*i/180, t = Math.pow(10,lx);
    const rr = 1 + (r.read.ratio-1)*Math.exp(-Math.pow(t/r.tau, 0.62));
    const y = Math.log10(rr) / Math.max(ratio0, 1e-6);
    if(i) g.lineTo(ax.X(lx), ax.Y(cl(y,0,1.05)));
    else  g.moveTo(ax.X(lx), ax.Y(cl(y,0,1.05)));
  }
  g.stroke(); g.restore();

  // Fatigue (cycles)
  g.save(); g.strokeStyle="#f59e0b"; g.lineWidth=2.4; g.beginPath();
  for(let i=0; i<=180; i++){
    const lx = 7*i/180, N = Math.pow(10,lx);
    const loss = 1 - Math.exp(-Math.pow(N/r.n0, 0.55));
    const y = cl(1 - 0.72*loss, 0, 1);
    if(i) g.lineTo(ax.X(lx), ax.Y(y));
    else  g.moveTo(ax.X(lx), ax.Y(y));
  }
  g.stroke(); g.restore();

  // Read-disturb cumulative
  g.save(); g.strokeStyle="#dc2626"; g.lineWidth=2.4; g.setLineDash([5,4]); g.beginPath();
  for(let i=0; i<=180; i++){
    const lx = 7*i/180, N = Math.pow(10,lx);
    const rd = 1 - Math.exp(-r.read.disturb*N/2.5e6);
    const y = cl(1 - rd, 0, 1);
    if(i) g.lineTo(ax.X(lx), ax.Y(y));
    else  g.moveTo(ax.X(lx), ax.Y(y));
  }
  g.stroke(); g.restore();

  // Legend
  fill(g, 88, 52, 156, 62, "rgba(255,255,255,.92)", "#cbd5e1");
  const labs = [["retention","#7c3aed",[]],["fatigue","#f59e0b",[]],["read disturb","#dc2626",[5,4]]];
  labs.forEach((l,i) => {
    line(g, 98, 68+i*17, 122, 68+i*17, l[1], 2, l[2]);
    txt(g, l[0], 130, 68+i*17, "#111827","11px sans-serif","left","middle");
  });
  txt(g,
    `τ ${tauFmt(r.tau)} | N₀ ${sci(r.n0)} | retention target ratio ${r.rGoal.toFixed(2)}× @ ${tauFmt(S.retentionGoal)}`,
    w/2, h-18, "#111827", "bold 12px sans-serif", "center");
}

// ============================================================
//  DRAW: 10) 32-state LTP/LTD with seeded noise
// ============================================================
function drawStates(sn){
  const {g,w,h} = canvasCtx(E.states);
  g.clearRect(0,0,w,h);
  fill(g,0,0,w,h,"#fff");
  const n = sn.n;
  // Ideal target levels
  const ax = axes(g, 64, 38, w-94, h-82,
    {xmin:0, xmax:n*2, ymin:sn.gmin-0.3, ymax:sn.gmax+0.3,
     xticks:8, yticks:5, xlabel:"Pulse index", ylabel:"ln(G)"});

  for(let i=0; i<n; i++){
    const lvl = sn.gmin + sn.step*i;
    line(g, ax.X(0), ax.Y(lvl), ax.X(2*n), ax.Y(lvl), "#e2e8f0", 1);
  }

  const pts = [];
  // LTP — saturating exponential up
  for(let i=0; i<=n; i++){
    const x = i/n;
    const ideal = sn.gmin + sn.span*(1 - Math.exp(-2.4*x))/(1 - Math.exp(-2.4));
    const y = ideal + seedNoise(i+100, 1)*sn.sigma;
    pts.push({x:i, y, type:"ltp"});
  }
  // LTD — saturating exponential down
  for(let i=0; i<=n; i++){
    const x = i/n;
    const ideal = sn.gmax - sn.span*(1 - Math.exp(-2.2*x))/(1 - Math.exp(-2.2));
    const y = ideal + seedNoise(i+300, 2)*sn.sigma;
    pts.push({x:n+i, y, type:"ltd"});
  }
  function drawType(type, col){
    const a = pts.filter(p => p.type===type);
    g.save(); g.strokeStyle=col; g.lineWidth=2.2; g.beginPath();
    a.forEach((p,i) => {
      if(i) g.lineTo(ax.X(p.x), ax.Y(p.y));
      else  g.moveTo(ax.X(p.x), ax.Y(p.y));
    });
    g.stroke(); g.restore();
    a.forEach(p => circ(g, ax.X(p.x), ax.Y(p.y), 2.2, col));
  }
  drawType("ltp", "#dc2626");
  drawType("ltd", "#2563eb");

  txt(g,"LTP", 70, 30, "#b91c1c","bold 12px sans-serif");
  txt(g,"LTD", w-90, 30, "#1d4ed8","bold 12px sans-serif");
  const verdict = sn.usable < n*0.5 ? "#b91c1c" : sn.usable < n*0.7 ? "#b45309" : "#15803d";
  txt(g,
    `step/σ ${sn.sep.toFixed(2)} | usable ${sn.usable}/${n} | BER ${sn.ber<1e-6?sn.ber.toExponential(1):sn.ber.toFixed(3)} | σ ${sn.sigma.toFixed(3)}`,
    w/2, h-18, verdict, "bold 12px sans-serif", "center");
}

// ============================================================
//  RENDER orchestration
// ============================================================
function render(){
  const m    = model();
  const fit  = fitMechanisms();
  const scan = scanRead(m);
  const pund = pundMetrics(m);
  const ret  = retentionMetrics(m);
  const sn   = stateMetrics(m);
  const risk = gradeRisk(m, scan, sn, fit, pund, ret);
  lastReport = {m, fit, scan, pund, ret, sn, risk};

  // KPIs
  const readNow = readMetrics(S.readV, m);
  E.kVapp.textContent = fmt(S.Vapp,2)+" V";
  E.kVappS.textContent = "V_TE − V_BE";
  E.kRatio.textContent = readNow.ratio.toFixed(1)+"×";
  E.kRatioS.textContent = `@ ${S.readV.toFixed(2)} V, dist ${readNow.disturb.toFixed(2)}`;
  E.kBestRead.textContent = scan.best.V.toFixed(2)+" V";
  E.kBestReadS.textContent = `score ${scan.best.score.toFixed(1)}, BER ${scan.best.ber<1e-6?scan.best.ber.toExponential(1):scan.best.ber.toFixed(3)}`;
  E.kMech.textContent = fit.best.name.split("/")[0];
  E.kMechS.textContent = `score ${fit.best.score.toFixed(2)}, R² ${fit.best.r2.toFixed(2)}`;
  const fn = fit.fits.find(f => f.name==="Fowler-Nordheim");
  if(Number.isFinite(fn.phi)){
    E.kPhi.innerHTML = fn.phi.toFixed(2)+" eV<span class='apparent'>apparent</span>";
  } else {
    E.kPhi.textContent = "—";
  }
  E.kPhiS.textContent = `R² ${fn.r2.toFixed(3)} ${fn.r2>0.97?"(credible)":fn.r2>0.90?"(marginal)":"(unreliable)"}`;
  E.kQsw.textContent = pund.qswPc.toFixed(2)+" pC";
  E.kQswS.textContent = `leak ${(pund.qLeakPc/Math.max(pund.qMeasPc,1e-12)*100).toFixed(0)}%`;
  E.kStates.textContent = `${sn.usable}/${sn.n}`;
  E.kStatesS.textContent = `step/σ ${sn.sep.toFixed(2)}`;
  E.kRisk.textContent = risk.toFixed(0);
  E.kRiskS.textContent = risk>65 ? "high caution" : risk>35 ? "watch" : "ok";

  drawBand();
  drawProfile();
  drawIV();
  drawPolarityGrid();
  drawFitBar(fit);
  drawFNPlot(fit);
  drawMultiRead();
  drawRegime();
  drawPUND(pund);
  drawPUNDhyst(pund);
  drawReliability(ret);
  drawStates(sn);
  updateNotes();
  E.stamp.textContent = `preset: ${S.preset} | ${DATA.length ? DATA.length+" CSV pts" : "synthetic"} | T=${S.temp} K, A=${S.area} µm²`;
}

// ============================================================
//  Notes & fit table
// ============================================================
function updateNotes(){
  const {fit, m, scan, pund, ret, sn, risk} = lastReport;
  const rowsHtml = fit.fits.map(r =>
    `<tr><td>${r.name}</td><td>${r.n}</td>` +
    `<td>${Number.isFinite(r.slope) ? r.slope.toExponential(2) : "—"}</td>` +
    `<td>${r.r2.toFixed(3)}</td>` +
    `<td>${r.score.toFixed(3)}</td>` +
    `<td>${Number.isFinite(r.phi) ? r.phi.toFixed(2)+" eV<span class='apparent'>apparent</span>" : ""}</td></tr>`
  ).join("");
  E.fitTable.innerHTML =
    `<table><thead><tr>` +
    `<th>mechanism</th><th>n</th><th>slope</th><th>R²</th><th>score</th><th>extract</th>` +
    `</tr></thead><tbody>${rowsHtml}</tbody></table>`;

  const fn = fit.fits.find(f => f.name==="Fowler-Nordheim");
  const warns = [];
  if(fn.r2 < 0.95) warns.push(["warn","F-N plot이 충분히 선형이 아니다. φ 추정값은 component-mixed apparent barrier로 봐야 한다."]);
  if(pund.qLeakPc > pund.qswPc*0.35) warns.push(["bad","PUND leakage fraction이 크다. (P−U)−(N−D) subtraction, shorter pulse, lower amplitude를 먼저 검토."]);
  if(scan.best.V > m.Vc*0.55) warns.push(["warn","best read가 Vc에 너무 가깝다. 반복 read-disturb를 별도 측정해야 한다."]);
  if(sn.usable < sn.n) warns.push([sn.usable < sn.n*0.5 ? "bad" : "warn",
    `32-state 목표 대비 usable ${sn.usable}/${sn.n}. read V·pulse amplitude·noise 재조정 필요.`]);
  if(ret.rGoal < Math.sqrt(ret.read.ratio)) warns.push(["warn","retention target에서 window가 √(현재 window) 미만. depolarization/screening 의심."]);
  if(risk < 30) warns.push(["good","현재 setup은 quick screening 기준 안정권. 단, 수치는 imported CSV fit으로 확정."]);
  // ===== v13: MFS-specific guidance =====
  if(m.mfs){
    const sp = voltageSplit(S.Vapp, +1, m);
    warns.push(["warn",
      `MFS 구조: 반도체 표면이 ${sp.regime} (W≈${sp.W.toFixed(2)} nm). `+
      `Vapp의 ${(Math.abs(sp.Vsc)/Math.max(Math.abs(S.Vapp),1e-3)*100).toFixed(0)}%가 반도체 공핍층에서 소모됨 → HZO 실효 전계 감소.`]);
    warns.push(["bad",
      `Native-oxide / Dit: HZO를 InGaAs에 직접 ALD하면 계면 trap·자연산화막으로 FE 죽거나 TAT·breakdown 우선 발생. `+
      `1nm 미만 고품질 dead layer(Al₂O₃/TiOₓ)가 현실적으로 필수 — tDead 슬라이더로 영향 확인.`]);
    warns.push(["warn",
      `Write-V penalty ×${m.writePenalty.toFixed(2)}: 같은 HZO를 MFM 대비 더 큰 Vapp로 써야 항전계 도달. `+
      `λ_TF=${m.lambdaTF.toFixed(2)} nm (금속≈0.05) → screening 실패로 E_dep 잔존(+${m.depolBoost.toFixed(2)} MV/cm).`]);
  }
  const pillsHtml = warns.map(w => `<span class="pill ${w[0]}">${w[1]}</span>`).join("");

  const recs = [];
  recs.push(`Read 추천: ${scan.best.V.toFixed(2)} V. 현재 read ${S.readV.toFixed(2)} V와 다르면 Auto-read 버튼.`);
  recs.push(`F-N fit 영역: |V| > ${Math.max(0.45, 0.55*S.Vmax).toFixed(2)} V (n=${fn.n}, R²=${fn.r2.toFixed(3)}).`);
  recs.push(`PUND: Qsw=${pund.qswPc.toFixed(2)} pC, leak=${pund.qLeakPc.toFixed(2)} pC. 보고용은 (P−U)−(N−D) subtraction 후 ΔQ.`);
  recs.push(`Reliability: τ ≈ ${tauFmt(ret.tau)}, fatigue N₀ ≈ ${sci(ret.n0)} cycles, read-disturb cumulative ≈ ${(ret.readDisturb*100).toFixed(1)}% @ N=${sci(S.enduranceN)}.`);
  E.notes.innerHTML =
    `<div>${pillsHtml}</div>` +
    `<p><b>Action plan:</b> ${recs.join(" ")}</p>` +
    `<p><b>Data mode:</b> ${DATA.length ? `imported CSV (${DATA.length} pts) being fitted` : "synthetic model only"}. ` +
    `보고/논문에는 synthetic 결과를 numeric parameter로 인용하지 말고 imported CSV fit 결과만 인용.</p>`;
}

// ============================================================
//  CSV / SAMPLE
// ============================================================
function parseData(){
  const txt = E.csvIn.value.trim();
  if(!txt){
    DATA = [];
    E.dataStatus.textContent = "No external data. Synthetic curve is being used.";
    render();
    return;
  }
  const rows = [];
  const m = model();
  txt.split(/\n+/).forEach(line => {
    const clean = line.replace(/#.*/,"").trim();
    if(!clean) return;
    const nums = clean.match(/[+-]?(?:\d+\.?\d*|\.\d+)(?:[eE][+-]?\d+)?/g);
    if(nums && nums.length >= 2){
      const V = Number(nums[0]), y = Number(nums[1]);
      if(Number.isFinite(V) && Number.isFinite(y)){
        const I = E.dataUnit.value==="J" ? y*m.areaCm2 : y;
        rows.push({V, I, J: I/m.areaCm2});
      }
    }
  });
  DATA = rows;
  E.dataStatus.textContent = rows.length ?
    `${rows.length} data points loaded. unit=${E.dataUnit.value}.` :
    "No numeric V,I rows detected.";
  render();
}
function loadSample(){
  const pts = syntheticData(true);
  E.csvIn.value = "V,I\n" + pts.map(p => `${p.V.toFixed(4)},${p.I.toExponential(6)}`).join("\n");
  E.dataUnit.value = "I";
  parseData();
}

// ============================================================
//  EXPORT / IMPORT
// ============================================================
function exportConfig(){
  const blob = new Blob([JSON.stringify(S,null,2)], {type:"application/json"});
  download(blob, "ftj_lab_v8_config.json");
}
function importConfig(ev){
  const file = ev.target.files[0];
  if(!file) return;
  const r = new FileReader();
  r.onload = () => {
    try{
      const obj = JSON.parse(r.result);
      Object.assign(S, obj);
      syncAll();
      render();
    } catch(e){ alert("JSON import failed: "+e.message); }
  };
  r.readAsText(file);
}
function exportReport(){
  const {fit, scan, pund, ret, sn, risk, m} = lastReport;
  const fn = fit.fits.find(f => f.name==="Fowler-Nordheim");
  const lines = [
    "item,value,unit,comment",
    `preset,${S.preset},,`,
    `te,${S.te},,`, `be,${S.be},,`,
    `area,${S.area},um2,`, `temp,${S.temp},K,`,
    `hzoT,${S.hzoT},nm,`, `bilT,${S.bilT},nm,`,
    `hzoPhi,${S.hzoPhi},eV,`, `bilPhi,${S.bilPhi},eV,`,
    `Pr,${S.Pr},uC/cm2,`,
    `TER_read,${readMetrics(S.readV,m).ratio},x,@ ${S.readV} V`,
    `best_read,${scan.best.V},V,score ${scan.best.score}`,
    `dominant_mechanism,${fit.best.name},,score ${fit.best.score}`,
    `FN_phi,${Number.isFinite(fn.phi)?fn.phi:""},eV,R2 ${fn.r2}`,
    `PUND_Qsw,${pund.qswPc},pC,leak ${pund.qLeakPc} pC`,
    `usable_states,${sn.usable},states,target ${sn.n}`,
    `retention_ratio_goal,${ret.rGoal},x,@ ${S.retentionGoal} s`,
    `tau,${ret.tau},s,`,
    `endurance_N0,${ret.n0},cycles,`,
    `risk,${risk},0-100,`
  ];
  fit.fits.forEach(f => lines.push(`fit_${f.name},${f.score},score,R2 ${f.r2} slope ${f.slope}`));
  download(new Blob([lines.join("\n")], {type:"text/csv"}), "ftj_lab_v8_report.csv");
}
function download(blob, name){
  const a = document.createElement("a");
  a.href = URL.createObjectURL(blob);
  a.download = name;
  a.click();
  setTimeout(() => URL.revokeObjectURL(a.href), 500);
}
function copySummary(){
  const {fit, scan, pund, ret, sn, risk, m} = lastReport;
  const fn = fit.fits.find(f => f.name==="Fowler-Nordheim");
  const text =
    `FTJ v8 summary\n`+
    `Preset: ${S.preset}\n`+
    `Stack: ${S.te}/HZO ${S.hzoT} nm/BIL ${S.bilT} nm/${S.be}, A=${S.area} µm², T=${S.temp} K\n`+
    `Read TER: ${readMetrics(S.readV,m).ratio.toFixed(2)}× @ ${S.readV} V\n`+
    `Best read: ${scan.best.V.toFixed(2)} V (BER ${scan.best.ber<1e-6?scan.best.ber.toExponential(1):scan.best.ber.toFixed(3)})\n`+
    `Dominant mechanism: ${fit.best.name}, score ${fit.best.score.toFixed(2)}\n`+
    `FN phi: ${Number.isFinite(fn.phi)?fn.phi.toFixed(2):"NA"} eV (R² ${fn.r2.toFixed(3)})\n`+
    `PUND Qsw: ${pund.qswPc.toFixed(2)} pC, leak ${pund.qLeakPc.toFixed(2)} pC\n`+
    `States usable: ${sn.usable}/${sn.n}, step/σ ${sn.sep.toFixed(2)}\n`+
    `Retention target ratio: ${ret.rGoal.toFixed(2)}× @ ${S.retentionGoal}s, τ ${tauFmt(ret.tau)}\n`+
    `Risk: ${risk.toFixed(0)}/100`;
  if(navigator.clipboard) navigator.clipboard.writeText(text);
  E.stamp.textContent = "summary copied";
}

// ============================================================
//  PRESETS
// ============================================================
function preset(p){
  const base = {preset:p};
  if(p==="user") Object.assign(base, {
    te:"Mo", be:"TiN", area:100, temp:300, mode:"live",
    hzoT:5.5, bilT:1.0, hzoPhi:1.85, bilPhi:2.55, hzoEg:5.7, bilEg:4.6,
    epsHzo:28, epsBil:14, mEff:0.32,
    Pr:24, screen:0.72, ifc:0.62, ovac:0.55, depol:0.38, trap:0.28, leak:0.12,
    Rs:250, Vapp:0.3, Vmax:2.5, readV:0.3, pulseV:2.2, resetV:-2.2, setV:2.4, pulseW:1,
    rA:0.3, rB:0.4, rC:0.5, rD:0.6,
    nStates:32, noisePct:2, retentionGoal:1e4, enduranceN:1e5
  });
  if(p==="mfm") Object.assign(base, {
    te:"TiN", be:"TiN", area:100, temp:300, mode:"mfm",
    hzoT:6.0, bilT:0, hzoPhi:1.95, bilPhi:2.4, hzoEg:5.8, bilEg:4.6,
    epsHzo:30, epsBil:10, mEff:0.35,
    Pr:22, screen:0.9, ifc:0.15, ovac:0.12, depol:0.11, trap:0.1, leak:0.04,
    Rs:120, Vapp:0.3, Vmax:3.0, readV:0.25, pulseV:2.4, resetV:-2.4, setV:2.4, pulseW:1,
    rA:0.2, rB:0.3, rC:0.4, rD:0.5,
    nStates:16, noisePct:1.2, retentionGoal:1e5, enduranceN:1e6
  });
  if(p==="mfis") Object.assign(base, {
    te:"Mo", be:"TiN", area:80, temp:300, mode:"mfis",
    hzoT:5.0, bilT:1.25, hzoPhi:1.7, bilPhi:2.9, hzoEg:5.6, bilEg:4.8,
    epsHzo:26, epsBil:9, mEff:0.32,
    Pr:20, screen:0.62, ifc:0.95, ovac:0.78, depol:0.48, trap:0.46, leak:0.10,
    Rs:320, Vapp:0.3, Vmax:2.4, readV:0.25, pulseV:2.1, resetV:-2.1, setV:2.6, pulseW:1.2,
    rA:0.25, rB:0.35, rC:0.45, rD:0.55,
    nStates:32, noisePct:2.8, retentionGoal:1e4, enduranceN:1e5
  });
  if(p==="leak") Object.assign(base, {
    te:"Mo", be:"TiN", area:100, temp:300, mode:"live",
    hzoT:4.7, bilT:0.65, hzoPhi:1.25, bilPhi:1.85, hzoEg:5.4, bilEg:4.0,
    epsHzo:25, epsBil:18, mEff:0.28,
    Pr:17, screen:0.55, ifc:0.85, ovac:1.08, depol:0.55, trap:1.0, leak:0.78,
    Rs:650, Vapp:0.4, Vmax:2.5, readV:0.3, pulseV:2.7, resetV:-2.6, setV:3.0, pulseW:1.6,
    rA:0.3, rB:0.4, rC:0.5, rD:0.6,
    nStates:16, noisePct:6, retentionGoal:1e3, enduranceN:1e4
  });
  if(p==="mfs") Object.assign(base, {
    // Mo / HZO / InGaAs:p++  — degenerate p-type semiconductor bottom electrode.
    // BIL≈0 (Gemini scenario), but a thin native-oxide dead layer is unavoidable.
    te:"Mo", be:"InGaAs:p++", area:80, temp:300, mode:"mfs",
    hzoT:5.0, bilT:0, hzoPhi:1.8, bilPhi:2.4, hzoEg:5.7, bilEg:4.6,
    epsHzo:28, epsBil:9, mEff:0.32,
    Pr:22, screen:0.60, ifc:0.70, ovac:0.55, depol:0.45, trap:0.35, leak:0.18,
    Rs:300, Vapp:0.3, Vmax:3.5, readV:0.30, pulseV:3.2, resetV:-3.2, setV:3.4, pulseW:1.2,
    rA:0.3, rB:0.4, rC:0.5, rD:0.6,
    nStates:32, noisePct:3.0, retentionGoal:1e4, enduranceN:1e5,
    NaLog:20.0, tDead:0.4, epsDead:8
  });
  Object.assign(S, base);
  syncAll();
  render();
}

// ============================================================
//  INIT
// ============================================================
function init(){
  // Electrode dropdowns
  Object.keys(MAT).forEach(k => {
    const a = document.createElement("option");
    a.value = k;
    a.textContent = `${k} (WF ${MAT[k].wf.toFixed(2)} eV)`;
    E.te.appendChild(a);
    E.be.appendChild(a.cloneNode(true));
  });
  E.te.value = S.te; E.be.value = S.be;
  E.area.value = S.area; E.temp.value = S.temp; E.mode.value = S.mode;

  // Build sliders
  makeSliders(vappDef,       E.vappSlider);
  makeSliders(stackDefs,     E.stackSliders);
  makeSliders(mfsDefs,       E.mfsSliders);
  makeSliders(defectDefs,    E.defectSliders);
  makeSliders(measDefs,      E.measSliders);
  makeSliders(readMultiDefs, E.readMultiSliders);

  // Events
  E.te.onchange   = ev => { S.te   = ev.target.value; render(); };
  E.be.onchange   = ev => { S.be   = ev.target.value; render(); };
  E.mode.onchange = ev => { S.mode = ev.target.value; render(); };
  E.area.oninput  = ev => { S.area = cl(Number(ev.target.value)||1, 0.001, 100000); render(); };
  E.temp.oninput  = ev => { S.temp = cl(Number(ev.target.value)||300, 4, 700); render(); };

  // Quick-volt buttons
  document.querySelectorAll(".quickVolt button").forEach(b => {
    b.onclick = () => {
      const v = b.getAttribute("data-v");
      S.Vapp = (v==="set") ? S.setV : Number(v);
      syncOne("Vapp");
      render();
    };
  });

  // Preset buttons
  E.pUser.onclick = () => preset("user");
  E.pMfm.onclick  = () => preset("mfm");
  E.pMfis.onclick = () => preset("mfis");
  E.pLeak.onclick = () => preset("leak");
  E.pMfs.onclick  = () => preset("mfs");

  // CSV
  E.sampleBtn.onclick = loadSample;
  E.parseBtn.onclick  = parseData;
  E.clearBtn.onclick  = () => {
    DATA = [];
    E.csvIn.value = "";
    E.dataStatus.textContent = "No external data. Synthetic curve is being used.";
    render();
  };

  // Export / import
  E.exportConfig.onclick  = exportConfig;
  E.exportCsv.onclick     = exportReport;
  E.importConfig.onchange = importConfig;
  E.copySummary.onclick   = copySummary;
  E.autoRead.onclick      = () => {
    const r = scanRead(model()).best;
    S.readV = r.V;
    syncOne("readV");
    render();
  };

  // Why? toggles for each panel
  document.querySelectorAll(".whyBtn").forEach(b => {
    b.onclick = () => {
      const targetId = b.getAttribute("data-why");
      const box = document.getElementById(targetId);
      if(!box) return;
      const wasOpen = box.classList.contains("open");
      box.classList.toggle("open");
      b.classList.toggle("open", !wasOpen);
      b.textContent = wasOpen ? "Why?" : "Close";
      // Re-render KaTeX inside the just-opened box
      if(!wasOpen && window.renderMathInElement){
        try { renderMathInElement(box, {
          delimiters:[{left:'$$',right:'$$',display:true},{left:'$',right:'$',display:false}],
          throwOnError:false
        }); } catch(e){}
      }
    };
  });

  window.addEventListener("resize", render);
  render();
}
init();
</script>
</body>
</html>
