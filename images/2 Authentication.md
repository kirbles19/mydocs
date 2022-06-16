---
type: page
title: Authentication
listed: true
slug: authentication
description: 
index_title: Authentication
hidden: 
---published

Torq REST API uses bearer tokens to authenticate requests. You generate a bearer token by sending a request to the Torq authentication server. In the request to the authentication server you'll provide your Torq API key, which consists of a client id and client   secret. After a successful request to the authentication server you'll receive a bearer token that you will pass in the `Authorization`  header for all Torq API requests.

$plugin[{
    "type": "callout",
    "data": {
        "text": "A bearer token is valid for one hour (3,600 seconds).",
        "type": "info",
        "title": "Note"
    }
}]$

## Create an API key

The API key consists of a `client_id`  and `client_secret` . These credentials are used to authenticate when you request a bearer token.

API keys are account-specific. This means that requests are made on the account where the API key used to create the bearer token was created. Make sure the API key you're using to generate the bearer token was created in the account you want to run the requests on.

1. In Torq, click your account icon/avatar.
2. Click **API KEYS &gt; GENERATE A DEVELOPER API KEY**.
3. Give the API key a meaningful name and click **Create**.
4. Copy the Client ID and Client Secret to a safe place. You won't be able to access the Client Secret later.

$plugin[{
    "type": "image",
    "data": {
        "url": "https:\/\/image-archive.developerhub.io\/image\/upload\/v2_5653\/ipuvdnxtqcxl00xqhjhe\/1645973466.png",
        "mode": "responsive",
        "width": 1922,
        "height": 889,
        "caption": null
    }
}]$

## Generate a bearer token

To generate the bearer token, send a request to the endpoint: `https://auth.torq.io/v1/auth/token` . See the sample request below for the full request.

Replace `<CLIENT`_`ID>`_and _`<`_`CLIENT_SECRET>` with the client ID and client secret you received when you created the API key.

### Sample request - cURL

$plugin[{
    "type": "code-block",
    "data": {
        "languageBlocks": [
            {
                "code": "curl POST https:\/\/auth.torq.io\/v1\/auth\/token -H \"Accept: application\/json\"  -H \"Accept-Language: en_US\"  -u \"<CLIENT_ID>:<CLIENT_SECRET>\"  -d \"grant_type=client_credentials\"",
                "title": "cURL",
                "language": "none"
            }
        ]
    }
}]$

### Sample response - cURL

The bearer token is the value of the `access_token` key.

You will pass this token in the authorization header for all API requests: `Authorization: Bearer <token>` .

$plugin[{
    "type": "code-block",
    "data": {
        "languageBlocks": [
            {
                "code": "{\"access_token\":\"81b15ad9-****-2245-****-f05p37053b25\",\"expires_in\":3600,\"token_type\":\"Bearer\"}",
                "title": "Sample response - cURL",
                "language": "json"
            }
        ]
    }
}]$

### Sample request - Torq

You can generate the bearer token in Torq by using an `Send an HTTP Request`  step. You need to add a body field for grant type.

| Field | Value | 
| ---- | ---- | 
| URL | [https://auth.torq.io/v1/auth/token](https://auth.torq.io/v1/auth/token) | 
| Method | POST | 
| Authorization | Basic | 
| Username | The `client_id` you received when creating the API key. | 
| Password | The `client_secret` you received when creating the API key. | 
| Content Type | application/x-www-form-urlencoded | 
| Type | - Name: grant_type\n- Value: client_credentials | 


$plugin[{
    "type": "image",
    "data": {
        "url": "https:\/\/uploads.developerhub.io\/prod\/QKND\/b5tng8nekq1qolz2n7n49jmyb5n9abmahvojocco6w3y28qrlsqef4fqw12s2z5r.png",
        "mode": "responsive",
        "width": 1058,
        "height": 1648,
        "caption": null
    }
}]$

### Sample response - Torq

$plugin[{
    "type": "code-block",
    "data": {
        "languageBlocks": [
            {
                "code": "{\n  \"api_object\": {\n    \"access_token\": \"8266095f-****-****-****-203a47f40c06\",\n    \"expires_in\": 3600,\n    \"token_type\": \"Bearer\"\n  },\n  \"headers\": {\n    \"Access-Control-Allow-Credentials\": \"true\",\n    \"Access-Control-Allow-Origin\": \"https:\/\/app.torq.io\",\n    \"Cache-Control\": \"no-store\",\n    \"Content-Length\": \"96\",\n    \"Content-Type\": \"application\/json;charset=UTF-8\",\n    \"Date\": \"Mon, 21 Mar 2022 15:00:02 GMT\",\n    \"Pragma\": \"no-cache\",\n    \"Strict-Transport-Security\": \"max-age=15724800; includeSubDomains\"\n  },\n  \"status_code\": 200,\n  \"step_status\": {\n    \"code\": 1,\n    \"message\": \"\",\n    \"verbose\": \"\"\n  }\n}",
                "title": "Sample response - Torq (JSON)",
                "language": "json"
            }
        ]
    }
}]$

