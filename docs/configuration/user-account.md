# user_account

## Description

User Accounts

## Read/write properties

`externalauthentication<Boolean>`

Enable/Disable external authentication for the user. This parameter is applicable for CloudBridge 400, 800, 1000, 2000, 2000WS, 3000, 4000, and 5000 platforms only. On other platforms this parameter is ignored..
Possible values = [true,false]

`sessiontimeout<String>`

Session timeout for the user. This parameter is applicable for CloudBridge 400, 800, 1000, 2000, 2000WS, 3000, 4000, and 5000 platforms only. On other platforms this parameter is ignored..

`username<String>`

User Name.
Valid char set = ^[-_.@0-9a-zA-Z]+

`password<String>`

Password.
Minimum length = 1

`enablesessiontimeout<Boolean>`

Enable/Disable session timeout for the user. This parameter is applicable for CloudBridge 400, 800, 1000, 2000, 2000WS, 3000, 4000, and 5000 platforms only. On other platforms this parameter is ignored..
Possible values = [true,false]

`sessiontimeoutunit<String>`

Session timeout unit. This parameter is applicable for CloudBridge 400, 800, 1000, 2000, 2000WS, 3000, 4000, and 5000 platforms only. On other platforms this parameter is ignored..
Possible values = [Hours,Minutes]

`groups<[String,...]>`

Groups to which user belongs. Session timeout unit. This parameter is applicable for CloudBridge 400, 800, 1000, 2000, 2000WS, 3000, 4000, and 5000 platforms only. On other platforms this parameter is ignored..

`privilege<String>`

User privilege. This parameter is applicable for CloudBridge SM83, SM85, SM88 and VPX platforms only. On other platforms this parameter is ignored..
Possible values = [admin,viewer]

## Read only properties

## Operations

NOTE: In request payload, Mandatory parameters are marked red and bold.

* [add](#add)
* [delete](#delete)
* [get(all)](#getall)
* [get](#get)
* [modify](#modify)

### <a name="add">Add</a>

**URL:** `http://<CBIP>/cb/nitro/v1/config/user_account`

**HTTP Method:** POST

**Request Payload:** JSON

```json
{"user_account":{
      "externalauthentication":<Boolean_value>,
      "sessiontimeout":<String_value>,
      "username":<String_value>,
      "password":<String_value>,
      "enablesessiontimeout":<Boolean_value>,
      "sessiontimeoutunit":<String_value>,
      "groups":<String_value>,
      "privilege":<String_value>}}
```

**Response Payload:** JSON

```json
{ "user_account":{
      "externalauthentication":<Boolean_value>,
      "sessiontimeout":<String_value>,
      "username":<String_value>,
      "password":<String_value>,
      "enablesessiontimeout":<Boolean_value>,
      "sessiontimeoutunit":<String_value>,
      "groups":<String_value>,
      "privilege":<String_value>}}
```

### <a name="delete">Delete</a>

**URL:** `http://<CBIP>/cb/nitro/v1/config/user_account/<username>`

**HTTP Method:** DELETE

**Response Payload:** EMPTY

### <a name="getall">Get (all)</a>

**URL:** `http://<CBIP>/cb/nitro/v1/config/user_account`

**HTTP Method:** GET

**Response Payload:** JSON

```json
{ "user_account":[{
      "externalauthentication":<Boolean_value>,
      "sessiontimeout":<String_value>,
      "username":<String_value>,
      "password":<String_value>,
      "enablesessiontimeout":<Boolean_value>,
      "sessiontimeoutunit":<String_value>,
      "groups":<String_value>,
      "privilege":<String_value>}, ...]}
```

### <a name="get">Get</a>

**URL:** `http://<CBIP>/cb/nitro/v1/config/user_account/<username>`

**HTTP Method:** GET

**Response Payload:** JSON

```json
{ "user_account":{
      "externalauthentication":<Boolean_value>,
      "sessiontimeout":<String_value>,
      "username":<String_value>,
      "password":<String_value>,
      "enablesessiontimeout":<Boolean_value>,
      "sessiontimeoutunit":<String_value>,
      "groups":<String_value>,
      "privilege":<String_value>}}
```

### <a name="modify">Modify</a>

**URL:** `http://<CBIP>/cb/nitro/v1/config/user_account/<username>`

**HTTP Method:** PUT

**Request Payload:** JSON

```json
{"user_account":{
      "externalauthentication":<Boolean_value>,
      "sessiontimeout":<String_value>,,
      "password":<String_value>,
      "enablesessiontimeout":<Boolean_value>,
      "sessiontimeoutunit":<String_value>,
      "groups":<String_value>,
      "privilege":<String_value>}}
```

**Response Payload:** JSON

```json
{ "user_account":{
      "externalauthentication":<Boolean_value>,
      "sessiontimeout":<String_value>,
      "username":<String_value>,
      "password":<String_value>,
      "enablesessiontimeout":<Boolean_value>,
      "sessiontimeoutunit":<String_value>,
      "groups":<String_value>,
      "privilege":<String_value>}}
```