# Data Center Liquid Cooling and Waste Heat Recovery Prompt Module

Use this module for manuscripts on AI data centers, high-density servers, cold plates, CDU systems, direct-to-chip liquid cooling, immersion cooling, two-phase cooling, absorption refrigeration, absorption heat transformers, heat pumps, and data-center waste heat recovery.

## Purpose

Revise the manuscript for energy and thermal engineering reviewers by strengthening system-boundary clarity, thermal-hydraulic reasoning, waste-heat quality assessment, engineering deployment discussion, and energy/carbon accounting.

## Core Checks

### 1. Boundary Level

Identify the level of analysis:

- chip;
- package;
- server;
- compute tray;
- rack;
- coolant distribution unit;
- data hall;
- facility;
- district heating;
- lifecycle.

Do not allow broad data-center energy claims if only chip-level or component-level results are reported.

### 2. Liquid Cooling Metrics

Check whether the manuscript reports:

- heat flux;
- chip power;
- inlet coolant temperature;
- outlet coolant temperature;
- coolant type;
- mass flow rate or volume flow rate;
- pressure drop;
- pumping power;
- maximum chip temperature;
- temperature uniformity;
- thermal resistance;
- heat transfer coefficient;
- CDU efficiency;
- facility-side heat rejection strategy.

### 3. Waste Heat Recovery Metrics

Check whether the manuscript distinguishes:

- heat quantity;
- temperature level;
- exergy content;
- supply-return temperature;
- useful heat demand;
- hourly heat-load matching;
- distance to heat users;
- heat exchanger loss;
- heat pump or heat transformer energy input;
- annual recovered heat;
- recovered heat utilization ratio.

### 4. Temperature Lift and Heat Quality

Flag unclear or physically implausible statements.

Bad:
> Liquid-cooling waste heat can directly supply high-temperature industrial heat.

Better:
> Liquid-cooling waste heat is typically available at low to medium temperature levels. Supplying high-temperature industrial heat requires a temperature-upgrading device such as a heat pump or absorption heat transformer, and feasibility depends on temperature lift, COP, exergy efficiency, and demand-side temperature requirements.

### 5. Thermal-Hydraulic Trade-Off

Do not report temperature reduction alone. Check:

- peak temperature reduction;
- temperature uniformity;
- pressure drop increase;
- pumping power;
- net cooling energy;
- thermal-hydraulic performance factor.

### 6. Comparison Baselines

Use appropriate baselines:

- air cooling;
- rear-door heat exchanger;
- direct-to-chip liquid cooling;
- conventional cold plate;
- straight-channel cold plate;
- serpentine cold plate;
- immersion cooling;
- conventional heat pump;
- absorption chiller;
- absorption heat transformer;
- free cooling system;
- district heating connection without temperature upgrading.

### 7. Reliability and Deployment

For engineering claims, discuss:

- leakage risk;
- connector reliability;
- coolant compatibility;
- corrosion;
- fouling;
- maintenance;
- redundancy;
- failure isolation;
- monitoring and control;
- retrofit feasibility;
- rack density constraints;
- server warranty constraints;
- operations and maintenance complexity.

### 8. Energy, Carbon, and Cost Accounting

When claiming energy-saving or decarbonization value, check:

- annualized electricity savings;
- additional pumping power;
- auxiliary energy consumption;
- avoided cooling energy;
- usable recovered heat;
- substituted heat source;
- marginal emission factor;
- electricity and heat price assumptions;
- CAPEX;
- OPEX;
- payback period;
- sensitivity analysis.

## Typical Revisions

### Liquid Cooling

Bad:
> The proposed liquid cooling system significantly improves heat dissipation.

Better:
> The proposed liquid-cooling system reduces the maximum chip temperature by X K at a heat flux of Y W/cm² and a coolant flow rate of Z L/min. The accompanying pressure drop and pumping-power penalty should be reported to determine whether the thermal benefit remains favorable at rack scale.

### Waste Heat Recovery

Bad:
> The recovered heat can be used for district heating and improves sustainability.

Better:
> The recovered heat can support district heating only if its outlet temperature, hourly availability, and distance to heat users match the demand profile. If the coolant outlet temperature is below the district heating supply requirement, a heat pump or absorption heat transformer is needed, which changes the net energy and carbon balance.

### Absorption Heat Transformer

Bad:
> The absorption heat transformer upgrades waste heat efficiently.

Better:
> The absorption heat transformer upgrades part of the waste heat to a higher temperature level. Its performance should be evaluated using temperature lift, COP, exergy efficiency, crystallization margin, solution concentration range, and stability under partial-load operation.

## Output Format

```markdown
## Revised Version
[revised text]

## Data Center Liquid Cooling Notes
- Boundary level:
- Missing thermal-hydraulic metrics:
- Waste-heat temperature and exergy:
- Baseline comparison:
- Reliability / deployment issues:
- Energy-carbon-cost accounting:
- Items needing verification:
```
