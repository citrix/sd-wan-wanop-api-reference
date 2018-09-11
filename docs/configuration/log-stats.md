# log_stats

## Description

Log Statistics

## Read/write properties

`lastdate <String>`

Date and time till which logs are available..

`firstnumber <Integer>`

First available log record number..

`lastnumber <Integer>`

Last available log record number..

`maxlogsize <Integer>`

Configured max log size in MB..

`firstdate <String>`

Start Date and time from which logs are available..

`currentlogsize <Integer>`

Current Log Size in MB.

## Read only properties

## Operations

**Note:** In request payload, Mandatory parameters are marked red and bold.

### Get

URL: `http://<CBIP>/cb/nitro/v1/config/log_stats`

HTTP Method: GET

Response Payload: JSON

```json
{ "log_stats":{
      "lastdate":<String_value>,
      "firstnumber":<Integer_value>,
      "lastnumber":<Integer_value>,
      "maxlogsize":<Integer_value>,
      "firstdate":<String_value>,
      "currentlogsize":<Integer_value>}}
```