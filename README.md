# hush-core (Hush Audio Workstation)

[![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg)](https://opensource.org/licenses/MIT)
[![C++ Standard](https://img.shields.io/badge/C%2B%2B-17-blue.svg)](https://en.cppreference.com/w/cpp/17)
[![Build Status](https://img.shields.io/badge/build-passing-brightgreen.svg)]()

> A modern, high-performance, zero-telemetry C++17 audio engine and modular digital audio workstation workspace[span_0](start_span)[span_0](end_span).

---

## 📖 Overview

**hush-core** is an advanced audio workstation repository engineered with clean C++17 architecture, native GUI implementations, and privacy-first zero-telemetry design principles[span_1](start_span)[span_1](end_span). It provides a modular framework incorporating dedicated engines for immersive audio mixing, MIDI notation, plugin hosting, video probing, neural composition assistance, and session core routing[span_2](start_span)[span_2](end_span).

---

## 🛠️ Completed Core Builds (Tier 1)

The repository successfully implements the first foundational wave of build targets:

1. **`hush-render` (`engines/render/`)**[span_3](start_span)[span_3](end_span)
   * **Target:** Immersive mixer CLI (`hush-render`) and static library (`hush_render`)[span_4](start_span)[span_4](end_span).
   * **Features:** Plain-text scene file parsing, custom std::-only PCM/float32 WAV reader, object-based panning via `hush::immersive`, and speaker level JSON output generation[span_5](start_span)[span_5](end_span).

2. **`hush-score` (`engines/score-cli/`)**[span_6](start_span)[span_6](end_span)
   * **Target:** MIDI to MusicXML to engraved score CLI (`hush-score`) and static library (`hush_score_cli`)[span_7](start_span)[span_7](end_span).
   * **Features:** Built-in std::-only Standard MIDI File (SMF) parser, tempo map/time signature extraction, MusicXML 3.1 export, and optional LilyPond PDF integration[span_8](start_span)[span_8](end_span).

3. **`hush-probe` (`engines/probe/`)**[span_9](start_span)[span_9](end_span)
   * **Target:** Video probe and thumbnail extractor CLI (`hush-probe`) and static library (`hush_probe`)[span_10](start_span)[span_10](end_span).
   * **Features:** FFmpeg video integration, strict MovieInfo JSON serialization, and a custom std::-only PNG thumbnail writer across timeline markers[span_11](start_span)[span_11](end_span).

---

## 🚀 Getting Started & Build Instructions

### Prerequisites
Ensure your build environment satisfies the following requirements:
* CMake 3.16 or higher[span_12](start_span)[span_12](end_span)
* A C++17 compliant compiler with `-Wall -Wextra` support[span_13](start_span)[span_13](end_span)
* Optional: FFmpeg development headers (for video features)[span_14](start_span)[span_14](end_span)

### Compilation

Clone the repository and build the workspace using CMake:

```bash
git clone [https://github.com/ljrseals-dev/hush-core.git](https://github.com/ljrseals-dev/hush-core.git)
cd hush-core
cmake -S . -B build
cmake --build build
