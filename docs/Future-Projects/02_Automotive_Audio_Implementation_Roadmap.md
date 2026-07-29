# 02 — Automotive Audio Implementation Roadmap

## Purpose

This roadmap organizes planned automotive-audio work so that early projects produce complete, reviewable evidence while longer-term studies remain available as ambitious extensions.

The roadmap is a development plan, not a claim that the listed projects have been completed. Each repository item should retain a visible status such as **Planned**, **In Development**, **Data Collection Complete**, or **Completed**.

## Portfolio Strategy

The work is organized around a repeatable engineering progression:

> **critical listening → system architecture → simulation → measurement → diagnosis → DSP implementation → validation**

The initial projects prioritize work that can be completed independently with existing computer access. Facility-dependent and hardware-dependent work follows only when the necessary access is confirmed.

## Phase 1 — Independently Achievable Automotive Foundations

### Project 1: CAN-Controlled Automotive Audio System Simulation

**Status:** Planned  
**Hardware required:** No

Develop a software-in-the-loop model of CAN-based vehicle and audio-system interaction.

Planned components:

- Python vehicle-state transmitter
- Python audio-system controller
- CAN monitor, logger, and replay utility
- Original DBC network definition
- Virtual CAN communication using `python-can`
- DBC encoding and decoding using `cantools`
- Optional SavvyCAN traffic visualization
- Automated tests and fault injection

Representative signals and behaviors:

- Ignition and controlled startup/shutdown
- Door state
- Seat occupancy
- Volume and mute commands
- Audio-mode selection
- Amplifier temperature, voltage, and fault status
- Missing-message timeout
- Invalid-signal rejection
- Safe fallback and controlled recovery

Portfolio outputs:

- Source code
- DBC file
- Architecture diagram
- Example CAN logs
- Automated test results
- Short demonstration
- Limitations and physical-hardware extension plan

This project will be identified as a **software-in-the-loop simulation**, not a physical CAN-bus or production-vehicle implementation.

### Project 2: Conceptual 25-Speaker Automotive Immersive Architecture

**Status:** Planned  
**Audio Weaver required:** No  
**Physical 25-speaker system required:** No

Design a platform-independent architecture for a conceptual 25-speaker automotive immersive-audio system.

Planned documentation:

- Loudspeaker location and functional-role map
- Distinction between physical transducers and independently processed channels
- Source-routing and processing matrix
- Per-channel gain, delay, polarity, EQ, crossover, limiting, and amplifier assignments
- Bass-management strategy
- Seat and zone control
- Driver-focused, front-seat, rear-seat, all-seat, stereo-preservation, and immersive-reference modes where technically justified
- Gain structure, headroom, and protection strategy
- System block diagram
- Reduced-subsystem validation plan

The system will be presented as a conceptual architecture supported by specifications and simulation, not as a deployed or vehicle-validated product.

### Project 3: GNU Octave/Python DSP Simulation

**Status:** Planned  
**Hardware required:** No

Build a representative multichannel simulation related to the 25-speaker architecture.

Initial scope:

- Model a manageable four-channel subsystem before scaling the software structure.
- Apply channel-specific gain, delay, EQ, filtering, and crossover processing.
- Generate impulse, magnitude, phase, summation, and headroom results.
- Export parameter tables and representative processed audio when practical.
- Keep simulated transfer functions visibly distinguished from measured data.

Potential later extension:

\[
\mathbf{y}(f)=\mathbf{H}(f)\mathbf{G}(f)\mathbf{x}(f)
\]

where \(\mathbf{x}\) represents source signals, \(\mathbf{G}\) represents routing and DSP, \(\mathbf{H}\) represents loudspeaker-to-seat acoustic paths, and \(\mathbf{y}\) represents predicted listener-position responses.

### Continuing Foundation: Critical Listening

The [Technical Ear Training repository](https://github.com/kevinworleymusic-afk/technical-ear-training) documents:

- A public SoundGym SPI of **3,410,130**
- SoundGym Diamond Ears recognition
- Prior academic study of Jason Corey's technical-ear-training methodology
- Continued chapter-based execution
- Confidence, error, and progress tracking
- Planned application to loudspeaker, spatial, DSP, and automotive-system evaluation

SoundGym, Corey exercises, measurement interpretation, and future listening samples remain distinct but complementary forms of evidence.

## Phase 2 — Vehicle Measurement and Analysis

### Project 4: Vehicle Acoustic Measurement Campaign

**Status:** Planned  
**Primary dependency:** Access to a vehicle, calibrated measurement microphone, interface, and measurement software

Use one controlled vehicle measurement campaign to generate a connected group of analyses:

1. Baseline cabin frequency-response characterization
2. Impulse-response and time-alignment analysis
3. Energy-time-curve and reflection analysis
4. Phase and crossover behavior
5. Spectral-decay and resonance analysis
6. Measurement-guided DSP optimization
7. Psychoacoustic and critical-listening interpretation
8. Integrated automotive audio engineering case study

These are related analyses derived from a shared measurement campaign, not eight unrelated measurement projects.

Required documentation:

- Vehicle and system configuration
- Measurement positions
- Microphone orientation and calibration
- Playback level
- Test signals
- Software settings
- Environmental conditions
- Raw-data organization
- Repeatability checks
- Measurement uncertainty and limitations

## Conditional Scenario — Installed Car DSP Development Platform

**Status:** Conditional and funding-dependent  
**Detailed plan:** [Conditional Car DSP Installation and Portfolio Validation Plan](04_Conditional_Car_DSP_Installation_and_Portfolio_Validation_Plan.md)

If sufficient capital becomes available, this scenario would proceed only after an itemized vehicle-specific quote confirms the complete equipment and installation cost and the system satisfies the required portfolio-development conditions.

The installation must provide full tuning-software access, exportable and restorable project files, a protected installer baseline, a complete channel map, safe crossover and limiter documentation, a comparison or bypass method, acceptable warranty terms, and enough independent control to support measurement-guided study. The factory system would be measured before installation.

If those conditions are satisfied, the installed DSP could support factory-versus-installed comparisons, time alignment, crossover and phase analysis, measurement-guided EQ, subwoofer integration where applicable, driver-focused versus all-seat presets, critical-listening correlation, configuration repeatability, and an integrated aftermarket automotive-audio case study.

The scenario remains optional. It will not proceed if adequate capital is unavailable, the total installed cost is unclear, the tuning is shop-locked, project files cannot be retained, safety boundaries cannot be protected, or the portfolio access does not justify the investment.

## Phase 3 — Belmont Immersive Audio Evaluation Study

### Project 5: Open-Room vs. Simulated-Cabin Evaluation

**Status:** Proposed; dependent on Belmont faculty sponsorship, facility approval, equipment access, and human-participant review

Research conditions:

- Conventional 7.1.4 open-room baseline
- Reduced-volume simulated-cabin condition

Listening-position variable:

- Front Left
- Front Right
- Rear Left
- Rear Right
- Rear Center or equivalent representative position

Recommended objective pilot:

- One calibrated omnidirectional measurement microphone
- Four representative loudspeaker channels
- Five positions
- Two environmental conditions
- Four sequential channel sweeps in each recording sequence
- Ten primary recording passes producing 40 channel-to-position impulse responses

Potential objective analysis:

- Frequency response
- Impulse response
- Arrival time
- Early reflections
- Decay behavior
- Left/right symmetry
- Channel consistency
- Seat-to-seat consistency

Potential subjective evaluation:

- Approximately 10–11 qualified listeners
- Counterbalanced presentation order
- Localization
- Front-stage stability
- Envelopment
- Height perception
- Tonal balance
- Bass uniformity
- Clarity
- Overall preference

The listener component will proceed only after Belmont confirms and completes the required human-participant review process. An objective pilot may stand as an independent deliverable if the full listener study is not immediately feasible.

## Phase 4 — Measurement-Guided DSP Follow-Up

### Project 6: SigmaStudio DSP Development

**Status:** Planned after usable measurement results  
**Detailed plan:** [Part 2 — Measurement-Guided DSP Development in SigmaStudio](03_Immersive_Audio_Evaluation_Part_2_SigmaStudio_DSP_Project.md)

Proposed signal flow:

> **Input routing → gain/mute → delay → parametric EQ → crossover or bass management → limiter → output routing**

Potential work:

- Measurement-to-processing requirements table
- Channel level and arrival-time alignment
- Broad, evidence-based parametric EQ
- Crossover and bass-management study
- Open-room and simulated-cabin references
- Front-seat, rear-seat, and all-seat compromise configurations where supported
- Bypass and controlled comparison
- GNU Octave/Python predicted validation
- Reduced two-input/four-output SigmaDSP implementation if hardware access becomes practical

Part 2 will remain separate from the original Part 1 experiment. DSP processing will not be retroactively presented as a variable in the initial study.

## Phase 5 — Optional Access-Dependent Extensions

These items can strengthen the portfolio but are not required for the core program:

- Physical SigmaDSP deployment and measurement
- Conditional installed car DSP study if the capital, quote, access, safety, and documentation requirements are satisfied
- Audio Weaver native-PC or embedded implementation
- Embedded-C audio-controller development
- Physical two-node CAN bench
- CAN FD and UDS diagnostic extensions
- Expanded channel count
- Physical 25-speaker demonstrator
- Real-time adaptive or vehicle-state-dependent processing
- Additional vehicles and cross-vehicle comparison

## Separate Future Research Concept

Road-noise and EV masking remain separate from the Belmont open-room versus simulated-cabin study.

Possible future conditions:

- Parked or quiet
- Low-speed EV operation
- Highway operation

Possible processing concepts:

- Noise-dependent EQ
- Adaptive gain
- Dynamic spatial processing
- Seat-specific tuning
- CAN-controlled vehicle-state presets

No road-noise condition will be described as part of the Belmont study unless the approved research design is formally changed before data collection.

## Employer-Facing Completion Milestones

### Milestone 1 — Automotive Software and Architecture

- Completed CAN/DBC simulation
- Completed 25-speaker conceptual architecture
- Representative GNU Octave/Python DSP simulation
- Linked critical-listening record

### Milestone 2 — Measured Automotive Evidence

- Vehicle measurement campaign
- At least one completed acoustic-analysis case study
- Measurement-guided DSP recommendation
- Objective results, limitations, and reproducible methodology

### Milestone 3 — Differentiating Research and DSP Evidence

- Belmont objective pilot or full study
- Listener results if approved and completed
- SigmaStudio Part 2 implementation
- Predicted or physical validation

Applications and professional outreach do not need to wait until Milestone 3. Each completed milestone should be published and reviewed independently.

## Scope and Claims Policy

Throughout this portfolio:

- Planned work will not be presented as completed work.
- Simulated data will not be presented as measured data.
- Software-in-the-loop CAN work will not be presented as a physical vehicle-network implementation.
- A conceptual 25-speaker design will not be presented as a deployed system.
- Participant roles will remain separate from authorship.
- Academic, classroom, independent-study, and portfolio work will not be described as peer-reviewed publication.
- Limitations and access dependencies will remain visible.

## Current Priority

The intended priority order is:

1. Secure feasibility information for the Belmont study.
2. Develop the software-only CAN/DBC simulation.
3. Specify the 25-speaker conceptual architecture.
4. Build a representative GNU Octave/Python DSP model.
5. Complete a vehicle measurement campaign.
6. Evaluate the [conditional installed car DSP scenario](04_Conditional_Car_DSP_Installation_and_Portfolio_Validation_Plan.md) only after sufficient capital, an itemized quote, and full portfolio-access conditions are confirmed.
7. Conduct the Belmont pilot or full study if approved.
8. Use the resulting evidence for the SigmaStudio Part 2 project.
9. Add other physical hardware or Audio Weaver only when access and project needs justify it.

