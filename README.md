# Integrated Energy System Multi-Load Prediction (Deep Learning)

This project focuses on predicting various load statuses in an integrated energy system—including electric load, cooling load, and heating load—to assist enterprises in optimizing energy dispatch and forecasting future trends.

---

## Table of Contents

- [Project Overview](#project-overview)
  - [Objectives](#objectives)
- [Data Sources](#data-sources)
- [Methodology](#methodology)
  - [Data Processing](#data-processing)
  - [Models Compared](#models-compared)
- [Key Findings](#key-findings)
  - [Correlation Analysis](#correlation-analysis)
  - [Model Performance Comparison](#model-performance-comparison)
- [Conclusion](#conclusion)
- [Recommendations](#recommendations)
- [Future Improvements](#future-improvements)
- [License](#license)
- [Contact](#contact)

---

## Project Overview

### Objectives

- **Identify key factors affecting energy loads:**  
  Analyze the impact of meteorological parameters and time-related variables on energy usage.

- **Predict short-term electric, cooling, and heating load statuses:**  
  Perform 168-hour single-step prediction using multi-output binary classification for multiple buildings.

- **Improve energy efficiency and reduce carbon emissions:**  
  Enable better energy dispatch optimization and future planning through accurate forecasting.

---

## Data Sources

- **Energy Data:**  
  Hourly electricity usage data from multiple buildings (including factories) covering January 2020.

- **Meteorological Data:**  
  Data from Taiwan's Central Weather Bureau, including temperature, humidity, wind speed, solar zenith angle, and pressure.

---

## Methodology

### Learning Type

- **Deep Learning**

### Task Type

- **168-hour single-step prediction (Multi-output Binary Classification)**

### Data Processing

- **Unit conversion:**  
  Ensures consistency across all data records.

- **Variational Mode Decomposition (VMD):**  
  Used for decomposing time-series signals to extract relevant features.

### Models Compared

- **CNN**
- **CNN + LSTM**
- **CNN + GRU**
- **CNN + BGRU**

---

## Key Findings

### Correlation Analysis

- **Electric–Cooling Load:**  
  0.795 (strong positive correlation)

- **Electric–Heating Load:**  
  -0.674 (moderate negative correlation)

- **Cooling–Heating Load:**  
  -0.902 (very strong negative correlation)

### Model Performance Comparison

#### Electric Load (Target 0)
- **Best Model:** CNN + LSTM (MSE: 0.0094, R²: 0.5474)
- **Second Best:** CNN + GRU

#### Cooling Load (Target 1)
- **Best Model:** CNN + LSTM (MSE: 0.0036, R²: 0.7463)
- **Second Best:** CNN + GRU

#### Heating Load (Target 2)
- **Best Model:** CNN + LSTM (MSE: 0.0263, R²: -0.1994)  
- **Alternative:** CNN + BGRU showed potential

---

## Conclusion

The **CNN + LSTM** model demonstrated the best overall performance across all three load types, particularly excelling in electric and cooling load predictions. Although the **CNN + GRU** model showed competitive results, the standalone **CNN** model underperformed, which highlights the importance of recurrent architectures in modeling time-series energy data.

---

## Recommendations

- **Model Selection:**  
  Adopt CNN + LSTM as the primary model for energy load forecasting.

---

## Future Improvements

- **Hybrid Architectures:**  
  Explore combinations of CNN, BiGRU, and LSTM for potentially better performance.
  
- **Feature Enhancement:**  
  Incorporate additional weather and temporal features into the model.

- **Extended Testing:**  
  Evaluate model performance on longer time periods to capture seasonal variations.

---

## Reference
1. https://academic.oup.com/ijlct/article/doi/10.1093/ijlct/ctae156/7738398?login=false
2. https://www.sciencedirect.com/science/article/abs/pii/S0142061520308255
3. https://inf.news/zh-hant/news/4903d1c59f9b9310cb32463bbd9c89a0.html
4. http://der.tsinghuajournals.com/article/2024/2096-2185/101427TR-2024-2-030.shtml

