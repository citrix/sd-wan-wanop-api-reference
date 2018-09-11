# tacacs_params

## Description

Configuration of TACACS server. This NITRO resource is applicable for CloudBridge SM83, SM85, SM88 and VPX platforms only.

## Read/write properties

`sharedsecretkey<String>`

TACACS server's shared secret key..

`serverport<Integer>`

TACACS server port.
Minimum value = 1
Maximum value = 65535

`status<Boolean>`

TACACS Enable/Disable status..
Possible values = [true,false]

`useencryption<Boolean>`

Use Encryption..
Possible values = [true,false]

`serverip<String>`

TACACS server IP address. (IPv4/IPv6 string).

## Read only properties

## Operations

NOTE: In request payload, Mandatory parameters are marked red and bold.

* [get](#get)
* [modify](#modify)

### <a name="get">Get</a>

**URL:** `http://<CBIP>/cb/nitro/v1/config/tacacs_params`

**HTTP Method:** GET

**Response Payload:** JSON

```json
{ "tacacs_params":{
      "sharedsecretkey":<String_value>,
      "serverport":<Integer_value>,
      "status":<Boolean_value>,
      "useencryption":<Boolean_value>,
      "serverip":<String_value>}}
```

### <a name="modify">Modify</a>

**URL:** `http://<CBIP>/cb/nitro/v1/config/tacacs_params`

**HTTP Method:** PUT

**Request Payload:** JSON

```json
{"tacacs_params":{
      "sharedsecretkey":<String_value>,
      "serverport":<Integer_value>,
      "status":<Boolean_value>,
      "useencryption":<Boolean_value>,
      "serverip":<String_value>}}
```

**Response Payload:** JSON

```json
{ "tacacs_params":{
      "sharedsecretkey":<String_value>,
      "serverport":<Integer_value>,
      "status":<Boolean_value>,
      "useencryption":<Boolean_value>,
      "serverip":<String_value>}}
```