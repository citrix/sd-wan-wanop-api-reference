# callhome

## Description

Call Home

## Read/write properties

`enable <Boolean>`

Enable/Disable Call Home Feature.

Possible values = [true,false]

`proxyip <String>`

Proxy IP for CallHome Server (IPv4/IPv6 string).

`contact <String>`

Contact.

`proxyport <Integer>`

Proxy PORT for CallHome Server.
Minimum value = 1
Maximum value = 65535

`proxy <Boolean>`

Proxy Set for CallHome Server.
Possible values = [true,false]

## Read only properties

## Operations

**Note:** In request payload, Mandatory parameters are marked red and bold.

* [get](#get)
* [modify](#modify)

### <a name="get">Get</a>

URL: `http://<CBIP>/cb/nitro/v1/config/callhome`

HTTP Method: GET

Response Payload: JSON

```json
{ "callhome":{
      "enable":<Boolean_value>,
      "proxyip":<String_value>,
      "contact":<String_value>,
      "proxyport":<Integer_value>,
      "proxy":<Boolean_value>}}
```

### <a name="modify">Modify</a>

URL: `http://<CBIP>/cb/nitro/v1/config/callhome`

HTTP Method: PUT

Request Payload: JSON

```json
{"callhome":{
      "enable":<Boolean_value>,
      "proxyip":<String_value>,
      "contact":<String_value>,
      "proxyport":<Integer_value>,
      "proxy":<Boolean_value>}}
```

Response Payload:JSON

```json
{ "callhome":{
      "enable":<Boolean_value>,
      "proxyip":<String_value>,
      "contact":<String_value>,
      "proxyport":<Integer_value>,
      "proxy":<Boolean_value>}}
```