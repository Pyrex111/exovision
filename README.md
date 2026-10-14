# Exovision

Exovision is a team project built by **Stellar Detectives** during the **NASA International Space Apps Challenge at the University of Victoria (UVic), October 2025**. It explores machine learning for exoplanet classification using Kepler Objects of Interest (KOI), K2, and TESS datasets.

**Award: Stellar Detectives won the Rising Stars category at the UVic hackathon.**

- [Live demo](https://exovision-spaceapps.vercel.app/)
- [Challenge: A World Away — Hunting for Exoplanets with AI](https://www.spaceappschallenge.org/2025/challenges/a-world-away-hunting-for-exoplanets-with-ai/)

## Team and contributions

Exovision was a collaborative hackathon project. The Stellar Detectives team combined machine learning research with application development, interface design, and data visualization.

| Team member | Contribution |
| --- | --- |
| **Taimoor Shahzad** | Machine learning research and development, mission-specific classification workflows, and project design. |
| **Saad Khan** | Full-stack development. |
| **Abdullah Shah** | Full-stack development. |
| **Muhammad Samad Mahar** | UI/UX design and data visualization. |

The team's main roles are shown on the final slide of the [Exovision pitch presentation](<Traversing Cosmic Objects and Distances in Collaboration With NASA.pdf>). This repository contains the ML notebooks, datasets, and presentation materials; the [live demo](https://exovision-spaceapps.vercel.app/) presents the team's web application.

## Repository contents

| File | Purpose |
| --- | --- |
| `NASA_KOI_DATASET.ipynb` | Logistic regression with scaler comparison, cross-validation, held-out evaluation, and SHAP analysis. |
| `NASA_K2_DATASET.ipynb` | Random forest classification with uncertainty features and missing-data handling. |
| `NASA_TESS_DATSASET.ipynb` | Histogram gradient boosting classification and class-distribution summaries. The original filename is retained. |
| `koifilterednoflags.xlsx` | KOI dataset supplied with the project. |
| `k2pandc.csv` | K2 dataset export. |
| `tessdataset.csv` | TESS dataset export. |
| `Challenge & Live Vercel Link.txt` | Original challenge and demo links. |
| `Traversing Cosmic Objects and Distances in Collaboration With NASA.pdf` | Exovision pitch presentation in PDF format, including the Stellar Detectives team roles. The original filename is retained. |
| `Traversing Cosmic Objects and Distances in Collaboration With NASA Lesson 1 - Stars and Their Fates (Student Version).pptx` | Editable PowerPoint version of the Exovision pitch presentation. The original filename is retained. |

The supplied folder contains notebooks, datasets, and reference materials. The source code for the deployed web application and trained model artifacts were not included in that folder.

## Running the notebooks

These notebooks were written for Google Colab and mount Google Drive. Open a notebook in Colab, upload its dataset to Drive, and update its configured path to match your upload:

| Notebook | Configuration variable | Included dataset |
| --- | --- | --- |
| KOI | `xlsx_path` | `koifilterednoflags.xlsx` (the notebook originally refers to `koifiltered.xlsx`) |
| K2 | `csv_path` | `k2pandc.csv` |
| TESS | `csv_path` | `tessdataset.csv` |

Install the packages used by the notebooks in a Colab cell:

```python
%pip install numpy pandas scipy scikit-learn joblib openpyxl matplotlib shap
```

The CSV exports include metadata lines beginning with `#`. The K2 notebook detects its header automatically. For the supplied TESS export, update the loading line to skip those metadata comments:

```python
df = pd.read_csv(csv_path, comment="#")
```

Run cells in order. The notebooks train models, report evaluation results, and write model artifacts to the Colab runtime. K2 and TESS both write `feature_names.json`; use separate runtime sessions or output folders to keep their artifacts distinct.

The original notebooks and data are preserved as supplied. Saved notebook outputs reflect earlier runs; they have not been regenerated for this publication.

## Data and reference attribution

The K2 and TESS CSV headers identify the [NASA Exoplanet Archive](https://exoplanetarchive.ipac.caltech.edu/) as their source. The included PDF and PowerPoint are the team's Exovision pitch presentation, preserved as supplied with their original filenames and contents.
