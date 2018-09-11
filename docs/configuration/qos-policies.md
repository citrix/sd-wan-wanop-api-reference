# qos_policies

## Description

Traffic shaping policies

## Read/write properties

`priority <Integer>`

Differential services priority.
Minimum value = 1
Maximum value = 256

`bandwidthlimittype <String>`

Bandwidth limit format, if percentage bandwidth limit in percentage, if Absolute bandwidht limit in bps. If limitbandwidth is false, bandwidhtlimittype will display Disabled as its value..
Possible values = [Percentage,Absolute]

`icapriorityenabled <Boolean>`

Enable/disable priority based on ICA channels.
Possible values = [true,false]

`maxbandwidthoutpercent <Integer>`

Maximum outgoing bandwidth for the QoS policy (in percent).
Minimum value = 0
Maximum value = 100

`enabled <Boolean>`

Enable/disable the link.
Possible values = [true,false]

`name <String>`

Name of the policy.
Minimum length = 1

`diffservenabled <Boolean>`

Control switch for policy differetial services..
Possible values = [true,false]

`maxbandwidthoutabsolute <Integer>`

Maximum outgoing bandwidth for the QoS policy (in bps).
Minimum value = 56000
Maximum value = 1000000000

`optimizeforvoice <Boolean>`

Enable/disable optimizing for voice..
Possible values = [true,false]

`diffserv <String>`

Differential services priority.
Valid char set = `^DSCP ([6][0-3]|[1-5][0-9]|[0]\?[1-9])`

`icadiffservices <{...}>`

Traffic Shaping DiffServ/TOS for different type of ICA Traffic.

`multistreaminteractive <String>`

ICA differential services multistream interactive traffic priority.
Valid char set = `^DSCP ([6][0-3]|[1-5][0-9]|[0]\?[1-9])`

`multistreamrealtime <String>`

ICA differential services multistream real-time traffic priority.
Valid char set = `^DSCP ([6][0-3]|[1-5][0-9]|[0]\?[1-9])`

`multistreambackground <String>`

ICA differential services multistream background traffic priority.
Valid char set = `^DSCP ([6][0-3]|[1-5][0-9]|[0]\?[1-9])`

`singlestreamallpriorities <String>`

ICA differential services single traffic priority.
Valid char set = `^DSCP ([6][0-3]|[1-5][0-9]|[0]\?[1-9])`

`multistreambulktransfer <String>`

ICA differential services multistream real-time traffic priority.
Valid char set = `^DSCP ([6][0-3]|[1-5][0-9]|[0]\?[1-9])`

`icapriorities <{...}>`

ICA priorities for different ICA Tag.

`interactive <Integer>`

ICA interactive traffic priority.
Minimum value = 1
Maximum value = 256

`background <Integer>`

ICA background traffic priority.
Minimum value = 1
Maximum value = 256

`bulktransfer <Integer>`

ICA bulk transfer traffic priority.
Minimum value = 1
Maximum value = 256

`realtime <Integer>`

ICA real-time traffic priority.
Minimum value = 1
Maximum value = 256

`maxbandwidthinabsolute <Integer>`

Maximum incoming bandwidth for the QoS policy (in bps).
Minimum value = 56000
Maximum value = 1000000000

`limitbandwidth <Boolean>`

Control switch for enabling/disabling bandwidth limiting..
Possible values = [true,false]

`icadiffservenabled <Boolean>`

Enable/disable priority based on ICA differential services.
Possible values = [true,false]

`maxbandwidthinpercent <Integer>`

Maximum incoming bandwidth for the QoS policy (in percent).
Minimum value = 0
Maximum value = 100

## Read only properties

`priorityenabled <Boolean>`

Control switch for enabling/disabling priorities..

`policyid <Integer>`

Policy ID unique for every policy and mapped with name.

`propertyflags <String>`

Flag to identify the property of link.

`modified <Boolean>`

Policy has been modified or not.

## Operations

**Note:** In request payload, Mandatory parameters are marked red and bold.

* [add](#add)
* [delete](#delete)
* [get(all)](#getall)
* [get](#get)
* [modify](#modify)

### <a name="add">Add</a>

URL: `http://<CBIP>/cb/nitro/v1/config/qos_policies`

HTTP Method: POST

Request Payload: JSON

```json
{"qos_policies":{
      "priority":<Integer_value>,
      "bandwidthlimittype":<String_value>,
      "icapriorityenabled":<Boolean_value>,
      "maxbandwidthoutpercent":<Integer_value>,
      "enabled":<Boolean_value>,
      "name":<String_value>,
      "diffservenabled":<Boolean_value>,
      "maxbandwidthoutabsolute":<Integer_value>,
      "optimizeforvoice":<Boolean_value>,
      "diffserv":<String_value>,
      "icadiffservices":{
            "multistreaminteractive":<String_value>,
            "multistreamrealtime":<String_value>,
            "multistreambackground":<String_value>,
            "singlestreamallpriorities":<String_value>,
            "multistreambulktransfer":<String_value>},
      "icapriorities":{
            "interactive":<Integer_value>,
            "background":<Integer_value>,
            "bulktransfer":<Integer_value>,
            "realtime":<Integer_value>},
      "maxbandwidthinabsolute":<Integer_value>,
      "limitbandwidth":<Boolean_value>,
      "icadiffservenabled":<Boolean_value>,
      "maxbandwidthinpercent":<Integer_value>}}
```

Response Payload: JSON

```json
{ "qos_policies":{
      "priority":<Integer_value>,
      "bandwidthlimittype":<String_value>,
      "icapriorityenabled":<Boolean_value>,
      "priorityenabled":<Boolean_value>,
      "policyid":<Integer_value>,
      "maxbandwidthoutpercent":<Integer_value>,
      "enabled":<Boolean_value>,
      "name":<String_value>,
      "diffservenabled":<Boolean_value>,
      "propertyflags":<String_value>,
      "modified":<Boolean_value>,
      "maxbandwidthoutabsolute":<Integer_value>,
      "optimizeforvoice":<Boolean_value>,
      "diffserv":<String_value>,
      "icadiffservices":{
            "multistreaminteractive":<String_value>,
            "multistreamrealtime":<String_value>,
            "multistreambackground":<String_value>,
            "singlestreamallpriorities":<String_value>,
            "multistreambulktransfer":<String_value>},
      "icapriorities":{
            "interactive":<Integer_value>,
            "background":<Integer_value>,
            "bulktransfer":<Integer_value>,
            "realtime":<Integer_value>},
      "maxbandwidthinabsolute":<Integer_value>,
      "limitbandwidth":<Boolean_value>,
      "icadiffservenabled":<Boolean_value>,
      "maxbandwidthinpercent":<Integer_value>}}
```

### <a name="delete">Delete</a>

URL: `http://<CBIP>/cb/nitro/v1/config/qos_policies/<name>`

HTTP Method: DELETE

Response Payload: EMPTY

### <a name="getall">Get (All)</a>

URL: `http://<CBIP>/cb/nitro/v1/config/qos_policies`

HTTP Method: GET

Response Payload: JSON

```json
{ "qos_policies":[{
      "priority":<Integer_value>,
      "bandwidthlimittype":<String_value>,
      "icapriorityenabled":<Boolean_value>,
      "priorityenabled":<Boolean_value>,
      "policyid":<Integer_value>,
      "maxbandwidthoutpercent":<Integer_value>,
      "enabled":<Boolean_value>,
      "name":<String_value>,
      "diffservenabled":<Boolean_value>,
      "propertyflags":<String_value>,
      "modified":<Boolean_value>,
      "maxbandwidthoutabsolute":<Integer_value>,
      "optimizeforvoice":<Boolean_value>,
      "diffserv":<String_value>,
      "icadiffservices":{
            "multistreaminteractive":<String_value>,
            "multistreamrealtime":<String_value>,
            "multistreambackground":<String_value>,
            "singlestreamallpriorities":<String_value>,
            "multistreambulktransfer":<String_value>},
      "icapriorities":{
            "interactive":<Integer_value>,
            "background":<Integer_value>,
            "bulktransfer":<Integer_value>,
            "realtime":<Integer_value>},
      "maxbandwidthinabsolute":<Integer_value>,
      "limitbandwidth":<Boolean_value>,
      "icadiffservenabled":<Boolean_value>,
      "maxbandwidthinpercent":<Integer_value>}, ...]}
```

### <a name="get">Get</a>

URL: `http://<CBIP>/cb/nitro/v1/config/qos_policies/<name>`

HTTP Method: GET

Response Payload: JSON

```json
{ "qos_policies":{
      "priority":<Integer_value>,
      "bandwidthlimittype":<String_value>,
      "icapriorityenabled":<Boolean_value>,
      "priorityenabled":<Boolean_value>,
      "policyid":<Integer_value>,
      "maxbandwidthoutpercent":<Integer_value>,
      "enabled":<Boolean_value>,
      "name":<String_value>,
      "diffservenabled":<Boolean_value>,
      "propertyflags":<String_value>,
      "modified":<Boolean_value>,
      "maxbandwidthoutabsolute":<Integer_value>,
      "optimizeforvoice":<Boolean_value>,
      "diffserv":<String_value>,
      "icadiffservices":{
            "multistreaminteractive":<String_value>,
            "multistreamrealtime":<String_value>,
            "multistreambackground":<String_value>,
            "singlestreamallpriorities":<String_value>,
            "multistreambulktransfer":<String_value>},
      "icapriorities":{
            "interactive":<Integer_value>,
            "background":<Integer_value>,
            "bulktransfer":<Integer_value>,
            "realtime":<Integer_value>},
      "maxbandwidthinabsolute":<Integer_value>,
      "limitbandwidth":<Boolean_value>,
      "icadiffservenabled":<Boolean_value>,
      "maxbandwidthinpercent":<Integer_value>}}
```

### <a name="modify">Modify</a>

URL: `http://<CBIP>/cb/nitro/v1/config/qos_policies/<name>`

HTTP Method: PUT

Request Payload: JSON

```json
{"qos_policies":{
      "priority":<Integer_value>,
      "bandwidthlimittype":<String_value>,
      "icapriorityenabled":<Boolean_value>,
      "maxbandwidthoutpercent":<Integer_value>,
      "enabled":<Boolean_value>,,
      "diffservenabled":<Boolean_value>,
      "maxbandwidthoutabsolute":<Integer_value>,
      "optimizeforvoice":<Boolean_value>,
      "diffserv":<String_value>,
      "icadiffservices":{
            "multistreaminteractive":<String_value>,
            "multistreamrealtime":<String_value>,
            "multistreambackground":<String_value>,
            "singlestreamallpriorities":<String_value>,
            "multistreambulktransfer":<String_value>},
      "icapriorities":{
            "interactive":<Integer_value>,
            "background":<Integer_value>,
            "bulktransfer":<Integer_value>,
            "realtime":<Integer_value>},
      "maxbandwidthinabsolute":<Integer_value>,
      "limitbandwidth":<Boolean_value>,
      "icadiffservenabled":<Boolean_value>,
      "maxbandwidthinpercent":<Integer_value>}}
```

Response Payload: JSON

```json
{ "qos_policies":{
      "priority":<Integer_value>,
      "bandwidthlimittype":<String_value>,
      "icapriorityenabled":<Boolean_value>,
      "priorityenabled":<Boolean_value>,
      "policyid":<Integer_value>,
      "maxbandwidthoutpercent":<Integer_value>,
      "enabled":<Boolean_value>,
      "name":<String_value>,
      "diffservenabled":<Boolean_value>,
      "propertyflags":<String_value>,
      "modified":<Boolean_value>,
      "maxbandwidthoutabsolute":<Integer_value>,
      "optimizeforvoice":<Boolean_value>,
      "diffserv":<String_value>,
      "icadiffservices":{
            "multistreaminteractive":<String_value>,
            "multistreamrealtime":<String_value>,
            "multistreambackground":<String_value>,
            "singlestreamallpriorities":<String_value>,
            "multistreambulktransfer":<String_value>},
      "icapriorities":{
            "interactive":<Integer_value>,
            "background":<Integer_value>,
            "bulktransfer":<Integer_value>,
            "realtime":<Integer_value>},
      "maxbandwidthinabsolute":<Integer_value>,
      "limitbandwidth":<Boolean_value>,
      "icadiffservenabled":<Boolean_value>,
      "maxbandwidthinpercent":<Integer_value>}}
```