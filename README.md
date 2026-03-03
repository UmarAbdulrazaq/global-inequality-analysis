Global Income Inequality Analysis

Overview
This project investigates the relationship between economic development and income inequality across countries.
Using World Bank data, the analysis examines whether higher GDP per capita is associated with lower income inequality (measured by the Gini index). The project combines data cleaning, transformation, statistical analysis, and economic interpretation.

Research Question
Does higher GDP per capita correlate with lower income inequality across countries?

Data Sources:
World Bank Open Data:
GDP per capita (current US$) — NY.GDP.PCAP.CD
Gini index (World Bank estimate) — SI.POV.GINI
Country metadata (Region, Income Group)

The analysis focuses on the year 2022, using the most recent available cross-country data.

Data Preparation
Key steps:
Removed metadata rows from World Bank files
Converted wide-format data into long format
Merged GDP and Gini datasets by country and year
Filtered to 2000–2022
Created a 2022 cross-sectional dataset
Log-transformed GDP per capita to address skewness
Removed missing and invalid values
All transformations were performed programmatically using Python to ensure reproducibility.

Methodology:
Two main approaches were used:
Correlation analysis
Pearson correlation between log(GDP per capita) and Gini index

Linear regression model

𝐺𝑖𝑛𝑖 = 𝛽0 + 𝛽1log(𝐺𝐷𝑃)+ 𝜖
Regression was estimated using Ordinary Least Squares (OLS).

Key Findings
Correlation (2022): -0.25
→ Richer countries tend to have lower inequality, but the relationship is moderate.
Regression coefficient (log GDP): -1.37
→ Higher income levels are associated with lower Gini values.
p-value: 0.037
→ The relationship is statistically significant at the 5% level.
R²: 0.064
→ GDP per capita explains only about 6.4% of inequality variation across countries.

Interpretation
While economic development is associated with lower inequality, income level alone explains only a small portion of cross-country differences. Institutional factors, redistribution policies, education systems, and labor market structures likely play a substantial role.

Regional comparison shows that:
Latin America & Caribbean exhibits the highest average inequality.
South Asia shows the lowest average inequality in 2022.

Tools Used
Python (pandas, numpy)
statsmodels (OLS regression)
matplotlib
Git & GitHub

Project struture 
global-inequality-analysis/
├── data/
│   ├── raw/
│   └── clean/
├── notebooks/
│   └── 01_data_preparation.ipynb
└── README.md