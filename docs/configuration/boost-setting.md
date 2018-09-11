# boost_setting

## Description

Configure boosting as Hardboost or Softboost as well as WAN bandwidth receive limit

## Read/write properties

`boostmode <String>`

Boost mode Hardboost or Softboost.

Possible values = [Softboost,Hardboost]

`bandwidhtreceivelimit <Integer>`

Bandwidth receive limit in Kbps.
Minimum value = 128
Maximum value = 1000000

## Read only properties

## Operations

**Note:** In request payload, Mandatory parameters are marked red and bold.

* [get](#get)
* [modify](#modify)

### <a name="get">Get</a>

URL: `http://<CBIP>/cb/nitro/v1/config/boost_setting`

HTTP Method: GET

Response Payload: JSON

```json
{ "boost_setting":{
      "boostmode":<String_value>,
      "bandwidhtreceivelimit":<Integer_value>}}
```

### <a name="modify">Modify</a>

URL: `http://<CBIP>/cb/nitro/v1/config/boost_setting`

HTTP Method: PUT

Request Payload: JSON

```json
{"boost_setting":{
      "boostmode":<String_value>,
      "bandwidhtreceivelimit":<Integer_value>}}
```
Response Payload:JSON

```json
{ "boost_setting":{
      "boostmode":<String_value>,
      "bandwidhtreceivelimit":<Integer_value>}}
```