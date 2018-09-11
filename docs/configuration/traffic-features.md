# traffic_features

## Description

Features related to network traffic

## Read/write properties

`featurestate<Boolean>`

Value of feature.
Possible values = [true,false]

`featurename<String>`

Name of feature. Note: For CB 4000 and CB 5000 platform TrafficBridging is not supported..
Possible values = [TrafficAcceleration,TrafficProcessing,TrafficShaping,TrafficBridging]

## Read only properties

`uiname<String>`

Display name of feature on GUI.

`message<String>`

Read only message depending upon feature state.

## Operations

NOTE: In request payload, Mandatory parameters are marked red and bold.

* [get(all)](#getall)
* [get](#get)
* [modify](#modify)

### <a name="getall">Get (all)</a>

**URL:** `http://<CBIP>/cb/nitro/v1/config/traffic_features`

**HTTP Method:** GET

**Response Payload:** JSON

{ "traffic_features":[{
      "uiname":<String_value>,
      "featurestate":<Boolean_value>,
      "featurename":<String_value>,
      "message":<String_value>}, ...]}

### <a name="get">Get</a>

**URL:** `http://<CBIP>/cb/nitro/v1/config/traffic_features/<featurename>`

**HTTP Method:** GET

**Response Payload:** JSON

```json
{ "traffic_features":{
      "uiname":<String_value>,
      "featurestate":<Boolean_value>,
      "featurename":<String_value>,
      "message":<String_value>}}
```

### <a name="modify">Modify</a>

**URL:** `http://<CBIP>/cb/nitro/v1/config/traffic_features/<featurename>`

**HTTP Method:** PUT

**Request Payload:** JSON

```json
{"traffic_features":{
      "featurestate":<Boolean_value>,}}
```

**Response Payload:** JSON

```json
{ "traffic_features":{
      "uiname":<String_value>,
      "featurestate":<Boolean_value>,
      "featurename":<String_value>,
      "message":<String_value>}}
```