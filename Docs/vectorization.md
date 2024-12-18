# Vectorization 

Vectorization is the process of converting textual data into numerical vectors and is a process that is usually applied once the text is cleaned.

One the data is vectorized we can then pass it to a model

There are three major methods for performing vectorization on text data:

1. CountVectorizer
2. TF-IDF
3. Word2Vec

## Count Vectorization 

```
from sklearn.feature_extraction.text import CountVectorizer
import pandas as pd
vectorizer = CountVectorizer()
X = vectorizer.fit_transform(cleaned_corpus)  ## passing cleaned corpus
doc_term_matrix = pd.DataFrame(X.toarray(),columns= vectorizer.get_feature_names())
print(doc_term_matrix)
```

Explanation :-

What is a <mark>document</mark> ?
In text processing, a document is simply a single piece of text. It could be anything like:

A single sentence: "This is an example."
A paragraph: "Natural language processing is a field of AI focused on enabling computers to understand human language."
A full article, blog, or book chapter.
The key idea is that each document is a unit of text that you want to analyze or process.

<mark>Corpus</mark> : This is a collection of documents

Corpus 

Bag of Words model is used to preprocess the text by converting it into a bag of words, which keeps a count of the total occurrences of most frequently used words.

<mark>CountVectorizer</mark> from sklearn.feature_extraction.text:

pd.Dataframe : Converts the sparse matrix into a pandas DataFrame for better readability.


## TF-IDF

The Term Frequency is the frequency of a word in a document. It is calculated by dividing the occurrence of a word inside a document by the total number of words in that document.

The Inverse Document Frequency is a measure of how much information a word provides. Words like “the,” for example, occur very frequently but provide little context or value to a sentence. It is calculated by taking the inverse log of document frequency, that is the proportion of documents that contain a particular word.


```
Ok So IN COUNT VECTORIZATION WE SAW BAG OG WORDS
but there only frequency was important but here 
it also retrived the importance of words towards the document
```
