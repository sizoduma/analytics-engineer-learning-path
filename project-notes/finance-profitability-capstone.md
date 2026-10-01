# Finance analytics capstone

## Business scenario

A finance team needs a trusted monthly product profitability report. The report must combine order revenue, refunds, direct cloud costs, customer attributes, and budget values.

## Proposed architecture

```text
ERP / billing / cloud exports
            |
            v
       raw Snowflake tables
            |
            v
       dbt staging models
            |
            v
   intermediate allocation logic
            |
            v
   finance profitability mart
            |
            v
       BI dashboard / planning
```

## Required outputs

1. Monthly gross revenue by product and region
2. Refunds and net revenue
3. Direct cloud cost by product
4. Gross margin and margin percentage
5. Actual versus budget variance
6. Data quality and reconciliation status

## Suggested model names

- `stg_billing_transactions`
- `stg_cloud_costs`
- `stg_budget_values`
- `dim_product`
- `dim_customer`
- `fct_revenue`
- `fct_cloud_cost`
- `fct_product_profitability`

## Acceptance criteria

- Revenue reconciles to the ERP within an agreed tolerance
- Cloud cost allocation percentages total 100 percent
- Every published metric has a definition and owner
- Models have not-null, uniqueness, and relationship tests
- The refresh has a documented SLA and failure runbook
- Sensitive columns are protected through role-based access

## Interview discussion prompts

- How would you handle late-arriving ERP transactions?
- How would you explain a revenue mismatch to Finance?
- When would you use an incremental dbt model?
- How would you allocate shared cloud costs fairly?
- Which quality checks should block publication?
