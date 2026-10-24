# Iris Flower Classification

<p align="center">
  <strong>A visual, notebook-first exploration of the Iris dataset</strong><br>
  Inspect flower measurements, compare species, and discover which features best separate them.
</p>

<p align="center">
  <img alt="Python" src="https://img.shields.io/badge/Python-3.9%2B-3776AB?logo=python&logoColor=white">
  <img alt="Jupyter Notebook" src="https://img.shields.io/badge/Interface-Jupyter-F37626?logo=jupyter&logoColor=white">
  <img alt="Project type" src="https://img.shields.io/badge/Focus-Exploratory%20data%20analysis-6C63FF">
</p>

---

## Project overview

This project explores the classic Iris flower dataset through a Jupyter notebook. It examines the dataset's structure and class balance, then uses statistical summaries and visualizations to compare sepal and petal measurements across **Iris setosa**, **Iris versicolor**, and **Iris virginica**.

The notebook is an analysis and visualization project, not a trained machine-learning application: it does **not** currently fit a classifier or report predictive accuracy. Its plots and findings are a useful foundation for a future classification workflow.

## At a glance

| | |
|---|---|
| **Notebook** | [`Iris_flower_classification.ipynb`](Iris_flower_classification.ipynb) |
| **Problem area** | Multiclass flower-species analysis |
| **Observations** | 150 |
| **Input measurements** | Sepal length, sepal width, petal length, petal width |
| **Target labels** | Setosa, versicolor, virginica |
| **Measurement units** | Centimeters |
| **Current scope** | Data inspection and exploratory visualization |

## Analysis workflow

```mermaid
flowchart LR
    A["Iris CSV"] --> B["Load with pandas"]
    B --> C["Inspect shape, types<br/>and missing values"]
    C --> D["Summarize species<br/>and measurements"]
    D --> E["Visualize distributions<br/>and feature relationships"]
    E --> F["Compare patterns<br/>across species"]
    F -. "Possible next step" .-> G["Train and evaluate<br/>a classifier"]
```

### What the notebook explores

- **Dataset inspection** — preview rows, check dimensions and column types, summarize numeric measurements, and count missing values.
- **Species balance** — count observations per species. The notebook's dataset contains 50 observations in each class.
- **Feature distributions** — visualize sepal and petal measurements with histograms and species-level distribution plots.
- **Feature relationships** — compare sepal and petal measurements with scatter plots and a pair plot colored by species.
- **Statistical comparisons** — inspect per-species box plots and a numeric-feature correlation heatmap.

## Dataset

The notebook expects an Iris CSV with these columns:

| Column | Meaning | Role |
|---|---|---|
| `Id` | Row identifier | Reference only; not a flower measurement |
| `SepalLengthCm` | Sepal length in centimeters | Input feature |
| `SepalWidthCm` | Sepal width in centimeters | Input feature |
| `PetalLengthCm` | Petal length in centimeters | Input feature |
| `PetalWidthCm` | Petal width in centimeters | Input feature |
| `Species` | Iris species label | Class / target |

The notebook's inspected dataset has **150 rows**, **four numeric measurements**, and **three balanced species classes**. It reports no missing values. The CSV itself is not included in this repository, so provide the dataset separately before running the notebook.

## Getting started

### Requirements

- Python 3.9 or newer
- Jupyter Notebook or JupyterLab
- pandas
- matplotlib
- seaborn

### 1. Get the project and dataset

Open a terminal in the project directory. Place your CSV there (or note its full path) and check that it contains the columns listed above.

### 2. Install the dependencies

```bash
python -m pip install pandas matplotlib seaborn notebook
```

### 3. Set the dataset path

The notebook currently reads the CSV from a Windows-specific path (`D:\iris\Iris_data.csv`). Update the `pd.read_csv(...)` cell in `Iris_flower_classification.ipynb` to point to your copy of the dataset. For example, when the CSV is in the project directory:

```python
Iris_data = pd.read_csv("Iris_data.csv")
```

### 4. Run the notebook

```bash
jupyter notebook Iris_flower_classification.ipynb
```

Run the cells from top to bottom. The notebook will display the data summaries and plots inline.

## Repository contents

```text
.
├── Iris_flower_classification.ipynb   # Data inspection and exploratory analysis
└── README.md                           # Project guide
```

Jupyter may also create a `.ipynb_checkpoints/` folder while you work; it contains automatically generated notebook checkpoints.

## Interpreting the results

Use the species-colored scatter plots and pair plot to see how measurements cluster, and the box plots and distributions to compare each feature across classes. In the classic Iris dataset, petal measurements are often especially useful for distinguishing species; use the notebook's visual evidence to assess that pattern rather than treating it as a measured model score.

The `Id` column is an identifier, not a biological feature. The notebook excludes it from the pair plot and correlation view; it should also be excluded from any future model inputs.

## Limitations and next steps

- **Local data required:** the CSV is not checked into the project.
- **Path needs updating:** the existing notebook uses a machine-specific absolute path.
- **Exploration only:** no train/test split, fitted classifier, or evaluation metrics are implemented.
- **Deprecated plotting API:** some distribution plots use Seaborn's `distplot`, which emits deprecation warnings in newer Seaborn versions.

Possible extensions include making data loading configurable, replacing deprecated plotting calls, and adding a stratified train/test split with a baseline classifier and appropriate evaluation metrics.

## Contributing

Improvements are welcome. Keep the notebook reproducible, avoid committing local dataset paths or unnecessary generated outputs, and describe any added model's evaluation setup alongside its results.
