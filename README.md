
---

## 📈 Key Insights

- Vehicles cluster into 3 distinct value bands:
  - **Luxury, low-mileage**, priced above $150K
  - **Mainstream**, ~10–300K km, prices between $5K–$70K
  - **Floor-priced salvage stock**, typically $1,500 with extreme mileage

- **Year**, **odometer**, and **vehicle type** explain most price variability  
- Features like **region**, **state**, **model**, and **paint color** were explored visually but dropped for modeling due to noise or complexity  
- Created engineered features like:
  - `log1p(odometer)`
  - `region_price_residual` (to capture geographic value distortions)
  - Optional price segment flags for future interaction modeling

---

## 🔍 Modeling Highlights

- **Target**: `log1p(price)` for skew normalization  
- **Core features retained**: age, mileage, type, transmission, drive, condition  
- **Dropped features**: manufacturer, model, VIN, region (raw), color, due to high noise or low added value  
- Built with **modular preprocessing** using `ColumnTransformer` and `Pipeline`

Model error on the test set: **< less than 1 >**

---

## 📦 Repository Structure
📦 vehicle-price-insights/
├── data/
│   └── vehicle_listings.csv             # Main cleaned dataset
├── notebook/
│   └── vehicle_price_analysis.ipynb     # Core analysis + modeling
├── images/
│   └── [Place any charts or diagrams here]
└── README.md                            # Executive summary + insights


## 🛤️ Future Enhancements

| Opportunity | Description |
|-------------|-------------|
| Cluster-based personas | Segment inventory via K-Means-like grouping |
| Brand-score engineering | Add tiered brand reputation metrics |
| Usage-adjusted price modeling | e.g., `km_per_year`, polynomial wear effects |
| Outlier-aware pipelines | Better isolate showroom and salvage anomalies |
| Geo-based reintroduction | Aggregate regions/states for regulatory or supply chain insights |

---

## 📎 Author Notes

This project was built to align technical rigor with business explainability. It provides a flexible structure for extending into deeper market segmentation, listing optimization, and customer-facing valuation tools.

For contributions, feedback, or integration discussions, feel free to fork or raise an issue.

---
