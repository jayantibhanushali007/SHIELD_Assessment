# Section A: How would you accurately predict if a certain app is a VPN app?
This project aims to accurately predict if a certain app is a VPN app using machine learning techniques. The dataset used for this project is the [ISCX VPN-nonVPN Dataset (2016)](https://www.unb.ca/cic/datasets/vpn.html).

## Table of Contents

1. [Initial Understanding of the Problem Statement](#understanding)
2. [Importing & Preparing Data](#import_data)
3. [Exploratory Data Analysis](#eda)
4. [Model Development on Full Data](#model_full)
5. [Model Development on Reduced Data](#model_reduced)
6. [Final Model with Hyperparameter Optimization](#model_final)
7. [Conclusion](#conclusion)
8. [Way Forward](#way_forward)

<a id='understanding'></a>
## Initial Understanding of the Problem Statement

- For SHIELD, one key problem is to address `Early Fraud Detection`. A common sign of a fraudulent device is the use of a VPN to hide its identity and avoid being traced.
- Hence, the problem of 'accurately predicting if a certain app is a VPN app' is an important feature to determine a potential threat (fraud device).

__Use of Public Dataset:__
- The ISCX VPN-nonVPN Dataset (2016) was chosen for this project due to its good documentation and availability in .ARFF format, which can be read directly as a Python DataFrame using Pandas.

__About the Dataset:__
- The dataset includes seven different types of traffic: web browsing, email, chat, streaming, file transfer, VoIP, and P2P.
- The dataset contains both packet-based and time-based features.

<a id='import_data'></a>
## Importing & Preparing Data

- The dataset was read from an ARFF file and converted into a Pandas DataFrame.
- Missing values were checked and handled.
- The target variable was transformed into a binary class (1=VPN, 0=Non-VPN).

<a id='eda'></a>
## Exploratory Data Analysis

- Distribution of the target variable was visualized.
- Boxplots for numerical features with respect to the target variable were created.
- Pairplot to visualize pairwise relationships was generated.
- Correlation heatmap was created to identify highly correlated features.

<a id='model_full'></a>
## Model Development on Full Data

- The dataset was split into training and testing sets (70:30).
- Various machine learning models were trained and evaluated using cross-validation and classification reports.
- Models used: Logistic Regression, Decision Tree, Random Forest, XGBoost, and SVM.

<a id='model_reduced'></a>
## Model Development on Reduced Data

- Highly correlated features were dropped based on a correlation threshold of 0.9.
- The reduced dataset was used to train and evaluate the same set of machine learning models.

<a id='model_final'></a>
## Final Model with Hyperparameter Optimization

- Random Forest was chosen as the final model due to its performance and simplicity.
- Hyperparameter optimization was performed using GridSearchCV.
- The final model was trained with the best parameters and evaluated.

<a id='conclusion'></a>
## Conclusion
The final model resulted in an accuracy of 91%, precision (VPN class) of 88% and recall (VPN class) of 94%. 

The top 5 important features for determining VPN vs. Non-VPN traffic are:
1. **total_biat (Total Backward Inter-Arrival Time)**
2. **min_flowiat (Minimum Flow Inter-Arrival Time)**
3. **flowBytesPerSecond (Number of Flow Bytes per Second)**
4. **total_fiat (Total Forward Inter-Arrival Time)**
5. **max_flowiat (Maximum Flow Inter-Arrival Time)**

<a id='way_forward'></a>
## Way Forward

- The learnings from this dataset can be used to develop a new model or integrate it with an existing model.
- Other factors that can help identify if the app is VPN or Non-VPN:
    - App Metadata Analysis
    - Permissions Analysis
    - System APIs Used
- Depending on the north star metric (speed or quality), we can deploy an ML or heuristic approach to detect VPN traffic and prevent potential fraud from those devices.

#############################################################################

# Section B: Given a pool of data of mobile device information that these users are using ie. Brand, model, design a model to determine the eligibility of individuals for obtaining a loan using device data. Take into account that not all device attributes are readily available all the time and there is no historical data available.

This project aims to determine the eligibility of individuals for obtaining a loan using mobile device data. The dataset includes information about mobile device usage, such as brand, model, app usage time, screen on time, battery drain, number of apps installed, data usage, and user behavior class. The goal is to leverage this data to infer the economic status of individuals and assess their loan eligibility.

## Problem Statement
Traditional creditworthiness data sources are often unavailable or insufficient, creating challenges for lenders. This project addresses the `Cold-Start Problem` in machine learning by using mobile device attributes as a proxy for an individual’s economic status. By analyzing these attributes, lenders can make informed lending decisions with reasonable confidence.

## Datasets
- **Mobile Usage Behaviour Dataset**: [Kaggle](https://www.kaggle.com/datasets/valakhorasani/mobile-device-usage-and-user-behavior-dataset)
- **Mobile Price Dataset**: [Kaggle](https://www.kaggle.com/datasets/rkiattisak/mobile-phone-price)

## Approach
1. **Data Import and Preparation**: Import and clean the datasets, merge them based on brand and model.
2. **Exploratory Data Analysis (EDA)**: Analyze the data to understand the distribution and relationships between variables.
3. **Hypothesis Testing**: Design and test hypotheses to determine the correlation between mobile device attributes and loan eligibility.

## Key Findings
- The data was limited and skewed with just 5 unique devices, making it difficult to distinctly observe the difference between mobile price and usage behavior.
- With more data points, this methodology can be effectively tested to assess loan eligibility based on mobile device attributes.

## Way Forward
- Design hypotheses and use collected information or external datasets to perform hypothesis testing.
- Potential hypotheses include:
    1. Higher-priced mobile devices are positively correlated with higher loan eligibility.
    2. Users with newer devices indicate better financial capacity.
    3. Users of premium brands are more likely to have higher loan eligibility.
    4. Users with high productivity and finance app usage are more likely to have better financial management.
    5. Users owning devices with high market share tend to have more predictable financial behaviors.

## Conclusion
This project demonstrates the potential of using mobile device attributes to determine loan eligibility. While the current dataset is limited, the methodology can be applied to larger datasets to make informed lending decisions.


## Contact

- **Jayantilal Bhanushali**
    - Email: jay4datascience@gmail.com
    - LinkedIn: [Jayantilal Bhanushali](https://www.linkedin.com/in/jayantilalb)
