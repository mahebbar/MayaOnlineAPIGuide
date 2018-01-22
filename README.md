# Introduction

This file file serves as your book's preface, a great place to describe your book's content and ideas.

## Why Use the REST API

TheCisco IMC SupervisorREST API allows an application to interact withCisco IMC Supervisorprogrammatically. These requests provide access to resources inCisco IMC Supervisor.

The API accepts and returns HTTP messages that contain Extensible Markup Language \(XML\) documents. The XML payload contained in an HTTP message describes a method or managed object \(MO\) inCisco IMC Supervisor. You can use any programming language to generate the messages and the XML payload.

## How the API Works

In RESTful APIs, the HTTP method specifies the action you want to perform and the URI specifies the resource you want to access.

REST API uses the following HTTP methods to perform create, read, update, and delete \(CRUD\) operations:

### HTTP Methods

#### POST

Submits data to be processed by the specified resource. The data to be processed is included in the request body. A POST operation can create a new resource.

* Every POST request must include an XML body containing a definition of the new resource.
* For a POST operation to create a new resource, the location header in the HTTP response must contain the complete URL to be used for subsequent PUT, GET, and DELETE commands.
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

## How to Interpret the HTTP Response

The following HTTP status codes are returned by MayaOnline:

* 401 Unauthorized—The API key is not a valid key.
* 200 OK—MayaOnline processed the request. The actual status of the request is in the body of the response.

## How to Make a REST API Request



### **Example API URL:**



### 



