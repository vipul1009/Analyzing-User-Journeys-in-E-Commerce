## **Analyzing User Journeys in E-Commerce**

### **Overview**
This project analyzes user conversion funnels in an e-commerce platform to understand how user behavior influences conversion rates. Using a dataset containing over **2.7 million user events** and **20 million item property records**, the study explores **challenges in handling large-scale data**, applies **dimensionality reduction techniques**, and compares machine learning models on scaled and unscaled datasets.

### **Dataset**
The dataset used in this project is from **RetailRocket** and consists of:
- **Events Data:** Contains user interactions labeled as `view`, `add to cart`, or `transaction`.
- **Item Properties:** Describes the characteristics of items, such as price, category, and other attributes.

Dataset source: [RetailRocket E-commerce Dataset](https://www.kaggle.com/datasets/retailrocket/ecommerce-dataset/data)

### **Project Structure**
```
│── extraction.ipynb     # Data extraction, preprocessing, and feature engineering
│── modelling.ipynb      # Model training and evaluation
│── main.ipynb           # Main execution script integrating all components
│── The_Outliers_report.pdf  # Detailed report on methodology, results, and insights
│── README.md            # Project documentation
```

### **Key Challenges & Solutions**
#### 1. **High Dimensionality**
- The dataset contains millions of records with multiple features, making model training computationally expensive.
- **Solution:** We applied the **Johnson-Lindenstrauss Lemma (JL Lemma)** for dimensionality reduction, preserving data structure while reducing computational complexity.

#### 2. **Large Data Volume**
- The dataset's size posed memory and processing challenges.
- **Solution:**
  - Handling missing values strategically.
  - Encoding categorical variables numerically.
  - Using **stratified sampling** to create balanced datasets for training.

### **Methodology**
#### **Feature Engineering**
- Extracted relevant features such as **user behavior**, **time of interaction**, and **item properties**.
- The target variable is whether a user completes a purchase within a week of viewing a product.

#### **Hypothesis Testing**
- **Effect of Item Category on Add-to-Cart Rate** (Chi-square test)  
  **Result:** Significant differences found—some categories are more appealing than others.
- **New vs. Returning User Conversion Rates** (Z-test for proportions)  
  **Result:** No statistically significant difference—both user types exhibit similar purchasing behaviors.

#### **Machine Learning Models**
The following models were trained and evaluated:
| Model                 | Accuracy (%) (Unscaled) | Accuracy (%) (Scaled) |
|-----------------------|-----------------------|----------------------|
| Random Forest (RF)    | 66.54                  | 61.69                |
| Gradient Boosting (GBM) | 58.98                | 58.60                |
| Multi-Layer Perceptron (MLP) | 56.62           | 49.58                |

- **Dimensionality Reduction:** Applying the JL Lemma reduced training times by up to **47.8%** with a marginal **2-3% accuracy loss**.

### **Results & Insights**
- **Random Forest** and **Gradient Boosting** performed best, balancing accuracy and efficiency.
- **Dimensionality reduction significantly optimized training time** while keeping accuracy nearly intact.
- **Item categories impact user engagement**, which can help businesses optimize recommendations and marketing strategies.

### **Future Work**
- Explore deep learning models (CNNs, RNNs) for improved predictive performance.
- Investigate **temporal patterns** in user behavior for **personalized recommendations**.
- Enhance feature engineering with **session-based** insights.

### **Contributors**
- **Vipul Mishra**  
- **Abhishek Bansal**


### **References**
- **Dataset:** [RetailRocket E-commerce Dataset](https://www.kaggle.com/datasets/retailrocket/ecommerce-dataset/data)
