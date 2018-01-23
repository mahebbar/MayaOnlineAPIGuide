# Introduction

This document helps you understand why you must use REST APIs, it's working, methods, and  examples.

## Why Use the REST API

The REST API allows an application to interact with MayaOnline programmatically. These requests provide access to resources in MayaOnline.

The API accepts and returns HTTP messages that contain Extensible Markup Language \(XML\) documents. The XML payload contained in an HTTP message describes a method or managed object \(MO\) in MayaOnline. You can use any programming language to generate the messages and the XML payload.

## How the API Works

In RESTful APIs, the HTTP method specifies the action you want to perform and the URI specifies the resource you want to access.

REST API uses the following HTTP methods to perform create,  update, and delete operations:

### HTTP Methods

#### POST

Submits data to be processed by the specified resource. The data to be processed is included in the request body. A POST operation can create a new resource.

* Every POST request must include an XML body containing a definition of the new resource.
* For a POST operation to create a new resource, the location header in the HTTP response must contain the complete URL to be used for subsequent PUT and DELETE commands.
* The HTTP POST response to a create request must have a 200 return code and a location header containing the URI of the newly created resource in the HTTP header.

#### PUT

Updates the specified resource with new information. The data that is included in the PUT operation replaces the previous data.

* The PUT operation cannot be used to create a new resource.
* The request body of a PUT operation must contain the complete representation of the mandatory attributes of the resource in XML format.

#### DELETE

Deletes a resource.

* If you delete a resource that has already been deleted, a 404 Not Found response is returned.
* The HTTP DELETE operation should not have a request body. If information is passed in a GET request, query parameters must be used instead.

## Generating an API Access Key



You can use the following example to access MayaOnline API in third party applications. The publicValue and secretValue must be added in the header in the following format where encdata contains base64 of public and private key.

headers: {

     'Authorization' : 'Basic ' + encdata,

  },

=================

HTTP/1.1 201

date:

Tue, 23 Jan 2018 06:19:28 GMT

x-api-user-id:

1a77

server:

nginx/1.13.6

x-api-client-ip:

106.51.73.198

x-api-roles:

user

strict-transport-security:

max-age=15724800; includeSubDomains;

content-type:

application/json; charset=utf-8

status:

201

x-api-account-id:

1a77

x-api-schemas:

https://dev.mayacloud.io/v3/schemas

content-length:

841

expires:

Thu, 01 Jan 1970 00:00:00 GMT

  


{

* "
  id
  "
  : 
  ["1ak52"](https://dev.mayacloud.io/v3/apikeys/1ak52)
  ,
* "
  type
  "
  : 
  ["apiKey"](https://dev.mayacloud.io/v3/schemas/apikey)
  ,
* "
  links
  "
  : {
  * "
    self
    "
    : 
    ["…/v3/apikeys/1ak52"](https://dev.mayacloud.io/v3/apikeys/1ak52)
    ,
  * "
    account
    "
    : 
    ["…/v3/apikeys/1ak52/account"](https://dev.mayacloud.io/v3/apikeys/1ak52/account)
    ,
  * "
    instances
    "
    : 
    ["…/v3/apikeys/1ak52/instances"](https://dev.mayacloud.io/v3/apikeys/1ak52/instances)
    ,
  * "
    remove
    "
    : 
    ["…/v3/apikeys/1ak52"](https://dev.mayacloud.io/v3/apikeys/1ak52)
    ,
  * "
    update
    "
    : 
    ["…/v3/apikeys/1ak52"](https://dev.mayacloud.io/v3/apikeys/1ak52)
    ,
  * "
    certificate
    "
    : 
    ["…/v3/apikeys/1ak52/certificate"](https://dev.mayacloud.io/v3/apikeys/1ak52/certificate)

  },
* "
  actions
  "
  : { },
* "
  baseType
  "
  : 
  "credential"
  ,
* "
  name
  "
  : 
  "test"
  ,
* "
  state
  "
  : 
  "creating"
  ,
* "
  accountId
  "
  : 
  ["1a77"](https://dev.mayacloud.io/v3/accounts/1a77)
  ,
* "
  clusterId
  "
  : 
  null
  ,
* "
  created
  "
  : 
  "2018-01-23T06:19:29Z"
  ,
* "
  createdTS
  "
  : 
  1516688369000
  ,
* "
  description
  "
  : 
  "test"
  ,
* "
  kind
  "
  : 
  "apiKey"
  ,
* "
  publicValue
  "
  : 
  "B1EC74D92D93610A2F6F"
  ,
* "
  removed
  "
  : 
  null
  ,
* "
  secretValue
  "
  : 
  "Gp355fxSDFNwZpUnq8UGxszBYydc4x5RrXKT1rLM"
  ,
* "
  transitioning
  "
  : 
  "yes"
  ,
* "
  transitioningMessage
  "
  : 
  "Creating"
  ,
* "
  uuid
  "
  : 
  "b41e3c75-188a-4cd5-86bd-d9c4809dfcd4"

}

## How to Interpret the HTTP Response

The following HTTP status codes are returned by MayaOnline:

* 401 Unauthorized—The API key is not a valid key.
* 200 OK—MayaOnline processed the request. The actual status of the request is in the body of the response.

## How to Make a REST API Request

### **Example API URL:**

## How to View Endpoints

Goes here to find all the available end points.

[https://dev.mayacloud.io/v3](https://dev.mayacloud.io/v3)

### Example of Available End Points

`{`

`"id": "v3",`

`"type": "apiVersion",`

`"links": {`

`"accounts": "…/v3/accounts",`

`"apiKeys": "…/v3/apikeys",`

`"certificates": "…/v3/certificates",`

`"clusters": "…/v3/clusters",`

`"externalServices": "…/v3/externalservices",`

`"hosts": "…/v3/hosts",`

`"identities": "…/v3/identities",`

`"instances": "…/v3/instances",`

`"mayaApplications": "…/v3/mayaapplications",`

`"mounts": "…/v3/mounts",`

`"organizations": "…/v3/organizations",`

`"projects": "…/v3/projects",`

`"registries": "…/v3/registries",`

`"schemas": "…/v3/schemas",`

`"secrets": "…/v3/secrets",`

`"self": "…/v3",`

`"serviceProxies": "…/v3/serviceproxies",`

`"services": "…/v3/services",`

`"settings": "…/v3/settings",`

`"slackClusterAssociations": "…/v3/slackclusterassociations",`

`"slackIntegrations": "…/v3/slackintegrations",`

`"stacks": "…/v3/stacks",`

`"storageDrivers": "…/v3/storagedrivers",`

`"storagePools": "…/v3/storagepools",`

`"userPreferences": "…/v3/userpreferences",`

`"volumeTemplates": "…/v3/volumetemplates",`

`"volumes": "…/v3/volumes"`

`},`

`"actions": { },`

`"baseType": "apiVersion"`

## Authorization Endpoint

[https://dev.mayacloud.io/v3/token](https://dev.mayacloud.io/v3/token)

## Example to View Redirect URL for Authentication without Logging In

{

"type": "collection",

"resourceType": "token",

"links": {

"self": "…/v3/token"

},

"createTypes": { },

"actions": { },

"data": \[

{

"id": null,

"type": "token",

"links": {

"remove": null

},

"actions": { },

"baseType": "token",

"accountId": null,

"authProvider": "githubconfig",

"code": null,

"enabled": true,

"inviteCode": null,

"jwt": "d1tRMgFzWffE9QsfA8neVr6iE7LE8QKEi2SkPJeo",

"redirectUrl": "[https://github.com/login/oauth/authorize?client\_id=841b168f866f1f7127e4](https://github.com/login/oauth/authorize?client_id=841b168f866f1f7127e4)",

"security": true,

"slackOauthUrl": "[https://slack.com/oauth/authorize?client\_id=259700574529.277662436016&scope=channels:history,im:history,bot,commands,incoming-webhook,chat:write:user,channels:read,channels:write,chat:write:bot,groups:read,groups:history,groups:write,im:read,mpim:history,usergroups:read](https://slack.com/oauth/authorize?client_id=259700574529.277662436016&scope=channels:history,im:history,bot,commands,incoming-webhook,chat:write:user,channels:read,channels:write,chat:write:bot,groups:read,groups:history,groups:write,im:read,mpim:history,usergroups:read)",

"user": null,

"userType": "user"

}

\],

"sortLinks": { },

"pagination": null,

"sort": null,

"filters": { },

"createDefaults": { }

