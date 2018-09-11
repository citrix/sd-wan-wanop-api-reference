# snmp\_user

## Description

SNMP Users

## Read/write properties

`privacypassword<String>`

Privacy Password.
Minimum length = 8
Maximum length = 31
Valid char set = `^[-_.# =:@0-9a-zA-Z]+`

`viewname<String>`

View.
Valid char set = `^[-_.@0-9a-zA-Z]+`

`privacyprotocol<String>`

Privacy Protocol.
Possible values = [AES,DES]

`authpassword<String>`

Authentication Password.
Minimum length = 8
Maximum length = 31
Valid char set = `^[-_.# =:@0-9a-zA-Z]+`

`authprotocol<String>`

Authentication Protocol.
Possible values = [SHA1,MD5]

`username<String>`

User Name.
Valid char set = `^[-_.@0-9a-zA-Z]+`

## Read only properties

## Operations

**NOTE**: In request payload, Mandatory parameters are marked red and bold.

* [add](#add)
* [delete](#delete)
* [get(all)](#getall)
* [get](#get)

### <a name="add">Add</a>

**URL**: `http://<CBIP>/cb/nitro/v1/config/snmp_user`

**HTTP Method**: POST

**Request Payload**: JSON

```json
{"snmp_user":{
      "privacypassword":<String_value>,
      "viewname":<String_value>,
      "privacyprotocol":<String_value>,
      "authpassword":<String_value>,
      "authprotocol":<String_value>,
      "username":<String_value>}}
```

**Response Payload**:JSON

```json
{ "snmp_user":{
      "privacypassword":<String_value>,
      "viewname":<String_value>,
      "privacyprotocol":<String_value>,
      "authpassword":<String_value>,
      "authprotocol":<String_value>,
      "username":<String_value>}}
```

### <a name="delete">Delete</a>

**URL**: `http://<CBIP>/cb/nitro/v1/config/snmp_user/<username>`

**HTTP Method**: DELETE

**Response Payload**: EMPTY

### <a name="getall">Get(all)</a>

**URL**: `http://<CBIP>/cb/nitro/v1/config/snmp_user`

**HTTP Method**: GET

**Response Payload**: JSON

```json
{ "snmp_user":[{
      "privacypassword":<String_value>,
      "viewname":<String_value>,
      "privacyprotocol":<String_value>,
      "authpassword":<String_value>,
      "authprotocol":<String_value>,
      "username":<String_value>}, ...]}
```

### <a name="get">Get</a>

**URL**:`http://<CBIP>/cb/nitro/v1/config/snmp_user/<username>`

**HTTP Method**: GET

**Response Payload**: JSON

```json
{ "snmp_user":{
      "privacypassword":<String_value>,
      "viewname":<String_value>,
      "privacyprotocol":<String_value>,
      "authpassword":<String_value>,
      "authprotocol":<String_value>,
      "username":<String_value>}}
```json