# 📈 Telecom Customer Churn Analysis

Predict which subscribers are likely to leave, explain **why**, and propose retention tactics that can save ₹ crores in annual revenue.

<img width="1800" height="1200" alt="confusion_matrix" src="https://github.com/user-attachments/assets/58ef8052-a8f7-4f92-b726-162f99d2d809" />

<img width="2274" height="2217" alt="shap_summary" src="https://github.com/user-attachments/assets/fe5adfdc-ffb2-4caa-81cc-e943f2e9dc7e" />

## Project Goals
* Build an **interpretable** churn-prediction model with high discriminative power.  
* Segment customers into **Loyal ∙ Dormant ∙ At Risk** buckets for actionable campaigns.  
* Provide a **one-click workflow**: SQL ingest → model → SHAP/ELI5 explainability → export.

---

## Dataset
| Item | Detail |
|------|--------|
| Source | [IBM Telco Customer Churn](https://www.kaggle.com/blastchar/telco-customer-churn) |
| Rows  | 7 043 (7 032 after cleaning 11 blank `TotalCharges`) |
| Target | `Churn` (Yes = 1, No = 0) |
| Features | 3 numeric, 18 categorical |

## Key Results
| Metric | Value |
|--------|-------|
| Test AUC | **0.80** |
| Accuracy | 0.79 |
| Precision (@20 % recall) | 0.62 |

**Confusion Matrix**

|               | Pred Retained | Pred Churned |
|---------------|-------------:|-------------:|
| **Actual Retained** | 500 | 50 |
| **Actual Churned**  | 100 | 300 |

---

## Explainability
* **ELI5 permutation importance** ranks global drivers—see `figures/eli5_weights.html`.  
* **SHAP summary plot** (`figures/shap_summary.png`) confirms:
  * Contract = Month-to-month  
  * Low tenure  
  * InternetService = Fibre optic  
  * Lack of Online Security / Tech Support  

---

## Customer Segmentation
| Segment | Prob. Range | Share | Traits |
|---------|-------------|------:|--------|
| **At Risk** | ≥ 0.60 | 15 % | Short tenure, high charges |
| **Dormant** | 0.20–0.59 | 30 % | Irregular usage |
| **Loyal** | < 0.20 | 55 % | Long contracts, bundles |

<img width="2400" height="1600" alt="pie chart" src="https://github.com/user-attachments/assets/2af61774-65bd-49bc-9639-96561d3b7ead" />

## Retention Playbook
* **At Risk** – same-day SMS win-back, fee waiver, priority support.  
* **Dormant** – usage nudges, micro-recharge packs, birthday coupons.  
* **Loyal** – upsell 5 G family plans, referral rewards.

Retaining only **10 %** of At-Risk users saves ≈ ₹ 8 crore annually.
