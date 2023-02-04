# Problem Statement
The pet training centre has been experiencing high call and visit volumes by pet owners who seek advice from staff when they need help in handling their pets (cats and dogs in particular) as the current chatbot was not giving relevant information to the customers. Such behaviour results in a waste of manpower resources as the staff had to spend a huge part of their time speaking with pet owners at the centre or over the phone. If the chatbot was able to classify the enquiries accurately and provide relevant information, the bulk of the enquiries could be handled automatically.

As a data analyst at the training centre, I was tasked to improve the existing classifier model used by the chatbot or design a new model with increased accuracy.

# Data Collection & Processing
Data was scrapped from Reddit (r/CatAdvice and r/DogAdvice) using Pushshift API. 5997 data points were collected from r/CatAdvice and 5999 data points were collected from r/DogAdvice.
The data was processed by combining 'title' and 'selftext' (body text) together to analyse the title and body text together. Duplicate entries were dropped. The words were then tokenised, and lemmatised. Lastly, English stopwords, numbers, punctuations, URLs, common words related to the categories e.g. dog, cat, kitten, puppy were removed to avoid having hint words. Other common words that could potentially make the two categories indistinguishable (e.g. month, year, age) were also removed.  

# Exploratory Data Analysis
Common words


Out of the three identified models, the Naive Bayes Bernoulli model on TF-IDF data (green line) is the best performing model with 84% accuracy and AUC of 0.93. The accuracy score difference between training and test data sets is less than 0.1 (0.88-0.84), indicating that there is no overfitting of data. The model also has an F1 score of 0.85, the highest relative to all the models tested - this model has a good balance between high precision and recall compared to the other models. Compared to the baseline model (KNN - TF-IDF), the accuracy (test) has increased by 27% (84%-57%).

# Results
| Model | Data Vectorization | Precision | Recall | F1 Score | Accuracy (Train) | Accuracy (Test) | AUC |
| :-- | :-- | :-- | :-- | :-- | :-- | :-- | :-- |
|**Bernoulli** | **TF-IDF** |0.83|0.87|0.85|0.88|0.84|0.93|
 |**K-NN (Baseline)** | **TF-IDF**|0.54|0.91|0.68|0.64|0.57|0.64|
 | Multinomial | TF-IDF |0.84|0.82|0.83|0.87|0.83|0.92|
 | Logistic | TF-IDF |0.83|0.86|0.85|0.90|0.84|0.92|

Out of the three identified models, the Naive Bayes Bernoulli model on TF-IDF data (green line) is the best performing model with 84% accuracy and AUC of 0.93. The accuracy score difference between training and test data sets is less than 0.1 (0.88-0.84), indicating that there is no overfitting of data. The model also has an F1 score of 0.85, the highest relative to all the models tested - this model has a good balance between high precision and recall compared to the other models. Compared to the baseline model (KNN - TF-IDF), the accuracy (test) has increased by 27% (84%-57%).

# Limitations

- Free text data - misspelt words could affect the word processing (e.g. Lemmatisation) and ultimately, the word count. This is crucial as the predictive models operates on the probabilities of words occurring for the respective categories. If the number of words misspelt and misclassified is huge, the probabilities of the words would be underestimated, and this would have consequential impact on the model's performance.

- The moderation requirements for both subreddits are different and result in data sets of different quality in the content. For instance, the r/CatAdvice moderators are very stringent in controlling the content such that irrelevant or repeated ones were removed. Images were also not allowed. On the contrary, the moderators for r/DogAdvice were less stringent - there were many posts with images only.

# Next Steps
With the best model identified, further tuning (e.g. boosting) could be carried out to further increase the accuracy and evaluate the performance with unseen data with the aim of increasing the accuracy to at least 90%.

# Conclusion
In summary, the new Naive Bayes Bernoulli (TF-IDF) model designed was able to increase the accuracy rate than the existing KNN (TF-IDF) model by 27%, to 84%. This would allow better classification of the queries by the chatbot so that it could pick out relevant responses/information for pet owners without requiring much human intervention. This would help reduce manpower consumption on managing simple queries so that the staff could focus on attending to pets and their owners who are physically present at the pet centre. The chatbot can also help to direct pet owners to specific staff so that their queries can be handled by the relevant personnel.
Footer
© 2023 GitHub, Inc.
Footer navigation
Terms
Privacy
Security
Status
Docs
Contact GitHub
Pricing
API
Training
Blog
About