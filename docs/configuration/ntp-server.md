# ntp_server

## Description

NTP Server

## Read/write properties

`ntpserver <String>`

IP address or hostname of NTP server..
Maximum value = 255

## Read only properties

## Operations

**Note:** In request payload, Mandatory parameters are marked red and bold.

* [add](#add)
* [delete](#delete)
* [get(all)](#getall)
* [get](#get)

### <a name="add">Add</a>'

URL: `http://<CBIP>/cb/nitro/v1/config/ntp_server`

HTTP Method: POST

Request Payload: JSON

```json
{"ntp_server":{
      "ntpserver":<String_value>}}
```

Response Payload: JSON

```json
{ "ntp_server":{
      "ntpserver":<String_value>}}
```

### <a name="delete">Delete</a>'

URL: `http://<CBIP>/cb/nitro/v1/config/ntp_server/<ntpserver>`

HTTP Method: DELETE

Response Payload: EMPTY

### <a name="getall">Get (All)</a>'

URL: `http://<CBIP>/cb/nitro/v1/config/ntp_server`

HTTP Method: GET

Response Payload: JSON

```json
{ "ntp_server":[{
      "ntpserver":<String_value>}, ...]}
```

### <a name="get">Get</a>'

URL: `http://<CBIP>/cb/nitro/v1/config/ntp_server/<ntpserver>`

HTTP Method: GET

Response Payload: JSON

```json
{ "ntp_server":{
      "ntpserver":<String_value>}}
```