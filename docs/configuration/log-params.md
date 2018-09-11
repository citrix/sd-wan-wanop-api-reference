# log_params

## Description

Configuration of Logging parameters

## Read/write properties

`adapterrecords <Boolean>`

Log adapter records or not.
Possible values = [true,false]

`opencloserecords <Boolean>`

Log open/close records or not.
Possible values = [true,false]

`maxsize <Integer>`

Maximum log size on disk in megabytes.
Minimum value = 1
Maximum value = 1024

`flowrecords <Boolean>`

Log flow records or not.
Possible values = [true,false]

`maxexportcount <Integer>`

Maximum number of export count.
Minimum value = 1
Maximum value = 1048576

`textrecords <Boolean>`

Log text records or not.
Possible values = [true,false]

`connectionrecords <Boolean>`

Log connection records or not.
Possible values = [true,false]

`cifssmbrecords <Boolean>`

Log CIFS/SMB records or not.
Possible values = [true,false]

`alertrecords <Boolean>`

Log alert records or not.
Possible values = [true,false]

`systemrecords <Boolean>`

Log system records or not.
Possible values = [true,false]

## Read only properties

## Operations

**Note:** In request payload, Mandatory parameters are marked red and bold.

* [get](#get)
* [modify](#modify)

### <a name="get">Get</a>'

URL: `http://<CBIP>/cb/nitro/v1/config/log_params`

HTTP Method: GET

Response Payload: JSON

```json
{ "log_params":{
      "adapterrecords":<Boolean_value>,
      "opencloserecords":<Boolean_value>,
      "maxsize":<Integer_value>,
      "flowrecords":<Boolean_value>,
      "maxexportcount":<Integer_value>,
      "textrecords":<Boolean_value>,
      "connectionrecords":<Boolean_value>,
      "cifssmbrecords":<Boolean_value>,
      "alertrecords":<Boolean_value>,
      "systemrecords":<Boolean_value>}}
```

### <a name="modify">Modify</a>'

URL: `http://<CBIP>/cb/nitro/v1/config/log_params`

HTTP Method: PUT

Request Payload: JSON

```json
{"log_params":{
      "adapterrecords":<Boolean_value>,
      "opencloserecords":<Boolean_value>,
      "maxsize":<Integer_value>,
      "flowrecords":<Boolean_value>,
      "maxexportcount":<Integer_value>,
      "textrecords":<Boolean_value>,
      "connectionrecords":<Boolean_value>,
      "cifssmbrecords":<Boolean_value>,
      "alertrecords":<Boolean_value>,
      "systemrecords":<Boolean_value>}}
```
Response Payload: JSON

```json
{ "log_params":{
      "adapterrecords":<Boolean_value>,
      "opencloserecords":<Boolean_value>,
      "maxsize":<Integer_value>,
      "flowrecords":<Boolean_value>,
      "maxexportcount":<Integer_value>,
      "textrecords":<Boolean_value>,
      "connectionrecords":<Boolean_value>,
      "cifssmbrecords":<Boolean_value>,
      "alertrecords":<Boolean_value>,
      "systemrecords":<Boolean_value>}}
```