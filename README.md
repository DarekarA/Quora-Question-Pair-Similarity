# Quora-Question-Pair-Similarity
- Identify which questions asked on Quora are duplicates of questions that have already been asked.  - This could be useful to instantly provide answers to questions that have already been answered.  - We are tasked with predicting whether a pair of questions are duplicates or not. 

- **Source : https://www.kaggle.com/c/quora-question-pairs**

Real world/Business Objectives and Constraints
1. The cost of a mis-classification can be very high. 2. You would want a probability of a pair of questions to be duplicates so that you can choose any threshold of choice. 3. No strict latency concerns. 4. Interpretability is partially important.
Machine Learning Probelm
- Data will be in a file Train.csv
- Train.csv contains 5 columns : qid1, qid2, question1, question2, is_duplicate
- Size of Train.csv - 60MB
- Number of rows in Train.csv = 404,290

Mapping the real world problem to an ML problem
It is a binary classification problem, for a given pair of questions we need to predict if they are duplicate or not.

Performance Metric
Source: https://www.kaggle.com/c/quora-question-pairs#evaluation

Metric(s):

log-loss : https://www.kaggle.com/wiki/LogarithmicLoss
Binary Confusion Matrix
We build train and test by randomly splitting in the ratio of 70:30 or 80:20 whatever we choose as we have sufficient points to work with.

Our Approach
After doing eda we found out that:

There are more 0's than 1's.
The 1's are 36.92% whereas the 0's are 63.08%
There are 537,933 unique questions of which 111,780 occured more than once.
Only one question appeared 157 times
There were no duplicates but we found out that there are 2 questions with null Values. So we replaced them with a space
