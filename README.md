# Information Retrieval System Using Word2Vec and Vector Space Model
This project implements an Information Retrieval System (IRS) using Word2Vec and the Vector Space Model (VSM). The system retrieves documents from the cran1400 dataset by calculating the similarity between a user query and preprocessed documents, based on their vector representations.

## Table of Contents

- [Introduction](#introduction)
- [Features](#features)
- [Installation](#installation)
- [Dataset](#dataset)
- [Methodology](#methodology)
  - [Data Preprocessing](#data-preprocessing)
  - [Word2Vec Model](#word2vec-model)
  - [Document Representation](#document-representation)
  - [Query Processing and Ranking](#query-processing-and-ranking)
- [Future Enhancements](#future-enhancements)

## Introduction
The Information Retrieval System is designed to retrieve relevant documents based on a user's query by leveraging word embeddings and vector space models. The project involves the following steps:

Preprocessing the dataset.
Training a Word2Vec model to create word embeddings.
Representing each document as a centroid of word vectors.
Ranking documents based on their cosine similarity to the query.
           
## Features
Tokenization and preprocessing of text data.
Word2Vec model training for word embedding generation.
Representation of each document as a centroid of word embeddings.
Cosine similarity for ranking documents based on query-document similarity.
Retrieval of top-N most relevant documents for a given query.
## Installation
Clone the repository:
<p>git clone: </p>
<a href="https://github.com/ElishBaraiya/information-retrieval-system.git">https://github.com/ElishBaraiya/information-retrieval-system.git</a>
<p>cd information-retrieval-system</p>

## Dataset
A small corpus of 1 400 scientific abstracts and 225 queries. It is considered among the first Information Retrieval initiatives to perform IR tasks in the 1960s.

Tag definitions:
- **docno:** Document unique number (identifier)
- **Title:** Document title
- **Author:** Document author(s)
- **Bibliography:** Bibliography
- **Text:** Main document content (the article Abstract)


To know more about the dataset please visit: <a href="https://github.com/oussbenk/cranfield-trec-dataset">https://github.com/oussbenk/cranfield-trec-dataset</a>

## Methodology
### Data Preprocessing
<ul>
  <li>Tokenization of text using gensim.utils.simple_preprocess.</li>
  <li>Removal of null and duplicate entries.</li>
  <li>Splitting documents into words for further processing.</li>
</ul>

### Word2Vec Model
<ul>
  <li>Trained on the processed documents using <code>gensim.models.Word2Vec</code>.</li>
  <li>Hyperparameters:</li>
  <li>
    <ul>
      <li><code>vector_size=100</code>: Each word is represented by a 100-dimensional vector</li>
      <li><code>window=5</code>: The context window size for capturing surrounding words.</li>
      <li><code>min_count=2</code>: Ignores words that appear less than twice.</li>
    </ul>
  </li>
</ul>

### Document Representation
<ul>
  <li>Each document is represented as the centroid (mean) of its word vectors.</li>
  <li>Documents with similar content have similar centroids, making them easier to compare with a query.</li>
</ul>

### Query Processing and Ranking
<ul>
  <li>The query is processed similarly to the documents (tokenization and centroid calculation).</li>
  <li>Cosine similarity is used to rank the documents based on the query's similarity to each document.</li>
</ul>

### Future Enhancements
<ul>
  <li>Stemming and Lemmatization: Incorporating these techniques may improve the quality of the tokenization process.</li>
  <li>Advanced Models: Testing other embedding models like FastText or BERT for improved document representation.</li>
  <li>Evaluation Metrics: Adding quantitative evaluation with IR metrics like Precision, Recall, and F1 Score.</li>
</ul>


