## A Multi-Domain Framework for Textual Similarity.

The aim of this work is to provide a unified framework to evaluate embedding models on **textual similarity**.

### A Case Study on Question-to-Question and Question-Answering Similarity Tasks.
We use the community question answering forum Stack-Exchange to extract posts and pairs of questions and answers from multiple domains.  We evaluate two baseline approaches over 19 domains and provide preliminary results on multiple annotated question-answering datasets to deal with question-answering similarity task.
We evaluatio is performed using two bottom-up sentence embedding representations (SentEmb and MappSent). The first approach (SentEmb) is a simple sum of word embedding vectors of each sequence (sentence, question, answer...), and the second approach ( MappSent) is a more sophisticated approach that uses a mapping matrix to improve sentence representation. 

The paper can be found [here](http://www.amirhazem.ovh/publications/year/2018/LREC/LREC_2018_Paper_Textual_Similarity.pdf)

When citing **this work** in academic papers and theses, please use the following BibTeX: [bib](http://www.amirhazem.ovh/publications/year/2018/LREC/bib.txt)

## Requirements

- Python 2.7
- NumPy
- SciPy
### StackExchange Data Sets 
Due to the large size of the corpus, the data sets can be downloaded [here](https://uncloud.univ-nantes.fr/index.php/s/9Ei9WykrGzMDcDb).

Please put the dowloaded directories (models/ and data/) under the root directory.

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

