# Sentimental-Analysis
 Sentiment analysis is a text analysis technique that detects emotions, opinions, or attitudes in content—classifying it as positive, negative, or neutral to understand public or customer sentiment.

 1. Data Collection and Preparation
The process begins with collecting the dataset, which is an IMDB movie review dataset of 50,000 reviews, downloaded via the Kaggle API. The dataset is a CSV file with two columns: review and sentiment. The sentiment labels, originally "positive" or "negative", are converted to a numerical format (1 and 0, respectively) to be used by the machine learning model. The dataset is then split into training and testing sets, with 40,000 reviews allocated for training and 10,000 for testing.

2. Data Preprocessing
To prepare the text data for the neural network, a Tokenizer is used to convert the text reviews into sequences of integers, representing a vocabulary of up to 5,000 words. To ensure all input sequences have the same length for the model, padding is applied to each sequence to make them 200 elements long.

3. Model Building and Training
The core of the project is a deep learning model built with Keras. The model is a sequential neural network composed of three layers:

An Embedding layer that takes the integer-encoded reviews as input, with an input dimension of 5,000 words and an output dimension of 128.

An LSTM (Long Short-Term Memory) layer with 128 units and a dropout rate of 0.2 to handle the sequential nature of the text.

A Dense output layer with a sigmoid activation function to produce a binary classification (positive or negative sentiment).

The model is compiled using the adam optimizer and binary_crossentropy as the loss function. It is then trained on the prepared data for five epochs. During training, the model's accuracy improved consistently, achieving a final training accuracy of 93.28% and a validation accuracy of 87.70%.

4. Model Evaluation and Prediction
The model's performance is evaluated on the unseen test set, where it achieves an accuracy of approximately 88.30%. Finally, a predictive function is created to classify new movie reviews by processing them in the same way the training data was handled and then using the trained model to predict the sentiment. The notebook demonstrates this function by successfully classifying a positive review as "positive" and two negative reviews as "negative".
