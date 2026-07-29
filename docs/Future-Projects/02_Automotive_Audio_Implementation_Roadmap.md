# 02 — Automotive Audio Implementation Roadmap

## Status

**Planned.** This document organizes future automotive-audio work and does not claim that the listed projects have been completed.

## Purpose

This roadmap organizes planned automotive-audio work so that early projects can produce complete, reviewable evidence while longer-term studies remain available as ambitious extensions.

The work follows this progression:

> **critical listening → system architecture → simulation → measurement → diagnosis → DSP implementation → validation**

## Planned work

### Software-in-the-loop CAN/DBC simulation

Develop a Python-based virtual vehicle and audio-system interaction model including ignition state, door state, seat occupancy, volume, mute, amplifier temperature, voltage, faults, missing-message handling, invalid-signal rejection, safe fallback, and recovery.

### Conceptual 25-speaker automotive immersive architecture

Design a platform-independent architecture defining loudspeaker locations, channel roles, source routing, delay, gain, EQ, crossover, limiting, amplifier assignment, bass management, seat control, and representative listening modes.

### GNU Octave/Python DSP simulation

Build a manageable multichannel subsystem using gain, delay, EQ, filters, and crossover processing. Generate impulse, magnitude, phase, summation, and headroom results while keeping simulated transfer functions clearly distinguished from measured data.

### Vehicle acoustic-measurement campaign

Use one controlled measurement campaign to investigate frequency response, impulse response, arrival time, early reflections, phase, crossover behavior, spectral decay, resonance, seat-to-seat variation, and measurement-guided DSP optimization.

### Proposed immersive evaluation

Compare an open-room 7.1.4 baseline with a reduced-volume simulated-cabin condition at representative listening positions, subject to facility approval, faculty sponsorship, equipment access, and any required human-participant review.

### Measurement-guided SigmaStudio follow-up

Translate usable findings into a documented DSP proof of concept involving routing, gain, delay, parametric EQ, crossover or bass management, limiting, presets, bypass comparison, and predicted validation.

### Conditional installed car-DSP platform

Consider an aftermarket vehicle DSP only when sufficient funding, a complete itemized quote, full tuning access, restorable project files, safe baseline protection, warranty clarity, and meaningful portfolio control are confirmed.

## Scope policy

- Planned work will not be presented as completed work.
- Simulated data will not be presented as measured data.
- Software-in-the-loop CAN work will not be presented as physical vehicle-network implementation.
- A conceptual architecture will not be presented as a deployed system.
- Access dependencies and limitations will remain visible.

## Intended sequence

1. Complete software-only CAN/DBC work.
2. Specify the conceptual automotive architecture.
3. Build a representative offline DSP model.
4. Complete controlled vehicle measurements.
5. Conduct the proposed immersive pilot or study if approved.
6. Develop the SigmaStudio follow-up from usable evidence.
7. Add optional hardware, Audio Weaver, embedded-C, or physical-CAN work only when access and project needs justify it.

## Related future documents

- [03 — Measurement-Guided DSP Development in SigmaStudio](03_Immersive_Audio_Evaluation_Part_2_SigmaStudio_DSP_Project.md)
- [04 — Conditional Vehicle DSP Development Platform](04_Conditional_Car_DSP_Installation_and_Portfolio_Validation_Plan.md)