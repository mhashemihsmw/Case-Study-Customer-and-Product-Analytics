# Customer & Product Analytics
This project analyzes anonymized CRM data from a B2B SaaS company to uncover insights across customers, sales opportunities, and product usage. By linking accounts, opportunities, and line items, the case study evaluates customer and product performance, explores account hierarchies and business unit structures, and identifies key drivers such as pricing, discounts, and subscription models.

The analysis focuses on segmenting top and bottom customers, ranking product performance, understanding customer structure, and building a similarity-based recommendation engine to suggest relevant products. Overall, the project demonstrates how integrated customer and product analytics can support revenue optimization, targeted sales strategies, and data-driven decision-making.


## Background

The following are datasets of the anonymized customer and sales data from CRM system. The data represents a B2B SaaS business with multiple business units and product categories.

## Data Structure

The dataset consists of three interconnected tables:

### 1. Accounts (Customers) - `data_challenge_account.csv`
- **id**: Unique account identifier (anonymized)
- **parent_account**: Parent account ID for hierarchical relationships
- **billing_address**: Anonymized billing address hash
- **shipping_address**: Anonymized shipping address hash
- **klienten_bewohner**: Number of clients/residents
- **renewal_model**: Subscription renewal model
- **category**: Account category
- **number_patients**: Number of patients served
- **business_unit**: Business unit serving this account

### 2. Opportunities (Sales) - `data_challenge_opportunity.csv`
- **record_type_name**: Type of opportunity record
- **id**: Unique opportunity identifier (anonymized)
- **closedate**: Date when opportunity was closed
- **account_id**: Associated account (links to accounts table)
- **lead_source**: Original source of the lead
- **business_unit**: Business unit handling the opportunity
- **opportunity_first_creation_date**: When opportunity was first created

### 3. Opportunity Line Items (Products) - `data_challenge_opportunity_line_item.csv`
- **id**: Unique line item identifier
- **opportunity_id**: Associated opportunity (links to opportunities table)
- **product_id**: Product identifier (anonymized)
- **quantity**: Number of units sold
- **discount**: Discount percentage applied
- **subtotal**: Subtotal before discount
- **totalprice**: Final price after discount
- **unitprice**: Price per unit
- **listprice**: Standard list price
- **subscriptiontype**: Type of subscription
- **startdate**: Subscription start date
- **enddate**: Subscription end date
- **product_category**: Product category
- **bundled**: Whether product is part of a bundle

## Data Relationships

```
Account (1) ←→ (Many) Opportunity (1) ←→ (Many) Line Items
     ↑
     └── Parent-Child Relationships (self-referencing)
```

## Challenge Questions

Please answer the following questions using the provided data. We expect both analytical insights and the code used to derive them.

### 1. Customer Analysis
**Question**: Who are our top and bottom-performing customers?

**Expected Analysis**:
- Define and justify your metrics for "top" and "bottom" customers
- Identify the top 10 and bottom 10 customers based on your chosen metrics
- Analyze customer characteristics (business unit, category, size indicators)
- Examine the parent-child account relationships and their impact

**Deliverables**:
- List of top/bottom customers with key metrics
- Customer segmentation analysis
- Visualization of customer performance distribution

### 2. Product Analysis
**Question**: What are our top and bottom-performing products?

**Expected Analysis**:
- Define product performance metrics (revenue, quantity, margin, etc.)
- Identify best and worst-performing products and product categories
- Analyze pricing patterns and discount impact
- Examine subscription vs. one-time products performance

**Deliverables**:
- Product performance ranking
- Product category analysis
- Price elasticity and discount impact assessment

### 3. Customer Structure Analysis
**Question**: What is our customer structure and what insights can we derive?

**Expected Analysis**:
- Analyze customer distribution across business units
- Examine account hierarchies (parent-child relationships)
- Customer size analysis (patients, clients/residents)
- Geographic distribution patterns (based on address data)
- Lead source effectiveness analysis

**Deliverables**:
- Customer structure visualization
- Business unit performance comparison
- Account hierarchy analysis
- Customer acquisition insights

### 4. Recommendation Engine
**Question**: Which products could be recommended to which customers based on similarities?

**Expected Analysis**:
- Define customer similarity metrics
- Implement a product recommendation algorithm
- Consider factors like: customer size, business unit, current products, industry patterns
- Validate recommendations with business logic

**Deliverables**:
- Recommendation algorithm explanation
- Sample recommendations for 5-10 customers
- Similarity analysis methodology
- Business value assessment of recommendations

### Bonus Question: Open Innovation Challenge

**Question**: Design and implement an additional data science use case that could provide business value using the available data.

**Task**:
Think like a data science consultant - identify a business problem that our leadership team might not have considered yet, but could be solved with the data at hand.

**Expected Analysis**:

#### Problem Definition
- **Business Context**: Clearly articulate the business problem you want to solve
- **Stakeholder Impact**: Who would benefit from this solution and how?
- **Success Metrics**: How would you measure the success of your solution?
- **Business Value**: What is the potential ROI or business impact?

#### Methodology & Approach
- **Data Requirements**: Which tables and fields would you use?
- **Analytical Approach**: What data science techniques would you apply?
- **Assumptions**: What assumptions are you making about the business or data?
- **Limitations**: What are the constraints or limitations of your approach?

#### Implementation (Bonus)
- **Code Solution**: Implement your solution with working code
- **Results**: Show actual insights or predictions from your implementation
- **Validation**: How would you validate your solution in a real business setting?
- **Scalability**: How could this solution be operationalized?
