# Fetching User Stats

To fetch user stats from the **InfinityBotList API** you first need to specify the User ID, from your bot you could grab the `message.author.id` or the user could specify the ID using args, from there you will add that as a  Domain Parameters. Follow the steps below.

#### Domain

`api.infinitybotlist.com/user/:userID`  
Where is says `:userID` please replace with the User ID of the person your trying to lookup. \(Example: `:12345678910`\)

#### Domain Parameters

":userID" means the user ID

#### Headers

"Content-Type": application/json

#### JSON

`res.json`: receive response from our API handler

#### RESPONSE

Success: \[200\] "USER STATS" \(JSON\)

Not Found: \[404\] "Couldn't find user!"

{% api-method method="get" host="https://api.infinitybotlist.com" path="/user/:userID" %}
{% api-method-summary %}
Getting User Stats
{% endapi-method-summary %}

{% api-method-description %}
Get User Stats From The API.
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
res.json
```
{% endapi-method-response-example %}

{% api-method-response-example httpCode=404 %}
{% api-method-response-example-description %}

{% endapi-method-response-example-description %}

```
Couldn't find user
```
{% endapi-method-response-example %}
{% endapi-method-response %}
{% endapi-method-spec %}
{% endapi-method %}

