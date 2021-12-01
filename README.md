# NLP-stockNewsBehavior

## Introduction
Predicting stock price momentum based on the top 25 news headlines of that day.

## Datset
|      Column     |                  Description                             |
| --------------- | -------------------------------------------------------- |
| Date            | Stock momentum date                                      |
| Label           | Price momentum on that day (UP = 1 , Down/no change = 0) |
| Top 1 to Top 25 | Top 25 headline data                                     |

## Data preprocessing
 * Dropping special Characters
 * Converting to Small case
 * <strike>Dropping Stopwords</strike>
 * Lemmatization
 * Word Embedding - Vectorization
   * Bag of words
 
## Why removing stop words is not always a good idea?
The definition of what’s a stop word may vary. You may consider a stop word a word that has high frequency on a corpus. Or you can consider every word that’s empty of true meaning given a context. Some verbs are usually considered stop words because they don’t help us to find the context or the true meaning of a sentence. These are words that can be removed without any negative consequences to the final model that you are training. But here’s the catch: there’s no universal stop words list because a word can be empty of meaning depending on the corpus you are using or on the problem you are analysing. Reducing the data set size is without any doubt a way of increasing performance. Training models takes time and if you have less tokens to be trained, the training time should decrease.<br/><br/>
In addition, techniques such as TF-IDF give more value to rare words than to very repetitive tokens. So, let’s say that you are working on a problem for a bank about one of their products. The name of this product could be a word with high frequency on your corpus, therefore, you could consider it a stop word. But now, let’s say that you are working on a problem about public transportation and suddenly, you find the name of a very rare disease on your corpus. Since the frequency of this word is very low, we can consider it a rare token with a high weight.<br/><br/>
Word importance may vary depending on the dataset. But it may also change depending on the goal you are trying to achieve. Problems like sentiment analysis are much more sensitive to stop words removal than document classification.

## Dataset - Right test and train split
Train - 90%, Test - 10% <br/>
You did everything right. Right from choosing a cool preprocessing step to a brand new loss and a neat accuracy metric. But boom! Your validation or test results are way worse than what you expected. So is it overfitting, or your model is wrong, or is it the loss? Sometimes, the simpler things are neglected in our minds and we overlook something so simple as splitting the dataset into train and test sets. Unless your dataset came with a predefined validation set, you most definitely have done this at least once. Most likely it’s the first thing you encounter in any data science tutorial on the web. And chances are you might have been doing it wrong. <br/>
A model trained on a vastly different data distribution than the test set will perform inferiorly at validation

## Model
| Sno  | Normalization | Vectorization |   Algortihm   |   Accuracy   | Precision | Recall | fscore |
| ---- | ------------- | ------------- | ------------- | ------------ | --------- | ------ | ------ |
|   1	 | Lemmetization | Bag of word	 | Random Forest |  85.97883598 |   0.803   |  0.958 |  0.874 |

## CONCLUSION
 * Accuracy value of 86% means that 1.4 of every 10 labels is incorrect, and 8.6 is correct.
 * Precision value of 80% means that on average, 2 of every 10 Positive labeled by our program is Negative, and 8 is Positive.
 * Recall value is 96% means that 0.4 of every 10 Positive in reality are missed by our program and 9.6 labeled as Positive.


## Refrences
https://medium.com/@limavallantin/why-is-removing-stop-words-not-always-a-good-idea-c8d35bd77214 <br/>
https://towardsdatascience.com/3-things-you-need-to-know-before-you-train-test-split-869dfabb7e50
