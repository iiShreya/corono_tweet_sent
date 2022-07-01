# corono_tweet_sent
target column: Sentiment 
## Preprocessing:
1. convert date column to pandas datetime format 
2. drop duplicate tweets
3. extract columns OriginalTweet, Sentiment 
4. clean the OriginalTweet by removing:
- emojis
- newlines and convert text to lowercase
- links and mentions
- non utf8/ascii characters
- hashtags
- & and $ present in words
- multiple spaces
5. find the length of the cleaned text to see if after cleaning, there are tweets with 0 words. So drop tweets with <5 words
6. tokenize the tweets using BERT tokenizer
7. remove tweets with token lengths >80 as they don't appear to be in English
8. convert Sentiment column to have only 3 columns: Negative: 0, Neutral: 1, Positive: 2

## Balance the Dataset
Balanced dataset for a model would generate 
- higher accuracy models
- higher balanced accuracy 
- balanced detection rate 
We use randomoversampler: 
- Randomly duplicate examples in the minority class.

## Validation set extracted from Train set to avoid overfitting
## Apply One-Hot Encoding:
We convert each categorical value into a new categorical column and assign a binary value of 1 or 0 to those columns. Each integer value is represented as a binary vector. All the values are zero, and the index is marked with a 1.

## Fit data to the Machine Learning models:

## 1. Naive Bayes Classifier

## 2. Logistic Regression Classifier

## 3. Random Forest Classifier

## 4. K Nearest Neighbours Classifier

## Metrics for ML Algorithms:
- Precision : TP/TP+FP
- Recall : TP/TP+FN
- F1 Score : 2 * Precision * Recall / (Precision + Recall)

## Results:
1. Naive Bayes Classifier: F1 Score: 70%

2. Logistic Regression Classifier: F1 Score: 78%

3. Random Forest Classifier: F1 Score: 67%

4. K Nearest Neighbours Classifier: F1 Score: 47%

## Fit data to the Deep Learning Models:

## 1. BERT
optimizer: Adam
learning rate: 1^-5
decay rate: 1^-7
epochs: 1
loss: categorical cross entropy
accuracy: categorical accuracy
input layer: 128 neurons
output layer: 3 neurons
activation: softmax

## 2. RoBERTa
optimizer: Adam
learning rate: 1^-5
decay rate: 1^-7
epochs: 1
loss: categorical cross entropy
accuracy: categorical accuracy
input layer: 128 neurons
output layer: 3 neurons
activation: softmax

## Metrics for Deep Learning Algorithms:
- Precision : TP/TP+FP
- Recall : TP/TP+FN
- F1 Score : 2 * Precision * Recall / (Precision + Recall)
- Confusion Matrix 

## Results:
1. BERT: F1 Score: 85%
2. RoBERTa: F1 Score: 88%

