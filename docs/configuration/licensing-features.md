# licensing_features

## Description

Cloud Bridge Features of different licenses. This NITRO resource is applicable for CloudBridge SM83, SM85, SM88, VPX, 400, 800, 1000, 2000, 2000WS and 3000 platforms only.

## Read/write properties

Read only properties

`graceenddate <String>`

End date of grace license.

`name <String>`

Name of license.

`licensetype <String>`

Type of license.

`graceperiodexpired <Boolean>`

Grace period expiration flag.

`usagedate <String>`

License expiration date.

`upgradedate <String>`

Upgrate expiration date.

`details <String>`

Description of license.

`settings <String>`

Configurable settings of license.

## Operations

**Note:** In request payload, Mandatory parameters are marked red and bold.

* [get](#get)

### <a name="get">Get</a>

URL: `http://<CBIP>/cb/nitro/v1/config/licensing_features`

HTTP Method: GET

Response Payload: JSON

```json
{ "licensing_features":{
      "graceenddate":<String_value>,
      "name":<String_value>,
      "licensetype":<String_value>,
      "graceperiodexpired":<Boolean_value>,
      "usagedate":<String_value>,
      "upgradedate":<String_value>,
      "details":<String_value>,
      "settings":<String_value>}}
```