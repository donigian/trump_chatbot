# trump_chatbot
Here's your chance to ask Trump what's on your mind...

## Overview
The training data contains 29,023 instances and is gathered from [www.trumptwitterarchive.com](http://www.trumptwitterarchive.com/archive). If you're interested in reproducing the results, simply export the tweet archive into a csv which can then be loaded via Pandas.

For the purposes of this chatbot, the interactions between the user & chatbot are Trump's tweets. Therefore, it doesn't matter who initiates the conversation. In order to get the data in the format we need, we'll need to pass it question and response pairs.

To match the question user inputs to the most relevant response, I'll be using TFID & cosine similarity. 
I first use the training data to create a TFID matrix. 
Now I can use this matrix to measure similarity of user's question to questions in our training set.

For example, when the user asks a question, I would output the cosine similarity scores with respect to responses in my training data set.

```

User Question: 
"Hi. What is your name?"

Answer: 
Id      Cosine Similarity Score
1304    0.231638
1303    0.191105
1062    0.166249
995     0.164847
856     0.123025
dtype: float64


Out[9]:
1304                                          @realDonaldTrump what is your favorite book that you have authored?  Art of the Deal!
1303            @realDonaldTrump what is your best piece of advice for someone starting over at 40? Work hard and love what you do!
1062    @realDonaldTrump craig ferguson called you a bad person the other day? what is your opinion of him?  Who is Craig Ferguson?
995     @realDonaldTrump You have so much confidence. Have you always had it and what is your advice for trying to find my own WIN!
856     @realDonaldTrump Mr. Trump Even though I'm not a Republican I wrote your name on my ballot during the election. A wise move
```