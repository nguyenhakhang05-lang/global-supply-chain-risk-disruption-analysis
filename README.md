# Global Supply Chain Risk & Disruption Analysis

Supply chain analytics case study using Python and machine learning to identify shipment disruption risk and forecast shipment lead times across 5,000 simulated global shipments.

## Business Problem

How can a global logistics company identify high-risk shipment conditions, anticipate disruptions, and improve lead-time planning?

The project addresses two questions:

1. Which factors are most strongly associated with shipment disruption?
2. Can shipment lead time be predicted accurately enough to support operational planning?

## Dataset

- 5,000 simulated shipments
- Period: 2024–2025
- 4 transport modes
- 5 weather conditions
- Classification target: `Disruption_Occurred`
- Regression target: `Lead_Time_Days`
- No missing values or duplicate shipment IDs

## Key Findings

- Overall disruption rate: **61.26%**
- Storm conditions were associated with a **79.54% disruption rate**
- Storm + highest geopolitical-risk quartile reached **95.9% disruption**
- Transport Mode, Weather, and Distance were the main lead-time drivers
- Disruption and lead-time performance were driven by different combinations of factors
- Extreme shipment delays remained more difficult to forecast accurately

## Predictive Models

### Disruption Classification

| Model | Test ROC-AUC | Recall | F1 | CV ROC-AUC |
|---|---:|---:|---:|---:|
| Logistic Regression | 0.828 | 0.801 | 0.791 | 0.826 |
| Random Forest | 0.812 | 0.780 | 0.776 | 0.819 |
| Regularized Random Forest | 0.821 | 0.791 | 0.781 | 0.824 |

**Selected model:** Logistic Regression

### Lead-Time Forecasting

| Model | MAE | RMSE | R² |
|---|---:|---:|---:|
| Median Baseline | 15.445 | 31.730 | -0.115 |
| Raw Linear Regression | 12.067 | 18.669 | 0.614 |
| Log Linear Regression | 3.986 | 8.774 | 0.915 |
| Log Linear + Smearing | 3.603 | 7.579 | 0.936 |
| Random Forest Regressor | 4.083 | 8.486 | 0.920 |

**Selected model:** Log-Linear Regression with Duan's Smearing Correction

## Business Recommendations

- Combine weather and geopolitical risk into a shipment risk-escalation framework
- Incorporate transport mode, distance, and weather into dynamic ETA planning
- Prioritize stronger carriers for high-risk shipments where operationally feasible
- Apply additional review and planning buffers to potential extreme-delay shipments
- Use routes as investigation segments rather than assuming route-level causality

## Tools

- Python
- Pandas
- NumPy
- Matplotlib
- Scikit-learn
- Statsmodels
- Power BI

## Project Files

- `notebooks/` – Complete Python analysis
- `images/` – Main project visualizations
- `dashboard/` – Power BI dashboard information
- `data/` – Dataset documentation

## Links

- **Full Case Study:** [Notion link]
- **Interactive Dashboard:** [Power BI link]
- **Kaggle Notebook:** [Kaggle link]

## Limitations

- The dataset is synthetic
- Actual records cover 2024–2025 despite the dataset filename
- Hurricane observations show a deterministic 100% disruption pattern
- Cost variables are unavailable
- Extreme lead times remain systematically underestimated
- Results represent predictive associations rather than causal effects

## Author

**Nguyen Ha Khang**

International Economics student with an interest in Supply Chain Data Analytics.

[LinkedIn] | [Portfolio]
