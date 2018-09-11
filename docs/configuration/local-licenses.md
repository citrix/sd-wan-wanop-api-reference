# local_licenses

## Description

Local licenses configuration. This NITRO resource is applicable for CloudBridge SM83, SM85, SM88, VPX, 400, 800, 1000, 2000, 2000WS and 3000 platforms only.

## Read/write properties

`content <String>`

Content of license file. The content of license file must be converted to string programatically loading into string data type and then pass to JSON payload. Directly copy paste from license file to JSON objent may not work. Response of get operation will also be in same format. Refer following C++ implementation for example: std::ifstream t(licenseFilePath); std::stringstream buffer; buffer << t.rdbuf(); std::string str = buffer.str(); This str can now be sent as value of content..

`name <String>`

Name of license.

## Read only properties

## Operations

**Note:** In request payload, Mandatory parameters are marked red and bold.

* [add](#add)
* [delete](#delete)
* [get(all)](#getall)
* [get](#get)

### <a name="add">Add</a>

URL: `http://<CBIP>/cb/nitro/v1/config/local_licenses`

HTTP Method: POST

Request Payload: JSON

```json
{"local_licenses":{
      "content":<String_value>,
      "name":<String_value>}}
```

Response Payload: JSON

```json
{ "local_licenses":{
      "content":<String_value>,
      "name":<String_value>}}
```

### <a name="delete">Delete</a>

URL: `http://<CBIP>/cb/nitro/v1/config/local_licenses/<name>`

HTTP Method: DELETE

Response Payload: EMPTY

### <a name="getall">Get (All)</a>

URL: `http://<CBIP>/cb/nitro/v1/config/local_licenses`

HTTP Method: GET

Response Payload: JSON

```json
{ "local_licenses":[{
      "content":<String_value>,
      "name":<String_value>}, ...]}
```
### <a name="get">Get</a>

URL: `http://<CBIP>/cb/nitro/v1/config/local_licenses/<name>`

HTTP Method: GET

Response Payload: JSON

```json
{ "local_licenses":{
      "content":<String_value>,
      "name":<String_value>}}
```