# cifs_features

# Description

CIFS Protocol Optimization enabled or disabled

## Read/write properties

`featurestate <String>`

Value of feature.
Possible values = [All,SMB1Only,SMB2Only,Disabled]

`featurename <String>`

Name of feature.
Possible values = [CIFSProtocolOptimization]

## Read only properties

`uiname <String>`

Display name of feature on GUI.

`message <String>`

Read only message depending upon feature state.

## Operations

**Note:** In request payload, Mandatory parameters are marked red and bold.

* [get](#get)
* [modify](#modify)

### <a name="get">Get</a>

URL: `http://<CBIP>/cb/nitro/v1/config/cifs_features`

HTTP Method: GET

Response Payload: JSON

```json
{ "cifs_features":{
      "uiname":<String_value>,
      "featurestate":<String_value>,
      "featurename":<String_value>,
      "message":<String_value>}}
```

### <a name="modify">Modify</a>

URL: `http://<CBIP>/cb/nitro/v1/config/cifs_features`

HTTP Method: PUT

Request Payload: JSON

```json
{"cifs_features":{
      "featurestate":<String_value>,
      "featurename":<String_value>}}
```

Response Payload:JSON

```json
{ "cifs_features":{
      "uiname":<String_value>,
      "featurestate":<String_value>,
      "featurename":<String_value>,
      "message":<String_value>}}
```