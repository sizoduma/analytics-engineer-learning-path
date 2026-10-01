# Module 3: Snowflake architecture and operations

Snowflake is central to this role. This module focuses on both foundational knowledge and practical operations.

## Learning objectives

- Understand Snowflake architecture and storage/compute separation
- Design warehouses for multiple workloads
- Load data into Snowflake and query large datasets efficiently
- Apply data security and governance patterns

## Core topics

### 1. Architecture

- storage layer
- compute layer
- virtual warehouses
- auto-suspend / auto-resume
- multi-cluster warehouses

### 2. Data loading and staging

- internal stages
- external stages
- COPY INTO
- file formats and ingestion patterns

### 3. Performance and cost optimization

- warehouse sizing
- clustering keys
- search optimization
- query profile and plan review

### 4. Security and access controls

- roles and responsibilities
- object-level permissions
- masking policies
- secure views and sharing

### 5. Data engineering patterns

- incremental loads
- streams and tasks
- transformations in a warehouse or transformation layer

## Example patterns

### Warehouse sizing and workload separation

```sql
CREATE WAREHOUSE finance_analytics_wh WITH
  WAREHOUSE_SIZE = 'MEDIUM'
  AUTO_SUSPEND = 300
  AUTO_RESUME = TRUE;

CREATE WAREHOUSE finance_etl_wh WITH
  WAREHOUSE_SIZE = 'SMALL'
  AUTO_SUSPEND = 180
  AUTO_RESUME = TRUE;
```

### Secure view example

```sql
CREATE OR REPLACE SECURE VIEW finance_reporting.secure_customer_summary AS
SELECT
    customer_id,
    customer_name,
    region
FROM finance_core.customer_dim;
```

### Task-based automation pattern

```sql
CREATE OR REPLACE TASK daily_revenue_rollup
  WAREHOUSE = finance_etl_wh
  SCHEDULE = 'USING CRON 0 2 * * * UTC'
AS
  CALL finance_analytics.sp_refresh_revenue_summary();
```

## Recommended references

- Snowflake docs: https://docs.snowflake.com
- Snowflake Labs examples: https://github.com/Snowflake-Labs/sfguide

## Suggested output

By the end of this module, you should be able to explain:
- why Snowflake separates storage and compute
- how to size warehouses for different user workloads
- how to implement secure views and role-based access

## Hands-on checklist

- Create a database, schema, and warehouse
- Load a sample CSV
- Query with aggregate and window functions
- Implement a role-based permission policy
