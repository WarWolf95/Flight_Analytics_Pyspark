# Flight Data Analytics with PySpark

[![Python](https://img.shields.io/badge/Python-3.9-blue.svg)](https://www.python.org)
[![PySpark](https://img.shields.io/badge/PySpark-3.4.0-orange.svg)](https://spark.apache.org)
[![Tableau](https://img.shields.io/badge/Tableau-Public-green.svg)](https://public.tableau.com)
[![License](https://img.shields.io/badge/License-MIT-yellow.svg)](LICENSE)

## Project Overview

This project implements a complete big data analytics pipeline using PySpark to analyze a large-scale flight dataset of **8,077,594 records** (>1GB, 16 features). The project addresses two real-world classification problems in aviation:

1. **Ground Detection**: Binary classification to predict whether an aircraft is on ground or airborne
2. **Vertical Rate Classification**: Multi-class classification to categorize flight phases (Descending, Level, Ascending)

Four machine learning algorithms were implemented and compared:
- Logistic Regression
- Decision Trees
- Multinomial Logistic Regression
- Naive Bayes

##  Key Achievements

| Metric | Value |
|--------|-------|
| Dataset Size | 8,077,594 records / 16 features |
| Storage Optimization | 29% reduction (Parquet format) |
| Best Model (Problem 1) | Decision Tree (AUC: 0.860, Accuracy: 0.9999) |
| Best Model (Problem 2) | Multinomial Logistic Regression (Accuracy: 0.673) |
| Processing Speedup | 6.93x faster than Pandas (20 processors) |
| Data Completeness | 92.09% |
| Tableau Dashboards | 4 interactive dashboards |

##  Dataset Schema

| Feature | Type | Description |
|---------|------|-------------|
| time | LongType | Unix timestamp |
| icao24 | StringType | Aircraft identifier |
| lat | DoubleType | Latitude |
| lon | DoubleType | Longitude |
| velocity | DoubleType | Ground speed (m/s) |
| heading | DoubleType | Direction (degrees) |
| vertrate | DoubleType | Vertical rate (m/s) |
| callsign | StringType | Flight identifier |
| onground | BooleanType | Ground/airborne indicator |
| baroaltitude | DoubleType | Barometric altitude (m) |
| geoaltitude | DoubleType | Geometric altitude (m) |

##  Project Structure
flight-analytics-pyspark/
│
├── 📜 CW_ML_v2.ipynb                    # Complete PySpark pipeline (all steps combined)
│
├── 📊 dashboard.twbx                     # Single Tableau workbook with 4 dashboards
│
├── 📄 report.pdf                          # Final coursework submission
│
├── 📄 README.md                            # Project documentation
├── 📄 requirements.txt                      
└── 📄 .gitignore 

##  Key Results

### Problem 1: Ground Detection

| Model | AUC | Accuracy | F1-Score | Precision | Recall |
|-------|-----|----------|----------|-----------|--------|
| Logistic Regression | 0.829 | 0.99989 | 0.99983 | 0.99977 | 0.99989 |
| Decision Tree | **0.860** | **0.99990** | **0.99986** | **0.99990** | **0.99990** |

### Problem 2: Vertical Rate Classification

| Model | Accuracy | F1-Score | Precision | Recall |
|-------|----------|----------|-----------|--------|
| Multinomial Logistic Regression | **0.673** | **0.617** | **0.651** | **0.673** |
| Naive Bayes | 0.596 | 0.445 | 0.355 | 0.596 |

### Feature Importance

| Feature | Coefficient | Impact |
|---------|-------------|--------|
| velocity | 0.42 | Positive |
| baroaltitude | 0.38 | Positive |
| geoaltitude | 0.35 | Positive |
| vertrate | -0.15 | Negative |
| heading | 0.05 | Positive |

##  Tableau Dashboards

The project includes four interactive Tableau dashboards:

1. **Data Quality Overview**: Dataset completeness, missing values, distributions
2. **Model Performance**: Algorithm comparison, feature importance, confusion matrices
3. **Business Insights**: Regional analysis, anomaly detection, recommendations
4. **Scalability Analysis**: Resource usage, cost projections, scaling behavior

##  Technologies Used

- **PySpark 3.4.0**: Distributed data processing and ML
- **Python 3.9**: Core programming language
- **Tableau Public**: Interactive visualizations
- **Pandas/NumPy**: Supplementary data processing
- **Git/GitHub**: Version control

##  Installation & Setup

### Prerequisites
- Python 3.9+
- Java 8 or 11 (for PySpark)
- Git

### Clone the Repository
```bash
git clone https://github.com/YOUR-USERNAME/flight-analytics-pyspark.git
cd flight-analytics-pyspark
