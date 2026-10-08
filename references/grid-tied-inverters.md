# Grid-Tied & Grid-Forming Inverters

## Grid-Following (Current-Controlled) Inverters
- Phase-Locked Loop (PLL) design and stability under weak grids
- Current control in dq or αβ frames
- Active and reactive power control
- Low-Voltage Ride-Through (LVRT) / Fault Ride-Through (FRT)
- Harmonic and unbalanced current control
- Anti-islanding detection methods

## Grid-Forming Inverters
- Voltage and frequency control without relying on a strong grid
- Droop control (P-f, Q-V and variants)
- Virtual Synchronous Machine (VSM) / Synchronverter concepts
- Virtual inertia and damping
- Black-start capability
- Synchronization and seamless transition between grid-connected and islanded modes

## Dual-Mode and Hybrid Control
- Grid-supporting functions
- Mode transitions and bumpless transfer
- Hierarchical control in microgrids (primary, secondary, tertiary)

## Practical Design Issues
- Weak-grid stability (impedance-based stability analysis, passivity)
- PLL bandwidth vs control bandwidth interactions
- DC-link voltage control under unbalanced/distorted grids
- Filter design (L, LCL) and resonance damping (passive/active)
- Current limitation and protection during faults
- Compliance with grid codes (IEEE 1547, national codes, ENTSO-E, etc.)

## Analysis & Simulation Recommendations
- Perform impedance scans or analytical impedance models for stability
- Include PLL dynamics and discrete control delays
- Test against relevant grid code scenarios (voltage/frequency ride-through, harmonics, unbalance)
- Never assume infinite-bus behavior for modern power-electronics-dominated grids
