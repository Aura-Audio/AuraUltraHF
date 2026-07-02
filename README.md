# 🎛️ UHF Sound Lab
### Ultra-High Frequency Generator & Audio Testing Suite (17.5 kHz — 24 kHz)

![HTML5](https://img.shields.io/badge/HTML5-E34F26?style=flat-square&logo=html5&logoColor=white)
![CSS3](https://img.shields.io/badge/CSS3-1572B6?style=flat-square&logo=css3&logoColor=white)
![JavaScript](https://img.shields.io/badge/Vanilla%20JS-F7DF1E?style=flat-square&logo=javascript&logoColor=black)
![Web Audio API](https://img.shields.io/badge/Web%20Audio%20API-AudioNode-ff5c7c?style=flat-square)
![License](https://img.shields.io/badge/License-MIT-green.svg?style=flat-square)

---

## 📖 Overview

**UHF Sound Lab** is a lightweight, browser-based audio synthesis tool specifically engineered to explore, test, and manipulate the ultra-high frequency (UHF) and pre-ultrasonic spectrum (**17.5 kHz to 24 kHz**).

While standard audio tools focus on the human hearing range (20 Hz – 20 kHz), this application targets the upper limits of human perception and the physical capabilities of modern smartphone and laptop DACs/speakers. It is designed for audio engineers, hardware testers, acoustic researchers, and curious audiophiles who need to generate precise high-frequency tones, shape ultrasonic noise, or test speaker roll-off characteristics without installing dedicated desktop software.

Built entirely on the **Web Audio API**, it runs client-side with zero backend dependencies, ensuring ultra-low latency and real-time parameter automation.

---

## ✨ Core Features

### 🎛️ Precision Generators
*   **Tone Generator:** Sine, Square, Sawtooth, and Triangle waves (17.5k – 24k Hz). Includes micro-detuning and **Binaural Mode** for high-frequency beat frequency experimentation.
*   **Noise Generator:** White, Pink, Brown, and **Blue** noise profiles. Features a dedicated High-Pass Filter (HPF) and adjustable Resonance (Q) to isolate the ultrasonic band.
*   **Sweep Generator:** Automated frequency sweeps with configurable start/end points, durations, and curves (Linear, Logarithmic/Exponential, Reverse).

### 🎚️ Modulation & Effects Chain
*   **Tremolo & Vibrato:** LFO-driven amplitude and frequency modulation with adjustable rates and depths.
*   **Filtering:** Master Low-Pass Filter (LPF) and a Band-Pass Focus node to isolate specific ultrasonic resonances.
*   **Delay Line:** Configurable delay time and feedback loops to create high-frequency comb-filtering and spatial echoes.
*   **Pulse/Pattern Mode:** Rhythmic gating with customizable On/Off times and Attack/Release ramps for testing transient response.

### 📊 Advanced Visualization
*   **Real-time Waveform:** High-resolution time-domain rendering.
*   **UHF Spectrum Analyzer:** Frequency-domain visualization *zoomed specifically to the 15 kHz – 24 kHz range* for precise harmonic inspection.
*   **Spectrogram (Waterfall):** A scrolling time-frequency heatmap to visualize sweeps, noise shaping, and intermodulation distortion.

### 🚀 Quality of Life
*   **One-Click Presets:** Mosquito Tone (17.5k), Teen Tone (19k), Ultra Sweep, UHF Hiss, Binaural Edge, and Pulse Train.
*   **Click-Free Automation:** All parameters utilize `setTargetAtTime` to prevent audio artifacts and DAC pops during live adjustments.
*   **Zero-Install:** A single self-contained `index.html` file. No build tools, no npm, no frameworks required.

---

## ⚠️ Important Hardware & Safety Disclaimers

> **Hardware Limitations:**
> Most built-in smartphone and laptop speakers have a severe physical roll-off above **16 kHz – 18 kHz**. If you generate a 20 kHz tone and hear nothing, the audio *is* being generated, but your hardware cannot reproduce it. For accurate testing, use high-quality wired IEMs, studio monitor headphones, or dedicated tweeter arrays.
>
> **Safety Warning:**
> While ultrasonic frequencies are largely inaudible to adults, high Sound Pressure Levels (SPL) in the 17.5k – 24k range can still cause physical discomfort, ear fatigue, or damage to the inner ear. **Always start with the master volume near zero and gradually increase.** Avoid prolonged exposure to intense UHF signals.

---

## 🚀 Getting Started

Because UHF Sound Lab is a pure frontend application, running it is trivial:

**Method 1: Direct Execution**
1. Download or clone this repository.
2. Open `index.html` directly in any modern web browser (Chrome, Edge, Firefox, or Safari recommended).
3. Click "Start" on any generator module. *(Note: Browsers require user interaction to unlock the Web Audio API context).*

**Method 2: Local Server (Recommended for CORS)**
```bash
# Using Python 3
python -m http.server 8000

# Using Node.js (http-server)
npx http-server -p 8000
```
Navigate to `http://localhost:8000` in your browser.

---

## 🗺️ Roadmap (Future Features)

We are actively working on expanding UHF Sound Lab into a comprehensive acoustic testing suite. Planned features include:

### Phase 1: Analysis & Export (Q3 2026)
- [ ] **WAV Export / Recording:** Record the generated UHF signals directly to a `.wav` file for use in external DAWs.
- [ ] **Microphone Input Analysis:** Pass-through mode to analyze the room's acoustic response to UHF sweeps via the device microphone.
- [ ] **THD+N Metering:** Real-time Total Harmonic Distortion + Noise calculation for hardware testing.

### Phase 2: Clinical & Testing Tools (Q4 2026)
- [ ] **Interactive Audiogram:** A guided hearing test to map the user's exact high-frequency hearing threshold curve (presbycusis mapping).
- [ ] **Frequency Masking Tests:** Simultaneous mid-range and UHF tone generation to test psychoacoustic masking effects.
- [ ] **Notch Filters:** Surgical parametric EQ to remove specific ultrasonic feedback frequencies.

### Phase 3: Spatial & Advanced Routing (2027)
- [ ] **HRTF Spatial Audio:** 3D panning using Web Audio `PannerNode` to test ultrasonic directionality perception.
- [ ] **Multi-Oscillator Stacking:** Add up to 4 independent UHF oscillators to test complex intermodulation distortion.
- [ ] **Web MIDI Support:** Map hardware MIDI controllers to UHF frequency sweeps and effect parameters.

---

## 🛠️ Tech Stack

*   **HTML5 / CSS3:** Responsive, mobile-friendly dark-mode UI using CSS Grid and custom properties.
*   **Vanilla JavaScript (ES6+):** No frameworks (React/Vue) to ensure maximum performance and zero bundle size.
*   **Web Audio API:** Core synthesis engine utilizing `OscillatorNode`, `AudioBufferSourceNode`, `BiquadFilterNode`, and `AnalyserNode`.
*   **HTML5 Canvas API:** High-performance 60fps rendering for the Spectrum Analyzer and Spectrogram.

---

## 🤝 Contributing

Contributions, issues, and feature requests are welcome!
If you are an acoustic engineer or Web Audio developer and want to improve the DSP algorithms (especially the Pink/Brown/Blue noise generation filters), please feel free to submit a Pull Request.

1. Fork the Project
2. Create your Feature Branch (`git checkout -b feature/AmazingFeature`)
3. Commit your Changes (`git commit -m 'Add some AmazingFeature'`)
4. Push to the Branch (`git push origin feature/AmazingFeature`)
5. Open a Pull Request

---

## 📄 License

Distributed under the MIT License. See `LICENSE` for more information.

---

<p align="center">
  <b>Built for the frequencies you feel, rather than hear.</b><br>
  <sub>If you use this tool for hardware testing or research, please consider citing or starring the repository!</sub>
</p>
