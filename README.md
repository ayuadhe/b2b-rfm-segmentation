# B2B RFM Segmentation for Q3–Q4 Revenue Optimization

<p align="center">
  <img width="2021" height="1311" alt="Image" src="https://github.com/user-attachments/assets/54a5d380-1e9d-4afd-943b-d68c9595d669" />
</p>

### Business Case:
The company is a B2B home and living products supplier with revenue concentrated among a limited number of corporate and retail clients. To drive performance in Q3–Q4, management requires a data-driven analysis of its 50 selected active clients. An RFM analysis will help prioritize clients, identify growth opportunities, and mitigate revenue risks.

### Business Questions:
- Which clients contribute the highest revenue and long-term value?
- How revenue is distributed across client segments?
- Which clients demonstrate strong growth potential?
- Which clients are at risk of decline or churn risk?
- How should the company prioritize clients strategically to maximize Q3–Q4 performance?

<br>
<h1 align="center">Data & Methodology</h1>
<br>

### Data Schema
The data model consists of two primary tables, **Dim_Customers** and **Fact_Sales**, each contributing key information for the RFM analysis.
<p align="center">
  <img width="1379" height="700" alt="Image" src="https://github.com/user-attachments/assets/5009f6e7-375c-4c46-88e8-e14ff3f1fe7d" />
</p>

### Methodology
**1. RFM Analysis**
- **Recency (R)**: Days since the last purchase.
- **Frequency (F)**: Number of transactions in the period.
- **Monetary (M)**: Total spend during the period.
Clients are scored on a 1-5 scale for each metric, then grouped into segments (Champions, Loyal, Potential, Growing, At Risk, Low Value).

**2. Pareto Analysis**

Pareto analysis (80/20 rule) is used to assess how revenue is distributed among clients, helping to understand whether a few clients drive most of the revenue or if it’s more evenly spread.

<br>
<h1 align="center">Insights</h1>
<br>

<p align="center">
  <img width="544" height="411" alt="Image" src="https://github.com/user-attachments/assets/b14e7adb-e215-4a06-8dc9-2c26ae57679f" />
</p>

We started by conducted a Pareto analysis to assess revenue concentration. The results show a long-tail distribution, indicating revenue is spread across a broad client base rather than driven by a few dominant accounts.

Reaching 80% of total revenue requires 36 of 50 clients, suggesting low concentration risk. **Therefore, growth strategy should focus on improving retention and purchase frequency across the broader client base.**

<br>
<p align="center">
  <img width="620" height="366" alt="Image" src="https://github.com/user-attachments/assets/f7699ac4-6232-483d-82f7-df9d483b5448" />
</p>

Structurally, the business is in a relatively healthy composition. High-value segments (Champions 24% and Loyal 20%) represent 44% of total clients and serve as the primary revenue drivers. Meanwhile, the lowest-performing segments, At Risk and Low Value (20% combined), represent the smallest portion of the portfolio. This distribution is generally positive, as a significant share of clients falls within productive segments.

However, the portfolio is not fully dominated by top-tier clients, meaning overall stability still depends on the movement and performance of mid-tier segments.

<br>
<p align="center">
  <img width="569" height="372" alt="Image" src="https://github.com/user-attachments/assets/1fd99329-c2d4-4646-983e-72e9f0466a52" />
</p>

There are two key areas to manage:

- **36% of clients are in the Potential and Growing segments**, representing the largest expansion opportunity. Upgrading 30–40% of these mid-tier clients (±5–7 accounts) to Loyal or Champions could generate measurable and sustainable revenue growth.
- **At Risk and Low Value segments represent 20% of total clients,** yet contribute approximately $2.4M (±17%) of total revenue. Churn within this group could impact cashflow stability.

Overall, the portfolio remains balanced without extreme concentration. However, revenue stability is influenced by three factors: reliance on high-value segments, under-monetized mid-tier clients (36%), and churn exposure within the 20% at-risk segment.

Q3–Q4 priorities should focus on: **retaining top-tier clients, accelerating mid-tier upgrading, and proactively reducing churn risk.**

<br>
<h1 align="center">Strategic Action Recommendations</h1>
<br>

<p align="center">
  <img width="1000" height="622" alt="Image" src="https://github.com/user-attachments/assets/7e967c3c-ddd7-4551-bb32-5a12bc83f1fb" />
</p>

### 1. Champions
- **Insight:** Largest and most stable revenue contributors.
- **Strategy:** Retain & maximize lifetime value.
- **Actions:**
  - VIP program & exclusive benefits
  - Personalized premium offers
  - Early access to launches
  - Referral program

### 2. Loyal
- **Insight:** Consistent buyers with strong retention and upsell potential.
- **Strategy:** Increase transaction value and elevate to Champions.
- **Actions:**
  - Strategic cross-selling & curated bundles
  - Subscription and replenishment programs
  - Tiered loyalty program
  - Volume discount

### 3. Potential
- **Insight:** Engaged but inconsistent purchasing behavior.
- **Strategy:** Increase purchase frequency.
- **Actions:**
  - Time-limited repeat order promotions
  - Segmented campaigns
  - Product education
  - Reminders or special offers for next purchase

### 4. Growing
- **Insight:** Demonstrating upward purchasing trends.
- **Strategy:** Leverage momentum and increase basket size.
- **Actions:**
  - Incentives for increased transaction value
  - Mid-tier & premium product promotions
  - Reorder reminders based on shopping cycle
  - Cross-category exposure strategy

### 5. At Risk
- **Insight:** Declining activity with potential revenue leakage.
- **Strategy:** Selective and efficient reactivation.
- **Actions:**
  - Limited-time win-back incentives
  - Product recommendations based on purchase history
  - Survey to identify behavior shifts
  - Direct outreach for high-value customers
 
### 6. Low Value
- **Insight:** Low contribution, volume-based segment.
- **Strategy:** Maintain cost efficiency & monitoring growth potential.
- **Actions:**
  - Automated campaigns
  - Promotions for entry-level / best-selling products
  - Controlled promotional spending
  - Behavioral tracking for growth signals
    
<br>

### Strategic Direction
- Protect core revenue from Champions & Loyal segments.
- Accelerate growth in Growing & Potential segments.
- Prevent revenue loss in At Risk segment.
- Optimize cost-to-serve for Low Value segment.




