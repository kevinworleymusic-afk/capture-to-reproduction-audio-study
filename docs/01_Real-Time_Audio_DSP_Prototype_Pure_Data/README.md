# 01 — Real-Time Audio DSP Prototype (Pure Data)

## Project status

**Status:** Implemented educational prototype under continued technical review

## Implementation files

- [Original Pure Data patch](Sample_Circuit.pd)
- [Clean layout, Version 2](Sample_Circuit_Clean_v2.pd)

## Project purpose

This project is the first implemented engineering artifact in the Capture-to-Reproduction Audio Study. It functions as a compact real-time DSP workbench for examining signal routing, time-domain processing, filtering, level control, diagnostics, low-frequency processing, and protected stereo output in Pure Data.

The patch occupies the processing stage between source capture and loudspeaker reproduction. It also provides a practical bridge from previous recording-focused work toward later simulation, measurement, SigmaStudio, loudspeaker, and automotive-audio projects.

## Concepts demonstrated

- Stereo audio-file selection and playback
- Sum-and-difference signal-processing experiments
- Independent left- and right-channel delay paths
- Voltage-controlled filtering
- High-pass filtering
- Independent channel gain
- An 80 Hz low-frequency branch with separate level control
- Broadband-noise and 1 kHz sine-wave test generation
- Envelope-derived level-control experiments
- Output clipping for prototype protection
- Separate left and right DAC routing
- Real-time DSP implementation in a visual programming environment
- Technical auditing, documentation, and revision control

## Functional blocks

The patch includes:

- `openpanel` and transport messages for file selection and playback
- `readsf~ 2` for stereo source playback
- `+~`, `-~`, and `*~ 0.5` objects for sum-and-difference experiments
- `delwrite~` and `delread~` objects for channel delay
- `hip~ 120` high-pass filters
- `vcf~ 2` voltage-controlled filters
- Slider-controlled `*~` gain stages
- `lop~ 80` for low-frequency extraction
- `noise~` for broadband test excitation
- `osc~ 1000` for a 1 kHz test tone
- `env~`, arithmetic objects, and `dbtorms` for level-derived control experiments
- `clip~ -1 1` before output
- Separate `dac~ 1` and `dac~ 2` output objects

## Version history

### Version 1

The original patch is preserved as the initial implementation state. It contains the complete stored connection graph and serves as the baseline for technical review.

### Version 2

Version 2 reorganizes the same connection graph into clearer visual sections:

- source playback
- sum-and-difference processing
- delay stage
- filter stage
- level diagnostics
- test-signal generators
- low-frequency path
- output levels
- stereo output

The cleaner layout improves readability and maintainability while preserving the implementation as a prototype rather than presenting it as a production-ready automotive processor.

## Signal-flow interpretation

```text
Stereo playback or generated test signal
                |
                v
      routing / sum-difference stage
                |
                v
       left and right delay paths
                |
                v
       filtering and gain control
                |
                v
     level-derived control experiment
                |
                v
          output clipping
                |
                v
        stereo DAC output
```

A separate low-frequency branch uses an 80 Hz low-pass filter and an independent gain control before being routed into the output structure.

## Technical review notes

The patch should be described as a working educational prototype, not as a finished stereo, Mid/Side, automotive-cabin, or production DSP architecture.

The stored sum-and-difference section requires explicit signal-path validation before being described as a conventional Mid/Side matrix. Filter-control ranges, startup values, envelope-derived gain behavior, and low-frequency routing should also be measured and documented before stronger functional claims are made.

`clip~ -1 1` is retained as numerical output protection. It is not presented as a transparent limiter.

## Recommended validation sequence

1. Verify left and right source routing with a known stereo file.
2. Test each output independently with a 1 kHz sine wave.
3. Confirm delay timing using impulses or repeated transients.
4. Measure high-pass and voltage-controlled filter behavior with broadband noise.
5. Record parameter settings and before/after levels.
6. Characterize the envelope-derived control response.
7. Verify the low-frequency branch source and output assignment.
8. Compare Version 1 and Version 2 to confirm identical stored connection behavior.

## Portfolio description

> Developed and documented a Pure Data prototype for real-time audio reproduction experiments. The patch combines stereo source playback, channel delay, filtering, adjustable gain, generated test signals, level-derived control, low-frequency routing, and protected stereo output. A second version reorganizes the same signal graph into a cleaner engineering layout, while the documentation distinguishes implemented behavior from items still requiring measurement and validation.

## Relationship to future projects

This project serves as the implemented starting point for the later work grouped in [Future Projects](../Future-Projects/), including automotive architecture, offline DSP simulation, measurement, SigmaStudio development, and possible vehicle implementation.