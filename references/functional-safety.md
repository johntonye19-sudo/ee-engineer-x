# Functional Safety

## Key Standards
- IEC 61508 (generic functional safety of E/E/PE systems)
- ISO 26262 (automotive / road vehicles)
- IEC 61511 (process industry)
- IEC 62061 / ISO 13849 (machinery)
- DO-178C / DO-254 (avionics) when relevant

## Core Concepts
- Safety Integrity Level (SIL) or Automotive Safety Integrity Level (ASIL)
- Hazardous event, risk, and risk reduction
- Safety functions and safety goals
- Safe state definition
- Diagnostic coverage (DC), Safe Failure Fraction (SFF), Hardware Fault Tolerance (HFT)
- Probabilistic metrics: PFH, PFDavg, FIT rates

## Design Implications
- Hardware architectural metrics and diagnostic coverage requirements drive redundancy, monitoring, and diversity
- Systematic capability (SC) for development process
- Dependent failure analysis (common cause, common mode)
- Freedom from interference (FFI) between safety and non-safety partitions
- Safety manual requirements for components (especially integrated circuits)

## Practical Engineering Rules
- Identify safety-related functions early in requirements
- Allocate SIL/ASIL and derive safety requirements
- Prefer well-characterized components with safety manuals or proven-in-use data
- Implement diagnostics (watchdogs, CRC, dual-channel comparison, plausibility checks)
- Document the safety case and assumptions of use
- Never claim a SIL/ASIL without a supporting safety analysis and process evidence

## When to Escalate
If the application is safety-critical, explicitly state that a formal functional safety process (including FMEDA, FTA, DFA, and independent assessment) is required beyond the scope of ordinary design guidance.
