# AML Customer Segmentation and Rule Generation Pipeline

This repository contains an end-to-end data science and machine learning pipeline for Anti-Money Laundering (AML) synthetic data generation, customer profile clustering, and risk-rating rule extraction.

## Project Structure

The project is structured as a sequential pipeline of Jupyter notebooks, ordered from minor to major:

1. **`00_data_generation.ipynb`**: Generates synthetic AML transactions, customers, and product tables, simulating real-world financial behavior and demographics within various Colombian municipalities.
2. **`01_data_understanding.ipynb`**: Conducts exploratory data analysis (EDA) on transaction histories, performs regional and product-based aggregations, and saves initial transaction metrics.
3. **`02-1_customer_data_preparation.ipynb`**: Cleans, transforms, and engineers features at the customer level to build a consolidated profile dataset.
4. **`03-1_final_eda_customer.ipynb`**: Validates the final engineered customer features, assesses statistical distributions, checks correlation matrices, and exports clean datasets.
5. **`04-1_clusters_customer.ipynb`**: Applies unsupervised learning (`K-Means` clustering) along with dimensionality reduction (`PCA`) to group customers into behavioral and demographic risk profiles. Evaluates clustering quality using Silhouette and Calinski-Harabasz metrics.
6. **`05-1_customer_rules.ipynb`**: Uses supervised `DecisionTreeClassifier` models to reverse-engineer transparent, highly interpretable business rules for each risk cluster and rating. Exports the final rule sets to Excel.

## Getting Started

### Prerequisites

Ensure you have Python 3.8+ installed in your environment.

### Installation

1. Create a virtual environment:
   ```bash
   python -m venv venv
   ```

2. Activate the virtual environment:
   - **Windows:**
     ```bash
     .\venv\Scripts\activate
     ```
   - **macOS/Linux:**
     ```bash
     source venv/bin/activate
     ```

3. Install the required dependencies:
   ```bash
   pip install -r requirements.txt
   ```

## Dependencies

The project relies on the following key libraries:
- **Data Manipulation**: `pandas`, `numpy`
- **Visualization**: `matplotlib`, `seaborn`, `plotly`
- **Machine Learning**: `scikit-learn`
- **File I/O**: `openpyxl` (Excel support), `pyarrow` (Parquet support)