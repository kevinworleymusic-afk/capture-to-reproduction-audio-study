# Project 1: Real-Time DSP Prototype in Pure Data

## Project status

**Status:** Implemented educational prototype under continued technical review  
**Original patch:** [Sample_Circuit.pd](../assets/pure-data/Sample_Circuit.pd)  
**Version 2:** [Sample_Circuit_Clean_v2.pd](../assets/pure-data/Sample_Circuit_Clean_v2.pd)

This is the first active implementation project in the Capture-to-Reproduction Audio Study. It is an early real-time DSP workbench rather than a finished automotive processor or production signal chain.

## What the project covers

The patch provides a visual, real-time environment for exploring how multiple audio-processing functions interact within one signal path. It currently includes:

- stereo audio-file loading and playback through `openpanel` and `readsf~ 2`
- a sum-and-difference processing experiment using `+~`, `-~`, and `*~ 0.5`
- independent left- and right-channel delay lines using `delwrite~` and `delread~`
- voltage-controlled and high-pass filtering through `vcf~` and `hip~`
- independent left and right output-level controls
- an 80 Hz low-pass branch with separate bass-level control
- a 1 kHz sine-wave generator for routing and level checks
- broadband noise generation for filter and diagnostic testing
- envelope-following control paths using `env~`, arithmetic scaling, and `dbtorms`
- hard output clipping through `clip~ -1 1` before the two DAC outputs
- separate channel-one and channel-two output routing

Together, these blocks make the patch useful as a small DSP laboratory for studying routing, timing, filtering, gain structure, generated test signals, low-frequency extraction, level-dependent control, and output protection.

## Version history

### Version 1: Original implementation

The original patch preserves the initial working arrangement and development state. It remains in the repository so later revisions can be compared against the starting point rather than silently replacing it.

### Version 2: Clean layout revision

Version 2 reorganizes the same connectable objects and preserves the original connection list. The revision improves readability by arranging the canvas into labeled functional regions:

1. Source Playback
2. Sum / Difference Stage
3. Delay Stage
4. Filter Stage
5. Level Diagnostics
6. Output Levels
7. Test Signal Generators
8. Low-Frequency Path
9. Left and Right Outputs

This revision is primarily a documentation and maintainability improvement. Object coordinates, section labels, canvas size, and control labels were changed, while the stored DSP connection graph was retained.

## Signal-flow overview

```text
Stereo file playback or generated test signals
                    |
                    v
          sum / difference experiment
                    |
                    v
       independent delay-line processing
                    |
                    v
        VCF and high-pass filter stages
                    |
                    v
       envelope-derived level control
                    |
                    v
        channel and bass gain controls
                    |
                    v
             output clipping
                    |
                    v
          separate stereo DAC outputs
```

## Engineering value

The project demonstrates more than isolated Pure Data objects. It shows the construction and revision of a connected real-time system containing source management, parallel branches, timing operations, filters, control-rate calculations, gain stages, diagnostic signals, and protected outputs.

It also creates a concrete artifact that can be:

- inspected block by block
- tested with known signals
- revised without losing the original version
- documented through signal-flow diagrams
- compared against later Python, GNU Octave, SigmaStudio, or embedded-DSP implementations

## Current technical notes

The patch should still be treated as a prototype whose intended behavior needs measurement-based verification.

- The sum-and-difference section is preserved exactly as wired in the submitted patch. In the current file, the left playback channel feeds both inputs of `+~`, while the right playback channel feeds both inputs of `-~`. It should therefore be described as a sum-and-difference experiment rather than a verified mid/side encoder.
- The number-box ranges and startup values for the filter controls should be documented and initialized.
- The envelope-derived multipliers behave as an experimental level-dependent control system. Threshold, attack, release, steady-state gain, and repeatability have not yet been formally characterized.
- `clip~ -1 1` provides hard numerical clipping, not transparent limiting.
- The 80 Hz low-frequency path is implemented, but its intended role and output assignment should be verified before it is labeled as complete bass management or LFE processing.
- The patch has not been validated using vehicle impulse responses, loudspeaker measurements, or cabin measurements.

## Recommended validation sequence

1. Confirm left and right routing with isolated channel test files.
2. Measure the result of the sum-and-difference section.
3. Verify delay times with impulses or repeated transients.
4. Sweep the filter controls and record their usable ranges.
5. Test the envelope-derived gain response with sine tones, noise, and drum transients.
6. Confirm headroom at every gain stage.
7. Compare processed and bypassed output at matched loudness.
8. Document expected and observed behavior for every block.

## Relationship to later work

This project now serves as the first completed implementation artifact in the repository. The broader sequence is:

1. **Pure Data real-time DSP prototype and Version 2 layout revision**
2. Future Python or GNU Octave DSP simulation
3. Future objective measurement and plotted validation
4. Future measurement-guided SigmaStudio implementation
5. Future loudspeaker-system or vehicle application

The remaining proposed projects are intentionally separated in the [Future Projects](Future-Projects/) folder so completed implementation work and planned work are not visually blended together.

## Portfolio description

> Developed and revised a Pure Data real-time DSP prototype combining stereo file playback, delay lines, filter stages, adjustable channel gain, a low-frequency branch, generated diagnostic signals, envelope-derived control, and protected stereo outputs. A second version reorganizes the complete patch into clearly labeled functional regions while retaining the original DSP connection graph, creating a more readable and maintainable artifact for continued testing and validation.
