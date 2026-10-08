# Wide-Bandgap Gate Drivers & Protection

## Requirements Driven by SiC & GaN
- High Common-Mode Transient Immunity (CMTI) — typically > 100 V/ns
- Fast switching with controlled dv/dt and di/dt
- Accurate and fast over-current / desaturation protection
- Miller clamp and/or negative turn-off bias to prevent spurious turn-on
- Low isolation capacitance
- Suitable gate voltage levels (e.g., +15…+20 V / –3…–5 V for many SiC MOSFETs; 5–6 V for many GaN devices)

## Driver Architectures
- Galvanically isolated drivers (capacitive, magnetic, or optical isolation)
- Bootstrap vs isolated supply for high-side
- Integrated vs discrete gate drive solutions
- Multi-channel and half-bridge drivers
- Digital isolators + external power stage vs fully integrated

## Critical Protection Features
- Desaturation (DESAT) detection with blanking time
- Soft turn-off or two-level turn-off under fault
- Undervoltage lockout (UVLO) on both primary and secondary sides
- Active Miller clamp
- Short-circuit withstand coordination with device short-circuit capability

## Layout Rules (Non-Negotiable)
- Minimize gate loop inductance (kelvin connection preferred)
- Separate power and gate return paths where possible
- Place driver and bypass capacitors as close as possible to the power device
- Control common-mode current paths created by isolation capacitance
- Consider PCB creepage/clearance for high working voltages

## Practical Recommendations
- Always verify driver CMTI, propagation delay matching, and fault response time against the application
- Evaluate gate resistor values for both turn-on and turn-off (split resistors recommended)
- Account for temperature dependence of threshold voltage and driver performance
- For paralleled WBG devices, ensure symmetrical gate and power loops
- Never rely on a driver’s “typical” ratings without checking worst-case conditions and layout impact
