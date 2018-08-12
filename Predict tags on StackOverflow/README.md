# Predict tags on StackOverflow

## Dataset

The data folder contains records 3 files:

- train.tsv
- test.tsv
- validation.tsv

with following columns in train and validation files:

- text of stackoverflow title
- tags associated with it

In the test file we only have text of title and we have to predict the tags.

## Data Preprocessing

- Lower case all words
- Replace non-textual characters
- Replace digits and hashtags
- Tokenise words
- Remove stopwords
- Words and Tag counting

## Models

### 1. Bag of words
The bag-of-words model is a simplifying representation used in natural language processing and information retrieval (IR). Also known as the vector space model. In this model, a text (such as a sentence or a document) is represented as the bag (multiset) of its words, disregarding grammar and even word order but keeping multiplicity.

### 2. TF-IDF
The second approach extends the bag-of-words framework by taking into account total frequencies of words in the corpora. It helps to penalize too frequent words and provide better features space.

## Multi Classification
I used `OneVsRestClassifier` in combination with `LogisticRegression` on both the models with penalties as `l1` and `l2`.

## Results
In all the 4 combinations, I got best results on TF-IDF with `l1` penalty option.
- F1(MICRO) SCORE: 0.6735434614823005

## Analysis

Here are the some of results:

### Output of tags on some of test set title
```
- Warning: mysql_query() expects parameter 2 to be resource, object given
('mysql', 'php') 

- get click coordinates from <input type='image'> via javascript 
 ('javascript',) 

- How to implement cloud storage for media assets in ZF? 
 () 

- What is catcomplete in jQuery's autocomplete plugin? 
 ('javascript', 'jquery') 

- Error building Android app with Cordova 3.1 CLI 
 ('android', 'java') 

- How to Parse XML File in PHP 
 ('php', 'xml') 

- Uploading files via JSON Post request to a Web Service provided by Teambox 
 ('json',) 

- Adding rows to JTable in the right order. 
 ('java', 'swing') 

- How to read input file in Python? 
 ('python',) 

- PDF generation from an html containing images and text 
 ('html',) 

- Trying to get sql query to be dynamic with jquery 
 ('jquery',) 

- Fiting 2-parameters weibull distribution for tabulated data 
 () 

- Add six months in php 
 ('php',) 

- Where/How to code Constants in Rails 3 Application 
 ('ruby-on-rails', 'ruby-on-rails-3') 

- Comparing list of items with one of the column in DataTable 
 ('c#',) 

- python sort upper case and lower case 
 ('python',) 

- How do I make a pointer to a multidimensional array which has an unknown size? 
 () 

- Rails 3 Trigger AJAX Submit On Radio Button Change is rendering html response 
 ('ajax', 'html', 'javascript', 'jquery', 'ruby-on-rails') 

- Source code of apps in windows8 
 () 

- Callback on sockets in linux 
 ('c', 'linux', 'sockets') 
```

### Top positive and negative words for some tags

### `c`
- __Top positive words__:	printf, fscanf, malloc, scanf, c
- __Top negative words__:	c #, php, javascript, java, python

### `c++`
- __Top positive words__:	stl, mfc, qt, boost, c++
- Top negative words:	php, java, javascript, python, jquery

### `linux`
- __Top positive words__:	address, system call, ubuntu, signal, linux
- __Top negative words__:	#, javascript, jquery, aspnet, array

### `python`
- __Top positive words__:	tkinter, matplotlib, numpy, pandas, python
- __Top negative words__:	php, java, c, django python, jquery

### `java`
- __Top positive words__:	jtable, jar, hibernate, spring, java
- __Top negative words__:	php, python, ruby, rails, django

### `android`
- __Top positive words__:	intent, edittext, asynctask, retrofit, android
- __Top negative words__:	python, c, swift, iphone, phonegap android

### `r`
- __Top positive words__:	rstudio, shiny, ggplot, ggplot2, r
- __Top negative words__:	android, php, java, python, c

### `ios`
- __Top positive words__:	afnetworking, objective, uicollectionview, swift, ios
- __Top negative words__:	java, python, php, jquery, rails

### `windows`
- __Top positive words__:	wmi, multithreaded application, mingw, windowsh, windows
- __Top negative words__:	javascript, jquery, array, windows form, phone




## Further Improvements

Any suggestions, always welcome! 

Send a pull request, if you see any errors...
