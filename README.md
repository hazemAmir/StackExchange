## A Multi-Domain Framework for Textual Similarity.

The aim of this work is to provide a unified framework to evaluate embedding models on **textual similarity**.

### A Case Study on Question-to-Question and Question-Answering Similarity Tasks.
We use the community question answering forum Stack-Exchange to extract posts and pairs of questions and answers from multiple domains.  We evaluate two baseline approaches over 19 domains and provide preliminary results on multiple annotated question-answering datasets to deal with question-answering similarity task.
The evaluation is performed using two bottom-up sentence embedding representations (SentEmb and MappSent). The first approach (SentEmb) is a simple sum of word embedding vectors of each sequence (sentence, question, answer...), and the second approach ( MappSent) is a more sophisticated approach that uses a mapping matrix to improve sentence representation. 

The paper can be found [here](http://www.amirhazem.ovh/publications/year/2018/LREC/LREC_2018_Paper_Textual_Similarity.pdf)

When citing **this work** in academic papers and theses, please use the following BibTeX: [bib](http://www.amirhazem.ovh/publications/year/2018/LREC/bib.txt)

## StackExchange Data Sets 
We provide 19 data sets that we extracted from the StackExchange community question answering forum. 

    Corpus        | token  | #all posts | #filtered posts |  #test  |
    -----------------------------------------------------------------      
    Earth Science |  221K  |    2.2k    |      1.6k       |   169   |
    Expatriates   |  185k  |    2.6k    |      1.3k       |   137   |
    Health        |  276k  |    2.9k    |      2.2k       |   223   |
    Sports        |  264K  |    3.2k    |      2.3k       |   240   |
    Politics      |  415K  |    3.2k    |      2.8k       |   282   |
    Pets          |  373k  |    3.4k    |      2.5k       |   253   |
    Economics     |  333k  |    4.1k    |      2.1k       |   210   |
    Law           |  609k  |    5.1k    |      3.6k       |   365   |
    History       |  741k  |    6.1k    |      5.2k       |   522   |
    Philosophy    |  1.1M  |    7.3k    |      5.7k       |   575   |
    Music         |  701k  |    9.1k    |      5.4k       |   544   |
    Workplace     |  1.7M  |   12.9k    |      8.2k       |   830   |
    Biology       |  1.1M  |   14.1k    |       10k       |  1001   |
    Cooking       |  1.2M  |     16k    |     11.3k       |  1132   |
    Chemistry     |  1.3M  |   18.5k    |     10.4k       |  1042   |
    Travel        |  1.6M  |   20.6k    |     12.9k       |  1297   |
    Physics       | 7.02M  |   87.2k    |     44.4k       |  4443   |
    AskUbuntu     | 11.1M  |    248k    |     79.1k       |  7912   |
    Math          | 28.8M  |    702k    |      168k       | 16820   |
    -----------------------------------------------------------------

- Corpus:            each corpus orresponds to a given StackExchange topic.     
- token:             number of tokens of all the posts of a given topic.   
- all posts:         the number of posts (each post is composed of a question, answers and comments).
- filtered posts:    the number of posts that we kept after filtering all the posts that didn'y contain a question mark in the question. This choice was done because posts are selected aotomatically. A manual selection would be obviously better but due to the size of the corpora we didn't addressed it this way. 
- test:              the number of test questions.

We plan to include other data sets to reach the entire dump of about 180 topics in the near future




Due to the large size of the corpus, the data sets can be downloaded [here](https://uncloud.univ-nantes.fr/index.php/s/9Ei9WykrGzMDcDb).

Please put the dowloaded directories (models/ and data/) under the root directory.


## Requirements

- Python 2.7
- NumPy
- SciPy

## Installing
This software depends on NumPy and Scipy, two Python packages for scientific computing.  

To install **this source** please type: 

```
git clone https://github.com/hazemAmir/StackExchange.git
```
## Usage

## Question to question similarity 

SentEmb approach:
----------------

To reproduce the results of the SentEmb approach please run the following script under scripts/ directory:

```
 command: python run_baseline_QQ.py corpus dim eval_ flag
 example: python run_baseline_QQ.py earthscience 100 dev 0

- corpus: one of the 19 available corpora (sports, earthscience, cooking...)
- dim   : the number of dimensions of the word embedding model (100/300)
- eval_ : evaluations on the development (dev) or the test (test) set
- flag  : 0 to reproduce the results of LREC 2018
          1 the results are slightly different (they are better in some cases).
            due to some "nan" numbers when applying cosine similarity, the python sort function put nan numbers at some arbitrary ranks which affect slightly the MAP scores. (This case is rare but needed to be fixed) 
```
MappSent approach:
----------------
Coming soon


## Question Answering Similarity 

SentEmb approach:
----------------

To reproduce the results of the SentEmb approach please run the following script under scripts/ directory:

```
 command: python run_baseline_QA.py corpus dim eval_ flag
 example: python run_baseline_QA.py earthscience 100 dev 0

- corpus: one of the 19 available corpora (sports, earthscience, cooking...)
- dim   : the number of dimensions of the word embedding model (100/300)
- eval_ : evaluations on the development (dev) or the test (test) set
- flag  : 0 to reproduce the results of LREC 2018
          1 the results are slightly different (they are better in some cases).
            due to some "nan" numbers when applying cosine similarity, the python sort function put nan numbers at some arbitrary ranks which affect slightly the MAP scores. (This case is rare but needed to be fixed) 
```
MappSent approach:
----------------
Coming soon


## Authors

* **Amir Hazem** 
* **Basma El Amal Boussaha**
* **Nicolas Hernandez**

## License

This project is licensed under the Apache License Version 2.0 - see the [LICENSE](LICENSE) file for details

## Acknowledgments
The current work was supported by  the ANR 2016 **PASTEL** http://www.agence-nationale-recherche.fr/?Projet=ANR-16-CE33-0007.

