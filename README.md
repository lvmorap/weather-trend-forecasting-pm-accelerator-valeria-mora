# Weather Trend Forecasting

**Author:** Valeria Mora  
**Date:** May 2026  

---

## PM Accelerator Mission

By making industry-leading tools and education available to individuals from all backgrounds, we level the playing field for future PM leaders. This is the PM Accelerator motto, as we grant aspiring and experienced PMs what they need most – Access. We introduce you to industry leaders, surround you with the right PM ecosystem, and discover the new world of AI product management skills.

---

## 📊 Project Overview

This project analyzes the **Global Weather Repository** dataset, a comprehensive collection of daily weather observations from cities around the world containing over 40 meteorological features. The analysis progresses from basic data cleaning and exploration to advanced machine learning models that forecast temperature with high precision.

### Dataset Information

- **Source:** [Global Weather Repository on Kaggle](https://www.kaggle.com/datasets/nelgiriyewithana/global-weather-repository/)
- **Records:** 20,000+ daily observations
- **Geographical Coverage:** Multiple countries and cities worldwide
- **Temporal Range:** Historical daily weather data
- **Key Features:**
  - Temperature (°C)
  - Humidity (%)
  - Wind Speed (km/h)
  - Precipitation (mm)
  - Atmospheric Pressure (mb)
  - Visibility (km)
  - UV Index
  - Cloud Coverage
  - And 30+ additional meteorological variables

---

## 🔍 Methodology

### 1. Data Cleaning & Preprocessing

The analysis begins with thorough data quality assessment and preparation:

- **Missing Value Handling:** Applied median imputation for numeric columns, ensuring no data loss while maintaining statistical integrity
- **Date Extraction:** Converted date fields to datetime objects and extracted temporal features (year, month, day, day of year, month name)
- **Statistical Summary:** Generated comprehensive statistics to understand data distributions and identify anomalies
- **Data Validation:** Verified data integrity and confirmed successful preprocessing

### 2. Exploratory Data Analysis (EDA)

Comprehensive visualization and correlation analysis revealed:

- **Temperature Distribution:** Global temperature patterns across the dataset with identified mean, median, and distribution shape
- **Seasonal Patterns:** Monthly aggregation showing temperature and precipitation trends throughout the year
- **Humidity-Temperature Relationship:** Scatter analysis identifying correlations between different weather variables
- **Correlation Matrix:** Computed Pearson correlations among 9 key meteorological variables to identify relationships

#### Key EDA Findings:
- Clear seasonal temperature variations with months showing distinct patterns
- Strong correlations between temperature and other climate variables
- Precipitation patterns vary significantly by month
- Humidity shows complex non-linear relationship with temperature

### 3. Predictive Model Development

Two machine learning models were developed and compared:

#### Model 1: Linear Regression
- **Algorithm:** Simple linear regression on standardized features
- **Approach:** Assumes linear relationships between input features and temperature
- **Preprocessing:** StandardScaler normalization applied
- **Use Case:** Baseline comparison and interpretability

#### Model 2: Random Forest (Advanced)
- **Algorithm:** Ensemble of 100 decision trees with random feature sampling
- **Approach:** Captures non-linear relationships and feature interactions
- **Data Split:** 80% training / 20% testing
- **Hyperparameters:** 100 estimators, random_state=42 for reproducibility
- **Advantage:** Superior performance with ability to measure feature importance

### 4. Model Evaluation

Models were evaluated using three complementary metrics:

- **MAE (Mean Absolute Error):** Average absolute difference between predicted and actual temperature
  - Interpretation: Direct magnitude of typical prediction error in °C
  
- **RMSE (Root Mean Squared Error):** Penalizes larger errors more heavily
  - Interpretation: Standard deviation-like metric for overall model fit quality
  - Useful for identifying models with occasional large errors

- **R² Score:** Proportion of temperature variance explained by the model
  - Interpretation: Percentage of temperature variability captured by the model
  - Range: 0-1 (or 0-100%), where higher values indicate better fit

#### Model Comparison Results:
The Random Forest model significantly outperforms Linear Regression, demonstrating the value of ensemble methods and non-linear modeling for weather forecasting.

### 5. Feature Importance Analysis

Random Forest provides relative importance scores for each input feature:

- **Top Features:** Identifies which variables most strongly influence temperature predictions
- **Interpretation:** Features with higher importance scores contribute more to accurate forecasts
- **Applications:** Guides data collection priorities and resource allocation for operational systems

### 6. Time Series Analysis

Evolution of global average temperature revealed through:

- **Daily Temperature Values:** Raw daily observations showing short-term fluctuations
- **7-Day Moving Average:** Smooths weekly noise while preserving trends
- **30-Day Moving Average:** Reveals longer-term seasonal and climate patterns

---

## 📈 Advanced Analysis Components

### Geographical Analysis

- **Country-Level Aggregation:** Computed average temperatures by country
- **Regional Extremes:** Identified 10 coldest and 10 hottest countries globally
- **Climate Zones:** Implicit regional climate categorization through temperature rankings
- **Insights:** Geographic variation in climate conditions affects forecasting model applicability

### Correlation Analysis

- Computed Pearson correlation coefficients among 9 key meteorological variables
- Identified strongest predictors of temperature
- Revealed inverse relationships (e.g., wind and pressure) and direct relationships (e.g., humidity variations)

### Ensemble Forecasting

- Combined multiple models (Linear Regression + Random Forest)
- Demonstrated ensemble advantage over individual model performance
- Validated predictions across different forecast horizons

---

## 🚀 Getting Started

### Requirements

- **Python Version:** 3.10+
- **Jupyter Notebook or JupyterLab**

### Installation

1. Clone or download this repository:
   ```bash
   git clone https://github.com/lvmorap/weather-trend-forecasting-pm-accelerator-valeria-mora.git
   cd weather-trend-forecasting-pm-accelerator-valeria-mora
   ```

2. Create and activate a virtual environment:
   ```bash
   python -m venv venv
   # On Windows:
   venv\Scripts\activate
   # On macOS/Linux:
   source venv/bin/activate
   ```

3. Install dependencies:
   ```bash
   pip install -r requirements.txt
   ```

### Running the Notebook

1. Start Jupyter:
   ```bash
   jupyter notebook
   ```

2. Open `weather_analysis.ipynb`

3. Run cells sequentially from top to bottom:
   - Cells execute independently and will regenerate all visualizations
   - All outputs display inline (no external file dependencies)
   - Estimated execution time: 3-5 minutes (mainly for Random Forest training)

---

## 📊 Notebook Structure

### Sections

1. **Title & Mission Statement** - Project overview and PM Accelerator context
2. **Libraries & Dataset Loading** - Environment setup and initial data access
3. **Dataset Overview** - Dimensions, features, and basic characteristics
4. **Data Cleaning & Quality Assessment** - Missing values, statistics, and data validation
5. **Data Preprocessing** - Date conversion, feature extraction, missing value imputation
6. **Exploratory Data Analysis** - Distributions, seasonal patterns, correlations
7. **Predictive Model Development** - Linear Regression and Random Forest comparison
8. **Feature Importance & Time Series** - Model interpretation and temporal trends
9. **Geographical Analysis** - Country-level temperature patterns
10. **Key Findings & Conclusions** - Summary statistics and model performance summary

---

## 📁 Project Structure

```
weather-trend-forecasting-pm-accelerator-valeria-mora/
├── weather_analysis.ipynb          # Main analysis notebook (refactored)
├── GlobalWeatherRepository.csv     # Input dataset
├── requirements.txt                 # Python dependencies
├── README.md                        # This file
└── LICENSE                          # Project license
```

### Files Explanation

- **weather_analysis.ipynb:** Jupyter notebook containing all analysis, visualizations, and model training
  - All outputs are regenerated at notebook execution
  - No external image files needed
  - Clean, professional report format

- **GlobalWeatherRepository.csv:** Original dataset from Kaggle (20,000+ records)

- **requirements.txt:** Lists all Python package dependencies with pinned versions

- **README.md:** Comprehensive project documentation

---

## 📚 Technical Stack

| Component | Technology | Purpose |
|-----------|-----------|---------|
| **Data Processing** | pandas, numpy | Data manipulation and numerical computing |
| **Visualization** | matplotlib, seaborn | Statistical graphics and visualizations |
| **Machine Learning** | scikit-learn | Model training, evaluation, and metrics |
| **Data Format** | CSV, JSON (notebook) | Input data and notebook storage |
| **Reporting** | Jupyter Notebook | Interactive analysis and documentation |

---

## 🔄 Reproducibility

The analysis is fully reproducible:

- **Fixed Random Seeds:** All randomization uses `random_state=42` for consistency
- **Version Control:** Specific package versions listed in `requirements.txt`
- **Data Source:** Uses publicly available Kaggle dataset
- **Notebook Kernel:** Runs in any Python 3.10+ Jupyter environment

To reproduce results:
1. Install exact dependencies from requirements.txt
2. Run all cells sequentially from top to bottom
3. Identical outputs will be generated with same data

