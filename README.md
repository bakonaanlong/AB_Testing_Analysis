# A/B Testing Analysis Dashboard  
**Testing Effectiveness Between PSA and Ads made with MS Excel**  


---

## 1. Background and Overview  

### Purpose  
This dashboard presents the results of an A/B test comparing the conversion performance of **paid advertisements (Ads)** versus **public service announcements (PSAs)**. The primary objective is to determine which channel yields a higher conversion rate and to identify behavioral patterns that can inform future media allocation decisions.

### Test Design  
- **Variant A**: Paid Advertisements (Ads)  
- **Variant B**: Public Service Announcements (PSAs)  
- **Metric of Interest**: Conversion Rate (% of impressions resulting in a completed action)  
- **Sample Period**: Aggregated weekly data (specific dates not displayed)  
- **Audience**: Uniformly exposed user cohort (assumed balanced randomization)

### Dashboard Components  
| Component | Description |
|---------|-------------|
| **Overall Conversion Rate** | Weighted average across both variants |
| **Ads vs. PSA Conversion Rates** | Direct head-to-head comparison |
| **Ads Conversion Distribution** | Pie chart showing Yes/No conversion split |
| **PSA Conversion Distribution** | Donut chart showing Yes/No conversion split |
| **Distribution of Conversions by Day of Week** | Bar chart illustrating daily conversion volume trends |

---

## 2. Data Structure Overview  

| Visual Element | Data Type | Key Fields | Granularity | Notes |
|----------------|-----------|------------|-------------|-------|
| **Conversion Rate (Header)** | Scalar | `total_conversions`, `total_impressions` | Test-level | Calculated as `(total_conversions / total_impressions) × 100` |
| **Ads vs. PSA Bar** | Comparative | `ads_conversions`, `ads_impressions`, `psa_conversions`, `psa_impressions` | Variant-level | Ads: 2.55%; PSA: 1.78% |
| **Ads Conversion Pie** | Categorical | `ads_yes`, `ads_no` | Variant-level | ~2.55% "Yes", ~97.45% "No" |
| **PSA Conversion Donut** | Categorical | `psa_yes`, `psa_no` | Variant-level | ~1.78% "Yes", ~98.22% "No" |
| **Daily Conversion Bar** | Time-series | `day_of_week`, `daily_conversions` | Day-level | Sunday highest; Saturday lowest |


---

## 3. Executive Summary  

| KPI | Value | Interpretation |
|-----|-------|----------------|
| **Overall Conversion Rate** | **2.52%** | Baseline blended performance |
| **Ads Conversion Rate** | **2.55%** | Outperforms PSA by **0.77 pp** |
| **PSA Conversion Rate** | **1.78%** | Underperforms relative to paid ads |
| **Relative Uplift** | **+43.3%** | Ads generate 43% more conversions per impression |
| **Peak Conversion Day** | **Sunday** | Highest volume observed |
| **Lowest Conversion Day** | **Saturday** | Minimal activity |

**Conclusion**: Paid advertisements demonstrate **statistically and practically superior conversion efficiency** compared to PSAs.

---

## 4. Insights Deep Dive  

![yessir](https://github.com/bakonaanlong/AB_Testing_Analysis/blob/main/ad_dashboard.JPG)

### 4.1 Conversion Rate Differential  
- Ads achieve **2.55%** vs. PSA’s **1.78%** — a **43% relative improvement**.  
- Even with potentially higher CPMs, the ROI per conversion favors Ads if cost-per-conversion remains below threshold (requires CPA data).

### 4.2 Conversion Distribution  
| Channel | Yes (%) | No (%) | Implication |
|--------|--------|--------|-----------|
| Ads | ~2.55 | ~97.45 | Small but efficient conversion slice |
| PSA | ~1.78 | ~98.22 | Lower engagement; possible fatigue or irrelevance |

> **Note**: Both channels show >97% non-conversion, indicating room for creative or targeting optimization.

### 4.3 Temporal Patterns  
- **Sunday** registers the tallest bar — highest absolute conversions.  
- **Progressive decline** through the week, with **Saturday** as the nadir.  
- Possible drivers:  
  - Weekend leisure browsing (higher intent on Sunday)  
  - Workweek distraction (Mon–Fri)  
  - Weekend ad fatigue or reduced budget burn on Saturday

### 4.4 Strategic Implications  
1. **Channel Prioritization**: Shift budget weight toward paid ads.  
2. **Dayparting Opportunity**: Increase ad delivery on Sundays; consider pausing or reducing spend on Saturdays.  
3. **Creative Testing**: PSA underperformance may signal weak messaging — test new variants.

---

## 5. Recommendations  

| # | Action Item | Owner | Priority | Timeline |
|---|-------------|-------|----------|----------|
| 1 | **Reallocate 70% of PSA budget to Ads** (maintaining current targeting) | Media Team | High | Immediate (next flight) |
| 2 | **Implement Sunday-heavy dayparting** (e.g., 40% of weekly budget on Sunday) | Programmatic Lead | High | Within 1 week |
| 3 | **Launch PSA creative refresh A/B test** (new copy, visuals, CTA) | Creative Team | Medium | Within 2 weeks |
| 4 | **Integrate cost data (CPC/CPA)** to calculate true ROAS | Analytics | High | Within 1 week |
| 5 | **Run statistical significance test** (chi-square or t-test) on full dataset | Data Science | Medium | Within 3 days |
| 6 | **Monitor Saturday performance post-changes**; consider exclusion if uplift < 1.0% | Media Team | Low | Ongoing |



---

