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
const { Client } = require('ibl-api');

const IBL = new Client(client, 'botAuth');

IBL.autoPost({
    botID: '474745745457', // Your botID
    timerLoop: 300000, // This is in MS, this is default to 5 minutes
}, true);

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
const { Client } = require('ibl-api');
const discord = require('discord.js');
const client = new discord.Client();

const IBL = new Client(client, 'botAuth', {
  webPort: 3001,
  webPath: '/IBLhook',
  webAuth: 'Auth you placed in custom webhooks',
});
IBL.voteWebhook(true);

IBL.on('ready', () => {
  console.log('Server Ready!');
});

IBL.on('vote', async (userID, botID, type) => {
  console.log(userID + 'Voted For' + botID);
});

client.login('token');
```

## Ratelimits

You can POST Server and Shard Count stats once every 5 minutes

**Rate Limit Structure**

| ROUTE | REQUEST | REQUESTS ALLOWED PER 5 MINUTES |
| :--- | :--- | :--- |
| /bots/:botid | POST | 3 |

