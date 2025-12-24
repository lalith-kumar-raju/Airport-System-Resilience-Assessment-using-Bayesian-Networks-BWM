# Airport System Resilience Assessment

A Bayesian Network-based approach for evaluating airport system resilience using the Best-Worst Method (BWM) for expert judgment aggregation.

## Overview

This project assesses the resilience of Chinese airport systems across three categories using:
- **14 risk factors** (C1–C14) covering personnel, equipment, environment, and management
- **4 resilience dimensions**: Preparation (B1), Resistance (B2), Recovery (B3), Optimization (B4)
- **Overall Resilience** (A1) as the target node

![Bayesian Network Model](bayesian_network.png)

## Results

| Airport Category | Resilience Score | 95% CI |
|------------------|------------------|--------|
| Category I (Major hubs) | 85.3% | [83.1%, 87.5%] |
| Category I-2nd (Regional) | 83.9% | [82.7%, 85.1%] |
| Category II (Medium) | 79.3% | [78.9%, 81.6%] |

## Repository Structure

```
├── model/
│   ├── airport_resilience.xdsl    # GeNIe Bayesian Network model
│   ├── priors.csv                 # Prior probabilities by airport category
│   └── cpt/                       # Conditional Probability Tables
│       ├── A1_cpt.csv
│       ├── B1_cpt.csv
│       ├── B2_cpt.csv
│       ├── B3_cpt.csv
│       └── B4_cpt.csv
└── data/
    └── incidents/                 # Incident data by airport category
```

## Requirements

- [GeNIe Academic](https://www.bayesfusion.com/genie/) for model visualization and inference

## Methodology

1. **Prior Probabilities**: Derived from incident frequency data
2. **CPT Generation**: Best-Worst Method with 10 domain experts
3. **Inference**: Bayesian Network propagation in GeNIe
4. **Validation**: Bootstrap confidence intervals (1,000 iterations)

## License

This project is for academic research purposes.
