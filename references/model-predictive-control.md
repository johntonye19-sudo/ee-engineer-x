# Model Predictive Control (MPC) for Power Electronics & Drives

## 1. Why MPC in Power Electronics
- Handles multi-objective optimization naturally (current tracking, switching frequency minimization, capacitor voltage balancing, common-mode voltage reduction, etc.)
- Explicitly includes constraints (current limits, voltage limits, switching restrictions)
- Suitable for systems with finite number of switching states (FCS-MPC)
- Fast dynamic response

## 2. Main Variants

**Finite Control Set MPC (FCS-MPC)**
- Enumerates the finite number of possible switching states
- Predicts system behavior for each state over a horizon (usually N = 1 or 2)
- Minimizes a cost function
- Applies the optimal state for the next sampling period
- Very popular for two-level, three-level, and multilevel converters

**Continuous Control Set MPC (CCS-MPC)**
- Outputs a continuous voltage vector (or duty cycles)
- Requires a modulator (PWM/SVM)
- Longer prediction horizons more practical
- Closer to classical optimal control

## 3. Standard FCS-MPC Formulation (Current Control Example)

Prediction model (discrete-time):

\[
\mathbf{i}(k+1) = \mathbf{A} \mathbf{i}(k) + \mathbf{B} \mathbf{v}(k) + \mathbf{E}
\]

Cost function (typical):

\[
g = \| \mathbf{i}^*(k+1) - \mathbf{i}(k+1) \|^2 + \lambda \cdot N_{sw} + \dots
\]

where \( N_{sw} \) penalizes switching effort and additional terms can include neutral-point balance, common-mode voltage, etc.

## 4. Design Steps
1. Derive accurate discrete-time prediction model (include delays if necessary)
2. Define control objectives and translate them into a cost function
3. Select weighting factors (critical and often empirical)
4. Choose prediction horizon and sampling time
5. Implement enumeration or efficient search (sphere decoding, branch-and-bound for long horizons)
6. Add constraints (current protection, overmodulation handling)
7. Validate against classical controllers (FOC + SVM, etc.) on dynamics, THD, switching frequency, and computational load

## 5. Practical Challenges & Solutions
- **Weighting factor tuning** — still largely heuristic; use systematic methods or adaptive weights when possible
- **Computational burden** — increases with number of switches and horizon; use efficient algorithms or FPGA implementation
- **Model mismatch** — add disturbance observers or online parameter estimation
- **Delay compensation** — account for calculation and actuation delay (usually one-step delay compensation)
- **Variable switching frequency** — can be mitigated by adding switching effort terms or using modulated MPC
- **Steady-state error** — use incremental models or add integrators / disturbance models

## 6. Application Examples
- Two-level and multilevel VSIs (current control + neutral-point balance)
- Motor drives (torque and flux control — predictive torque control)
- Active front-end rectifiers
- MMC (current + circulating current + capacitor voltage balancing)
- Dual Active Bridge and other dual-active converters
- Grid-forming inverters with virtual inertia constraints

## 7. Implementation Recommendations
- Start with horizon N = 1 FCS-MPC for concept validation
- Use exact discretization or high-accuracy approximation of continuous-time model
- Measure or estimate all states required by the prediction model
- Benchmark against well-tuned classical control before claiming superiority
- For production code, carefully evaluate worst-case execution time and numerical robustness

**Key insight:** MPC shines when the system has multiple conflicting objectives or hard constraints that are difficult to handle with cascaded PI controllers. For simple single-objective problems, classical control is often still preferable due to lower complexity and easier certification.
