# From-Data-to-Dining-Feature-Selection-and-Rating-Prediction-in-Zomato-Dataset
This project is an **exploratory data analysis (EDA) and predictive modeling exercise** centered on a Zomato dataset, with a particular focus on restaurants operating in Bangalore. Zomato, a prominent Indian food delivery and restaurant review platform, provides detailed information on restaurants, including ratings, costs, cuisines, and customer preferences. The goal of this project is to examine the dataset to identify key factors influencing restaurant ratings, clean and prepare the data for analysis, and build a predictive model to enhance Zomato’s recommendation capabilities.

#### **1. Data Cleaning and Preprocessing:**
   - The dataset initially contained over 51,000 records with multiple columns. Several columns, such as phone numbers, URLs, and reviews lists, were deemed non-informative for analysis and were dropped.
   - Missing values were handled using appropriate techniques. For example:
     - Columns with negligible missing data were filled or dropped.
     - Rating entries such as "NEW" or "-" were standardized to `NaN`.
   - Skewed numerical data, like **Cost (Rupees)** and **Number of Votes**, was transformed using log transformations to normalize distributions.
   - Categorical variables, such as **Cuisines** and **Restaurant Types**, were grouped into generalized categories (e.g., grouping various dessert types into a single “Dessert” category) to improve analysis and reduce noise. 

#### **2. Exploratory Data Analysis (EDA):**
   - **Numerical Analysis:**
     - Analyzed key numeric predictors such as **Cost (Rupees)** and **Number of Votes** using visualizations like histograms, Q-Q plots, and box plots.
     - Found that numeric variables like **Votes** and **Cost** were right-skewed, indicating outliers and high kurtosis, which were addressed through transformations.
   - **Categorical Analysis:**
     - Examined variables like **Online Ordering**, **Reservation Needed**, and **Cuisines** to understand their impact on ratings using box plots and pair plots.
     - Identified that restaurants requiring reservations tend to have higher average ratings, while online ordering did not show a significant impact.
   - **Correlation Analysis:**
     - Built a heatmap to assess relationships between predictors and the target variable, **Rating**.
     - Found significant correlations between **Cost**, **Number of Votes**, and **Rating**.

#### **3. Significant Predictors Identified:**
   - Using techniques like **OLS regression** and p-value analysis, the following predictors were identified as most impactful for predicting ratings:
     1. **Number of Votes**: Highly correlated with higher ratings, indicating popularity contributes to better reviews.
     2. **Cost (Rupees)**: Positively correlated, as more expensive restaurants tend to receive higher ratings.
     3. **Reservation Needed**: Restaurants that require reservations generally have better ratings.
   - Other predictors, such as **Online Ordering**, showed weaker significance but were explored further for their combined effects.

#### **4. Model Development:**
   - Built predictive models using statistical and machine learning approaches:
     - **OLS Regression**: Used to evaluate the relationship between key predictors and ratings.
     - **H2O AutoML**: Automated machine learning models, including **Generalized Linear Models (GLMs)**, were employed to build and evaluate predictive models efficiently.
   - **Model Evaluation Metrics:**
     - Models were evaluated using R² values, which indicated a strong relationship between predictors and the target variable.
     - Checked assumptions like multicollinearity using **Variance Inflation Factor (VIF)** to ensure predictors were independent.

#### **5. Data Insights and Visualizations:**
   - Various visualization techniques were employed to understand data distribution and predictor relationships:
     - Heatmaps and pair plots to examine correlations and trends.
     - Box plots to analyze distributions of categorical variables.
     - Histograms and Q-Q plots to check normality and the effects of transformations.
   - Significant findings included:
     - Restaurants with high costs and reservation requirements generally scored better ratings.
     - Votes strongly influenced ratings, likely reflecting customer satisfaction and engagement.

#### **6. Conclusion and Applications:**
   - The project demonstrated that **Cost (Rupees)**, **Number of Votes**, and **Reservation Needed** are key predictors of restaurant ratings.
   - Insights from this analysis can be used to enhance Zomato’s recommendation system, enabling it to suggest restaurants more accurately based on user preferences.
   - The analysis workflow provides a framework for handling similar datasets, focusing on data cleaning, transformation, and predictive modeling.

#### **7. Tools and Techniques Used:**
   - **Programming Languages and Libraries:**
     - Python: Used for data manipulation, cleaning, and analysis.
     - H2O: Utilized for automated machine learning.
     - Visualization tools: **Seaborn**, **Matplotlib**, and **statsmodels** for statistical analysis and plotting.
   - **Key Techniques:**
     - Statistical methods (e.g., t-tests, p-values) to evaluate predictor significance.
     - Log transformations and normalization for data standardization.
     - Correlation analysis and multicollinearity checks using VIF.
