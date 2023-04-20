# Sentiment Analysis of Dating App Reviews

The dating app industry is growing, but there seem to be a lot of negative sentiments around dating apps. I'm using a dataset of Tinder, Bumble, and Hinge reviews to break down these positive and negative feelings. My final Linear SVC model was able to get an 87% accuracy.

![datingappetiquette_Prancheta-1-1.png](attachment:datingappetiquette_Prancheta-1-1.png)

### Business Understanding and Data Understanding

There were 366 million dating app users in 2022, up from 324 million in 2021, so this $4.3 billion dollar industry is continuing to grow. However, 88% of users are disatisfied with what they find on dating apps and they have been touted as one of the main causes of depression, anxiety, stress, and body dissatisfaction. Where are all these apps going wrong and what can they be doing better? Based on reviews, is the sentiment around the top dating apps truly this negative?

To dig deeper into this, I am using a dataset from Kaggle, which contains about 682,000 reviews from 2017-2022 on Tinder, Bumble, and Hinge. Each row of this dataset included the name of the reviewer, the review, their rating, whether other users "thumb's up-ed" their review, the date and time, and the app they were reviewing.

Before jumping into modeling, I had to use NLP to pre-process the review data. So I changed the reviews to strings, split the deliminator, tokenized the data, flattend the corpus, removed stop words, and normalized the data. Then I used a Wordnet lemmatizer and count vectorized the data. Now we are ready to run our models!

### Modeling and Evaluation

I started off with a simple logistic regression as our baseline, because it is relatively easy to implement and can provide good accuracy for binary classification problems like sentiment analysis. However, because of it's limitations, assuming that the relationship between the input features and the output variable is linear, the accuracy of the model only hit a 55%.

For my second model I went with a Multinomial Naive Bayes (NB) classifier, as it can be a good option for sentiment analysis, especially when working with text data. The algorithm is also simple and efficient and can handle high-dimensional sparse data well. This model ended up doing significantly better than the logistic regression and jumped us up to an 85% accuracy score.

After this jump, I ran a Naive Bayes, which got us up to 86%, then a Linear SVC which stuck at 87%, after that I tried a Random Forest which gave me the same result, then a Gradient Boost which dropped us down to 80%, and finally a Recurrent Neural Network (RNN) which bumped us back up to an 88%, my highest score, but it took significantly longer to run.

So for my final model, I decided to go with the Linear SVC as it works well on high-dimensional datasets and is known for its ability to handle sparse data, plus can also be used for binary and multi-class classification tasks, making it a versatile model for sentiment analysis. It had also given me a pretty high accuracy score of 87%, but at a much faster rate than the RNN, and gave high precision (0 = 84%, 1 = 89%), recall (0 = 87%, 1 = 87%), and f1 (0 = 86%, 1 = 88%) scores. So compared to my baseline it was a significant improvement!


### Conclusion

I would reccomend that this model be used to predict the sentiment (positive = 1 or negative = 0) of new reviews. ANd once I can get the deployment to work properly it could be used to determine the appropriate dating app for users.

Some next steps that I would like to take to take this project further:
- Explore reviews and their sentiment further
    Are there other external factors, such as the global pandemic in 2020, that are affecting these reviews?
    Want to look at the timing of the majority to guage this.
    Or is it even based on location?
    Etc
- Translating non-English reviews
- Dig into other apps
    Explore untraditional dating style apps such as Feeld, Pure, etc.
    How do their reviews/ sentiments compare?
- Build out deployment

### Repository Navigation

In my repository you will find:
- .gitignore
- Dating App Sentiment Analysis.pdf, my presentation on this project
- DatingAppReviewsDataset.csv, which is the dataset used for this project
- Dating_Apps.ipynb, the notebook of work for this project
- this README.md

### Links
![Dating_App_Sentiment_Analysis.pdf](/Users/aheinke/Documents/Flatiron/Dating_App_Sentiment/Dating_App_Sentiment_Analysis.pdf)
![Dating_Apps.ipynb](/Users/aheinke/Documents/Flatiron/Dating_App_Sentiment/Dating_Apps.ipynb)