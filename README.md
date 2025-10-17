# Kindle Book Recommendation System: SVD & Collaborative Filtering 📚

**Project Type:** Unsupervised Machine Learning (Collaborative Filtering / Matrix Factorization)

**Source Dataset:** [Book-Crossing Dataset (Users, Books, Ratings)] - *Link to your Google Drive or the original Kaggle source here.*

## Project Overview
This Capstone project designs and implements a high-accuracy **Collaborative Filtering** recommendation engine using **Singular Value Decomposition (SVD)**. The primary objective was to overcome the inherent **sparsity** and noise of large-scale interaction data to provide personalized book suggestions, thereby maximizing user engagement and book sales for a digital reading platform.

## Skills and Tools
* **Machine Learning:** SVD (Matrix Factorization), Collaborative Filtering, KNN
* **Feature Engineering:** Sparsity Management, User-Item Matrix Construction
* **Statistical Techniques:** Hyperparameter Tuning (GridSearchCV), Cross-Validation, RMSE/MAE Evaluation
* **Programming & Libraries:** Python (Pandas, NumPy, Scikit-surprise)
* **Data Engineering:** Multi-Table Data Integration (Mimicking SQL Joins)

## Methodology and Technical Challenges
The project was structured to handle real-world data complexity:

1.  **Sparsity Management (Data Filtering):** The initial multi-file dataset exhibited extreme sparsity. An aggressive filtering strategy was applied to eliminate over $\mathbf{65\%}$ of non-interactive data, yielding a robust $\mathbf{359,054}$-rating interaction base. This was critical for ensuring model accuracy.
2.  **Feature Engineering:** The data was transformed into a sparse **User-Item Interaction Matrix**, the required input for collaborative filtering.
3.  **Model Selection & Tuning:** Three models were compared (Normal Predictor Baseline, KNNWithMeans, and SVD). **GridSearchCV** was used to meticulously tune the SVD model's parameters ($\mathbf{n\_factors}$, $\mathbf{n\_epochs}$) to achieve peak performance.
4.  **Dimensionality Reduction:** The SVD model inherently performs dimensionality reduction, collapsing the sparse matrix into **Latent Factors** to uncover hidden patterns (e.g., genre preferences).

## Final Model Performance and Choice

The **Tuned SVD Model** was selected as the final model due to its superior performance in handling sparse data and its ability to capture complex user patterns.

| Model | Average RMSE | Average MAE | Key Advantage |
| :--- | :--- | :--- | :--- |
| **Normal Predictor (Baseline)** | $\approx 3.7500$ | $\approx 3.0300$ | Benchmark only |
| **KNNWithMeans (Tuned)** | $3.5427$ | $2.6969$ | Learned neighborhood patterns |
| **SVD (Final Model)** | $\mathbf{3.4965}$ | $\mathbf{2.7178}$ | **Lowest RMSE, captures latent factors** |

## Conclusion and Business Impact
The final **Tuned SVD Model** achieved the lowest $\mathbf{RMSE}$ ($\mathbf{3.4965}$), proving its efficacy in generating accurate rating predictions. This project demonstrates a full-stack ML solution capable of:
* **Reducing Churn:** By minimizing prediction errors (low RMSE), the system builds user trust and loyalty.
* **Driving Discovery:** Uncovering hidden preferences (latent factors) leads to highly personalized book recommendations.
* **Deployment Readiness:** The pipeline is fully documented and structured for easy deployment into a live server environment.

---
