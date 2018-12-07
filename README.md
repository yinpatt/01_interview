# 01_interview

This repo is built for the interview. Please read the interview_question.ipynb to view the answers for the interview questions.
The answers for Q3a as below:


Q3a Chinese NLP Question
Questions:

1) How well does your model perform?
Please check 3.1 below. According to a 10 fold cross validation, the model performs close to ~0.99 precision, and it generalize well in unseen data

2) How did you choose the parameters of the final model?
Please check 3.2. To choose the best parameters of the final model, we can use a grid search which loops through all potential parameters within a chosen range.

3) On a high level, please explain your final model’s structure, and how it predicts tags from the article text
The methodology of the model is,

  i) clean and tokenize chinese words into bigram & trigram, then use word2vec to transform these words into vector. The word vector is built based on this "universe" of chinese words

  ii) Given other news article on HK01, if the word has been seen in the previous text, a word vector will be calculated based on the word-cocurence matrix. Average word vector is being used to turn a paragraph into vectors.

  iii) This is a classification problem, so i decided to use random forest. Random forest is a model based on multiple decision tree, randomly selected partial features & each tree vote for the final outcome. The random forest learn the relationship between the tag & the word matrix, and therefore able to predict the probable text based on the word feature. Please note that "out of bag" words is not taken care in this case.
