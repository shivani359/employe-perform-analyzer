# Employee Performance Predictor

An educational Python/Streamlit portfolio project that uses fictional employee-cycle data to demonstrate model training, evaluation, explainability, and aggregate fairness diagnostics.

## Run & Operate

- `cd employee-performance-predictor && python main.py` — generate synthetic data, train/evaluate models, and save local outputs
- `cd employee-performance-predictor && python -m streamlit run app.py --server.port 5000 --server.address 0.0.0.0` — run the dashboard
- `cd employee-performance-predictor && python -m unittest discover -s tests -v` — run project sanity tests
- Python dependencies are listed in `employee-performance-predictor/requirements.txt`
- No secrets or external services are required

## Stack

- Python, NumPy, Pandas, scikit-learn, Streamlit, Matplotlib, Joblib
- The pnpm workspace and shared API-server scaffold remain in the starter environment; this project does not depend on them

## Where things live

- `employee-performance-predictor/src/data.py` — synthetic data generator and feature lists
- `employee-performance-predictor/src/modeling.py` — preprocessing, model comparison, and evaluation
- `employee-performance-predictor/src/fairness.py` — aggregate group diagnostics
- `employee-performance-predictor/src/recommendations.py` — supportive coaching prompts
- `employee-performance-predictor/app.py` — interactive dashboard
- `employee-performance-predictor/main.py` — reproducible CLI run and outputs
- `employee-performance-predictor/docs/PROJECT_GUIDE.md` — phases, setup, GitHub, interviews, and limitations

## Architecture decisions

- Synthetic data only; generated labels demonstrate a workflow and do not validate real-world HR prediction.
- Gender is audit-only and excluded from model features; IDs and the target-generation signal are also excluded.
- Preprocessing stays in scikit-learn pipelines so transformations are learned from training folds.
- Holdout metrics, permutation importance, and group-rate summaries are limited diagnostics.
- Predictions are framed as coaching prompts, never automated personnel decisions.

## Product

Students can explore synthetic data, compare classifiers, inspect evaluation and aggregate audits, try a fictional coaching scenario, and generate reproducible charts and metrics for a portfolio.

## User preferences

- The project is intended as student portfolio proof for placements and internships.
- Use public or synthetic data and virtual simulation; no real company HR data is available.

## Gotchas

- The dashboard trains the demo model in memory on first load and does not require a saved CSV.
- `main.py` writes generated rows, a model, metrics, charts, and audit outputs locally; generated data and models are ignored by Git.
- Do not interpret synthetic scores as evidence that the model is suitable for real employee decisions.

## Pointers

- See the `pnpm-workspace` skill for workspace structure, TypeScript setup, and package details
