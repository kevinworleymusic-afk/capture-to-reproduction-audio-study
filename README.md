# Capture-to-Reproduction Audio Study

A portfolio repository documenting progression from [recording engineering](https://github.com/kevinworleymusic-afk/engineering-development-portfolio/tree/main/Projects/Technical-Audio-and-Research/Ocean-Way-Jazz-Combo-Dolby-Atmos-Independent-Study) toward loudspeaker system design, [DSP](https://github.com/kevinworleymusic-afk/engineering-development-portfolio/tree/main/Projects/Coding-and-Audio-Software/MATLAB-Projects), and automotive audio reproduction.

## Publication status

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
└── assets/             # Images, audio samples, and supporting media files
```

### Current `docs/` Contents

- [docs/README.md](docs/README.md) — overview and organization notes for repository documentation
- [docs/00_Engineering_Study_Template.md](docs/00_Engineering_Study_Template.md) — standard template for engineering studies and technical reports
- [docs/engineering-evolution/](docs/engineering-evolution/) — working space for drafting vision documents that guide development of future documentation

---

## Related Repositories

This repository complements my [Audio File Report](https://github.com/kevinworleymusic-afk/audio-file-report), where objective analysis tools are developed to support many of the engineering investigations documented here.

- [**Technical Audio Engineering Portfolio**](https://github.com/kevinworleymusic-afk/engineering-development-portfolio) — broader evidence across measurement, immersive audio, DSP, and software
- [**Dolby Atmos Recording Independent Study**](https://github.com/kevinworleymusic-afk/engineering-development-portfolio/tree/main/Projects/Technical-Audio-and-Research/Ocean-Way-Jazz-Combo-Dolby-Atmos-Independent-Study) — capture-focused foundation for this reproduction study
- [**Technical Ear Training**](https://github.com/kevinworleymusic-afk/technical-ear-training) — structured critical-listening development for system evaluation

---
## Current Projects

No projects have been completed yet. This section will be updated as work progresses.

Planned initial work includes:

- Documenting the theoretical relationship between microphone capture geometry and stereo image reproduction on a two-channel loudspeaker system
- Surveying crossover topologies and their interaction with driver impedance curves
- Beginning an automotive cabin acoustic study using available measurement references

---

## Future Roadmap

The following areas are planned for future development. Items are listed in approximate order of priority, not completion:

1. **Signal chain documentation** — end-to-end write-up of capture-to-reproduction decisions with justification for each stage
2. **Loudspeaker system design study** — enclosure modeling, driver parameter analysis (Thiele/Small), and crossover design
3. **DSP implementation notes** — parametric EQ, linear-phase filtering, and digital crossover design
4. **Automotive acoustics module** — literature review and cabin measurement methodology
5. **Comparative listening analysis framework** — structured approach to evaluating reproduction against source intent

This roadmap reflects intent, not completed work. Updates will be made as each area is studied and documented.

---

## License

This repository is for portfolio and educational purposes.

All original written content, diagrams, and documentation authored in this repository are released under the [Creative Commons Attribution 4.0 International License (CC BY 4.0)](https://creativecommons.org/licenses/by/4.0/).

Third-party references, citations, and source materials retain their original licenses and are included here solely for educational commentary.
