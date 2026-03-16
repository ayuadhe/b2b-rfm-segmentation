# B2B RFM Segmentation for H2 Revenue Optimization

<p align="center">
  <img width="1670" height="1080" alt="Image" src="https://github.com/user-attachments/assets/f2c248f3-7143-42cf-afd4-ce97899de602" />
</p>

The company is a B2B supplier of home and living products serving corporate and retail clients. To support revenue growth in H2 2020, management requires a data-driven understanding of 50 selected active clients.

This project applies RFM analysis to segment these clients based on their transactional behavior during H1 2020. The analysis aims to **uncover differences in client value and engagement patterns**. The results provide **actionable insights for the sales and marketing teams** to implement more **targeted marketing strategies, improve marketing efficiency, and mitigate potential churn risks ahead of H2 2020**.

### Business Questions:
1. How is revenue distributed across the 50 active clients?
2. What are the Recency, Frequency, and Monetary profiles of each client?
3. How can clients be segmented based on their RFM scores?
4. Which segments contribute the most revenue and which show the highest growth potential?
5. What strategic actions should be taken for each segment to optimize revenue performance in H2 2020?

<br>
<h1 align="center">Key Findings</h1>
<br>

1. **Revenue is broadly distributed.**<br>
   Reaching 80% of total revenue requires 36 of 50 clients (72%), indicating a diversified revenue base with no single dominant account.
3. **Top-tier clients drive nearly half of total revenue.**<br>
   Champions and Loyal represent 42% of the client base yet contribute 49.49% of revenue. Retention of these two segments is critical to revenue stability.
5. **Growing clients present the largest expansion opportunity.**<br>
   The largest segment by client count (26%) yet contributes only 19.94% of revenue, indicating significant untapped growth potential.
7. **At Risk clients are small in number but significant in revenue exposure.**<br>
   Only 6% of clients, however the average revenue per client reaches $334K, making proactive retention efforts essential.
9. **Low Value clients still contribute meaningful revenue share.**<br>
   This segment generates $2.13M (15.10% of total revenue), modest individually but significant in aggregate.


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
<h1 align="center">Deep Dive</h1>

### 1. KPI Overview

<br> 

<p align="center">
  <img width="665" height="188" alt="Image" src="https://github.com/user-attachments/assets/6a1c8afe-c983-44ed-b94d-a5c13ae1d3ff" />
</p>

During H1 2020, the 50 active clients collectively generated **$14.10M** in total revenue. Nearly half of this (**49.5%**) was driven by the **top two segments (Champions and Loyal)**, underscoring their critical role in revenue stability. 

At the same time, **$1.00M** in revenue sits within the **At Risk segment**, representing accounts that were once high-value but have shown declining activity — making proactive **retention** a near-term priority heading into **H2 2020**.

<br>

### 2. Revenue & Segment Distribution

<br>

<p align="center">
  <img width="441" height="249" alt="Image" src="https://github.com/user-attachments/assets/cd376b76-8f51-4f2a-8d91-50edb29d3ce2" />
</p>


- **Champions lead revenue generation** with **$4.0M (28.3%)**, **followed closely by Loyal** at **$3.0M (21.2%)**, together contributing nearly half of the revenue observed, despite representing only **42%** of the client base.

- **The Growing segment is the largest by client count** (**13 clients, 26%**) yet contributes **19.94% of revenue**, below its proportional share. This gap between client volume and revenue highlights significant **untapped growth potential** within this segment.

- **Potential clients** (**4 clients, 8%**) contribute **8.35% of revenue**, nearly proportional to their size, suggesting that while this segment is small, its members are already transacting at a relatively **healthy level**.

- **At Risk clients (3 clients, 6%)** generate **7.12% of revenue ($1.00M)**, with an average revenue per client of approximately **$334K**. Despite being the **smallest segment by count, the *revenue at stake per client is significant**. Churn within this group would have an **outsized impact** relative to its size.

- **Low Value clients (9 clients, 18%)** contribute **15.10%** of revenue, below their proportional client share, as expected. While individually modest, their collective contribution of **$2.13M is not negligible**. **A cost-efficient, monitoring-based approach** is appropriate here, with **selective escalation** for clients showing growth signals.
<br>

<p align="center">
  <img width="307" height="503" alt="Image" src="https://github.com/user-attachments/assets/900d73dc-ceaf-4d3e-9804-457698ccfa5c" />
</p>

***A Pareto analysis was conducted to assess revenue concentration across the 50 active clients**. Total revenue generated during the observation period (January–June 2020) amounted to **$14.10M**.*

The results reveal a **long-tail distribution** — reaching 80% of total revenue requires approximately **36 out of 50 clients (72%)**, which deviates significantly from the classic 80/20 Pareto principle that would typically predict only 10 clients driving that threshold.

Individual client contributions are notably thin, ranging from **4.1% at the highest** down to **1.7% at the 80% cumulative mark**, with minimal spread between them. This indicates that revenue is evenly distributed  across the observed client base, with no single dominant account.

Two strategic implications follow from this finding:

- The business is **not exposed to high concentration risk**: the loss of any single client would not critically impact overall revenue.
- There is **no quick win** from focusing exclusively on a handful of top accounts. Sustainable revenue growth must therefore come from **broad-based improvements across segments:** retaining top-tier clients, accelerating mid-tier development, and reducing churn exposure at the lower end.

<br>

### 3. RFM Segment Positioning

<br>
<p align="center">
  <img width="432" height="317" alt="Image" src="https://github.com/user-attachments/assets/23f4e43d-70e2-4324-aff0-31a4090962ab" />
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

**Insight:** Champions are the revenue backbone of the business, contributing 28.31% of total observed revenue ($14.10M). The primary priority is ensuring zero friction in the business relationship with this segment.

**Recommended Actions:**

- Establish a VIP loyalty program with exclusive benefits
- Offer early access to new products or priority purchasing programs
- Personalized premium offers to drive upsell and cross-sell
- Implement referral programs to leverage their business network

<br>

### **2. Loyal →**  *Increase Transaction Value & Elevate to Champions*

**Insight:** Loyal clients have proven their consistency. The focus is not retention — they are already retained — but increasing value per transaction.

**Recommended Actions:**

- Cross-selling strategy for complementary products based on purchase history
- Volume discount or bundling program to drive basket size increase
- Tiered loyalty program with thresholds that incentivize progression to Champions tier

<br>

### **3. Growing →**  *Accelerate Frequency & Basket Expansion*

**Insight:** Growing is the largest segment by client count (26%) yet its revenue share is below proportional (19.94%). This gap represents the largest growth opportunity heading into H2 2020, making it critical to leverage momentum and increase basket size.

**Recommended Actions:**

- Incentives for increased transaction value
- Mid-tier & premium product promotions
- Time-limited promotions to drive transaction frequency
- Cross-category exposure strategy

<br>

### **4. Potential →**  *Frequency Activation*

**Insight:** Potential clients show strong spending capacity but inconsistent purchase frequency. The objective is to convert sporadic purchases into a regular pattern.

**Recommended Actions:**

- Purchase reminders based on intervals between previous transactions
- Special offers for second and third orders to establish buying habits
- Segmented campaigns based on most frequently purchased product categories

<br>

### **5. At Risk →**  *Urgent Reactivation*

**Insight:** With an average revenue of ~$334K per client, losing even one At Risk client carries significant impact. The intervention window is narrow.

**Recommended Actions:**

- Direct and personal outreach to understand root cause of declining activity
- Time-limited win-back offers based on individual purchase history
- Brief survey to identify behavior shift

<br>

### **6. Low Value →**  *Cost Efficiency & Monitor Growth Signals*

**Insight:** Low Value clients collectively contribute $2.13M — not negligible, but insufficient to justify high-touch engagement. The approach must be cost-efficient.

**Recommended Actions:**

- Automated campaigns promoting entry-level and best-selling products
- Controlled promotional spending, prioritizing high-margin products
- Behavioral monitoring to detect clients showing growth signals

<br>

## Project Report
📄 PDF Report:
[B2B RFM Segmentation for H2 Revenue Optimization.pdf](b2b-rfm-segmentation-h2-revenue-optimization.pdf)






