<svg xmlns="http://www.w3.org/2000/svg" viewBox="0 0 820 340" width="820" height="340">
  <defs>
    <!-- Dithered Monochrome Pattern -->
    <pattern id="dither" width="6" height="6" patternUnits="userSpaceOnUse">
      <rect width="6" height="6" fill="#0a0a0a"/>
      <rect x="0" y="0" width="3" height="3" fill="#171717"/>
      <rect x="3" y="3" width="3" height="3" fill="#171717"/>
    </pattern>

    <!-- Scanline Overlay Pattern -->
    <pattern id="scanlines" width="4" height="4" patternUnits="userSpaceOnUse">
      <rect width="4" height="2" fill="rgba(255,255,255,0)"/>
      <rect y="2" width="4" height="2" fill="rgba(0,0,0,0.32)"/>
    </pattern>

    <!-- Viewport Clip Path for Sliding Panels -->
    <clipPath id="viewport-clip">
      <rect x="28" y="64" width="764" height="224"/>
    </clipPath>
  </defs>

  <!-- Outer Handheld Console Bezel -->
  <rect x="0" y="0" width="820" height="340" fill="url(#dither)"/>
  <rect x="8" y="8" width="804" height="324" fill="#141414" stroke="#fafafa" stroke-width="4"/>
  <rect x="16" y="16" width="788" height="308" fill="#0a0a0a" stroke="#737373" stroke-width="2"/>

  <!-- Top Console Status Header -->
  <rect x="28" y="24" width="764" height="32" fill="#fafafa"/>
  <text x="40" y="45" font-family="monospace" font-size="14" font-weight="bold" fill="#0a0a0a">
    SRK-OS v1.0 // R. SIVA RAMA KRISHNA — MONOCHROME 8-BIT TERMINAL
  </text>
  <text x="695" y="45" font-family="monospace" font-size="13" font-weight="bold" fill="#0a0a0a">
    [BAT: 100%]
  </text>

  <!-- Fixed-Size Sliding Viewport -->
  <g clip-path="url(#viewport-clip)">
    <rect x="28" y="64" width="764" height="224" fill="#121212"/>

    <!-- SLIDE 01: PLAYER PROFILE (0s - 4s, slides out left at 4s) -->
    <g>
      <animateTransform attributeName="transform" type="translate"
        values="0,0; 0,0; -780,0; -780,0; 780,0; 0,0"
        keyTimes="0; 0.18; 0.20; 0.98; 0.981; 1"
        dur="20s" repeatCount="indefinite"/>

      <rect x="42" y="76" width="736" height="200" fill="#1c1c1c" stroke="#fafafa" stroke-width="2"/>
      <rect x="42" y="76" width="210" height="28" fill="#fafafa"/>
      <text x="52" y="95" font-family="monospace" font-size="13" font-weight="bold" fill="#0a0a0a">
        ▶ [01] PLAYER PROFILE
      </text>
      <text x="620" y="95" font-family="monospace" font-size="12" fill="#a3a3a3">
        SCREEN 01 / 05
      </text>

      <!-- Pixel Avatar Frame -->
      <rect x="62" y="118" width="84" height="84" fill="#0a0a0a" stroke="#d4d4d4" stroke-width="2"/>
      <rect x="86" y="128" width="36" height="10" fill="#fafafa"/>
      <rect x="80" y="138" width="48" height="28" fill="#d4d4d4"/>
      <rect x="90" y="146" width="8" height="8" fill="#0a0a0a"/>
      <rect x="110" y="146" width="8" height="8" fill="#0a0a0a"/>
      <rect x="76" y="170" width="56" height="24" fill="#737373"/>
      <rect x="94" y="170" width="20" height="24" fill="#fafafa"/>

      <!-- Profile Details -->
      <text x="166" y="136" font-family="monospace" font-size="17" font-weight="bold" fill="#fafafa">
        AI/ML &amp; BACKEND SOFTWARE ENGINEER
      </text>
      <text x="166" y="160" font-family="monospace" font-size="13" fill="#d4d4d4">
        EDUCATION : B.E. CSE — Chandigarh University (2022–2025 | CGPA: 7.53)
      </text>
      <text x="166" y="182" font-family="monospace" font-size="13" fill="#d4d4d4">
        LOCATION  : Hyderabad, Telangana, India
      </text>
      <text x="166" y="204" font-family="monospace" font-size="13" fill="#fafafa">
        FOCUS     : Python, Deep Learning, Computer Vision, LLMs/RAG, REST APIs
      </text>
      <rect x="62" y="218" width="696" height="42" fill="#0a0a0a" stroke="#737373" stroke-width="1.5"/>
      <text x="76" y="244" font-family="monospace" font-size="12" fill="#d4d4d4">
        &gt; MOTTO: "Master low-level algorithmic logic before relying on abstractions."
      </text>
    </g>

    <!-- SLIDE 02: ARSENAL / SKILLS (Slides in from right at 3.6s - 4.0s) -->
    <g transform="translate(780,0)">
      <animateTransform attributeName="transform" type="translate"
        values="780,0; 780,0; 0,0; 0,0; -780,0; -780,0"
        keyTimes="0; 0.18; 0.20; 0.38; 0.40; 1"
        dur="20s" repeatCount="indefinite"/>

      <rect x="42" y="76" width="736" height="200" fill="#1c1c1c" stroke="#fafafa" stroke-width="2"/>
      <rect x="42" y="76" width="220" height="28" fill="#fafafa"/>
      <text x="52" y="95" font-family="monospace" font-size="13" font-weight="bold" fill="#0a0a0a">
        ▶ [02] TECH ARSENAL
      </text>
      <text x="620" y="95" font-family="monospace" font-size="12" fill="#a3a3a3">
        SCREEN 02 / 05
      </text>

      <!-- Monochrome Stat Bars -->
      <text x="64" y="132" font-family="monospace" font-size="13" font-weight="bold" fill="#fafafa">
        PYTHON &amp; ALGORITHMS  [████████████████████] 95%
      </text>
      <text x="64" y="160" font-family="monospace" font-size="13" font-weight="bold" fill="#fafafa">
        DEEP LEARNING &amp; CV   [██████████████████░░] 90%
      </text>
      <text x="64" y="188" font-family="monospace" font-size="13" font-weight="bold" fill="#fafafa">
        NLP, LLMs &amp; RAG      [█████████████████░░░] 85%
      </text>
      <text x="64" y="216" font-family="monospace" font-size="13" font-weight="bold" fill="#fafafa">
        SQL, APIS &amp; CLOUD    [█████████████████░░░] 85%
      </text>

      <rect x="62" y="232" width="696" height="32" fill="#0a0a0a" stroke="#737373" stroke-width="1.5"/>
      <text x="76" y="253" font-family="monospace" font-size="12" fill="#d4d4d4">
        STACK: PyTorch | TensorFlow | YOLOv5 | OpenCV | T5 | FastAPI | SQL | Docker
      </text>
    </g>

    <!-- SLIDE 03: QUEST LOG / PROJECTS (Slides in from right at 7.6s - 8.0s) -->
    <g transform="translate(780,0)">
      <animateTransform attributeName="transform" type="translate"
        values="780,0; 780,0; 0,0; 0,0; -780,0; -780,0"
        keyTimes="0; 0.38; 0.40; 0.58; 0.60; 1"
        dur="20s" repeatCount="indefinite"/>

      <rect x="42" y="76" width="736" height="200" fill="#1c1c1c" stroke="#fafafa" stroke-width="2"/>
      <rect x="42" y="76" width="210" height="28" fill="#fafafa"/>
      <text x="52" y="95" font-family="monospace" font-size="13" font-weight="bold" fill="#0a0a0a">
        ▶ [03] QUEST LOG
      </text>
      <text x="620" y="95" font-family="monospace" font-size="12" fill="#a3a3a3">
        SCREEN 03 / 05
      </text>

      <text x="64" y="130" font-family="monospace" font-size="13" font-weight="bold" fill="#fafafa">
        [BOSS-01] Lung Cancer Detection Using ML (Published 2025) — 89% Val Acc
      </text>
      <text x="64" y="158" font-family="monospace" font-size="13" fill="#d4d4d4">
        [QUEST-2] Automatic Number Plate Recognition (YOLOv5/OpenCV) — 95%+ Acc
      </text>
      <text x="64" y="186" font-family="monospace" font-size="13" fill="#d4d4d4">
        [QUEST-3] Text Summarization &amp; Extraction (T5 Seq2Seq) — ROUGE Tuned
      </text>
      <text x="64" y="214" font-family="monospace" font-size="13" fill="#d4d4d4">
        [QUEST-4] Local RAG Chatbot (Ollama) &amp; AI Voice Assistant (STT/TTS)
      </text>

      <rect x="62" y="232" width="696" height="32" fill="#0a0a0a" stroke="#737373" stroke-width="1.5"/>
      <text x="76" y="253" font-family="monospace" font-size="12" fill="#fafafa">
        &gt; ALL QUESTS VERIFIED &amp; DEPLOYED ON GITHUB.COM/SIVARAMAKRISHNA1146
      </text>
    </g>

    <!-- SLIDE 04: TROPHIES & CERTS (Slides in from right at 11.6s - 12.0s) -->
    <g transform="translate(780,0)">
      <animateTransform attributeName="transform" type="translate"
        values="780,0; 780,0; 0,0; 0,0; -780,0; -780,0"
        keyTimes="0; 0.58; 0.60; 0.78; 0.80; 1"
        dur="20s" repeatCount="indefinite"/>

      <rect x="42" y="76" width="736" height="200" fill="#1c1c1c" stroke="#fafafa" stroke-width="2"/>
      <rect x="42" y="76" width="230" height="28" fill="#fafafa"/>
      <text x="52" y="95" font-family="monospace" font-size="13" font-weight="bold" fill="#0a0a0a">
        ▶ [04] ACHIEVEMENTS
      </text>
      <text x="620" y="95" font-family="monospace" font-size="12" fill="#a3a3a3">
        SCREEN 04 / 05
      </text>

      <text x="64" y="132" font-family="monospace" font-size="13" font-weight="bold" fill="#fafafa">
        ★ Advanced Machine Learning on Google Cloud — Google Cloud
      </text>
      <text x="64" y="160" font-family="monospace" font-size="13" fill="#d4d4d4">
        ★ Computer Vision Fundamentals with Google Cloud — Google Cloud
      </text>
      <text x="64" y="188" font-family="monospace" font-size="13" fill="#d4d4d4">
        ★ Databases and SQL for Data Science with Python — IBM
      </text>
      <text x="64" y="216" font-family="monospace" font-size="13" fill="#d4d4d4">
        ★ Python for Data Science, AI &amp; Development — IBM
      </text>

      <rect x="62" y="232" width="696" height="32" fill="#0a0a0a" stroke="#737373" stroke-width="1.5"/>
      <text x="76" y="253" font-family="monospace" font-size="12" fill="#fafafa">
        HACKATHON: CISCO CODATHON AP (Cisco Networking Academy)
      </text>
    </g>

    <!-- SLIDE 05: WARP LINK / CONTACT (Slides in from right at 15.6s - 16.0s) -->
    <g transform="translate(780,0)">
      <animateTransform attributeName="transform" type="translate"
        values="780,0; 780,0; 0,0; 0,0; -780,0"
        keyTimes="0; 0.78; 0.80; 0.98; 1"
        dur="20s" repeatCount="indefinite"/>

      <rect x="42" y="76" width="736" height="200" fill="#1c1c1c" stroke="#fafafa" stroke-width="2"/>
      <rect x="42" y="76" width="210" height="28" fill="#fafafa"/>
      <text x="52" y="95" font-family="monospace" font-size="13" font-weight="bold" fill="#0a0a0a">
        ▶ [05] WARP LINK
      </text>
      <text x="620" y="95" font-family="monospace" font-size="12" fill="#a3a3a3">
        SCREEN 05 / 05
      </text>

      <text x="64" y="136" font-family="monospace" font-size="15" font-weight="bold" fill="#fafafa">
        STATUS : OPEN FOR SOFTWARE ENGINEER &amp; AI/ML ROLES
      </text>
      <text x="64" y="168" font-family="monospace" font-size="14" fill="#d4d4d4">
        EMAIL  : Sivaramakrishnarachakulla@gmail.com
      </text>
      <text x="64" y="196" font-family="monospace" font-size="14" fill="#d4d4d4">
        PHONE  : +91-9121141146
      </text>
      <text x="64" y="224" font-family="monospace" font-size="14" fill="#fafafa">
        GITHUB : https://github.com/Sivaramakrishna1146
      </text>

      <rect x="62" y="238" width="696" height="28" fill="#fafafa"/>
      <text x="76" y="257" font-family="monospace" font-size="12" font-weight="bold" fill="#0a0a0a">
        &gt; CLICK ANY MONOCHROME OPTION BOX BELOW TO INSPECT FULL LOGS
      </text>
    </g>

    <!-- Subtle CRT Scanline Layer -->
    <rect x="28" y="64" width="764" height="224" fill="url(#scanlines)" pointer-events="none"/>
  </g>

  <!-- Bottom Console Menu Bar -->
  <rect x="28" y="294" width="764" height="22" fill="#1c1c1c" stroke="#737373" stroke-width="1"/>
  <text x="40" y="309" font-family="monospace" font-size="11" fill="#fafafa">
    [01] PROFILE   |   [02] ARSENAL   |   [03] QUESTS   |   [04] TROPHIES   |   [05] CONTACT
  </text>
  <text x="655" y="309" font-family="monospace" font-size="11" fill="#a3a3a3">
    AUTO-SLIDE: R→L
  </text>
</svg>
