# **Exploring Factors of Problematic Internet Use in Children**

# In today's digital age, problematic internet use among children and adolescents is a growing concern, often linked to mental health issues like depression and anxiety. Current methods for measuring problematic internet use are complex and require professional assessments, creating barriers for many families.

Physical fitness indicators, such as posture, diet, and activity levels, are more accessible and can serve as proxies for detecting problematic internet use. Changes in these habits are commonly observed in excessive technology users.

This competition challenges us to develop a predictive model using children's physical activity data to detect early signs of problematic internet use, enabling timely interventions and promoting healthier digital habits.Our work will help children navigate the digital landscape responsibly and lead healthier lives.
# Data preprocessing 
I took many steps for cleaning the data and preparing it for predictive modeling. First, I merged a time-series parquet file with the main CSV dataset using the ID column, utilizing Dask and PyArrow for efficient handling of large datasets. Missing values were imputed based on their distribution: the mean for normally distributed numerical features, the median for skewed ones, and the mode for categorical features. Outliers were handled using the IQR method, replaced with NaN, and imputed similarly to missing values. For feature engineering, numerical columns were normalized with StandardScaler, categorical features were transformed using One-Hot Encoding, and naturally encoded columns were left unchanged. Finally, I applied a ColumnTransformer to streamline preprocessing, ensuring all features were appropriately transformed before feeding them into the model.
# balancing the data
To address class imbalance in the dataset, I applied a combination of SMOTE (Synthetic Minority Over-sampling Technique) and Random Under Sampling using a pipeline. This pipeline first oversamples the minority class using SMOTE and then undersamples the majority class, resulting in a balanced dataset for training.

# prediction 
on the Child Mind Institute dataset, I utilized three classifiers: Gradient Boosting, LightGBM (LGBM), and CatBoost. Among these, CatBoost delivered the highest performance, surpassing the other models in prediction accuracy and proving to be the most effective for this task.
