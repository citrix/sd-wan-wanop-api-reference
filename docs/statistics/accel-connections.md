# accel_connections

## Description

Accelerated Connections

## Read/write properties

## Read only properties

`compressionalgorithm<String>`

Compression algorithm either Memory based compression, Disk based compression or None.

`duration<Integer>`

Duration of connection in seconds.

`compressionratio<Double>`

Compression Ratio.

`iscompressed<Boolean>`

Compression is enabled or disabled.

`state<String>`

State of connection.

`serviceclass<String>`

Service Class under which connection is established.

`partnerunit<String>`

IP address of partner unit.

`initiator<String>`

IP address and port number of connection initiator.

`idletime<Integer>`

Idle time for connection is seconds.

`issslproxy<Boolean>`

SSL proxy enabled or disabled.

`responder<String>`

IP address and port number of responder.

`bytestransferred<String>`

Total data transfered by this connection in bytes.

## Operations

NOTE: In request payload, Mandatory parameters are marked red and bold.

### Get

**URL:** `http://<CBIP>/cb/nitro/v1/stat/accel_connections`

**HTTP Method:** GET

**Response Payload:** JSON

```json
{ "accel_connections":{
      "compressionalgorithm":<String_value>,
      "duration":<Integer_value>,
      "compressionratio":<Double_value>,
      "iscompressed":<Boolean_value>,
      "state":<String_value>,
      "serviceclass":<String_value>,
      "partnerunit":<String_value>,
      "initiator":<String_value>,
      "idletime":<Integer_value>,
      "issslproxy":<Boolean_value>,
      "responder":<String_value>,
      "bytestransferred":<String_value>}}
```