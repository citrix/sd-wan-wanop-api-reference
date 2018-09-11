# snmp_trap_dest

## Read/write properties

`trapdestport<Integer>`

Trap Destination Port.
Minimum value = 1
Maximum value = 65535

`authprotocol<String>`

Authentication Protocol.
Possible values = [SHA1,MD5]

`username<String>`

User Name.
Valid char set = `^[-_.@0-9a-zA-Z]+`

`privacypassword<String>`

Privacy Password.
Minimum length = 8
Maximum length = 31
Valid char set = `^[-_.# =:@0-9a-zA-Z]+`

`traptype<String>`

Trap Type.
Possible values = [trap,inform]

`community<String>`

Trap Community.
Valid char set = `^[-_.@0-9a-zA-Z]+`

`privacyprotocol<String>`

Privacy Protocol.
Possible values = [AES,DES]

`authpassword<String>`

Authentication Password.
Minimum length = 8
Maximum length = 31
Valid char set = ^[-_.# =:@0-9a-zA-Z]+

`trapdestname<String>`

Trap Destination Name.
Valid char set = ^[-_.@0-9a-zA-Z]+

`snmpversion<String>`

Snmp Version.
Possible values = [v1,v2c,v3]

`trapdestip<String>`

Trap Destination Ip Address (IPv4/IPv6 string).

## Read only properties

### Operations

**NOTE**: In request payload, Mandatory parameters are marked red and bold.

* [add](#add)
* [delete](#delete)
* [get(all)](#getall)
* [get](#get)

### <a name="add">Add</a>

**URL:** `http://<CBIP>/cb/nitro/v1/config/snmp_trap_dest`

**HTTP Method:** POST

**Request Payload:** JSON

```json
{"snmp_trap_dest":{
      "trapdestport":<Integer_value>,
      "authprotocol":<String_value>,
      "username":<String_value>,
      "privacypassword":<String_value>,
      "traptype":<String_value>,
      "community":<String_value>,
      "privacyprotocol":<String_value>,
      "authpassword":<String_value>,
      "trapdestname":<String_value>,
      "snmpversion":<String_value>,
      "trapdestip":<String_value>}}
```

**Response Payload:** JSON

```json
{ "snmp_trap_dest":{
      "trapdestport":<Integer_value>,
      "authprotocol":<String_value>,
      "username":<String_value>,
      "privacypassword":<String_value>,
      "traptype":<String_value>,
      "community":<String_value>,
      "privacyprotocol":<String_value>,
      "authpassword":<String_value>,
      "trapdestname":<String_value>,
      "snmpversion":<String_value>,
      "trapdestip":<String_value>}}
```

### <a name="delete">Delete</a>

**URL:** `http://<CBIP>/cb/nitro/v1/config/snmp_trap_dest/<trapdestname>`

**HTTP Method:** DELETE

**Response Payload:** EMPTY

### <a name="getall">Get (all)</a>

**URL:** `http://<CBIP>/cb/nitro/v1/config/snmp_trap_dest`

**HTTP Method:** GET

**Response Payload:** JSON

{ "snmp_trap_dest":[{
      "trapdestport":<Integer_value>,
      "authprotocol":<String_value>,
      "username":<String_value>,
      "privacypassword":<String_value>,
      "traptype":<String_value>,
      "community":<String_value>,
      "privacyprotocol":<String_value>,
      "authpassword":<String_value>,
      "trapdestname":<String_value>,
      "snmpversion":<String_value>,
      "trapdestip":<String_value>}, ...]}

### <a name="get">Get</a>

**URL:** `http://<CBIP>/cb/nitro/v1/config/snmp_trap_dest/<trapdestname>`

**HTTP Method:** GET

**Response Payload**: JSON

```json
{ "snmp_trap_dest":{
      "trapdestport":<Integer_value>,
      "authprotocol":<String_value>,
      "username":<String_value>,
      "privacypassword":<String_value>,
      "traptype":<String_value>,
      "community":<String_value>,
      "privacyprotocol":<String_value>,
      "authpassword":<String_value>,
      "trapdestname":<String_value>,
      "snmpversion":<String_value>,
      "trapdestip":<String_value>}}
```