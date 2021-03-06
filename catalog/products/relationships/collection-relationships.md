# Collection Relationships

{% api-method method="post" host="https://api.moltin.com" path="/v2/products/:productId/relationships/collections " %}
{% api-method-summary %}
Create Collection Relationship\(s\)
{% endapi-method-summary %}

{% api-method-description %}
Create a product relationship to one or many Collections. If any relationships already exist, the one's made in the request will be added to them.
{% endapi-method-description %}

{% api-method-spec %}
{% api-method-request %}
{% api-method-path-parameters %}
{% api-method-parameter name="productId" type="string" required=true %}
The **ID** of the product you wish to relate to the collection\(s\).
{% endapi-method-parameter %}
{% endapi-method-path-parameters %}

{% api-method-headers %}
{% api-method-parameter name="Authorization" type="string" required=true %}
The Bearer token to grant access to the API.
{% endapi-method-parameter %}
{% endapi-method-headers %}

{% api-method-body-parameters %}
{% api-method-parameter name="data\[\].type" type="string" required=true %}
Represents the type of object \(should be **collection**\).
{% endapi-method-parameter %}

{% api-method-parameter name="data\[\].id" type="string" required=true %}
The **ID** of the collection.
{% endapi-method-parameter %}
{% endapi-method-body-parameters %}
{% endapi-method-request %}

{% api-method-response %}
{% api-method-response-example httpCode=200 %}
{% api-method-response-example-description %}

{% endapi-method-response-example-description %}

```bash
{
    "data": [
        {
            "type": "collection",
            "id": "5ab3deca-1f11-47b7-a409-24ea3234d72c"
        },
        {
          "type": "collection",
          "id": "2c740aa0-7fb7-4bd6-9347-78988cf60f9a"
        }
    ]
}
```
{% endapi-method-response-example %}
{% endapi-method-response %}
{% endapi-method-spec %}
{% endapi-method %}

{% tabs %}
{% tab title="cURL" %}
```javascript
curl -X "POST" https://api.moltin.com/v2/products/:productId/relationships/collections \
     -H "Authorization: Bearer XXXX" \
     -H "Content-Type: application/json" \
     -d $'{
      "data": [
        {
          "type": "collection",
          "id": "5ab3deca-1f11-47b7-a409-24ea3234d72c"
        },
        {
          "type": "collection",
          "id": "2c740aa0-7fb7-4bd6-9347-78988cf60f9a"
        }
      ]
    }'
```
{% endtab %}

{% tab title="JavaScript SDK" %}
```javascript
 const MoltinGateway = require('@moltin/sdk').gateway

const Moltin = MoltinGateway({
  client_id: 'X',
  client_secret: 'X'
})

const productId = 'XXXX'

const collectionIds = [
    '5ab3deca-1f11-47b7-a409-24ea3234d72c',
    '2c740aa0-7fb7-4bd6-9347-78988cf60f9a'
]

Moltin.Products.CreateRelationships(productId, 'collection', collectionIds).then((relationships) => {
  // Do something
})
```
{% endtab %}
{% endtabs %}

{% api-method method="put" host="https://api.moltin.com" path="/v2/products/:productId/relationships/collections" %}
{% api-method-summary %}
Update Collection Relationship\(s\)
{% endapi-method-summary %}

{% api-method-description %}
Replace the relationships between a Product and a Collection. Unlike a **POST** to this endpoint, a **PUT** overrides any existing relationships.
{% endapi-method-description %}

{% api-method-spec %}
{% api-method-request %}
{% api-method-path-parameters %}
{% api-method-parameter name="productId" type="string" required=true %}
The **ID** of the product you wish to relate to the collection\(s\).
{% endapi-method-parameter %}
{% endapi-method-path-parameters %}

{% api-method-headers %}
{% api-method-parameter name="Authorization" type="string" required=true %}
The Bearer token to grant access to the API.
{% endapi-method-parameter %}
{% endapi-method-headers %}

{% api-method-body-parameters %}
{% api-method-parameter name="data\[\].type" type="string" required=true %}
Represents the type of object \(should be **collection**\).
{% endapi-method-parameter %}

{% api-method-parameter name="data\[\].id" type="string" required=true %}
The **ID** of the collection.
{% endapi-method-parameter %}
{% endapi-method-body-parameters %}
{% endapi-method-request %}

{% api-method-response %}
{% api-method-response-example httpCode=200 %}
{% api-method-response-example-description %}

{% endapi-method-response-example-description %}

```bash
{
    "data": [
        {
            "type": "collection",
            "id": "2c740aa0-7fb7-4bd6-9347-78988cf60f9a"
        }
    ]
}
```
{% endapi-method-response-example %}
{% endapi-method-response %}
{% endapi-method-spec %}
{% endapi-method %}

{% tabs %}
{% tab title="cURL" %}
```javascript
curl -X "PUT" https://api.moltin.com/v2/products/{PRODUCT_ID}/relationships/collections \
     -H "Authorization: Bearer XXXX" \
     -H "Content-Type: application/json" \
     -d $'{
      "data": [
        {
          "type": "collection",
          "id": "2c740aa0-7fb7-4bd6-9347-78988cf60f9a"
        }
      ]
    }'
```
{% endtab %}

{% tab title="JavaScriptSDK" %}
```javascript
const MoltinGateway = require('@moltin/sdk').gateway

const Moltin = MoltinGateway({
  client_id: 'X',
  client_secret: 'X'
})

const productId = 'XXXX'

var collectionIds = [
    '2c740aa0-7fb7-4bd6-9347-78988cf60f9a'
];

Moltin.Products.UpdateRelationships(productId, 'collection', collectionIds).then((relationships) => {
    // Do something
});
```
{% endtab %}
{% endtabs %}

{% api-method method="delete" host="https://api.moltin.com" path="/v2/products/:productId/relationships/collections" %}
{% api-method-summary %}
Delete Collection Relationship\(s\)
{% endapi-method-summary %}

{% api-method-description %}
Remove a relationship between a Product and a Collection\(s\). This deletes the relationship specified in the payload.
{% endapi-method-description %}

{% api-method-spec %}
{% api-method-request %}
{% api-method-path-parameters %}
{% api-method-parameter name="productId" type="string" required=true %}
The **ID** of the product you wish to relate to the collection\(s\).
{% endapi-method-parameter %}
{% endapi-method-path-parameters %}

{% api-method-headers %}
{% api-method-parameter name="Authorization" type="string" required=true %}
The Bearer token to grant access to the API.
{% endapi-method-parameter %}
{% endapi-method-headers %}

{% api-method-body-parameters %}
{% api-method-parameter name="data\[\].type" type="string" required=true %}
Represents the type of object \(should be **collection**\).
{% endapi-method-parameter %}

{% api-method-parameter name="data\[\].id" type="string" required=true %}
The **ID** of the collection.
{% endapi-method-parameter %}
{% endapi-method-body-parameters %}
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

{% tabs %}
{% tab title="cURL" %}
```javascript
curl -X "DELETE" https://api.moltin.com/v2/products/:productId/relationships/collections \
     -H "Authorization: Bearer XXXX" \
     -H "Content-Type: application/json" \
     -d $'{
      "data": [
        {
          "type": "collection",
          "id": "2c740aa0-7fb7-4bd6-9347-78988cf60f9a"
        }
      ]
    }'
```
{% endtab %}

{% tab title="JavaScript SDK" %}
```javascript
const MoltinGateway = require('@moltin/sdk').gateway

const Moltin = MoltinGateway({
  client_id: 'X',
  client_secret: 'X'
})

const productId = 'XXXX'

var collectionIds = [
    '2c740aa0-7fb7-4bd6-9347-78988cf60f9a'
];

Moltin.Products.DeleteRelationships(productId, 'collection', collectionIds).then((relationships) => {
    // Do something
});
```
{% endtab %}
{% endtabs %}

