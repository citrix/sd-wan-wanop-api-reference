# session_params

## Description

Configuration of session parameters.

## Read/write properties

`guibanner <String>`

GUI banner text..

`loginfailurelimit <Integer>`

Login failure limit..
Minimum value = 1

`clibanner <String>`

CLI banner text..

`guibannerenable <Boolean>`

GUI banner enable..
Possible values = [true,false]

`guisessiontimeout <Integer>`

GUI session timeout minutes. Timeout value 0 means, infinite timeout..
Minimum value = 0

`lockouttime <Integer>`

Lockout time seconds..
Minimum value = 1

`maxuserfailures <Integer>`

Maximum failures per user..
Minimum value = 1

`clibannerenable <Boolean>`

CLI banner enable..
Possible values = [true,false]

`clisessiontimeout <Integer>`

CLI session timeout minutes. Timeout value 0 means, infinite timeout..
Minimum value = 0

## Read only properties

## Operations

**Note:** In request payload, Mandatory parameters are marked red and bold.

* [get](#get)
* [modify](#modify)

### <a name="get">Get</a>

URL: `http://<CBIP>/cb/nitro/v1/config/session_params`

HTTP Method: GET

Response Payload: JSON

```json
{ "session_params":{
      "guibanner":<String_value>,
      "loginfailurelimit":<Integer_value>,
      "clibanner":<String_value>,
      "guibannerenable":<Boolean_value>,
      "guisessiontimeout":<Integer_value>,
      "lockouttime":<Integer_value>,
      "maxuserfailures":<Integer_value>,
      "clibannerenable":<Boolean_value>,
      "clisessiontimeout":<Integer_value>}}
```

### <a name="modify">Modify</a>

URL: `http://<CBIP>/cb/nitro/v1/config/session_params`

HTTP Method: PUT

Request Payload: JSON

```json
{"session_params":{
      "guibanner":<String_value>,
      "loginfailurelimit":<Integer_value>,
      "clibanner":<String_value>,
      "guibannerenable":<Boolean_value>,
      "guisessiontimeout":<Integer_value>,
      "lockouttime":<Integer_value>,
      "maxuserfailures":<Integer_value>,
      "clibannerenable":<Boolean_value>,
      "clisessiontimeout":<Integer_value>}}
```

Response Payload: JSON

```json
{ "session_params":{
      "guibanner":<String_value>,
      "loginfailurelimit":<Integer_value>,
      "clibanner":<String_value>,
      "guibannerenable":<Boolean_value>,
      "guisessiontimeout":<Integer_value>,
      "lockouttime":<Integer_value>,
      "maxuserfailures":<Integer_value>,
      "clibannerenable":<Boolean_value>,
      "clisessiontimeout":<Integer_value>}}
```