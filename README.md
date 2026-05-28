# Climate and Tourism in Europe

Interactive computational social science project exploring the relationships between climate conditions, tourism activity, territorial heterogeneity, and spatial structures across European NUTS2 regions.

The project combines spatial data engineering, econometric panel models, machine learning techniques, and exploratory spatial network analysis to investigate tourism dynamics in Europe between 2010 and 2023.

---

## Architecture

![Project architecture](results/project_architecture.png)

End-to-end analytical workflow integrating climate acquisition, territorial harmonization, econometric modeling, machine learning, and spatial network analysis.

---

## Overview

This project investigates the relationship between climate conditions and tourism activity across European regions at the NUTS2 level over the period 2010–2023.

The analysis combines:

* panel econometric models,
* machine learning techniques,
* geospatial processing,
* and exploratory spatial network analysis.

The project adopts an observational and non-causal perspective focused on identifying robust spatial and statistical patterns within the European tourism system.

---

## Research Questions

Main research question:

> What is the relationship between climate conditions and tourism activity across European regions over time?

Secondary research question:

> Are cooler European destinations becoming relatively more attractive in a context of rising temperatures?

---

## Methodological Overview

The analytical workflow combines:

* Eurostat regional tourism indicators,
* ERA5 climate datasets,
* geospatial territorial harmonization,
* panel econometric models,
* machine learning prediction,
* spatial network analysis.

The project investigates:

* climate-tourism relationships,
* regional heterogeneity,
* non-linear temperature effects,
* territorial segmentation,
* spatial connectivity structures.

---

## Data Sources

### Eurostat

Regional socio-economic indicators:

* Tourism nights (`tour_occ_nin2`)
* GDP (`nama_10r_2gdp`)
* Population (`demo_r_pjanaggr3`)

### ERA5 Climate Data

Climate indicators:

* 2m temperature
* Total precipitation

Climate data were spatially aggregated from ERA5 grids to European NUTS2 regions.

---

## Final Dataset

Final harmonized panel dataset:

* 273 NUTS2 regions
* 2010–2023
* ~3,200 observations

Dataset available in:

```text
data/processed/final_dataset_nuts2_2010_2023.csv
```

Raw ERA5 climate files are not included due to storage limitations.

---

## Analytical Workflow

### 01 — Eurostat Data Acquisition

* tourism indicators
* GDP extraction
* population harmonization

### 02 — Climate Data Processing

* ERA5 acquisition
* annual climate aggregation
* spatial joins with NUTS2 regions

### 03 — Dataset Construction

* territorial harmonization
* panel dataset construction
* missing value handling

### 04 — Econometric Analysis

* OLS models
* fixed effects panel models
* non-linear specifications

### 05 — Machine Learning Analysis

* decision tree regression
* random forest models
* feature importance analysis
* partial dependence plots

### 06 — Spatial Network Analysis

* territorial adjacency graph
* network centrality
* spatial community detection
* macro-regional structures

---

## Econometric Framework

The econometric analysis includes:

* pooled OLS,
* time fixed effects,
* region fixed effects,
* quadratic temperature specifications.

Non-linear temperature effects are estimated through:

T^* = -\frac{\beta_1}{2\beta_2}

---

## Machine Learning Framework

Implemented models include:

* Decision Tree Regressor
* Random Forest Regressor

The analysis includes:

* predictive performance evaluation,
* feature importance analysis,
* partial dependence visualization.

---

## Spatial Network Analysis

The project additionally explores the relational organization of the European territorial system through a spatial adjacency network.

Regions are represented as nodes, while territorial contiguity relationships define network edges.

The network analysis investigates:

* spatial connectivity,
* intermediary territorial regions,
* macro-regional community structures.

---

## Main Findings

Main exploratory findings include:

* Temperature exhibits a positive within-region relationship with tourism activity
* Evidence of non-linearity appears in econometric specifications
* Precipitation effects remain weak and unstable
* GDP remains the dominant explanatory variable
* Machine learning models suggest mostly monotonic temperature effects
* No strong empirical evidence supports a systematic shift toward cooler destinations
* Spatial network analysis reveals coherent European macro-regional structures

Overall, climate conditions matter, but remain secondary to structural economic and territorial factors.

---

## Results

Outputs available in:

```text
results/
```

Includes:

* tourism distributions,
* climate visualizations,
* econometric outputs,
* non-linear effect plots,
* decision trees,
* partial dependence plots,
* spatial centrality maps,
* community structure maps.

---

## Model Performance

### Random Forest

* OOB R² ≈ 0.66
* RMSE ≈ 2.44

The predictive performance remains good, although tourism intensity is still largely dominated by economic indicators.

---

## Project Structure

```text
CSS_Climate-Tourism-Europe_HenriVasserot/
│
├── code/
│   ├── 01_data_eurostat.ipynb
│   ├── 02_data_climate.ipynb
│   ├── 03_build_dataset.ipynb
│   ├── 04_regression.ipynb
│   ├── 05_machine_learning.ipynb
│   └── 06_network_analysis.ipynb
│
├── data/
│   ├── raw/
│   └── processed/
│       └── final_dataset_nuts2_2010_2023.csv
│
├── results/
│
├── paper/
│   └── paper.pdf
│
├── presentation/
│   └── presentation.pdf
│
├── README.md
├── requirements.txt
└── .gitignore
```

---

## Reproducibility

### Create virtual environment

```bash
python -m venv .venv
```

### Activate virtual environment

```bash
# Windows
.venv\Scripts\activate

# Linux / macOS
source .venv/bin/activate
```

### Install dependencies

```bash
pip install -r requirements.txt
```

---

## Run Analytical Pipeline

```bash
jupyter notebook
```

Then execute notebooks sequentially:

1. 01_data_eurostat.ipynb
2. 02_data_climate.ipynb
3. 03_build_dataset.ipynb
4. 04_regression.ipynb
5. 05_machine_learning.ipynb
6. 06_network_analysis.ipynb

---

## Technologies Used

* Python
* pandas
* geopandas
* xarray
* statsmodels
* scikit-learn
* networkx
* matplotlib
* Eurostat API
* ERA5 climate data

---

## Limitations

The project remains exploratory and observational.

Several limitations should be acknowledged:

* incomplete climate uncertainty modeling,
* limited causal identification,
* annual aggregation effects,
* heterogeneous regional tourism structures,
* simplified territorial adjacency assumptions in network analysis.

---

## Future Work

Potential future extensions include:

* tourism flow networks,
* causal inference strategies,
* seasonal climate analysis,
* advanced spatial econometric models,
* dynamic network evolution,
* forecasting models.

---

## Author

Henri Vasserot
MSc Data Science — University of Trento
Computational Social Science (CAMPEDELLI)
