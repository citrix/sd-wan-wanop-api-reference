# delegate_users

## Description

Delegate Users and domain name

## Read/write properties

`delegateuserpassword <String>`

Password.
Minimum length = 7

`domainname <String>`

Domain Name of user.
Valid char set = ^[-.0-9a-zA-Z]+$

`delegateusername <String>`

Delegated user name.
Valid char set = ^[-!#$%().^_~0-9a-zA-Z]+$

## Read only properties

`userstatus <String>`

User status in domain.

## Operations

**Note:** In request payload, Mandatory parameters are marked red and bold.

* [add](#add)
* [delete](#delete)
* [get(all)](#getall)
* [get](#get)
* [modify](#modify)

### <a name="add">Add</a>

URL: `http://<CBIP>/cb/nitro/v1/config/delegate_users`

HTTP Method: POST

Request Payload: JSON

```json
{"delegate_users":{
      "delegateuserpassword":<String_value>,
      "domainname":<String_value>,
      "delegateusername":<String_value>}}
```

Response Payload:JSON

```json
{ "delegate_users":{
      "userstatus":<String_value>,
      "delegateuserpassword":<String_value>,
      "domainname":<String_value>,
      "delegateusername":<String_value>}}
```

### <a name="delete">Delete</a>

URL: `http://<CBIP>/cb/nitro/v1/config/delegate_users/domainname=<String>,delegateusername=<String>`

HTTP Method: DELETE

Response Payload: EMPTY

### <a name="getall">Get(All)</a>

URL: `http://<CBIP>/cb/nitro/v1/config/delegate_users`

HTTP Method: GET

Response Payload: JSON

```json
{ "delegate_users":[{
      "userstatus":<String_value>,
      "delegateuserpassword":<String_value>,
      "domainname":<String_value>,
      "delegateusername":<String_value>}, ...]}
```

### <a name="get">Get</a>

URL: `http://<CBIP>/cb/nitro/v1/config/delegate_users/domainname=<String>,delegateusername=<String>`

HTTP Method: GET

Response Payload: JSON

```json
{ "delegate_users":{
      "userstatus":<String_value>,
      "delegateuserpassword":<String_value>,
      "domainname":<String_value>,
      "delegateusername":<String_value>}}
```

### <a name="modify">Modify</a>

URL: `http://<CBIP>/cb/nitro/v1/config/delegate_users/<domainname>`

HTTP Method: PUT

Request Payload: JSON

```json
{"delegate_users":{
      "delegateuserpassword":<String_value>,,}}
```

Response Payload:JSON

```json
{ "delegate_users":{
      "userstatus":<String_value>,
      "delegateuserpassword":<String_value>,
      "domainname":<String_value>,
      "delegateusername":<String_value>}}
```