# Proposals

1. Is a beginning farmer's business likely to succeed? 
    1. I worked on a small farm: < 5 acres; < 10 workers; < $250,000 income. By gathering data on certain metrics I would like to generate models that predict if these farmers will succeed.
    2. Predict likelihood of success for beginning farmers in US based on metrics like funding, years experience, education, supplemental income, individual or partnership
    3. Other features to consider: location, race
    4. Data resources:
        1. [USDA: agriculture prices](https://usda.library.cornell.edu/concern/publications/c821gj76b?locale=en)
    6. Parameters to limit research: farmers farming on < 100 acres; income < $500,000; < 15 workers
    7. Success baromoter: are they still farming after 5 years?

# Current proposal as of 3/17
1. Data: monthly prices of 1500 stocks for their entire lifetimes
    1. Test different theories of predicting stock prices
        1. momentum
        2. mean reversion
        3. martingales
    3. Goal: build a model that can predict whether stocks will rise or fall (in building the model using the current price as the 'future' price) based on historical prices
    4. Notes
        1. I've collected all the data
        2. Next step: create features like % increase over: the last 5 months, the last year, last 3 years, last 5 years.


Keep in mind:
1. Clear defined targets
2. What features define the target  
3. Get the data
