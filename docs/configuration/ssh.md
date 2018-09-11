# ssh

## Description

Configure SSH status.

## Read/write properties

`enable<Boolean>`

Enable/Disable SSH..
Possible values = [true,false]

## Read only properties

`status<Boolean>`

Current status of SSH daemon..

## Operations

**NOTE**: In request payload, Mandatory parameters are marked red and bold.

* [get](#get)
* [modify](#modify)

### <a name="get">Get</a>

**URL:** `http://<CBIP>/cb/nitro/v1/config/ssh`

**HTTP Method:** GET

**Response Payload:** JSON

```json
{ "ssh":{
      "enable":<Boolean_value>,
      "status":<Boolean_value>}}
```

### <a name="modify">Modify</a>

**URL:** `http://<CBIP>/cb/nitro/v1/config/ssh`

**HTTP Method:** PUT

**Request Payload:** JSON

```json
{"ssh":{
      "enable":<Boolean_value>}}
```

**Response Payload:** JSON

```json
{ "ssh":{
      "enable":<Boolean_value>,
      "status":<Boolean_value>}}
```