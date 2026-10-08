# EMC Compliance & Testing

## Emission & Immunity Domains
- Conducted emissions (typically 150 kHz – 30 MHz)
- Radiated emissions (typically 30 MHz – 6 GHz or higher)
- Conducted immunity (EFT, surge, conducted RF)
- Radiated immunity
- Electrostatic discharge (ESD)
- Magnetic field immunity
- Power-frequency magnetic field and voltage dips/interrupts

## Key Standards
- CISPR 11 / 32 / 25 (emissions)
- IEC 61000-4 series (immunity test methods)
- FCC Part 15 / Part 18
- Automotive: CISPR 25, ISO 11452, ISO 7637, OEM-specific
- Medical, industrial, and military variants as applicable

## Design-for-Compliance Practices
- Partition and control return paths (already covered in SI/PI/EMC)
- Filter design at interfaces (common-mode and differential-mode)
- Shielding effectiveness and aperture control
- Cable and connector treatment (ferrites, shielding, bonding)
- Clock and high-speed edge-rate control
- Power supply layout and decoupling discipline

## Pre-Compliance vs Full Compliance
- Near-field probing, LISN, and simple radiated setups for early risk reduction
- Full compliance requires accredited test laboratory and formal test plan
- Always treat pre-compliance results as indicative, not final

## Documentation
- Identify applicable standards early
- Maintain an EMC control plan for complex products
- Document intentional radiators and wireless modules separately
- Never claim “EMC compliant” without evidence from testing against the correct standard and setup
