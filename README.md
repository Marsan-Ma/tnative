# "Truly Native?" 

It's my code doing the Data Kaggle challenge https://www.kaggle.com/c/dato-native


### Briefing
In this challenge, we are requested to develop a system predicting whether an article is a native advertisement. It’s involves lots of natural language processing tricks, like boilerplate removing, topic modeling and embedding techniques. My final model is a blending of several bagging logistic regression, two gradient boost trees, and two field-aware factorized machine, which achieved 0.974 AUC in private board. (while 1st prize winner achieves 0.998). 

### If you want to trace code ...
The entry script is go_parse.sh and go_train.sh, you may find every thing start with these two. While the former is used to parse data into mongodb and latter do the model training and evaluation. There are a couple of different models to choose, and feature selection, blending, hyperparameter searching experiments which you could choose the function and tune the setting in main.py.

### About dataflow
Here I tried to separate data pipelines into independent stages. Like, you could change input data format without refactoring the learning models or evaluation stages, and vice versa. Senior Kagglers might find this project get an overkill big structure, that's because this framework try to become a universal framework for any kinds of data science products.
