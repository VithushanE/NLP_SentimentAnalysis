# NLP_SentimentAnalysis

For this project, I developed a sentiment analysis model using various supervised machine learning algorithms to classify customer reviews. 

The dataset consists of movie theater reviews, with each entry containing two columns: the first column includes the text of the review (unstructured data), while the second column contains a binary rating (1 or 0), likely indicating whether the review is positive or negative. Below is an outline of the approach I followed to build and evaluate the model.


## Step 1: Data Exploration
After installing the necessary libraries and uploading the training and testing datasets, I began with an initial exploration of the data. This allowed me to understand the structure, quality, and distribution of the data. By examining the "Sentence" and "Polarity" columns, I gained insights into the text data (reviews) and their corresponding sentiment labels, which would guide further preprocessing and modeling decisions.

## Step 2: Modeling with Different Machine Learning Algorithms
Next, I developed a machine learning pipeline that incorporated a variety of algorithms to predict sentiment. To prepare the data, I first split the dataset into training and testing sets. I performed this split for both the "Sentence" (features) and "Polarity" (target variable) columns. The "Polarity" column, which contains the sentiment labels (positive or negative), was used as the target variable, while the "Sentence" column provided the textual data for feature extraction.

The machine learning algorithms included in the pipeline were:

Logistic Regression (with L2 regularization),
Decision Tree Classifier,
XGBoost,
CatBoost,
Random Forest Classifier.
These algorithms were chosen for their versatility in handling text data and their ability to deliver strong performance in classification tasks.

## Step 3: Assessing Machine Learning Models
After training each model using the defined pipeline, I evaluated their performance through a series of metrics, focusing primarily on the confusion matrix to examine the model's classification accuracy. This step allowed me to compare the performance of each model on both the training and testing datasets.

The use of a train/test split was crucial to avoid data leakage, ensuring that the evaluation results were unbiased and reflective of the model's ability to generalize. Despite efforts to tune the models, I found that some models exhibited signs of data leakage, highlighting the importance of careful preprocessing and cross-validation to ensure robust model performance.

## Step 4: Logistic regression with different Hyperparameter Tuning Combinations 

Ultimately, I found logistic regression to be the best performing model. I decided to go deeper by creating another ML pipeline, but this time specifcally looking at lasso, ridge and elasticnet within logistic regression. I also created separate grid search parameters for each regression and assessed each. Ultimaately, Ridge regression was the best out of all the logistic regression variations. 

## Step 5: Examining results from a business point of view

The high F1 and accuracy scores on the training data indicate that the model learned from the training dataset very well. However, the drop in performance on the test dataset suggests that the model may not perform as well on unseen data, potentially due to overfitting. Hyperparameter tuning was applied to the best model after comparing it with other models.

From a business standpoint, it is reasonable to assume that some customer feedback could be misinterpreted by the model, possibly due to variations in customers' grammar or the use of sarcasm. Given these considerations, I am satisfied with an overall accuracy of 0.76 on the testing dataset for the ridge model.

## Step 6: Visualizing Correct predictions with Label 0 and 1

<img width="798" alt="Screenshot 2024-11-18 at 12 43 29 PM" src="https://github.com/user-attachments/assets/2bd5e692-c8b1-4e44-88d2-e0eae6e02dd3">


The model's inaccuracies may be attributed to the complexities of the english language. For example, sarcasm in customer reviews can affect the true sentiment, making it challenging for the model to correctly classify them as positive or negative. Additionally, certain words may appear in both positive and negative contexts, potentially leading to misclassifications. These factors highlight the complex nature of language and its impact on model performance
