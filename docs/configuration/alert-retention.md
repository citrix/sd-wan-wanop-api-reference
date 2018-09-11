# alert_retention

## Description

Alert retention time

## Read/write properties

`alertretentiontime <Integer>`

Alert retention time.

## Read only properties

## Operations

**Note:** In request payload, Mandatory parameters are marked red and bold.

* [get](#get)
* [modify](#modify)

### <a name="get">Get</a>

URL: `http://<CBIP>/cb/nitro/v1/config/alert_retention`

HTTP Method: GET

Response Payload: JSON

```json
{ "alert_retention":{
      "alertretentiontime":<Integer_value>}}
```

### <a name="modify">Modify</a>

URL: `http://<CBIP>/cb/nitro/v1/config/alert_retention`

HTTP Method: PUT

Request Payload: JSON

```json
{"alert_retention":{}}
```

Response Payload:JSON

```json
{ "alert_retention":{
      "alertretentiontime":<Integer_value>}}
```