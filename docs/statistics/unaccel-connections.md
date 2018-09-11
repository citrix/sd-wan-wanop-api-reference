# unaccel_connections

## Description

Unaccelerated Connections

## Read/write properties

## Read only properties

`initiator<String>`

IP address and port number of connection initiator.

`idletime<Double>`

Idle time for connection is seconds.

`passthroughreason<String>`

Reason for connection not being accelerated.

`responder<String>`

IP address and port number of responder.

`duration<Double>`

Duration of connection in seconds.

`bytestransferred<String>`

Total data transfered by this connection in KB.

`state<String>`

State of connection.

## Operations

NOTE: In request payload, Mandatory parameters are marked red and bold.

### Get

**URL:** `http://<CBIP>/cb/nitro/v1/stat/unaccel_connections`

**HTTP Method:** GET

**Response Payload:** JSON

```json
{ "unaccel_connections":{
      "initiator":<String_value>,
      "idletime":<Double_value>,
      "passthroughreason":<String_value>,
      "responder":<String_value>,
      "duration":<Double_value>,
      "bytestransferred":<String_value>,
      "state":<String_value>}}
```