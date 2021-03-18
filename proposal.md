# Proposals
### As of 3.18

Hey Dan, I know you’re taking a look at our proposals today Tuesday. I am still finding clear direction for my project. I landed on doing stock predictions, and I’ve done a fair amount of research and have what might be good ideas, they are simply still coming together. Here is where I am currently at:

1. *Target* stock increase/stayed the same or decreased from last month to current month (binary classification).
2. *Features*
    1. F1 Stock increase/stayed the same or decreased from 1 month prior to 6 months prior (binary classification) (momentum theory of stock price movement)
    2. Using unbiastock.com 
        1. F2 Reddit trending stocks
        2. F3 Twitter trending stocks
        3. F4 Google trending stocks
    3. F5 Use NLP to gather sentiment data on stocks from Twitter 
    4. F6 Use NLP to gather media data on stocks from a news source

Since we are doing NLP on Tuesday, I figure I will have those weeknight to work on gathering and preparing the media data.




### As of 3.16
1. Data: monthly prices of 1500 stocks for their entire lifetimes
    1. Test different theories of predicting stock prices
        1. momentum
        2. mean reversion
        3. martingales
    3. Goal: build a model that can predict whether stocks will rise or fall (in building the model using the current price as the 'future' price) based on historical prices
    4. Notes
        1. I've collected all the data
        2. Next steps: 
            1. create features like % increase over: the last 5 months, the last year, last 3 years, last 5 years.
            2. Have better understanding of testing time-series data
            3. just use data from https://unbiastock.com/reddit.php?

### As of 3.12
1. Is a beginning farmer's business likely to succeed? 
    1. I worked on a small farm: < 5 acres; < 10 workers; < $250,000 income. By gathering data on certain metrics I would like to generate models that predict if these farmers will succeed.
    2. Predict likelihood of success for beginning farmers in US based on metrics like funding, years experience, education, supplemental income, individual or partnership
    3. Other features to consider: location, race
    4. Data resources:
        1. [USDA: agriculture prices](https://usda.library.cornell.edu/concern/publications/c821gj76b?locale=en)
    6. Parameters to limit research: farmers farming on < 100 acres; income < $500,000; < 15 workers
    7. Success baromoter: are they still farming after 5 years?


Keep in mind:
1. Clear defined targets
2. What features define the target  
3. Get the data
