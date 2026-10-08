# Sensors & Transducers

## Common Sensor Types
- Temperature: thermocouples, RTDs, thermistors, IC sensors
- Current: shunt, Hall-effect, fluxgate, Rogowski, CT
- Voltage: resistive dividers, isolation amplifiers, differential probes
- Position / speed: encoders (incremental/absolute), resolvers, Hall, potentiometers, LVDT
- Force / pressure / strain: load cells, piezoresistive, capacitive
- Light / optical: photodiodes, phototransistors, ambient light, spectrometers
- Chemical / gas / humidity: various electrochemical and capacitive types
- Inertial: accelerometers, gyroscopes, IMUs

## Signal Conditioning
- Amplification (instrumentation amplifiers, programmable-gain)
- Filtering (anti-aliasing, noise rejection)
- Linearization and compensation (temperature, non-linearity)
- Isolation (galvanic, capacitive, optical)
- Excitation (constant current/voltage for bridges and RTDs)
- ADC interface considerations (sampling rate, resolution, reference accuracy)

## Accuracy & Error Sources
- Offset, gain, non-linearity, hysteresis
- Temperature drift and long-term stability
- Noise (thermal, 1/f, interference)
- Quantization and sampling effects
- Installation and mounting errors
- Calibration uncertainty

## Design Practice
- Specify the required measurement uncertainty early
- Choose sensor technology matched to range, bandwidth, environment, and cost
- Provide proper shielding, grounding, and filtering
- Include self-test or diagnostic features where reliability matters
- Document calibration intervals and traceability requirements
- For safety-related measurements, apply functional safety principles (redundancy, diagnostics)
