# Posting Bot Stats

To post your bot stats to the **InfinityBotList API** you first need to find out your Client ID this can be located on the [Discord Developer Portal](https://discord.com/developers/applications) in your bot application, now follow the steps below to get started!

#### Domain

`/api/bots/:id`  
Where is says `:id` please replace with your bot's ID / Client ID. \(Example: `:12345678910`\)

#### Domain Parameters

":id" means botID or your clientID

#### Headers

"authorization": Your bot's API token, which can be found on its page  
"Content-Type": application/json

#### Body Parameters

"servers": Bot servers count  
"shards": Bot shards count if sharding

#### JSON

`res.json`: receive response from our API handler

#### RESPONSE

Success: \[200\] "MESSAGE"

Not Found: \[404\] "MESSAGE"

Rate Limit: \[429\] "MESSAGE"

Internal Server Error: \[500\] "MESSAGE"  
  
Error: \[400\] "MESSAGE"

### Example:

{% api-method method="post" host="" path="/api/bots/:id" %}
{% api-method-summary %}
Posting Stats
{% endapi-method-summary %}

{% api-method-description %}
Posting The Stats To The API.
{% endapi-method-description %}

{% api-method-spec %}
{% api-method-request %}
{% api-method-path-parameters %}
{% api-method-parameter name="Authorization " type="string" required=true %}
YOUR\_TOKEN
{% endapi-method-parameter %}
{% endapi-method-path-parameters %}
{% endapi-method-request %}

{% api-method-response %}
{% api-method-response-example httpCode=200 %}
{% api-method-response-example-description %}

{% endapi-method-response-example-description %}

```
SUCCESS: res.json
```
{% endapi-method-response-example %}

{% api-method-response-example httpCode=429 %}
{% api-method-response-example-description %}

{% endapi-method-response-example-description %}

```
RATE LIMITED
```
{% endapi-method-response-example %}
{% endapi-method-response %}
{% endapi-method-spec %}
{% endapi-method %}

