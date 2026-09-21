
# Customer Segmentation & Purchase Prediction

# Project Overview

Customer Segmentation & Purchase Prediction** is a machine learning project based on the **UCI Online Shoppers Purchasing Intention Dataset.

The project analyzes online shopping session behavior to:

* Understand customer browsing patterns
* Perform statistical analysis and Exploratory Data Analysis (EDA)
* Segment customers/sessions based on browsing behavior
* Predict whether an online session will result in a purchase
* Compare multiple machine learning classification models
* Evaluate and validate the models
* Generate business-oriented insights and recommendations

The overall workflow is:

**Data Understanding → Statistical Analysis → EDA → Preprocessing → Customer Segmentation → Purchase Prediction → Model Evaluation → Validation → Business Insights**


# Business Problem

Online businesses receive a large number of website visits, but not every visitor makes a purchase.

Understanding visitor behavior can help businesses:

* Identify different types of shoppers
* Understand browsing and purchasing patterns
* Identify sessions with higher purchase potential
* Improve targeted marketing
* Reduce customer drop-off
* Improve website engagement and conversion
* Design more effective offers and campaigns

This project uses machine learning and data analysis to study these patterns and support data-driven business decisions.


#Dataset

##Dataset Name

**Online Shoppers Purchasing Intention Dataset**

## Source

The dataset is from the **UCI Machine Learning Repository**.

### Target Variable

`Revenue`

The `Revenue` column indicates whether the browsing session resulted in a purchase:

* `True` → Purchase was made
* `False` → No purchase was made

### Important Features

The dataset contains information related to:

* Administrative page visits
* Informational page visits
* Product-related page visits
* Time spent on different types of pages
* Bounce rate
* Exit rate
* Page value
* Month
* Visitor type
* Weekend
* Operating system
* Browser
* Region
* Traffic type
* And other session-related attributes

---

#Technologies Used

### Programming Language

* Python

### Libraries

* Pandas
* NumPy
* Matplotlib
* Scikit-learn

### Development Environment

* Jupyter Notebook
* Visual Studio Code


#Project Structure

```text
Miniproject/
│
├── dataset/
│   └── online_shoppers_intention.csv
│
├── notebook.ipynb
│
└── README.md
```


#Project Workflow

### 1. Data Understanding

The dataset is loaded and inspected using Pandas.

The following operations are performed:

* Load the dataset
* Check number of rows and columns
* Inspect column names
* Check data types
* Check missing values
* Check duplicate records
* Understand categorical and numerical features
* Analyze the target variable `Revenue`

# 2. Statistical Analysis

Statistical analysis is performed on numerical features.

The analysis includes:

* Mean
* Median
* Mode
* Minimum
* Maximum
* Variance
* Standard deviation
* Quartiles
* Interquartile Range (IQR)
* Distribution analysis
* Correlation analysis

These statistics help understand the central tendency, spread, and relationships between variables.


# 3. Exploratory Data Analysis (EDA)

EDA is performed to understand visitor behavior and relationships between different variables.

### Univariate Analysis

Individual variables are analyzed using charts such as:

* Histograms
* Bar charts
* Frequency distributions

Examples include:

* Page visits
* Session duration
* Visitor type
* Month
* Revenue
* Weekend/weekday behavior

### Bivariate Analysis

Relationships between two variables are analyzed.

Examples include:

* Visitor Type vs Revenue
* Month vs Revenue
* Page Values vs Revenue
* Bounce Rate vs Revenue
* Session Duration vs Revenue

### Multivariate Analysis

Multiple variables are analyzed together using:

* Correlation heatmaps
* Box plots
* Scatter plots
* Multiple-variable comparisons

The purpose of EDA is to identify patterns that may be useful for customer segmentation and purchase prediction.


# 4. Customer Segmentation

Customer/session segmentation is performed using clustering techniques.

The objective is to group sessions with similar browsing behavior.

### Features Used for Segmentation

The clustering analysis uses behavioral features such as:

```text
Administrative
Informational
ProductRelated
Administrative_Duration
Informational_Duration
ProductRelated_Duration
BounceRates
ExitRates
PageValues
```

The target variable `Revenue` is not used to create the clusters.

This prevents the purchase outcome from directly determining the customer segments.


#5. Data Preprocessing for Clustering

Before clustering:

1. Relevant features are selected.
2. Missing values are handled.
3. Numerical features are standardized.
4. The processed data is used for clustering.

Standardization is important because the features have different scales.

For example, page counts and duration values may have very different numerical ranges.


# 6. K-Means Clustering

K-Means clustering is used to divide sessions into groups with similar behavior.

The **Elbow Method** is used to determine a suitable number of clusters.

The clustering process includes:

* Testing different values of K
* Calculating inertia
* Plotting the Elbow Curve
* Selecting an appropriate K
* Creating the final clusters
* Analyzing cluster sizes
* Comparing cluster profiles


# 7. Hierarchical Clustering

Hierarchical/Agglomerative Clustering is also applied to the standardized behavioral data.

The results are compared with K-Means to understand whether both approaches produce meaningful and similar customer/session groups.


# 8. Customer Segment Analysis

After clustering, each cluster is analyzed using its average behavioral values.

Important characteristics include:

* Number of product-related pages visited
* Time spent on product pages
* Bounce rate
* Exit rate
* Page value
* Purchase rate

Business-oriented segment names are assigned **after analyzing the actual cluster profiles**.

For example, depending on the actual results, segments may represent patterns such as:

* High-intent shoppers
* Highly engaged visitors
* Quick-exit visitors
* Low-engagement visitors

The final segment names are based on the observed data rather than assumptions.


# 9. Purchase Prediction

The next stage is to predict whether an online shopping session will result in a purchase.

### Target

```text
Revenue
```

### Data Preparation

The following preprocessing steps are performed:

* Handle missing values
* Separate features and target
* Encode categorical variables
* Scale numerical features where required
* Split the data into training and testing sets

The dataset is divided into:

* Training data
* Testing data

A stratified split is used so that the distribution of the target classes is maintained between training and testing data.


## 10. Machine Learning Models

Multiple classification algorithms are trained and compared.

The models include:

### Logistic Regression

Used as a baseline classification model for predicting purchase probability.

### Decision Tree

Creates decision rules by splitting the data based on feature values.

### Random Forest

Uses multiple decision trees to improve prediction performance and reduce the limitations of a single tree.

### AdaBoost

Combines multiple weak learners to create a stronger classifier.

### K-Nearest Neighbors (KNN)

Predicts the class of a session based on nearby observations in feature space.



#  11. Model Evaluation

The classification models are evaluated using multiple metrics.

### Accuracy

Measures the overall percentage of correct predictions.

### Precision

Measures how many sessions predicted as purchases were actually purchases.

### Recall

Measures how many actual purchasing sessions were correctly identified.

### F1 Score

Combines precision and recall into a single metric.

### Confusion Matrix

Shows:

* True Positives
* True Negatives
* False Positives
* False Negatives

### ROC-AUC

Measures the model's ability to distinguish between purchasing and non-purchasing sessions across different classification thresholds.


## Model Comparison

The models are compared using:

```text
Accuracy
Precision
Recall
F1 Score
ROC-AUC
```

The final model is not selected using accuracy alone.

Precision, recall, F1 score, ROC-AUC, and the business cost of incorrect predictions are considered when interpreting model performance.


# 12. Model Validation

Model reliability is analyzed using:

* Training performance
* Testing performance
* Confusion matrices
* Incorrect predictions
* Overfitting analysis
* Underfitting analysis
* Important features
* Cluster validation

Training and testing performance are compared to identify whether a model generalizes well to unseen data.

A large difference between training and testing performance may indicate overfitting.


##  13. Important Features

Feature importance is analyzed to understand which variables contribute strongly to purchase prediction.

Depending on the model, feature importance can be studied using:

* Model coefficients
* Tree-based feature importance
* Other feature-importance techniques

The important features are then connected to the business problem.

For example, browsing behavior, page value, session duration, or other variables may show strong relationships with purchasing behavior.

The final conclusions are based on the actual model results.


# 14. Business Insights

The final stage converts the analytical and machine learning results into business insights.

The analysis focuses on:

* Customer/session behavior associated with purchases
* High-potential customer segments
* Low-engagement sessions
* Browsing patterns
* Visitor types
* Page values
* Product-related browsing
* Marketing opportunities
* Conversion improvement

Recommendations are made based on the findings from:

* Statistical analysis
* EDA
* Clustering
* Classification
* Model evaluation
* Validation


##  Business Recommendations

Depending on the actual findings, businesses can consider strategies such as:

### Targeted Marketing

Target high-potential segments with relevant campaigns and personalized communication.

### Customer Engagement

Improve engagement for sessions showing low activity or high exit/bounce behavior.

### Conversion Optimization

Analyze pages and browsing patterns associated with higher purchase activity and improve the customer journey.

### Personalized Offers

Use customer/session segments to provide more relevant offers and promotions.

### Retention Strategies

Analyze returning visitor behavior and develop strategies to encourage repeat purchases.

The final recommendations should be updated with the actual numerical findings obtained from the project.


#  15. Limitations

Some limitations of the project include:

* The dataset represents online shopping sessions rather than necessarily unique individual customers.
* Clustering results can depend on feature selection and scaling.
* The selected number of clusters can affect customer segmentation.
* Machine learning performance may change when applied to different datasets or future website traffic.
* Correlation and predictive relationships do not necessarily establish causation.
* The target variable represents purchase behavior for the recorded session.
* Business recommendations depend on the quality and representativeness of the available data.


#  16. Future Improvements

Possible future improvements include:

* Hyperparameter tuning
* Cross-validation
* Additional feature engineering
* More advanced classification algorithms
* Gradient Boosting models
* XGBoost or other boosting approaches
* Better cluster validation
* Interactive dashboards
* Real-time purchase prediction
* Customer lifetime value analysis
* Deployment as a web application


#  17. Final Project Outcome

This project follows a complete machine learning workflow:

```text
Data Collection
      ↓
Data Understanding
      ↓
Statistical Analysis
      ↓
Exploratory Data Analysis
      ↓
Data Preprocessing
      ↓
Customer Segmentation
      ↓
K-Means Clustering
      ↓
Hierarchical Clustering
      ↓
Purchase Prediction
      ↓
Classification Models
      ↓
Model Evaluation
      ↓
Model Validation
      ↓
Business Insights
      ↓
Recommendations
```

The project aims to identify meaningful customer/session segments, predict purchase behavior, understand important behavioral factors, and convert the findings into useful business recommendations.


#  How to Run the Project

## 1. Clone or download the project

Place the project folder on your computer.

## 2. Install Python

Make sure Python is installed on your system.

## 3. Install required libraries

Open the terminal in the project directory and run:

```bash
pip install pandas numpy matplotlib scikit-learn jupyter
```

## 4. Open the notebook

Run:

```bash
jupyter notebook
```

or open the project in Visual Studio Code and launch the notebook.

## 5. Add the dataset

Place the dataset inside:

```text
dataset/online_shoppers_intention.csv
```

## 6. Run the notebook

Run the notebook cells in order from:

```text
Data Understanding
        ↓
Statistical Analysis
        ↓
EDA
        ↓
Customer Segmentation
        ↓
Purchase Prediction
        ↓
Evaluation
        ↓
Validation
        ↓
Business Insights
```


#  Project Deliverables

The project includes:

* `notebook.ipynb` — Complete analysis and machine learning implementation
* `README.md` — Project documentation
* Project report
* Project presentation
* Dataset


#  Author

 Reehan Nawaz2124

B.Tech – Computer Science and Engineering

## 
Learning Objectives

Through this project, the following concepts are practiced:

* Data understanding
* Data preprocessing
* Statistical analysis
* Exploratory Data Analysis
* Data visualization
* Feature selection
* Feature scaling
* K-Means clustering
* Hierarchical clustering
* Classification
* Logistic Regression
* Decision Trees
* Random Forest
* AdaBoost
* KNN
* Model evaluation
* Model validation
* Feature importance
* Business analysis
* Data-driven recommendations

