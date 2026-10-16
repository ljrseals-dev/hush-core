```markdown
# hush-core (Hush Audio Workstation)

[![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg)](https://opensource.org/licenses/MIT)
[![C++ Standard](https://img.shields.io/badge/C%2B%2B-17-blue.svg)](https://en.cppreference.com/w/cpp/17)
[![Build Status](https://img.shields.io/badge/build-passing-brightgreen.svg)]()

> A modern, high-performance, zero-telemetry C++17 audio engine and modular digital audio workstation workspace.

---

## 📖 Overview

**hush-core** is available at [https://github.com/ljrseals-dev/hush-core](https://github.com/ljrseals-dev/hush-core). It is an advanced audio workstation repository engineered with clean C++17 architecture, native implementations, and privacy-first zero-telemetry design principles. It provides a complete modular framework incorporating dedicated engines for immersive audio mixing, MIDI notation, plugin hosting, video probing, neural composition assistance, and session core routing.

---

## 🗺️ Repository Architecture & Roadmap

![Hush DAW Repository Core Implementations & Roadmap](1562.jpg)[span_0](start_span)[span_0](end_span)

---

## 🛠️ Completed Implementations

The repository successfully implements the full lifecycle of build targets across all development phases:

### Tier 1: Foundational Engines
1. **`hush-render` (`engines/render/`)**
   * **Target:** Immersive mixer CLI (`hush-render`) and static library (`hush_render`).
   * **Features:** Plain-text scene file parsing, custom std::-only PCM/float32 WAV reader, object-based panning via `hush::immersive`, and speaker level JSON output generation.

2. **`hush-score` (`engines/score-cli/`)**
   * **Target:** MIDI to MusicXML to engraved score CLI (`hush-score`) and static library (`hush_score_cli`).
   * **Features:** Built-in std::-only Standard MIDI File (SMF) parser, tempo map/time signature extraction, MusicXML 3.1 export, and optional LilyPond PDF integration.

3. **`hush-probe` (`engines/probe/`)**
   * **Target:** Video probe and thumbnail extractor CLI (`hush-probe`) and static library (`hush_probe`).
   * **Features:** FFmpeg video integration, strict MovieInfo JSON serialization, and a custom std::-only PNG thumbnail writer across timeline markers.

### Tier 2: Advanced Spatial & Neural Modules
4. **`hush-immersive` (`engines/immersive/`)**
   * **Target:** Object-based immersive library and renderer.
   * **Features:** Comprehensive multi-channel layouts (Mono to 9.1.6, Ambisonics FOA/SOA/HOA3 with ACN/SN3D normalisation), distance attenuation, binaural fold-down, and ADM/BW64 metadata export (`exportAdm`).

5. **`hush-neural-lite` / `composer` (`composer/neural-lite/`)**
   * **Target:** Rule-based harmony engine and style continuation suite.
   * **Features:** Roman-numeral chord progressions, cadence detection, voice-leading cost evaluation, key detection via Krumhansl-Schmuckler profiles, and Markov transition models for pop, jazz, classical, and ambient styles.

### Tier 3: Core DAW Orchestration
6. **`hush-daw-core` (`engines/daw_core/`)**
   * **Target:** Comprehensive session engine (`hush-daw` CLI and `hush_daw_core` library).
   * **Features:** Unified Session management for audio, MIDI, video, and object tracks; topological DAG RenderGraph with cycle detection; headless Transport controls; and portable binary file serialization (`HUSHSESS`).

---

## 🚀 Getting Started & Build Instructions

### Prerequisites
Ensure your build environment satisfies the following requirements:
* CMake 3.16 or higher
* A C++17 compliant compiler with `-Wall -Wextra` support
* Optional: FFmpeg development headers (for video features)

### Compilation

Clone the repository and build the workspace using CMake:

```bash
git clone [https://github.com/ljrseals-dev/hush-core.git](https://github.com/ljrseals-dev/hush-core.git)
cd hush-core
cmake -S . -B build
cmake --build build

```
### Running Tests
Execute the automated test suites via CTest:
```bash
cd build
ctest --output-on-failure

```
## 💻 Usage Examples
 * **Render an Immersive Scene:**
   ```bash
   hush-render scene.txt --out output.wav --levels levels.json
   
   ```
 * **Convert MIDI to MusicXML / Text Score:**
   ```bash
   hush-score input.mid --xml score.xml --text score.txt
   
   ```
 * **Probe a Video File:**
   ```bash
   hush-probe video.mp4 --json info.json --thumbs 8 --out thumbs/
   
   ```
 * **Manage Session Core & Render DAW Projects:**
   ```bash
   hush-daw render session.hush --out final_mix.wav --seconds 30
   
   ```
## 🤝 Contributing
Contributions, issues, and architectural expansions are welcome. Please ensure all contributions adhere to the strict zero-warning policy, C++17 standards, and modern RAII memory paradigms.
## 📝 License
Distributed under the MIT License. See LICENSE for more information.
```

```
