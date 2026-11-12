<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8" />
  <meta name="viewport" content="width=device-width, initial-scale=1.0" />
  <title>SRK-OS v1.0 | R. Siva Rama Krishna - Monochrome 8-Bit Portfolio</title>
  <!-- Retro 8-bit pixel & crisp monospace fonts -->
  <link rel="preconnect" href="https://fonts.googleapis.com">
  <link rel="preconnect" href="https://fonts.gstatic.com" crossorigin>
  <link href="https://fonts.googleapis.com/css2?family=JetBrains+Mono:wght@400;600;700&family=Press+Start+2P&display=swap" rel="stylesheet">
  <script src="https://cdn.tailwindcss.com"></script>
  <style>
    :root {
      --mono-black: #0a0a0a;
      --mono-dark: #1c1c1c;
      --mono-panel: #262626;
      --mono-mid: #737373;
      --mono-light: #d4d4d4;
      --mono-white: #fafafa;
    }

    * {
      box-sizing: border-box;
      -webkit-tap-highlight-color: transparent;
    }

    body, html {
      margin: 0;
      padding: 0;
      min-height: 100vh;
      background-color: var(--mono-black);
      color: var(--mono-white);
      font-family: 'JetBrains Mono', monospace;
      overflow-x: hidden;
    }

    .font-pixel {
      font-family: 'Press Start 2P', monospace;
    }

    /* Subtle Dithered Background Pattern */
    .dither-bg {
      background-color: #0d0d0d;
      background-image:
        linear-gradient(45deg, #161616 25%, transparent 25%),
        linear-gradient(-45deg, #161616 25%, transparent 25%),
        linear-gradient(45deg, transparent 75%, #161616 75%),
        linear-gradient(-45deg, transparent 75%, #161616 75%);
      background-size: 8px 8px;
      background-position: 0 0, 0 4px, 4px -4px, -4px 0;
    }

    /* Classic 8-Bit Double Pixel Frame */
    .pixel-frame {
      background-color: var(--mono-dark);
      border: 3px solid var(--mono-white);
      box-shadow:
        0 0 0 3px var(--mono-black),
        0 0 0 6px var(--mono-mid),
        6px 6px 0 6px rgba(0, 0, 0, 0.85);
      position: relative;
    }

    .pixel-subframe {
      background-color: var(--mono-panel);
      border: 2px solid var(--mono-light);
      box-shadow: 3px 3px 0 var(--mono-black);
    }

    /* Retro Interactive Menu Option */
    .menu-option {
      border: 2px solid transparent;
      transition: background-color 0.08s steps(1), color 0.08s steps(1);
      cursor: pointer;
    }

    .menu-option:hover {
      background-color: var(--mono-panel);
      border-color: var(--mono-mid);
    }

    .menu-option.active {
      background-color: var(--mono-white);
      color: var(--mono-black);
      border-color: var(--mono-white);
      box-shadow: 4px 4px 0 var(--mono-mid);
    }

    .menu-option.active .cursor-arrow {
      opacity: 1;
      animation: cursorBlink 0.7s infinite steps(1);
    }

    .cursor-arrow {
      opacity: 0;
      display: inline-block;
    }

    @keyframes cursorBlink {
      0%, 49% { opacity: 1; }
      50%, 100% { opacity: 0; }
    }

    /* Retro Monochrome Action Buttons */
    .mono-btn {
      background-color: var(--mono-dark);
      color: var(--mono-white);
      border: 2px solid var(--mono-white);
      box-shadow: 3px 3px 0 var(--mono-mid);
      cursor: pointer;
      transition: transform 0.06s ease, background-color 0.06s;
    }

    .mono-btn:hover {
      background-color: var(--mono-white);
      color: var(--mono-black);
    }

    .mono-btn:active {
      transform: translate(2px, 2px);
      box-shadow: 1px 1px 0 var(--mono-mid);
    }

    /* Monochrome Pixel Stat Bar */
    .stat-track {
      width: 100%;
      height: 14px;
      background-color: var(--mono-black);
      border: 2px solid var(--mono-light);
      padding: 2px;
      display: flex;
      gap: 2px;
    }

    .stat-segment {
      height: 100%;
      flex: 1;
      background-color: var(--mono-white);
    }

    .stat-segment.empty {
      background-color: var(--mono-panel);
    }

    /* Optional CRT Scanlines Overlay */
    .scanlines::after {
      content: "";
      position: fixed;
      inset: 0;
      background: repeating-linear-gradient(
        to bottom,
        rgba(255, 255, 255, 0) 0px,
        rgba(255, 255, 255, 0) 2px,
        rgba(0, 0, 0, 0.28) 3px,
        rgba(0, 0, 0, 0.28) 4px
      );
      pointer-events: none;
      z-index: 50;
    }

    /* Content Fade-In Step Animation */
    @keyframes pixelReveal {
      0% { opacity: 0; transform: translateY(4px); }
      100% { opacity: 1; transform: translateY(0); }
    }
    .panel-reveal {
      animation: pixelReveal 0.16s steps(3) forwards;
    }

    /* Custom Monochrome Scrollbar */
    ::-webkit-scrollbar {
      width: 8px;
      height: 8px;
    }
    ::-webkit-scrollbar-track {
      background: var(--mono-black);
      border-left: 1px solid var(--mono-mid);
    }
    ::-webkit-scrollbar-thumb {
      background: var(--mono-light);
      border: 1px solid var(--mono-black);
    }
  </style>
</head>
<body id="app-body" class="dither-bg scanlines flex flex-col justify-between p-3 sm:p-6 md:p-8">

  <!-- MAIN CONSOLE SHELL -->
  <div class="max-w-6xl w-full mx-auto flex-1 flex flex-col gap-6">

    <!-- TOP RETRO STATUS HEADER -->
    <header class="pixel-frame px-4 py-3 sm:px-6 sm:py-4 flex flex-wrap items-center justify-between gap-4">
      <div class="flex items-center gap-3">
        <!-- Monochrome 8-Bit Cartridge / Terminal Icon -->
        <div class="w-9 h-9 sm:w-11 sm:h-11 bg-white text-black flex items-center justify-center font-pixel text-xs sm:text-sm border-2 border-neutral-400 shrink-0">
          SRK
        </div>
        <div>
          <h1 class="font-pixel text-[11px] sm:text-sm md:text-base tracking-wide text-white">
            R. SIVA RAMA KRISHNA
          </h1>
          <p class="text-xs sm:text-sm text-neutral-300 mt-1">
            AI/ML &amp; BACKEND SOFTWARE ENGINEER // HYDERABAD, IN
          </p>
        </div>
      </div>

      <!-- Hardware Toggle Controls -->
      <div class="flex items-center gap-2 sm:gap-3">
        <button id="crt-toggle" class="mono-btn font-pixel text-[9px] sm:text-[10px] px-2.5 py-2" title="Toggle CRT Scanlines">
          CRT: ON
        </button>
        <button id="sfx-toggle" class="mono-btn font-pixel text-[9px] sm:text-[10px] px-2.5 py-2" title="Toggle Retro Menu Blips">
          SFX: ON
        </button>
      </div>
    </header>

    <!-- TWO-COLUMN RETRO CONSOLE INTERFACE -->
    <main class="flex-1 grid grid-cols-1 lg:grid-cols-12 gap-6 items-start">

      <!-- LEFT COLUMN: CLASSIC 8-BIT OPTION MENU -->
      <aside class="lg:col-span-4 pixel-frame p-4 sm:p-5 flex flex-col justify-between">
        <div>
          <div class="flex items-center justify-between border-b-2 border-neutral-500 pb-2.5 mb-3">
            <span class="font-pixel text-[10px] sm:text-xs text-neutral-200">SELECT OPTION</span>
            <span class="font-pixel text-[9px] text-neutral-400">[01-05]</span>
          </div>

          <ul id="menu-list" class="space-y-2" role="listbox" aria-label="Portfolio Sections">
            <li>
              <button
                type="button"
                data-section="profile"
                class="menu-option active w-full text-left px-3 py-3 font-pixel text-[10px] sm:text-[11px] flex items-center justify-between"
              >
                <span class="flex items-center gap-2">
                  <span class="cursor-arrow">▶</span>
                  <span>01. PLAYER PROFILE</span>
                </span>
                <span class="text-[9px] opacity-75">BIO</span>
              </button>
            </li>
            <li>
              <button
                type="button"
                data-section="inventory"
                class="menu-option w-full text-left px-3 py-3 font-pixel text-[10px] sm:text-[11px] flex items-center justify-between"
              >
                <span class="flex items-center gap-2">
                  <span class="cursor-arrow">▶</span>
                  <span>02. INVENTORY</span>
                </span>
                <span class="text-[9px] opacity-75">SKILLS</span>
              </button>
            </li>
            <li>
              <button
                type="button"
                data-section="quests"
                class="menu-option w-full text-left px-3 py-3 font-pixel text-[10px] sm:text-[11px] flex items-center justify-between"
              >
                <span class="flex items-center gap-2">
                  <span class="cursor-arrow">▶</span>
                  <span>03. QUEST LOG</span>
                </span>
                <span class="text-[9px] opacity-75">WORK</span>
              </button>
            </li>
            <li>
              <button
                type="button"
                data-section="achievements"
                class="menu-option w-full text-left px-3 py-3 font-pixel text-[10px] sm:text-[11px] flex items-center justify-between"
              >
                <span class="flex items-center gap-2">
                  <span class="cursor-arrow">▶</span>
                  <span>04. ACHIEVEMENTS</span>
                </span>
                <span class="text-[9px] opacity-75">CERTS</span>
              </button>
            </li>
            <li>
              <button
                type="button"
                data-section="contact"
                class="menu-option w-full text-left px-3 py-3 font-pixel text-[10px] sm:text-[11px] flex items-center justify-between"
              >
                <span class="flex items-center gap-2">
                  <span class="cursor-arrow">▶</span>
                  <span>05. WARP LINK</span>
                </span>
                <span class="text-[9px] opacity-75">COMM</span>
              </button>
            </li>
          </ul>
        </div>

        <!-- Retro D-Pad / Controls Guide -->
        <div class="mt-6 pt-3 border-t-2 border-neutral-600 text-xs text-neutral-300 space-y-2">
          <div class="flex items-center justify-between">
            <span class="font-pixel text-[9px] text-neutral-400">CONTROLS</span>
            <span class="font-pixel text-[9px] text-white">READY ●</span>
          </div>
          <p class="text-[11px] leading-relaxed text-neutral-300">
            Click any option or use <span class="bg-neutral-800 border border-neutral-500 px-1.5 py-0.5 text-white">↑</span> <span class="bg-neutral-800 border border-neutral-500 px-1.5 py-0.5 text-white">↓</span> arrow keys to inspect data.
          </p>
          <!-- Mobile / Quick Prev-Next D-Pad -->
          <div class="grid grid-cols-2 gap-2 pt-1">
            <button id="btn-prev" type="button" class="mono-btn font-pixel text-[9px] py-2 text-center">
              ▲ PREV
            </button>
            <button id="btn-next" type="button" class="mono-btn font-pixel text-[9px] py-2 text-center">
              ▼ NEXT
            </button>
          </div>
        </div>
      </aside>

      <!-- RIGHT COLUMN: DYNAMIC DATA VIEWPORT -->
      <section class="lg:col-span-8 pixel-frame p-5 sm:p-7 min-h-[470px] flex flex-col justify-between">
        <div>
          <!-- Section Title Header -->
          <div class="flex flex-wrap items-center justify-between gap-2 border-b-2 border-white pb-3 mb-5">
            <div class="flex items-center gap-2.5">
              <span id="stage-badge" class="bg-white text-black font-pixel text-[9px] sm:text-[10px] px-2 py-1">
                STAGE 01
              </span>
              <h2 id="stage-title" class="font-pixel text-xs sm:text-sm md:text-base text-white">
                PLAYER PROFILE
              </h2>
            </div>
            <span id="stage-meta" class="font-pixel text-[9px] text-neutral-400">
              MEM: 64KB OK
            </span>
          </div>

          <!-- Dynamic Details Container -->
          <div id="stage-content" class="panel-reveal space-y-5 text-sm sm:text-[15px] leading-relaxed text-neutral-200">
            <!-- Populated via JS -->
          </div>
        </div>

        <!-- Bottom Console Footer Bar -->
        <div class="mt-8 pt-3 border-t-2 border-neutral-700 flex flex-wrap items-center justify-between gap-2 text-xs text-neutral-400">
          <span class="font-pixel text-[9px]">SYS: MONOCHROME-8BIT</span>
          <span id="footer-hint" class="font-pixel text-[9px] text-neutral-300">PRESS [↑/↓] TO SWITCH</span>
        </div>
      </section>

    </main>
  </div>

  <script>
    /**
     * MONOCHROME PORTFOLIO CONTENT DATA
     */
    const SECTIONS = {
      profile: {
        badge: "STAGE 01",
        title: "PLAYER PROFILE",
        meta: "CLASS: AI/ML & BACKEND",
        html: `
          <!-- Character Sheet Box -->
          <div class="pixel-subframe p-4 sm:p-5 flex flex-col sm:flex-row items-start sm:items-center gap-4">
            <!-- Crisp Monochrome 8-Bit Pixel Avatar SVG -->
            <div class="w-20 h-20 bg-black border-2 border-white p-1.5 shrink-0 flex items-center justify-center">
              <svg viewBox="0 0 16 16" class="w-full h-full" shape-rendering="crispEdges">
                <rect x="4" y="1" width="8" height="2" fill="#fafafa"/>
                <rect x="3" y="3" width="10" height="2" fill="#d4d4d4"/>
                <rect x="4" y="5" width="8" height="5" fill="#fafafa"/>
                <rect x="5" y="6" width="2" height="2" fill="#0a0a0a"/>
                <rect x="9" y="6" width="2" height="2" fill="#0a0a0a"/>
                <rect x="6" y="9" width="4" height="1" fill="#262626"/>
                <rect x="3" y="11" width="10" height="4" fill="#737373"/>
                <rect x="6" y="11" width="4" height="4" fill="#fafafa"/>
              </svg>
            </div>

            <div class="space-y-1.5 flex-1">
              <div class="flex flex-wrap items-center justify-between gap-2">
                <span class="font-pixel text-xs sm:text-sm text-white">R. SIVA RAMA KRISHNA</span>
                <span class="border border-white px-2 py-0.5 font-pixel text-[9px] text-white">B.E. CSE (2025)</span>
              </div>
              <p class="text-neutral-300 font-semibold">AI/ML Engineer &amp; Backend Software Developer</p>
              <p class="text-xs text-neutral-400">Location: Hyderabad, India &bull; Focus: Python, Deep Learning, REST APIs, SQL</p>
            </div>
          </div>

          <!-- Core Engineering Philosophy -->
          <div class="space-y-2">
            <h3 class="font-pixel text-[11px] text-white border-l-4 border-white pl-2.5">
              ENGINEERING PHILOSOPHY
            </h3>
            <p class="text-neutral-200">
              Passionate AI &amp; ML Computer Science graduate specializing in building low-latency backend services, RESTful APIs, and end-to-end deep learning pipelines. Committed to mastering low-level algorithmic fundamentals and data structures rather than relying blindly on high-level abstractions.
            </p>
          </div>

          <!-- Education Timeline -->
          <div class="space-y-2.5">
            <h3 class="font-pixel text-[11px] text-white border-l-4 border-white pl-2.5">
              EDUCATION LOG
            </h3>
            <div class="grid grid-cols-1 md:grid-cols-2 gap-3">
              <div class="pixel-subframe p-3.5">
                <div class="flex justify-between items-center text-xs text-neutral-400 mb-1">
                  <span>2022 – 2025</span>
                  <span class="bg-white text-black px-1.5 py-0.5 font-bold">CGPA: 7.53</span>
                </div>
                <div class="font-bold text-white">B.E. in Computer Science Engineering</div>
                <div class="text-xs text-neutral-300 mt-0.5">Chandigarh University, Chandigarh</div>
              </div>

              <div class="pixel-subframe p-3.5">
                <div class="flex justify-between items-center text-xs text-neutral-400 mb-1">
                  <span>2019 – 2022</span>
                  <span class="bg-white text-black px-1.5 py-0.5 font-bold">83.4%</span>
                </div>
                <div class="font-bold text-white">Diploma in Computer Science Eng.</div>
                <div class="text-xs text-neutral-300 mt-0.5">AANM &amp; VVRSR Polytechnic College</div>
              </div>
            </div>
          </div>
        `
      },

      inventory: {
        badge: "STAGE 02",
        title: "INVENTORY & STATS",
        meta: "EQUIPPED: 4 MODULES",
        html: `
          <!-- Monochrome Stat Bars -->
          <div class="grid grid-cols-1 sm:grid-cols-2 gap-4">
            <div class="pixel-subframe p-3.5 space-y-2">
              <div class="flex justify-between font-pixel text-[10px]">
                <span>PYTHON &amp; ALGORITHMS</span>
                <span>95%</span>
              </div>
              <div class="stat-track">${renderSegments(10, 10)}</div>
              <p class="text-xs text-neutral-400">OOP, Manual Logic, Data Structures, Scripting</p>
            </div>

            <div class="pixel-subframe p-3.5 space-y-2">
              <div class="flex justify-between font-pixel text-[10px]">
                <span>DEEP LEARNING &amp; CV</span>
                <span>90%</span>
              </div>
              <div class="stat-track">${renderSegments(9, 10)}</div>
              <p class="text-xs text-neutral-400">PyTorch, TensorFlow, Keras, CNNs, YOLOv5, OpenCV</p>
            </div>

            <div class="pixel-subframe p-3.5 space-y-2">
              <div class="flex justify-between font-pixel text-[10px]">
                <span>NLP, LLMs &amp; RAG</span>
                <span>85%</span>
              </div>
              <div class="stat-track">${renderSegments(8, 10)}</div>
              <p class="text-xs text-neutral-400">T5 Seq2Seq, Ollama, TinyLlama, Vector Search</p>
            </div>

            <div class="pixel-subframe p-3.5 space-y-2">
              <div class="flex justify-between font-pixel text-[10px]">
                <span>SQL, APIS &amp; CLOUD</span>
                <span>85%</span>
              </div>
              <div class="stat-track">${renderSegments(8, 10)}</div>
              <p class="text-xs text-neutral-400">REST APIs, FastAPI, Docker, AWS/GCP, TCP/IP</p>
            </div>
          </div>

          <!-- Categorized Skill Tags -->
          <div class="space-y-3 pt-1">
            <div>
              <div class="font-pixel text-[10px] text-neutral-300 mb-2">[CORE LANGUAGES &amp; DATABASES]</div>
              <div class="flex flex-wrap gap-2 text-xs">
                ${renderTags(['Python', 'SQL', 'SQLite', 'C', 'JavaScript', 'HTML5', 'CSS3', 'Bootstrap'])}
              </div>
            </div>

            <div>
              <div class="font-pixel text-[10px] text-neutral-300 mb-2">[AI, COMPUTER VISION &amp; NLP]</div>
              <div class="flex flex-wrap gap-2 text-xs">
                ${renderTags(['PyTorch', 'TensorFlow', 'Keras', 'CNNs', 'YOLOv5', 'OpenCV', 'Scikit-learn', 'T5 Transformers', 'RAG Pipelines', 'Pandas', 'NumPy'])}
              </div>
            </div>

            <div>
              <div class="font-pixel text-[10px] text-neutral-300 mb-2">[BACKEND, CLOUD &amp; NETWORKING]</div>
              <div class="flex flex-wrap gap-2 text-xs">
                ${renderTags(['REST APIs', 'FastAPI', 'Docker', 'Kubernetes', 'AWS', 'Linux (Ubuntu)', 'Git / GitHub', 'TCP/IP', 'DNS / DHCP'])}
              </div>
            </div>
          </div>
        `
      },

      quests: {
        badge: "STAGE 03",
        title: "QUEST LOG & RESEARCH",
        meta: "COMPLETED: 04",
        html: `
          <div class="space-y-4">
            <!-- Quest 01: Published Research -->
            <article class="pixel-subframe p-4 space-y-2">
              <div class="flex flex-wrap items-center justify-between gap-2">
                <span class="bg-white text-black font-pixel text-[9px] px-2 py-0.5">BOSS QUEST // PUBLISHED 2025</span>
                <span class="font-pixel text-[10px] text-white">VAL ACCURACY: 89%</span>
              </div>
              <h3 class="font-bold text-base text-white">Lung Cancer Detection Using Machine Learning</h3>
              <p class="text-xs sm:text-sm text-neutral-300">
                Architected a Convolutional Neural Network (CNN) to classify lung histopathology scans into Adenocarcinoma, Squamous Cell Carcinoma, and Normal Tissue. Applied OpenCV resizing, normalization, and augmentation, validating diagnostic reliability with Confusion Matrix and F1-Score metrics.
              </p>
              <div class="text-xs text-neutral-400 pt-1">
                TECH: Python &bull; Keras &bull; TensorFlow &bull; OpenCV &bull; Scikit-learn &bull; Seaborn
              </div>
            </article>

            <!-- Quest 02: ANPR -->
            <article class="pixel-subframe p-4 space-y-2">
              <div class="flex flex-wrap items-center justify-between gap-2">
                <span class="border border-white text-white font-pixel text-[9px] px-2 py-0.5">QUEST 02 // REAL-TIME CV</span>
                <span class="font-pixel text-[10px] text-white">DETECTION: 95%+</span>
              </div>
              <h3 class="font-bold text-base text-white">Automatic Number Plate Recognition (ANPR)</h3>
              <p class="text-xs sm:text-sm text-neutral-300">
                Built a real-time license plate detection pipeline for varied lighting and traffic angles. Annotated a custom dataset, trained YOLOv5 for high-speed bounding-box localization, and integrated OpenCV for live frame deployment.
              </p>
              <div class="text-xs text-neutral-400 pt-1">
                TECH: Python &bull; YOLOv5 &bull; OpenCV &bull; TensorFlow &bull; Matplotlib
              </div>
            </article>

            <!-- Quest 03: Text Summarization -->
            <article class="pixel-subframe p-4 space-y-2">
              <div class="flex flex-wrap items-center justify-between gap-2">
                <span class="border border-white text-white font-pixel text-[9px] px-2 py-0.5">QUEST 03 // SEQ2SEQ NLP</span>
                <span class="font-pixel text-[10px] text-neutral-300">ROUGE OPTIMIZED</span>
              </div>
              <h3 class="font-bold text-base text-white">Text Summarization &amp; Insight Extraction</h3>
              <p class="text-xs sm:text-sm text-neutral-300">
                Designed a Seq2Seq neural pipeline powered by T5 Transformers to condense large documents into context-aware summaries. Implemented tokenization, stopword removal, and lemmatization with hyperparameter tuning for higher ROUGE scores.
              </p>
              <div class="text-xs text-neutral-400 pt-1">
                TECH: Python &bull; T5 Transformer &bull; NLP &bull; Pandas &bull; NumPy
              </div>
            </article>

            <!-- Quest 04: Local RAG & Voice Assistant -->
            <article class="pixel-subframe p-4 space-y-2">
              <div class="flex flex-wrap items-center justify-between gap-2">
                <span class="border border-white text-white font-pixel text-[9px] px-2 py-0.5">QUEST 04 // GEN-AI &amp; VOICE</span>
                <span class="font-pixel text-[10px] text-neutral-300">LOCAL + API</span>
              </div>
              <h3 class="font-bold text-base text-white">Local RAG Chatbot &amp; AI Voice Assistant</h3>
              <p class="text-xs sm:text-sm text-neutral-300">
                Developed a private Retrieval-Augmented Generation (RAG) document QA system using Ollama/TinyLlama alongside a voice-enabled assistant integrating SpeechRecognition (STT), offline Pyttsx3 (TTS), and live REST APIs.
              </p>
              <div class="text-xs text-neutral-400 pt-1">
                TECH: Python &bull; Ollama &bull; TinyLlama &bull; SpeechRecognition &bull; Pyttsx3 &bull; REST APIs
              </div>
            </article>
          </div>
        `
      },

      achievements: {
        badge: "STAGE 04",
        title: "ACHIEVEMENTS & CERTS",
        meta: "UNLOCKED: 06",
        html: `
          <div class="space-y-4">
            <h3 class="font-pixel text-[11px] text-white border-l-4 border-white pl-2.5">
              VERIFIED CERTIFICATIONS
            </h3>

            <div class="grid grid-cols-1 sm:grid-cols-2 gap-3">
              <div class="pixel-subframe p-3.5 space-y-1">
                <div class="font-pixel text-[9px] text-neutral-400">[IBM CREDENTIAL]</div>
                <div class="font-bold text-white">Python for Data Science, AI &amp; Development</div>
              </div>

              <div class="pixel-subframe p-3.5 space-y-1">
                <div class="font-pixel text-[9px] text-neutral-400">[IBM CREDENTIAL]</div>
                <div class="font-bold text-white">Databases and SQL for Data Science with Python</div>
              </div>

              <div class="pixel-subframe p-3.5 space-y-1">
                <div class="font-pixel text-[9px] text-neutral-400">[GOOGLE CLOUD]</div>
                <div class="font-bold text-white">Advanced Machine Learning on Google Cloud</div>
              </div>

              <div class="pixel-subframe p-3.5 space-y-1">
                <div class="font-pixel text-[9px] text-neutral-400">[GOOGLE CLOUD]</div>
                <div class="font-bold text-white">Computer Vision Fundamentals with Google Cloud</div>
              </div>
            </div>

            <h3 class="font-pixel text-[11px] text-white border-l-4 border-white pl-2.5 pt-2">
              HACKATHONS &amp; EXTRACURRICULAR
            </h3>

            <div class="space-y-3">
              <div class="pixel-subframe p-3.5 flex flex-col sm:flex-row sm:items-center justify-between gap-2">
                <div>
                  <div class="font-bold text-white">CISCO CODATHON AP — Cisco Networking Academy</div>
                  <div class="text-xs text-neutral-300">Algorithmic problem-solving and network architecture competition.</div>
                </div>
                <span class="font-pixel text-[9px] border border-white px-2 py-1 self-start sm:self-center">2020</span>
              </div>

              <div class="pixel-subframe p-3.5 flex flex-col sm:flex-row sm:items-center justify-between gap-2">
                <div>
                  <div class="font-bold text-white">Kabaddi Sports Club — University &amp; Polytechnic</div>
                  <div class="text-xs text-neutral-300">Team strategy, high-pressure coordination, and competitive athletics.</div>
                </div>
                <span class="font-pixel text-[9px] border border-white px-2 py-1 self-start sm:self-center">2019–2021</span>
              </div>
            </div>
          </div>
        `
      },

      contact: {
        badge: "STAGE 05",
        title: "WARP LINK // CONTACT",
        meta: "CHANNEL: OPEN",
        html: `
          <div class="space-y-4">
            <div class="pixel-subframe p-4 bg-black">
              <p class="font-pixel text-[10px] text-white leading-relaxed">
                &gt; STATUS: AVAILABLE FOR SOFTWARE ENGINEER, AI/ML ENGINEER &amp; PYTHON BACKEND ROLES.
              </p>
            </div>

            <div class="grid grid-cols-1 sm:grid-cols-2 gap-3.5">
              <!-- Email -->
              <div class="pixel-subframe p-4 space-y-2">
                <div class="font-pixel text-[9px] text-neutral-400">[DIRECT EMAIL]</div>
                <div class="text-xs sm:text-sm font-bold text-white break-all">
                  Sivaramakrishnarachakulla@gmail.com
                </div>
                <button type="button" onclick="copyText('Sivaramakrishnarachakulla@gmail.com', 'EMAIL')" class="mono-btn font-pixel text-[9px] px-3 py-1.5 mt-1">
                  COPY EMAIL
                </button>
              </div>

              <!-- Phone -->
              <div class="pixel-subframe p-4 space-y-2">
                <div class="font-pixel text-[9px] text-neutral-400">[PHONE / WHATSAPP]</div>
                <div class="text-sm font-bold text-white">
                  +91-9121141146
                </div>
                <button type="button" onclick="copyText('+91-9121141146', 'PHONE')" class="mono-btn font-pixel text-[9px] px-3 py-1.5 mt-1">
                  COPY NUMBER
                </button>
              </div>

              <!-- GitHub -->
              <div class="pixel-subframe p-4 space-y-2 sm:col-span-2">
                <div class="font-pixel text-[9px] text-neutral-400">[CODE REPOSITORY]</div>
                <div class="flex flex-wrap items-center justify-between gap-2">
                  <span class="text-sm font-bold text-white">github.com/Sivaramakrishna1146</span>
                  <a href="https://github.com/Sivaramakrishna1146" target="_blank" rel="noopener noreferrer" class="mono-btn font-pixel text-[9px] px-3 py-1.5 inline-block">
                    OPEN GITHUB ↗
                  </a>
                </div>
              </div>
            </div>

            <!-- Copy Feedback Box -->
            <div id="copy-status" class="h-6 font-pixel text-[10px] text-white"></div>
          </div>
        `
      }
    };

    const SECTION_KEYS = ['profile', 'inventory', 'quests', 'achievements', 'contact'];
    let currentIndex = 0;
    let sfxEnabled = true;
    let crtEnabled = true;

    /**
     * HELPER RENDERERS FOR MONOCHROME BARS & TAGS
     */
    function renderSegments(filled, total) {
      let html = '';
      for (let i = 0; i < total; i++) {
        html += `<div class="stat-segment ${i < filled ? '' : 'empty'}"></div>`;
      }
      return html;
    }

    function renderTags(items) {
      return items.map(item =>
        `<span class="bg-black border border-neutral-400 text-white px-2.5 py-1 font-mono">${item}</span>`
      ).join('');
    }

    /**
     * MINIMALIST 8-BIT MENU BLIP AUDIO
     */
    let audioCtx = null;

    function playBlip(freq = 660, duration = 0.055) {
      if (!sfxEnabled) return;
      try {
        if (!audioCtx) {
          const AudioContext = window.AudioContext || window.webkitAudioContext;
          if (AudioContext) audioCtx = new AudioContext();
        }
        if (!audioCtx) return;
        if (audioCtx.state === 'suspended') audioCtx.resume();

        const now = audioCtx.currentTime;
        const osc = audioCtx.createOscillator();
        const gain = audioCtx.createGain();
        osc.type = 'square';
        osc.frequency.setValueAtTime(freq, now);
        gain.gain.setValueAtTime(0.05, now);
        gain.gain.exponentialRampToValueAtTime(0.001, now + duration);

        osc.connect(gain);
        gain.connect(audioCtx.destination);
        osc.start(now);
        osc.stop(now + duration);
      } catch (err) {
        // Ignore if blocked before user gesture
      }
    }

    /**
     * SELECT & RENDER MENU SECTION
     */
    function selectSection(index, playAudio = true) {
      if (index < 0) index = SECTION_KEYS.length - 1;
      if (index >= SECTION_KEYS.length) index = 0;
      currentIndex = index;

      const key = SECTION_KEYS[currentIndex];
      const data = SECTIONS[key];

      if (playAudio) playBlip(740, 0.05);

      // Update Menu Button Active Highlight & Blinking Cursor
      const buttons = document.querySelectorAll('#menu-list .menu-option');
      buttons.forEach((btn, idx) => {
        if (idx === currentIndex) {
          btn.classList.add('active');
          btn.setAttribute('aria-selected', 'true');
        } else {
          btn.classList.remove('active');
          btn.setAttribute('aria-selected', 'false');
        }
      });

      // Update Right Viewport Panel
      document.getElementById('stage-badge').textContent = data.badge;
      document.getElementById('stage-title').textContent = data.title;
      document.getElementById('stage-meta').textContent = data.meta;

      const contentEl = document.getElementById('stage-content');
      contentEl.classList.remove('panel-reveal');
      void contentEl.offsetWidth; // trigger reflow for crisp step animation
      contentEl.innerHTML = data.html;
      contentEl.classList.add('panel-reveal');
    }

    /**
     * CLIPBOARD COPY UTILITY (iFrame-safe)
     */
    function copyText(text, label) {
      const temp = document.createElement('input');
      temp.value = text;
      document.body.appendChild(temp);
      temp.select();
      document.execCommand('copy');
      document.body.removeChild(temp);

      playBlip(980, 0.08);
      const statusEl = document.getElementById('copy-status');
      if (statusEl) {
        statusEl.textContent = `> ${label} COPIED TO CLIPBOARD!`;
      }
    }

    /**
     * EVENT LISTENERS (Click, D-Pad, Keyboard Arrows, CRT/SFX toggles)
     */
    document.querySelectorAll('#menu-list .menu-option').forEach((btn, idx) => {
      btn.addEventListener('click', () => selectSection(idx, true));
    });

    document.getElementById('btn-prev').addEventListener('click', () => {
      selectSection(currentIndex - 1, true);
    });

    document.getElementById('btn-next').addEventListener('click', () => {
      selectSection(currentIndex + 1, true);
    });

    window.addEventListener('keydown', (e) => {
      if (e.key === 'ArrowUp' || e.key === 'w' || e.key === 'W') {
        e.preventDefault();
        selectSection(currentIndex - 1, true);
      } else if (e.key === 'ArrowDown' || e.key === 's' || e.key === 'S') {
        e.preventDefault();
        selectSection(currentIndex + 1, true);
      } else if (e.key >= '1' && e.key <= '5') {
        selectSection(parseInt(e.key, 10) - 1, true);
      }
    });

    document.getElementById('crt-toggle').addEventListener('click', () => {
      crtEnabled = !crtEnabled;
      const body = document.getElementById('app-body');
      const btn = document.getElementById('crt-toggle');
      if (crtEnabled) {
        body.classList.add('scanlines');
        btn.textContent = 'CRT: ON';
      } else {
        body.classList.remove('scanlines');
        btn.textContent = 'CRT: OFF';
      }
      playBlip(580, 0.04);
    });

    document.getElementById('sfx-toggle').addEventListener('click', () => {
      sfxEnabled = !sfxEnabled;
      const btn = document.getElementById('sfx-toggle');
      btn.textContent = sfxEnabled ? 'SFX: ON' : 'SFX: OFF';
      if (sfxEnabled) playBlip(880, 0.06);
    });

    // Initialize default section on window load
    window.onload = function () {
      selectSection(0, false);
    };
  </script>
</body>
</html>
