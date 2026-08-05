# 05 — Automotive DSP Learning Resources and Access Constraints

## Status

**Dated professional-guidance and resource-triage note — August 3, 2026.**

This document records learning guidance received from Jay Krusac after Kevin asked about realistic automotive-DSP development without immediate access to commercial production tools. It is not a completed implementation project.

## Audio Weaver

Jay advised that Audio Weaver is not affordable as a typical consumer purchase and generally requires evaluation/demo hardware and MATLAB licensing to get a working development setup. He suggested that studying public videos and learning to discuss its concepts can still help in interviews.

- [Audio Weaver overview shared by Jay](https://www.youtube.com/watch?v=fHBc4pHY9PI)
- **Current use:** vocabulary, signal-flow concepts, and interview preparation
- **Not claimed:** licensed access, evaluation-board access, MATLAB integration, embedded deployment, or production experience

## Lower-Cost Hands-On Routes

### miniDSP

Jay identified [miniDSP](https://www.minidsp.com/) as a route to light DSP equalization and tuning practice.

Potential learning value:

- Parametric EQ
- Crossover and routing concepts
- Delay and level adjustment where supported
- Bypass and before/after comparison
- Measurement-guided tuning workflow

### TinySine with SigmaStudio

Jay identified [TinySine DSP amplifier hardware](https://www.tinysineaudio.com/collections/audio-amplifier-with-dsp) as a way to experiment with DSP through SigmaStudio.

Potential learning value:

- Graphical signal-flow design
- Real hardware deployment
- Gain, filtering, routing, and protection concepts
- Transfer from the existing Pure Data prototype toward embedded-DSP workflows

### DSPi

Jay shared the [DSPi project discussion](https://www.audiosciencereview.com/forum/index.php?threads/introducing-dspi-a-powerful-user-friendly-and-open-source-dsp-for-less-than-a-cup-of-coffee.69343/) as an affordable-looking open-source resource. He stated that he had not explored it.

DSPi therefore remains an option for independent technical evaluation, not a platform validated or endorsed through Jay’s direct experience.

## Near-Term Learning Sequence

1. Study the Audio Weaver overview and map its high-level concepts to the implemented Pure Data signal graph.
2. Compare miniDSP, TinySine/SigmaStudio, and DSPi against a defined exercise: source routing, gain, delay, parametric EQ, crossover, limiting/protection, bypass, and validation.
3. Prefer a platform only after checking hardware, software, licensing, I/O, export, measurement, and repeatability requirements.
4. Document any future purchase, implementation, or validation separately with exact hardware, software, method, and results.

## Evidence Boundary

This note records guidance, access constraints, and resource selection. It does not claim ownership, hands-on use, implementation, measurement, validation, embedded deployment, vehicle integration, production experience, or endorsement of any listed platform.
