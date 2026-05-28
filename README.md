\# Climate and Tourism in Europe  
\### Are Cooler Destinations Becoming More Attractive?

\*\*Henri Vasserot\*\*  
MSc Data Science — University of Trento  
Computational Social Science (CAMPEDELLI)  

\---

\## 📌 Overview

This project investigates the relationship between climate conditions and tourism activity across European regions (NUTS2 level) over the period \*\*2010–2023\*\*.

The analysis combines \*\*econometric panel data methods\*\* and \*\*machine learning techniques\*\* to explore both linear and non-linear relationships between climate variables (temperature, precipitation) and tourism flows.

The study adopts a \*\*relational (non-causal) perspective\*\*, focusing on identifying robust statistical patterns rather than causal effects.

\---

## 🔗 Quick Access

- 📄 Paper: paper/paper.pdf  
- 🎤 Presentation: presentation/presentation.pdf  
- 📦 Data: data/processed/final_dataset_nuts2_2010_2023.csv  
- ⚙️ Code: code/  

\---

\## 🎯 Research Question

> \*What is the relationship between climate conditions and tourism activity across European regions over time?\*

A secondary motivation explores whether:

> \*Tourism demand may shift toward cooler regions in a context of rising temperatures.\*

\---

\## 🧠 Key Findings
\- Temperature has a significant positive within-region effect on tourism activity  

\- Precipitation does not exhibit a robust relationship  

\- Evidence of non-linearity (inverted U-shape) in econometric models  

\- Machine learning suggests a weaker, mostly monotonic relationship  

\- GDP is the dominant driver of tourism across all specifications  

\- No strong empirical evidence of a systematic shift toward cooler destinations  

Overall:  
Climate matters, but remains secondary to structural economic factors

\---

\## 🗂️ Data
\### Sources

\- Eurostat  

&#x20; - Tourism: `tour\_occ\_nin2`  

&#x20; - GDP: `nama\_10r\_2gdp`  

&#x20; - Population: `demo\_r\_pjanaggr3`  

\- ERA5 (Copernicus / Open-Meteo)  

&#x20; - Temperature (2m)  

&#x20; - Precipitation  

\### Construction

\- Spatial aggregation: grid → NUTS2 regions  

\- Temporal aggregation: monthly → annual  


Final dataset:

\- 273 regions  

\- 2010–2023  

\- \~3,200 observations  

📁 Available here:

data/processed/final_dataset_nuts2_2010_2023.csv


⚠️ Raw ERA5 data is not included due to file size.

\---

\## ⚙️ Methodology
\### Econometric Approach

\- OLS with time fixed effects  

\- Panel fixed effects (region + year)  

\- Non-linear specification with quadratic term  


Turning point:

T* = -β₁ / (2β₂)

\---

\### Machine Learning

\- Decision Tree (interpretability)  

\- Random Forest (predictive performance)  


Tools:

\- Feature importance  

\- Partial Dependence Plots (PDP)  

\---

\## 📊 Results

Outputs available in:

results/


Includes:


\- Distribution plots  

\- Spatial maps  

\- Temperature trend  

\- Non-linear effects  

\- Decision tree segmentation  

\- Partial dependence plots  

\---

\## 📈 Model Performance

Random Forest:
\- OOB R² ≈ 0.66  

\- RMSE ≈ 2.44  

Good predictive performance, but dominated by GDP

\---

\## 🧩 Project Structure

CSS\_Climate-Tourism-Europe/HenriVasserot

├── data/

│ ├── raw/

│ └── processed/

│ └── final_dataset_nuts2_2010_2023.csv

├── code/

│ ├── 01_data_eurostat.py

│ ├── 02_data_climate.py

│ ├── 03_build_dataset.py

│ ├── 04_regression.py

│ └── 05_machine_learning.py

├── results/

├── paper/

│ └── paper.pdf

├── presentation/

│ └── presentation.pdf

├── README.md

└── requirements.txt


Run pipeline:

python code/01_data_eurostat.py

python code/02_data_climate.py

python code/03_build_dataset.py

python code/04_regression.py

python code/05_machine_learning.py


Full article:

paper/paper.pdf









