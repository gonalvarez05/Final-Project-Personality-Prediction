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
In the first place, I analyse the dataset to have a first impression of the data. Afterwards, the second step is to clean the posts column, deleting separations tabs, urls, @ and other information that is irrelevant for the model. I didn't remove stop words, tokenize the words or lemmatize them, due to the preprocessing model used doesn't need this steps.

## Word Embedding
Once we have our cleaned data and our labels in numbers, this step is the most controversial because there are several preprocessing models and I had to choose the best that fits to my problem. After trying different models the best one was [nnlm-en-dim50](https://tfhub.dev/google/nnlm-en-dim50/2), a token based text embedding trained on English Google News published by Google. It is based on NNLM (Neural Network Language Model) with to hidden layers. 

## Create and train the model
With tensorflow and keras I create a sequential model where I added the data that was before transform in arrays and to more dense layers. As optimizer I used 
Adam Optimation and a loss function, a categorial crossentropy. As a metric I had to use a categorical accuracy beacause there are 16 different personality types.

## Results
| Model      | Train accuracy | Validation accuracy | Test accuracy|
| ----------- | ----------- | ---------------| ---------------| 
| Categorical model   |  56.65%       | 35.97%|     37.58% |

Binary results

| Model      | Train accuracy | Validation accuracy | Test accuracy|
| ----------- | ----------- | ---------------| ---------------| 
| Intro vs Extro  |  99.10%       | 86.23%|     83.54% |
| Sens vs Intuition  |  86.72%       | 86.11%|     85.24% |
| Think vs Feeling  |  87.19%       | 80.45%|     80.87% |
| Judging vs Perceiving  |  59.87%       | 60.23%|     61.77% |







