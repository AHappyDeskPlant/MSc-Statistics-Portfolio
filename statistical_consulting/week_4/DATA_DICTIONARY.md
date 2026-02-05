# Data Dictionary

**Dataset Name:** week4_dataset*.csv

**Description:** Dataset containing customer demographics, behavioral metrics, intervention group assignment, and purchase outcome data.

| Variable Name | Data Type | Description |
| :--- | :--- | :--- |
| `group` | Factor | Group membership used for comparison (Control, Treatment). The individual who prepared the data had worked in the medical field and often used this terminology to differentiate between those with and without an intervention. |
| `customer_age` | Integer | Customer age at the time of the extract (in years). Expected range: 18 to 90. |
| `customer_type` | Factor | Customer status based on prior relationship with the company (New, Existing). Please confirm the rule used to classify "New" vs "Existing" (e.g., any prior purchase ever, or within a lookback window). |
| `avg_order_value_gbp` | Numeric | Average order value for the customer over a stated historical window in GBP (£). Expected range: Approximately 8 to 350 (in this file). Please confirm the window used (e.g., last 12 months) and whether refunds/cancellations are included. |
| `orders_last_90d` | Integer | Number of orders placed in the last 90 days prior to the extract date. Expected range: 0 and above. |
| `web_sessions_last_30d` | Integer | Number of website sessions in the last 30 days prior to the extract date. Expected range: 0 and above. Please confirm session definition (e.g., analytics tool, timeout rules, bots filtered or not). |
| `discount_eligible` | Factor | Whether the customer is eligible for a discount under the intervention rules (No, Yes). Please confirm whether this is eligibility or actual discount use. |
| `area_affluence_score` | Integer | Area-level affluence score associated with the customer's location (higher implies more affluent). Unitless index. Expected range: 1 to 60. Please confirm the source and scale (e.g., internal segmentation score, external index) and whether higher always means more affluent. |
| `made_purchase_30d` | Factor | Whether the customer made at least one purchase in the 30 days after the intervention/extract reference point (No, Yes). Please confirm the time window anchor date (intervention send date vs extract date), and whether purchases are defined by order placed vs fulfilled. |