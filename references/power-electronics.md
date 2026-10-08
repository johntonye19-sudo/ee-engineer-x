# Power Electronics — Core & Advanced Guidance

## Converter Topologies

**Non-isolated**
- Buck, Boost, Buck-Boost, SEPIC, Ćuk, Zeta
- Synchronous and bidirectional variants
- Multi-phase / interleaved

**Isolated**
- Flyback (DCM/CCM), Forward (single/double-switch), Push-Pull
- Half-Bridge, Full-Bridge (hard-switched and phase-shifted)
- LLC, Series Resonant (SRC), Parallel Resonant (PRC), LCC
- Dual Active Bridge (DAB) and variants (TAB, etc.)
- Active Clamp Forward / Flyback

**Special / Advanced**
- Totem-pole and bridgeless PFC
- Multi-level (NPC, Flying Capacitor, Cascaded H-Bridge, MMC)
- Matrix converters
- Current-source converters
- Solid-state transformers / power electronic transformers
- Modular and fault-tolerant architectures

## Mandatory Analysis for Every Switching Converter

- Operating mode (CCM / DCM / BCM / critical)
- Exact duty-cycle and conversion ratio derivation
- Inductor current ripple and magnetizing current
- Capacitor voltage ripple and RMS currents
- Switching frequency selection rationale (loss, size, EMI, control bandwidth)
- Detailed loss breakdown:
  - Semiconductor conduction (including dead-time and reverse conduction)
  - Switching (Eon/Eoff or calculated with capacitances and recovery)
  - Gate-drive
  - Magnetic (core + copper, including skin/proximity)
  - Capacitor ESR / ESL
- Soft-switching boundaries (ZVS/ZCS range)
- dv/dt, di/dt, voltage overshoot, and snubber requirements
- EMI noise sources and filter requirements
- Thermal performance and power density
- Control-to-output and line-to-output transfer functions (including RHP zeros)

Derive from first principles: switching states → state equations → averaging → linearization → small-signal model.

## Wide-Bandgap Devices (SiC & GaN)

Evaluate using full set of dynamic parameters:
- RDS(on) vs temperature and current
- Qg, Qgd, Qgs, Qoss, Qrr
- Ciss, Coss, Crss (and energy-related Coss)
- Eon / Eoff (or calculated)
- Reverse conduction / third-quadrant behavior
- Threshold voltage and Miller plateau
- dv/dt immunity and gate-loop requirements
- Package inductance and Kelvin connections

**Gate-drive requirements for WBG**
- Isolated drivers with sufficient CMTI
- Desaturation / over-current protection
- Miller clamp and negative turn-off bias when needed
- Gate resistor optimization (turn-on vs turn-off split)
- Layout rules: ultra-low inductance gate and power loops

Selection priority remains: voltage → current → switching performance → losses → thermal → package → availability → cost, with realistic margins.

## Soft-Switching Techniques

- Zero-Voltage Switching (ZVS) and Zero-Current Switching (ZCS)
- Quasi-resonant, multi-resonant, and resonant transition converters
- Phase-shift full-bridge with ZVS
- LLC design methodology (gain curves, FHA, time-domain, magnetizing inductance selection)
- Critical conduction / boundary mode for PFC and low-power converters
- Trade-offs: complexity, circulating energy, load range, EMI

## Advanced Modulation & Control

- Space Vector Modulation (SVM) and discontinuous PWM
- Selective Harmonic Elimination (SHE)
- Model Predictive Control (MPC) — finite control set and continuous
- Multi-sampling and advanced digital delay compensation
- Current-mode control variants (peak, average, emulated, sensorless)
- Grid-forming vs grid-following control
- Virtual synchronous machine / inertia emulation
- Droop control and hierarchical microgrid control

## Magnetic Design (Advanced)

- Core materials: ferrite grades, powder cores, amorphous, nanocrystalline
- Loss models: Steinmetz, improved Generalized Steinmetz Equation (iGSE), loss maps
- Skin and proximity effect (Dowell’s method and improvements)
- Planar magnetics and integrated magnetics
- Fringing field management
- Thermal design of magnetics (hot-spot temperature)
- Interleaving and winding strategies for loss and capacitance reduction

## EMI Filter Design for Converters

- Separation of Differential Mode (DM) and Common Mode (CM) noise
- LISN and measurement considerations
- Filter topologies and damping (to avoid resonance with converter)
- Component selection and parasitic impact
- Layout of filter components

## Reliability & Lifetime of Power Electronics

- Power cycling and thermo-mechanical fatigue
- Capacitor lifetime models (electrolytic, film)
- Semiconductor wear-out mechanisms
- Mission-profile-based lifetime estimation
- Condition monitoring and prognostics (basic concepts)

## Practical Rules

- Never treat an ideal switch as a real semiconductor for final efficiency or thermal claims.
- Always examine the high di/dt and high dv/dt loops in layout.
- For high-power designs, analyze Electrical + Thermal + Mechanical + EMI + Control + Reliability together.
- Document all assumptions and required datasheet verifications.
