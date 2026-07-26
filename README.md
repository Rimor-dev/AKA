<html>
<body>
<!--StartFragment--><!-- obsidian --><h1 data-heading="AKA — ComfyUI Advanced Manager">AKA — ComfyUI Advanced Manager</h1>

<img src="https://github.com/Rimor-dev/my-assets_/blob/main/assets/scrn_.png" alt="main" width="100%"> 

<h2 data-heading="WHY AKA">WHY AKA</h2>
<p>ComfyUI has no built-in environment manager. Users must manually create venvs, install PyTorch, manage custom nodes, and juggle multiple Python configurations. AKA solves all of this with a single integrated interface.</p>
<h3 data-heading="Problems AKA solves:">Problems AKA solves:</h3>
<ul>
<li><strong>Multiple ComfyUI installations require separate venvs</strong> — AKA creates, clones and switches between them in one click.</li>
<li><strong>PyTorch version hell</strong> — AKA detects your CUDA version and GPU, suggests compatible PyTorch builds, and installs them automatically.</li>
<li><strong>Custom nodes are a mess</strong> — AKA scans, installs, clones and removes custom nodes with dependency tracking.</li>
<li><strong>No unified monitoring</strong> — AKA provides real-time server logs, hardware stats, GPU temperature tracking with voice alerts.</li>
<li><strong>Browser window clutter</strong> — AKA embeds ComfyUI directly into its interface, no external browser needed.</li>
</ul>
<p>AKA is a standalone executable. No Python required. No dependencies to install. Download, run, work.</p>
<hr>
<h2 data-heading="SYSTEM REQUIREMENTS &#x26; WORKFLOW">SYSTEM REQUIREMENTS &#x26; WORKFLOW</h2>
<h3 data-heading="Tested Platform">Tested Platform</h3>
<p>AKA has been tested on <strong>Windows 11 x64</strong>. It should work on Windows 10 x64 as well.</p>
<h3 data-heading="Prerequisites">Prerequisites</h3>
<p>Before using AKA, install these system components:</p>
<ul>
<li><strong>Python 3.11+</strong> — download from python.org. AKA detects installed Python versions automatically.</li>
<li><strong>CUDA Toolkit</strong> — if you have an NVIDIA GPU. AKA can download it for you (MAiN tab > DOWNLOAD > CUDA).</li>
<li><strong>cuDNN</strong> — required for GPU acceleration. AKA can download it (MAiN tab > DOWNLOAD > cuDNN).</li>
<li><strong>Git</strong> — required for cloning ComfyUI and custom nodes. AKA can download it (MAiN tab > DOWNLOAD > GIT).</li>
</ul>
<p>You can install all prerequisites manually or use the DOWNLOAD section in the MAiN tab — AKA will download the installers to <code>bin/downloads/</code>. Run each installer after downloading.</p>
<h3 data-heading="Recommended Workflow">Recommended Workflow</h3>
<p><strong>1. Install prerequisites.</strong><br>
Make sure Python, CUDA, cuDNN, and Git are installed and available in your system PATH.</p>
<p><strong>2. Create a clean ComfyUI installation through AKA.</strong><br>
In the MAiN tab, set an empty folder as the PATH, then click CLONE. AKA will clone the latest ComfyUI from GitHub. This ensures you start with a clean, known-good installation without legacy files or conflicting dependencies.</p>
<p><strong>3. Create a virtual environment.</strong><br>
Go to the VENVs tab, click CREATE. AKA detects your GPU, driver, and CUDA version and suggests the best matching PyTorch build. Select a version from the list or enable <strong>MANUAL INPUT</strong> to enter a custom pip command. <strong><em>Example for a manual PyTorch install:</em></strong> </p>
<pre><code>torch==2.8.0 torchvision==0.23.0 torchaudio==2.8.0 --index-url https://download.pytorch.org/whl/cu128
</code></pre>
<p>Optionally enter a description for the environment. Click INSTALL and AKA will handle the full setup — venv creation, pip upgrade, requirements installation (excluding torch packages), manager requirements, and the selected PyTorch build. Progress is displayed in the Progress Panel.</p>
<p><strong>4. Launch ComfyUI.</strong><br>
Select your new venv in the table, configure launch flags in LAUNCH KEYS, and click SERVER START. Monitor the output in the Server Monitor panel.</p>
<p><strong>5. Install custom nodes.</strong><br>
Use the NODEs tab to clone repositories, install requirements, and manage your node whitelist. AKA can run <code>requirements.txt</code> and <code>install.py</code> for any selected nodes.</p>
<p><strong>6. Switch between environments.</strong><br>
Create multiple venvs with different PyTorch or CUDA versions. Switch between them by checking the box in the VENVs table. Each environment is isolated — no conflicts.</p>
<h3 data-heading="File Locations">File Locations</h3>

Data | Location
-- | --
AKA executable | bin/AKA.exe (or AKA_Launcher.exe in root)
Settings | bin/settings.json (public), internal state in Windows registry
ComfyUI path | bin/config.ini
Downloaded installers | bin/downloads/
Wheel files | wheels/
Node maps | profiles/
Browser data | bin/akamfy_data/


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
<li><strong>Progress Panel</strong> — operation log and progress bar for long tasks.</li>
<li><strong>Server Monitor</strong> — real-time ComfyUI server output with warning/error counters.</li>
<li><strong>HW Monitor</strong> — CPU, GPU, memory load and GPU temperature.</li>
<li><strong>Server Control</strong> — START/STOP buttons with session timer.</li>
<li><strong>AKAMFY Bar</strong> — toggle between AKA tabs and embedded ComfyUI browser.</li>
</ul>
<h3 data-heading="Center Panel">Center Panel</h3>
<ul>
<li><strong>MAiN tab</strong> — path configuration, system info, component downloads.</li>
<li><strong>VENVs tab</strong> — virtual environment management.</li>
<li><strong>WHEELs tab</strong> — wheel file installer.</li>
<li><strong>NODEs tab</strong> — custom nodes manager.</li>
<li><strong>TOOLs tab</strong> — Python versions, ComfyUI updates, package manager, links.</li>
</ul>
<h3 data-heading="Right Panel">Right Panel</h3>
<ul>
<li><strong>AKASHI Terminal</strong> — onboard computer with menu system, command line, sound synthesizer, voice notifications.</li>
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
<li><strong>REFRESH</strong> — reloads all tabs and system info.</li>
<li><strong>TERMINATE</strong> — stops server and exits AKA.</li>
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
<li><strong>GPU</strong> — GPU name and VRAM.</li>
<li><strong>DRIVER</strong> — NVIDIA driver version.</li>
<li><strong>CUDA</strong> — CUDA toolkit version.</li>
<li><strong>cuDNN</strong> — cuDNN version.</li>
<li><strong>OS</strong> — Windows version and architecture.</li>
</ul>
<h3 data-heading="DOWNLOAD Section">DOWNLOAD Section</h3>
<p>Pre-configured download buttons for common dependencies:</p>
<ul>
<li><strong>PYTHON</strong> — select version and click DWNLD to download the installer.</li>
<li><strong>CUDA</strong> — NVIDIA CUDA Toolkit installer.</li>
<li><strong>cuDNN</strong> — NVIDIA cuDNN archive.</li>
<li><strong>GIT</strong> — Git for Windows installer.</li>
</ul>
<p>All downloaded files are saved to <code>bin/downloads/</code> inside the AKA installation directory. The folder is created automatically on first use.</p>
<p>Versions are defined in <code>configs/paths.json</code> and can be customized with <strong>path_editor.exe</strong></p>
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
<li>Detects your GPU, driver, and CUDA version.</li>
<li>Suggests the best PyTorch build (or CPU-only if no GPU).</li>
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
<p>For HuggingFace authentication. <strong>ENTR</strong> toggles edit mode. The token is passed to ComfyUI as <code>--hf-token</code> on launch.</p>
<hr>
<h2 data-heading="WHEELs TAB — WHEEL FILE INSTALLER">WHEELs TAB — WHEEL FILE INSTALLER</h2>
<h3 data-heading="Wheels Table">Wheels Table</h3>
<p>Lists <code>.whl</code> files from the <code>wheels/</code> folder next to the executable. Columns:</p>
<ul>
<li><strong>Checkbox</strong> — select files to install or delete.</li>
<li><strong>FILE</strong> — wheel filename.</li>
<li><strong>SIZE</strong> — file size.</li>
</ul>
<h3 data-heading="INSTALL">INSTALL</h3>
<p>Installs selected wheels into the active environment using <code>pip install</code>.</p>
<h3 data-heading="DELETE">DELETE</h3>
<p>Removes selected wheel files from disk.</p>
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
<li><strong>DELETE</strong> — removes selected node folders.</li>
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
<h2 data-heading="TOOLs TAB — TOOLS &#x26; UTILITIES">TOOLs TAB — TOOLS &#x26; UTILITIES</h2>
<h3 data-heading="PYTHON VERSIONS">PYTHON VERSIONS</h3>
<p>Detects all Python installations from Windows registry and filesystem. Shows version buttons — click to switch the active system Python. This affects which Python is used for creating new venvs.</p>
<h3 data-heading="COMFYUI VERSION">COMFYUI VERSION</h3>
<ul>
<li><strong>CURRENT</strong> — installed version (from git or <code>comfyui_version.py</code>).</li>
<li><strong>LATEST</strong> — latest release from GitHub API.</li>
<li><strong>CHECK</strong> — queries GitHub for the latest version.</li>
<li><strong>UPDATE</strong> — pulls the latest tag and reinstalls requirements.</li>
<li><strong>DNDATE</strong> — rolls back to a previous version from the snapshot list.</li>
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
<li><code>splash</code> — sets the selected image as the splash screen. </li>
<li><code>beep &#x3C;quality> &#x3C;wave> &#x3C;notes></code> — plays a tone sequence. Quality: <code>hf</code>, <code>8b</code>, <code>cr</code>, <code>lf</code>. Wave: <code>sqr</code>, <code>tri</code>, <code>sin</code>. Notes format: <code>freq/duration;freq/duration</code> (e.g., <code>beep 8b sqr 440/0.5;880/0.3</code>).</li>
<li><code>snd on/off</code> — global sound toggle.</li>
<li><code>beep on/off</code> — enable/disable event beeps.</li>
<li><code>speech on/off</code> — enable/disable voice notifications.</li>
<li><code>cntrl on/off</code> — enable/disable server monitoring.</li>
<li><code>scr off</code> — turns off the AKASHI screen (terminal still functions). Any button press wakes it.</li>
<li><code>deft</code> — resets AKASHI settings to default.</li>
<li><code>deft aka</code> — resets all AKA settings to default.</li>
<li><code>info</code> — developer contact information.</li>
<li><code>help</code> — command list.</li>
<li><code>clear</code> — clears the display.</li>
</ul>
<h3 data-heading="BEEP Menu">BEEP Menu</h3>
<p>Manages the sound synthesizer:</p>
<ul>
<li><strong>PHRASES</strong> — saved tone sequences. Select and play with ENTR.</li>
<li><strong>SYNTH</strong> — help screen showing synthesizer syntax.</li>
<li><strong>FUNC</strong> — enables event beeps (boot, shutdown, confirm, cancel, click, error, warn).</li>
<li><strong>UNFUNC</strong> — disables event beeps.</li>
</ul>
<h3 data-heading="SPEECH Menu">SPEECH Menu</h3>
<p>Manages voice notifications:</p>
<ul>
<li><strong>FUNC</strong> — enables speech for events.</li>
<li><strong>UNFUNC</strong> — disables speech.</li>
</ul>
<p>Speech plays MP3 files from <code>assets/akaspeech/</code>. Triggers include server start/stop, job completion, job error, GPU overheating, and system warnings. Each event plays once — no looping. GPU warning re-arms when temperature drops below threshold and rises again.</p>
<h3 data-heading="CNTRL Menu">CNTRL Menu</h3>
<p>Master control for voice monitoring:</p>
<ul>
<li><strong>FUNC</strong> — enables CNTRL monitoring. Requires SPEECH FUNC to be on for voice.</li>
<li><strong>UNFUNC</strong> — disables CNTRL.</li>
</ul>
<p>CNTRL bridges server events to speech. It does not control beeps or speech directly — those are independent. Sound levels: SND (global mute) > SPEECH/BEEP (per-type) > CNTRL (events enabled).</p>
<h3 data-heading="VIEW Menu">VIEW Menu</h3>
<p>Image browser. Lists PNG files from the bundled assets. Arrow keys scroll. ENTR displays the selected image full-screen. The <code>splash</code> command in CMD mode sets the viewed image as the splash screen.</p>
<p>Hidden images (marked with <code>*</code>) are not visible until unlocked via the <code>unlock</code> command or earned through gameplay.</p>
<h3 data-heading="GAMES Menu">GAMES Menu</h3>
<p>Currently contains <strong>ARKANOID</strong> — a vector breakout game on the AKASHI screen. Control the paddle with AKASHI left/right arrows or keyboard arrows. Every 100 points unlocks a hidden image. ESC exits.</p>
<h3 data-heading="NFO Menu">NFO Menu</h3>
<p>Displays program information and credits.</p>
<h3 data-heading="EDIT Menu">EDIT Menu</h3>
<p>System settings:</p>
<ul>
<li><strong>ONSTART</strong> — auto-boot AKASHI when AKA launches.</li>
<li><strong>OFSTART</strong> — manual boot only.</li>
<li><strong>ONSND</strong> — sound enabled by default.</li>
<li><strong>OFSND</strong> — sound disabled by default.</li>
</ul>
<h3 data-heading="TOOLS Menu">TOOLS Menu</h3>
<p><strong>AKASKY ANTVIR</strong> — a humorous fake antivirus scanner.</p>
<h3 data-heading="SND Button">SND Button</h3>
<p>Global sound toggle. When off, all audio (beeps and speech) is muted regardless of other settings.</p>
<h3 data-heading="Sound Synthesizer">Sound Synthesizer</h3>
<p>The beep engine supports four quality levels affecting sample rate and bit depth.</p>
<p>Three waveforms: square, triangle, sine.</p>
<hr>
<h2 data-heading="AKAMFY BROWSER (Embedded ComfyUI)">AKAMFY BROWSER (Embedded ComfyUI)</h2>
<p>Toggle between AKA tabs and the ComfyUI interface using the <strong>AKAMFY MODE</strong> checkbox and the <code>AKAMFY >>></code> button in the left panel.</p>
<p>The browser loads <code>http://localhost:8188</code> when the server is running. It supports:</p>
<ul>
<li>Full WebGL rendering</li>
<li>File downloads (output images, models)</li>
<li>Persistent storage (cookies, localStorage, IndexedDB)</li>
<li>Session persistence between launches</li>
</ul>
<p>Data is stored in the <code>akamfy_data/</code> folder next to the executable.</p>
<hr>
<h2 data-heading="CONTACTS">CONTACTS</h2>
<ul>
<li><strong>Telegram:</strong> @Rimor_Spectator (questions and feedback)</li>
<li><strong>GitHub:</strong> github.com/Rimor-dev</li>
</ul>
<hr><!--EndFragment-->
</body>
</html>
