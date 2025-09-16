<!-- Hero -->
<div align="center" style="font-family: ui-sans-serif, system-ui, Segoe UI; color:#e5e7eb; background:#0b1220; padding:28px 18px; border-radius:16px;">
  <h1 style="margin:0 0 6px; font-size:36px;">⚒️ ExeFoundry — BAT → EXE Converter (portable)</h1>
  <p style="margin:0 0 16px; font-size:16px; opacity:.9;">
    Turn any Windows <b>Batch (<code>.bat</code>)</b> into a <b>single portable <code>.exe</code></b>.<br>
    Custom icon, console/GUI mode, and argument forwarding. No admin rights needed.
  </p>

  <img alt="Windows" src="https://img.shields.io/badge/OS-Windows-0078D6?logo=windows&logoColor=white" />
  <img alt="Shell" src="https://img.shields.io/badge/Shell-PowerShell%20%2B%20C%23-111827" />
  <img alt="Requires" src="https://img.shields.io/badge/Requires-.NET%20compiler%20(csc)-informational" />
  <img alt="License" src="https://img.shields.io/badge/License-MIT-yellow.svg" />
</div>

<!-- Quick-links badges (keep right after the hero) -->
<p align="center" style="margin:10px 0 0;">
  <a href="docs/ExeFoundry Portable BAT to EXE Converter for Shareable Windows Utilities.pdf">
    <img alt="Docs (PDF)" src="https://img.shields.io/badge/Docs-PDF-2563EB?logo=readthedocs&logoColor=white">
  </a>
  <a href="#-documentation">
    <img alt="Docs Section" src="https://img.shields.io/badge/Documentation-0EA5E9">
  </a>
  <a href="#-quick-start">
    <img alt="Quick Start" src="https://img.shields.io/badge/Quick%20Start-22C55E">
  </a>
</p>

<!-- =========================
      Dedicated Documentation (NEW)
     ========================= -->
<div id="-documentation" class="blk card">
  <h2>📄 Documentation</h2>
  <ul>
    <li><b>Tech note (PDF):</b> <a href="docs/ExeFoundry Portable BAT to EXE Converter for Shareable Windows Utilities.pdf">docs/ExeFoundry Portable BAT to EXE Converter for Shareable Windows Utilities.pdf</a></li>
    <li><b>LaTeX source (ZIP):</b> <a href="docs/Documentation Maker.zip">docs/Documentation Maker.zip</a></li>
    <li><b>How to Cite:</b> <a href="CITATION.cff">CITATION.cff</a></li>
  </ul>
  <p style="opacity:.85;margin:.4rem 0 0;">
    Tip: Put both the <code>PDF</code> and the <code>ZIP</code> in each Release along with checksums — this helps reviewers & professors find docs fast.
  </p>
</div>

<!-- =========================
      Background & Motivation
     ========================= -->
<div class="blk card">
  <h2>🧭 Background — Why this tool exists</h2>
  <p class="lead" style="margin:.25rem 0 .75rem; font-size:16px; opacity:.9">
    Lots of handy internal tools still ship as <b>.bat</b> scripts. Users want something that’s
    <b>double-clickable</b>, has a <b>proper icon</b>, and can be <b>shared as a single file</b> without setup.
    ExeFoundry turns your batch into a clean <code>.exe</code> while keeping behavior identical.
  </p>
  <ul>
    <li>Ship utilities as one file (easier to email/host).</li>
    <li>Keep the original arguments and quoting behavior.</li>
    <li>Offer a GUI mode for end-user apps (no console flash).</li>
  </ul>
</div>

<div class="blk card">
  <h2>🚀 What ExeFoundry does (in simple words)</h2>
  <p class="lead" style="margin:.25rem 0 .75rem; font-size:16px; opacity:.9">
    You give it a <b>.bat</b>. It builds a tiny <b>C# launcher</b> that runs your batch with the same arguments
    and (optionally) embeds an <b>.ico</b> as the app icon. Output is a <b>single .exe</b>.
  </p>
  <ul>
    <li>No admin rights, registry edits, or system changes.</li>
    <li>Works on standard Windows 10/11 with a C# compiler available.</li>
    <li>Perfect for packaging scripts for non-technical users.</li>
  </ul>
</div>

<div class="blk card">
  <h2>🧩 Typical use case</h2>
  <ol style="margin-left:1.1rem">
    <li><b>Prepare</b> your script: <code>scripts\tool.bat</code>.</li>
    <li><b>Build</b> with ExeFoundry into <code>Tool.exe</code> (with or without a custom icon).</li>
    <li><b>Share</b> the single EXE — users just double-click and pass arguments as usual.</li>
  </ol>
  <p class="muted" style="opacity:.85">Tip: For end-user facing tools, use the GUI build switch to hide the console.</p>
</div>

<div class="blk card">
  <h2>🛡️ Good-citizen notes</h2>
  <p class="lead" style="margin:.25rem 0 .75rem; font-size:16px; opacity:.9">
    ExeFoundry does <b>not</b> access OS core, registry, or services. It simply launches your batch.
  </p>
  <ul>
    <li>No admin / elevation required.</li>
    <li>For production distribution, consider code-signing the EXE.</li>
    <li>Quote paths with spaces: <code>"C:\Path With Spaces\script.bat"</code>.</li>
  </ul>
</div>

<div class="blk card">
  <h2>🎯 <span class="result">Outcome</span></h2>
  <ul>
    <li>Input: <b>.bat</b> + (optional) <b>.ico</b></li>
    <li>Output: <b>single .exe</b> (console or GUI)</li>
    <li>Argument forwarding preserved</li>
    <li>Same behavior as the original batch</li>
  </ul>
</div>

<div class="blk card">
  <h2>📊 <span id="-quick-start" class="step">Quick Start</span></h2>
  <ol>
    <li>Create a batch file, e.g., <code>scripts\hello.bat</code> (example below)</li>
    <li>Open PowerShell in the repo root</li>
    <li>Run a build command (see examples)</li>
  </ol>
</div>

<div class="blk card">
  <h2>⚙️ Config</h2>
  <p><span class="pill">Icon (.ico)</span><span class="pill">GUI switch</span><span class="pill">Quoting</span></p>
  <pre><code># Use -Icon to embed an .ico; add -WinExe for a GUI build (no console)
# Always quote paths with spaces and use absolute/relative paths consistently.
</code></pre>
</div>

<div class="blk card">
  <h2>🧠 How it works</h2>
  <ul>
    <li>Builds a tiny <code>C#</code> launcher that calls your <code>.bat</code> with proper quoting</li>
    <li>Packs the launcher into a single <code>.exe</code> (with optional icon)</li>
    <li>When run, the EXE executes the batch and forwards arguments</li>
  </ul>
</div>

<div class="blk card">
  <h2>📦 Command-line options</h2>

| Option       | Required | Description                                                        |
|--------------|:--------:|--------------------------------------------------------------------|
| `-InputBat`  | ✅       | Path to the source `.bat` file.                                    |
| `-OutputExe` | ❌       | Output `.exe` path (default: same folder/name as BAT).             |
| `-Icon`      | ❌       | Optional `.ico` to embed as the EXE icon.                          |
| `-WinExe`    | ❌       | Build as GUI app (no console window). Omit for console builds.     |

**Examples**
```powershell
# Basic
.\ExeFoundry.exe -InputBat ".\scripts\build.bat"

# Custom output
.\ExeFoundry.exe -InputBat ".\scripts\build.bat" -OutputExe ".\Build.exe"

# Icon + Console (default)
.\ExeFoundry.exe -InputBat ".\scripts\tool.bat" -Icon ".\scripts\icon\bat_to_exe.ico"

# Icon + GUI (no console)
.\ExeFoundry.exe -InputBat ".\scripts\tool.bat" -OutputExe ".\Tool.exe" -Icon ".\scripts\icon\bat_to_exe.ico" -WinExe
