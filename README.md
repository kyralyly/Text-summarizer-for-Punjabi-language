# Text-summarizer-for-Punjabi-language

# Overview
This is a text summarizer based on sequence to sequence framework for Punjabi language. It uses extractive summarization- does not generate new text but rather extracts and compiles existing content. Since there are very few nlp application model that focus on indian languages, i trained this model for punjabi language.

# Dataset used
XLSum- The XLSum dataset is a comprehensive dataset containing multilingual news articles and their summaries. The dataset includes a wide range of languages. The XLSum dataset for Punjabi is used from the dataset library for this project. There is an 80%-10%-10% split generally, but in the Punjabi language, we have a total of 10267 sample counts, of which 8215 are for training, 1026 for test, and 1026 for validation. This is enough for training a small model.

from datasets import load_dataset
config_name='punjabi'
dataset = load_dataset("csebuetnlp/xlsum",config_name)

# Transformer Model used: T5
T5-(Text-To-Text Transfer Transformer)- is a pre-trained encoder-decoder model handling all NLP tasks as a unified text-to-text-format where the input and output are always text strings. T5-Small is the checkpoint with 60 million parameters.

# optimizer
Optimizer used is AdamWeightDecay with a learning rate of 2e-5 and weight decay of 0.01.

# Evaluation metric and Results
After training the model for 2 epochs, we evaluate its performance using the rouge metric for the 50th entry of test data. The input_text given is the ‘text’ of dataset[‘test’][50].
 
The results are as follows:

●	{'rouge1': 0.23815098039215686, 
●	'rouge2': 0.05604331811023622, 
●	'rougeL': 0.12156862745098039, 
●	'rougeLsum': 0.1546758823529412}






