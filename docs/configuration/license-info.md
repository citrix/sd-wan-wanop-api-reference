# license_info

## Description

License Information. This NITRO resource is applicable for CloudBridge SM83, SM85, SM88, VPX, 400, 800, 1000, 2000, 2000WS and 3000 platforms only.

## Read/write properties

`serverport <Integer>`

License server port number. This value should be present when the server location is remote..
Minimum value = 1
Maximum value = 65535

`requestcryptolicense <Boolean>`

Request crypto license.
Possible values = [true,false]

`serverlocation <String>`

Server Location.
Possible values = [remote,local]

`serveraddress <String>`

License server IP address. This value should be present when the server location is remote. (IPv4/IPv6 string).

`basemodel <String>`

Base Model.
Possible values = [100,200,300,5M,10M,20M,45M,100M,8510,8520,8530,8540,8310,8320,8810,8820,V1,V2,V10,V20,V45,V50,VEXP,V100,V200,V13500,2000-010,2000-020,2000-050,3000-050,3000-100,3000-155,400-002,400-006,800-002,800-006,800-010,1000-006,1000-010,1000-020]

`productname <String>`

Product Name.
Possible values = [CBR,CWSDE,CWS,CCB]

## Read only properties

`serverstatus <String>`

Server Status.

`hostid <String>`

Host ID.

`islicensed <Boolean>`

Is licensed or not.

`basemodelstatus <String>`

Base Model Status.

## Operations

**Note:** In request payload, Mandatory parameters are marked red and bold.

* [get](#get)
* [modify](#modify)

### <a name="get">Get</a>

URL: `http://<CBIP>/cb/nitro/v1/config/license_info`

HTTP Method: GET

Response Payload: JSON

```json
{ "license_info":{
      "serverport":<Integer_value>,
      "serverstatus":<String_value>,
      "requestcryptolicense":<Boolean_value>,
      "hostid":<String_value>,
      "serverlocation":<String_value>,
      "islicensed":<Boolean_value>,
      "basemodelstatus":<String_value>,
      "serveraddress":<String_value>,
      "basemodel":<String_value>,
      "productname":<String_value>}}
```

### <a name="modify">Modify</a>

URL: `http://<CBIP>/cb/nitro/v1/config/license_info`

HTTP Method: PUT

Request Payload: JSON

```json
{"license_info":{
      "serverport":<Integer_value>,
      "requestcryptolicense":<Boolean_value>,,
      "serveraddress":<String_value>,
      "basemodel":<String_value>,
      "productname":<String_value>}}
```

Response Payload: JSON

```json
{ "license_info":{
      "serverport":<Integer_value>,
      "serverstatus":<String_value>,
      "requestcryptolicense":<Boolean_value>,
      "hostid":<String_value>,
      "serverlocation":<String_value>,
      "islicensed":<Boolean_value>,
      "basemodelstatus":<String_value>,
      "serveraddress":<String_value>,
      "basemodel":<String_value>,
      "productname":<String_value>}}
```