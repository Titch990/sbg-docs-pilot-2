---
title: "List user resources"
layout: default
excerpt: "API list user resources returns information about the specified user."
endpoint: users/{username}
---
# {{ site.data.api.rest-method-icons.get }} List user resources

This call returns information about the specified user. Currently you can only view  your own user information, so this call is equivalent to the call to [Get my information]

## Endpoint

This way is cumbersome but works. The value for ```{{ "{{" }} page.endpoint }}``` is correctly substituted in the snippet.

{% include /APIs/aws-gcs-endpoint.md %}

This way is tidy but doens't work! The value for ```{{ "{{" }} page.endpoint }}``` is *not* correctly substituted in the snippet.

{{ site.data.api.aws-gcs-endpoint}}

TEST LINE page.endpoint is {{ page.endpoint }}

Replace `{username}` with your own user name. Remember to use the same capitalization that you used when you registered on the Seven Bridges Platform.
 
## Request

### Example request
[block:code]
{
  "codes": [
    {
      "code": "GET /v2/users/RFranklin HTTP/1.1\nHost: api.sbgenomics.com\nX-SBG-Auth-Token: 3259c50e1ac5426ea8f1273259740f74",
      "language": "http",
      "name": null
    },
    {
      "code": "curl -s -H \"X-SBG-Auth-Token: 6282d5e2121d43e7900e9d52b15845e7\" -H \"content-type: application/json\" -X GET \"https://api.sbgenomics.com/v2/users/RFranklin\"",
      "language": "curl",
      "name": "cURL"
    }
  ],
  "sidebar": true
}
[/block]
### Header Fields
[block:parameters]
{
  "data": {
    "h-0": "Name",
    "h-1": "Description",
    "0-0": "`X-SBG-Auth-Token`\n_required_",
    "0-1": "Your Seven Bridges Platform [authentication token](doc:get-your-authentication-token).",
    "h-2": ""
  },
  "cols": 2,
  "rows": 1
}
[/block]
### Path parameters
[block:parameters]
{
  "data": {
    "h-0": "Name",
    "h-1": "Description",
    "0-0": "`username`",
    "0-1": "Your Seven Bridges Platform username."
  },
  "cols": 2,
  "rows": 1
}
[/block]
### Query parameters
[block:parameters]
{
  "data": {
    "h-0": "Name",
    "h-1": "Data type",
    "h-2": "Description",
    "0-0": "**fields**",
    "0-1": "string",
    "0-2": "Selector specifying a subset of fields to include in the response."
  },
  "cols": 3,
  "rows": 1
}
[/block]
## Response

[See a list of Seven Bridges Platform-specific response codes that may be contained in the body of the response.](doc:api-status-codes)

### Example response body 
[block:code]
{
  "codes": [
    {
      "code": "{\n  \"href\": \"https://api.sbgenomics.com/v2/users/RFranklin\",\n  \"username\": \"RFranklin\",\n  \"email\": \"rosalind.franklin@sbgenomics.com\",\n  \"first_name\": \"Rosalind\",\n  \"last_name\": \"Franklin\",\n  \"affiliation\": \"Seven Bridges\",\n  \"phone\": \"\",\n  \"address\": \"\",\n  \"city\": \"London\",\n  \"state\": \"\",\n  \"country\": \"United Kingdom\",\n  \"zip_code\": \"\"\n}",
      "language": "json"
    }
  ],
  "sidebar": true
}
[/block]

<div align="right"><a href="#top">top</a></div>

<hr>

<div align="right"><a href="http://docs.sevenbridges.com/docs/billing">Next section: <i>Learn about API Billing calls <b>>></b></i></a></div>