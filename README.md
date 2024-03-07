# NLP-TF-IDF
Machine Learning simple models using NLP algorithm TF-IDF.

TF-IDF is used to improve the count vectorizer. This is a famous method in NLP for document retrieval and text mining.

Remembering: stopwords are used as a list to filter out. These are words we do not want to keep. We don’t want to keep these words because they are very unlikely to be helpful for any NLP task we want to do. Probably every document contains these words.
But how do we know if our list of stopwords is correct? We don’t, because it depends on the scenario we are in. They can be application-specific. if we only have biology documents, for example, the word “mitochondria” might not be a good word because every document can have it. And, instead of selecting manually the words in our stopwords lists, there is a way to select the important words and ignore the unimportant ones automatically following some general principle.

The main idea behind TF-IDF

Words that we want to ignore are words that appear in many different documents, that’s why they don’t help us differentiate between documents. We want to scale down the vector component for those words. The word ‘the’ may have a high count in the documents, for example, and so we want to scale down based on the frequency of the word and the frequency of the documents.

TF-IDF = Term Frequency - inverse Document Frequency
TF-IDF ~= Term Frequency/Document Frequency

where

Term Frequency: we count the number of times the word appeared.
Document Frequency: how many documents this word appears in.

Some variations on TF-IDF.

Variation on the Term Frequency:
1.	Represent the terms using binary values (1 if the word appears, 0 otherwise)
2.	Normalize the count by dividing by the sum over all terms in the document. Each term now represents the proportion of time that the word appears in the document.
3.	Take the log of (1+ count(t,d)), this reduce the influence of extreme values. The log function squashes down large values. The larger they are, the more they get squashed.
	
Variation on the Inverse Document Frequency (IDF):
1.	Smooth IDF: add 1 to the denominator and after taking the log. This prevents us from ever getting a value of zero, which is possible (log 1 = 0). 
2.	IDF Max.
3.	Probabilistic IDF.
4.	Just set the IDF=1. In this case, the TF-IDF just becomes the TF itself.

