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

{% api-method method="get" host="https://infinitybotlist.com" path="/api/bots/:botID/info" %}
{% api-method-summary %}
Fetching Bot Stats
{% endapi-method-summary %}

{% api-method-description %}
Fetch Bot Stats
{% endapi-method-description %}

{% api-method-spec %}
{% api-method-request %}
{% api-method-headers %}
{% api-method-parameter name="Content-Type" type="string" required=false %}

{% endapi-method-parameter %}
{% endapi-method-headers %}
{% endapi-method-request %}

{% api-method-response %}
{% api-method-response-example httpCode=200 %}
{% api-method-response-example-description %}

{% endapi-method-response-example-description %}

```
BOT STATS" (JSON)
```
{% endapi-method-response-example %}

{% api-method-response-example httpCode=404 %}
{% api-method-response-example-description %}

{% endapi-method-response-example-description %}

```
Couldn't find bot
```
{% endapi-method-response-example %}
{% endapi-method-response %}
{% endapi-method-spec %}
{% endapi-method %}

