# Capture-to-Reproduction Audio Study

A portfolio repository documenting progression from [recording engineering](https://github.com/kevinworleymusic-afk/engineering-development-portfolio/tree/main/Projects/Technical-Audio-and-Research/Ocean-Way-Jazz-Combo-Dolby-Atmos-Independent-Study) toward loudspeaker system design, [DSP](https://github.com/kevinworleymusic-afk/engineering-development-portfolio/tree/main/Projects/Coding-and-Audio-Software/MATLAB-Projects), and automotive audio reproduction.

## Publication Status

This repository contains **independent educational and portfolio work, not peer-reviewed or formally published research**. Citations to published literature are supporting references and do not imply that the studies or analyses in this repository have been academically published.

---

## Project Overview

This repository serves as a [structured engineering portfolio](docs/) tracing the audio signal chain from [acoustic capture](https://github.com/kevinworleymusic-afk/engineering-development-portfolio/tree/main/Projects/Technical-Audio-and-Research/Ocean-Way-Jazz-Combo-Dolby-Atmos-Independent-Study) to final reproduction.

It builds upon [previous graduate work in Audio Engineering](https://www.belmont.edu/academics/majors-programs/ms-audio-engineering/), including the design of an [immersive Dolby Atmos Session Layout](https://github.com/kevinworleymusic-afk/engineering-development-portfolio/blob/main/Projects/Technical-Audio-and-Research/Ocean-Way-Jazz-Combo-Dolby-Atmos-Independent-Study/Session-Layout.pdf) and studies of [natural ensemble recording techniques](https://github.com/kevinworleymusic-afk/engineering-development-portfolio/tree/main/Projects/Technical-Audio-and-Research/Ocean-Way-Jazz-Combo-Dolby-Atmos-Independent-Study). Those projects investigated how [microphone placement, room acoustics, and recording methodology](https://github.com/kevinworleymusic-afk/engineering-development-portfolio/tree/main/Projects/Technical-Audio-and-Research/Ocean-Way-Jazz-Combo-Dolby-Atmos-Independent-Study) influence the accurate capture of an acoustic event.

This repository continues that work by exploring the engineering decisions required to reproduce those captured sound fields through loudspeaker systems, [digital signal processing](https://github.com/kevinworleymusic-afk/engineering-development-portfolio#audio-dsp-and-software), and automotive audio system design.

Rather than viewing recording and reproduction as separate disciplines, this project approaches them as complementary stages of the same engineering problem.

---

## Engineering Theme

The central question guiding this portfolio is:

> *What is lost, preserved, or transformed between the moment sound is captured and the moment it is reproduced — and how can engineering decisions at every stage of that chain be made intentionally?*

Specific areas of focus include:

- [**Acoustic capture**](https://github.com/kevinworleymusic-afk/engineering-development-portfolio/tree/main/Projects/Technical-Audio-and-Research/Ocean-Way-Jazz-Combo-Dolby-Atmos-Independent-Study) — microphone polar patterns, placement geometry, room interaction, and ensemble balance
- [**Signal chain integrity**](https://github.com/kevinworleymusic-afk/engineering-development-portfolio/tree/main/Projects/Technical-Audio-and-Research/Studer-A80-vs-A800-Plugin-Validation-Study) — gain structure, analog-to-digital conversion, and file-format considerations
- **Loudspeaker system design** — driver selection, enclosure modeling, and crossover topology
- [**Digital signal processing**](https://github.com/kevinworleymusic-afk/engineering-development-portfolio/tree/main/Projects/Coding-and-Audio-Software/MATLAB-Projects) — equalization, time alignment, and room correction
- **Automotive audio** — cabin acoustics, boundary effects, and reproduction challenges unique to vehicle interiors
- [**Critical listening**](https://github.com/kevinworleymusic-afk/technical-ear-training) — connecting a quantified [SoundGym SPI and Diamond Ears record](https://www.soundgym.co/member/profile?m=byy1s26wj7u), continued Jason Corey-based training, and structured listening observations to measurement and system evaluation

---

## Foundation

This repository continues several previous engineering studies, including:

- [**Dolby Atmos Recording Array Design**](https://github.com/kevinworleymusic-afk/engineering-development-portfolio/blob/main/Projects/Technical-Audio-and-Research/Ocean-Way-Jazz-Combo-Dolby-Atmos-Independent-Study/Session-Layout.pdf)
  - [Design and documentation of a microphone layout](https://github.com/kevinworleymusic-afk/engineering-development-portfolio/tree/main/Projects/Technical-Audio-and-Research/Ocean-Way-Jazz-Combo-Dolby-Atmos-Independent-Study) intended for immersive audio capture in a Dolby Atmos production workflow.
- [**Natural Ensemble Recording Methodology**](https://github.com/kevinworleymusic-afk/engineering-development-portfolio/tree/main/Projects/Technical-Audio-and-Research/Ocean-Way-Jazz-Combo-Dolby-Atmos-Independent-Study)
  - Investigation of microphone-array techniques and recording practices aimed at preserving a realistic acoustic presentation with minimal reliance on corrective post-production.
- [Additional recording, acoustics, and production projects completed during graduate study](https://github.com/kevinworleymusic-afk/engineering-development-portfolio#major-technical-audio-and-applied-engineering-projects).

The studies in this repository extend those capture-focused investigations into the reproduction side of the signal chain, including loudspeaker systems, DSP, room and vehicle acoustics, and objective system evaluation.

## Repository Structure

```

capture-to-reproduction-audio-study/
├── README.md           # This file — repository overview and navigation
├── docs/               # Written documentation, study notes, and engineering write-ups
├── diagrams/           # Signal flow charts, system block diagrams, and schematic references
├── references/         # Source materials, citations, and annotated reading lists
├── results/            # Measurements, simulation outputs, and analysis artifacts
└── assets/             # Images, audio samples, Pure Data patches, and supporting media files
```

### Current `docs/` Contents

- [docs/README.md](docs/README.md) — overview and organization notes for repository documentation
- [docs/00_Engineering_Study_Template.md](docs/00_Engineering_Study_Template.md) — standard template for engineering studies and technical reports
- [docs/01_From_Capture_to_Reproduction_Establishing_the_Engineering_Foundation.md](docs/01_From_Capture_to_Reproduction_Establishing_the_Engineering_Foundation.md) — systems-level engineering foundation
- [docs/02_Automotive_Audio_Implementation_Roadmap.md](docs/02_Automotive_Audio_Implementation_Roadmap.md) — prioritized automotive plan designed to produce employer-reviewable evidence in stages
- [docs/03_Immersive_Audio_Evaluation_Part_2_SigmaStudio_DSP_Project.md](docs/03_Immersive_Audio_Evaluation_Part_2_SigmaStudio_DSP_Project.md) — measurement-guided SigmaStudio follow-up to the proposed immersive study
- [docs/04_Conditional_Car_DSP_Installation_and_Portfolio_Validation_Plan.md](docs/04_Conditional_Car_DSP_Installation_and_Portfolio_Validation_Plan.md) — conditional scenario for an installed car DSP, proceeding only with sufficient capital, an acceptable itemized quote, and full tuning/configuration access
- [docs/05_Real-Time_DSP_Prototype_in_Pure_Data.md](docs/05_Real-Time_DSP_Prototype_in_Pure_Data.md) — documented Pure Data implementation artifact, technical audit, and staged revision plan
- [docs/engineering-evolution/](docs/engineering-evolution/) — working space for drafting vision documents that guide development of future documentation

### Current implementation artifacts

- [assets/pure-data/Sample_Circuit.pd](assets/pure-data/Sample_Circuit.pd) — original Pure Data patch preserved as the starting state for the real-time DSP prototype and audit

---

## Related Repositories

This repository complements my [Audio File Report](https://github.com/kevinworleymusic-afk/audio-file-report), where objective analysis tools are developed to support many of the engineering investigations documented here.

- [**Technical Audio Engineering Portfolio**](https://github.com/kevinworleymusic-afk/engineering-development-portfolio) — broader evidence across measurement, immersive audio, DSP, and software
- [**Dolby Atmos Recording Independent Study**](https://github.com/kevinworleymusic-afk/engineering-development-portfolio/tree/main/Projects/Technical-Audio-and-Research/Ocean-Way-Jazz-Combo-Dolby-Atmos-Independent-Study) — capture-focused foundation for this reproduction study
- [**Technical Ear Training**](https://github.com/kevinworleymusic-afk/technical-ear-training) — established and continuing critical-listening development for system evaluation, including a quantified [SoundGym SPI of 3,410,130 and Diamond Ears recognition](https://www.soundgym.co/member/profile?m=byy1s26wj7u), followed by continued Jason Corey-based technical ear training

---

## Planned Automotive Implementation Program

The [Automotive Audio Implementation Roadmap](docs/02_Automotive_Audio_Implementation_Roadmap.md) organizes the planned work so that early projects create complete, employer-reviewable evidence while access-dependent and hardware-dependent extensions remain clearly labeled.

Initial planned work includes:

- A software-in-the-loop Python CAN/DBC simulation for automotive audio control and diagnostics
- A platform-independent conceptual 25-speaker automotive immersive architecture
- A representative GNU Octave/Python DSP simulation
- A controlled vehicle acoustic-measurement campaign and connected analysis portfolio
- A proposed Belmont open-room versus simulated-cabin immersive evaluation
- A [post-study SigmaStudio DSP project](docs/03_Immersive_Audio_Evaluation_Part_2_SigmaStudio_DSP_Project.md)
- A [conditional installed car DSP scenario](docs/04_Conditional_Car_DSP_Installation_and_Portfolio_Validation_Plan.md), pursued only if sufficient capital, an acceptable quote, full software/project-file access, protected safety settings, warranty clarity, and meaningful portfolio control are confirmed
- Optional SigmaDSP hardware, Audio Weaver, embedded-C, and physical-CAN extensions when access and project requirements justify them

These items are plans, not completed-work claims. Each will be assigned a visible status as it progresses.

---

## Development Sequence

The detailed [automotive implementation roadmap](docs/02_Automotive_Audio_Implementation_Roadmap.md) follows this sequence:

1. Independently achievable CAN, architecture, DSP-simulation, and critical-listening work
2. Vehicle measurement and analysis
3. Belmont immersive evaluation if institutional access is approved
4. Measurement-guided SigmaStudio implementation
5. Conditional installed car DSP work if its capital, quote, access, safety, and documentation gates are satisfied
6. Optional additional hardware, Audio Weaver, embedded-C, and expanded research

The [Pure Data real-time DSP prototype](docs/05_Real-Time_DSP_Prototype_in_Pure_Data.md) is retained as a preliminary implementation and technical-audit exercise that supports the later simulation and SigmaStudio stages without being represented as a completed automotive system.

Applications and professional outreach do not need to wait for every phase. Each completed stage is intended to stand as independently reviewable portfolio evidence.

---

## License

This repository is for portfolio and educational purposes.

All original written content, diagrams, and documentation authored in this repository are released under the [Creative Commons Attribution 4.0 International License (CC BY 4.0)](https://creativecommons.org/licenses/by/4.0/).

Third-party references, citations, and source materials retain their original licenses and are included here solely for educational commentary.
