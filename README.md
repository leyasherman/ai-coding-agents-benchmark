# AI Coding Agents: Comparative Evaluation

UCL group coursework comparing GitHub Copilot, Claude Code and OpenAI Codex on a small, structured set of data science tasks. The business problem is how to evaluate coding assistance beyond plausible-looking code, including statistical validity, reproducibility and successful debugging.

## Methodology and recorded findings

The study uses Titanic survival prediction across five tasks: ingestion/cleaning, baseline modelling, leakage detection, debugging and exploratory analysis. Each task is assessed on six dimensions (correctness, statistical validity, reproducibility, code quality, efficiency and safety), scored 0–2 each, for 60 points overall.

The original project documentation records:

| Tool configuration in this coursework | Score |
|---|---|
| GitHub Copilot | 29/60 |
| Claude Code | 54/60 |
| OpenAI Codex | 59/60 |

These are coursework rubric scores, not general rankings of current products. The recorded runs illustrate how execution and verification affect saved fixes and how preprocessing mistakes can propagate into later tasks. Publication preserved the supplied scripts, including intentionally broken examples; the study was not rerun.

## Technologies

Python, pandas, NumPy, scikit-learn, matplotlib, seaborn and Jupyter. The task scripts use logistic regression, preprocessing pipelines, train/test evaluation and EDA charts.

## Start here

- [`runs/`](runs/): tool-specific scripts, notebooks and selected aggregate plots.
- [`data/titanic_pipeline_v1.py`](data/titanic_pipeline_v1.py) and [`data/titanic_pipeline_v2.py`](data/titanic_pipeline_v2.py): intentionally flawed task inputs.
- [Dataset setup](data/README.md).

## How to run

```bash
python -m venv .venv
# Activate the environment, then:
python -m pip install -r requirements.txt
```

Download the original Titanic file from the provider linked in [data instructions](data/README.md) and place it at `data/Titanic-Dataset.csv`. For an example cleaning run, start from the repository root:

```bash
cd "runs/Claude Code"
python preprocess.py
```

Inspect input paths before running other scripts: some expect local `titanic.csv` or a tool-specific `titanic_clean.csv`. Open the notebooks with Jupyter for the corresponding sessions. The archive is a selected evidence collection, not a single automated benchmark runner. Some files referenced by the original study, including combined notebooks and full run logs, are not included.

## Limitations and authorship

Group coursework; the supplied materials do not establish Leya Sherman's individual task allocation, so these results are presented as collaborative work. AI-generated run code is retained as evaluation evidence. The small task set, subjective rubric, historical tool versions/configurations and different execution interfaces limit generalisation. Intentionally faulty scripts should not be used as production templates. Raw and cleaned datasets are excluded because redistribution permission was not supplied. The original numeric scoring is documented here; full scoring logs were absent from the prepared archive.
