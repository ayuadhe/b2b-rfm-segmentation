# B2B RFM Segmentation for H2 Revenue Optimization

<p align="center">
  <img width="1670" height="1080" alt="Image" src="https://github.com/user-attachments/assets/f2c248f3-7143-42cf-afd4-ce97899de602" />
</p>

### Business Case:

The company is a B2B supplier of home and living products serving corporate and retail clients. To support revenue growth in H2 2020, management requires a data-driven client segmentation to enable more targeted and effective marketing initiatives.

### Objective:
This project aims to segment the clients based on their H1 2020 transactional behavior to enable targeted marketing, improve marketing effectiveness, and mitigate churn risk ahead of H2 2020.

### Business Questions:
1. How is revenue distributed across clients?
2. How can clients be segmented using RFM?
3. Which segments deliver the highest value, growth potential, and churn risk?
4. How should marketing strategies be tailored for each segment?

<br>
<h1 align="center">Key Findings</h1>
<br>

1. Revenue is broadly distributed across clients, with 80% contributed by 36 of 50 clients (72%), indicating low concentration risk.
2. Using the RFM framework, clients are segmented into six distinct groups: Champions, Loyal, Potential, Growing, At Risk, and Low Value.
   *(Further details on the segmentation are provided in the Methodology section).*
3. Champions and Loyal represent 42% of the client base and contribute 49.49% of revenue, indicating a healthy and balanced revenue structure driven by top-tier clients.
4. Growing clients represent 26% of the client base but contribute 19.94% of revenue, showing a lower revenue contribution relative to their size.
5. Low Value clients contribute $2.13M (15.10% of total revenue), reflecting a long-tail segment with aggregate contribution driven by volume despite low individual value.


<br>
<h1 align="center">Data & Methodology</h1>

### 1. Data Overview

The data model consists of two primary tables, **Dim_Customers** and **Fact_Sales**, each contributing key information for the RFM analysis. The dataset covers transactions from **January 1 to June 30, 2020**, representing **50 active B2B clients**.

<p align="center">
  <img width="861" height="443" alt="Image" src="https://github.com/user-attachments/assets/197596af-273f-4720-9e52-e6cfd8033832" />
</p>

<br>

### 2. RFM Metrics

Three behavioral metrics are derived for each client:

- **Recency (R):** Days between the client’s most recent transaction and the reference date (**June 30, 2020**). Lower values indicate more recent activity.
- **Frequency (F):** Total number of orders placed during the observation period.
- **Monetary (M):** Total revenue generated during the observation period.
  
<br>

### 3. Scoring Method

Each metric is scored on a **1–5 scale** using a **rank-based approach**. Clients are ranked across the full client base and converted into scores using:

> Score = ROUNDUP((Rank × 5) / Maximum Rank, 0)
> 

More recent transactions receive higher **Recency** scores, while higher order counts and revenue produce higher **Frequency** and **Monetary** scores. This method ensures scores reflect the **relative distribution of the client base** rather than fixed thresholds.

<br>

### 4. Segmentation Logic

Clients are classified into **six segments** based on their RFM scores, evaluated in the following priority order:
| Priority | Segment | Condition |
| --- | --- | --- |
| 1 | Champions | R ≥ 4, F ≥ 4, M ≥ 4 |
| 2 | Loyal | R ≥ 3, F ≥ 3, M ≥ 3 |
| 3 | Potential | R ≥ 4, F ≥ 2, M ≥ 3 |
| 4 | At Risk | R ≤ 2 and (F ≥ 3 or M ≥ 3) |
| 5 | Growing | R ≥ 3, F ≥ 2, M ≥ 1 |
| 6 | Low Value | All remaining clients |

<br>

1. **Champions** : Most valuable and highly engaged clients. They purchase frequently, spend the most, and have purchased recently.
2. **Loyal** : Regular and stable customers with solid purchasing behavior across all dimensions.
3. **Potential** : High-value clients who have shown strong spending but are not yet frequent buyers.
4. **At Risk** : Previously valuable customers who have not purchased recently.
5. **Growing** : Emerging customers showing initial engagement and spending behavior.
6. **Low Value** : Low engagement, low spending, or inconsistent purchasing behavior.

<br>
<h1 align="center">Deep Dive</h1>

### 1. KPI Overview

<br> 

<p align="center">
  <img width="673" height="111" alt="Image" src="https://github.com/user-attachments/assets/29a4a02d-edbd-4058-9d3b-a8a8c1c29841" />
</p>

In H1 2020, the 50 active clients generated $14.10M in total revenue. Nearly half (49.5%) was contributed by the Champions and Loyal segments, highlighting their importance to overall revenue stability.

Meanwhile, $1.00M is attributed to the At Risk segment, representing previously high-value clients that have shown declining activity and may require retention focus ahead of H2 2020.

<br>

### 2. Revenue & Segment Distribution

<br>

<p align="center">
  <img width="434" height="196" alt="Image" src="https://github.com/user-attachments/assets/13a7891d-e9d2-4005-a0f9-fc98156779e5" />
</p>


- **Champions** lead revenue with $4.0M (28.3%), followed by **Loyal** at $3.0M (21.2%). Together, they contribute nearly half of total revenue while representing 42% of clients.
- **Growing** is the largest segment by size (13 clients, 26%) but contributes only 19.94% of revenue, indicating room for value expansion.
- **Potential** clients (4 clients, 8%) contribute 8.35% of revenue, broadly aligned with their share of the client base.
- **At Risk** clients (3 clients, 6%) generate $1.0M (7.12%), despite being the smallest segment, indicating meaningful revenue exposure and potential churn impact.
- **Low Value** clients (9 clients, 18%) contribute 15.10% of revenue, reflecting a long-tail segment with aggregate contribution despite low individual value.
<br>

<p align="center">
  <img width="307" height="503" alt="Image" src="https://github.com/user-attachments/assets/900d73dc-ceaf-4d3e-9804-457698ccfa5c" />
</p>

***A Pareto analysis was conducted to assess revenue concentration across the 50 active clients**. Total revenue generated during the observation period (January–June 2020) amounted to **$14.10M**.*

The results reveal a **long-tail distribution** — reaching 80% of total revenue requires approximately **36 out of 50 clients (72%)**, which deviates significantly from the classic 80/20 Pareto principle that would typically predict only 10 clients driving that threshold.

Individual client contributions are notably thin, ranging from **4.1% at the highest** down to **1.7% at the 80% cumulative mark**, with minimal spread between them. This indicates that revenue is evenly distributed  across the observed client base, with no single dominant account.

Two key implications emerge from this finding:

- The business has a relatively balanced revenue base with no strong concentration risk.
- There is **no quick win** from focusing exclusively on a handful of top accounts. Sustainable revenue growth must therefore come from **broad-based improvements across segments:** retaining top-tier clients, accelerating mid-tier development, and reducing churn exposure at the lower end.

<br>

### 3. RFM Segment Positioning

<br>
<p align="center">
  <img width="386" height="245" alt="Image" src="https://github.com/user-attachments/assets/d0363ace-430b-4dc6-9fc8-c5da014db5b4" />
</p>

*The scatter plot presents each segment’s average RFM profile across Recency (X-axis), Monetary (Y-axis), and Frequency (bubble size).*

- **Champions** occupy the top-right with the largest bubble, confirming their dominance **as the most recent, highest-spending, and most frequent buyers**.
- **At Risk**, in the top-left, has a similarly large bubble but low Recency, **signaling declining activity and the need for immediate retention efforts**.
- **Loyal** clusters near the center-right, showing **balanced**, above-average RFM scores — consistent **performers below the Champions level**.
- **Potential** appears on the right with a smaller bubble, reflecting **strong recent engagement but lower Frequency and Monetary scores**.
- **Growing**, near the center, shows **moderate Recency and low Monetary**, indicating active clients still in **early development**.
- **Low Value** occupies the lower-left with a small bubble, reflecting **limited engagement across all three dimensions.**


<br>
<h1 align="center">Strategic Recommendations</h1>

### **1. Champions  →**  *Retain & Maximize Lifetime Value*

**Insight:** Champions are the core revenue driver of the business, contributing 28.3% of total revenue ($14.10M). The key priority is to maintain a seamless customer experience and maximize lifetime value through deepened engagement.

**Recommended Actions:**

- Establish a VIP loyalty program with exclusive benefits and priority services
- Provide early access to new products and priority purchasing opportunities
- Personalized premium offers to drive upsell and cross-sell
- Introduce referral programs to leverage their network and expand acquisition

<br>

### **2. Loyal →**  *Increase Transaction Value & Elevate to Champions*

**Insight:** Loyal clients demonstrate consistent purchasing behavior and stable engagement. The focus is not retention, but increasing transaction value and encouraging progression to the Champions segment.

**Recommended Actions:**

- Cross-selling strategy for complementary products based on purchase history
- Volume discount or bundling strategies to increase basket size
- Tiered loyalty program with clear progression thresholds toward the Champions segment

<br>

### **3. Growing →**  *Accelerate Frequency & Basket Expansion*

**Insight:** Growing is the largest segment by client count (26%) yet its revenue share is below proportional (19.94%). This gap represents the largest opportunity heading into H2 2020, making it critical to leverage momentum, increase frequency and basket size.

**Recommended Actions:**

- Incentives for increased transaction value
- Promote mid-tier and premium product categories
- Run time-limited promotions to stimulate purchase frequency
- Expand cross-category exposure to broaden purchasing behavior

<br>

### **4. Potential →**  *Frequency Activation*

**Insight:** Potential clients show strong spending capacity but inconsistent purchase frequency. The objective is to convert sporadic purchases into a regular pattern.

**Recommended Actions:**

- Purchase reminders based on historical buying intervals
- Offer incentives for second and third purchases to establish repeat behavior
- Run targeted campaigns based on frequently purchased product categories

<br>

### **5. At Risk →**  *Reactivation Priority*

**Insight:** With an average revenue of ~$334K per client, losing even one At Risk client carries significant impact. The intervention window is narrow.

**Recommended Actions:**

- Conduct direct outreach to identify drivers of reduced activity
- Deploy time-limited win-back offers tailored to past purchase behavior
- Use short surveys or interviews to identify behavioral changes

<br>

### **6. Low Value →**  *Cost Efficiency & Monitor Growth Signals*

**Insight:** Low Value clients collectively contribute $2.13M in revenue. While not negligible, their low individual value does not justify high-touch engagement, requiring a cost-efficient and scalable approach.

**Recommended Actions:**

- Automated campaigns promoting entry-level and best-selling products
- Optimize promotional spend by focusing on high-margin products
- Behavioral monitoring to detect clients showing growth signals

<br>

## Project Report
📄 PDF Report:
[B2B RFM Segmentation for H2 Revenue Optimization.pdf](b2b-rfm-segmentation-h2-revenue-optimization.pdf)






