# alert_options

## Description

Alert Options

## Read/write properties

`alertlevel <String>`

Alert level.

Possible values = [disable,log,alert]

`alertid <Integer>`

Alert ID

Minimum value = 0

`thresholdvalue <Integer>`

Alert threshold value

Minimum value = 0
Maximum value = 999

## Read only properties

`helptext <String>`

Help Text.

`minimumalertlevel <String>`

Minimum configurable alert level supported for the specific alert ID..

`description <String>`

Alert description.

`alertname <String>`

Alert Name.

`alertcondition <String>`

Condition on which the alert is generated..

## Operations

**Note:** In request payload, Mandatory parameters are marked red and bold.

* [reset](#reset)
* [get](#get)
* [modify](#modify)

### <a name="reset">Reset</a>

URL: `http://<CBIP>/cb/nitro/v1/config/alert_options?action=reset` 

HTTP Method: POST

Response Payload: JSON

```json
{ "errorcode": 0, "message": "Done", "severity": <String_value>}
```

### <a name="get">Get</a>

URL: `http://<CBIP>/cb/nitro/v1/config/alert_options`

HTTP Method: GET

Response Payload: JSON

```json
{ "alert_options":{
      "alertlevel":<String_value>,
      "helptext":<String_value>,
      "minimumalertlevel":<String_value>,
      "description":<String_value>,
      "alertname":<String_value>,
      "alertid":<Integer_value>,
      "alertcondition":<String_value>,
      "thresholdvalue":<Integer_value>}}
```

### <a name="modify">Modify</a>

URL: `http://<CBIP>/cb/nitro/v1/config/alert_options`

HTTP Method: PUT

Request Payload: JSON

```json
{"alert_options":{
      "alertlevel":<String_value>,,
      "thresholdvalue":<Integer_value>}}
```

Response Payload:JSON

```json
{ "alert_options":{
      "alertlevel":<String_value>,
      "helptext":<String_value>,
      "minimumalertlevel":<String_value>,
      "description":<String_value>,
      "alertname":<String_value>,
      "alertid":<Integer_value>,
      "alertcondition":<String_value>,
      "thresholdvalue":<Integer_value>}}
```