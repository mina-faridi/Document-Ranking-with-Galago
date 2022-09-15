# Document-Ranking-with-Galago
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

```
  {
  	"server" : true,
   
    "indexPath" : "indexDir",
    "inputPath" : "./CA1-Resources/Corpus/corpus/Documents.trectext",
      
      "stemmer" : ["porter"],
      
      "tokenizer" : {
      
      "fields" : ["text","head"],
      
      "formats" : {
          "text"    : "string",
          "head"    : "string"
        }
      },
      "fileType":"trectext"
    }
```
## First question: BM25 recovery method
First, we perform the query on queries 101 to 150 or the main method BM25. And we set the value of output results for each query to 100 (100 = requested).
The following table shows the results of MAP, nDCG, Recall, P5 criteria in queries 101 to 150 with different b, k parameters. Based on this table, we can see that the optimal state occurred at b=0.4, k=2.5.




In the next part, we perform the query for queries 51 to 100. Once we give the default value to parameters b, k and once the optimal value of the previous part and observe that the result is better by using the optimal parameters. Because the optimal values of b and k are related to the document itself, and since the documents are fixed, with different queries, the optimal values should not differ much, and optimization can be effective in this case.
