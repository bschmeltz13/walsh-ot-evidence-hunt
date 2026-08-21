[index.html](https://github.com/user-attachments/files/31287864/preview.html)
[index.htm](https://github.com/user-attachments/files/31287055/Walsh_OT_Evidence_Hunt.html)
# walsh-ot-evidence-hunt<!DOCTYPE html>
<html lang="en">
<head><!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="utf-8" />
  <meta name="viewport" content="width=device-width, initial-scale=1" />
  <title>Walsh OT Evidence Hunt</title>
  <style>
    :root{
      --bg:#f7f8fa; --panel:#ffffff; --text:#1f2937; --muted:#667085;
      --border:#d9dee7; --accent:#7a1f3d; --accent-soft:#f5e9ee;
      --good:#16794b; --warn:#9a6700;
    }
    *{box-sizing:border-box}
    body{margin:0;font-family:Arial,Helvetica,sans-serif;background:var(--bg);color:var(--text);line-height:1.5}
    .shell{max-width:980px;margin:0 auto;padding:24px}
    .hero,.card{background:var(--panel);border:1px solid var(--border);border-radius:18px;padding:24px;margin-bottom:18px}
    h1,h2,h3{margin-top:0}
    h1{font-size:2rem;margin-bottom:8px}
    h2{font-size:1.35rem}
    h3{font-size:1.05rem}
    .muted{color:var(--muted)}
    .progress-wrap{margin:16px 0 6px}
    .progress{height:10px;background:#e8ebf0;border-radius:999px;overflow:hidden}
    .progress > div{height:100%;background:var(--accent);width:16.67%;transition:width .2s ease}
    .step-label,.status,.help{font-size:.92rem}
    .grid{display:grid;gap:16px}
    .grid-2{grid-template-columns:repeat(2,minmax(0,1fr))}
    label{display:block;font-weight:700;margin-bottom:6px}
    input,textarea,select{width:100%;padding:11px 12px;border:1px solid var(--border);border-radius:10px;font:inherit;color:var(--text);background:white}
    textarea{resize:vertical}
    .help{color:var(--muted);margin-top:6px}
    .tip{background:var(--accent-soft);border-left:4px solid var(--accent);padding:12px 14px;border-radius:10px;margin-top:12px}
    .checklist label{font-weight:400;display:flex;gap:10px;align-items:flex-start;margin:9px 0}
    .checklist input{width:auto;margin-top:5px}
    .nav,.actions{display:flex;justify-content:space-between;gap:12px;flex-wrap:wrap}
    .actions{justify-content:flex-start;align-items:center}
    button{border:0;border-radius:10px;padding:11px 16px;font-weight:700;cursor:pointer;font:inherit}
    .btn-primary{background:var(--accent);color:white}
    .btn-secondary{background:white;color:var(--text);border:1px solid var(--border)}
    .btn-success{background:var(--good);color:white}
    button:disabled{opacity:.45;cursor:not-allowed}
    .hidden{display:none}
    .article{border:1px solid var(--border);border-radius:14px;padding:16px;margin:14px 0}
    .summary-block{border-top:1px solid var(--border);padding-top:14px;margin-top:14px}
    .summary-value{white-space:pre-wrap;background:#fafbfc;border:1px solid var(--border);border-radius:10px;padding:10px}
    .required::after{content:" *";color:#b42318}
    .good{color:var(--good)}
    .warn{color:var(--warn)}
    .student-meta{display:grid;grid-template-columns:2fr 1fr;gap:16px}
    @media (max-width:720px){.grid-2,.student-meta{grid-template-columns:1fr}.shell{padding:14px}}
    @media print{
      body{background:white}
      .no-print,.hero .muted,.progress-wrap,.step-label{display:none !important}
      .shell{max-width:none;padding:0}
      .card,.hero{border:0;border-radius:0;padding:0;margin:0 0 18px}
      #finalSummary{display:block !important}
      .summary-value{border:1px solid #bbb;background:white}
      .page-break{page-break-before:always}
    }
  </style>
</head>
<body>
<main class="shell">
  <section class="hero">
    <h1>Evidence Hunt</h1>
    <p class="muted">Using Walsh University Library Resources</p>
    <p>Complete each step to build a focused clinical question, create a search strategy, locate evidence, identify study design, and reflect on the search process.</p>

    <div class="student-meta">
      <div>
        <label for="studentName" class="required">Student Name</label>
        <input id="studentName" type="text" autocomplete="name" />
      </div>
      <div>
        <label for="activityDate">Date</label>
        <input id="activityDate" type="date" />
      </div>
    </div>

    <div class="progress-wrap no-print"><div class="progress"><div id="progressBar"></div></div></div>
    <div id="stepLabel" class="step-label no-print">Step 1 of 6</div>
    <div class="actions no-print" style="margin-top:10px">
      <span id="saveStatus" class="status good">Autosave is on.</span>
      <button id="clearBtn" class="btn-secondary" type="button">Start Over / Clear Saved Work</button>
    </div>
  </section>

  <section id="step1" class="card step">
    <h2>1. PICO/PIO Question</h2>
    <p class="muted">Identify the major components of the clinical question. Comparison is optional.</p>
    <div class="grid grid-2">
      <div><label for="population" class="required">Population / Problem (P)</label><input id="population" type="text" /></div>
      <div><label for="intervention" class="required">Intervention / Interest (I)</label><input id="intervention" type="text" /></div>
      <div><label for="comparison">Comparison (C) — optional</label><input id="comparison" type="text" /></div>
      <div><label for="outcome" class="required">Outcome (O)</label><input id="outcome" type="text" /></div>
    </div>
    <div style="margin-top:16px">
      <label for="picoQuestion" class="required">Final PICO/PIO Question</label>
      <textarea id="picoQuestion" rows="4"></textarea>
    </div>
  </section>

  <section id="step2" class="card step hidden">
    <h2>2. Keywords and Synonyms</h2>
    <p class="muted">Choose the strongest concepts from the PICO/PIO question and identify 2–3 synonyms or related terms for each.</p>
    <div class="article"><h3>Concept 1</h3><div class="grid grid-2">
      <div><label for="concept1" class="required">Keyword</label><input id="concept1" type="text" /></div>
      <div><label for="syn1" class="required">Synonyms / Related Terms</label><input id="syn1" type="text" placeholder="Separate terms with commas" /></div>
    </div></div>
    <div class="article"><h3>Concept 2</h3><div class="grid grid-2">
      <div><label for="concept2" class="required">Keyword</label><input id="concept2" type="text" /></div>
      <div><label for="syn2" class="required">Synonyms / Related Terms</label><input id="syn2" type="text" placeholder="Separate terms with commas" /></div>
    </div></div>
    <div class="article"><h3>Concept 3</h3><div class="grid grid-2">
      <div><label for="concept3">Keyword</label><input id="concept3" type="text" /></div>
      <div><label for="syn3">Synonyms / Related Terms</label><input id="syn3" type="text" placeholder="Separate terms with commas" /></div>
    </div></div>
    <div class="tip"><strong>Search tip:</strong> Use <strong>OR</strong> between synonyms and <strong>AND</strong> between different concepts.</div>
  </section>

  <section id="step3" class="card step hidden">
    <h2>3. Search Strategy</h2>
    <label for="searchString" class="required">Search String</label>
    <textarea id="searchString" rows="5" placeholder="Example: (stroke OR CVA) AND (occupational therapy OR rehabilitation)"></textarea>
    <div style="margin-top:16px">
      <label for="databases" class="required">Database(s) Used</label>
      <input id="databases" type="text" />
    </div>
    <div class="article checklist">
      <h3>Search Quality Check</h3>
      <label><input type="checkbox" id="qc1" /> OR is used between synonyms or related terms.</label>
      <label><input type="checkbox" id="qc2" /> AND is used between different concepts.</label>
      <label><input type="checkbox" id="qc3" /> Search terms directly relate to the PICO/PIO question.</label>
    </div>
  </section>

  <section id="step4" class="card step hidden">
    <h2>4. Articles Found</h2>
    <p class="muted">Locate at least one systematic review and two primary research articles. Record each citation in APA format.</p>
    
    <div class="article">
      <h3>Article 1</h3>
      <label for="citation1" class="required">APA Citation</label>
      <textarea id="citation1" rows="4"></textarea>
      <label for="design1" class="required">Evidence Level / Study Design</label>
      <select id="design1">
        <option value="">Select one</option>
        <option>Systematic review / meta-analysis</option>
        <option>Randomized controlled trial (RCT)</option>
        <option>Cohort study</option>
        <option>Case-control study</option>
        <option>Cross-sectional study</option>
        <option>Qualitative study</option>
        <option>Mixed-methods study</option>
        <option>Case series / case study</option>
        <option>Other</option>
      </select>
    </div>
    <div class="article">
      <h3>Article 2</h3>
      <label for="citation2" class="required">APA Citation</label>
      <textarea id="citation2" rows="4"></textarea>
      <label for="design2" class="required">Evidence Level / Study Design</label>
      <select id="design2">
        <option value="">Select one</option>
        <option>Systematic review / meta-analysis</option>
        <option>Randomized controlled trial (RCT)</option>
        <option>Cohort study</option>
        <option>Case-control study</option>
        <option>Cross-sectional study</option>
        <option>Qualitative study</option>
        <option>Mixed-methods study</option>
        <option>Case series / case study</option>
        <option>Other</option>
      </select>
    </div>
    <div class="article">
      <h3>Article 3</h3>
      <label for="citation3" class="required">APA Citation</label>
      <textarea id="citation3" rows="4"></textarea>
      <label for="design3" class="required">Evidence Level / Study Design</label>
      <select id="design3">
        <option value="">Select one</option>
        <option>Systematic review / meta-analysis</option>
        <option>Randomized controlled trial (RCT)</option>
        <option>Cohort study</option>
        <option>Case-control study</option>
        <option>Cross-sectional study</option>
        <option>Qualitative study</option>
        <option>Mixed-methods study</option>
        <option>Case series / case study</option>
        <option>Other</option>
      </select>
    </div>
  </section>

  <section id="step5" class="card step hidden">
    <h2>5. Reflection</h2>
    <label for="challenges" class="required">What challenges did your group face while searching?</label>
    <textarea id="challenges" rows="5"></textarea>
    <div style="margin-top:16px">
      <label for="strategies" class="required">What strategies helped refine your search?</label>
      <textarea id="strategies" rows="5"></textarea>
    </div>
  </section>

  <section id="step6" class="card step hidden">
    <h2>6. Final Review & Submission</h2>
    <p class="muted">Review the completed Evidence Hunt. Use the buttons below to print or save the completed activity as a PDF for Canvas submission.</p>
    <div class="article checklist">
      <h3>Final Check</h3>
      <label><input type="checkbox" id="fc1" /> Three scholarly articles are included.</label>
      <label><input type="checkbox" id="fc2" /> At least one article is a systematic review.</label>
      <label><input type="checkbox" id="fc3" /> At least two articles are primary research.</label>
      <label><input type="checkbox" id="fc4" /> APA citations and evidence levels have been checked.</label>
    </div>

    <div id="finalSummary">
      <div class="summary-block"><h3>Student</h3><div class="summary-value" id="sStudent"></div></div>
      <div class="summary-block"><h3>PICO/PIO Question</h3><div class="summary-value" id="sPico"></div></div>
      <div class="summary-block"><h3>Keywords & Synonyms</h3><div class="summary-value" id="sKeywords"></div></div>
      <div class="summary-block"><h3>Search Strategy</h3><div class="summary-value" id="sSearch"></div></div>
      <div class="summary-block page-break"><h3>Articles Found</h3><div class="summary-value" id="sArticles"></div></div>
      <div class="summary-block"><h3>Reflection</h3><div class="summary-value" id="sReflection"></div></div>
    </div>

    <div class="actions no-print">
      <button class="btn-success" type="button" id="printBtn">Print / Save as PDF</button>
      <button class="btn-secondary" type="button" id="downloadBtn">Download .txt Copy</button>
    </div>
    <div class="help no-print">To create a PDF: choose <strong>Print / Save as PDF</strong>, then select your browser's <strong>Save as PDF</strong> destination.</div>
  </section>

  <div class="nav no-print">
    <button id="backBtn" class="btn-secondary" type="button" disabled>Back</button>
    <button id="nextBtn" class="btn-primary" type="button">Next Step</button>
  </div>
  <div id="validationMsg" class="status warn no-print" role="status" aria-live="polite"></div>
</main>

<script>
(function(){
  const totalSteps = 6;
  let currentStep = 1;
  const STORAGE_KEY = "walsh_ot_evidence_hunt_v2";

  const ids = [
    "studentName","activityDate","population","intervention","comparison","outcome","picoQuestion",
    "concept1","syn1","concept2","syn2","concept3","syn3","searchString","databases",
    "qc1","qc2","qc3","citation1","design1","citation2","design2","citation3","design3",
    "challenges","strategies","fc1","fc2","fc3","fc4"
  ];

  function el(id){ return document.getElementById(id); }
  function value(id){
    const node = el(id);
    if(!node) return "";
    if(node.type === "checkbox") return node.checked;
    return node.value.trim();
  }

  function saveWork(){
    const data = { currentStep };
    ids.forEach(id=>{
      const node = el(id);
      if(!node) return;
      data[id] = node.type === "checkbox" ? node.checked : node.value;
    });
    localStorage.setItem(STORAGE_KEY, JSON.stringify(data));
    el("saveStatus").textContent = "Saved automatically on this device.";
  }

  function restoreWork(){
    const raw = localStorage.getItem(STORAGE_KEY);
    if(!raw) return false;
    try{
      const data = JSON.parse(raw);
      ids.forEach(id=>{
        const node = el(id);
        if(!node || data[id] === undefined) return;
        if(node.type === "checkbox") node.checked = !!data[id];
        else node.value = data[id];
      });
      if(Number.isInteger(data.currentStep) && data.currentStep >= 1 && data.currentStep <= totalSteps){
        currentStep = data.currentStep;
      }
      return true;
    }catch(e){ return false; }
  }

  function clearSavedWork(){
    if(!confirm("This will permanently clear all saved responses for this Evidence Hunt on this device. Continue?")) return;
    localStorage.removeItem(STORAGE_KEY);
    ids.forEach(id=>{
      const node = el(id);
      if(!node) return;
      if(node.type === "checkbox") node.checked = false;
      else node.value = "";
    });
    const d = new Date();
    el("activityDate").value = d.toISOString().slice(0,10);
    currentStep = 1;
    showStep(1);
    el("saveStatus").textContent = "Saved work cleared. A new activity is ready.";
  }

  function showStep(step){
    document.querySelectorAll(".step").forEach((node, idx)=>node.classList.toggle("hidden", idx !== step-1));
    currentStep = step;
    el("stepLabel").textContent = `Step ${step} of ${totalSteps}`;
    el("progressBar").style.width = `${(step/totalSteps)*100}%`;
    el("backBtn").disabled = step === 1;
    el("nextBtn").textContent = step === totalSteps ? "Review Complete" : "Next Step";
    el("validationMsg").textContent = "";
    if(step === 6) renderSummary();
    saveWork();
    window.scrollTo({top:0, behavior:"smooth"});
  }

  function requiredForStep(step){
    return ({
      1:["studentName","population","intervention","outcome","picoQuestion"],
      2:["concept1","syn1","concept2","syn2"],
      3:["searchString","databases"],
      4:["citation1","design1","citation2","design2","citation3","design3"],
      5:["challenges","strategies"],
      6:[]
    })[step] || [];
  }

  function validateStep(step){
    const missing = requiredForStep(step).filter(id => !value(id));
    if(missing.length){
      el("validationMsg").textContent = "Please complete all required fields before continuing.";
      return false;
    }
    return true;
  }

  function esc(text){
    return String(text || "").replace(/[&<>"']/g, ch => ({"&":"&amp;","<":"&lt;",">":"&gt;",'"':"&quot;","'":"&#039;"}[ch]));
  }

  function renderSummary(){
    el("sStudent").innerHTML = `${esc(value("studentName"))}${value("activityDate") ? " — " + esc(value("activityDate")) : ""}`;
    el("sPico").innerHTML =
      `<strong>Population/Problem:</strong> ${esc(value("population"))}<br>
       <strong>Intervention/Interest:</strong> ${esc(value("intervention"))}<br>
       <strong>Comparison:</strong> ${esc(value("comparison") || "Not applicable")}<br>
       <strong>Outcome:</strong> ${esc(value("outcome"))}<br><br>
       <strong>Final Question:</strong><br>${esc(value("picoQuestion"))}`;
    el("sKeywords").innerHTML =
      `<strong>Concept 1:</strong> ${esc(value("concept1"))}<br><strong>Synonyms:</strong> ${esc(value("syn1"))}<br><br>
       <strong>Concept 2:</strong> ${esc(value("concept2"))}<br><strong>Synonyms:</strong> ${esc(value("syn2"))}<br><br>
       <strong>Concept 3:</strong> ${esc(value("concept3") || "Not used")}<br><strong>Synonyms:</strong> ${esc(value("syn3") || "Not used")}`;
    el("sSearch").innerHTML =
      `<strong>Search String:</strong><br>${esc(value("searchString"))}<br><br><strong>Database(s):</strong> ${esc(value("databases"))}`;
    let a = "";
    [1,2,3].forEach(i=>{
      a += `<strong>Article ${i}</strong><br>${esc(value("citation"+i))}<br><em>${esc(value("design"+i))}</em>${i<3 ? "<br><br>" : ""}`;
    });
    el("sArticles").innerHTML = a;
    el("sReflection").innerHTML =
      `<strong>Challenges:</strong><br>${esc(value("challenges"))}<br><br>
       <strong>Strategies that helped refine the search:</strong><br>${esc(value("strategies"))}`;
  }

  function textExport(){
    return `WALSH OT EVIDENCE HUNT

Student: ${value("studentName")}
Date: ${value("activityDate")}

1. PICO/PIO QUESTION
Population/Problem: ${value("population")}
Intervention/Interest: ${value("intervention")}
Comparison: ${value("comparison") || "Not applicable"}
Outcome: ${value("outcome")}
Final Question: ${value("picoQuestion")}

2. KEYWORDS AND SYNONYMS
Concept 1: ${value("concept1")}
Synonyms: ${value("syn1")}

Concept 2: ${value("concept2")}
Synonyms: ${value("syn2")}

Concept 3: ${value("concept3") || "Not used"}
Synonyms: ${value("syn3") || "Not used"}

3. SEARCH STRATEGY
Search String: ${value("searchString")}
Database(s): ${value("databases")}

4. ARTICLES FOUND
Article 1:
${value("citation1")}
Evidence Level/Study Design: ${value("design1")}

Article 2:
${value("citation2")}
Evidence Level/Study Design: ${value("design2")}

Article 3:
${value("citation3")}
Evidence Level/Study Design: ${value("design3")}

5. REFLECTION
Challenges:
${value("challenges")}

Strategies:
${value("strategies")}
`;
  }

  el("nextBtn").addEventListener("click", ()=>{
    if(currentStep < totalSteps){
      if(!validateStep(currentStep)) return;
      showStep(currentStep + 1);
    } else {
      renderSummary();
      saveWork();
      el("validationMsg").textContent = "Review complete. Use Print / Save as PDF to create your submission file.";
      el("validationMsg").className = "status good no-print";
    }
  });

  el("backBtn").addEventListener("click", ()=>{ if(currentStep > 1) showStep(currentStep - 1); });
  el("printBtn").addEventListener("click", ()=>{ renderSummary(); saveWork(); window.print(); });
  el("downloadBtn").addEventListener("click", ()=>{
    saveWork();
    const blob = new Blob([textExport()], {type:"text/plain;charset=utf-8"});
    const url = URL.createObjectURL(blob);
    const a = document.createElement("a");
    const safe = (value("studentName") || "student").replace(/[^a-z0-9]+/gi,"_");
    a.href = url; a.download = `${safe}_Evidence_Hunt.txt`;
    document.body.appendChild(a); a.click(); a.remove(); URL.revokeObjectURL(url);
  });

  ids.forEach(id=>{
    const node = el(id);
    if(!node) return;
    node.addEventListener("input", saveWork);
    node.addEventListener("change", saveWork);
  });
  el("clearBtn").addEventListener("click", clearSavedWork);

  const restored = restoreWork();
  if(!value("activityDate")) el("activityDate").value = new Date().toISOString().slice(0,10);
  showStep(restored ? currentStep : 1);
  el("saveStatus").textContent = restored ? "Previous work restored from this device." : "Autosave is on.";
})();
</script>
</body>
</html>
  <meta charset="utf-8" />
  <meta name="viewport" content="width=device-width, initial-scale=1" />
  <title>Walsh OT Evidence Hunt</title>
  <style>
    :root{
      --bg:#f7f8fa;
      --panel:#ffffff;
      --text:#1f2937;
      --muted:#667085;
      --border:#d9dee7;
      --accent:#7a1f3d;
      --accent-soft:#f5e9ee;
      --good:#16794b;
      --warn:#9a6700;
    }
    *{box-sizing:border-box}
    body{margin:0;font-family:Arial,Helvetica,sans-serif;background:var(--bg);color:var(--text);line-height:1.5}
    .shell{max-width:980px;margin:0 auto;padding:24px}
    .hero{background:var(--panel);border:1px solid var(--border);border-radius:18px;padding:24px;margin-bottom:18px}
    h1,h2,h3{margin-top:0}
    h1{font-size:2rem;margin-bottom:8px}
    h2{font-size:1.35rem}
    h3{font-size:1.05rem}
    .muted{color:var(--muted)}
    .progress-wrap{margin:16px 0 6px}
    .progress{height:10px;background:#e8ebf0;border-radius:999px;overflow:hidden}
    .progress > div{height:100%;background:var(--accent);width:16.67%;transition:width .2s ease}
    .step-label{font-size:.92rem;color:var(--muted);margin-top:6px}
    .card{background:var(--panel);border:1px solid var(--border);border-radius:16px;padding:22px;margin:16px 0}
    .grid{display:grid;gap:16px}
    .grid-2{grid-template-columns:repeat(2,minmax(0,1fr))}
    label{display:block;font-weight:700;margin-bottom:6px}
    input,textarea,select{
      width:100%;padding:11px 12px;border:1px solid var(--border);border-radius:10px;
      font:inherit;color:var(--text);background:white
    }
    textarea{resize:vertical}
    .help{font-size:.9rem;color:var(--muted);margin-top:6px}
    .tip{background:var(--accent-soft);border-left:4px solid var(--accent);padding:12px 14px;border-radius:10px;margin-top:12px}
    .checklist label{font-weight:400;display:flex;gap:10px;align-items:flex-start;margin:9px 0}
    .checklist input{width:auto;margin-top:5px}
    .nav{display:flex;justify-content:space-between;gap:12px;margin-top:22px}
    button{
      border:0;border-radius:10px;padding:11px 16px;font-weight:700;cursor:pointer;font:inherit
    }
    .btn-primary{background:var(--accent);color:white}
    .btn-secondary{background:white;color:var(--text);border:1px solid var(--border)}
    .btn-success{background:var(--good);color:white}
    button:disabled{opacity:.45;cursor:not-allowed}
    .hidden{display:none}
    .article{border:1px solid var(--border);border-radius:14px;padding:16px;margin:14px 0}
    .summary-block{border-top:1px solid var(--border);padding-top:14px;margin-top:14px}
    .summary-value{white-space:pre-wrap;background:#fafbfc;border:1px solid var(--border);border-radius:10px;padding:10px}
    .actions{display:flex;gap:10px;flex-wrap:wrap;margin-top:18px}
    .required::after{content:" *";color:#b42318}
    .status{font-size:.9rem;margin-top:8px}
    .good{color:var(--good)}
    .warn{color:var(--warn)}
    .student-meta{display:grid;grid-template-columns:2fr 1fr;gap:16px}
    @media (max-width:720px){
      .grid-2,.student-meta{grid-template-columns:1fr}
      .shell{padding:14px}
    }
    @media print{
      body{background:white}
      .no-print,.hero .muted,.progress-wrap,.step-label{display:none !important}
      .shell{max-width:none;padding:0}
      .card,.hero{border:0;border-radius:0;padding:0;margin:0 0 18px}
      #finalSummary{display:block !important}
      .summary-value{border:1px solid #bbb;background:white}
      .page-break{page-break-before:always}
    }
  </style>
</head>
<body>
  <main class="shell">
    <section class="hero">
      <h1>Evidence Hunt</h1>
      <p class="muted">Using Walsh University Library Resources</p>
      <p>Complete each step to build a focused clinical question, create a search strategy, locate evidence, identify study design, and reflect on the search process.</p>

      <div class="student-meta">
        <div>
          <label for="studentName" class="required">Student Name</label>
          <input id="studentName" type="text" autocomplete="name" />
        </div>
        <div>
          <label for="activityDate">Date</label>
          <input id="activityDate" type="date" />
        </div>
      </div>

      <div class="progress-wrap no-print">
        <div class="progress"><div id="progressBar"></div></div>
      </div>
      <div id="stepLabel" class="step-label no-print">Step 1 of 6</div>
    </section>

    <section id="step1" class="card step">
      <h2>1. PICO/PIO Question</h2>
      <p class="muted">Identify the major components of the clinical question. Comparison is optional.</p>

      <div class="grid grid-2">
        <div>
          <label for="population" class="required">Population / Problem (P)</label>
          <input id="population" type="text" placeholder="Who is the population or what is the problem?" />
        </div>
        <div>
          <label for="intervention" class="required">Intervention / Interest (I)</label>
          <input id="intervention" type="text" placeholder="Intervention, exposure, or area of interest" />
        </div>
        <div>
          <label for="comparison">Comparison (C) — optional</label>
          <input id="comparison" type="text" placeholder="Comparison intervention or usual care" />
        </div>
        <div>
          <label for="outcome" class="required">Outcome (O)</label>
          <input id="outcome" type="text" placeholder="What outcome is being examined?" />
        </div>
      </div>

      <div style="margin-top:16px">
        <label for="picoQuestion" class="required">Final PICO/PIO Question</label>
        <textarea id="picoQuestion" rows="4" placeholder="Write the complete clinical question."></textarea>
      </div>
    </section>

    <section id="step2" class="card step hidden">
      <h2>2. Keywords and Synonyms</h2>
      <p class="muted">Choose the strongest concepts from the PICO/PIO question and identify 2–3 synonyms or related terms for each.</p>

      <div class="article">
        <h3>Concept 1</h3>
        <div class="grid grid-2">
          <div>
            <label for="concept1" class="required">Keyword</label>
            <input id="concept1" type="text" />
          </div>
          <div>
            <label for="syn1" class="required">Synonyms / Related Terms</label>
            <input id="syn1" type="text" placeholder="Separate terms with commas" />
          </div>
        </div>
      </div>

      <div class="article">
        <h3>Concept 2</h3>
        <div class="grid grid-2">
          <div>
            <label for="concept2" class="required">Keyword</label>
            <input id="concept2" type="text" />
          </div>
          <div>
            <label for="syn2" class="required">Synonyms / Related Terms</label>
            <input id="syn2" type="text" placeholder="Separate terms with commas" />
          </div>
        </div>
      </div>

      <div class="article">
        <h3>Concept 3</h3>
        <div class="grid grid-2">
          <div>
            <label for="concept3">Keyword</label>
            <input id="concept3" type="text" />
          </div>
          <div>
            <label for="syn3">Synonyms / Related Terms</label>
            <input id="syn3" type="text" placeholder="Separate terms with commas" />
          </div>
        </div>
      </div>

      <div class="tip"><strong>Search tip:</strong> Use <strong>OR</strong> between synonyms and <strong>AND</strong> between different concepts.</div>
    </section>

    <section id="step3" class="card step hidden">
      <h2>3. Search Strategy</h2>
      <p class="muted">Build and refine the search string used in Walsh University Library databases.</p>

      <label for="searchString" class="required">Search String</label>
      <textarea id="searchString" rows="5" placeholder="Example: (stroke OR CVA) AND (occupational therapy OR rehabilitation) AND (ADL OR activities of daily living)"></textarea>

      <div style="margin-top:16px">
        <label for="databases" class="required">Database(s) Used</label>
        <input id="databases" type="text" placeholder="Enter the database(s) searched" />
      </div>

      <div class="article checklist">
        <h3>Search Quality Check</h3>
        <label><input type="checkbox" id="qc1" /> OR is used between synonyms or related terms.</label>
        <label><input type="checkbox" id="qc2" /> AND is used between different concepts.</label>
        <label><input type="checkbox" id="qc3" /> Search terms directly relate to the PICO/PIO question.</label>
      </div>
    </section>

    <section id="step4" class="card step hidden">
      <h2>4. Articles Found</h2>
      <p class="muted">Locate at least one systematic review and two primary research articles. Record each citation in APA format.</p>

      <div class="article">
        <h3>Article 1</h3>
        <label for="citation1" class="required">APA Citation</label>
        <textarea id="citation1" rows="4"></textarea>
        <label for="design1" class="required">Evidence Level / Study Design</label>
        <select id="design1">
          <option value="">Select one</option>
          <option>Systematic review / meta-analysis</option>
          <option>Randomized controlled trial (RCT)</option>
          <option>Cohort study</option>
          <option>Case-control study</option>
          <option>Cross-sectional study</option>
          <option>Qualitative study</option>
          <option>Mixed-methods study</option>
          <option>Case series / case study</option>
          <option>Other</option>
        </select>
      </div>

      <div class="article">
        <h3>Article 2</h3>
        <label for="citation2" class="required">APA Citation</label>
        <textarea id="citation2" rows="4"></textarea>
        <label for="design2" class="required">Evidence Level / Study Design</label>
        <select id="design2">
          <option value="">Select one</option>
          <option>Systematic review / meta-analysis</option>
          <option>Randomized controlled trial (RCT)</option>
          <option>Cohort study</option>
          <option>Case-control study</option>
          <option>Cross-sectional study</option>
          <option>Qualitative study</option>
          <option>Mixed-methods study</option>
          <option>Case series / case study</option>
          <option>Other</option>
        </select>
      </div>

      <div class="article">
        <h3>Article 3</h3>
        <label for="citation3" class="required">APA Citation</label>
        <textarea id="citation3" rows="4"></textarea>
        <label for="design3" class="required">Evidence Level / Study Design</label>
        <select id="design3">
          <option value="">Select one</option>
          <option>Systematic review / meta-analysis</option>
          <option>Randomized controlled trial (RCT)</option>
          <option>Cohort study</option>
          <option>Case-control study</option>
          <option>Cross-sectional study</option>
          <option>Qualitative study</option>
          <option>Mixed-methods study</option>
          <option>Case series / case study</option>
          <option>Other</option>
        </select>
      </div>
    </section>

    <section id="step5" class="card step hidden">
      <h2>5. Reflection</h2>

      <label for="challenges" class="required">What challenges did your group face while searching?</label>
      <textarea id="challenges" rows="5"></textarea>

      <div style="margin-top:16px">
        <label for="strategies" class="required">What strategies helped refine your search?</label>
        <textarea id="strategies" rows="5"></textarea>
      </div>
    </section>

    <section id="step6" class="card step hidden">
      <h2>6. Final Review & Submission</h2>
      <p class="muted">Review the completed Evidence Hunt. Use the buttons below to print or save the completed activity as a PDF for Canvas submission.</p>

      <div class="article checklist">
        <h3>Final Check</h3>
        <label><input type="checkbox" id="fc1" /> Three scholarly articles are included.</label>
        <label><input type="checkbox" id="fc2" /> At least one article is a systematic review.</label>
        <label><input type="checkbox" id="fc3" /> At least two articles are primary research.</label>
        <label><input type="checkbox" id="fc4" /> APA citations and evidence levels have been checked.</label>
      </div>

      <div id="finalSummary">
        <div class="summary-block">
          <h3>Student</h3>
          <div class="summary-value" id="sStudent"></div>
        </div>
        <div class="summary-block">
          <h3>PICO/PIO Question</h3>
          <div class="summary-value" id="sPico"></div>
        </div>
        <div class="summary-block">
          <h3>Keywords & Synonyms</h3>
          <div class="summary-value" id="sKeywords"></div>
        </div>
        <div class="summary-block">
          <h3>Search Strategy</h3>
          <div class="summary-value" id="sSearch"></div>
        </div>
        <div class="summary-block page-break">
          <h3>Articles Found</h3>
          <div class="summary-value" id="sArticles"></div>
        </div>
        <div class="summary-block">
          <h3>Reflection</h3>
          <div class="summary-value" id="sReflection"></div>
        </div>
      </div>

      <div class="actions no-print">
        <button class="btn-success" type="button" id="printBtn">Print / Save as PDF</button>
        <button class="btn-secondary" type="button" id="downloadBtn">Download .txt Copy</button>
      </div>
      <div class="help no-print">To create a PDF: select <strong>Print / Save as PDF</strong>, then choose your browser's <strong>Save as PDF</strong> printer option.</div>
    </section>

    <div class="nav no-print">
      <button id="backBtn" class="btn-secondary" type="button" disabled>Back</button>
      <button id="nextBtn" class="btn-primary" type="button">Next Step</button>
    </div>

    <div id="validationMsg" class="status warn no-print" role="status" aria-live="polite"></div>
  </main>

<script>
(function(){
  const totalSteps = 6;
  let currentStep = 1;

  const ids = [
    "studentName","activityDate","population","intervention","comparison","outcome","picoQuestion",
    "concept1","syn1","concept2","syn2","concept3","syn3","searchString","databases",
    "qc1","qc2","qc3","citation1","design1","citation2","design2","citation3","design3",
    "challenges","strategies","fc1","fc2","fc3","fc4"
  ];

  function el(id){ return document.getElementById(id); }
  function value(id){
    const node = el(id);
    if(!node) return "";
    if(node.type === "checkbox") return node.checked;
    return node.value.trim();
  }

  function showStep(step){
    document.querySelectorAll(".step").forEach((node, idx)=>{
      node.classList.toggle("hidden", idx !== step-1);
    });
    currentStep = step;
    el("stepLabel").textContent = `Step ${step} of ${totalSteps}`;
    el("progressBar").style.width = `${(step/totalSteps)*100}%`;
    el("backBtn").disabled = step === 1;
    el("nextBtn").textContent = step === totalSteps ? "Review Complete" : "Next Step";
    el("validationMsg").textContent = "";
    if(step === 6) renderSummary();
    window.scrollTo({top:0, behavior:"smooth"});
  }

  function requiredForStep(step){
    const map = {
      1:["studentName","population","intervention","outcome","picoQuestion"],
      2:["concept1","syn1","concept2","syn2"],
      3:["searchString","databases"],
      4:["citation1","design1","citation2","design2","citation3","design3"],
      5:["challenges","strategies"],
      6:[]
    };
    return map[step] || [];
  }

  function validateStep(step){
    const missing = requiredForStep(step).filter(id => !value(id));
    if(missing.length){
      el("validationMsg").textContent = "Please complete all required fields before continuing.";
      return false;
    }
    return true;
  }

  function esc(text){
    return String(text || "").replace(/[&<>"']/g, ch => ({
      "&":"&amp;","<":"&lt;",">":"&gt;",'"':"&quot;","'":"&#039;"
    }[ch]));
  }

  function renderSummary(){
    el("sStudent").innerHTML = `${esc(value("studentName"))}${value("activityDate") ? " — " + esc(value("activityDate")) : ""}`;
    el("sPico").innerHTML =
      `<strong>Population/Problem:</strong> ${esc(value("population"))}<br>
       <strong>Intervention/Interest:</strong> ${esc(value("intervention"))}<br>
       <strong>Comparison:</strong> ${esc(value("comparison") || "Not applicable")}<br>
       <strong>Outcome:</strong> ${esc(value("outcome"))}<br><br>
       <strong>Final Question:</strong><br>${esc(value("picoQuestion"))}`;

    el("sKeywords").innerHTML =
      `<strong>Concept 1:</strong> ${esc(value("concept1"))}<br><strong>Synonyms:</strong> ${esc(value("syn1"))}<br><br>
       <strong>Concept 2:</strong> ${esc(value("concept2"))}<br><strong>Synonyms:</strong> ${esc(value("syn2"))}<br><br>
       <strong>Concept 3:</strong> ${esc(value("concept3") || "Not used")}<br><strong>Synonyms:</strong> ${esc(value("syn3") || "Not used")}`;

    el("sSearch").innerHTML =
      `<strong>Search String:</strong><br>${esc(value("searchString"))}<br><br>
       <strong>Database(s):</strong> ${esc(value("databases"))}`;

    let articleText = "";
    [1,2,3].forEach(i=>{
      articleText += `<strong>Article ${i}</strong><br>${esc(value("citation"+i))}<br><em>${esc(value("design"+i))}</em>${i<3 ? "<br><br>" : ""}`;
    });
    el("sArticles").innerHTML = articleText;

    el("sReflection").innerHTML =
      `<strong>Challenges:</strong><br>${esc(value("challenges"))}<br><br>
       <strong>Strategies that helped refine the search:</strong><br>${esc(value("strategies"))}`;
  }

  function textExport(){
    return `WALSH OT EVIDENCE HUNT

Student: ${value("studentName")}
Date: ${value("activityDate")}

1. PICO/PIO QUESTION
Population/Problem: ${value("population")}
Intervention/Interest: ${value("intervention")}
Comparison: ${value("comparison") || "Not applicable"}
Outcome: ${value("outcome")}
Final Question: ${value("picoQuestion")}

2. KEYWORDS AND SYNONYMS
Concept 1: ${value("concept1")}
Synonyms: ${value("syn1")}

Concept 2: ${value("concept2")}
Synonyms: ${value("syn2")}

Concept 3: ${value("concept3") || "Not used"}
Synonyms: ${value("syn3") || "Not used"}

3. SEARCH STRATEGY
Search String: ${value("searchString")}
Database(s): ${value("databases")}

4. ARTICLES FOUND
Article 1:
${value("citation1")}
Evidence Level/Study Design: ${value("design1")}

Article 2:
${value("citation2")}
Evidence Level/Study Design: ${value("design2")}

Article 3:
${value("citation3")}
Evidence Level/Study Design: ${value("design3")}

5. REFLECTION
Challenges:
${value("challenges")}

Strategies that helped refine the search:
${value("strategies")}
`;
  }

  el("nextBtn").addEventListener("click", ()=>{
    if(currentStep < totalSteps){
      if(!validateStep(currentStep)) return;
      showStep(currentStep + 1);
    } else {
      renderSummary();
      el("validationMsg").textContent = "Review complete. Use Print / Save as PDF to create your submission file.";
      el("validationMsg").className = "status good no-print";
    }
  });

  el("backBtn").addEventListener("click", ()=>{
    if(currentStep > 1) showStep(currentStep - 1);
  });

  el("printBtn").addEventListener("click", ()=>{
    renderSummary();
    window.print();
  });

  el("downloadBtn").addEventListener("click", ()=>{
    const blob = new Blob([textExport()], {type:"text/plain;charset=utf-8"});
    const url = URL.createObjectURL(blob);
    const a = document.createElement("a");
    const safe = (value("studentName") || "student").replace(/[^a-z0-9]+/gi,"_");
    a.href = url;
    a.download = `${safe}_Evidence_Hunt.txt`;
    document.body.appendChild(a);
    a.click();
    a.remove();
    URL.revokeObjectURL(url);
  });

  // Keep student work in memory only; no external data is sent anywhere.
  if(!value("activityDate")){
    const d = new Date();
    const yyyy = d.getFullYear();
    const mm = String(d.getMonth()+1).padStart(2,"0");
    const dd = String(d.getDate()).padStart(2,"0");
    el("activityDate").value = `${yyyy}-${mm}-${dd}`;
  }

  showStep(1);
})();
</script>
</body>
</html>
