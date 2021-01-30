# Fetching Bot Stats

To fetch bot stats from the **InfinityBotList API** you first need to specify your Bot ID, you can find this on your Discord Developer Portal or from the edit bot page.

#### Domain

`/api/bots/:botID/info`  
Where is says `:botID` please replace with the Bots ID

#### Domain Parameters

":botID" means your Bot ID

#### Headers

"Content-Type": application/json

#### JSON

`res.json`: receive response from our API handler

#### RESPONSE

Success: \[200\] "BOT STATS" \(JSON\)

Not Found: \[404\] "Couldn't find bot!"

