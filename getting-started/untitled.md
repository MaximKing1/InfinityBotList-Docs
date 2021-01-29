# Fetching User Stats

To fetch user stats from the **InfinityBotList API** you first need to specify the User ID, from your bot you could grab the `message.author.id` or the user could specify the ID using args, from there you will add that as a  Domain Parameters. Follow the steps below.

#### Domain

`/api/users/:userID`  
Where is says `:userID` please replace with the User ID of the person your trying to lookup. \(Example: `:12345678910`\)

#### Domain Parameters

":id" means userID

#### Headers

"Content-Type": application/json

#### JSON

`res.json`: receive response from our API handler

#### RESPONSE

Success: \[200\] "USER STATS" \(JSON\)

Not Found: \[404\] "Couldn't find user!"

