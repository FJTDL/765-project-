# 765-project-
STATS 765 Wine project

This project is done for submission of the University of Auckland, Department of 
Statistics, STATS 765 - Statistical Learning for Data Science course. The 
introductory lecture of the course included an explanation of how we can use 
statistical methods on food fraud, a field I find very interesting. Originally, 
I wanted to find a seafood fraud dataset as I have been caught out 
eating species other than what I was sold on a few occasions, but I struggled
to find such a dataset. However, the University of California Irvine (UCI) 
maintains a repository of datasets for machine learning, including being home
to several food fraud datasets such as the wine quality dataset I have chosen to 
use. 

I grew up in Italy, so I am familiar with the wine culture and production of the 
area, so it felt right to still have a somewhat personal dataset. This ReadMe 
contains the project proposal submitted for milestone 1.

## Milestone 1 - Cultivar Prediction

### Objective
The objective of my project is to predict the cultivar of grapes used in the 
production of various Italian wines, and attempt to develop separation rules for 
them.

### Data
My data is sourced from the UCI machine learning repository, which has been 
downloaded in a plain text file. The data is originally from the University of 
Genoa. Some of our variables include alkalinity of ash, which is a measure of 
basic mineral content, such as potassium, after a sample is burned. Flavinoids, 
total phenols, and non-flavanoid phenols, are some of the other variables we may 
wish to investigate the relationships of, as well as hue and colour intensity, 
to see if relationships between colours and phenols (flavanoids being a subset 
of phenols) can be used in our analysis, or how this may select variable 
selection. Because this is a well-curated dataset on a popular repository, the 
data thankfully has no missing values, although as this is lab data the most 
obvious source of noise will come from human error during experimentation, 
collection, and analysis.

### Exploration
- Determine if there is a relationship between phenol-related variables and colour-related variables.
- Determine which variables are highly co-linear, as they will be problematic for methods such as LDA.
- Which variables provide maximum separation between the groups?
- Which variables provide minimal separation between the groups?
- After determining the best separation/prediction rules, can we then determine if some cultivars result in higher alcohol than others, and which variables may be indicative of higher alcohol levels.
- I’d like to see for curiosity if I can predict the proline levels of a given sample, as proline has a very large range compared to the other variables, and should make for an interesting regression challenge.

### Methods
I already have the data from UCI, and I want to preprocess the data as needed by 
standardising/normalising my variables. In this way, particularly extreme 
outliers that are likely due to human error should become obvious and I can 
decide how to handle them such as through attenuation or imputation, as well as 
the possible need for dimension reduction techniques such as PCA. My problem is 
more multiple-classification, and I intend to try both trees and neural networks 
for the classification, and a few different methods such as penalised regression 
(if needed) for prediction of proline. I would prefer to use trees or regression 
models where possible as they allow us to understand their rules better than a 
neural network does, and can possibly support heuristic rule development. 
Multivariate methods such as LDA/QDA/PLS-DA could also prove beneficial in 
development of classification models with some insight into the variables for 
best separation. Ultimately, the goal is to achieve the highest level of 
predictive accuracy, but a secondary goal is to determine the most “powerful” 
rules for separation/discrimination between groups.

### Challenges
I am not a chemist. My understanding of the actual structures and relationships 
of the variables is based almost entirely on what can be found through the 
internet and readings, as well as whatever the paper on the UCI repository says, 
meaning most of my understanding will come from what I find in the data rather 
than physically motivated relationships, which has various complications. 
Furthermore, my data is fairly limited at only 178 rows, which is generally 
considered small for a machine learning problem, especially for test/training 
splits, meaning cross-validation will likely become a vital tool in my analyses.
