# Electricity Generation Data Analysis 🔌⚡

A comprehensive Python-based desktop application for analyzing and visualizing global electricity generation data. This project provides interactive tools for exploring energy production trends, making predictions, and understanding renewable energy consumption patterns across different countries and time periods.

## 📋 Table of Contents

- [Overview](#overview)
- [Features](#features)
- [Installation](#installation)
- [Dependencies](#dependencies)
- [Usage](#usage)
- [Project Structure](#project-structure)
- [Data Requirements](#data-requirements)
- [Visualizations](#visualizations)
- [Machine Learning Models](#machine-learning-models)
- [Contributing](#contributing)
- [License](#license)

## 🌟 Overview

This application analyzes historical electricity generation data from multiple countries, enabling users to:
- Visualize electricity generation vs demand patterns
- Predict future electricity generation using linear regression
- Identify top electricity-producing countries by year
- Explore renewable energy sources (solar, wind, hydro, nuclear)
- Perform clustering analysis on energy consumption data
- View geographical distribution of electricity generation

## ✨ Features

### 1. **Generation vs Demand Analysis**
- Compare electricity generation and demand for specific countries and years
- Visualize renewable energy resource distribution (pie charts)
- Display summary statistics for energy-related metrics

### 2. **Electricity Generation Prediction**
- Machine learning-based predictions using Linear Regression
- Country-specific models trained on historical data
- Interactive visualization of actual vs predicted values

### 3. **Top Countries Analysis**
- Identify the top 5 electricity-producing countries for any given year
- Interactive bar chart visualizations
- Year-by-year comparison capabilities

### 4. **Geographic Visualization**
- World map visualization of electricity generation
- Color-coded countries based on production levels
- Interactive year selection

### 5. **Energy Source Analysis**
- Detailed breakdown of energy sources (fossil, renewable, nuclear)
- Time-series analysis of energy source evolution
- Multi-country comparison capabilities

### 6. **Renewables Consumption Comparison**
- Compare up to 4 countries simultaneously
- Analyze solar, wind, and hydro consumption patterns
- 3D and 2D scatter plots for trend visualization

### 7. **K-Means Clustering**
- Cluster countries based on renewable energy consumption
- 2D and 3D visualization of clusters
- Identify patterns in energy consumption behavior

## 🚀 Installation

### Prerequisites
- Python 3.7 or higher
- pip (Python package installer)

### Step-by-step Installation

1. **Clone the repository**
```bash
git clone https://github.com/sri-ravi13/ELECTRICITY-DATA-ANALYSIS.git
cd ELECTRICITY-DATA-ANALYSIS
```

2. **Create a virtual environment (recommended)**
```bash
python -m venv venv
source venv/bin/activate
```

3. **Install required packages**
```bash
pip install -r requirements.txt
```

4. **Prepare your data**
- Place your `dataset.csv` file in the project root directory
- Ensure the background image `electric-background-ajls9e7ox1fxljz2.jpg` is in the same directory (optional)

5. **Run the application**
```bash
jupyter notebook Electricity.ipynb
```

## 📦 Dependencies

```txt
pandas>=1.3.0
numpy>=1.21.0
matplotlib>=3.4.0
seaborn>=0.11.0
scikit-learn>=0.24.0
geopandas>=0.10.0
Pillow>=8.3.0
tkinter (usually comes with Python)
```

Create a `requirements.txt` file with:
```txt
pandas
numpy
matplotlib
seaborn
scikit-learn
geopandas
Pillow
```

## 💻 Usage

### Running the Application

1. **Launch Jupyter Notebook**
```bash
jupyter notebook
```

2. **Open the notebook**
- Navigate to `Electricity.ipynb`
- Run all cells (Cell → Run All)

3. **Main Interface**
The application will display a GUI window with the following buttons:
- **Generation vs Demand**: Analyze specific country and year
- **Top 5 Countries by Electricity Production**: View rankings
- **Visualize Electricity Generation Map**: Geographic distribution
- **Predict Electricity Generation**: Make future predictions
- **Analyze Energy Sources**: Compare energy source breakdown
- **Analyse Renewables Consumption**: Compare renewable energy usage
- **Cluster**: Perform clustering analysis

### Example Workflows

#### Analyzing a Specific Country
```python
# The GUI will prompt you for:
# 1. Country name (e.g., "United States")
# 2. Year (e.g., 2020)
# Results will show:
# - Electricity generation vs demand
# - Renewable energy breakdown
```

#### Making Predictions
```python
# The GUI will prompt you for:
# 1. Future year (e.g., 2030)
# 2. Country name (e.g., "Germany")
# Results will show:
# - Predicted electricity generation
# - Comparison with historical data
```

## 📁 Project Structure

```
electricity-data-analysis/
│
├── Electricity.ipynb          # Main Jupyter notebook
├── dataset.csv                # Electricity generation data
├── electric-background-*.jpg  # Background image (optional)
├── requirements.txt           # Python dependencies
├── README.md                  # This file
│
└── outputs/                   # Generated visualizations (auto-created)
```

## 📊 Data Requirements

The `dataset.csv` file should contain the following columns:

| Column Name | Description | Data Type |
|------------|-------------|-----------|
| `country` | Country name | String |
| `year` | Year of measurement | Integer |
| `electricity_generation` | Total electricity generated (TWh) | Float |
| `electricity_demand` | Total electricity demand (TWh) | Float |
| `solar_electricity` | Solar energy production (TWh) | Float |
| `wind_electricity` | Wind energy production (TWh) | Float |
| `hydro_electricity` | Hydro energy production (TWh) | Float |
| `nuclear_electricity` | Nuclear energy production (TWh) | Float |
| `solar_consumption` | Solar energy consumption (TWh) | Float |
| `wind_consumption` | Wind energy consumption (TWh) | Float |
| `hydro_consumption` | Hydro energy consumption (TWh) | Float |

### Sample Data Format
```csv
country,year,electricity_generation,electricity_demand,solar_electricity,wind_electricity,hydro_electricity,nuclear_electricity
United States,2020,4286.0,3989.0,112.3,338.0,291.0,790.0
China,2020,7779.0,7506.0,261.0,466.0,1352.0,344.0
```

## 📈 Visualizations

The application generates various types of visualizations:

### 1. **Bar Charts**
- Generation vs Demand comparison
- Top 5 countries ranking

### 2. **Pie Charts**
- Renewable energy source distribution

### 3. **Scatter Plots**
- Prediction visualization (actual vs predicted)
- Clustering results

### 4. **Geographic Maps**
- World map with color-coded electricity generation

### 5. **3D Plots**
- Clustering visualization in 3D space

### 6. **Time Series**
- Energy source evolution over time

## 🤖 Machine Learning Models

### Linear Regression for Prediction
- **Purpose**: Predict future electricity generation
- **Features**: Year
- **Target**: Electricity generation
- **Model**: Separate models trained for each country
- **Scaling**: 2.5x scaling factor applied to predictions

### K-Means Clustering
- **Purpose**: Group countries by renewable energy consumption patterns
- **Features**: Solar, wind, and hydro consumption
- **Clusters**: 3 clusters
- **Preprocessing**: StandardScaler normalization
- **Visualization**: Both 2D and 3D representations

## 🛠️ Customization

### Modifying the Scaling Factor
```python
# In the predict_electricity_generation() function
scaling_factor = 2.5  # Adjust this value as needed
```

### Changing Number of Clusters
```python
# In the cluster_and_visualize() function
kmeans = KMeans(n_clusters=3, random_state=42)  # Change n_clusters
```

### Customizing Colors
```python
# Button colors can be modified in the GUI section
button1 = tk.Button(root, text="...", bg="#008CBA", fg="black", ...)
```

## 🤝 Contributing

Contributions are welcome! Here's how you can help:

1. **Fork the repository**
2. **Create a feature branch**
```bash
git checkout -b feature/AmazingFeature
```

3. **Commit your changes**
```bash
git commit -m 'Add some AmazingFeature'
```

4. **Push to the branch**
```bash
git push origin feature/AmazingFeature
```