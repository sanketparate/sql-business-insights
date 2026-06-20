# ECOM Schema Dictionary

## Findings:
Schema has 46 tables.

Important attributes:

<br>customers 
orders 
order_items 
products 
sessions 
Events <br>


## Row Counts<br>

Top 5 table names: </br>
| Table Name | Approx Row Count |
|---------|---------|
| session_events  | 292903 | 
| order_status_history | 158414 | 
| experiment_assignments | 140670 | 
| attribution_touches | 100000 | 
| sessions | 100000 | 


## Foreign Key<br>


| Table | Column | References Table | References Column |
|---------|---------|---------|---------|
| orders | customer_id | customers | customer_id |
| order_items | order_id | orders | order_id |
| order_items | variant_id | product_variants | variant_id |
| product_variants | product_id | products | product_id |
| shipments | order_id | orders | order_id |
| reviews | product_id | products | product_id |


# Distinct Categorical Value

Orders:

| Value | Count |
|---------|---------|
| delivered | 19779 |
| shipped | 7715 |
| cancelled | 2178 |


Payment Method:

| Value | Count |
|---------|---------|
| Paid | 37822 |
| failed | 2178 |

Channel:

| Value | Count |
|---------|---------|
| Organic | 4023 |
| Paid  | 3490 |
| Referral | 1192 |
| email| 708|


## Empty Tables

<br>collections : 0
collection_products : 0
consents : 0 


# New tables
| Table Name | Row Count | Grain | Purpose |
|---------|---------|---------|---------|
| session_events | 292903   |One row per event|Tracks user actions during sessions |
| notifications | 6856 | One row per notification sent | Tracks notification sends |
|marketing_campaigns| 100 | One row per campaign | Marketing campaign master data |
|attribution_campaigns| 38405 | One row per attribution mapping | Links marketing campaigns to attribution records |
|product_reviews| 8000 | One row per review | Stores customer product reviews |
|loyalty_accounts| 3000 | One row per loyalty transaction | Points earned/redeemed history |
|loyalty_transactions| 21475 | One row per loyalty transaction | Points earned/redeemed history |
|inventory_items| 2000 | One row per inventory item | Current product inventory |
|inventory_movements| 30207 | One row per inventory transaction |Stock movement history |
|customer_segments| 10 | One row per segment | Segment definitions |
|segment_memberships| 16461 |One row per customer-segment relationship | Maps customers to segments |
|product_images| 7188 | One row per image | Stores product image metadata | 



