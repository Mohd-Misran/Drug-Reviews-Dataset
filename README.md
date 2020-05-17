# Drug-Reviews-Dataset
Capstone-2 (MLFA Speckbit)

**About the dataset**
The dataset provides patient reviews on specific drugs along with related conditions and a 10 star patient rating reflecting overall patient satisfaction. The data was obtained by crawling online pharmaceutical review sites.
The dataset contains 215063 instances and 5 columns.
The data is split into a train (75%) a test (25%) partition and stored in two .tsv (tab-separated-values) files, respectively.

*Attribute Information*:
1. drugName - name of the drug
2. condition - name of the condition
3. review - patient review
4. rating - 10 star patient rating
5. usefulCount - number of users who found the review useful

You can use this dataset to study:
* sentiment analysis of drug experience over multiple facets, i.e. sentiments learned on specific aspects such as effectiveness and side effects
* the transferability of models among domains, i.e. conditions
* the transferability of models among different data sources

To download the dataset, click [here](https://archive.ics.uci.edu/ml/datasets/Drug+Review+Dataset+%28Drugs.com%29)

**What I'm gonna do with the dataset**
I will be using this dataset to do sentiment analysis on the patient reviews. The two sentiments will be labeled as negative (if rating < 6) and positive (if rating >=6).
I have divided my work into three Google Colab notebooks:
* Notebook 1 contains the script for some graphical visualizations of the data. I am concatenating both train and test data for visualization.
* Notebook 2 contains the script for getting rid of certain values in the dataset and cleaning the text data which is required for the sentiment analysis model. The cleaning is done on the concatenated dataset. 
* Notebook 3 contains the script for creating word embeddings and my model architecture. The cleaned reviews is represented as a label encoded token vector. And I will be using the Keras Sequential Model to fit my data.

**Requirements**
* Python
* numpy
* pandas
* matplotlib
* seaborn
* nltk
* re
* BeautifulSoup
* Tensorflow
* Keras

**Result**
It was very challenging for me to work on this dataset as I had never worked on a dataset with large number of instances. The text features can be represented as Count Vectors, TFIDF Vectors and also Word Embeddings. The first two seemed difficult to me as I didn't have enough RAM to process them. Hence, I represented the text features as Word Embeddings. I used a simple shallow neural network to train my model and achieved an accuracy of almost 86% on the train data. Then I used the model to predict on the test data and achieved an accuracy of 83%.
