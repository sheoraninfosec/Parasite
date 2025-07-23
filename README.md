<h1>🦠 parasite.exe</h1>


#### A Stealthy Keylogger + Spreader Prototype

**parasite.exe** is an experimental stealth spyware that logs keystrokes, transmits captured data via email, and silently spreads via USB drives. Designed to be lightweight and evasive, it operates on Windows systems (XP and later) and is highly resistant to detection by traditional antivirus software.

> ⚠️ **Strictly for educational and cybersecurity research purposes only.**

---

### 📁 Components

- `parasite.cpp` – Core spyware module: keylogger, mailer, USB infect routine.
- `infect.cpp` – Payload loader from infected USB drives.
- `transmit.exe` – Sends the collected data using a command-line curl executable.
- `auto-launch.lnk` – Drop-in startup shortcut for persistence.
- `bait.lnk` – Disguised shortcut in USB drives that activates the infection.
- `decoder.cpp` – Decodes incoming email payloads to readable format.

---

### 🔧 Setup

<ol>
<li>
<b>Preparation</b>
  <ol>
    <li>Clone or download the full repo from this project.</li>
    <li>In `parasite.cpp`, edit the <b>sendData()</b> method to include your email credentials.
    <div align="center">
      <img src="https://cloud.githubusercontent.com/assets/5456665/21505255/c5c3db2e-cc8f-11e6-834f-1312e566a7ed.png" width="600px"/>
    </div>
    </li>
    <li>Compile `parasite.cpp` and `infect.cpp` with a C++ compiler. Place all compiled files in the same directory:
      - `parasite.exe`
      - `infect.exe`
      - `transmit.exe`
      - `auto-launch.lnk`
      - `bait.lnk`
    </li>
    <li>Run `parasite.exe` and insert a USB device. A hidden payload folder and disguised `.lnk` file will appear.</li>
  </ol>
</li>
<br/>
<li>
<b>Attack Flow</b>
  <ol>
    <li>Insert the infected USB into a target PC and run `bait.lnk`. The spyware installs silently.</li>
    <li>On next reboot, spyware activates and starts logging. It also infects any new USB inserted thereafter.</li>
  </ol>
</li>
<br/>
<li>
<b>Data Collection</b>
  <ol>
    <li>Wait a few days for emails to begin arriving.</li>
    <li>Copy each email's body into a `.txt` file.</li>
    <li>Run `decoder.exe` to clean up the encoded data into readable form.
    <div align="center">
      <img src="https://cloud.githubusercontent.com/assets/5456665/21505528/59e92b0e-cc92-11e6-90bf-a050ed920ee9.png" width="600px"/>
    </div>
    </li>
  </ol>
</li>
</ol>

---

### 🧠 Behind the Scenes

This project serves as a learning sandbox for:

- Building stealthy malware behaviors.
- USB propagation mechanics.
- Evasion techniques.
- Basic cryptography and encoding/decoding.
- Windows system internals (startup persistence, user behavior monitoring).

---

### 🚨 Disclaimer

This project is intended for ethical hacking education, academic research, and red-team simulation **only**. Misuse is strictly discouraged and the author takes **no responsibility** for any harm or legal violations resulting from abuse of this project.

**parasite.exe** includes minor obfuscations and incomplete documentation intentionally — it's up to the learner to fill in the gaps. True understanding comes from debugging, experimenting, and exploring.

---

### 📜 License

<p align="left">
  <a rel="license" href="https://opensource.org/licenses/MIT">
    <img alt="MIT License" src="https://cloud.githubusercontent.com/assets/5456665/18950087/fbe0681a-865f-11e6-9552-e59d038d5913.png" width="60em"/>
  </a>
</p>

**parasite.exe** © [Jigesh Sheoran](https://github.com/sheoraninfosec) is licensed under the [MIT License](https://opensource.org/licenses/MIT).
