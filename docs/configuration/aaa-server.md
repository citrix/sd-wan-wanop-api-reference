# aaa_server

## Description

AAA server configuration. This NITRO resource is applicable for CloudBridge 400, 800, 1000, 2000, 2000WS, 3000, 4000, and 5000 platforms only.

## Read/write properties

`servername <String>`

Name of AAA server. This server should be already configured using radius_servers/tacacs_servers..

`servertype <String>`

Type of AAA server. Possible values = [LOCAL,RADIUS,TACACS]

`fallbacklocalauthentication <String>`

Enable/disable local fallback authentication. Possible values = [true,false]

## Read only properties

## Operations

**Note**: In request payload, Mandatory parameters are marked red and bold.

* [get](#get)
* [modify](#modify)

### <a name="get">Get</a>

URL: `http://<CBIP>/cb/nitro/v1/config/aaa_server`

HTTP Method: GET

Response Payload: JSON

```json
{ "aaa_server":{  
      "servername":<String_value>,  
      "servertype":<String_value>,  
      "fallbacklocalauthentication":<String_value>}}
```

### <a name="modify">Modify</a>

URL: `http://<CBIP>/cb/nitro/v1/config/aaa_server/<>`

HTTP Method: PUT

Request Payload: JSON

```json
{"aaa_server":{
      "servername":<String_value>,,
      "fallbacklocalauthentication":<String_value>}}
```

Response Payload: JSON

```json
{ "aaa_server":{  
      "servername":<String_value>,  
      "servertype":<String_value>,  
      "fallbacklocalauthentication":<String_value>}}
```