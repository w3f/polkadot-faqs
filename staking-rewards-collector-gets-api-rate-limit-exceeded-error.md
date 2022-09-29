Every time I try to run the staking-rewards-collector, I get an error from the Subscan API that the API rate limit is exceeded. Anyone know how I can slow down the query speed or something to get around this?

Solution: enter your own Subscan API key as a new JSON file element "subscan_apikey" in the config file.