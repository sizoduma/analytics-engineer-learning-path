# Module 9: Cloud cost attribution and FinOps

This module addresses a critical set of responsibilities often required in modern finance and product analytics roles: understanding cloud and software spend and tying it to product or business usage.

## Learning objectives

- Understand modern cloud cost structures
- Use cost allocation frameworks to map spend to products and teams
- Connect cloud usage and finance data for operational decision-making
- Apply FinOps-style thinking to analytics and product performance

## Core concepts

### Cloud cost fundamentals

- compute, storage, network, and data transfer costs
- per-service usage metadata
- cost structures across AWS, Azure, and GCP

### FinOps and cost attribution

- resource tagging and metadata quality
- cost mapping by product, business unit, or environment
- linking usage and spend to revenue and margin analysis

### FOCUS framework

The FOCUS framework provides a standardized way to represent cost and usage data. You should understand the importance of:

- normalized cost dimensions
- product and service attribution
- spend transparency across multi-cloud environments

## Example cost attribution logic

```python
# Conceptual example

costs = {
    "compute": 12000,
    "storage": 3500,
    "network": 2200,
}

allocation = {
    "product_a": 0.50,
    "product_b": 0.30,
    "internal": 0.20,
}

for key, value in costs.items():
    print(f"{key}: {value}")
```

## Recommended resources

- https://github.com/microsoft/finops-toolkit
- https://github.com/finopsfoundation/focus-standards

## Suggested output

By the end of this module, you should be able to explain:
- how cost attribution supports product and finance decision-making
- why tagging and source data quality are essential for spend analysis
- how cloud cost data can be integrated into finance reporting workflows
