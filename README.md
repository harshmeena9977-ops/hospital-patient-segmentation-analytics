# Hospital Segmentation Study: Patient Segmentation Using Healthcare Utilization, Billing, and Admission Data

## 📋 Project Overview
This project addresses a critical operational challenge for a network of community clinics and hospitals in Hyderabad, which historically treated all patients, departments, and doctors uniformly. By leveraging an extensive anonymized healthcare dataset (**~500,000 rows across 33 relational tables**), this study transitions the network from a blanket operational model to a targeted, data-driven strategy to optimize resource allocation, patient retention, and revenue streams.

---

## 🛠️ Data Engineering & Preprocessing
Working with real-world-style healthcare records required rigorous data pipeline construction:
* **Relational Integration:** Programmatically loaded and validated 33 CSV tables, ensuring referential integrity across primary and foreign keys (appointments, inpatient admissions, lab tests, billing records).
* **Data Cleaning:** Handled free-text medical diagnoses, normalized age entries provided as dates of birth, and corrected billing anomalies where GST was counted twice.
* **Feature Engineering:** Synthesized multidimensional patient-level behavioral metrics:
  * **Recency (`recency_days`):** Engagement timing relative to the analysis baseline.
  * **Frequency (`visit_frequency`):** Total historical appointment and visit volume.
  * **Monetary Value (`total_revenue`):** Cumulative paid revenue generated.
  * **Clinical Metrics:** Average length of stay (`avg_los`), bed occupancy impact, and 30-day readmission tendency.
* **Transformation & Scaling:** Applied logarithmic transformations ($\log(1+x)$) to manage heavy financial/utilization skewness, followed by feature standardization using `StandardScaler`.

---

## 🤖 Modeling & Segmentation Methodology
1. **Cluster Optimization:** Evaluated optimal cluster counts ($K$) using the **Elbow Method** (inertia reduction) and **Silhouette Analysis** (cohesion and separation).
2. **Comparative Modeling:** Evaluated traditional RFM-style scoring against unsupervised **K-Means clustering** on scaled features, ultimately selecting K-Means for capturing complex multi-variable clinical behaviors.
3. **Profiling:** Profiled each segment by population size, revenue/volume share, average length of stay, bed occupancy, and readmission risk, assigning intuitive business-friendly names.
4. **Stability Analysis (Stretch Requirement):** Re-ran segmentation across multiple historical time periods to measure entity migration and ensure strategic reliability.

---

## 📂 Repository Structure
```text
hospital-patient-segmentation-analytics/
├── data/
│   ├── raw/                 # Original anonymized CSV files (33 relational tables)
│   └── processed/           # Cleaned and feature-engineered datasets (`cleaned_patient_dataset.csv`)
├── notebooks/
│   └── analysis.ipynb       # End-to-end Jupyter Notebook pipeline
├── reports/
│   ├── project_report.docx  # Final project report Word document submission
│   └── segment_profiles.csv # Summary table of segment metrics and sizes
├── presentation/
│   ├── executive_slides.pdf # Short presentation for the business head
│   └── images/              # Visualizations and screenshots (Elbow, Silhouette, Clusters, Migration)
├── .gitignore               # Excludes large files, cache, and checkpoints
├── requirements.txt         # Python dependencies
└── README.md                # Project documentation