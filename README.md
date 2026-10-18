# 📊 Python Data Visualization and Graph Export

A hands-on Python notebook demonstrating how to explore numerical datasets, build plots with **Pandas, Matplotlib, and Seaborn**, and export visualizations as PNG images.

The notebook uses two datasets: **Dow Jones stock-index data** to plot trading volumes and the **UCI Auto MPG dataset** to explore relationships between automobile horsepower, weight, fuel efficiency, cylinders, and model year.

## ✨ Features

- Read and preview tabular data with Pandas.
- Plot trading volumes for selected stocks (**MSFT, GE, PG**) and all stocks in the Dow Jones dataset.
- Create scatter plots with Matplotlib and Pandas.
- Use Seaborn to encode additional variables with plot color and point size.
- Clean and convert automobile horsepower values into a numeric column.
- Plot average horsepower by model year.
- Customize plot dimensions and line styling.
- Export plots to PNG files, including an example with **300 DPI**.

## 🎯 Objective

Explore several approaches to plotting data in Python, then demonstrate how to save the resulting graphics for reports, presentations, or further analysis. The notebook is an introductory visualization exercise, not a forecasting or machine learning system.

## 📁 Datasets

### Dow Jones stock data

Loaded from a local file named `dow_jones_index.data`. The notebook uses the `stock` and `volume` columns to plot trading volume across records, including a comparison of MSFT, GE, and PG.

**Setup note:** The `dow_jones_index.data` file is not embedded in the notebook and must be provided separately in the notebook's working directory.

### UCI Auto MPG data

Loaded directly from the [UCI Machine Learning Repository](https://archive.ics.uci.edu/ml/machine-learning-databases/auto-mpg/auto-mpg.data).

The notebook uses the following fields:

| Column | Used for |
|---|---|
| `horsepower` | Scatter plots and yearly averages |
| `weight` | Scatter plots |
| `cylinders` | Seaborn point color |
| `mpg` | Seaborn point size |
| `year` | Grouping average horsepower by model year |

Missing horsepower values represented by `?` are converted to `NaN`, and horsepower is converted to a numeric type.

## 🛠️ Technologies

- Python
- Jupyter Notebook
- Pandas
- Matplotlib
- Seaborn
- NumPy

## 🔄 Notebook Workflow

1. Import Pandas and Matplotlib.
2. Load and preview the Dow Jones dataset.
3. Plot trading volumes for three selected stocks, then for all stocks.
4. Load the UCI Auto MPG dataset, name its columns, and preprocess horsepower and year.
5. Create horsepower-versus-weight scatter plots with Matplotlib, Seaborn, and Pandas.
6. Visualize average horsepower by year using a styled line plot.
7. Experiment with larger figure dimensions.
8. Export plots as PNG images.

## 📈 Visualizations

### Stock trading volume

The notebook compares the volume series for **MSFT, GE, and PG**, and separately plots volume series across all stocks in the dataset. These plots use the row order within stock groups, rather than explicitly setting calendar dates as the x-axis.

### Automobile horsepower and weight

Several scatter plots compare horsepower and vehicle weight, including a Seaborn plot in which:

- **Color (`hue`)** represents cylinder count.
- **Marker size (`size`)** represents miles per gallon (`mpg`).

### Average horsepower by model year

A grouped line plot displays mean horsepower for each year using a red dash-dot line.

## 💾 Exported Graphs

The notebook includes these saving operations:

```python
plt.savefig('horsepower_weight_scatter.png')
```

```python
plt.savefig('scatter_fig.png', dpi=300)
```

| Output | Description |
|---|---|
| `horsepower_weight_scatter.png` | Pandas scatter plot of vehicle weight versus horsepower; the same export cell appears twice |
| `scatter_fig.png` | Seaborn horsepower-versus-weight plot, with cylinders as color and MPG as point size, saved at 300 DPI |

These files are produced when the corresponding cells run successfully. They are not included as separate files in the supplied notebook.

## 🚀 Getting Started

### 1. Clone or download the repository

Download the project and open `Exporting_Graphs.ipynb` in Jupyter Notebook or JupyterLab.

### 2. Install the dependencies

```bash
pip install notebook pandas numpy matplotlib seaborn
```

### 3. Prepare the Dow Jones data

Place `dow_jones_index.data` next to the notebook, or adjust the path in:

```python
df = pd.read_csv('dow_jones_index.data')
```

### 4. Run the notebook

Run its cells in sequence. Internet access is needed to fetch the UCI Auto MPG dataset from its URL. Exported PNG images are written to the current working directory.

## 📂 Suggested Repository Structure

```text
Python-Data-Visualization-and-Graph-Export/
├── Exporting_Graphs.ipynb
├── dow_jones_index.data       # Required local input; add separately
├── README.md
└── outputs/                  # Optional folder for exported figures
```

**Note:** The notebook currently saves figures to the working directory, not to `outputs/`. To use that optional folder, change the `savefig` paths accordingly.

## ⚠️ Limitations

- The local Dow Jones data file is required but was not supplied with the notebook.
- The notebook reuses the variable `df` for the Auto MPG dataset, so later plots no longer use the stock data.
- The stock-volume plots do not explicitly use date values along the x-axis.
- Two consecutive cells save the same `horsepower_weight_scatter.png` filename, overwriting the earlier saved file.
- The notebook demonstrates visualization techniques; it does not perform statistical hypothesis testing, price prediction, or model evaluation.
- Online data-loading URLs may need updating if the source changes.

## 🔮 Possible Improvements

- Add plot titles, axis labels, and legends consistently.
- Use calendar dates on the stock-volume plots.
- Save exported plots into a dedicated folder with distinct filenames.
- Add brief interpretations of each visualization.
- Pin dependency versions for reproducibility.
- Package or document how to obtain the Dow Jones input data.

## 📌 Summary

This notebook is a compact demonstration of exploratory plotting and figure export in Python. Its main value is showing how Pandas, Matplotlib, and Seaborn can visualize financial and automobile datasets using different plotting interfaces and output settings.
