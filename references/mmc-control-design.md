# Modular Multilevel Converter (MMC) — Control & Design Deep Dive

## 1. Topology Fundamentals
- Upper and lower arms, each with N series-connected submodules (SMs)
- Submodule types: Half-Bridge (HB), Full-Bridge (FB), Hybrid, Clamp-Double, etc.
- Arm inductor \( L_{arm} \) (limits circulating current and fault current)
- Submodule capacitor \( C_{sm} \) (energy storage and voltage ripple)

## 2. Key Internal Dynamics
**Circulating current**
- Appears as a second-harmonic (and other even harmonics) component
- Causes additional capacitor voltage ripple and conduction loss
- Must be actively controlled or suppressed

**Capacitor voltage balancing**
- Individual SM voltages must be kept equal on average
- Methods: sorting algorithms, phase-shifted carriers with balancing control, model-predictive balancing

**Energy balance**
- Average energy in upper and lower arms must be controlled
- Total energy (DC voltage) and differential energy (affects circulating current)

## 3. Control Hierarchy (Typical Cascaded Structure)

**Outer loops**
- DC-link voltage or power control
- AC-side active/reactive power or current control (grid-following or grid-forming)

**Intermediate loops**
- Arm energy / average capacitor voltage control
- Circulating current control (usually PR or resonant controllers in stationary frame, or PI in dq frames rotating at 2ω)

**Inner loops / Modulation**
- Submodule insertion indices or averaged duty cycles
- Nearest-Level Modulation (NLM), Phase-Shifted PWM (PS-PWM), or Space-Vector methods
- Capacitor voltage sorting and selection logic

## 4. Design Procedure Outline
1. Define system voltage, power, and number of levels (N)
2. Select SM voltage rating and semiconductor devices
3. Calculate required SM capacitance from voltage ripple specification:

\[
C_{sm} \approx \frac{\Delta E_{arm}}{2 \cdot V_{sm} \cdot \Delta V_{sm}}
\]

4. Size arm inductance for circulating current and fault current limiting
5. Design circulating current suppressor (bandwidth, harmonic targets)
6. Design energy balancing controllers
7. Choose modulation method and balancing algorithm
8. Evaluate loss distribution, thermal design, and cooling
9. Design protection: SM bypass, arm overcurrent, DC-side faults (especially for HB-MMC)

## 5. Critical Practical Issues
- Communication and computational burden of sorting algorithms at high N
- Sensor count and reliability (voltage sensors per SM or estimation techniques)
- Startup / pre-charging of SM capacitors
- DC fault handling (HB-MMC cannot block DC faults; FB or hybrid needed)
- Common-mode voltage and high-frequency issues
- Redundancy and fault-tolerant operation (bypassing failed SMs)

## 6. Analysis & Simulation Recommendations
- Use averaged models for control design and system studies
- Use detailed switched models for loss, balancing, and transient validation
- Perform small-signal analysis of circulating current and energy loops
- Include discrete control delays and measurement filters
- Verify performance under unbalanced grid, faults, and submodule failures

**Key reminder:** MMC control is multi-time-scale and multi-objective. Neglecting circulating current or energy balancing will lead to excessive capacitor voltage ripple, higher losses, or instability.
