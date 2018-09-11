# http_params

## Description

HTTP Configuration.

## Read/write properties

`sslprivatekey <String>`

SSL Private Key

Valid char set `= ^(-{1,}BEGIN \\w* PRIVATE KEY-{1,}).+(-{1,}END \\w* PRIVATE KEY-{1,}\r{0,1}\n{0,1})$`

`httpport <Integer>`

HTTP port.
Minimum value = 1
Maximum value = 65535

`httpforwarding <Boolean>`

Enable/disable HTTP forwarding.
Possible values = [true,false]

`sslcertificate <String>`

SSL Certificate.

Valid char set `= ^(-{1,}BEGIN CERTIFICATE-{1,}).+(-{1,}END CERTIFICATE-{1,}\r{0,1}\n{0,1})$`

`httpsport <Integer>`

HTTPS port.
Minimum value = 1
Maximum value = 65535

`status <Boolean>`

HTTP Enable/Disable status..
Possible values = [true,false]

`webaccessprotocol <String>`

Web Access Protocol. Possible values HTTP, HTTPS..
Possible values = [https,http]

## Read only properties

##Operations

**Note:** In request payload, Mandatory parameters are marked red and bold.

* [get](#get)
* [modify](#modify)

### <a name="get">Get</a>

URL: `http://<CBIP>/cb/nitro/v1/config/http_params`

HTTP Method: GET

Response Payload: JSON

```json
{ "http_params":{
      "sslprivatekey":<String_value>,
      "httpport":<Integer_value>,
      "httpforwarding":<Boolean_value>,
      "sslcertificate":<String_value>,
      "httpsport":<Integer_value>,
      "status":<Boolean_value>,
      "webaccessprotocol":<String_value>}}
```

### <a name="modify">Modify</a>

URL: `http://<CBIP>/cb/nitro/v1/config/http_params`

HTTP Method: PUT

Request Payload: JSON

```json
{"http_params":{
      "sslprivatekey":<String_value>,
      "httpport":<Integer_value>,
      "httpforwarding":<Boolean_value>,
      "sslcertificate":<String_value>,
      "httpsport":<Integer_value>,
      "status":<Boolean_value>,
      "webaccessprotocol":<String_value>}}
```

Response Payload: JSON

```json
{ "http_params":{
      "sslprivatekey":<String_value>,
      "httpport":<Integer_value>,
      "httpforwarding":<Boolean_value>,
      "sslcertificate":<String_value>,
      "httpsport":<Integer_value>,
      "status":<Boolean_value>,
      "webaccessprotocol":<String_value>}}
```