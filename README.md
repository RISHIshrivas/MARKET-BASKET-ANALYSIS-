# MARKET-BASKET-ANALYSIS-
Market Basket Analysis (MBA) is a data mining method originally developed for the retail industry to discover patterns among products that are frequently purchased together. This GitHub repository provides a Python implementation of Market Basket Analysis using the Apriori algorithm and demonstrates its application to Natural Language Processing (NLP) for analyzing trends in text data.

# Installation
- Use the package manager pip to install the required library.
``
pip install apyori
``
# Usage

``
import pandas as pd
from apyori import apriori
#Load your dataset
data = pd.read_csv("store_data.csv", header=None)
#Preprocess the data
transactions = []
for i in range(1, len(data)):
    transactions.append([str(data.values[i, j]) for j in range(0, 20)])
#Apply the Apriori algorithm
association_rules = apriori(transactions, min_support=0.0045, min_confidence=0.2, min_lift=3, min_length=2)
association_results = list(association_rules)
#Display association rules, support, confidence, and lift ratio
for item in association_results:
    pair = item[0]
    items = [x for x in pair]
    print("Rule: " + items[0] + " -> " + items[1])
    print("Support: " + str(item[1]))
    print("Confidence: " + str(item[2][0][2]))
    print("Lift: " + str(item[2][0][3]))
    print("-----------------------------------------------------")
`` 

Make sure to replace "store_data.csv" with the path to your dataset.

# Requirements
- pandas
- numpy
- seaborn
- matplotlib
- mlxtend
- apyori
Install the required packages using the following command:
`` 
pip install pandas numpy seaborn matplotlib mlxtend apyori
``
# Contributing
Pull requests are welcome. For major changes, please open an issue first to discuss what you would like to change.

# License
MIT
