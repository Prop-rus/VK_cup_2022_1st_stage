**VK CUP 2022. First stage**

This decision took 49 place in private part of test dataset out of 471 competetives.


***Descrpition***

Participants needed to classify groups in social network VK by their posts on 13 categories.  
Categories:  
- 'winter_sport'
- 'extreme'
- 'football'
- 'boardgames'
- 'hockey'
- 'esport'
- 'athletics'
- 'motosport'
- 'basketball'
- 'tennis'
- 'autosport'
- 'martial_arts'
- 'volleyball'

In train dataset we have 38740 posts for 10 on each group.
We had to predict the catogories for 2626 groups by their posts in test dataset.


***Solution description***

As we can see in EDA.ipynb a lot of posts do not apply to any theme of groups - many of them are commercial posts. More over there are some dublicated posts with the same text, but categorized to different themes.

So I have made the decision to train models both on raw text data, and on cleaned text (without duplicates, special symbols, after stemming and etc.)

I have used bert model with pretraining on *DeepPavlov/rubert-base-cased*. Also i have trained simple LSTM model. The predictions for each post of each model are concatenated together (including predicted scores).
After that all scores for each post for each category are summarized. For each group were chosen category with the most sum of scores (and some of categories with low scores were dropped).

*EDA.ipynb*  
Dataset analisys 

*bert.ipynb*  
training and predicting bert model on raw text data

*bert_clean.ipynb*  
training and predicting bert model on cleaned text data

*LSTM.ipynb*
training and predicting LSTM model on cleaned text data

*blend.ipynb*  
concatenating the predictions of each model, summarizing scores, choosing the best category for eanch group




