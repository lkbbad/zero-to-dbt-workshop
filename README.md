# [Zero to dbt Workshop](https://www.getdbt.com/resources/webinars/zero-to-dbt-workshop)

This project contains the completed work from the [dbt + Snowflake Quickstart](https://docs.getdbt.com/guides/snowflake?step=1), a hands-on workshop designed to introduce new users to dbt (data build tool) using Snowflake as the data warehouse.

## Project Overview

The goal of this workshop is to demonstrate how to use dbt to:
- Transform raw data into analytics-ready models
- Implement modular SQL development
- Build documentation and testing into your analytics workflow

The project uses a mock e-commerce dataset provided by dbt Labs, simulating a typical analytics workflow from staging to marts.

---

## Setup Steps Completed

The following steps were completed during the workshop and are reflected in this repository:

1. **Project Initialization**
   - Created a new dbt project using `dbt init`
   - Configured `profiles.yml` for Snowflake access

2. **Data Source Setup**
   - Connected to the `SNOWFLAKE_SAMPLE_DATA` database
   - Used the `TPC-H` dataset as source tables

3. **Staging Layer**
   - Created models under `models/staging/` to clean and prepare raw data
   - Defined sources in `models/src.yml` with descriptions

4. **Transformation Layer**
   - Built intermediate models in `models/intermediate/` (optional)
   - Built final marts in `models/marts/`:
     - `fct_orders.sql` for fact table
     - `dim_customers.sql` for dimension table

5. **Testing & Documentation**
   - Added schema tests for uniqueness and non-null constraints
   - Added custom tests for valid values
   - Generated documentation via `dbt docs generate`
   - Served docs locally using `dbt docs serve`

6. **Running the Project**
   - Executed `dbt run` to build models in Snowflake
   - Validated model logic and outputs using `dbt test`

---

## Key dbt Features Used

- Sources and seed data
- Ref macros for dependency management
- Schema testing and assertions
- Model materializations
- Documentation generation

---

## How to Reproduce This Locally

To replicate this project, you’ll need:

- A Snowflake account (e.g., a free trial)
- Python + dbt installed
- Your Snowflake credentials in `~/.dbt/profiles.yml`

Then clone the repo and run:

```bash
git clone https://github.com/lkbbad/zero-to-dbt-workshop.git
cd zero-to-dbt-workshop
dbt deps
dbt debug
dbt run
dbt test
dbt docs generate
dbt docs serve