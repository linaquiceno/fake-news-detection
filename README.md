# fake-news-detection

Fake News Detection
Omar Elhayboubi, Lina Quiceno

Problem and Data Set description
Fake news has been growing lately and got a lot of attention after the US presidential election in 2016 and
getting special attention from the republican party. Detecting Fake news is critical for our society as it spreads
very fast due to social media networks and word of mouth. Our project aims to classify fake news with logistic
regression.

Our Data set is composed of:
● 44.898 Articles
● 5 Columns: title, text, subject, date, class
● Non-null values


Method
Data Processing: we started with two datasets, one of real news (21.417
data entries) and one with fake news (23.481). Then, we merged them
into one data frame and created a variable called ‘class’ with 1 for real
news and 0 for fake news. This is the data frame we will use to train our
models.

Data Cleaning: we decide to merge all text in 1 column. Remove stopwords, square brackets, symbols, and
URLs.

Data Exploration: Before doing the data cleaning, we checked the class distribution, which we found to be
balanced. We also printed the distribution of subjects and their class distribution. Still, it is impossible to make
conclusions with this information because both original data frames (fake and real news) have similar subjects
(with different names). We also explore the characters in text and the average word length in text, which
shows a normal distribution.

After the data cleaning, we created word clouds for real news and one for fake news; as with the subject
distributions, it was challenging to make conclusions. For one of them, we used a mask of the “trump” logo,
which helps us make a stronger point on how the words in the news were related to Donald Trump.

Vectorizing: As an initial step, we created a corpus with our text column, and then we started a function to vectorize our corpus so we can make unigram, bigram, and trigram analyses. In this function, we used CountVectorizer from the library Skicit Learn. This allowed us to see the distribution of words over the vocabulary. Unsurprisingly in the three analyses, we got words related to Donald Trump.

LDA: we used LDA to explore and understand the topics inside our news. We printed the 10 top words for each Topic. We used our intuition to give a title for each topic and found out that topics related to Clinton vs Donald Trump had the most fake news.

Data modeling: The data set was split with a distribution of 75 to 25 for training and test, and decided to use Logistic Regression with three different versions CountVectorizer, TFIDF and Ngrams so we could test data modeling with different inputs. Logistic regression maps the confidence of categorical variables in a range of [0,1].

Results: The three models got outstanding results with AUCs of 0.99 and f-score of 0.99 or 1 in our test data. We chose LR Countvectorizer as our best performing model.

Demo: As an extra step we decided to develop a small demo in which the app asks the user for an URL of news from 2016-2017 and it will return the classification of the news (fake or real) along with the article title and content of it. We used Article Library to web scrape the text from the
Article URLs. Then, We call the pre-processing functions we created for training the model. Finally we run the cleaned data through our best performing model to predict whether the article is Real or Fake. Screenshot below shows results for following Article entered by user:
