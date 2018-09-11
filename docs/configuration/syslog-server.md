# syslog\_server

## Description

Syslog Server

## Read/write properties

`serverip<String>`

IP address of syslog server. (IPv4/IPv6 string).

`port<Integer>`

Syslog server port.
Minimum value = 1
Maximum value = 65535

## Read only properties

## Operations

**NOTE**: In request payload, Mandatory parameters are marked red and bold.

* [add](#add)
* [delete](#delete)
* [get(all)](#getall)
* [get](#get)

### <a name="add">Add</a>

**URL:** `http://<CBIP>/cb/nitro/v1/config/syslog_server`

**HTTP Method:** POST

**Request Payload:** JSON

```json
{"syslog_server":{
      "serverip":<String_value>,
      "port":<Integer_value>}}
```
**Response Payload:** JSON

```json
{ "syslog_server":{
      "serverip":<String_value>,
      "port":<Integer_value>}}
```

### <a name="delete">Delete</a>

**URL:** `http://<CBIP>/cb/nitro/v1/config/syslog_server/serverip=<String>,port=<Integer>`

**HTTP Method:** DELETE

**Response Payload:** EMPTY

### <a name="getall">Get(all)</a>

**URL:** `http://<CBIP>/cb/nitro/v1/config/syslog_server`

**HTTP Method:** GET

**Response Payload:** JSON

```json
{ "syslog_server":[{
      "serverip":<String_value>,
      "port":<Integer_value>}, ...]}
```

### <a name="get">Get</a>

**URL:** `http://<CBIP>/cb/nitro/v1/config/syslog_server/serverip=<String>,port=<Integer>`

**HTTP Method:** GET

**Response Payload:** JSON

```json
{ "syslog_server":{
      "serverip":<String_value>,
      "port":<Integer_value>}}
```