# Capstone-Airbnb-NYC-Market-Analysis-Price-Prediction

![image](https://github.com/user-attachments/assets/f5f42671-65af-4561-ae4b-8c8b9d635a38)


### ✅ **Project Overview**

The goal of this project was to conduct an in-depth analysis of the New York City Airbnb market using publicly available data. I explored the dataset to uncover trends, patterns, and insights that can inform business decisions for hosts, property managers, and investors.

The project focused on:

* 🔍 Data cleaning and preprocessing
* 📈 Exploratory data analysis (EDA)
* 📊 Visualization of key insights
* 🤖 Predictive modeling using machine learning
* 📐 Model comparison with LazyPredict

---

### 🎯 **Key Business Questions**

1. **What are the most popular neighborhoods in NYC for Airbnb rentals?**
2. **How do prices vary across different neighborhoods and room types?**
3. **What factors influence the pricing of Airbnb listings?**
4. **Can we predict the price of an Airbnb listing based on its attributes?**

---

## 📝 **Project Workflow**

### 1️⃣ **Data Loading & Inspection**

* Loaded `listings.csv` dataset (NYC Airbnb listings)
* Initial shape: *\[rows] x \[columns]*
* Selected relevant columns: `price`, `neighbourhood_cleansed`, `room_type`, `review_scores_rating`, `reviews_per_month`, etc.

### 2️⃣ **Data Cleaning**

* Removed dollar signs and commas from `price` and converted to numeric
* Handled missing values:

  * Filled `review_scores_rating` and `reviews_per_month` with median
  * Dropped listings with missing `price`
* Encoded categorical variables using Label Encoding

### 3️⃣ **Exploratory Data Analysis (EDA)**

Key findings:
✅ **Most listings are in Manhattan**, followed by Brooklyn
✅ **Price variation is highest in Sixth Ward**(many luxury listings)
✅ **Entire home/apartment listings are priced higher** than private/shared rooms
✅ **Slight negative correlation** between number of reviews and price (popular listings often cheaper)

👉 Visualizations included:

* Countplot of listings per neighborhood
* Boxplot of price distribution by neighborhood & room type
* Correlation heatmap

---

### 4️⃣ **Feature Engineering & Preparation**

* Selected features for modeling:
  `neighbourhood_encoded`, `room_type_encoded`, `minimum_nights`,
  `number_of_reviews`, `review_scores_rating`, `reviews_per_month`,
  `availability_365`, `calculated_host_listings_count`
* Scaled features with StandardScaler
* Split data: **80% train, 20% test**

---

### 5️⃣ **Modeling & Evaluation**

🔍 Used **LazyPredict** to quickly benchmark multiple regression models.

| Model                 | R² Score | RMSE  |
| --------------------- | -------- | ----- |
| RandomForestRegressor | 0.22     | 91.54 |
| KNeighborsRegressor   | 0.22     | 91.77 |
| ExtraTreesRegressor   | 0.19     | 93.30 |
| LGBMRegressor         | 0.19     | 93.54 |
| BaggingRegressor      | 0.18     | 93.91 |
| (Others lower)        | <0.18    | >94   |

* All models have low R² (highest is 0.22) → means only 22% of price variability is explained by the features.
* RMSE around 91–154 → high error cos the price range is not wide.
* Models didn’t perform very well → underfitting likely.

---

## 💡 **Insights & Recommendations**

* Investors may prioritize **Sixth Ward** and **Second Ward** for high-demand neighborhoods
* Listing an **entire home/apartment commands higher pricing**
* To improve price prediction, future models could include **amenities**, **description text**, **review sentiment**, and **calendar data**

---

## 🚀 **Next Steps**

1. Tune hyperparameters of Random Forest for higher accuracy
2. Use NLP on listing descriptions to extract more predictive features
3. Deploy the model as a **web app** for real-time price estimation

---

## 🗂️ **Files & Repository**

✅ Cleaned dataset saved as `clean_listings.csv`
✅ Jupyter notebook: [`nyc_listing.ipynb`][(http://insideairbnb.com/get-the-data.html)]

---

## 🏆 **Skills Demonstrated**

✅ Data cleaning & wrangling

✅ Exploratory Data Analysis (EDA)

✅ Data visualization (Seaborn, Matplotlib)

✅ Machine Learning with Scikit-learn & LazyPredict

✅ Model evaluation & interpretation

---

