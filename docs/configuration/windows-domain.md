# windows_domain

## Description

Join Leave or Get status of windows domain

## Read/write properties

`domainaction<String>`

Action based on progress of leave or join request: If Request is new the value of domainaction has to be configure but to poll the progress of previous request the value of domain action should be status.
Possible values = [configure,status]

`domainuserpassword<String>`

Password.
Minimum length = 1

`domainname<String>`

Domain Name of user.
Valid char set = ^[-.0-9a-zA-Z]+$

`leaveorjoin<String>`

leave domain or join domain.
Possible values = [Leave,Join]

`domainuser<String>`

Domain user name.
Valid char set = ^[-!#$%().^_~0-9a-zA-Z]+$

## Read only properties

`registeredstatus<String>`

Registered domain status.

`registeredstatuserrormsg<String>`

Registered domain status error msg if any error.

`registereddomain<String>`

registered windows domain.

## Operations

NOTE: In request payload, Mandatory parameters are marked red and bold.

* [get](#get)
* [modify](#modify)

### <a name="get">Get</a>

**URL:** `http://<CBIP>/cb/nitro/v1/config/windows_domain`

**HTTP Method:** GET

**Response Payload:** JSON

```json
{ "windows_domain":{
      "domainaction":<String_value>,
      "registeredstatus":<String_value>,
      "registeredstatuserrormsg":<String_value>,
      "domainuserpassword":<String_value>,
      "domainname":<String_value>,
      "leaveorjoin":<String_value>,
      "registereddomain":<String_value>,
      "domainuser":<String_value>}}
```

### <a name="modify">Modify</a>

**URL:** `http://<CBIP>/cb/nitro/v1/config/windows_domain`

**HTTP Method:** PUT

**Request Payload:** JSON

```json
{"windows_domain":{
      "domainuserpassword":<String_value>,
      "domainname":<String_value>,,
      "domainuser":<String_value>}}
```

**Response Payload:** JSON

```json
{ "windows_domain":{
      "domainaction":<String_value>,
      "registeredstatus":<String_value>,
      "registeredstatuserrormsg":<String_value>,
      "domainuserpassword":<String_value>,
      "domainname":<String_value>,
      "leaveorjoin":<String_value>,
      "registereddomain":<String_value>,
      "domainuser":<String_value>}}
```