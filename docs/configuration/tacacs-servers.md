# tacacs\_servers

## Description

Configuration of TACACS server. This NITRO resource is applicable for CloudBridge 400, 800, 1000, 2000, 2000WS, 3000, 4000, and 5000 platforms only.

## Read/write properties

`authtimeout<String>`

The maximum number of seconds the system will wait for a response from the TACACS server..

`tacacskey<String>`

TACACS server's shared secret key..

`ip<String>`

TACACS server IP address..

`name<String>`

Name of TACACS server..

`accounting<String>`

Enable accounting in the tacacs server..
Possible values = [true,false]

`port<String>`

TACACS server port.

## Read only properties

## Operations

NOTE: In request payload, Mandatory parameters are marked red and bold.

* [add](#add)
* [delete](#delete)
* [get(all)](#getall)
* [get](#get)
* [modify](#modify)

### <a name="add">Add</a>

**URL:** `http://<CBIP>/cb/nitro/v1/config/tacacs_servers`

**HTTP Method:** POST

**Request Payload:** JSON

```json
{"tacacs_servers":{
      "authtimeout":<String_value>,
      "tacacskey":<String_value>,
      "ip":<String_value>,
      "name":<String_value>,
      "accounting":<String_value>,
      "port":<String_value>}}
```

**Response Payload:** JSON

```json
{ "tacacs_servers":{
      "authtimeout":<String_value>,
      "tacacskey":<String_value>,
      "ip":<String_value>,
      "name":<String_value>,
      "accounting":<String_value>,
      "port":<String_value>}}
```

### <a name="delete">Delete</a>

**URL:** `http://<CBIP>/cb/nitro/v1/config/tacacs_servers/<name>`

**HTTP Method:** DELETE

**Response Payload:** EMPTY

### <a name="getall">Get (all)</a>

**URL:** `http://<CBIP>/cb/nitro/v1/config/tacacs_servers`

**HTTP Method:** GET

**Response Payload:** JSON

```json
{ "tacacs_servers":[{
      "authtimeout":<String_value>,
      "tacacskey":<String_value>,
      "ip":<String_value>,
      "name":<String_value>,
      "accounting":<String_value>,
      "port":<String_value>}, ...]}
```

### <a name="get">Get</a>

**URL:** `http://<CBIP>/cb/nitro/v1/config/tacacs_servers/<name>`

**HTTP Method:** GET

**Response Payload:** JSON

```json
{ "tacacs_servers":{
      "authtimeout":<String_value>,
      "tacacskey":<String_value>,
      "ip":<String_value>,
      "name":<String_value>,
      "accounting":<String_value>,
      "port":<String_value>}}
```

### <a name="modify">Modify</a>

**URL:** `http://<CBIP>/cb/nitro/v1/config/tacacs_servers/<name>`

**HTTP Method:** PUT

**Request Payload:** JSON

```json
{"tacacs_servers":{
      "authtimeout":<String_value>,
      "tacacskey":<String_value>,
      "ip":<String_value>,,
      "accounting":<String_value>,
      "port":<String_value>}}
```

**Response Payload:** JSON

```json
{ "tacacs_servers":{
      "authtimeout":<String_value>,
      "tacacskey":<String_value>,
      "ip":<String_value>,
      "name":<String_value>,
      "accounting":<String_value>,
      "port":<String_value>}}
```