# Capture-to-Reproduction Audio Study

A portfolio repository documenting progression from [recording engineering](https://github.com/kevinworleymusic-afk/engineering-development-portfolio/tree/main/Projects/Technical-Audio-and-Research/Ocean-Way-Jazz-Combo-Dolby-Atmos-Independent-Study) toward loudspeaker systems, digital signal processing, critical listening, and automotive audio reproduction.

## Publication status

This repository contains **independent educational and portfolio work, not peer-reviewed or formally published research**. Citations to published literature are supporting references and do not imply that the studies or analyses in this repository have been academically published.

## Project overview

The repository traces the audio chain from acoustic capture to final reproduction. It builds on previous graduate work in Audio Engineering, including immersive recording-array design, natural ensemble capture, technical measurement, and signal-chain analysis.

The central engineering question is:

> *What is lost, preserved, or transformed between the moment sound is captured and the moment it is reproduced, and how can engineering decisions at each stage be made intentionally?*

Areas of focus include acoustic capture, signal-chain integrity, real-time DSP, loudspeaker reproduction, critical listening, system measurement, and automotive cabin acoustics.

---

# Project 01: Real-Time DSP Prototype in Pure Data

**Status:** Implemented educational prototype under continued technical review

- [Full project documentation](docs/01_Real-Time_DSP_Prototype_in_Pure_Data.md)
- [Original Pure Data patch](assets/pure-data/Sample_Circuit.pd)
- [Clean layout, Version 2](assets/pure-data/Sample_Circuit_Clean_v2.pd)

**Programming / DSP environment:** [Pure Data](https://puredata.info/) (`.pd`) — a visual dataflow programming environment for real-time audio and multimedia systems. The repository's [GitHub Linguist configuration](.gitattributes) explicitly includes the two `.pd` patches in language statistics.

Pure Data provides an accessible graphical environment for prototyping signal flow, routing, gain, delay, filtering, test signals, and control behavior. Those concepts are transferable to node-based commercial DSP environments such as Audio Weaver, making this project useful preparation when Audio Weaver access is unavailable. Pure Data is not presented as a complete substitute for Audio Weaver's proprietary modules, embedded-target integration, deployment workflow, automotive middleware, or production validation tools.

This is the first active implementation project in the repository. The Pure Data patch functions as a small real-time DSP workbench covering:

- stereo audio-file selection and playback
- sum-and-difference processing experiments
- independent left and right delay lines
- voltage-controlled and high-pass filtering
- separate left and right output gain
- an 80 Hz low-frequency branch with independent level control
- 1 kHz sine and broadband-noise test generation
- envelope-derived level-control experiments
- output clipping and separate stereo DAC routing

Version 2 reorganizes the same stored DSP connection graph into clearly labeled sections for source playback, sum/difference processing, delay, filtering, diagnostics, test signals, low-frequency processing, output levels, and channel outputs. The cleaner layout improves readability and maintainability without presenting the prototype as a finished automotive processor.

The project documentation identifies what is implemented, what still requires validation, and how the patch can be tested with known signals before being extended into later Python, GNU Octave, SigmaStudio, loudspeaker, or vehicle work.

---

## Foundation documents

- [Engineering Study Template](docs/00_Engineering_Study_Template.md)
- [From Capture to Reproduction: Establishing the Engineering Foundation](docs/Engineering_Foundation_From_Capture_to_Reproduction.md)

These documents establish the systems-level framework connecting capture, processing, acoustics, reproduction, measurement, and perception.

## Future projects

Planned, proposed, conditional, and access-dependent projects are grouped separately in the [Future Projects folder](docs/Future-Projects/) so they are not visually blended with work that already contains an implementation artifact.

The future-project group currently covers:

- a software-in-the-loop automotive CAN/DBC simulation
- a conceptual 25-speaker automotive immersive architecture
- a representative GNU Octave/Python DSP simulation
- a controlled vehicle acoustic-measurement campaign
- a proposed open-room versus simulated-cabin immersive evaluation
- a planned measurement-guided SigmaStudio follow-up
- a conditional installed-car-DSP development platform
- optional hardware, embedded-C, Audio Weaver, and physical-CAN extensions

These remain plans rather than completed-work claims.

---

## Repository structure

```text
capture-to-reproduction-audio-study/
├── README.md
├── docs/
│   ├── 00_Engineering_Study_Template.md
│   ├── Engineering_Foundation_From_Capture_to_Reproduction.md
│   ├── 01_Real-Time_DSP_Prototype_in_Pure_Data.md
│   ├── Future-Projects/
│   │   ├── 02_Automotive_Audio_Implementation_Roadmap.md
│   │   ├── 03_Immersive_Audio_Evaluation_Part_2_SigmaStudio_DSP_Project.md
│   │   └── 04_Conditional_Car_DSP_Installation_and_Portfolio_Validation_Plan.md
│   └── engineering-evolution/
├── diagrams/
├── references/
├── results/
└── assets/
    └── pure-data/
        ├── Sample_Circuit.pd
        └── Sample_Circuit_Clean_v2.pd
```

## Related repositories

- [Technical Audio Engineering Portfolio](https://github.com/kevinworleymusic-afk/engineering-development-portfolio)
- [Audio File Report](https://github.com/kevinworleymusic-afk/audio-file-report)
- [Technical Ear Training](https://github.com/kevinworleymusic-afk/technical-ear-training)
- [Dolby Atmos Recording Independent Study](https://github.com/kevinworleymusic-afk/engineering-development-portfolio/tree/main/Projects/Technical-Audio-and-Research/Ocean-Way-Jazz-Combo-Dolby-Atmos-Independent-Study)

## License

This repository is for portfolio and educational purposes.

All original written content, diagrams, and documentation authored in this repository are released under the [Creative Commons Attribution 4.0 International License](https://creativecommons.org/licenses/by/4.0/).

Third-party references, citations, and source materials retain their original licenses and are included solely for educational commentary.
