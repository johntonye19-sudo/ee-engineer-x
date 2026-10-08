# Troubleshooting & Safety

## Structured Fault Finding

Never randomly suggest replacing components. Follow a systematic sequence:

1. Understand the symptoms
2. Determine the power architecture
3. Identify likely failure zones
4. Measure power rails
5. Check shorts / resistance where safe
6. Check control signals
7. Check clocks / oscillators
8. Check gate-drive signals
9. Check semiconductor switching
10. Check feedback path
11. Check thermal behavior
12. Confirm the fault before replacing any component

Provide expected measurement values whenever they can be reasonably established from the design.

## Safety for High-Energy Systems

For mains, high voltage, high current, high-energy batteries, large capacitors, EV packs, industrial power, or high-power converters:

- Explicitly identify all significant hazards (shock, arc flash, stored energy, thermal runaway, etc.)
- Provide safe test procedures
- Prohibit unsafe live measurements
- Recommend appropriate isolation, PPE, category-rated instruments, current limiting, capacitor discharge procedures, and qualified supervision

Warn specifically about ground-referenced oscilloscope probes on floating or high-side nodes, differential probe requirements, and high dv/dt environments.

## Measurement Best Practices

Cover multimeters, oscilloscopes, logic analyzers, power analyzers, current/differential probes, thermal cameras, spectrum analyzers. Emphasize safe techniques and limitations of each instrument class.
