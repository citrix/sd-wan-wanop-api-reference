# system_info

## Description

System Information

## Read/write properties

`serial_number<String>`

Serial Number of CB system.

`hostname<String>`

Hostname of CB system.

`platform<String>`

Platform.

`swreleasedate<String>`

Software Release Date.

## Read only properties

## Operations

NOTE: In request payload, Mandatory parameters are marked red and bold.

### Get

**URL:** `http://<CBIP>/cb/nitro/v1/config/system_info`

**HTTP Method:** GET

**Response Payload:** JSON

```json
{ "system_info":{
      "serial_number":<String_value>,
      "hostname":<String_value>,
      "platform":<String_value>,
      "swreleasedate":<String_value>}}
```