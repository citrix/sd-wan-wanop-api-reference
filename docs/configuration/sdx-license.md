# sdx_license

## Description

Configuration for License Information resource. This NITRO resource is applicable for CloudBridge 4000 and 5000 platforms only.

## Read/write properties

## Read only properties

`max_number_of_br_instances <Integer>`

Maximum CloudBridge Instances.

`cluster <Boolean>`

Cluster License.

`available_number_of_ns_instances <Integer>`

Available NetScaler Instances (Shared).

`max_throughput <String>`

Maximum Throughput in Mbps.

`max_number_of_ns_instances <Integer>`

Maximum NetScaler Instances.

`act_id <String>`

Activity Id.

`available_throughput <String>`

Available Throughput in Mbps.

`platform <String>`

Platform.

`max_number_of_instances <Integer>`

Maximum Instances.

`available_number_of_instances <Integer>`

Available Instances.

## Operations

**Note:** In request payload, Mandatory parameters are marked red and bold.

The following parameters can be used in the nitro request:

`onerror   <String_value>`

Use this parameter to set the onerror status for nitro request. Applicable only for bulk requests.
Default value: EXIT
Possible values = EXIT, CONTINUE

* [apply](#apply)
* [get](#get)

### <a name="apply">Apply</a>

URL: `http://<SDXIP>/nitro/v1/config/sdx_license`

HTTP Method: POST

Request Payload: JSON

```json
object={"params": {"action":"apply"
      "onerror":<String_value>
      },"sdx_license": { }}
```

Response Payload: JSON

```json
{ "errorcode": 0, "message": "Done", "severity": <String_value>}
```

### <a name="get">Get</a>

URL: `http://<SDXIP>/nitro/v1/config/sdx_license`

HTTP Method: GET

Response Payload: JSON

```json
{ "errorcode": 0, "message": "Done", "severity": <String_value>, "sdx_license":[{
      "max_number_of_br_instances":<Integer_value>,
      "cluster":<Boolean_value>,
      "available_number_of_ns_instances":<Integer_value>,
      "max_throughput":<String_value>,
      "max_number_of_ns_instances":<Integer_value>,
      "act_id":<String_value>,
      "sync_operation":<Boolean_value>,
      "available_throughput":<String_value>,
      "platform":<String_value>,
      "max_number_of_instances":<Integer_value>,
      "available_number_of_instances":<Integer_value>}]}
```