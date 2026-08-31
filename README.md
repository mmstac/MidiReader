# MIDI Piano Visualizer (v2)

A lightweight, browser-based app designed to visualize, learn, and practice piano pieces using standard MIDI (`.mid` or `.midi`) files. The notes display size and color can be easily configured for easy viewing, and the app allows stepping through the music either using the step button, microphone (key sound or voice), or waiting for the correct keys to be played on the midi keyboard.

This app operates entirely in your web browser, no external software, backend servers, drivers, or heavy libraries required.

## 🌟 What's New in v2

*   **Plug-and-Play Hardware Integration:** Automatically detects and connects to USB Class Compliant MIDI keyboards. Just plug your piano into your computer via USB, click "Connect MIDI", and start playing.
*   **Real-time Visual Feedback:** Accurately maps your physical key strokes to the virtual on-screen piano. 
    *   🟢 **Green Circle:** Perfect hit! You played the correct note at the correct time.
    *   🔴 **Red Circle:** Incorrect pitch or mistimed keystroke.
*   **WAIT / CONT Modes:** Train at your own pace. Switch the app to **WAIT** mode, and the timeline will gracefully pause at every upcoming note/chord until you press the exact corresponding keys on your physical hardware. 
*   **Smart Step Logic:** Advance through a song note-by-note with the press of a button. Alternatively, check the **Mic** box to step forward automatically using a spoken word, a hand clap, or by physically playing the piano note.

## ✨ Core Features

*   **88-Key UI:** Notes accurately fall toward a proportionately rendered 88-key piano bed.
*   **Intelligent Bounding-Box Camera:** The dynamic zoom camera looks ahead to upcoming chords and smoothly pushes the frame left or right just enough to keep all active notes perfectly in view. You can alternatively set a static zoom size.
*   **A/B Loop Training:** Isolate difficult measures by adjusting the dual-thumb loop slider. 
*   **Customize Display:** Open the settings menu to adjust note block font sizes and colors for specific notes. Settings are automatically saved to your browser.

## 🚀 Instructions

### 1. Open MIDI File and Select Tracks
You will need to have a midi file already downloaded to your device. Click on the OPEN MIDI FILE button and select it from the folder where it was saved. You will then see a list of available tracks, this will be different for each file. You can choose which tracks you want displayed. For midi files specifically for piano, often the left and right hand tracks will be separate so it is possible to practice only one hand.

<img width="300" alt="Track Selection Menu" src="https://github.com/user-attachments/assets/b6376f24-cbe5-47df-ac4b-db5aef1bd6c9" />

### 2. Connect to USB MIDI Keyboard (OPTIONAL)
Plug in your USB MIDI keyboard to your device and click on the CONNECT MIDI KEYBOARD button in the upper right corner. You should see a popup window confirming the device was found, and the device name will replace the connect button in the upper right corner.

<img width="300" alt="Connect USB Midi" src="https://github.com/user-attachments/assets/924dec04-cd2a-417d-863b-9bd7085c8f41" />


### 3. Main Interface

<img width="800" alt="Main Visualizer Interface" src="https://github.com/user-attachments/assets/c20972c2-5659-445c-af3e-6593a6ce70bc" />

*   **MODE:** CONT = continuous playback, WAIT = wait for correct keys to be pressed on the USB midi keyboard.
*   **PLAY / PAUSE:** start or pause the playback.
*   **STEP:** go to the next note, play it and pause/wait.
*   **MIC:** this can be used to sound/voice trigger the STEP button when selected, and the slider sets the mic sensitivity.
*   **SPEED:** adjust the playback speed, BPM also shown here.
*   **<img width="24" style="vertical-align: middle;" alt="Fullscreen Icon" src="https://github.com/user-attachments/assets/2f0edc04-75a2-4b05-b7cc-f1f240a4ebb5" /> FULLSCREEN:** toggle fullscreen mode.
*   **<img width="24" style="vertical-align: middle;" alt="Settings Icon" src="https://github.com/user-attachments/assets/957619e0-99f6-4592-9d50-45456707942d" /> SETTINGS:** customize note display.

<img width="400" alt="Settings Configuration Modal" src="https://github.com/user-attachments/assets/26ba7e7a-40a3-4ffb-acdd-0607eac1dfe6" />

*   **LOOP:** Set the A/B loop for which measures to repeat.
*   **TIME:** time progression slider.
*   **ZOOM:** controls the viewing window, a static zoom can be selected.
     Slider to the left displays the full keyboard. Slider to the right is dynamic auto zoom.
*   **VOLUME:** playback volume of the notes on the device.
*   **<img width="24" style="vertical-align: middle;" alt="Triangle" src="https://github.com/user-attachments/assets/631d9bab-a915-4768-ada7-8166a7095587" /> HIDE/SHOW:** Hide or show the interface


## 🚀 Installation & Usage

Because the app is fully self-contained within a single HTML file, setup takes less than a minute.

### Option 1: Live Demo (No Install Required)
You can try the app instantly directly from the web! 
1. Navigate to: `https://mmstac.github.io/MidiReader/` 

### Option 2: Local File
1. Download the `index.html` file to your computer.
2. Double click the file to open it. 
*(Note: If your operating system blocks the file with a security warning, right-click the file, select **Properties**, check the **Unblock** box, and open it in a modern browser like Chrome or Edge).*

### Option 3: Host Your Own Live Link
Host the file securely via GitHub Pages to bypass local browser security blocks and enable seamless hardware access.
1. Fork or clone this repository to your own GitHub account.
2. Go to your repository's **Settings** > **Pages**.
3. Under "Build and deployment", select the `main` branch and click Save.
4. After a minute, your app will be live at: `https://[your-username].github.io/MidiReader/`


> ⚠️ **A Note on Web MIDI Compatibility:**
> *   **Windows / macOS:** The Web MIDI API is natively supported on Chromium-based browsers (Chrome, Edge, Opera) and Firefox. Note that on Windows, Chrome may take an "exclusive lock" on your MIDI port, meaning you cannot run this visualizer simultaneously with a DAW (like Ableton). Mac's CoreMIDI allows multi-client routing natively.
> *   **iOS / iPadOS:** Apple does not permit hardware MIDI connections through standard Safari. To use this app with a physical keyboard on an iPad, download a third-party app such as *Web MIDI Browser*. 

## 🛠 Built With
*   Standard **HTML5**, **JavaScript**, **Web Audio API**, and **Web MIDI API**
*   [Tailwind CSS](https://tailwindcss.com/) for UI styling
*   [@tonejs/midi](https://github.com/Tonejs/Midi) for parsing binary `.mid` files
*   Coding/debugging with help of Gemini and ChatGPT.
