# Data Dictionary

**Dataset Name:** `week4_dataset*.csv`

**Description:** Dataset containing customer demographics, behavioral metrics, intervention group assignment, and purchase outcome data.

| Variable Name | Data Type | Description |
| :--- | :--- | :--- |
| `group` | Factor | Group membership used for comparison (Control, Treatment). The individual who prepared the data had worked in the medical field and often used this terminology to differentiate between those with and without an intervention. |
| `customer_age` | Integer | Customer age at the time of the extract (in years). |
| `customer_type` | Factor | Customer status based on prior relationship with the company (New, Existing). |
| `avg_order_value_gbp` | Numeric | Average order value for the customer over a stated historical window in GBP (£). |
| `orders_last_90d` | Integer | Number of orders placed in the last 90 days prior to the extract date. |
| `web_sessions_last_30d` | Integer | Number of website sessions in the last 30 days prior to the extract date. |
| `discount_eligible` | Factor | Whether the customer is eligible for a discount under the intervention rules (No, Yes).|
| `area_affluence_score` | Integer | Area-level affluence score associated with the customer's location (higher implies more affluent). Unitless index. |
| `made_purchase_30d` | Factor | Whether the customer made at least one purchase in the 30 days after the intervention/extract reference point (No, Yes). |
