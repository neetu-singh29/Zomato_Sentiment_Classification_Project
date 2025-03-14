✅ **Project Summary :**

This project is aimed at analyzing customer reviews and restaurant metadata from Zomato to perform **Sentiment Classification and Restaurant Clustering. Using both Supervised and Unsupervised Machine Learning techniques**, the project explores how customers perceive different restaurants and how restaurants can be segmented based on key features such as cost, rating, cuisine variety, and customer feedback.

* We used **two** datasets:
1. **Zomato Restaurant Names & Metadata** (contains restaurant-specific information like cost, cuisines, collections, timings, etc.).
2. **Zomato Restaurant Reviews** (contains user reviews, ratings, metadata, time, and more).

📊 **Data Exploration & Preprocessing:**
* First, we merged both datasets on **Restaurant Name**, resulting in a consolidated dataset containing both review text and restaurant-specific metadata.
* Missing values were handled appropriately:
 * **Numerical columns**(e.g., Cost, Ratings, Pictures) filled with **median** values.
 * **Categorical columns** filled with mode or placeholders.
* Outliers in `Cost` were treated using the Interquartile Range (IQR) method.
 * **Feature engineering was applied to create new columns like:**
 * **`review_length`**: Number of characters in the review.
 * **`cuisine_count`**: Number of cuisines a restaurant offers.
 * **`Hour`**: Extracted review time hour.
 * **`review_word_count`**: Total words in each review.
* Textual reviews were cleaned using NLP steps including **lowercasing, punctuation removal, stopword removal, lemmatization**, and vectorized using **TF-IDF** for ML modeling.

📈 **Visualization & EDA (15+ charts):**

Following **UBM (Univariate, Bivariate, Multivariate)** analysis:

*  **Univariate**: Histograms for cost and review lengths, count plots for cuisine counts.
*  **Bivariate**: Boxplots, violin plots, scatter plots to analyze relationships between cost, ratings, and review length.
*  **Multivariate**: Heatmaps and pairplots to explore feature correlations.
* **Word clouds** generated to highlight frequently used terms in reviews.

* **Insights:**
* Cost and reviews are moderately correlated.
* North Indian and Chinese cuisines dominate.
* High-rated restaurants usually maintain moderate costs.
* Review lengths are longer for higher-cost restaurants, indicating detailed feedback.

**Sentiment Analysis:**

**TextBlob** is used to perform sentiment analysis on customer reviews, categorizing them as **`Positive, Negative, or Neutral`**. This analysis provides a deeper understanding of customer perceptions and overall satisfaction levels.


🔍 **Hypothesis Testing:**

We formulated and tested three key business-related hypotheses:

1. High-cost restaurants receive higher ratings.
2. Restaurants with more cuisines tend to receive longer reviews.
3. Rating distribution is independent of the restaurant collections type.

Using **ANOVA and Chi-square tests**, we rejected/accepted hypotheses based on p-values and statistical significance.

⚙️ **Feature Selection & Engineering:**
* Important features for modeling: **`Cost_log`, `Rating`, `cuisine_count`, `review_length`, `review_word_count`, `Hour`**.
* Data scaled using **StandardScaler** for optimal model performance.

🤖 **Machine Learning Models & Tuning:**

Three models were trained and evaluated:

1. **Logistic Regression (Baseline model)**
* Accuracy: 73.4%
* Precision: 85.2%

2. **Random Forest Classifier (Best Performing Model)**
* Initial Accuracy: 82%, F1-score: 83%
* After tuning (GridSearch): Accuracy improved to 82.6%, F1-score to 83.4%.

3. **SVM (Support Vector Machine)**
* Initial Accuracy: 73.7%
* After tuning: Improved to 74.8%.

📊 **Evaluation Metrics for Business Impact:**
* **Precision:** Ensures correct sentiment identification, important for user satisfaction.
* **Recall:** Ensures no sentiment (especially negative) is missed.
* **F1-Score:** Balanced metric for imbalanced datasets.
* **Accuracy:** Overall correctness of model predictions.

✅ **Final Model & Deployment Readiness:**
* **Random Forest Classifier (Tuned)** selected as final model.
* Saved as **pickle file** for deployment.
* Successfully tested on **unseen data**.
* Ready for real-time prediction deployment via Flask/FastAPI APIs.

🚀 **Business Value:**
* **Actionable insights** for restaurant owners to improve offerings.
* **Sentiment analysis** helps Zomato tailor personalized recommendations and improve user retention.
* Targeted marketing based on real-time sentiment trends.

**A. The Supervised Learning part (Sentiment Analysis)** focuses on predicting whether a customer's sentiment toward a restaurant is **Good, Average, or Poor** based on their review content. We used **TF-IDF Vectorization** for review text and applied **Logistic Regression, Random Forest, and SVM models** to classify sentiments.

**B. The Unsupervised Learning part (Restaurant Clustering)** segments restaurants into meaningful groups using **KMeans Clustering** based on numeric and derived features such as Cost (log-transformed), Cuisine count, Review length, and Rating. Clusters were analyzed to identify potential market segments.

**Key achievements:**

* Successfully built and tuned Sentiment Classification models.
* Clustered restaurants into interpretable groups based on customer preferences and restaurant attributes.
* Delivered actionable insights that can guide Zomato and restaurants in marketing and service improvements.
