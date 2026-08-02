# 🤖 Machine Learning Roadmap & Projects

You can find a structured path and hands-on projects about Machine Learning in this repository.

---

## 📂 Repository Structure

* **`0.0-UsedCarsDataset/`**: Advanced Regression & Optimization Case Study (R²: 0.41 ➔ 0.80)
* **`1.1-SimpleLineerRegression/`**: Basics of Simple Linear Regression
* **`1.2-MultipleLineerRegression/`**: Multiple Features & Regression Dynamics
* **`1.3-PolynomialRegression-Pipeline/`**: Non-linear data modeling with Scikit-Learn Pipelines
* **`1.4-AlgerianForestFiresDataset/`**: Classification & EDA on Environmental Data

---

## 🚗 Featured Project: Used Car Price Prediction (From 0.41 to 0.80 R²)

Inside the `00-UsedCarsDataset/` folder, a full optimization pipeline is implemented on a real-world used car dataset.

### 📊 Performance Jump
| Stage | R² Score | Key Bottleneck / Fix |
| :--- | :--- | :--- |
| **Baseline** | **~0.41** | Raw features, extreme outliers present |
| **Optimized** | **~0.797** | High-cardinality encoding, IQR outlier removal, Target log-transform |

### 🔑 Key Engineering Steps
1. **High Cardinality Encoding:** Reduced 250+ unique color/model strings into `Top N + Other` categories to prevent dimensionality explosion.
2. **Feature Engineering:** Built domain-specific interaction terms (`annual_milage` via `milage / car_age`).
3. **Outlier Filtering (IQR):** Removed extreme $1.5M+ hypercars causing high MSE penalty, instantly boosting $R^2$ from 0.33 to 0.72.
4. **Target Transformation:** Applied `np.log1p(y)` to handle right-skewed prices, achieving the final **~0.80 R²**.
