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

{% api-method method="get" host="" path="/api/users/:userID" %}
{% api-method-summary %}
Getting User Stats
{% endapi-method-summary %}

{% api-method-description %}
Get User Sats From The API.
{% endapi-method-description %}

{% api-method-spec %}
{% api-method-request %}
{% api-method-path-parameters %}
{% api-method-parameter name="" type="string" required=false %}

{% endapi-method-parameter %}
{% endapi-method-path-parameters %}
{% endapi-method-request %}

{% api-method-response %}
{% api-method-response-example httpCode=200 %}
{% api-method-response-example-description %}

{% endapi-method-response-example-description %}

```

```
{% endapi-method-response-example %}
{% endapi-method-response %}
{% endapi-method-spec %}
{% endapi-method %}

