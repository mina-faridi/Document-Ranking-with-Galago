## Document-Ranking-with-Galago
Galago related homeworks of Information Retrieval Course

In this code News documents in TREC type are ranked. Here are the steps that the code works:

* stemming

* tokenizing


these methods are used as the retrieval function:

* BM25

* Pivoted Length Normalization


* nDCG, MAP, Recall and P@5 scales are used for evaluation.

preparing the environment:

First, install the ubuntu operating system, and then install Java, Maven, and Galago respectively.
The text file, which is in the form of a zip, must be extracted from the zip so that it can be converted into the trectext format.

Creating the index:
This code creates an index and performs the steps of tokenization, normalization of words, removal of prepositions, and stemming.

We use these settings to tokenize the text:

```sh

"tokenizer" :{

"fields" : ["text","head"],

"formats" : {
  
    "text"   : "string",
    
    "head"   : "string"
  
  }

}
```
There are different algorithms for rooting, one of the most common of which is porter, which actually removes repetitive parts such as ing from the end of words and has a good performance overall. Set it up
This is how it was done
```sh
"stemmer" : ["porter"]
```

To create the mentioned index, save it and run it with the following command:
```sh
Galago/galago-3.16/core/target/appassembler/bin/galago build  /home/mina/Desktop/CA1-Resources/indexResult.json
```
