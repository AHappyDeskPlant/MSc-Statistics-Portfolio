# Data Dictionary

# Data Dictionary


**Dataset Name:** st422_week3_subscription_*.csv

**Description:** Dataset containing customer demographics, subscription details, marketing info, and revenue metrics.

*Note: Version `v3` includes 5 additional variables regarding marketing and revenue that are not present in v1 or v2.*

| Variable Name | Data Type | Description |
| :--- | :--- | :--- |
| `customer_id` | Integer | Unique identifier for each customer |
| `signup_date` | Date | The date the customer originally registered |
| `region` | Factor | The geographic region of the customer (e.g., North, South) |
| `plan_type` | Factor | The subscription tier (e.g., Basic, Premium) |
| `tenure_months` | Integer | Number of months the customer has held the subscription |
| `monthly_fee_gbp` | Numeric | Monthly cost of the subscription in GBP (£) |
| `support_tickets_90d` | Integer | Number of customer support tickets raised in the last 90 days |
| `last_login_days` | Integer | Number of days elapsed since the customer's last login |
| `nps_score` | Numeric | Net Promoter Score (customer satisfaction rating 0-10) |
| `churned_90d` | Integer | Indicator if the customer cancelled in the last 90 days (1 = Churned, 0 = Active) |
| `marketing_channel` | Factor | The acquisition channel (e.g., Social, Paid Search, Organic) |
| `device_type` | Factor | The primary device used to access the service (e.g., Mobile, Desktop) |
| `income_band` | Factor | Estimated annual income bracket of the customer |
| `contract_type` | Factor | The billing frequency (e.g., Monthly, Annual) |
| `revenue_last_3m_gbp` | Numeric | Total revenue generated from this customer in the last 3 months (£) |
