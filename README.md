# Aiqon assignment

Shipment ETA and delay propagation, take-home for the Aiqon AI internship.

## What is in here

- `Aiqon_assignment.ipynb`: the whole project (synthetic data, features, models, evaluation, explanations)
- `Aiqon_assignment_report.pdf`: technical report
- `requirements.txt`: Python packages

## How to run

```
pip install -r requirements.txt
jupyter notebook Aiqon_assignment.ipynb
```

Run all cells from top to bottom (it takes about a minute). Everything is seeded, so the numbers reproduce.
The notebook writes `data/shipments_synthetic.csv` and the tables and figures in `outputs/`.
It also runs in Google Colab, the notebook installs `shap` itself if it is missing.

## Short summary

- 300 synthetic shipments over 8 routes, five stages each (departure, sea transit, port handling, customs, delivery).
- ETA is predicted at three checkpoints (departure, port arrival, customs cleared) by modelling the remaining delay on top of the delay already carried.
- Chronological 75/25 split plus a 5 fold time series split.
- Explanations come from SHAP values summed by stage, plus the observed delay of each stage that has already happened.

The data is synthetic, so the scores show how well the method recovers the rules in the simulator, not real-world accuracy.
