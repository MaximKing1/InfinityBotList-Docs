# JavaScript Library

To get stated we first need to download the wrapper using NPM, follow the steps below to get started.

### Posting Stats

#### Step 1:

Download the wrapper using the following

```javascript
npm i infinity-api
```

#### Step 2:

In your main file add the following code

```javascript
const IBL = require("infinity-api"); // We import our api
const stats = new IBL("Your BotID", "Your Bot Api token") // Add botID string, And Authorization token from the bot page

    setInterval(() => { 
        stats.postStats("Guilds count" /*, "Shards Count" */) // Post guilds count and shards count
    }, 3e5)
```

Now all the stats like our Guild Count and Shards Count will be posted automatically using the IBL wrapper.

### Get Requests

We will show you how to fetch data such as votes and other data from the IBL API, follow the steps below to get started!

#### Step 1:

First we need to install the API wrapper from NPM if you haven't done so already.

```javascript
npm i infinity-api
```

#### Step 2:

Now we need to add the following to our main code

```javascript
const IBL = require("infinity-api"); // We import our api
const stats = new IBL("Your BotID", "Your Bot Api token") // Add botID string, And Authorization token from the bot page

// Get Bot Stats
    stats.getStats((data) => {
        console.log(data)
    })

// Get User Stats
    stats.getUser("userID", (data) => {
        console.log(data)
    })
```

### Ratelimits

You can POST Server and Shard Count stats once every 5 minutes

**Rate Limit Structure**

| ROUTE | TYPE | OVERVIEW |
| :--- | :--- | :--- |
| timestamp | Integar | Time of vote time |
| userID | Snowflake | DiscordID of the voted user |
| botID | Snowflake | DiscordID of the bot |
| type | String | Type of request |

