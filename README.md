# Hyperparameter Tuning with Grid Search

## Optimizing a K-Nearest Neighbors Classification Model

This project demonstrates **Hyperparameter Tuning using Grid Search** on a Sales Analysis dataset.

A **K-Nearest Neighbors (KNN)** classification model is trained to predict the **Customer Segment** based on sales-related features. `GridSearchCV` is used to systematically test different combinations of KNN hyperparameters and identify the configuration that provides the best cross-validation performance.

---

## Project Objective

The main objective of this project is to:

* Build a KNN classification model.
* Prepare and preprocess the Sales dataset.
* Standardize numerical features.
* Apply Grid Search with cross-validation.
* Optimize KNN hyperparameters.
* Compare default KNN with tuned KNN.
* Evaluate the optimized model.
* Visualize model performance.
* Save the trained model for future predictions.

---

## Dataset

The project uses the **Sales_Data** sheet from the Sales Analysis Excel dataset.

Important columns include:

* `Order_ID`
* `Order_Date`
* `Customer_Name`
* `Customer_Segment`
* `Product_Name`
* `Category`
* `Sub_Category`
* `Region`
* `Quantity`
* `Unit_Price`
* `Discount`
* `Sales`
* `Profit`
* `Payment_Method`
* `Year`
* `Month`
* `Month_Number`
* `Quarter`
* `Profit_Margin`

### Target Variable

The target variable is:

```text
Customer_Segment
```

The model predicts the customer segment based on selected sales-related features.

---

## Features Used

The following six numerical features are used:

```text
Quantity
Unit_Price
Discount
Sales
Profit
Profit_Margin
```

These features are standardized before being provided to the KNN model.

---

## Machine Learning Algorithm

### K-Nearest Neighbors

KNN is a supervised machine learning algorithm that classifies a data point based on the classes of its nearest neighboring data points.

In this project, KNN is used for multi-class classification of customer segments.

---

## Hyperparameter Tuning

Grid Search is used to find the best combination of KNN hyperparameters.

### Parameters Tuned

| Hyperparameter | Values Tested        |
| -------------- | -------------------- |
| `n_neighbors`  | 3, 5, 7, 9, 11, 15   |
| `weights`      | uniform, distance    |
| `metric`       | euclidean, manhattan |

A total of:

```text
6 × 2 × 2 = 24
```

hyperparameter combinations are tested.

### Cross-Validation

The project uses:

```text
5-Fold Cross-Validation
```

The combination with the highest mean cross-validation accuracy is selected as the best configuration.

---

## Project Workflow

```text
Sales Dataset
       ↓
Load Sales_Data Sheet
       ↓
Data Cleaning
       ↓
Feature Selection
       ↓
Target Encoding
       ↓
Train-Test Split
       ↓
Feature Standardization
       ↓
KNN Model
       ↓
GridSearchCV
       ↓
Hyperparameter Optimization
       ↓
Best KNN Model
       ↓
Model Evaluation
       ↓
Visualization
       ↓
Model Saving
       ↓
New Customer Prediction
```

---

## Model Evaluation

The optimized KNN model is evaluated using:

* Accuracy
* Precision
* Recall
* F1-Score
* Confusion Matrix

The project also compares:

```text
Default KNN
      vs
Tuned KNN
```

This comparison demonstrates whether hyperparameter tuning improves model performance.

---

## Visualizations

The project generates the following visualizations:

### 1. Confusion Matrix

Shows correctly and incorrectly classified customer segments.

### 2. Default vs Tuned KNN Accuracy

Compares the performance of the default KNN model with the optimized model.

### 3. KNN Performance for Different K Values

Shows how cross-validation accuracy changes with different values of `n_neighbors`.

### 4. Tuned Model Performance Metrics

Visualizes:

* Accuracy
* Precision
* Recall
* F1-Score

---

## Model Files

The trained model and preprocessing components are saved as:

```text
models/
├── best_knn_model.pkl
├── scaler.pkl
└── label_encoder.pkl
```

### `best_knn_model.pkl`

Contains the optimized KNN classifier selected by Grid Search.

### `scaler.pkl`

Contains the `StandardScaler` used to standardize input features.

### `label_encoder.pkl`

Contains the encoding information used to convert customer-segment labels between text and numerical values.

---

## Grid Search Results

The complete Grid Search results are saved as:

```text
results/grid_search_results.csv
```

This file contains the tested hyperparameter combinations and their cross-validation performance.

---

## Example Prediction

After training, the saved model can be used to predict the customer segment of a new sales record.

Example input:

```text
Quantity       = 5
Unit_Price     = 1000
Discount       = 0.10
Sales          = 4500
Profit         = 900
Profit_Margin  = 20
```

The trained model returns the predicted customer segment.

---

## Technologies Used

* Python
* Pandas
* NumPy
* Matplotlib
* Seaborn
* Scikit-learn
* Joblib
* Google Colab
* Jupyter Notebook

---

## Project Structure

```text
Hyperparameter-Tuning-GridSearch/
│
├── README.md
├── requirements.txt
│
├── data/
│   └── Sales_Analysis.xlsx
│
├── notebooks/
│   └── Hyperparameter_Tuning_GridSearch.ipynb
│
├── models/
│   ├── best_knn_model.pkl
│   ├── scaler.pkl
│   └── label_encoder.pkl
│
└── results/
    └── grid_search_results.csv
```

---

## Installation

Clone the repository:

```bash
git clone <your-repository-url>
```

Move into the project directory:

```bash
cd Hyperparameter-Tuning-GridSearch
```

Install the required libraries:

```bash
pip install -r requirements.txt
```

---

## Running the Project

The project can be executed using Google Colab or Jupyter Notebook.

Open:

```text
notebooks/Hyperparameter_Tuning_GridSearch.ipynb
```

Upload the Sales Analysis Excel dataset and run the notebook cells sequentially.

---

## Key Learning Outcomes

Through this project, the following concepts are demonstrated:

* Supervised Machine Learning
* Classification
* K-Nearest Neighbors
* Feature Selection
* Label Encoding
* Train-Test Split
* Feature Scaling
* Cross-Validation
* Hyperparameter Optimization
* Grid Search
* Model Evaluation
* Confusion Matrix
* Model Persistence
* Prediction using a Saved Model

---

## Conclusion

This project demonstrates how **Grid Search can be used to optimize machine learning hyperparameters**.

Instead of manually selecting KNN parameters, multiple combinations are systematically evaluated using cross-validation. The best-performing configuration is then selected and evaluated on unseen test data.

The optimized model can subsequently be saved and reused for making predictions on new data.

---

## Author

**Sana Kishore**

Third-Year Computer Science / Data Analytics Student

---

## License

This project is intended for educational and academic purposes.
