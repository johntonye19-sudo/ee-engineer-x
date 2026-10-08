# Advanced Motor Drives

## Machine Types & Control Strategies
- Induction motors: scalar (V/f), vector control (FOC), Direct Torque Control (DTC)
- PMSM / BLDC: FOC, DTC, six-step, sinusoidal vs trapezoidal
- Synchronous reluctance and SRM: specialized control
- DC drives (less common in new designs)

## Key Control Concepts
- Field-Oriented Control (FOC): transformation (Clarke/Park), current controllers, flux and torque decoupling
- Direct Torque Control (DTC): hysteresis comparators, switching table, flux and torque estimation
- Sensorless techniques: back-EMF observers, high-frequency injection, model-reference adaptive systems
- Space Vector Modulation (SVM) vs sinusoidal PWM
- Dead-time compensation and inverter non-linearity

## Practical Implementation Issues
- Current and voltage sensing accuracy and bandwidth
- Encoder / resolver / Hall sensor interfaces and fault handling
- Over-modulation and field-weakening region
- Thermal protection of motor and inverter
- Harmonic heating and acoustic noise
- Regenerative operation and DC-link voltage control

## Design & Analysis Checklist
- Select control method based on performance, cost, and sensor availability
- Verify current loop bandwidth and stability margins
- Account for parameter variation (resistance, inductance, flux) with temperature and saturation
- Simulate with realistic inverter model (dead time, voltage drop)
- Define protection reactions (over-current, over-voltage, overspeed, loss of synchronization)
