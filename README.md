# MIDI Piano Visualizer (v2)

A lightweight, browser-based app designed to visualize, learn, and practice piano pieces using standard MIDI (`.mid` or `.midi`) files. 

This app operates entirely in your web browser. It leverages HTML5 Canvas, the Web Audio API, and the Web MIDI API to locally parse, synthesize, and visually render tracks—no external software, backend servers, drivers, or heavy sample libraries required.

## 🌟 What's New in v2

*   **Plug-and-Play Hardware Integration:** Automatically detects and connects to USB Class Compliant MIDI keyboards. Just plug your piano into your computer via USB, click "Connect MIDI", and start playing.
*   **Real-time Visual Feedback:** Accurately maps your physical key strokes to the virtual on-screen piano. 
    *   🟢 **Green Circle:** Perfect hit! You played the correct note at the correct time.
    *   🔴 **Red Circle:** Incorrect pitch or mistimed keystroke.
*   **WAIT / CONT Modes:** Train at your own pace. Switch the app to **WAIT** mode, and the timeline will gracefully pause at every upcoming chord until you press the exact corresponding keys on your physical hardware. 
*   **Smart Step Logic:** Advance through a song chord-by-chord with the press of a button. Alternatively, check the **Mic** box to step forward automatically using a spoken word, a hand clap, or by physically playing the piano note.

## ✨ Core Features

*   **Realistic 88-Key UI:** Notes accurately fall toward a proportionately rendered 88-key piano bed. Black keys are sized realistically to prevent optical illusions and overlaps.
*   **Intelligent Bounding-Box Camera:** The dynamic zoom camera looks ahead to upcoming chords and smoothly pushes the frame left or right just enough to keep all active notes perfectly in view. 
*   **A/B Loop Training:** Isolate difficult measures by adjusting the dual-thumb loop slider. 
*   **Deep Customization:** Open the settings menu to adjust block sizes, font colors, and customize the color family for specific notes. Settings are automatically saved to your browser.

## 🚀 Installation & Usage

Because the app is fully self-contained within a single HTML file, setup takes less than a minute.

### Option 1: Live Web Link (Recommended)
Host the file securely via GitHub Pages to bypass local browser security blocks and enable seamless hardware access.
1. Fork or clone this repository to your own GitHub account.
2. Go to your repository's **Settings** > **Pages**.
3. Under "Build and deployment", select the `main` branch and click Save.
4. After a minute, your app will be live at: `https://[your-username].github.io/midi-piano-visualizer/`

### Option 2: Local File
1. Download the `index.html` file to your computer.
2. Double click the file to open it. 
*(Note: If your operating system blocks the file with a security warning, right-click the file, select **Properties**, check the **Unblock** box, and open it in a modern browser like Chrome or Edge).*

> ⚠️ **A Note on Web MIDI Compatibility:**
> *   **Windows / macOS:** The Web MIDI API is natively supported on Chromium-based browsers (Chrome, Edge, Opera) and Firefox. Note that on Windows, Chrome may take an "exclusive lock" on your MIDI port, meaning you cannot run this visualizer simultaneously with a DAW (like Ableton). Mac's CoreMIDI allows multi-client routing natively.
> *   **iOS / iPadOS:** Apple does not permit hardware MIDI connections through standard Safari. To use this app with a physical keyboard on an iPad, download a third-party app such as *Web MIDI Browser*. 

## 🛠 Built With
*   Standard **HTML5**, **JavaScript**, **Web Audio API**, and **Web MIDI API**
*   [Tailwind CSS](https://tailwindcss.com/) for UI styling
*   [@tonejs/midi](https://github.com/Tonejs/Midi) for parsing binary `.mid` files
