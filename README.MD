# Usage of token weights

In the field of Natural Language processing, each token is not of equal importance to classify a number of songs into a few groups. TF-IDF model is useful in this field, because we want to give different weights to different tokens in a song. If two songs are similar in geometry, we assume that they are on the same topic.

#TF-IDF models

Given the factors mentioned above, we need to build a model of how important tokens are based on the given keywords in a song. TF-IDF is a suitable model to distinguish two songs in different topics. In this model, more weight is given to a term if it appears many times in a song, and less weight is given to a term if it appears in many documents. This is because some terms like "it", "is", "a" are not useful at all in terms of classifying songs.

#Calulation of TF-IDF models

Based on the TF-IDF models, we can calculate the weight of each term in a song. First of all, we need to build a vector space based on the tokens that appear in the songs. When we build the vector space, we need to preprocess the data. Specifically, what we have to do is consistent casing (map all characters to upper (or lower) case), unify or remove numbers (map all characters to upper (or lower) case), remove unnecessary spacing (duplicate white spaces) and word tokenization (split text into individual tokens (aka words)). After we have completed building the vector space, we are able to calculate the weights of each token based on the TF-IDF model. To narrow down the gap between the weights of different tokens, we have used log function instead of directly using the frequency of tokens. The formula used for calulation is w(d,t)=log(1+f(d,t)), if f(d,t)>0; w(d,t)=0, if f(d,t)<=0. Given this formula, the weight of each token in a song can be calculated, thus we are able to get the vector of each song.