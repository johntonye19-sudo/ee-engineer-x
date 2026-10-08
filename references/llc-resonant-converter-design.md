# LLC Resonant Converter — Detailed Design Procedure

## 1. Specifications Capture
- Input voltage range (Vin_min, Vin_nom, Vin_max)
- Output voltage and current (Vout, Iout_max)
- Output power and overload capability
- Efficiency target
- Switching frequency range (f_min, f_max, f_nom)
- Isolation requirement and safety standards
- Maximum component temperatures and cooling method

## 2. Gain Requirements
Define the required voltage gain range:

\[
M(f_n, Q, k) = \frac{V_{out} \cdot n}{V_{in}/2} \quad \text{(half-bridge)}
\]

or appropriate definition for full-bridge.

Calculate:
- Maximum gain \( M_{max} \) (at Vin_min, full load)
- Minimum gain \( M_{min} \) (at Vin_max, light/no load)

## 3. Resonant Tank Selection
Resonant frequency:

\[
f_r = \frac{1}{2\pi\sqrt{L_r C_r}}
\]

Inductance ratio:

\[
k = \frac{L_m}{L_r}
\]

Quality factor:

\[
Q = \frac{\sqrt{L_r / C_r}}{R_{ac}}
\]

where \( R_{ac} \) is the equivalent AC load resistance reflected to the primary.

**Design trade-offs**
- Higher k → narrower frequency range but higher magnetizing current (higher conduction loss)
- Lower k → wider frequency range, better light-load regulation, larger resonant inductor
- Typical practical k range: 3 – 10 (often 5 – 7 for good compromise)

## 4. First Harmonic Approximation (FHA) Design Steps
1. Choose resonant frequency \( f_r \) (usually near the desired nominal operating point).
2. Select inductance ratio \( k \) based on gain and efficiency targets.
3. Calculate required peak gain and select Q_max from FHA gain curves.
4. Calculate \( R_{ac} \) at full load.
5. Solve for \( L_r \) and \( C_r \).
6. Calculate \( L_m = k \cdot L_r \).
7. Verify gain at Vin_min and Vin_max across load range.
8. Check magnetizing current and resonant current stress.

**Limitations of FHA**
- Inaccurate near or below resonance and at light load.
- Does not capture higher harmonics or discontinuous modes well.
- Always validate critical operating points with time-domain simulation (LTspice, SIMPLIS, PLECS, etc.).

## 5. Time-Domain / Exact Analysis Considerations
- Operation modes: below resonance (boost), at resonance, above resonance (buck)
- ZVS range verification (especially at light load and high input voltage)
- Current and voltage stresses on resonant capacitor and switches
- Dead-time requirement for ZVS

## 6. Magnetic Design
- Integrated transformer (Lr + Lm) vs discrete resonant inductor
- Core selection (ferrite grade suitable for frequency and flux density)
- Gap calculation for Lm
- Winding strategy to control leakage and proximity loss
- Thermal design of transformer

## 7. Secondary-Side Considerations
- Center-tapped vs full-bridge rectifier
- Synchronous rectification (timing, body-diode conduction, adaptive gate drive)
- Output capacitor RMS current and voltage ripple
- Snubbers if needed for secondary ringing

## 8. Control
- Frequency modulation (VCO or digital frequency control)
- Feedback isolation (opto, magnetic, digital isolator)
- Start-up (frequency sweep or open-loop start)
- Over-current and over-voltage protection
- Light-load techniques (burst mode, pulse skipping)

## 9. Validation Checklist
- [ ] ZVS achieved across specified load and input range
- [ ] Gain requirements met with margin
- [ ] Component stresses within ratings with derating
- [ ] Efficiency target reachable (loss breakdown performed)
- [ ] Thermal design acceptable
- [ ] Time-domain simulation confirms FHA results at critical points
- [ ] EMI and layout constraints considered

**Never finalize an LLC design using only FHA curves.** Always close the loop with accurate simulation and, ultimately, hardware measurement.
