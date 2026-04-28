# Energy Top Journal Prompt Module

Use this prompt module when revising manuscripts for energy and thermal engineering journals, including Energy, Applied Energy, Energy Conversion and Management, Renewable and Sustainable Energy Reviews, Applied Thermal Engineering, International Journal of Heat and Mass Transfer, Energy & Environmental Science, Joule, and related outlets.

## Purpose

Revise the manuscript as an energy top-journal reviewer would expect. Improve not only language quality but also technical credibility, system-level clarity, thermodynamic consistency, validation strength, and engineering relevance.

## Core Revision Principles

1. Preserve all numerical values, units, equations, symbols, figures, tables, and references.
2. Do not invent data, citations, experiments, or validation results.
3. Replace broad claims with metric-based statements.
4. Clarify the system boundary before making energy-saving or carbon-reduction claims.
5. Separate first-law energy efficiency from second-law exergy interpretation.
6. Require fair baseline comparison under the same operating conditions.
7. Discuss thermal-hydraulic trade-offs rather than reporting temperature reduction alone.
8. Flag unsupported claims about sustainability, deployment, commercialization, and carbon neutrality.

## Energy Top-Journal Audit Checklist

### 1. Novelty

Check whether the contribution is:

- a new physical mechanism;
- a new system architecture;
- a new optimization method;
- new experimental evidence;
- a new model or validation framework;
- a new review taxonomy;
- a new techno-economic or environmental insight.

Weak novelty statement:
> This study provides a novel and efficient cooling solution.

Stronger novelty statement:
> This study proposes a manifold-based cold plate that reduces peak chip temperature while constraining pressure-drop growth, and evaluates the design under rack-level operating conditions relevant to high-density AI servers.

### 2. System Boundary

Always identify the level of analysis:

- chip level;
- package level;
- server level;
- rack level;
- room level;
- data-center level;
- district-heating level;
- lifecycle level.

Flag any claim that says a technology saves energy without defining whether auxiliary energy is included.

Example revision:
> Within the rack-level cooling boundary, the proposed liquid-cooling design reduces fan power and improves heat removal capacity. The data-center-level benefit depends on CDU pumping power, facility-side heat rejection, and whether recovered heat is used.

### 3. Thermodynamic Consistency

Check:

- source temperature;
- sink temperature;
- output temperature;
- temperature lift;
- heat quantity;
- exergy content;
- COP;
- exergy efficiency;
- heat recovery efficiency;
- heat pump or heat transformer operating principle.

Flag physically implausible claims.

Example revision:
> A 55 °C liquid-cooling outlet stream cannot directly supply 120 °C heat. A heat pump or absorption heat transformer is required to upgrade the temperature level, and feasibility depends on temperature lift, working pair, COP, and part-load stability.

### 4. Thermal-Hydraulic Trade-Off

For cold plates, immersion cooling, microchannels, and liquid-cooling systems, check:

- maximum temperature;
- temperature uniformity;
- thermal resistance;
- heat transfer coefficient;
- Nusselt number;
- Reynolds number;
- pressure drop;
- mass flow rate;
- pumping power;
- overall performance factor.

Bad:
> The optimized cold plate shows better thermal performance.

Better:
> Compared with the straight-channel baseline at the same mass flow rate, the optimized cold plate lowers the peak surface temperature by X K and improves temperature uniformity by Y%. However, pressure drop increases by Z%, so the net benefit should be evaluated using a thermal-hydraulic performance factor.

### 5. Baseline Comparison

Every performance claim must state the comparison baseline:

- air cooling;
- conventional liquid cooling;
- straight-channel cold plate;
- serpentine channel;
- tree-shaped channel;
- immersion cooling;
- existing heat pump;
- absorption chiller;
- absorption heat transformer;
- industry benchmark;
- literature benchmark.

The baseline must use the same or clearly comparable operating conditions.

### 6. Validation and Uncertainty

Check whether the manuscript reports:

- experimental validation;
- literature validation;
- grid or mesh independence;
- time-step independence;
- uncertainty analysis;
- sensor accuracy;
- model assumptions;
- boundary condition sensitivity;
- parameter ranges.

Example revision:
> The numerical model agrees with experimental data within X% across the tested operating range. Additional sensitivity analysis is needed to assess robustness to inlet temperature, mass flow rate, heat flux, and ambient conditions.

### 7. Off-Design and Partial-Load Operation

Top energy journals often expect performance beyond nominal conditions. Check:

- partial load;
- seasonal operation;
- variable ambient temperature;
- variable IT load;
- transient behavior;
- control strategy;
- stability;
- startup and shutdown conditions.

### 8. Engineering Applicability

For engineering deployment claims, check:

- manufacturability;
- coolant compatibility;
- leakage risk;
- corrosion;
- fouling;
- clogging;
- maintenance;
- redundancy;
- system integration;
- safety;
- control complexity;
- CAPEX and OPEX.

Example revision:
> The proposed microchannel design improves chip-level heat removal, but deployment in data centers depends on manufacturability, clogging risk, coolant compatibility, leakage management, and integration with rack-level distribution manifolds.

### 9. Economic and Environmental Relevance

When the manuscript claims sustainability, carbon reduction, or deployment value, check whether it reports:

- annual energy savings;
- electricity price assumptions;
- marginal grid emission factor;
- carbon reduction;
- heat substitution assumptions;
- CAPEX;
- OPEX;
- payback period;
- lifecycle boundary;
- scenario sensitivity.

Example revision:
> The system may support decarbonization if the reduction in cooling electricity and usable recovered heat exceeds additional pumping and control energy. This claim should be quantified using annual energy savings, marginal grid emission factors, and heat-substitution assumptions.

### 10. Figure and Table Quality

Check:

- Are units shown?
- Are operating conditions stated?
- Is the baseline visible?
- Are error bars or uncertainty ranges included where needed?
- Are legends readable?
- Are axes physically meaningful?
- Are temperature, pressure, and flow ranges realistic?
- Does the caption explain the physical implication?

Caption upgrade template:

> Figure X shows [quantity] as a function of [independent variable] under [operating conditions]. Compared with [baseline], [proposed design/system] [main quantitative difference]. This indicates [physical or engineering implication].

## Output Format

Use this format when applying the module:

```markdown
## Revised Version
[revised text]

## Energy Top Journal Notes
- System boundary:
- Metrics and units:
- Baseline comparison:
- Thermodynamic consistency:
- Validation / uncertainty:
- Engineering applicability:
- Items needing verification:
```
