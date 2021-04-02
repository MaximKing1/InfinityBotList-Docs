# JavaScript Library

To get stated we first need to download the wrapper using NPM, follow the steps below to get started.

## Posting Stats

### Step 1:

Download the wrapper using the following

```javascript
npm install --save ibl-api
```

### Step 2:

In your main file add the following code

```javascript
const discord = require('discord.js');
const client = new discord.Client();
const { IBL } = require('ibl-api');

const ibl = new IBL(client, 'botAuth');

ibl.postStats() //Posts stats (retrieved from bot client)
ibl.autopost(60 * 60 * 1000) //Posts every hour

client.login('token');
```

Now all the stats like our Guild Count and Shards Count will be posted automatically using the IBL wrapper.

## Webhook Receiver

### Step 1:

First we need to install the API wrapper from NPM if you haven't done so already.

```javascript
npm install --save ibl-api
```

### Step 2:

```javascript
const { IBL } = require('ibl-api');
const discord = require('discord.js');
const client = new discord.Client();

const ibl = new IBL(client, 'botAuth');
ibl.voteWebhook(
    'web auth', //web auth set on bot page
    3001, //port
    '/ibl/webhook' //path to post to, set on bot page
)

ibl.webhook.on("ready", port => {
    console.log(`Infinity Bot List webhook is listening on ${port}`)
});

ibl.webhook.on("vote", async (user, bot, type) => {
  console.log(`${user} voted for ${bot}`);
});

client.login('token');
```

## Ratelimits

You can POST Server and Shard Count stats once every 5 minutes

**Rate Limit Structure**

| ROUTE | REQUEST | REQUESTS ALLOWED PER 5 MINUTES |
| :--- | :--- | :--- |
| /bots/:botid | POST | 3 |

