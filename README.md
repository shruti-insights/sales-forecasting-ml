# 🛒 Sales Prediction Using Machine Learning

A comprehensive machine learning project that predicts sales amounts using customer demographic data, product information, and purchasing behavior patterns.

## 📊 Project Overview

This project analyzes sales data from 11,251 customer transactions to build a predictive model for sales forecasting. Using advanced feature engineering and XGBoost regression, the model achieves an impressive **R² score of 0.9991**, demonstrating excellent predictive accuracy.

## 🎯 Key Findings

### Customer Insights
- **Gender Impact**: Female customers generate ₹161M in sales (2.3× more than males)
- **Age Demographics**: 26-35 age group leads with ₹94M+ in sales
- **Target Segment**: Unmarried females represent the most profitable customer segment
- **Geographic Leaders**: Maharashtra, Uttar Pradesh, and Karnataka drive highest sales volumes

### Product Performance
- **Top Category**: Food products dominate with ₹73M in sales and 5,482 orders
- **Volume Leader**: Clothing & Apparel leads in order volume (6,452 orders)
- **Professional Focus**: IT, Healthcare, and Aviation professionals are high-value customers

## 🛠️ Technologies Used

- **Python 3.12**
- **Data Analysis**: Pandas, NumPy
- **Visualization**: Matplotlib, Seaborn
- **Machine Learning**: XGBoost, Scikit-learn
- **Feature Engineering**: Custom transformations and categorical encoding

## 📁 Dataset Information

- **Size**: 11,251 rows × 14 columns
- **Target Variable**: Total Sales Amount (log-transformed)
- **Features**: Customer demographics, product categories, geographic data, order history

### Key Features
- Customer ID, Name, Age, Gender, Marital Status
- Geographic: State, Zone
- Professional: Occupation
- Product: Category, Orders, Amount
- Target: Total Sales Amount

## 🔧 Data Preprocessing

### Data Cleaning
- Handled 12 missing values in the Amount column
- Removed outliers using IQR method for sales amount, orders, and age
- Final cleaned dataset: 10,591 rows

### Outlier Removal Process
1. **Sales Amount**: Removed extreme values using 1.5×IQR rule
2. **Orders**: Applied IQR filtering for order count
3. **Age**: Cleaned age-based outliers

## ⚙️ Feature Engineering

Created 23 new engineered features to improve model performance:

### Customer Behavior Features
- `avg_order_value`: Average spending per order
- `amount_per_age`: Spending relative to age
- `spending_efficiency`: Total sales relative to age

### Categorical Encoding
- `age_group_encoded`: Numerical encoding of age groups
- `zone_encoded`: Geographic zone encoding

### Customer Segmentation
- `high_value_customer`: Top 25% by sales amount
- `frequent_buyer`: Top 25% by order frequency
- `big_spender`: Top 25% by individual purchase amount

### Advanced Features
- Product category statistics (average amounts, orders)
- State-wise performance metrics
- Age interaction features
- Relative performance indicators

## 🤖 Model Development

### Algorithm Selection
**XGBoost Regressor** was chosen for its:
- Excellent performance with tabular data
- Built-in categorical feature handling
- Robust handling of missing values
- Feature importance insights

### Hyperparameter Optimization
Used RandomizedSearchCV with 50 iterations and 5-fold cross-validation:

```python
Best Parameters:
- n_estimators: 500
- max_depth: 5
- learning_rate: 0.15
- subsample: 0.7
- reg_alpha: 0.5
- reg_lambda: 5
```

## 📈 Model Performance

### Final Results
- **R² Score**: 0.9991 (99.91% variance explained)
- **RMSE**: 0.0253
- **MAE**: 0.0145
- **Cross-validation**: 0.9989 ± 0.0002

### Performance Improvement
| Metric | Baseline | Enhanced | Improvement |
|--------|----------|----------|-------------|
| R² Score | 0.9877 | 0.9991 | +1.16% |
| RMSE | 0.0943 | 0.0253 | +73.18% |
| MAE | 0.0392 | 0.0145 | +63.01% |

## 🔍 Feature Importance

Top 5 most important features:
1. **high_value_customer** (57.9%) - Customer value segmentation
2. **spending_efficiency** (30.8%) - Age-adjusted spending patterns
3. **total_vs_amount_ratio** (2.7%) - Sales relationship metrics
4. **Age** (2.3%) - Customer age
5. **Orders** (1.8%) - Order frequency

## 📊 Exploratory Data Analysis

### Key Visualizations
- Gender-based sales distribution
- Age group analysis with purchase patterns
- State-wise sales performance
- Product category revenue breakdown
- Marital status impact on spending
- Occupation-based customer segmentation

### Business Insights
- **Marketing Focus**: Target unmarried females aged 26-35
- **Geographic Strategy**: Concentrate on Maharashtra, UP, Karnataka
- **Product Strategy**: Expand Food category offerings
- **Professional Targeting**: Focus on IT, Healthcare, Aviation sectors
