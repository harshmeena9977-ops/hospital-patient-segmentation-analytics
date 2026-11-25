# Hospital Patient Segmentation — Internship Task Project

This repository contains my Yuvaintern internship task project: an exploratory analysis of healthcare-style utilization, billing, and admission data. It demonstrates a notebook-based segmentation exercise; it is not a study commissioned by a Hyderabad hospital network, a deployed clinical system, or evidence of patient or business outcomes.

## Project artifacts

- [Open the analysis notebook](notebooks/analysis.ipynb.ipynb)
- [View the project report](reports/project_report.docx)
- [View the presentation deck](presentation/Hospital%20Segmentation%20Study%20-%20Comprehensive%20Executive%20Deck.pptx)
- [View the Elbow plot](presentation/01_elbow_method.png)
- [View the silhouette plot](presentation/02_silhouette_scores.png)
- [View the cluster visualization](presentation/03_segment_clusters.png)
- [View the processed patient dataset](data/processed/cleaned_data.csv)
- [View the segment summary CSV](reports/segment_profiles.csv)
- [Review the Python dependencies](requirements.txt)

## What the notebook explores

The notebook loads multiple CSV tables, creates patient-level utilization and billing features, and includes an exploratory K-Means segmentation with saved cluster summaries and visualizations. The notebook also contains saved output from a readmission calculation. These outputs are exploratory and have not been independently validated against an external source or clinical standard.

## Evidence and limitations

The repository includes raw CSV tables under data/raw/hospital_100k and a processed CSV at data/processed/cleaned_data.csv. The dataset publisher, generation method, license, and whether the records are synthetic or anonymized are not documented. The project should therefore be described as using healthcare-style data, not verified real hospital or patient records. The project files do not establish a real hospital client or deployment.

There is an unresolved output mismatch: the notebook reports a five-cluster result, while reports/segment_profiles.csv contains four named segments. Reconcile the segment labels, definitions, and metrics before presenting the CSV, report, or slides as a single validated result. Numerical findings and operational recommendations are not included here until that reconciliation is complete.

The notebook currently points to a machine-specific Windows folder (D:\Healthcare-Segmentation\data\raw\hospital_100k). A clean clone will not use that path automatically. Update the notebook to use the repository-relative data/raw/hospital_100k folder before attempting a fresh run. The requirements file lists analysis libraries but does not include Jupyter itself, and no end-to-end run guide is provided.

## Repository layout

- data/raw/hospital_100k/ — raw healthcare-style CSV tables.
- data/processed/cleaned_data.csv — processed dataset.
- notebooks/analysis.ipynb.ipynb — analysis notebook; note the duplicated .ipynb extension in the filename.
- reports/ — project report and segment summary CSV.
- presentation/ — three PNG plots and a PowerPoint deck. No executive_slides.pdf or presentation/images/ folder is present.
- requirements.txt — Python analysis dependencies.

## Local setup status

The notebook is available to review on GitHub. To reproduce it locally, clone the repository, create and activate a Python virtual environment, install requirements.txt, install or open a Jupyter environment, and update the notebook data path to the local repository folder. A fresh, clean run has not been verified, so saved outputs should be treated as notebook artifacts rather than a reproducible release.

This README update documents the current files and known gaps. It does not change the analysis, dataset, reports, or presentation.
