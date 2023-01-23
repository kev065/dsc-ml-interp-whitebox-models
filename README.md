# Machine Learning Interpretability - White-Box Models

## Introduction

Successful machine learning projects require that we negotiate trade-offs between the accuracy of our predictions and the interpretability of our predictions. This is why it is important to carefully consider your use case and what you hope to gain from your predictions. This can help you to understand where it is appropriate to trade accuracy for interpretability.

When discussing interpretability in machine learning, the terms "white-box" and "black-box" refer to how interpretable a model is. The term __white-box__ models refers to models that are interpretable on an in __intrinsic__ level, like the upward trending line in a regression visualization. This means that we can infer why the model made the decision it did with minimal investigation. On the other hand, __blackbox__ models refer to models that are not simple to interpret, like neural networks. While it is theoretically possible to examine the weights of layer, it isn't necessarily practical. 

In this lesson, we will discuss the different approaches to building interpretable models and the layers of interpretability. Then, we will discuss some of the most common white-box models, regression and tree based.

## Objectives

You will be able to:

* Distinguish between intrinsic and post-hoc interpretation
* Distinguish between model-specific and model-agnostic interpretation
* Distinguish between local and global interpretation
* Describe the common white-box models like regression and simple trees and identify use cases for each

## Model Interpretation
Successfully interpreting a machine learning model takes planning. It is necessary to take into consideration the goals of your project when selecting a model, to ensure the the combination of interpretation methods available to you are sufficient to test your hypothesis and explain your results.

### Model Selection and Common White-Box Models
There is an old adage with mysterious origins in data science that states "always try regression first". While regression is certainly not a magic bullet, the sentiment behind this motto is a prudent one. When possible, starting out with a simple and easy to interpret model can be more valuable that diving right into neural networks. 

Model interpretation begins at model selection and model selection should generally reflect your use case. Consider the following white-box models and some examples of how we can apply them to solve problems.

### Linear Regression
If you want to predict the actual value of a home based on a limited set of variables that are well understood and in a tabular (structured) format, like neighborhood averages, number of bedrooms, and/or square footage, __linear regression__ is your friend. 

### Logistic Regression
If you need to build a model that evaluates the description of a home on Zillow to determine if the home is a McMansion, you might use some NLP pre-processing techniques to extract the relevant words and their values. Then, you could use __logistic regression__ to classify each of the homes.

### Naive Bayes
If you wanted to analyze unstructured data, like the descriptions of the homes, to determine which words appeared most frequently in homes that are classified as McMansions, you could use a __Naive Bayes Classifier__ and __permutation feature importance__ to infer the most common (and least common!) characteristics of McMansions by analyzing their descriptions programatically.

### Decision Trees
If you wanted to build a model that would tell you to buy a McMansion based on the presence of important characteristics listed in the description, a __simple decision tree__ can get the job done. 

All of these examples use the same data source, real estate listings on Zillow. In the first example, the goal was to __predict an exact price__ and in the second example, we wanted to extract the data ourselves and __infer price using the other features to classify__ the home. In the last example, we wanted to __investigate other potential features that might be characteristic of our target class__ of McMansions. Finally, we wanted to __automate our buying decision based on features revealed to be important__. 

Since the end goal was different, the model and preprocessing techniques chosen were unique to each case. You might even notice that we used various models to analyze different aspects of the same problem to gain a well rounded perspective. 

### Types of Interpretation
The type of model that you that you choose impact the types of interpretation that are available to you. Let's discuss the two types of interpretation -- __intrinsic__ and __post-hoc__.

#### Intrinsic
A model is considered __intriniscally interpretable__, when the it is easy for an observer to understand how the model arrived at its prediction. Intrinsic interpretability is achieved by restricting the complexity of the model itself during the training phase. This is achieved by limiting the number of features, the size of the dataset, and selecting a white-box model. It also requires a well-defined problem or hypothesis. In linear regression and logistic regression, it's easy to see the relationship between variables in visualizations. The same can be said for simple tree-based models as well. 

#### Post-Hoc
__Post-Hoc Interpretation__ is the process of applying methods to interpret the model results after the training period. This can include using statistical methods like permutation feature importance or other feature summary statistics. It can also include reading data visualizations and/or model internals (like weights). Post-hoc interpretation is sometimes known as __explainability__. In the Naive Bayes example, the technique of __permutation feature importance__ is applied after the training phase to determine the importance of each feature. Post-hoc interpretations can also be applied to intrinsically interpretable models.

### Methods of Interpretation
__Model specific__ interpretation methods are methods of interpretation that can only be applied with a specific model. For example, regression weights are an interpretability metric that we can only use with regression models. Models that are intrinsically interpretable generally have model specific interpretation methods.

__Model agnostic__ interpretation methods are methods of interpretation that analyze input/output pairs, on models that are already trained. 

#### Scope of Interpretation
You will also want to consider the extent to which your results and interpretations apply.
For example, __Local__ interpretation explains a given prediction on an individual level. __Global__ interpretation explains the behavior of the model as a whole. 

## Summary
In this lesson, we discussed different approaches to building interpretable models. We discussed the two kinds of interpretability, intrinsic and post-hoc. Then, we discussed model specific versus model agnostic interpretability methods and local versus global explanations. Finally, we briefly reviewed two of the most common white-box models, regression and tree-based and reviewed use cases for each.

In the next lesson, we will build an interpretable model with sci-kit learn regression and decision trees. Then, we will test some of the interpretability methods discussed in this lesson. 
