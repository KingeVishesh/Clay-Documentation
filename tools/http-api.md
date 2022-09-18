# HTTP API

Even though Clay has many inbuilt integrations, you might want to use some that aren't offered by Clay. You can make use of Clay's HTTP API integration in situations like these. It allows you to call any API, similar to Postman, Make.com, or Zapier.

## Adding the Module&#x20;

Like any integration in clay, you will need to add the HTTP API integration. By clicking on the top “Add Integration” button.

## Setup the Module

Setting up HTTP integration does require more work than any other integration. Every API will require a different set of setups.

### Common API inputs

#### **Method**&#x20;

Method is the HTTP method of your call, e.g. GET, POST, PATCH, or DELETE. You can know which method to use by reading the API documentation of the API which you are using.&#x20;

#### Endpoint

Endpoint will be the URL where you will be requesting the API. You can see the URL mentioned in the curl command. Every endpoint is made to do different things so be sure that you are entering the right URL for the request.

#### Body

Body is the underlying data you want to put into the request. Unlike Method or Endpoint, this is optional. Some APIs require it and some don't. Clay only allows you to put a raw JSON body right now, you might also need to use a JSON minifier too for your body.&#x20;

It will look something like - {“a”:1, “b”:2}

#### **Headers**

Headers are similar to Body, except unlike Body, which can take arrays or plain text as input, they only handle Key-Value pairs. It is commonly used in request authentication or to specify the content type of the body.

### Clay Functions

#### Remove null & undefined values

This is a Clay toggle that removes the empty values from the Body and Headers. This is only helpful when the API is extremely sensitive to this info.

#### Run as a button

This is also a Clay function that allows you to run the API on a button, it works the same way as it works in other integration in Clay.

### **Rate Limits**

#### Request Limits

The number of requests you can make in a given timeframe which can be defined in duration. Some APIs limit you on how many requests you can do in a minute, an hour, or a day. So you can limit that number of requests here.

#### Duration

This is the timeframe you set for the request in Milliseconds. This value needs to be between 1 and 900000 (15 minutes).

## Examples

### Clearbit Autocomplete Name to Domain API
