# snmp_view

## Description

View Names

## Read/write properties

`subtree<String>`

SNMP View Subtree.
Maximum length = 256
Valid char set = ^[.0-9]+

`include<Boolean>`

View Type.
Possible values = [true,false]

`name<String>`

View Name.
Valid char set = ^[-\_.@0-9a-zA-Z]+

## Read only properties

## Operations

**NOTE**: In request payload, Mandatory parameters are marked red and bold.

* [add](#add)
* [delete](#delete)
* [get(all)](#getall)
* [get](#get)

### <a name="add">Add</a>

**URL**: `http://<CBIP>/cb/nitro/v1/config/snmp_view`

**HTTP Method**:POST

**Request Payload:**JSON

```json
{"snmp_view":{
      "subtree":<String_value>,
      "include":<Boolean_value>,
      "name":<String_value>}}
```

**Response Payload**:JSON

```json
{ "snmp_view":{
      "subtree":<String_value>,
      "include":<Boolean_value>,
      "name":<String_value>}}
```

### <a name="delete">Delete</a>

**URL**: `http://<CBIP>/cb/nitro/v1/config/snmp_view/subtree=<String>,name=<String>`

**HTTP Method**:DELETE

**Response Payload**:EMPTY

### <a name="getall">Get (all)</a>

**URL**: `http://<CBIP>/cb/nitro/v1/config/snmp_view`

**HTTP Method**:GET

**Response Payload**:JSON

```json
{ "snmp_view":[{
      "subtree":<String_value>,
      "include":<Boolean_value>,
      "name":<String_value>}, ...]}
```

### <a name= "get">Get</a>

**URL**:`http://<CBIP>/cb/nitro/v1/config/snmp_view/subtree=<String>,name=<String>`

**HTTP Method**: GET

**Response Payload**:JSON

```json
{ "snmp_view":{
      "subtree":<String_value>,
      "include":<Boolean_value>,
      "name":<String_value>}}
```