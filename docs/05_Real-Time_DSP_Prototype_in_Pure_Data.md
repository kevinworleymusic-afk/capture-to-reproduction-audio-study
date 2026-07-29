# Real-Time DSP Prototype in Pure Data

## Project status

**Status:** Working educational prototype under technical review

**Implementation:** [Pure Data patch](../assets/pure-data/Sample_Circuit.pd)

This project is an early real-time DSP implementation within the broader Capture-to-Reproduction Audio Study. It is preserved as a development artifact rather than presented as a finished automotive processor, validated cabin model, or production-ready signal chain.

## Design context

The broader study follows audio from acoustic capture through signal processing and final loudspeaker reproduction. This Pure Data patch occupies the processing stage of that chain. It provides a visual environment for exploring how source routing, delay, filtering, gain control, signal monitoring, test signals, and output protection interact in real time.

The patch also establishes a practical bridge between previous recording-focused work and later reproduction-focused projects. Concepts first explored here can be refined through offline Python or GNU Octave simulations, measurement-guided analysis, and later SigmaStudio or embedded-DSP implementation.

## Intended engineering purpose

The prototype was designed to support several learning objectives:

1. Build and inspect a real-time stereo audio signal path.
2. Explore independent left- and right-channel delay and filtering.
3. Add adjustable channel and low-frequency gain controls.
4. Generate noise and sinusoidal test signals for basic diagnostics.
5. Observe level-dependent control behavior using envelope followers.
6. Protect the output path from values outside the nominal digital range.
7. Practice documenting the difference between intended architecture and verified implementation.

## Current functional blocks

The patch contains the following Pure Data objects and subsystems:

- `readsf~ 2` for stereo file playback
- `openpanel` and transport messages for source selection and playback
- `delwrite~` and `delread~` objects for left- and right-channel delay paths
- `hip~ 120` high-pass filters
- `vcf~ 2` voltage-controlled filters
- `*~` gain stages controlled by vertical sliders
- `lop~ 80` for a low-frequency path
- `noise~` for broadband test excitation
- `osc~ 1000` for a 1 kHz test tone
- `env~`, arithmetic objects, and `dbtorms` for level-derived control values
- `clip~ -1 1` before the two output channels
- separate `dac~ 1` and `dac~ 2` output objects

## Signal-flow interpretation

At a conceptual level, the patch is attempting to organize the following chain:

```text
Stereo media or generated test signal
                |
                v
      routing and summing stage
                |
                v
      left/right delay paths
                |
                v
       filtering and gain control
                |
                v
       level-dependent control
                |
                v
          output clipping
                |
                v
          stereo DAC output
```

A low-frequency branch is also present, using an 80 Hz low-pass filter and an independent gain control before being routed into the right-side output path.

## Technical audit of the current patch

The patch contains useful DSP building blocks, but its present wiring should not yet be described as a verified stereo, mid/side, or automotive-cabin processor.

### 1. The apparent sum-and-difference section is not currently a correct mid/side matrix

The left output of `readsf~ 2` is connected to both inputs of `+~`, producing `L + L`, which is then multiplied by 0.5 and therefore returns approximately `L`.

The right output is connected to both inputs of `-~`, producing `R - R`, which evaluates to zero before the 0.5 gain stage.

A conventional mid/side encoder would instead require:

```text
Mid  = 0.5(L + R)
Side = 0.5(L - R)
```

This routing issue should be corrected before the section is labeled as mid/side processing.

### 2. Filter-control inputs require explicit validation

The two number boxes feed the cutoff-frequency inlets of the `hip~` and `vcf~` objects. Their usable ranges, initialization behavior, and response should be documented and tested. Without load-time defaults, the patch may open in a state that does not reproduce the intended response.

### 3. The envelope-following path is acting as a gain-control experiment

Each delayed and high-pass-filtered channel feeds an `env~` object. The resulting control value passes through subtraction, inversion/scaling, and `dbtorms` before controlling a downstream multiplier.

This resembles an experimental level-dependent gain stage, but its target behavior has not yet been formally defined. Before calling it compression, automatic gain control, or dynamics processing, the following should be measured:

- control value versus input level
- attack behavior
- release behavior
- steady-state gain reduction
- behavior when the source loops or playback restarts

This is especially relevant to critical-listening work because a meter or control path that fails to reset correctly can make a valid listening observation appear inconsistent.

### 4. Output clipping is protection, not full limiting

`clip~ -1 1` prevents numerical output beyond the nominal full-scale range, but hard clipping is not equivalent to a transparent limiter. It should be described as output protection for the prototype rather than as a completed dynamics-safety system.

### 5. The low-frequency branch needs clearer routing documentation

The `lop~ 80` path is controlled by a separate slider and is summed into the second output path. The intended source, channel assignment, and purpose of this branch should be clarified before it is described as a subwoofer, bass-management, or LFE implementation.

## Recommended next revision

A second revision should focus on correctness and repeatability before adding more features.

### Routing corrections

- Connect left and right playback channels to the proper inputs of the sum-and-difference stage.
- Decide whether the patch should remain left/right throughout or intentionally encode and decode mid/side.
- Label every signal branch with its channel and purpose.
- Route the low-frequency branch explicitly to both mains or to a dedicated output, depending on the intended architecture.

### Initialization and gain staging

- Add `loadbang` objects with conservative default values.
- Use channel-gain ranges that prevent accidental 5x amplification at startup.
- Add pre-processing and post-processing level meters.
- Document expected peak level and headroom at each stage.

### Dynamics validation

- Replace the experimental envelope-derived multiplier with a clearly defined compressor or automatic-gain-control design.
- Expose threshold, ratio, attack, release, and makeup gain when compression is the intended function.
- Verify that gain reduction repeats identically on every pass of a looped transient.
- Export processed files and compare them against the unprocessed source at matched loudness.

### Measurement and evidence

For each processing block, record:

- parameter settings
- input signal
- expected result
- observed result
- waveform or level plot
- listening notes
- limitations

Recommended initial test signals:

- 1 kHz sine wave for level and routing checks
- broadband noise for filter-response checks
- repeated snare transients for dynamics and timing behavior
- stereo music for image and channel-balance checks

## Relationship to later portfolio work

This patch is best presented as a **Phase 0 real-time DSP bench**. It provides an early visual implementation before more formal projects in the repository:

1. Pure Data real-time signal-flow prototype
2. Python or GNU Octave offline DSP simulation
3. objective measurement and plotted verification
4. measurement-guided SigmaStudio implementation
5. vehicle or loudspeaker-system application

The value of this artifact is not that every block is already correct. Its value is that it provides a concrete system to audit, revise, measure, and document. That process demonstrates engineering development more credibly than presenting an unfinished prototype as a completed solution.

## Portfolio description

> Developed and technically audited a Pure Data prototype for real-time audio reproduction experiments. The patch combines stereo source playback, delay, filtering, adjustable gain, generated test signals, level-derived control, low-frequency routing, and output protection. Documentation distinguishes intended architecture from verified behavior and defines a revision plan for repeatable measurement, dynamics validation, and later automotive-audio DSP implementation.

## Current limitations

- The current sum-and-difference wiring is not a valid mid/side encoder.
- Parameter defaults and safe startup behavior are not yet defined.
- The envelope-derived gain-control behavior has not been fully characterized.
- The low-frequency branch is not yet documented as a validated bass-management design.
- No vehicle impulse responses, loudspeaker measurements, or cabin measurements are incorporated.
- The patch has not been validated as an automotive production architecture.

These limitations are retained explicitly so future revisions can show measurable progress rather than quietly replacing the original development state.
