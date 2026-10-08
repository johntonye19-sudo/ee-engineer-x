# Master EE Checklist

Use this as a living quality gate across the full engineering lifecycle. Mark each applicable item. Incomplete critical items block release.

## 1. Requirements & Architecture
- [ ] All electrical, mechanical, thermal, environmental, regulatory, cost, and reliability targets captured
- [ ] Interfaces, power domains, clock domains, and critical signals defined
- [ ] Performance budgets (voltage, current, power, timing, noise, efficiency) established
- [ ] Safety and EMC requirements identified
- [ ] Block diagram and architecture decision records produced
- [ ] High-risk items (long-lead, sole-source, high-power, high-voltage, high-speed) flagged

## 2. Topology & Mathematical Design
- [ ] Appropriate topology selected with clear rationale
- [ ] Governing equations derived (not merely quoted)
- [ ] Operating modes (CCM/DCM, continuous/discontinuous, etc.) identified
- [ ] All calculations include units and intermediate steps
- [ ] Design margins stated and justified
- [ ] Assumptions explicitly listed

## 3. Component Selection
- [ ] Voltage, current, power, frequency, and temperature ratings adequate with derating
- [ ] Package, availability, lifecycle, and second-source considered
- [ ] Reputable manufacturers preferred; datasheet verification flagged where needed
- [ ] Magnetic components sized for saturation, loss, and thermal rise
- [ ] Passive components (ESR, ESL, tolerance, voltage coefficient) considered

## 4. Electrical Performance
- [ ] DC operating points verified
- [ ] Transient behavior (startup, load step, short-circuit) analyzed
- [ ] Efficiency and loss breakdown calculated
- [ ] Thermal performance (junction temperatures, heatsinking) acceptable
- [ ] Parasitics and non-ideal effects considered
- [ ] Control loop stability margins adequate (gain/phase margin, RHP zeros addressed)

## 5. Protection & Safety
- [ ] Over-voltage, over-current, short-circuit, and thermal protection defined
- [ ] Soft-start / inrush limiting implemented where needed
- [ ] Isolation barriers and creepage/clearance meet requirements
- [ ] High-energy hazards (capacitors, batteries, mains) explicitly addressed
- [ ] Safe test procedures and measurement warnings provided
- [ ] Applicable standards identified (no invented clauses)

## 6. Schematic Quality
- [ ] Hierarchical structure clear; net naming consistent
- [ ] Full annotation and design notes for critical decisions
- [ ] ERC clean; all warnings reviewed and justified
- [ ] Power domains, grounding strategy, and return paths documented
- [ ] Measurement points and test connectors defined
- [ ] Schematic review checklist completed (`schematic-review-checklist.md`)

## 7. PCB & Layout
- [ ] Stackup defined early with fabricator input
- [ ] Design rules set by net class (current, impedance, voltage, clearance)
- [ ] Critical components placed first; domains partitioned
- [ ] High di/dt and high dv/dt loops minimized
- [ ] Return path continuity maintained under sensitive nets
- [ ] Decoupling strategy frequency-appropriate
- [ ] Thermal vias, copper pours, and heatsinking planned
- [ ] Layout review checklist completed (`layout-review-checklist.md`)

## 8. SI / PI / EMC
- [ ] Controlled impedance and length matching applied where required
- [ ] PDN impedance targets and decoupling verified
- [ ] Filtering, shielding, and cable/connector strategy addressed
- [ ] High-speed transitions and via stubs managed
- [ ] See `si-pi-emc.md` for detailed guidance

## 9. Simulation & Analysis
- [ ] Appropriate analysis performed (DC, AC, transient, Monte Carlo, worst-case)
- [ ] Models and assumptions documented
- [ ] Simulation results match expected physical behavior
- [ ] Control-to-output and line-to-output transfer functions validated (power electronics)
- [ ] No reliance on ideal switches for final loss/thermal claims

## 10. Manufacturability & Test
- [ ] DFM/DFT/DFA checklist completed
- [ ] Test points, programming access, and fiducials present
- [ ] Fabricator and assembler capabilities confirmed
- [ ] Manufacturing package complete and versioned
- [ ] BOM includes lifecycle and second-source notes

## 11. Prototype & Validation
- [ ] Bring-up plan and test procedures defined
- [ ] Expected measurement values stated
- [ ] Acceptance criteria clear
- [ ] Failure modes and contingency plans identified
- [ ] Lessons learned captured

## 12. Final Engineering Judgment
- [ ] “Would this actually work when physically built?” answered honestly
- [ ] All critical risks (thermal, EMI, stability, safety, reliability) addressed
- [ ] Uncertainties and datasheet-verification items explicitly stated
- [ ] Design is manufacturable, testable, and maintainable
- [ ] Documentation is sufficient for another competent engineer to reproduce the work

---

**Usage notes**
- Apply the full checklist for new designs and major reviews.
- For focused tasks (e.g., pure calculation or troubleshooting), apply only the relevant sections.
- Critical unchecked items must be resolved or formally risk-accepted before declaring a design complete.
