
# RappiPlus | End-to-End Business Analytics Capstone

### E-commerce Performance, Customer Behaviour & Experimentation

**Tools:** Python (Pandas, Statsmodels) · PostgreSQL / SQL · Power BI · Jupyter Notebook

## Project Overview

RappiPlus is an end-to-end business analytics capstone examining the commercial performance and customer journey of a simulated e-commerce business.

The project combines data preparation, profitability analysis, customer behaviour analysis, SQL-based funnel exploration, and A/B testing to translate transactional and behavioural data into actionable business recommendations.

The analysis addresses four core business questions:

1. How much revenue does the business generate, and what do the available cost data reveal about profitability?
2. Which products and categories contribute most to commercial performance?
3. Where do event-level customer activity patterns suggest potential friction in the purchasing journey?
4. Does the tested checkout interface change produce a statistically significant difference in conversion?

The project culminates in an interactive Power BI dashboard designed to communicate financial performance, operational insights, and recommendations to business stakeholders.

> **Data transparency:** Some product costs are unavailable, and the SQL funnel analysis cannot verify sequential user progression. These limitations are explicitly documented in the analysis.


## Analytical Methodology

### 1. Data Preparation & Quality Assurance | Python

- Loaded and examined transactional, product catalog, and marketing expenditure datasets.
- Standardised date formats and validated numerical fields.
- Removed duplicate records and checked dataset integrity.
- Preserved 30 transactions with missing product information to avoid understating revenue.
- Exported cleaned datasets for downstream analysis in Power BI.

### 2. Commercial Performance & Profitability | Python + Power BI

- Calculated gross revenue, net sales revenue, product costs, and marketing expenditure.
- Analysed average order value, units per order, and product-level performance.
- Distinguished verified gross profit from provisional profitability estimates.
- Developed interactive Power BI visualisations for commercial performance monitoring.

### 3. Customer Journey Analysis | SQL

- Structured customer interaction events into six purchasing-journey stages.
- Calculated distinct user counts for each event type.
- Compared event-level activity across checkout and payment stages.
- Documented why independent event counts cannot establish sequential conversion or individual user abandonment.

### 4. Checkout Experimentation | Python + Statistical Testing

- Compared control and treatment conversion rates using a two-sided, two-proportion Z-test.
- Evaluated statistical significance at a 5% threshold.
- Interpreted the experiment in the context of a checkout interface decision.

### 5. Business Intelligence & Recommendations | Power BI

- Developed a three-page interactive dashboard: Overview, Details, and Insights.
- Integrated financial KPIs, product-level performance, funnel activity, and A/B testing findings.
- Formulated recommendations for checkout optimisation, acquisition efficiency, and further experimentation.


## Key Findings

### 1. Commercial Performance

| KPI | Result |
|---|---:|
| Gross Revenue (Before Discounts) | $52,079,302.37 |
| Net Sales Revenue | $51,966,981.56 |
| Known Product Costs | $43,124,069.01 |
| Marketing Expenditure | $2,871,843.53 |
| Gross Profit (Pre-Discount, Provisional) | $8,955,233.36 |
| Estimated Profit After Marketing | $5,971,069.02 |
| Verified Gross Profit (Known-Cost Transactions) | $8,942,845.77 |
| Units Sold | 177,527 |

**Interpretation:** The business generates approximately $52 million in gross revenue. However, estimated profitability must be interpreted cautiously because some product costs and other operating expenses are unavailable.

### 2. Data Quality & Profitability Limitations

- 24,946 order records were retained after cleaning.
- 30 transactions have missing product information and unverified product costs.
- These transactions represent $12,262.62 in net sales revenue.
- Verified Gross Profit includes only transactions with known product costs and is calculated before discounts and marketing expenditure.
- Estimated Profit After Marketing is a provisional upper bound, not accounting net income.

### 3. Customer Journey Insights

Event-level unique-user counts indicate:

| Event | Unique Users |
|---|---:|
| First Visit | 7,796 |
| Select Item | 7,582 |
| Add to Cart | 7,634 |
| Begin Checkout | 7,208 |
| Add Payment Info | 6,250 |
| Purchase | 6,240 |

**Interpretation:** The payment-information event records 958 fewer unique users than the checkout event. This warrants investigation into potential payment friction, but does not establish that 958 individual users abandoned checkout.

### 4. A/B Testing Results

| Metric | Control | Treatment |
|---|---:|---:|
| Users | 4,965 | 5,035 |
| Conversions | 779 | 820 |
| Conversion Rate | 15.69% | 16.29% |

- **Statistical test:** Two-sided, two-proportion Z-test
- **Z-statistic:** -0.8133
- **P-value:** 0.4161
- **Significance threshold:** 0.05

**Finding:** The observed conversion-rate difference is not statistically significant. The experiment does not provide sufficient evidence to justify rolling out the checkout interface change.


## Business Recommendations

### 1. Investigate Checkout Friction

**Observation:** The checkout event recorded 7,208 unique users, compared with 6,250 at the payment-information event.

**Recommendation:** Investigate potential friction in payment selection, checkout usability, and transaction completion.

**Next step:** Conduct a sequential, user-level funnel analysis to establish actual progression and abandonment before prioritising specific interventions.

### 2. Do Not Roll Out the Tested Checkout Interface Yet

**Observation:** The treatment achieved a 16.29% conversion rate versus 15.69% for the control group, but the difference was not statistically significant (p = 0.4161).

**Recommendation:** Retain the existing checkout experience until further evidence supports a change.

**Next step:** Review experiment design, sample-size requirements, and statistical power before conducting another controlled test.

### 3. Improve Marketing Efficiency Before Scaling Investment

**Observation:** Marketing expenditure totalled approximately $2.87 million.

**Recommendation:** Evaluate marketing performance by channel, focusing on acquisition efficiency, customer quality, and profitability rather than traffic volume alone.

**Next step:** Develop channel-level performance reporting and validate attribution before reallocating marketing budgets.

### 4. Strengthen Profitability Reporting

**Observation:** Missing product costs prevent complete verification of gross profit, while additional operating expenses are excluded from the estimated profit calculation.

**Recommendation:** Establish data-quality controls for product costs and separate verified financial metrics from provisional estimates.

**Next step:** Resolve missing catalog information and incorporate additional operating expenses to support more reliable profitability decisions.

## Conclusion

The RappiPlus capstone demonstrates how Python, SQL, statistical testing, and Power BI can support evidence-based commercial decision-making.

Beyond dashboard development, the project emphasises data integrity, transparent financial reporting, appropriate statistical interpretation, and the translation of analytical findings into actionable business priorities.


## Project Deliverables

### Python & SQL Analysis
The Jupyter Notebook documents the end-to-end analytical workflow, including:

- Data cleaning and validation
- Revenue and profitability analysis
- SQL-based customer event analysis
- A/B testing and statistical interpretation
- Business insights and recommendations

### Power BI Dashboard
The interactive Power BI report contains three pages:

**01 | Overview**
- Revenue, profitability, and marketing KPIs
- Monthly performance and product-category analysis
- Interactive business filters

**02 | Details**
- Product-level revenue and costs
- Verified gross profit analysis
- Identification of unclassified products

**03 | Insights**
- Customer journey event analysis
- Checkout A/B test results
- Strategic business recommendations

### Repository Structure

The repository is being organised to include:

- `README.md` — Project documentation and key findings
- `rappiplus_capstone_portfolio.ipynb` — Python and SQL analysis
- `dashboard/` — Power BI report and dashboard screenshots

### Data Availability

The analysis uses educational datasets provided for the TripleTen Data Analytics capstone.

Original and cleaned datasets are excluded from this public repository pending confirmation of redistribution permissions.

The notebook requires access to the authorised source datasets to reproduce the full analysis. SQL queries additionally require a configured PostgreSQL connection.

## Skills Demonstrated

**Technical:** Python, Pandas, SQL, PostgreSQL, Power BI, DAX, Jupyter Notebook, statistical hypothesis testing.

**Business:** Commercial performance analysis, profitability assessment, marketing efficiency, customer behaviour, experimentation, KPI reporting, and strategic recommendations.
