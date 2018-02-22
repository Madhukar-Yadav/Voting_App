# DynamoDB Setup

1. Create a table with name "VotingTable"
    a. Index on candidate string
    b. set read & write channels to 1

2. Add trigger to GenerateDataJSONLambda
    a. select -> Latest result
    b. set batch size to 1
