# Car Price Analysis

## Overview
This project analyzes car price data using Python, focusing on statistical operations and data visualization techniques. The goal is to understand the distribution of car prices, detect patterns, and explore relationships using fundamental statistical concepts.

## Dataset
The dataset used in this project is sourced from Kaggle: [Car Price Dataset](https://www.kaggle.com/datasets/asinow/car-price-dataset). It contains car price information that will be analyzed to extract insights. I have picked this publicly available dataset on Kaggle to apply real-world statistical analysis and AI/ML concepts.

## Methodology
The following statistical operations and visualizations were applied to the dataset:

- **Mean, Median, Mode**: Understanding central tendency.
- **Standard Deviation**: Measuring price variation.
- **Histogram**: Visualizing the distribution of car prices.
- **Box Plot**: Identifying outliers in the dataset.
- **Skewness & Kurtosis**: Checking for symmetry and the presence of extreme values.
- **Normal Distribution Curve**: Comparing the dataset with a theoretical normal distribution.

## Implementation
This project was implemented using the following Python libraries:

```python
import pandas as pd
import numpy as np
import seaborn as sns
import matplotlib.pyplot as plt
from scipy.stats import skew, kurtosis, norm
```

### Steps:
1. Load the dataset using Pandas.
2. Perform data cleaning (handling missing values if necessary).
3. Compute statistical measures (mean, median, mode, standard deviation).
4. Visualize data using histograms, box plots, and normal distribution curves.
5. Analyze skewness and kurtosis to assess data distribution.

## Results

- The **mean price** of cars is approximately `8852.96`, while the **mode price** is `2000`, indicating a variation in common price points.
- The **standard deviation** of `3112.59` suggests moderate price variability.
- The **histogram** shows that the price distribution is approximately normal, but with minor deviations.
- The **box plot** highlights the presence of a few high-value outliers.
- **Skewness (0.026)** confirms that the distribution is nearly symmetric.
- **Kurtosis (-0.48)** suggests that extreme outliers are relatively limited.

## Visualizations

### Histogram with Normal Distribution Curve

```python
plt.figure(figsize=(8,5))
sns.histplot(car_dataset['Price'], bins=20, kde=False, color='navy', edgecolor='white', stat='density')

x = np.linspace(car_dataset['Price'].min(), car_dataset['Price'].max(), 100)
y = norm.pdf(x, mean_price, std_price)
plt.plot(x, y, color='red', label="Normal Distribution Curve")

plt.xlabel("Car Price")
plt.ylabel("Density")
plt.title("Car Price Distribution with Normal Curve")
plt.legend()
plt.show()
```

## Conclusion

This analysis provided insights into car price trends using basic statistical techniques. The findings can be useful for:
- Understanding pricing trends in the automobile market.
- Identifying common price ranges and outliers.
- Exploring potential applications in price prediction using AI & ML.

## How to Use This Project
To run this project on your local machine:

1. Clone the repository:
   ```bash
   git clone https://github.com/your-username/car-price-analysis.git
   ```
2. Install dependencies:
   ```bash
   pip install pandas numpy seaborn matplotlib scipy
   ```
3. Run the Python script:
   ```bash
   python analysis.py
   ```

## Future Enhancements
- Adding more advanced ML models for price prediction.
- Exploring correlations with other factors such as mileage, brand, and model year.
- Creating an interactive dashboard for real-time data visualization.

---

For any questions or contributions, feel free to open an issue or submit a pull request! 🚀

