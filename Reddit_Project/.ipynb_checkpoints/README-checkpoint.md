# Project 3: Web APIs & Classification

## Introduction

The goal was to build a model using Natural Language Processing (NLP) to predit which subreddit a post came from.  Data was scraped from two subreddits using Reddit'API.

The two subreddits chosen were Jokes and Dad Jokes.  While some level of overlap was expected between the subreddits, either literal or just similarity, the goal was to discern if it was possible to differentiate between the two of them.

## Data Collection

A function was created in Python to scrape the subreddits.  Each "scrape" would retrieve 25 posts at a time in json format.  The function was looped through at 40 second intervals to gain the maximum 1000 post.  The function was run a total of 17 times over 4 days to gather a total of 35,829 posts.

## Data Cleaning

After each scrape, a function was run that would convert that would create a data frame and save it as a csv file.  The columns in the data frame were:


| Column Name  | Description                                               |
|--------------|-----------------------------------------------------------|
| id           | A group of letters and numbers that identified each post. |
| num_comments | The number of comments that each post had received.       |
| subreddit    | The name of the subreddit that post had come from.        |
| text         | The body of post.                                         |
| time_created | The UTC time that the posted was created.                 |
| title        | The title of the post.                                    |
| full_text    | A field I created by combining the title and text fields. |

The choice was made not to include comments in the dataframe.  It was determined that they were unnecessary for the analysis.  The title column represented the set up for the joke and the text was the punchline.  The comments did not add anything to jokes that would help differentiate them.

Duplicate posts were removed.  This reduced it to a total of 4,157 posts, 2,509 posts were from the Jokes subreddit and 1,648 were from the Dad Jokes subreddit.  The data was then cleaned to remove most characters that are not letters.  The remaining words were then all converted to lowercase to standarize them.  The subreddit column was converted with Jokes being replaced with 0's and Dad Jokes with 1's.  The cleaned data was saved to a new csv file.

## Modeling

The data was assigned to a new dataframe.  The full_text column was assigned to the predictor variable (X) and subreddit was assigned as the dependent variable (y).  The standard list of English stopwords but excluded contractions.  A count vectorizer was established with a maximum of 2,000 features.  The standard train-test split was applied.

Below are the results of the models that were run:

| Model                | Train Score | Test Score |
|----------------------|-------------|------------|
| Logistic Regression  | 0.85338     | 0.59808    |
| Grid Search          | 0.90728     | 0.61250    |
| Naive Bayes          | 0.71671     | 0.58461    |

## Interpretation and Conclusions

The Logistic Regression and Grid Search models both overfit on the training data relative to the test data.  They both did a better job of predicting the negative case (Joke or 0).  This was expected as the model is bias to the negative case (60% of the actual data were classified as Jokes).  The Naive Bayes model proved to be slightly less accurate.

## Further Work and Follow Up

The models can be further modified by adding more features and lemmantizing words instead of just tokenizing them.  The words man, says, one, i'm, get, said, call, don't, know and got frequently occur in both Jokes and Dad Jokes.  Excluding these words may lead to better models.  What often determines a joke is tone.  In addition, one of the key attributes to a Dad Joke is the use of puns.  Designing a far more advanced model that can detect tone and the use of things like puns would likely produce a model that is better at identifying Dad Jokes.
