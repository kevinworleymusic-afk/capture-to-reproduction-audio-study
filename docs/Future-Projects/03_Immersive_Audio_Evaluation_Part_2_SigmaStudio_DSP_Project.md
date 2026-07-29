# 03 — Measurement-Guided DSP Development in SigmaStudio

## Immersive Audio Evaluation: Part 2 Project Sheet

### Project Status

Planned post-study engineering extension. This project begins after the initial open-room versus simulated-cabin research process has been completed and usable measurement and listening results are available.

## Project Purpose

Translate findings from the initial Immersive Audio Evaluation Research Study into a documented DSP correction strategy using SigmaStudio.

Part 1 asks what measurable and perceptual changes are introduced when a conventional 7.1.4 Dolby Atmos listening environment is changed from its normal open-room condition to a reduced-volume simulated-cabin condition at fixed listening positions.

Part 2 asks:

> Based on the measured and perceived differences identified in Part 1, how could targeted DSP processing improve channel alignment, tonal consistency, spatial stability, and seat-to-seat consistency in the simulated-cabin environment?

Part 2 is an engineering application of the Part 1 findings. It does not change the original experiment, add new independent variables to it, or retroactively treat DSP processing as part of the initial comparison.

## Connection to Part 1

### Part 1 conditions

- Open-room baseline
- Reduced-volume simulated-cabin condition

### Part 1 listening positions

- Front Left
- Front Right
- Rear Left
- Rear Right
- Rear Center or equivalent representative position

### Potential Part 1 evidence used in Part 2

- Frequency-response measurements
- Impulse responses and arrival-time data
- Early-reflection behavior
- Decay characteristics
- Left/right symmetry
- Channel-to-channel consistency
- Seat-to-seat consistency
- Subjective ratings of localization, front-stage stability, envelopment, height perception, tonal balance, bass uniformity, clarity, and overall preference

Only findings that are supported by the completed study will become DSP requirements.

## Core Engineering Objective

Develop a measurement-guided SigmaStudio proof of concept that demonstrates the process:

**measurement → diagnosis → DSP requirement → implementation → predicted validation → future physical validation**

The project will prioritize broad, repeatable problems rather than attempting to correct every narrow response irregularity at one microphone position.

## Proposed SigmaStudio Signal Flow

**Input routing → gain/mute → channel delay → parametric EQ → crossover or bass management → output limiting → output routing**

The first implementation may use a reduced channel count that represents a portion of the complete 7.1.4 system. The design will explain how the same method could scale to a larger immersive or automotive architecture.

## Work Packages

### 1. Post-Study Findings Review

- Organize the usable Part 1 measurement and listening results.
- Identify differences that occur consistently between the open-room and simulated-cabin conditions.
- Identify position-dependent differences across the representative seats.
- Distinguish global system problems from localized seat-specific effects.
- Create a prioritized list of candidate DSP corrections.

### 2. DSP Requirements Definition

For each proposed correction, document:

- The measurement or listening result that motivates it
- The affected channel or listening position
- The proposed processing block
- The intended improvement
- Possible tradeoffs or unintended effects
- The measurement needed to validate the change

### 3. Channel Architecture and Routing

- Create and label the input and output channels.
- Establish consistent channel naming.
- Add input and output gain controls.
- Add mute, bypass, and comparison controls.
- Document how the reduced proof-of-concept architecture maps to the full 7.1.4 system.

### 4. Arrival-Time and Level Alignment

- Calculate candidate channel delays from the Part 1 impulse-response data.
- Apply delay only where supported by repeatable arrival-time differences.
- Correct relevant channel-level differences.
- Compare optimization for a selected seat with a broader all-seat compromise.
- Document delay values, gain values, calculation methods, and reference positions.

### 5. Measurement-Guided Parametric EQ

- Identify broad tonal deviations that are repeatable across measurements.
- Select center frequency, gain, and Q for each proposed filter.
- Avoid attempting to equalize narrow nulls that are unlikely to respond reliably to electronic correction.
- Maintain sufficient headroom when applying boosts.
- Create a filter table connecting every adjustment to its supporting evidence.

### 6. Crossover and Bass-Management Study

- Establish representative high-pass and low-pass filters.
- Compare appropriate crossover frequencies, slopes, and alignments.
- Examine expected magnitude and phase interaction.
- Consider bass uniformity across listening positions.
- Include protective high-pass filtering where appropriate.
- State clearly when the available Part 1 data is insufficient to justify a final crossover decision.

### 7. Preset Development

Develop only the presets supported by the research findings. Candidate configurations include:

- Open-Room Baseline
- Simulated-Cabin Uncorrected Reference
- Simulated-Cabin Corrected
- Front-Seat Optimization
- Rear-Seat Optimization
- All-Seat Compromise

Not every candidate preset must be built. The final set will depend on the quality and relevance of the Part 1 results.

### 8. Gain Structure and Output Protection

- Establish input and output trims.
- Account for headroom consumed by positive EQ.
- Add output limiting.
- Check for clipping at each major stage.
- Document operating levels and limiting thresholds.

### 9. Bypass and Controlled Comparison

Provide controls that allow meaningful comparisons among:

- Unprocessed and corrected signal paths
- Open-room reference and simulated-cabin correction settings
- Seat-specific and all-seat-compromise settings
- Individual processing blocks enabled and bypassed

### 10. Predicted Validation

Because SigmaStudio does not provide the same complete native-PC execution environment as Audio Weaver, use MATLAB, Python, or another appropriate analysis environment to apply equivalent processing and generate predicted results before hardware implementation.

Potential comparisons include:

- Before/after frequency response
- Before/after impulse or arrival-time alignment
- Channel summation around crossover regions
- Left/right symmetry
- Variation across listening positions
- Peak level and headroom

The simulation and SigmaStudio implementation must use the same documented parameter values.

### 11. Optional Physical DSP Validation

If suitable SigmaDSP hardware and a compatible Windows computer become available:

- Transfer the processing structure to the physical DSP.
- Verify routing and channel polarity.
- Confirm that filter, delay, gain, and limiter parameters match the design record.
- Repeat relevant measurements.
- Compare predicted and measured results.
- Conduct a limited controlled listening comparison.
- Record discrepancies and revise the model where appropriate.

Hardware validation is a later extension, not a requirement for beginning the project documentation and design work.

## Minimum Viable Implementation

The initial proof of concept will use a manageable two-input/four-output architecture or another reduced configuration supported by the selected hardware.

It should demonstrate:

- Clear channel routing
- At least one evidence-based delay correction
- Evidence-based parametric EQ
- Representative crossover or bass-management processing
- Gain structure and limiting
- Bypass controls
- At least two justified presets
- Predicted before/after validation

The reduced implementation will not be presented as a complete 7.1.4 processor or a production automotive system.

## Project Deliverables

- SigmaStudio project file
- Signal-flow diagram or high-resolution schematic export
- Block-by-block system explanation
- DSP requirements table
- Filter, gain, delay, crossover, and limiter parameter map
- Preset comparison table
- MATLAB/Python validation files, where applicable
- Before/after plots
- Measurement-to-processing traceability table
- Hardware-validation plan
- Limitations and future-work section
- Short narrated screen demonstration
- Concise GitHub project summary linking to the full documentation

## Measurement-to-Processing Traceability Template

| Part 1 finding | Affected condition/position | Proposed DSP response | SigmaStudio block | Validation measure | Status |
|---|---|---|---|---|---|
| To be determined from results | — | — | — | — | Pending Part 1 |

## Success Criteria

The project will be considered successful if it:

- Derives processing decisions from documented Part 1 evidence.
- Keeps measured findings, engineering interpretations, and subjective observations clearly distinguished.
- Demonstrates a coherent and technically justified SigmaStudio architecture.
- Uses simulation to predict the effect of the implemented parameters.
- Evaluates compromises between seat-specific optimization and broader spatial consistency.
- Documents limitations without overstating the results.
- Produces a reproducible portfolio record that another engineer can review.

Physical hardware validation would strengthen the project but is not required to satisfy the initial proof-of-concept objectives.

## Scope Boundaries

This project does not initially claim:

- A complete production-ready automotive audio system
- Full implementation of all 12 channels in the 7.1.4 layout
- Validation on an actual vehicle
- Real-time adaptive processing
- Road-noise-dependent processing
- Generalizable correction for every cabin geometry
- Improvement unless supported by the final measurements and listening results

Road-noise masking, adaptive vehicle-state processing, CAN integration, embedded C development, and a conceptual 25-speaker Audio Weaver architecture remain separate potential companion projects.

## Automotive Relevance

Although the study uses a simulated-cabin condition rather than an actual vehicle, Part 2 demonstrates an automotive-relevant engineering workflow:

- Interpreting multichannel acoustic measurements
- Connecting objective and perceptual evidence
- Diagnosing position-dependent reproduction problems
- Developing channel-specific tuning strategies
- Comparing individual-seat and all-seat compromises
- Implementing graphical DSP processing
- Managing gain, headroom, crossovers, delay, and protection
- Planning repeatable validation

This project is intended to demonstrate foundational system-tuning judgment and transferable DSP-development skills while clearly identifying the additional work required for a production automotive implementation.
