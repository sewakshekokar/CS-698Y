# Student Dropout Prediction — Fairness & Bias
Generated on 2025-08-31.

## Files
- `student_dropout_fairness.ipynb` — full notebook with EDA, modeling, fairness metrics, and mitigations.
- `requirements.txt` — Python dependencies.
- `Dockerfile` — container to reproduce the environment.
- `metrics_comparison.csv` — saved summary table from the notebook after you run it.

## How to Use (VS Code)
1. Open the folder in VS Code.
2. Create a Python environment and install dependencies:
   ```bash
   pip install -r requirements.txt
   ```
3. Open `student_dropout_fairness.ipynb` and run the cells.

## How to Use (Docker)
```bash
docker build -t dropout-fairness .
docker run --rm -it -p 8888:8888 -v "$PWD":/app dropout-fairness \
    jupyter lab --ip=0.0.0.0 --no-browser --allow-root --NotebookApp.token=''
```

## Notes
- The notebook expects your dataset at `/mnt/data/data.csv` (this path is set in the loading cell). If running outside this environment, update the `csv_path` accordingly.
- Fairness metrics implemented: SPD (Statistical Parity Difference) and EOD (Equal Opportunity Difference).
- Mitigations: Drop sensitive attribute; Oversample unprivileged group.
