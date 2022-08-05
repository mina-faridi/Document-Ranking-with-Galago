# Document-Ranking-with-Galago
Galago related homeworks of Information Retrieval Course

In this code News documents in TREC type are ranked.

Here are the steps that the code works:

-stemming

-tokenizing


these methods are used as the retrieval function:

BM25

Pivoted Length Normalization


nDCG, MAP, Recall and P@5 scales are used for evaluation.

preparing the environment:

First, install the ubuntu operating system, and then install Java, Maven, and Galago respectively.
The text file, which is in the form of a zip, must be extracted from the zip so that it can be converted into the trectext format.

Creating the index:
This code creates an index and performs the steps of tokenization, normalization of words, removal of prepositions, and stemming.

We use these settings to tokenize the text:


There are different algorithms for rooting, one of the most common of which is porter, which actually removes repetitive parts such as ing from the end of words and has a good performance overall. Set it up
This is how it was done
