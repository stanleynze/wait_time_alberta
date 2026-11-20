# Waiting on Alberta
**Benchmarking Alberta's Wait Times for Priority Procedures Against Canada, 2016 to 2025**

> This is an independent student capstone project (PROJ 406 Data Analytics Capstone Project).
> It is not affiliated with or endorsed by the Alberta Ministry of Hospital and Surgical Health
> Services, the Canadian Institute for Health Information (CIHI) or Statistics Canada.

## Overview
The project measures how quickly Alberta treats patients for five priority procedures (hip
replacement, knee replacement, cataract surgery, radiation therapy and hip fracture repair),
using Canada as the benchmark and the other nine provinces as comparison cases. It follows the
CRISP-DM process, uses Python for data preparation and modeling, and presents the results in a
Power BI dashboard built on a star schema.

## Business questions and results
| # | Question | Model | Key result |
|---|---|---|---|
| Q1 | How much do capacity and ageing explain long waits? | Multiple linear regression | R² 0.51; Alberta waits 22.8 days longer than expected (cataract +46.2) |
| Q2 | Can we predict whether a province meets or beats Canada? | K-Nearest Neighbors (K = 1) | Accuracy 74.8% vs 55.3% baseline; precision 0.76, recall 0.64 |
| Q3 | Which provinces share a similar access and ageing profile? | K-Means (2 groups) | Alberta groups with MB, SK and PE; silhouette 0.27 (target 0.30 not met) |

**Main finding:** Alberta treated 72.5% of patients within the benchmark, against 75.6% for
Canada. The gap is in elective surgery (cataract −10.8 points), while Alberta does better than
Canada on urgent care.

## Repository structure
| Folder | Contents |
|---|---|
| `raw_data/` | Source files from CIHI and Statistics Canada |
| `notebook/` | Data_Preparation, Modeling and Clustering_Comparison notebooks |
| `cleaned/` | Cleaned model data and star schema tables (CSV) |
| `powerbi/` | Power BI report (`wait_time_alberta.pbix`) |
| `docs/` | CRISP-DM report, executive summary, data dictionary and slides |

## How to run
1. Install Python 3 and the packages: `pip install -r requirements.txt`
2. Open the notebooks in the `notebook/` folder and run them in order:
   `Data_Preparation.ipynb` → `Modeling.ipynb` → `Clustering_Comparison.ipynb`
3. Open `powerbi/wait_time_alberta.pbix` in Power BI Desktop and refresh the data
   (update the file paths to your `cleaned/` folder if prompted).

## Data sources
- Canadian Institute for Health Information. (2026). *Wait times for priority procedures in
  Canada, 2008–2025: Data tables.* https://www.cihi.ca/en/explore-wait-times-for-priority-procedures-across-canada
  Used for non-commercial educational purposes with acknowledgement of CIHI as the source.
- Statistics Canada. (2026). *Table 17-10-0005-01 Population estimates on July 1, by age and
  gender.* https://doi.org/10.25318/1710000501-eng
  Contains information licensed under the Statistics Canada Open Licence.

## Tools
Python (pandas, NumPy, matplotlib, seaborn, scikit-learn) in VS Code; Power BI Desktop.

## Team
- Stanley Nze, Project Lead
- Edson Neto, Project Manager

Instructor: Moulya Pradeep