# Write-Your-Personality
Predict Myers-Briggs personality test with last social media posts using Natural Language Processing.

![Image](https://user-images.githubusercontent.com/70896372/117457835-edaddd00-af49-11eb-8ec8-e033bd5b9a1a.png)

## Introduction
The MBTI personality classification system grew out with Jungian psychoanalytic psychology as a systematization of archetypal personality types. The system is divided along four binary orthogonal personality dimensions, altogether comprising a total of a 16 distinct personality types.The dimensions are the following:

- Extraversion (E) vs Introvertion (I): a measure of how much an individual prefers their outer or inner world. 
- Sensing (S) vs Intuition (N): a measure of how much an individual processes information through the five senses versus impressions through patterns.
- Thinking (T) vs Feeling (F): a measure of preference for objective principles and facts versus weighing the emotional perspectivers of others. 
- Judging (J) vs Perceiving (P): a measure of hoe much an individual prefers a planned ans ordered life versus a flexible and spontaneous life.

## Preprocessing

In the first place, I analyse the dataset to have a first impression of the data I had. Afterwards, the second step was to clean the posts column, deleting separations tabs, urls, @ and other information that was irrelevant for the model. I didn't remove stop words, tokenize the words or lemmatize them, due to the preprocessing model I used didn't need to do this steps.

## Word Embedding


