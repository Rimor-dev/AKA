<html>
<body>
<!--StartFragment--><!-- obsidian --><h1 data-heading="AKA — ComfyUI Advanced Manager">AKA — ComfyUI Advanced Manager</h1>

<img src="https://github.com/Rimor-dev/my-assets_/blob/main/assets/akacover.png" alt="main" width="90%">

<h2 data-heading="WHY AKA">WHY AKA</h2>
<p>ComfyUI has no built-in environment manager. Users must manually create venvs, install PyTorch, manage custom nodes, and juggle multiple Python configurations. AKA solves all of this with a single integrated interface.</p>
<h3 data-heading="Problems AKA solves:">Problems AKA solves:</h3>
<ul>
<li><strong>Multiple ComfyUI installations require separate venvs</strong> — AKA creates, clones and switches between them in one click.</li>
<li><strong>PyTorch version hell</strong> — AKA detects your GPU architecture (Blackwell, Ada, Ampere, Turing, Pascal, Volta), CUDA version, and suggests compatible PyTorch builds. Manual input always available.</li>
<li><strong>Custom nodes are a mess</strong> — AKA scans, installs, clones and removes custom nodes with dependency tracking.</li>
<li><strong>No unified monitoring</strong> — AKA provides real-time server logs, hardware stats, GPU temperature tracking with voice alerts.</li>
<li><strong>Browser window clutter</strong> — AKA embeds ComfyUI directly into its interface, no external browser needed. Built-in RELOAD button.</li>
<li><strong>Model management chaos</strong> — MODELs tab provides tree browser with HuggingFace download, usage analytics, auto-resume for interrupted downloads.</li>
<li><strong>Workflow mess</strong> — FLOWs tab manages local workflows and syncs with official Comfy-Org/workflow_templates. New flows highlighted, one-click download.</li>
<li><strong>Missing update notifications</strong> — Scheduler checks ComfyUI releases on startup and every 3 hours. Voice alert when new version found.</li>
<li><strong>Wheel file hassle</strong> — WHEELs tab: import from disk, download by URL, install into active venv.</li>
<li><strong>Configuration pain</strong> — AKATOOLS external editor for paths.json and settings.json with UI.</li>
</ul>
<p>AKA is a standalone executable. No Python required. No dependencies to install. Download, run, work.</p>
<img src="https://github.com/Rimor-dev/my-assets_/blob/main/assets/aka_f.png" alt="main" width="20%"> 
<hr>
<h2 data-heading="SYSTEM REQUIREMENTS &#x26; WORKFLOW">SYSTEM REQUIREMENTS &#x26; WORKFLOW</h2>
<h3 data-heading="Tested Platform">Tested Platform</h3>
<p>AKA has been tested on <strong>Windows 11 x64</strong>. It should work on Windows 10 x64 as well.</p>

<h3 data-heading="Prerequisites">Prerequisites</h3>

Before using AKA, install these system components. You can download them directly through AKA (MAiN tab → DOWNLOAD section) — no need to visit external websites manually:

<strong>Python 3.11+</strong> — AKA can download the installer for you (MAiN tab → DOWNLOAD → PYTHON, versions 3.13, 3.12, 3.11). During installation, check the box <strong>"Add Python to PATH"</strong> — this is important. AKA detects installed Python versions automatically. For maximum flexibility, consider installing multiple versions (3.11, 3.12, 3.13). AKA will let you choose which one to use for each venv.

<strong>Git</strong> — required for cloning ComfyUI and custom nodes. AKA can download it automatically (MAiN tab → DOWNLOAD → GIT). No manual download needed.

That's it. NVIDIA drivers are assumed to be already installed. CUDA Toolkit and cuDNN are <strong>not required</strong> — PyTorch includes its own CUDA libraries.

<strong>Recommended Workflow</strong>

<strong>1. Install prerequisites.</strong><br>
Install Python (with "Add Python to PATH" checked) and Git.

<strong>2. Create a clean ComfyUI installation through AKA.</strong><br>
In the MAiN tab, set an empty folder as the PATH, then click CLONE. AKA will clone the latest ComfyUI from GitHub. This ensures you start with a clean, known-good installation without legacy files or conflicting dependencies.

<strong>3. Create a virtual environment.</strong><br>
Go to the VENVs tab, click CREATE. AKA detects your GPU architecture, driver, and CUDA version and suggests the best matching PyTorch build. Select a version from the list or enable <strong>MANUAL INPUT</strong> to enter a custom pip command. <strong><em>Example for a manual PyTorch install:</em></strong>
<pre><code>torch==2.8.0 torchvision==0.23.0 torchaudio==2.8.0 --index-url https://download.pytorch.org/whl/cu128
</code></pre>
Optionally enter a description for the environment. Click INSTALL and AKA will handle the full setup — venv creation, pip upgrade, requirements installation (excluding torch packages), manager requirements, and the selected PyTorch build. Progress is displayed in the Progress Panel.

<strong>4. Launch ComfyUI.</strong><br>
Select your new venv in the table, configure launch flags in LAUNCH KEYS, and click SERVER START. Monitor the output in the Server Monitor panel.

<img src="https://github.com/Rimor-dev/my-assets_/blob/main/assets/aka_air.png" alt="main" width="30%">

<strong>5. Install custom nodes.</strong><br>
Use the NODEs tab to clone repositories, install requirements, and manage your node whitelist. AKA can run <code>requirements.txt</code> and <code>install.py</code> for any selected nodes.

<strong>6. Manage models.</strong><br>
MODELs tab — browse models tree, paste HuggingFace URL, select target folder, DOWNLOAD. Interrupted downloads auto-resume. ANALYZE shows usage statistics.

<strong>7. Manage workflows.</strong><br>
FLOWs tab — LOCAL submenu for ComfyUI/user/default/workflows, REPO submenu for official workflow_templates. New flows highlighted, one-click download to workflows root.

<strong>8. Switch between environments.</strong><br>
Create multiple venvs with different PyTorch or CUDA versions. Switch between them by checking the box in the VENVs table. Each environment is isolated — no conflicts.

<h3 data-heading="File Locations">File Locations</h3>

<table>
<tr><th>Data</th><th>Location</th></tr>
<tr><td>AKA executable</td><td>bin/AKA.exe (or AKA_Launcher.exe in root)</td></tr>
<tr><td>Settings</td><td>C:\Users\Username\AppData\Roaming\AKA\settings.json</td></tr>
<tr><td>Config paths</td><td>C:\Users\Username\AppData\Roaming\AKA\configs\paths.json</td></tr>
<tr><td>Downloaded installers</td><td>C:\Users\Username\Downloads\AKA_downloads</td></tr>
<tr><td>Wheel files</td><td>C:\Users\Username\AppData\Roaming\AKA\wheels</td></tr>
<tr><td>Flows catalog</td><td>C:\Users\Username\AppData\Roaming\AKA\flows_catalog.json</td></tr>
<tr><td>Node maps</td><td>profiles/</td></tr>
<tr><td>Browser data</td><td>C:\Users\Username\AppData\Roaming\AKA\akamfy_data</td></tr>
</table>

<h3 data-heading="Notes">Notes</h3>
<ul>
<li>AKA does not touch your system Python. All packages are installed inside virtual environments within the ComfyUI folder.</li>
<li>Multiple ComfyUI installations can be managed by changing the PATH in the MAiN tab. Each installation has its own set of venvs.</li>
<li>The splash screen launcher (<code>AKA_Launcher.exe</code>) can be used as the primary entry point. It shows a loading screen while AKA starts, then closes automatically.</li>
</ul>
<hr>
<h2 data-heading="INSTALLATION">INSTALLATION</h2>
<ol>
<li>Download <code>AKA_Setup.exe</code> from Releases.</li>
<li>Run the installer, choose a destination folder.</li>
<li>A desktop shortcut is created automatically.</li>
<li>Launch AKA.</li>
</ol>
<p>The program is self-contained. All components are bundled inside. Settings and data are stored in the installation folder.</p>
<hr>
<h2 data-heading="MAIN WINDOW LAYOUT">MAIN WINDOW LAYOUT</h2>
<p>The interface is divided into three vertical panels, fixed at 1300x680 pixels.</p>
<h3 data-heading="Left Panel">Left Panel</h3>
<ul>
<li><strong>Progress Panel</strong> — operation log and progress bar for long tasks. ABORT button kills all active operations without touching server.</li>
<li><strong>Server Monitor</strong> — real-time ComfyUI server output with warning/error counters.</li>
<li><strong>HW Monitor</strong> — CPU, GPU, memory load and GPU temperature.</li>
<li><strong>Server Control</strong> — START/STOP buttons with session timer.</li>
<li><strong>AKAMFY Bar</strong> — AKAMFY MODE checkbox, RELOAD button (active when browser open), AKA/AKAMFY toggle button.</li>
</ul>
<h3 data-heading="Center Panel">Center Panel</h3>
<ul>
<li><strong>MAiN tab</strong> — path configuration, system info, component downloads, AKATOOLS launcher.</li>
<li><strong>VENVs tab</strong> — virtual environment management.</li>
<li><strong>MODELs tab</strong> — model browser with HuggingFace download, usage analytics, drag & drop.</li>
<li><strong>NODEs tab</strong> — custom nodes manager.</li>
<li><strong>FLOWs tab</strong> — workflow manager (LOCAL and REPO submenus).</li>
<li><strong>TOOLs tab</strong> — Python versions, ComfyUI updates, package manager, links.</li>
<li><strong>WHEELs tab</strong> — wheel file installer with ADD and DOWNLOAD.</li>
</ul>
<h3 data-heading="Right Panel">Right Panel</h3>
<ul>
<li><strong>AKASHI Terminal</strong> — onboard computer with menu system, command line, sound synthesizer, voice notifications, scheduler.</li>
<li><strong>Logo Widget</strong> — AKA branding.</li>
<li><strong>Venv Console</strong> — direct Python console for the active environment.</li>
</ul>
<h3 data-heading="Top Bar">Top Bar</h3>
<ul>
<li><strong>TRM block</strong> — status indicator (green = normal, red = error).</li>
<li><strong>Cursor ">"</strong> — blinking prompt.</li>
<li><strong>Info line</strong> — last message from the system.</li>
<li><strong>"赤" square</strong> — clears the terminal line.</li>
<li><strong>"aKa" block</strong> — shows version on click.</li>
</ul>
<h3 data-heading="Bottom Bar">Bottom Bar</h3>
<ul>
<li><strong>ZOOM</strong> — fullscreen mode with adaptive layout and background image with masks.</li>
<li><strong>MINIMIZE</strong> — minimize to taskbar.</li>
<li><strong>REFRESH</strong> — reloads all tabs and system info.</li>
<li><strong>TERMINATE</strong> — stops server, plays shutdown voice, blinks, exits after 3 seconds.</li>
</ul>
<hr>
<h2 data-heading="MAiN TAB — PATH &#x26; SYSTEM">MAiN TAB — PATH &#x26; SYSTEM</h2>
<h3 data-heading="PATH Section">PATH Section</h3>
<p>This is where you tell AKA where ComfyUI lives.</p>
<p><strong>BRW</strong> — opens a folder picker dialog to select the ComfyUI directory.<br>
<strong>ENTR</strong> — toggles manual path entry mode. Click once to edit, type the path, click again to confirm.<br>
<strong>CLONE</strong> — if the folder does not contain a ComfyUI installation, this button clones the official repository from GitHub into the specified directory.</p>
<h3 data-heading="SYS Section">SYS Section</h3>
<p>Displays complete system information:</p>
<ul>
<li><strong>PATH</strong> — current ComfyUI directory.</li>
<li><strong>INSTALLED</strong> — YES if <code>main.py</code> is found.</li>
<li><strong>VERSION</strong> — ComfyUI version (from git tag or <code>comfyui_version.py</code>).</li>
<li><strong>VENV</strong> — currently active environment name.</li>
<li><strong>VENVS</strong> — total number of virtual environments detected.</li>
<li><strong>NODES</strong> — total number of custom node folders.</li>
<li><strong>PYTHON</strong> — active system Python version.</li>
<li><strong>PYTORCH</strong> — PyTorch version installed in the active venv.</li>
<li><strong>PY_PATH</strong> — path to Python executable in the active venv.</li>
<li><strong>GPU</strong> — GPU name, VRAM, architecture (Blackwell, Ada, Ampere, Turing, Pascal, Volta).</li>
<li><strong>DRIVER</strong> — NVIDIA driver version.</li>
<li><strong>CUDA</strong> — CUDA toolkit version.</li>
<li><strong>cuDNN</strong> — cuDNN version.</li>
<li><strong>OS</strong> — Windows version and architecture.</li>
</ul>
<h3 data-heading="DOWNLOAD Section">DOWNLOAD Section</h3>
<p>Pre-configured download buttons for common dependencies:</p>
<ul>
<li><strong>PYTHON</strong> — select version and click DWNLD to download the installer. Three versions available (3.13, 3.12, 3.11).</li>
<li><strong>GIT</strong> — Git for Windows installer.</li>
</ul>
<p>All downloaded files are saved to <code>Downloads/AKA_downloads/</code>.</p>
<p>Versions are defined in <code>configs/paths.json</code> and can be customized with <strong>AKATOOLS</strong>.</p>
<h3 data-heading="AKATOOLS Section">AKATOOLS Section</h3>
<p><strong>AKATOOLS</strong> button launches external configuration editor:</p>
<ul>
<li>Edit PyTorch versions and CUDA mappings</li>
<li>Edit GPU architecture map</li>
<li>Edit Python download URLs</li>
<li>Edit Git URL</li>
<li>Edit settings.json (HF token encrypted, theme, splash key, links)</li>
</ul>
<hr>
<h2 data-heading="VENVs TAB — ENVIRONMENT MANAGEMENT">VENVs TAB — ENVIRONMENT MANAGEMENT</h2>
<h3 data-heading="Environments Table">Environments Table</h3>
<p>Lists all virtual environments found in the ComfyUI folder. Columns:</p>
<ul>
<li><strong>Checkbox</strong> — select to activate this environment.</li>
<li><strong>NAME</strong> — folder name (venv, venv_1, etc.) with optional description in brackets.</li>
<li><strong>PYTORCH</strong> — installed PyTorch version.</li>
<li><strong>CUDA</strong> — CUDA variant (e.g. 12.4, CPU).</li>
<li><strong>PYTHON</strong> — Python version in the venv.</li>
<li><strong>SIZE</strong> — total folder size.</li>
</ul>
<p>Only one environment can be active at a time. Selecting one updates the Server Control, Tools packages, and Venv Console.</p>
<h3 data-heading="CREATE Button">CREATE Button</h3>
<p>Launches the PyTorch installation dialog:</p>
<ol>
<li>Detects your GPU architecture, driver, and CUDA version.</li>
<li>Suggests the best PyTorch build for your GPU generation.</li>
<li>Allows manual pip command input for custom builds.</li>
<li>Optionally adds a description for the environment.</li>
</ol>
<p>After confirmation, AKA performs the full setup pipeline:</p>
<ol>
<li>Creates the venv using the active system Python.</li>
<li>Upgrades pip.</li>
<li>Installs <code>requirements.txt</code> (excluding torch packages).</li>
<li>Installs <code>manager_requirements.txt</code> if present.</li>
<li>Installs the selected PyTorch build.</li>
<li>Saves metadata to <code>venv_info.json</code>.</li>
</ol>
<p>Progress is displayed in the Progress Panel.</p>
<h3 data-heading="LAUNCH KEYS">LAUNCH KEYS</h3>
<p>Checkboxes for ComfyUI launch arguments. Standard flags:</p>
<ul>
<li><code>--windows-standalone-build</code></li>
<li><code>--enable-manager</code></li>
<li><code>--preview-method auto</code></li>
<li><code>--force-fp16</code></li>
<li><code>--highvram</code> / <code>--normalvram</code> / <code>--lowvram</code> / <code>--novram</code></li>
<li><code>--cpu</code></li>
<li><code>--disable-xformers</code></li>
<li><code>--verbose</code></li>
<li><code>--listen</code></li>
<li><code>--port 8188</code></li>
</ul>
<p><strong>ADD</strong> — adds a custom flag.<br>
<strong>DEL</strong> — removes a custom flag.</p>
<p>Flag states are saved between sessions.</p>
<h3 data-heading="HF TOKEN">HF TOKEN</h3>
<p>For HuggingFace authentication. <strong>ENTR</strong> toggles edit mode. The token is passed to ComfyUI as <code>--hf-token</code> on launch. Token is encrypted in settings.json.</p>
<hr>
<h2 data-heading="MODELs TAB — MODEL MANAGER">MODELs TAB — MODEL MANAGER</h2>
<h3 data-heading="Models Tree">Models Tree</h3>
<p>Browses <code>models/</code> folder. Directories on top. Columns: Name, Size, Modified, Usage.</p>
<ul>
<li><strong>Drag & drop</strong> — move model files between folders.</li>
<li><strong>REFRESH</strong> — rescan models folder.</li>
<li><strong>ANALYZE</strong> — loads usage statistics from aka_model_usage.json. Colors: green (HIGH), orange (LOW), red (NONE).</li>
<li><strong>DELETE</strong> — confirmation dialog, files only. Folders preserved.</li>
</ul>
<h3 data-heading="HF Download">HF Download</h3>
<p>Paste HuggingFace URL (supports ?download=true suffix), select target folder in tree, DOWNLOAD. Progress in Progress Panel. Interrupted downloads auto-resume on restart via aka_download_resume.json. ABORT cancels and removes resume file.</p>
<hr>
<h2 data-heading="WHEELs TAB — WHEEL FILE INSTALLER">WHEELs TAB — WHEEL FILE INSTALLER</h2>
<h3 data-heading="Wheels Table">Wheels Table</h3>
<p>Lists <code>.whl</code> files from the <code>wheels/</code> folder. Columns:</p>
<ul>
<li><strong>Checkbox</strong> — select files to install or delete.</li>
<li><strong>FILE</strong> — wheel filename.</li>
<li><strong>SIZE</strong> — file size.</li>
</ul>
<h3 data-heading="ADD">ADD</h3>
<p>Multi-select .whl files from disk. Copies to wheels folder.</p>
<h3 data-heading="DOWNLOAD">DOWNLOAD</h3>
<p>Download wheel by URL. Progress in Progress Panel.</p>
<h3 data-heading="INSTALL">INSTALL</h3>
<p>Installs selected wheels into the active environment using <code>pip install</code>.</p>
<h3 data-heading="DELETE">DELETE</h3>
<p>Confirmation dialog. Removes selected wheel files from disk.</p>
<hr>
<h2 data-heading="NODEs TAB — CUSTOM NODES MANAGER">NODEs TAB — CUSTOM NODES MANAGER</h2>
<h3 data-heading="Nodes Table">Nodes Table</h3>
<p>Scans <code>custom_nodes/</code> folder. Columns:</p>
<ul>
<li><strong>Checkbox</strong> — select nodes for batch operations.</li>
<li><strong>NAME</strong> — folder name.</li>
<li><strong>REQS</strong> — YES if <code>requirements.txt</code> exists.</li>
<li><strong>INST.PY</strong> — YES if <code>install.py</code> exists.</li>
<li><strong>ACTIVE</strong> — whitelist toggle for ComfyUI launch.</li>
</ul>
<h3 data-heading="Operation Buttons">Operation Buttons</h3>
<ul>
<li><strong>REQS</strong> — runs <code>pip install -r requirements.txt</code> for selected nodes in the active venv.</li>
<li><strong>INST.PY</strong> — runs <code>install.py</code> for selected nodes.</li>
<li><strong>DELETE</strong> — confirmation dialog. Removes selected node folders.</li>
</ul>
<h3 data-heading="Map Management">Map Management</h3>
<ul>
<li><strong>SAVE MAP</strong> — exports the active nodes list to a JSON file.</li>
<li><strong>LOAD MAP</strong> — imports a saved map, activating only matching installed nodes.</li>
<li><strong>ALL</strong> — activates all nodes in the whitelist.</li>
<li><strong>NONE</strong> — deactivates all nodes.</li>
</ul>
<h3 data-heading="Clone Section">Clone Section</h3>
<ul>
<li><strong>URL field</strong> — paste a GitHub repository URL.</li>
<li><strong>ENTR</strong> — toggles edit mode.</li>
<li><strong>CLONE</strong> — clones the repository into <code>custom_nodes/</code>.</li>
</ul>
<p>The whitelist system generates <code>--disable-all-custom-nodes</code> and <code>--whitelist-custom-nodes</code> flags for ComfyUI launch.</p>
<hr>
<h2 data-heading="FLOWs TAB — WORKFLOW MANAGER">FLOWs TAB — WORKFLOW MANAGER</h2>
<h3 data-heading="LOCAL Submenu">LOCAL Submenu</h3>
<p>Browses <code>ComfyUI/user/default/workflows</code>:</p>
<ul>
<li>Directories always on top</li>
<li>NEW DIR — create folder</li>
<li>DELETE — confirmation dialog, files only</li>
<li>Drag & drop — move flows between folders</li>
<li>MOVE — select destination folder dialog</li>
</ul>
<h3 data-heading="REPO Submenu">REPO Submenu</h3>
<p>Syncs with <code>Comfy-Org/workflow_templates</code>:</p>
<ul>
<li>New flows highlighted green, existing orange</li>
<li>DOWNLOAD — saves selected flows to workflows root</li>
<li>Filter by name</li>
<li>Catalog stored in flows_catalog.json</li>
</ul>
<hr>
<h2 data-heading="TOOLs TAB — TOOLS &#x26; UTILITIES">TOOLs TAB — TOOLS &#x26; UTILITIES</h2>
<h3 data-heading="PYTHON VERSIONS">PYTHON VERSIONS</h3>
<p>Detects all Python installations from Windows registry and filesystem. Shows version buttons — click to switch the active system Python. This affects which Python is used for creating new venvs. Warning text explains impact.</p>
<h3 data-heading="COMFYUI VERSION">COMFYUI VERSION</h3>
<ul>
<li><strong>CURRENT</strong> — installed version (from git or <code>comfyui_version.py</code>).</li>
<li><strong>LATEST</strong> — latest release from GitHub API.</li>
<li><strong>CHECK</strong> — queries GitHub for the latest version.</li>
<li><strong>UPDATE</strong> — pulls the latest tag and reinstalls requirements.</li>
<li><strong>DNDATE</strong> — rolls back to a previous version from the snapshot list. Custom AKA-style dialog.</li>
<li><strong>ALL VENVS</strong> — when checked, update/rollback applies to all environments.</li>
</ul>
<h3 data-heading="CUSTOM VENV PACKAGES">CUSTOM VENV PACKAGES</h3>
<p>Lists pip packages installed in the active venv. Select packages and click <strong>UNINSTALL</strong> to remove them.</p>
<h3 data-heading="USEFUL LINKS">USEFUL LINKS</h3>
<p>Customizable link list. <strong>ENTR</strong> toggles edit mode for the URL field. <strong>ADD</strong> saves a new link. Click any link to open in the system browser.</p>
<hr>
<h2 data-heading="SERVER MONITOR (Left Panel)">SERVER MONITOR (Left Panel)</h2>
<p>Real-time display of ComfyUI server output. Features:</p>
<ul>
<li><strong>Log area</strong> — shows server stdout with color coding: errors in red, warnings in orange, info in blue.</li>
<li><strong>SZE</strong> — toggles font size (small/normal).</li>
<li><strong>LOG</strong> — copies the entire log to clipboard.</li>
<li><strong>ERR LOG</strong> — copies only error and warning lines.</li>
<li><strong>ONF</strong> — toggles the monitor on/off.</li>
<li><strong>CLR</strong> — clears the log and resets counters.</li>
<li><strong>WRN counter</strong> — increments on warning lines.</li>
<li><strong>ERR counter</strong> — increments on error/exception/traceback lines.</li>
</ul>
<p>The monitor auto-activates when server output arrives.</p>
<hr>
<h2 data-heading="HW MONITOR (Left Panel)">HW MONITOR (Left Panel)</h2>
<p>Hardware resource indicators updated every second:</p>
<ul>
<li><strong>CPU</strong> — usage percentage with dot indicator. Green under 60%, orange 60-80%, red above 80%.</li>
<li><strong>GPU</strong> — utilization from <code>nvidia-smi</code>. Same color logic.</li>
<li><strong>MEM</strong> — RAM usage percentage.</li>
<li><strong>TC</strong> — GPU temperature in Celsius. Blinks when above 80 degrees.</li>
<li><strong>Percent labels</strong> — numeric values next to indicators.</li>
</ul>
<hr>
<h2 data-heading="PROGRESS PANEL (Left Panel)">PROGRESS PANEL (Left Panel)</h2>
<p>Displays operation progress for venv creation, downloads, node installation, etc.</p>
<ul>
<li><strong>Log area</strong> — shows operation steps with green/yellow text.</li>
<li><strong>ABORT</strong> — kills all active operations. Stops downloads, git processes, pip installs. Server is stopped correctly via SERVER TERMINATE logic. HuggingFace resume file removed.</li>
<li><strong>SZE</strong> — toggles font size.</li>
<li><strong>LOG</strong> — copies log to clipboard.</li>
<li><strong>ONF</strong> — toggles screen on/off (darkens when off).</li>
<li><strong>CLR</strong> — clears the log.</li>
<li><strong>Dot progress bar</strong> — 50 dots filling green as progress increases.</li>
<li><strong>Percent label</strong> — numeric percentage.</li>
</ul>
<hr>
<h2 data-heading="AKASHI TERMINAL (Right Panel)">AKASHI TERMINAL (Right Panel)</h2>
<p>The onboard computer. Modeled after the MU/TH/UR 6000 interface from "Alien", hacked by the Matrix.</p>
<h3 data-heading="Power On/Off">Power On/Off</h3>
<p>Press <strong>ONF</strong> to boot. A vector animation plays: octagon forms, splits, then "AKASHI" letters appear. Press again to shut down.</p>
<h3 data-heading="Main Menu">Main Menu</h3>
<p>Two-column navigation:</p>
<ul>
<li><strong>Left column:</strong> CMD, EDIT, VIEW, TOOLS, HELP</li>
<li><strong>Right column:</strong> BEEP, SPEECH, CNTRL, GAMES, NFO</li>
</ul>
<p>Navigate with 0-9 buttons (0-4 left, 5-9 right) or arrow keys. <strong>ENTR</strong> selects. <strong>ESC</strong> goes back.</p>
<h3 data-heading="CMD Mode">CMD Mode</h3>
<p>Command line interface for direct text commands:</p>
<ul>
<li><code>splash</code> — sets the selected image as the splash screen.</li>
<li><code>beep &lt;quality&gt; &lt;wave&gt; &lt;notes&gt;</code> — plays a tone sequence. Quality: <code>hf</code>, <code>8b</code>, <code>cr</code>, <code>lf</code>. Wave: <code>sqr</code>, <code>tri</code>, <code>sin</code>. Notes format: <code>freq/duration;freq/duration</code>.</li>
<li><code>snd on/off</code> — global sound toggle.</li>
<li><code>beep on/off</code> — enable/disable event beeps.</li>
<li><code>speech on/off</code> — enable/disable voice notifications.</li>
<li><code>cntrl on/off</code> — enable/disable server monitoring.</li>
<li><code>sched on/off</code> — enable/disable scheduler.</li>
<li><code>sched check</code> — force scheduler check now.</li>
<li><code>scr off</code> — turns off the AKASHI screen. Any button press wakes it.</li>
<li><code>deft</code> — resets AKASHI settings to default.</li>
<li><code>deft aka</code> — resets all AKA settings to default.</li>
<li><code>info</code> — developer contact information.</li>
<li><code>help</code> — command list.</li>
<li><code>clear</code> — clears the display.</li>
</ul>
<h3 data-heading="BEEP Menu">BEEP Menu</h3>
<ul>
<li><strong>PHRASES</strong> — saved tone sequences. Select and play with ENTR.</li>
<li><strong>SYNTH</strong> — help screen showing synthesizer syntax.</li>
<li><strong>FUNC</strong> — enables event beeps.</li>
<li><strong>UNFUNC</strong> — disables event beeps.</li>
</ul>
<h3 data-heading="SPEECH Menu">SPEECH Menu</h3>
<ul>
<li><strong>FUNC</strong> — enables speech for events.</li>
<li><strong>UNFUNC</strong> — disables speech.</li>
</ul>
<p>Speech plays MP3 files from <code>assets/akaspeech/</code>. Triggers include server start/stop, job completion, job error, GPU overheating, ComfyUI updates. Each event plays once — no looping.</p>
<h3 data-heading="CNTRL Menu">CNTRL Menu</h3>
<ul>
<li><strong>FUNC</strong> — enables CNTRL monitoring.</li>
<li><strong>UNFUNC</strong> — disables CNTRL.</li>
</ul>
<h3 data-heading="VIEW Menu">VIEW Menu</h3>
<p>Image browser. Lists PNG files from the bundled assets. The <code>splash</code> command sets the viewed image as the splash screen. Hidden images (marked with <code>*</code>) unlocked via <code>unlock</code> command or gameplay.</p>
<h3 data-heading="GAMES Menu">GAMES Menu</h3>
<p><strong>ARKANOID</strong> — vector breakout game. Control with AKASHI arrows or keyboard. Every 100 points unlocks a hidden image. ESC exits.</p>
<h3 data-heading="NFO Menu">NFO Menu</h3>
<p>Displays program information and credits.</p>
<h3 data-heading="EDIT Menu">EDIT Menu</h3>
<ul>
<li><strong>ONSTART</strong> — auto-boot AKASHI on launch.</li>
<li><strong>OFSTART</strong> — manual boot.</li>
<li><strong>ONSND</strong> — sound enabled by default.</li>
<li><strong>OFSND</strong> — sound disabled by default.</li>
</ul>
<h3 data-heading="TOOLS Menu">TOOLS Menu</h3>
<p><strong>AKASKY ANTVIR</strong> — humorous fake antivirus scanner.</p>
<h3 data-heading="SND Button">SND Button</h3>
<p>Global sound toggle.</p>
<hr>
<h2 data-heading="AKAMFY BROWSER (Embedded ComfyUI)">AKAMFY BROWSER (Embedded ComfyUI)</h2>
<p>Toggle between AKA tabs and the ComfyUI interface using the <strong>AKAMFY MODE</strong> checkbox and the <code>AKAMFY >>></code> button.</p>
<p><strong>RELOAD</strong> button — reloads ComfyUI page. Active only when browser is open.</p>
<p>The browser loads <code>http://localhost:8188</code>. Supports WebGL, file downloads, persistent storage, session persistence.</p>
<p><code>beforeunload</code> dialogs suppressed.</p>
<hr>
<h2 data-heading="CONTACTS">CONTACTS</h2>
<ul>
<li><strong>Telegram:</strong> @Rimor_Spectator</li>
<li><strong>GitHub:</strong> github.com/Rimor-dev</li>
</ul>
<hr><!--EndFragment-->
</body>
</html>
