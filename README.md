# NVIDIA GPU Performance Analytics: A Data Science Study on GPU Specifications, Benchmarks, and Performance Drivers

## Project Overview

This project performs an end-to-end Data Science analysis of NVIDIA, AMD, and ATI GPU datasets to identify the key factors influencing graphics performance.

The project combines multiple real-world datasets containing GPU specifications, benchmark scores, and graphics API performance metrics. The data is cleaned, merged, analyzed, and transformed into a feature-engineered dataset to uncover meaningful insights about GPU performance trends and hardware characteristics.

---

## Problem Statement

Modern GPUs differ significantly in architecture, memory capacity, processing power, and efficiency.

The objective of this project is to:

- Analyze GPU hardware specifications and benchmark data.
- Identify the strongest factors affecting GPU performance.
- Perform statistical testing to validate findings.
- Engineer meaningful features for future Machine Learning applications.
- Generate actionable business and technical insights from GPU data.

---

## Dataset Sources

This project uses three datasets:

### 1. GPU Specifications Dataset

Contains:

- GPU Name
- Memory Size
- Memory Clock
- GPU Clock
- Shader Units
- TMU
- ROP
- Bus Type
- Release Year

### 2. GPU Benchmark Dataset

Contains:

- G3DMark
- G2DMark
- GPU Value
- Price
- TDP
- Power Performance

### 3. Graphics API Performance Dataset

Contains:

- OpenCL Score
- CUDA Score
- Vulkan Score
- Metal Score

---

## Project Workflow

```text
Raw Datasets
      ↓
Data Cleaning
      ↓
Data Standardization
      ↓
Dataset Merging
      ↓
Missing Value Treatment
      ↓
Exploratory Data Analysis (EDA)
      ↓
Statistical Analysis
      ↓
Feature Engineering
      ↓
Business Insights
      ↓
Final Analytics Dataset
```

---

## Technologies Used

- Python
- Pandas
- NumPy
- Matplotlib
- Seaborn
- SciPy
- Jupyter Notebook

---

## Project Structure

```text
nvidia-gpu-data-science/

├── data/
│   ├── raw/
│   ├── cleaned/
│   └── processed/
│
├── notebooks/
│   ├── Project_Understanding.ipynb
│   ├── 03_data_cleaning.ipynb
│   ├── 04_eda.ipynb
│   └── 05_statistical_analysis.ipynb
│
├── visuals/
│   ├── gpu_memory_distribution.png
│   ├── gpu_clock_distribution.png
│   ├── g3d_distribution.png
│   ├── correlation_heatmap.png
│   └── manufacturer_comparison.png
│
├── requirements.txt
│
└── README.md
```

---

## Data Cleaning

The following preprocessing steps were performed:

- Standardized column names
- Standardized GPU identifiers
- Merged three independent datasets
- Removed duplicate records
- Handled missing values
- Removed columns with excessive missing data
- Created a clean master dataset

---

## Exploratory Data Analysis

The analysis included:

### Univariate Analysis

- GPU Memory Distribution
- GPU Clock Distribution
- G3DMark Distribution

### Bivariate Analysis

- Memory Size vs Performance
- GPU Clock vs Performance
- Unified Shader vs Performance
- Release Year vs Performance
- Manufacturer vs Performance

### Correlation Analysis

- Correlation Heatmap
- Strongest Performance Predictors

### Outlier Detection

- Boxplots
- Distribution Analysis
- Hardware Performance Extremes

---

## Statistical Analysis

### Confidence Interval

Mean G3DMark Score:

```text
2401.65
```

95% Confidence Interval:

```text
2149.83 – 2653.46
```

Interpretation:

We are 95% confident that the true average GPU benchmark score lies within this interval.

---

### Independent T-Test

Objective:

Determine whether modern GPUs significantly outperform older GPUs.

Results:

```text
T Statistic = 14.99
P Value = 2.69 × 10⁻³⁸
```

Conclusion:

Modern GPUs significantly outperform older generations.

---

### ANOVA Test

Objective:

Determine whether manufacturer affects GPU performance.

Results:

```text
F Statistic = 43.22
P Value = 7.86 × 10⁻¹⁹
```

Conclusion:

GPU manufacturer has a statistically significant impact on performance.

---

## Feature Engineering

The following features were created:

### Performance Per Watt

```python
g3dmark / tdp
```

Measures energy efficiency.

---

### Performance Per GB

```python
g3dmark / memsize
```

Measures memory efficiency.

---

### Performance Per Shader

```python
g3dmark / unifiedshader
```

Measures shader utilization efficiency.

---

### GPU Age

```python
2026 - releaseyear
```

Represents hardware age.

---

### Performance Category

Created using quartile-based segmentation:

- Low
- Mid
- High
- Extreme

Balanced distribution:

| Category | Count |
| -------- | ----- |
| Low      | 298   |
| Mid      | 285   |
| High     | 293   |
| Extreme  | 289   |

---

## Key Findings

### 1. OpenCL Score is the Strongest Predictor of GPU Performance

Correlation:

```text
0.944
```

---

### 2. Memory Size Strongly Influences GPU Performance

Correlation:

```text
0.817
```

---

### 3. GPU Performance Has Improved Significantly After 2015

Validated through statistical testing.

---

### 4. Manufacturer Significantly Affects GPU Performance

Validated using ANOVA testing.

---

### 5. Unified Shader Count Positively Impacts Performance

Higher shader counts generally lead to better benchmark scores.

---

### 6. Clock Speed Alone Does Not Fully Explain Performance

GPU architecture and memory subsystem also contribute significantly.

---

### 7. High-End GPUs Form Most Performance Outliers

Examples include:

- RTX 3090 Ti
- RTX 4090 Class GPUs
- Professional Workstation GPUs

---

## Business Insights

- Newer GPU generations provide substantially better performance.
- OpenCL performance is highly associated with benchmark scores.
- Performance-per-watt varies significantly across architectures.
- Memory capacity remains a critical factor in high-end GPUs.
- Manufacturer choice influences overall GPU capability.

---

## Future Work

This project serves as the foundation for a separate Machine Learning project.

Future ML tasks include:

### Regression

Predict GPU benchmark scores (G3DMark).

### Classification

Predict GPU performance category:

- Low
- Mid
- High
- Extreme

Models to be evaluated:

- Linear Regression
- Random Forest
- Gradient Boosting
- XGBoost
- Classification Algorithms

---

## Author

**G N Bhuvaneshwaran**

B.Tech Computer Science & Engineering

Amrita Vishwa Vidyapeetham

Data Science | Machine Learning | AI Enthusiast
