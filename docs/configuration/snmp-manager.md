# snmp_manager

## Description

SNMP Manager Configuration

## Read/write properties

`community<String>`

Community.
Valid char set = `^[-_.@0-9a-zA-Z]+`

`snmpmanager<String>`

Ip Address of SNMP Manager (IPv4/IPv6 string).
Bitmask = Required (format IP/bitmask)

## Read only properties

## Operations

**NOTE**: In request payload, Mandatory parameters are marked red and bold.

* [add](#add)
* [delete](#delete)
* [get(all)](#getall)
* [get](#get)

### <a name="add">Add</a>

**URL**: `http://<CBIP>/cb/nitro/v1/config/snmp_manager`

**HTTP Method**: POST

**Request Payload**: JSON

```json
{"snmp_manager":{
      "community":<String_value>,
      "snmpmanager":<String_value>}}
```

Response Payload:JSON

```json
{ "snmp_manager":{
      "community":<String_value>,
      "snmpmanager":<String_value>}}
```
### <a name="delete">Delete</a>

**URL**: `http://<CBIP>/cb/nitro/v1/config/snmp_manager/community=<String>,snmpmanager=<String>`

**HTTP Method**: DELETE

**Response Payload**: EMPTY

### <a name="getall">Get (all)</a>

**URL**: `http://<CBIP>/cb/nitro/v1/config/snmp_manager`

**HTTP Method**: GET

**Response Payload**: JSON

```json
{ "snmp_manager":[{
      "community":<String_value>,
      "snmpmanager":<String_value>}, ...]}
```

### <a name="get">Get</a>

**URL**: http://<CBIP>/cb/nitro/v1/config/snmp_manager/community=<String>,snmpmanager=<String>

**HTTP Method**: GET

**Response Payload**: JSON

```json
{ "snmp_manager":{
      "community":<String_value>,
      "snmpmanager":<String_value>}}
```