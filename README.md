# Airport System Resilience Assessment

A Bayesian Network-based approach for evaluating airport system resilience using the Best-Worst Method (BWM) for expert judgment aggregation.

## Overview

This project assesses the resilience of Chinese airport systems across three categories using:
- **14 risk factors** (C1–C14) covering personnel, equipment, environment, and management
- **4 resilience dimensions**: Preparation (B1), Resistance (B2), Recovery (B3), Optimization (B4)
- **Overall Resilience** (A1) as the target node

![Bayesian Network Model](bayesian_network.png)

## Repository Structure

```
├── Model/
│   ├── Bayesian_network.xdsl      # GeNIe Bayesian Network model
│   ├── priors.csv                 # Prior probabilities by airport category
│   ├── A1_cpt.csv                 # CPT for Overall Resilience
│   ├── B1_cpt.csv                 # CPT for Preparation Ability
│   ├── B2_cpt.csv                 # CPT for Resistance Ability
│   ├── B3_cpt.csv                 # CPT for Recovery Ability
│   └── B4_cpt.csv                 # CPT for Optimization Ability
└── Data/                          # Incident data by airport category
    ├── incidents_category_I.csv
    ├── incidents_category_I_2nd.csv
    └── incidents_category_II.csv
```

## Requirements

- [GeNIe Academic](https://www.bayesfusion.com/genie/) for model visualization and inference

## Methodology

1. **Data Collection**: Incident data gathered from Civil Aviation Safety Information Network (CSIN)
2. **Prior Probabilities**: Computed from incident frequency for each risk factor (C1–C14)
3. **Expert Elicitation**: 10 domain experts provided Best-Worst comparisons for CPT generation
4. **CPT Generation**: Best-Worst Method (BWM) optimization to derive conditional probability tables
5. **Model Building**: Bayesian Network constructed in GeNIe with 19 nodes (14 root + 4 intermediate + 1 target)
6. **Inference**: Probability propagation to compute overall resilience P(A1=T)

## License

This project is for academic research purposes.
