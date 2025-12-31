# Fake News Detection

Misinformation is a huge problem online, so I wanted to see if I could build a tool that actually understands the linguistic difference between real reporting and "fake" news. This project uses Natural Language Processing (NLP) to classify articles based on their text content.

Why I chose the Passive Aggressive Classifier:
While many people use basic Naive Bayes for this, I decided to implement a Passive Aggressive Classifier.

Passive: If the prediction is correct, the model keeps the current weight.

Aggressive: If the prediction is wrong, it makes a massive update to correct itself. This makes it incredibly effective for high-dimensional data like news articles, where the vocabulary is huge.

How it works:
The Data: I used a dataset of labeled news articles (REAL vs FAKE).

Vectorization: I implemented TfidfVectorizer with a max_df of 0.7. This tells the model to ignore words that appear in more than 70% of the articles, helping it focus on the unique keywords that actually distinguish fake news from real news.

The Split: I held back 30% of the data for testing to make sure the model wasn't just memorizing the training set.

The Results: The model achieved an accuracy of 94.84%.

Performance:
True Positives (Real News correctly identified): 899
True Negatives (Fake News correctly identified): 904

How to use this:
Since I want this to be accessible, I’ve set it up to pull the news.csv directly from this repository.
Open the .ipynb file in Google Colab.
Run the cells. It will automatically grab the data and train the model for you.
