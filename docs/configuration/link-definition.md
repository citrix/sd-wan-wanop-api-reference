# link_definition

## Description

Links configured and their property

## Read/write properties

`linktype <String>`

Type of link WAN or LAN.
Possible values = [LAN,WAN]

`name <String>`

Name of the link.
Minimum length = 1

`filterrules <[{...},...]>`

filter rules associated with link.

`vlans <[{...},...]>`

VLAN IDs for filter rules. Note: Not supported on CB 4000 and CB 5000 platform..

`vlanid <Integer>`

vlan id to be used for this rule.
Minimum value = 1
Maximum value = 4094

`excluded <Boolean>`

If true, use the rule component as an exclude entity.
Possible values = [true,false]

`srcethernetaddresses <[{...},...]>`

List of source ethernet addresses to be included or excludedin filter rules. Note: Not supported on CB 4000 and CB 5000 platform.

`excluded <Boolean>`

If true, use the rule component as an exclude entity.
Possible values = [true,false]

`srcetheraddress <String>`

`srcipaddresses <[{...},...]>`

list of source IPs to be included or excluded in filter rules.

`srcipaddress <{...}>`

srcipaddress to be used for this rule.

`left <String>`

Lower bound of IP address range (IPv4/IPv6 string).

`right <String>`

Upper bound of IP address range (IPv4/IPv6 string).

`ipaddress <String>`

IP address representation (IPv4/IPv6 string).

`ipaddressmask <String>`

IP adreess and mask representation (IPv4/IPv6 string).
Bitmask = Optional (format IP[/bitmask])

`rangetype <String>`

Use left/right fields for hyphen seperated IP range, ipaddressmask field for IP/mask, ipaddress field for IP address..
Possible values = [hyphen seperated,ipmask,ipaddress]

`excluded <Boolean>`

If true, use the rule component as an exclude entity.
Possible values = [true,false]

`dstethernetaddresses <[{...},...]>`

List of destination ethernet addresses to be included or excludedin filter rules. Note: Not supported on CB 4000 and CB 5000 platform.

`excluded <Boolean>`

If true, use the rule component as an exclude entity.
Possible values = [true,false]

`dstetheraddress <String>`

`interfaces <[{...},...]>`

List of interface(Adapter) names for link. Note: Not supported on CB 4000 and CB 5000 platform.

`interfacename <String>`

interface to be used for this rule.

`excluded <Boolean>`

If true, use the rule component as an exclude entity.
Possible values = [true,false]

`dstipaddresses <[{...},...]>`

List of destination IPs to be included or excluded in filter rules.

`excluded <Boolean>`

If true, use the rule component as an exclude entity.
Possible values = [true,false]

`dstipaddress <{...}>`

dstipaddress to be used for this rule.

`left <String>`

Lower bound of IP address range (IPv4/IPv6 string).

`right <String>`

Upper bound of IP address range (IPv4/IPv6 string).

`ipaddress <String>`

IP address representation (IPv4/IPv6 string).

`ipaddressmask <String>`

IP adreess and mask representation (IPv4/IPv6 string).
Bitmask = Optional (format IP[/bitmask])

`rangetype <String>`

Use left/right fields for hyphen seperated IP range, ipaddressmask field for IP/mask, ipaddress field for IP address..
Possible values = [hyphen seperated,ipmask,ipaddress]

`wccpservicegroups <[{...},...]>`

WCCP service group IDs. Note: Not supported on CB 4000 and CB 5000 platform..

`excluded <Boolean>`

If true, use the rule component as an exclude entity.
Possible values = [true,false]

`groupid <Integer>`

groupid to be used for this rule.
Minimum value = 51
Maximum value = 255

`enabled <Boolean>`

Filter rule enabled or disabled.
Possible values = [true,false]

`maxbandwidthout <Long>`

Maximum outgoing bandwidth for link in units of bps. Max value is 10 gbps for CB 4000 and CB 5000 but only 1 gbps for other platform. Note: Not supported on CB 4000 and CB 5000 platform if link type is LAN. This is a reequired key on all platrform but on CB 4000 and CB 5000 if link type is LAN then not required..
Minimum value = 56000
Maximum value = 10000000000

`maxbandwidthin <Long>`

Maximum incoming bandwidth for link in units of bps. Note: Not supported on CB 4000 and CB 5000 platform, but a required key for add operation on all other platform..
Minimum value = 56000
Maximum value = 1000000000

`order <Integer>`

Precedance order of link.
Minimum value = 1

`enabled <Boolean>`

Link enabled or not.
Possible values = [true,false]

Read only properties

`linkid <Integer>`

Link Id unique for every link and mapped with name.

`propertyflags <String>`

Flag to identify the property of link.

`modified <Boolean>`

Link has been modified or not.

## Operations

**Note:** In request payload, Mandatory parameters are marked red and bold.

* [add](#add)
* [delete](#delete)
* [get(all)](#getall)
* [get](#get)
* [modify](#modify)

### <a name="add">Add</a>

URL: `http://<CBIP>/cb/nitro/v1/config/link_definition`

HTTP Method: POST

Request Payload: JSON

```json
{"link_definition":{
      "linktype":<String_value>,
      "name":<String_value>,
      "filterrules":[{
            "vlans":[{
                  "vlanid":<Integer_value>,
                  "excluded":<Boolean_value>}, ...],
            "srcethernetaddresses":[{
                  "excluded":<Boolean_value>,
                  "srcetheraddress":<String_value>}, ...],
            "srcipaddresses":[{
                  "srcipaddress":{
                        "left":<String_value>,
                        "right":<String_value>,
                        "ipaddress":<String_value>,
                        "ipaddressmask":<String_value>,
                        "rangetype":<String_value>},
                  "excluded":<Boolean_value>}, ...],
            "dstethernetaddresses":[{
                  "excluded":<Boolean_value>,
                  "dstetheraddress":<String_value>}, ...],
            "interfaces":[{
                  "interfacename":<String_value>,
                  "excluded":<Boolean_value>}, ...],
            "dstipaddresses":[{
                  "excluded":<Boolean_value>,
                  "dstipaddress":{
                        "left":<String_value>,
                        "right":<String_value>,
                        "ipaddress":<String_value>,
                        "ipaddressmask":<String_value>,
                        "rangetype":<String_value>}}, ...],
            "wccpservicegroups":[{
                  "excluded":<Boolean_value>,
                  "groupid":<Integer_value>}, ...],
            "enabled":<Boolean_value>}, ...],
      "maxbandwidthout":<Long_value>,
      "maxbandwidthin":<Long_value>,
      "order":<Integer_value>,
      "enabled":<Boolean_value>}}
```

Response Payload: JSON

```json
{ "link_definition":{
      "linktype":<String_value>,
      "name":<String_value>,
      "filterrules":[{
            "vlans":[{
                  "vlanid":<Integer_value>,
                  "excluded":<Boolean_value>}, ...],
            "srcethernetaddresses":[{
                  "excluded":<Boolean_value>,
                  "srcetheraddress":<String_value>}, ...],
            "srcipaddresses":[{
                  "srcipaddress":{
                        "left":<String_value>,
                        "right":<String_value>,
                        "ipaddress":<String_value>,
                        "ipaddressmask":<String_value>,
                        "rangetype":<String_value>},
                  "excluded":<Boolean_value>}, ...],
            "dstethernetaddresses":[{
                  "excluded":<Boolean_value>,
                  "dstetheraddress":<String_value>}, ...],
            "interfaces":[{
                  "interfacename":<String_value>,
                  "excluded":<Boolean_value>}, ...],
            "dstipaddresses":[{
                  "excluded":<Boolean_value>,
                  "dstipaddress":{
                        "left":<String_value>,
                        "right":<String_value>,
                        "ipaddress":<String_value>,
                        "ipaddressmask":<String_value>,
                        "rangetype":<String_value>}}, ...],
            "wccpservicegroups":[{
                  "excluded":<Boolean_value>,
                  "groupid":<Integer_value>}, ...],
            "enabled":<Boolean_value>}, ...],
      "linkid":<Integer_value>,
      "propertyflags":<String_value>,
      "modified":<Boolean_value>,
      "maxbandwidthout":<Long_value>,
      "maxbandwidthin":<Long_value>,
      "order":<Integer_value>,
      "enabled":<Boolean_value>}}
```

### <a name="delete">Delete</a>


URL: `http://<CBIP>/cb/nitro/v1/config/link_definition/<name>`

HTTP Method: DELETE

Response Payload: EMPTY

### <a name="getall">Get (All)</a>

URL: `http://<CBIP>/cb/nitro/v1/config/link_definition`

HTTP Method: GET

Response Payload: JSON

```json
{ "link_definition":[{
      "linktype":<String_value>,
      "name":<String_value>,
      "filterrules":[{
            "vlans":[{
                  "vlanid":<Integer_value>,
                  "excluded":<Boolean_value>}, ...],
            "srcethernetaddresses":[{
                  "excluded":<Boolean_value>,
                  "srcetheraddress":<String_value>}, ...],
            "srcipaddresses":[{
                  "srcipaddress":{
                        "left":<String_value>,
                        "right":<String_value>,
                        "ipaddress":<String_value>,
                        "ipaddressmask":<String_value>,
                        "rangetype":<String_value>},
                  "excluded":<Boolean_value>}, ...],
            "dstethernetaddresses":[{
                  "excluded":<Boolean_value>,
                  "dstetheraddress":<String_value>}, ...],
            "interfaces":[{
                  "interfacename":<String_value>,
                  "excluded":<Boolean_value>}, ...],
            "dstipaddresses":[{
                  "excluded":<Boolean_value>,
                  "dstipaddress":{
                        "left":<String_value>,
                        "right":<String_value>,
                        "ipaddress":<String_value>,
                        "ipaddressmask":<String_value>,
                        "rangetype":<String_value>}}, ...],
            "wccpservicegroups":[{
                  "excluded":<Boolean_value>,
                  "groupid":<Integer_value>}, ...],
            "enabled":<Boolean_value>}, ...],
      "linkid":<Integer_value>,
      "propertyflags":<String_value>,
      "modified":<Boolean_value>,
      "maxbandwidthout":<Long_value>,
      "maxbandwidthin":<Long_value>,
      "order":<Integer_value>,
      "enabled":<Boolean_value>}, ...]}
```

### <a name="get">Get</a>

URL: `http://<CBIP>/cb/nitro/v1/config/link_definition/<name>`

HTTP Method: GET

Response Payload: JSON

```json
{ "link_definition":{
      "linktype":<String_value>,
      "name":<String_value>,
      "filterrules":[{
            "vlans":[{
                  "vlanid":<Integer_value>,
                  "excluded":<Boolean_value>}, ...],
            "srcethernetaddresses":[{
                  "excluded":<Boolean_value>,
                  "srcetheraddress":<String_value>}, ...],
            "srcipaddresses":[{
                  "srcipaddress":{
                        "left":<String_value>,
                        "right":<String_value>,
                        "ipaddress":<String_value>,
                        "ipaddressmask":<String_value>,
                        "rangetype":<String_value>},
                  "excluded":<Boolean_value>}, ...],
            "dstethernetaddresses":[{
                  "excluded":<Boolean_value>,
                  "dstetheraddress":<String_value>}, ...],
            "interfaces":[{
                  "interfacename":<String_value>,
                  "excluded":<Boolean_value>}, ...],
            "dstipaddresses":[{
                  "excluded":<Boolean_value>,
                  "dstipaddress":{
                        "left":<String_value>,
                        "right":<String_value>,
                        "ipaddress":<String_value>,
                        "ipaddressmask":<String_value>,
                        "rangetype":<String_value>}}, ...],
            "wccpservicegroups":[{
                  "excluded":<Boolean_value>,
                  "groupid":<Integer_value>}, ...],
            "enabled":<Boolean_value>}, ...],
      "linkid":<Integer_value>,
      "propertyflags":<String_value>,
      "modified":<Boolean_value>,
      "maxbandwidthout":<Long_value>,
      "maxbandwidthin":<Long_value>,
      "order":<Integer_value>,
      "enabled":<Boolean_value>}}
```

### <a name="modify">Modify</a>

URL: `http://<CBIP>/cb/nitro/v1/config/link_definition/<name>`

HTTP Method: PUT

Request Payload: JSON

```json
{"link_definition":{
      "linktype":<String_value>,,
      "filterrules":[{
            "vlans":[{
                  "vlanid":<Integer_value>,
                  "excluded":<Boolean_value>}, ...],
            "srcethernetaddresses":[{
                  "excluded":<Boolean_value>,
                  "srcetheraddress":<String_value>}, ...],
            "srcipaddresses":[{
                  "srcipaddress":{
                        "left":<String_value>,
                        "right":<String_value>,
                        "ipaddress":<String_value>,
                        "ipaddressmask":<String_value>,
                        "rangetype":<String_value>},
                  "excluded":<Boolean_value>}, ...],
            "dstethernetaddresses":[{
                  "excluded":<Boolean_value>,
                  "dstetheraddress":<String_value>}, ...],
            "interfaces":[{
                  "interfacename":<String_value>,
                  "excluded":<Boolean_value>}, ...],
            "dstipaddresses":[{
                  "excluded":<Boolean_value>,
                  "dstipaddress":{
                        "left":<String_value>,
                        "right":<String_value>,
                        "ipaddress":<String_value>,
                        "ipaddressmask":<String_value>,
                        "rangetype":<String_value>}}, ...],
            "wccpservicegroups":[{
                  "excluded":<Boolean_value>,
                  "groupid":<Integer_value>}, ...],
            "enabled":<Boolean_value>}, ...],
      "maxbandwidthout":<Long_value>,
      "maxbandwidthin":<Long_value>,
      "order":<Integer_value>,
      "enabled":<Boolean_value>}}
```
Response Payload: JSON

```json
{ "link_definition":{
      "linktype":<String_value>,
      "name":<String_value>,
      "filterrules":[{
            "vlans":[{
                  "vlanid":<Integer_value>,
                  "excluded":<Boolean_value>}, ...],
            "srcethernetaddresses":[{
                  "excluded":<Boolean_value>,
                  "srcetheraddress":<String_value>}, ...],
            "srcipaddresses":[{
                  "srcipaddress":{
                        "left":<String_value>,
                        "right":<String_value>,
                        "ipaddress":<String_value>,
                        "ipaddressmask":<String_value>,
                        "rangetype":<String_value>},
                  "excluded":<Boolean_value>}, ...],
            "dstethernetaddresses":[{
                  "excluded":<Boolean_value>,
                  "dstetheraddress":<String_value>}, ...],
            "interfaces":[{
                  "interfacename":<String_value>,
                  "excluded":<Boolean_value>}, ...],
            "dstipaddresses":[{
                  "excluded":<Boolean_value>,
                  "dstipaddress":{
                        "left":<String_value>,
                        "right":<String_value>,
                        "ipaddress":<String_value>,
                        "ipaddressmask":<String_value>,
                        "rangetype":<String_value>}}, ...],
            "wccpservicegroups":[{
                  "excluded":<Boolean_value>,
                  "groupid":<Integer_value>}, ...],
            "enabled":<Boolean_value>}, ...],
      "linkid":<Integer_value>,
      "propertyflags":<String_value>,
      "modified":<Boolean_value>,
      "maxbandwidthout":<Long_value>,
      "maxbandwidthin":<Long_value>,
      "order":<Integer_value>,
      "enabled":<Boolean_value>}}
```