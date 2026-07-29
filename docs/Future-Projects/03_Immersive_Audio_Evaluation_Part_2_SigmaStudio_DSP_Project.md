# 03 — Measurement-Guided DSP Development in SigmaStudio

## Status

**Planned post-study engineering extension.** This project begins only after usable measurement and listening results are available from the proposed open-room versus simulated-cabin evaluation.

## Purpose

Translate supported findings from the initial immersive evaluation into a documented DSP correction strategy using SigmaStudio.

The intended workflow is:

> **measurement → diagnosis → DSP requirement → implementation → predicted validation → future physical validation**

## Proposed signal flow

> **Input routing → gain/mute → channel delay → parametric EQ → crossover or bass management → output limiting → output routing**

## Planned work packages

1. Review usable measurement and listening results.
2. Separate global problems from position-dependent effects.
3. Create a prioritized DSP requirements table.
4. Establish channel naming, routing, gain, mute, bypass, and comparison controls.
5. Derive candidate delay and level corrections from repeatable evidence.
6. Apply broad, evidence-based parametric EQ rather than attempting to correct narrow cancellation nulls.
7. Study crossover and bass-management behavior.
8. Develop only presets supported by the final findings.
9. Document gain structure, headroom, and limiting.
10. Simulate equivalent processing in Python, MATLAB, or GNU Octave for predicted before/after validation.
11. Transfer the design to physical SigmaDSP hardware only if compatible access becomes available.

## Minimum viable implementation

The initial proof of concept may use a manageable two-input/four-output architecture. It should demonstrate:

- clear channel routing
- at least one evidence-based delay correction
- evidence-based parametric EQ
- representative crossover or bass-management processing
- gain structure and limiting
- bypass controls
- at least two justified presets
- predicted before/after validation

The reduced design will not be presented as a complete 7.1.4 processor or a production automotive system.

## Intended deliverables

- SigmaStudio project file
- signal-flow diagram or schematic export
- block-by-block explanation
- DSP requirements table
- filter, gain, delay, crossover, and limiter map
- preset comparison table
- Python, MATLAB, or GNU Octave validation files
- before/after plots
- measurement-to-processing traceability table
- hardware-validation plan
- limitations and future-work section

## Scope boundaries

This project does not initially claim:

- a complete production automotive processor
- full implementation of every 7.1.4 channel
- validation in an actual vehicle
- adaptive or road-noise-dependent processing
- improvement unless supported by completed measurements and listening results

## Relationship to Project 01

[Project 01](../01_Real-Time_Audio_DSP_Prototype_Pure_Data/) provides an earlier real-time visual DSP prototype. This future project would increase rigor by deriving parameter choices from measurements, documenting processing requirements, and predicting the effect of the implemented settings.