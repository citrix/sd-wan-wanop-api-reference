# additional_features

## Description

Additional features for network and advance optimization

## Read/write properties

`featurestate <Boolean>`

Value of feature.

Possible values = [true,false]

`featurename <String>`

Name of feature. GroupMode and HighAvailability is supported on CB 3000, CB 2000, CB 1000, CB 400 and CB 300 platforms only. Enabling video caching will restart the service and reset the compressing history.

Possible values = [IPv6Acceleration,AppFlow,RPCOverHTTP,NativeMapi,ICAMultiStream,MAPICrossProtocolOptimization,SCPS,SecurePartner,SNMP,SSHAccess,SSLOptimization,Syslog,UserDataStoreEncryption,VideoCaching,CloudBridgePlugIn,WCCP,GroupMode,HighAvailability]

## Read only properties

`uiname <String>`

Display name of feature on GUI.

`message <String>`

Read only message depending upon feature state.

## Operations

**Note:** In request payload, Mandatory parameters are marked red and bold.

* [get(all)](#getall)
* [get](#get)
* [modify](#modify)

### <a name="getall">Get (all)</a>

URL: `http://<CBIP>/cb/nitro/v1/config/additional_features`

HTTP Method: GET

Response Payload: JSON

```json
{ "additional_features":[{
      "uiname":<String_value>,
      "featurestate":<Boolean_value>,
      "featurename":<String_value>,
      "message":<String_value>}, ...]}
```
### <a name="get">Get</a>

URL: `http://<CBIP>/cb/nitro/v1/config/additional_features/<featurename>`

HTTP Method: GET

Response Payload: JSON

```json
{ "additional_features":{
      "uiname":<String_value>,
      "featurestate":<Boolean_value>,
      "featurename":<String_value>,
      "message":<String_value>}}
```

### <a name="modify">Modify</a>

URL: `http://<CBIP>/cb/nitro/v1/config/additional_features/<featurename>`

HTTP Method: PUT

Request Payload: JSON

```json
{"additional_features":{
      "featurestate":<Boolean_value>,}}
```

Response Payload:JSON

```json
{ "additional_features":{
      "uiname":<String_value>,
      "featurestate":<Boolean_value>,
      "featurename":<String_value>,
      "message":<String_value>}}
```