# snmp

## Description

Configure SNMP status.

## Read/write properties

`status<Boolean>`

SNMP status..
Possible values = [true,false]

## Read only properties

## Operations

**NOTE**: In request payload, Mandatory parameters are marked red and bold.

* [get](#get)
* [modify](#modify)

### <a name="get">Get</a>

**URL:** `http://<CBIP>/cb/nitro/v1/config/snmp`

**HTTP Method:** GET

**Response Payload:** JSON

```json
{ "snmp":{
      "status":<Boolean_value>}}
```

### <a name="modify">Modify</a>

**URL:** `http://<CBIP>/cb/nitro/v1/config/snmp`

**HTTP Method:** PUT

**Request Payload:** JSON

```json
{"snmp":{
      "status":<Boolean_value>}}
```

**Response Payload:** JSON

```json
{ "snmp":{
      "status":<Boolean_value>}}
```