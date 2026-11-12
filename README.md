# 🏦 Customer Churn Analysis

## Project Overview
- An end-to-end descriptive, diagnostic and predictive analysis of customer attrition to identify key churn drivers, high-risk customer segments, and actionable retention strategies.
**10,000 European retail banking customers** across France, Germany, and Spain (`$764.9M` initial asset base; `$579.7M` current remaining assets), uncovering the structural drivers behind deposit concentration, customer complaints, and churn risk.

---

## 📊 Executive Summary & Key Metrics

| Metric | France | Germany | Spain | Total / Portfolio |
| :--- | :---: | :---: | :---: | :---: |
| **Customer Base** | 5,014 (50.1%) | 2,509 (25.1%) | 2,477 (24.8%) | **10,000 (100%)** |
| **Share of Total Assets** | 40.7% (`$311.3M`) | 39.3% (`$300.4M`) | 20.0% (`$153.1M`) | **`$764.9M`** |
| **Average Account Balance** | `$62,093` | **`$119,730`** | `$61,818` | `$76,486` |
| **Balance Volatility (CV)** | 103% (High) | **23% (Highly Stable)** | 104% (High) | — |
| **Total Asset Loss from Churn** | `$57.6M` (19%) | **`$97.8M` (33%)** | `$29.7M` (19%) | **`$185.2M` (24.2%)** |
| **Current Remaining Assets** | `$253.7M` | `$202.6M` | `$123.4M` | **`$579.7M`** |

---

## 🔍 Core Analytical Insights

### 1. Germany is the Bank’s High-Value, Low-Volatility Anchor
* **Outsized Capital Concentration:** Despite representing only **25% of customers**, Germany holds **39% of total assets**, with an average balance (`$119.7K`) nearly **double** that of France and Spain (`~$62K`).
* **Income-Independent Wealth:** Unlike France and Spain—which contain high volumes of `$0`-balance transactional accounts—Germany maintains a minimum deposit floor of **`$27.2K`**. Even among German clients earning under `$1K`, **0%** hold balances below `$10K`, proving Germany is a heavily capitalized wealth segment rather than a transactional pool.
* **Tight Distribution:** Germany’s **23% Coefficient of Variation (CV)** and `$27K` standard deviation indicate that ~68% of German accounts consistently sit between `$93K` and `$147K`, whereas France and Spain exceed `100%` CV.

### 2. Satisfaction Scores Mask Underlying Churn Risk
* **The Satisfaction Illusion:** Correlation analysis shows **no meaningful relationship** between `Satisfaction Score` and `Tenure` or attrition—meaning passive survey scores fail to capture deep relationship decay.
* **Tenure Vulnerability:** While **Medium-Tenure clients (4–7 years)** hold the largest share of assets across all markets, **High-Tenure clients (8–10 years)** in France and Germany exhibit acute retention vulnerability. Analytical tracking must shift from passive satisfaction surveys to **real-time complaint diagnostics**.

### 3. Inactivity + Complaints = Severe Balance Sheet Exposure
* **Dormant Account Sensitivity:** **30%–40%** of the customer base is inactive and highly sensitive to operational friction. When inactive accounts experience service failures, baseline churn spikes to **30%**.
* **Regional Risk Exposure:**
  * **Germany (Highest Capital Risk):** Accounted for **53% (`$62.1M`)** of all inactive churn losses and **33% (`$97.8M`)** of total asset attrition. When a German client logs a complaint, exit probability surges to **~60%**.
  * **Spain (Highest Active Volatility):** High-tenure inactive clients show a **38% complaint rate** driving a **24% attrition rate**, while medium-tenure active complainants show a **47% churn rate**—putting **13% (`$15.9M`)** of Spain's remaining balance at immediate risk.

### 4. VIP Concentration & Capital Drain
* **Historical Loss:** Attrition among historical Top-10 VIP clients in France (`5 exited`) and Spain (`8 exited`) has already drained **`~$2.8M–$4.0M`** in high-value capital.
* **Immediate Exposure:** The remaining VIP cohort holds **`~$3.5M`** in concentrated deposits (including all **10/10** original German VIPs still retained at `$2.02M`). Defection of this remaining tier would wipe out nearly **1%** of the bank's `$580M` remaining asset base.

---

## 🎯 Strategic Recommendations

1. **Deploy Universal Complaint-to-Retention SLAs:** Treat every logged complaint—especially from German accounts and inactive users—as a high-probability churn trigger requiring immediate intervention.
2. **Re-Engage Dormant Capital:** Launch targeted reactivation campaigns for inactive customers with balances >`$50K` before service friction occurs.
3. **Establish Dedicated VIP Relationship Management:** Assign white-glove retention protocols to the remaining Top-10 VIP accounts per region (especially Germany's 10 retained VIPs and Spain's remaining 2) to prevent further high-value capital flight.

---



## 🛠️ Methodology & Workbook Structure
* **Tools:** Microsoft Excel (`COUNTIFS`, `MEDIAN/STDEV.S + FILTER`, `COVARIANCE.S`, `CORREL`, One-Hot Encoding, Pivot Cross-Tabulations)
* **Workbook Architecture:**
  * `Bank-Customer-Attrition-Insight`: Cleaned dataset (`N = 10,000`) with engineered age brackets and regional indicator columns.
  * `1_Overall` & `2_GroupStats`: Univariate and geography-segmented central tendency and dispersion metrics.
  * `3_Relationships`: Covariance and correlation matrices across numeric and encoded variables.
  * `4_Patterns` & `5_Findings`: Multi-dimensional cross-tabulations on tenure, activity status, complaints, and balance risk.
  * `6_Report`: Executive synthesis and VIP watchlist.
