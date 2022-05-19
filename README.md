# Phishing-Url-Detection
An algorithm modified into a system which can scan the URL and can predict whether it is safe or maliciously prone to phishing attacks.

# Detecting phishing websites using a decision tree
This repository is a tutorial explaining how to train a simple decision tree classifier to detect websites that are used for phishing. Typically, phishing websites disguise as trustworthy websites in order to gain the trust of their victims, and malicious parties use them to obtain sensitive information from their victims: e.g., passwords or credit card numbers. In this tutorial, we train a decision tree to detect such websites, with a success rate of 90.5%.

# Installation
To get started, you should first clone this repository by running the following command from a UNIX terminal.

``` git clone https://github.com/npapernot/phishing-detection ```
This will download the code that trains the phishing detector, as well as the training data required for that operation.

You should also install``` scikit-learn ```, which is a collection of tools for machine learning written in Python. You can find instructions on how to install it [here](https://scikit-learn.org/stable/install.html). On a UNIX machine configured with pip, the simplest way is to run:

```pip install -U scikit-learn```
Once you have installed scikit-learn, you can check whether the library is correctly setup by typing the following in a Python shell:
```import sklearn```
If the command runs with no error, you are ready to train the phishing detector!

# Phishing Website Dataset
In this tutorial, we use a dataset of phishing website publicly available on the [machine learning repository](https://archive.ics.uci.edu/ml/datasets/Phishing+Websites) provided by UCI. You don't have to download the dataset yourself as it is included directly in this repository (```dataset.csv``` file) and was downloaded on your machine when you cloned this repository.

The dataset was collected by analyzing a collection of 2456 websites among which some were used for phishing and others not. For each website included in the dataset, 30 attributes are given. You can find a list here. The list includes for instance the URL length, whether the website uses pop-up windows or Iframes, or how old the domain registration is.

Each website in the dataset is labeled by -1 if it is not a phishing website and by 1 if it is a website used for phishing.

# Training the decision tree to detect phishing website
You can find the code that trains the decision tree in the ```decision_tree.py``` file. To run the code, simply execute it in a terminal:

```python decision_tree.py``` 

This will first train the decision tree on 2,000 websites, then use the trained model to predict whether 456 websites are used for phishing or not (these websites were not analyzed during training). The model should make predictions that are about 90.5% correct, i.e. the accuracy of the model on the testing data should be 90.5%. Here is a dump of the output made by the script.

```Tutorial: Training a decision tree to detect phishing websites
Training data loaded.
Decision tree classifier created.
Beginning model training.
Model training completed.
Predictions on testing data computed.
The accuracy of your decision tree on testing data is: 0.906129210381```

To understand how this was done, you can read the line by line comments in the decision_tree.py file.
