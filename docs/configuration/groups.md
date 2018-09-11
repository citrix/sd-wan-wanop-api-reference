# groups

## Description

Configuration of Groups. This NITRO resource is applicable for CloudBridge 400, 800, 1000, 2000, 2000WS, 3000, 4000, and 5000 platforms only.

## Read/write properties

`enablesessiontimeout <String>`

Enables session timeout for group..
Possible values = [true,false]

`sessiontimeout <String>`

Session timeout for the Group..

`permission <String>`

Permission for the group (admin/read-only)..
Possible values = [admin,readonly]

`sessiontimeoutunit <String>`

Session timeout unit for the Group..
Possible values = [Minutes,Hours]

`name <String>`

Group Name..

`users <[String,...]>`

Users belong to the group..

## Read only properties

## Operations

**Note:** In request payload, Mandatory parameters are marked red and bold.

* [add](#add)
* [delete](#delete)
* [get(all)](#getall)
* [get](#get)
* [modify](#modify)

### <a name="add">Add</a>

URL: `http://<CBIP>/cb/nitro/v1/config/groups`

HTTP Method: POST

Request Payload: JSON

```json
{"groups":{
      "enablesessiontimeout":<String_value>,
      "sessiontimeout":<String_value>,
      "permission":<String_value>,
      "sessiontimeoutunit":<String_value>,
      "name":<String_value>,
      "users":<String_value>}}
```

Response Payload:JSON

```json
{ "groups":{
      "enablesessiontimeout":<String_value>,
      "sessiontimeout":<String_value>,
      "permission":<String_value>,
      "sessiontimeoutunit":<String_value>,
      "name":<String_value>,
      "users":<String_value>}}
```

### <a name="delete">Delete</a>

URL: `http://<CBIP>/cb/nitro/v1/config/groups/<name>`

HTTP Method: DELETE

Response Payload: EMPTY

### <a name="getall">Get (All)</a>

URL: `http://<CBIP>/cb/nitro/v1/config/groups`

HTTP Method: GET

Response Payload: JSON

```json
{ "groups":[{
      "enablesessiontimeout":<String_value>,
      "sessiontimeout":<String_value>,
      "permission":<String_value>,
      "sessiontimeoutunit":<String_value>,
      "name":<String_value>,
      "users":<String_value>}, ...]}
```

### <a name="get">Get</a>

URL: `http://<CBIP>/cb/nitro/v1/config/groups/<name>`

HTTP Method: GET

Response Payload: JSON

```json
{ "groups":{
      "enablesessiontimeout":<String_value>,
      "sessiontimeout":<String_value>,
      "permission":<String_value>,
      "sessiontimeoutunit":<String_value>,
      "name":<String_value>,
      "users":<String_value>}}
```

### <a name="modify">Modify</a>

URL: `http://<CBIP>/cb/nitro/v1/config/groups/<name>`

HTTP Method: PUT

Request Payload: JSON

```json
{"groups":{
      "enablesessiontimeout":<String_value>,
      "sessiontimeout":<String_value>,
      "permission":<String_value>,
      "sessiontimeoutunit":<String_value>,,
      "users":<String_value>}}
```

Response Payload: JSON

```json
{ "groups":{
      "enablesessiontimeout":<String_value>,
      "sessiontimeout":<String_value>,
      "permission":<String_value>,
      "sessiontimeoutunit":<String_value>,
      "name":<String_value>,
      "users":<String_value>}}
```