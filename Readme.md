# Student Academic Profile: Campus Placement Analysis using Python

**Course:** Fundamentals of Data Science (Semester Project)
**Submitted by:** Aanya (590026676), Gaurangi (590026692) · Batch 01
**Submitted to:** Mr. Virender Kadayan Sir

## Overview

This project studies how academic performance, aptitude and technical skills relate to campus placement outcomes. A deliberately messy **mock (synthetic)** dataset is inspected, cleaned, summarised, visualised and analysed with basic statistical tests and simple models.

> The dataset contains no real student records. It is inspired by the IEEE DataPort dataset
> *Student Placement Prediction and Career Readiness Dataset for Personalized Career Guidance*.
> All findings apply only to this mock data.

## Dataset

- File: `mock_placement_raw.csv`
- Raw size: 212 rows × 26 columns (200 unique students after removing duplicate IDs)
- Data quality issues practised: duplicate IDs, inconsistent spellings, mixed Yes/No formats, numbers stored as text, placeholders (`NA`, `?`, `null`, `TBD`), impossible values

## What the project does

1. Loads and inspects the CSV
2. Detects missing values, duplicates and inconsistent entries
3. Cleans the data (spaces, placeholders, duplicates, labels, CGPA formats, invalid ranges)
4. Computes descriptive statistics, probabilities and a frequency distribution
5. Compares placement across branches
6. Visualises distributions and relationships
7. Calculates covariance and Pearson correlation
8. Runs a Welch's t-test (CGPA vs placement status)
9. Runs a chi-square test of independence (branch vs placement)
10. Fits a logistic regression (CGPA → placement)
11. Fits a simple linear regression (CGPA → package)

## Key findings

- About **52%** of the 200 students are placed.
- Mean CGPA is 7.58 (SD 0.88); the distribution is roughly symmetric.
- Placed students have a **significantly higher CGPA** than not-placed students (t = 2.439, p = 0.0157).
- **Branch is not significantly associated** with placement (χ² = 3.632, p = 0.726).
- CGPA and aptitude score are weakly positively correlated (r = 0.266).
- Logistic regression on CGPA alone reaches **55.3%** test accuracy, so CGPA is a weak predictor.
- CGPA explains only **0.6%** of the variation in package; company type matters far more.

## Project structure

```
.
├── mock_placement_raw.csv                 # raw mock dataset
├── Student_Academic_Profile_Home.ipynb    # analysis notebook (HTML export also included)
├── report/
│   ├── main.tex                           # LaTeX project report
│   └── images/                            # figures used in the report
├── requirements.txt
└── README.md
```

Adjust the file names above to match your repository.

## How to run

1. Clone the repository:
   ```bash
   git clone <your-repo-url>
   cd <your-repo-folder>
   ```
2. Install the dependencies:
   ```bash
   pip install -r requirements.txt
   ```
3. Open the notebook and run all cells:
   ```bash
   jupyter notebook
   ```

### Building the report

Upload the `report/` folder (with `images/`) to [Overleaf](https://www.overleaf.com) and compile `main.tex`, or run locally:

```bash
cd report
pdflatex main.tex
pdflatex main.tex   # run twice for the table of contents
```

## Tools and libraries

Python, Pandas, NumPy, Matplotlib, Seaborn, Scikit-learn, SciPy, Jupyter, LaTeX.

## Limitations

- Mock data may not represent real placement conditions; do not generalise to any real college or employer.
- Some records stay missing or inconsistent after cleaning.
- Unequal branch sizes and small expected counts affect the chi-square test.
- Correlation does not imply causation.
- Models use a single predictor and must not be used for real student selection or salary decisions.

## References

- IEEE DataPort: https://ieee-dataport.org/documents/student-placement-prediction-and-career-readiness-dataset-personalized-career-guidance
- pandas: https://pandas.pydata.org/docs/
- NumPy: https://numpy.org/doc/
- Scikit-learn: https://scikit-learn.org/stable/
- Matplotlib: https://matplotlib.org/stable/
- seaborn: https://seaborn.pydata.org/
