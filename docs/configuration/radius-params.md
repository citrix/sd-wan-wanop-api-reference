# radius_params

## Description

Configuration of RADIUS server. This NITRO resource is applicable for CloudBridge SM83, SM85, SM88 and VPX platforms only.

## Read/write properties

`sharedsecretkey <String>`

RADIUS server's shared secret key..

`serverport <Integer>`

RADIUS server port.
Minimum value = 1
Maximum value = 65535

`status <Boolean>`

Status of RADIUS server..
Possible values = [true,false]

`serverip <String>`

RADIUS server IP address. (IPv4/IPv6 string).

## Read only properties

## Operations

**Note:** In request payload, Mandatory parameters are marked red and bold.

* [get](#get) 
* [modify](#modify)

### <a name="get">Get</a>

URL: `http://<CBIP>/cb/nitro/v1/config/radius_params`

HTTP Method: GET

Response Payload: JSON

```json
{ "radius_params":{
      "sharedsecretkey":<String_value>,
      "serverport":<Integer_value>,
      "status":<Boolean_value>,
      "serverip":<String_value>}}
```

### <a name="modify">Modify</a>

URL: `http://<CBIP>/cb/nitro/v1/config/radius_params`

HTTP Method: PUT

Request Payload: JSON

```json
{"radius_params":{
      "sharedsecretkey":<String_value>,
      "serverport":<Integer_value>,
      "status":<Boolean_value>,
      "serverip":<String_value>}}
```

Response Payload: JSON

```json
{ "radius_params":{
      "sharedsecretkey":<String_value>,
      "serverport":<Integer_value>,
      "status":<Boolean_value>,
      "serverip":<String_value>}}
```