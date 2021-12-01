# NLP-stockNewsBehavior


## Dataset - Right test and train split
You did everything right. Right from choosing a cool preprocessing step to a brand new loss and a neat accuracy metric. But boom! Your validation or test results are way worse than what you expected. So is it overfitting, or your model is wrong, or is it the loss? Sometimes, the simpler things are neglected in our minds and we overlook something so simple as splitting the dataset into train and test sets. Unless your dataset came with a predefined validation set, you most definitely have done this at least once. Most likely it’s the first thing you encounter in any data science tutorial on the web. And chances are you might have been doing it wrong. <br/>
A model trained on a vastly different data distribution than the test set will perform inferiorly at validation

## Why removing stop words is not always a good idea?
The definition of what’s a stop word may vary. You may consider a stop word a word that has high frequency on a corpus. Or you can consider every word that’s empty of true meaning given a context. Some verbs are usually considered stop words because they don’t help us to find the context or the true meaning of a sentence. These are words that can be removed without any negative consequences to the final model that you are training. But here’s the catch: there’s no universal stop words list because a word can be empty of meaning depending on the corpus you are using or on the problem you are analysing. Reducing the data set size is without any doubt a way of increasing performance. Training models takes time and if you have less tokens to be trained, the training time should decrease.<br/><br/>
In addition, techniques such as TF-IDF give more value to rare words than to very repetitive tokens. So, let’s say that you are working on a problem for a bank about one of their products. The name of this product could be a word with high frequency on your corpus, therefore, you could consider it a stop word. But now, let’s say that you are working on a problem about public transportation and suddenly, you find the name of a very rare disease on your corpus. Since the frequency of this word is very low, we can consider it a rare token with a high weight.<br/><br/>
Word importance may vary depending on the dataset. But it may also change depending on the goal you are trying to achieve. Problems like sentiment analysis are much more sensitive to stop words removal than document classification.

## Refrences
https://medium.com/@limavallantin/why-is-removing-stop-words-not-always-a-good-idea-c8d35bd77214 <br/>
https://towardsdatascience.com/3-things-you-need-to-know-before-you-train-test-split-869dfabb7e50
