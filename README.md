# ❤️‍🩹 EDA PROJECT 6:
# Beyond the Average: Uncovering Geographic, Sex, and Race/Ethnicity Disparities in U.S. Heart Disease Mortality (2019–2021)

## 📌 Project Overview
This repository contains a comprehensive Exploratory Data Analysis (EDA) of **heart disease mortality among U.S. adults (35+)** for 2019–2021, using age-adjusted, spatially smoothed 3-year average mortality rates from the National Center for Health Statistics (NCHS) (data.gov). The analysis focuses on identifying geographic hotspots and disparities by **sex** and **race/ethnicity**, and assessing distributional characteristics of the mortality rates.

Primary aims:
- Identify geographic hotspots and county/state patterns of elevated heart disease mortality.
- Examine sex differences (male vs female) and geographic heterogeneity.
- Quantify disparities across race/ethnicity groups and subgroup hotspots (race × sex).
- Assess distributional properties of the mortality rates and implications for modeling.

---

## 🧰 Tools & Libraries
- **Python** (Jupyter / Colab)  
- `pandas`, `numpy` — data wrangling  
- `matplotlib`, `seaborn` — static visualization  
- `geopandas`, `plotly.express` — mapping / choropleths  
- `scipy`, `statsmodels` — basic statistical testing

---

## 🔍 Key Questions Addressed
1. **Which counties and states have the highest age-adjusted heart disease mortality (2019–2021, smoothed 3-yr avg)?**  
2. **How do male and female mortality rates compare across locations (paired comparisons and rate ratios)?**  
3. **How do mortality rates vary by race/ethnicity, and which groups show the highest medians/IQRs?**  
4. **Where are subgroup hotspots (race × sex) — e.g., Black males, AI/AN populations?**  
5. **Are mortality rate distributions skewed or heavy-tailed, and do they require transformation for modeling?**

---

## 🔍 Key Analysis Steps
1. **Initial review** — load data, inspect schema, data types, and sample rows.  
2. **Cleaning & normalization** — snake_case columns, coerce `data_value` to numeric, create flags (smoothed, geographic level), remove 'Insufficient Data' rows, pad FIPS (`location_id`).  
3. **Filtering for analysis** — extract county-level, smoothed, relevant stratifications (Overall, Male, Female, and race/ethnic groups).  
4. **Ranking & hotspot detection** — rank counties/states by mortality rate and generate choropleth maps.  
5. **Paired comparisons by sex** — merge male/female county rates for paired scatterplots and compute rate ratios/differences.  
6. **Race/ethnicity comparisons** — group summaries (median, IQR) and boxplots by `stratification2`.  
7. **Distributional analysis** — histograms, log-transforms, skewness/kurtosis to guide downstream modeling.

---

## 📊 Key Findings (summary)
- **Geographic disparities & hotspots:** The southeastern U.S. repeatedly emerges with the highest age-adjusted mortality (LA, KY, AL, MS, GA, SC, TN, OK). County-level choropleths confirm concentrated hotspots in the Southeast and parts of Appalachia.  
- **Sex differences:** In most counties, **male mortality > female mortality**. Paired scatterplots show most counties above the y=x line; magnitude varies geographically.  
- **Race/ethnicity disparities:** Median rates are highest among **Black** and **Native Hawaiian / Other Pacific Islander** groups, with Asian and “More than one race” showing lower medians. Boxplots reveal greater spread in certain groups (higher IQR).  
- **Subgroup hotspots:** Race × sex maps show particularly severe hotspots for **Black males/females** in the Southeast. White males show elevated rates across the Southeast, Appalachia, and parts of the Midwest.  
- **Distributional characteristics:** Original `data_value` is positively skewed (skew ≈ 0.73) with moderate kurtosis (≈1.52). Log-transform reduces skew but increases kurtosis; transformation choice should be driven by modeling goals and robustness considerations.

> **Public-health implication:** The findings point to concentrated geographic and demographic inequities in heart disease mortality — targeted interventions and investments in the Southeast and among specific race/sex subgroups could yield high public-health benefit.

---

## 📸 Visual Highlights

| Top 20 Counties (bar) | County Choropleth (smoothed rates) |
|-----------------------|------------------------------------|
| `images/top20_counties.png` | `images/choropleth_county.png` |

| Paired Male vs Female Scatter | Race/Ethnicity Boxplot |
|------------------------------|-------------------------|
| `images/male_vs_female_scatter.png` | `images/race_boxplot.png` |

## 🗂 Repository Structure


