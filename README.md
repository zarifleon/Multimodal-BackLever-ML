# Cuantificación Multimodal de Calidad y Costo en Isométricos de Alta Intensidad: Full Back Lever

Zone-Aware Ant Colony Optimization for Neural Network Topology Search.

This repository contains the implementation and experiments for **Z-ANN-Miner**, an extension of the ANN-Miner algorithm (Salama & Abdelbar, ANTS 2014) that introduces typed zone neighbourhoods, secondary zonal pheromone diffusion, and a composite quality function combining Balanced Accuracy with a connection-density penalty. Four algorithms are benchmarked: `ANNMinerOriginal`, `ZANNMiner`, `ThreeLayerBP`, and `RandomMiner`.

Experiments run 6×5-fold stratified cross-validation across eight small UCI classification datasets and three larger datasets, reporting Accuracy, Balanced Accuracy, F1-macro, and MCC, with statistical comparison via Friedman test and Holm post-hoc correction.

## Requirements

- Python 3.12

## Setup

Install [uv](https://docs.astral.sh/uv/getting-started/installation/):

```bash
# macOS / Linux
curl -LsSf https://astral.sh/uv/install.sh | sh

# Windows (PowerShell)
powershell -ExecutionPolicy ByPass -c "irm https://astral.sh/uv/install.ps1 | iex"
```

Then sync the environment from the lockfile:

```bash
uv sync
```

This reads `pyproject.toml` and `uv.lock`, creates a local virtual environment (`.venv/`), and installs the exact pinned dependencies. The Python version is pinned in `.python-version` and will be respected automatically.

## Running the experiments

Open the main notebook:

```bash
uv run jupyter lab Z-ANN-Miner.ipynb
```

Sections 0–1 library setup and algorithm implementation. Sections 2 run the four algorithms and aggregate results. Section 3 compares the results of the algorithms. Each (seed, fold) result is saved to disk under `results/{dataset}/{seed}_fold_{k}/` and skipped if already present, so runs are resumable.

## Project structure

```
.
├── Z-ANN-Miner.ipynb    # Main experiment notebook
├── pyproject.toml       # Project metadata and dependencies
├── uv.lock              # Pinned dependency lockfile
├── .python-version      # Pinned Python version
├── datasets/            # Contains Ottogroup and segment datasets, since they are not easily downloadable via code
├── comparison/          # Output directory for comparison plots
└── results/             # Output directory for experiment results, metrics, statistical tests, and model states

```



## Reference

Salama, K. & Abdelbar, A. M. (2014). A Novel Ant Colony Algorithm for Building Neural Network Topologies. *Swarm Intelligence (ANTS 2014)*, LNCS 8667, 1–12. https://doi.org/10.1007/978-3-319-09952-1_1