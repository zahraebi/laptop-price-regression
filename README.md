# Laptop Price Regression Project

This project performs a comparative analysis of different regression models (simple linear, multiple linear, and polynomial regression) to predict laptop prices based on a dataset of hardware specifications. It evaluates and visualizes the performance of each model to determine which regression approach best fits the data.



## Dataset

The dataset used in this project contains specifications and prices of various laptops. Key features include:

- Manufacturer
- GPU
- CPU_core
- Screen_Size_inch
- CPU_frequency
- RAM_GB
- Storage_GB_SSD
- Weight_pounds
- Screen-Full_HD (binary feature)

The dataset is originally from [IBM Skills Network](https://coursera.org/projects/data-analysis-python) (used in IBM Data Science courses on Coursera).
##   Models Compared

The following models were implemented using `sklearn.pipeline.Pipeline`:

| Model                                  | Features Used       | Notes                      |
|---------------------------------------|----------------------|----------------------------|
| Simple Linear Regression              | CPU_frequency only   | One feature                |
| Multiple Linear Regression            | All selected features| One-hot encoding applied   |
| Polynomial Regression (deg=3, simple) | CPU_frequency only   | Overfitting observed       |
| Polynomial Regression (deg=5, simple) | CPU_frequency only   | Slightly better than linear|
| Polynomial Regression (deg=3, multi)  | All features         | Performed very poorly      |

---

##   Evaluation Results

All models were evaluated using:

- Mean Squared Error (MSE)
- R-squared score (R²)

| Model                            | MSE         | R² Score     |
|----------------------------------|-------------|--------------|
| Simple Linear Regression         | 239,036     | -0.037       |
| Multiple Linear Regression       | 172,995     | 0.249        |
| Simple Polynomial Regression (3) | 10,877,124,056 | -47195.615 |
| Simple Polynomial Regression (5) | 207,336     | 0.100        |
| Multi Polynomial Regression (3)  | 10,877,124,056 | -47195.615 |

  **Conclusion:**  
Multiple Linear Regression performed best in terms of MSE and R².  
Polynomial models showed **severe overfitting**, especially with multiple variables.

---
 
##   Used Tools & Libraries

- Python 3.10+
- pandas
- numpy
- matplotlib
- seaborn
- scikit-learn

## How to run

1. Load dataset from `data/laptop_pricing_dataset_mod2.csv`.
2. Run the Jupyter notebook in `notebooks/laptop_price_analysis.ipynb`.
3. Models are trained using scikit-learn pipelines.

## Author

Zahra

🔖 License
This project is for educational purposes only. Dataset provided by IBM Skills Network.
