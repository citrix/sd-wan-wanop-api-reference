# service_class

## Description

Configuration for service classes.

## Read/write properties

`qoslinkpolicies <[{...},...]>`

Per link QOS policy for the service class..

`qospolicyname <String>`

Use ipaddressmask paramter to define ip or ip/mask type range or use left/right parameters to define hyphen seperated range.

`linkname <String>`

Use ipaddressmask paramter to define ip or ip/mask type range or use left/right parameters to define hyphen seperated range.

`filterrules <[{...},...]>`

Filter rules defining the service class.

`sslprofiles <[String,...]>`

SSL profile attached with rule to enable SSL optomization.

`dstipaddresses <[{...},...]>`

Destination IP address range defining the rule.

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

`applications <[{...},...]>`

Applications defining the rule..

`appname <String>`

app to be used for this rule.

`excluded <Boolean>`

If true, use the rule component as an exclude entity.
Possible values = [true,false]

`sslenabled <Boolean>`

Used to enable SSL profiles attached to rule.
Possible values = [true,false]

`srcipaddresses <[{...},...]>`

Source IP address range defining the rule.

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

`vlans <[{...},...]>`

VLANs defining the rule. Note: VLANs in filter rules are not supported on CB 4000 and CB 5000 platform..

`vlanid <Integer>`

vlan id to be used for this rule.
Minimum value = 1
Maximum value = 4094

`excluded <Boolean>`

If true, use the rule component as an exclude entity.
Possible values = [true,false]

`diffservices <[{...},...]>`

Differntial service bits defining the rule.

`excluded <Boolean>`

If true, use the rule component as an exclude entity.
Possible values = [true,false]

`bitsvalue <String>`

bitsvalue of diff service to be used for this rule.
Valid char set = ^DSCP ([6][0-3]|[1-5][0-9]|[0]\?[1-9])

`directiontype <String>`

Direction of SYN for which the rule applies.
Possible values = [Uni-directional,Bi-directional]

`qospolicy <String>`

QoS policy applied for this service class. This field applies only when QOS policy applied not per link..

`classname <String>`

Service class name..

`accelerationpolicy <String>`

Acceleration policy for the service class..
Possible values = [flowcontrol,disk,memory,none]

`enabled <Boolean>`

Enable/Disable service class..
Possible values = [true,false]

## Read only properties

`classid <Integer>`

Unique Id generated for each service class..

`modified <Boolean>`

Flag to indicate user modified service classes..

`propertyflags <String>`

Defines operations allowed on the service class.

`index <Integer>`

Index of the service class in service class list..

`order <Integer>`

Precedence order of the service class. Higher the order, more the precedence.

## Operations

**Note:** In request payload, Mandatory parameters are marked red and bold.

* [add](#add)
* [delete](#delete)
* [get(all)](#getall)
* [get](#get)
* [modify](#modify)

### <a name="add">Add</a>

URL: `http://<CBIP>/cb/nitro/v1/config/service_class`

HTTP Method: POST

Request Payload: JSON

```json
{"service_class":{
      "qoslinkpolicies":[{
            "qospolicyname":<String_value>,
            "linkname":<String_value>}, ...],
      "filterrules":[{
            "sslprofiles":<String_value[]>,
            "dstipaddresses":[{
                  "excluded":<Boolean_value>,
                  "dstipaddress":{
                        "left":<String_value>,
                        "right":<String_value>,
                        "ipaddress":<String_value>,
                        "ipaddressmask":<String_value>,
                        "rangetype":<String_value>}}, ...],
            "applications":[{
                  "appname":<String_value>,
                  "excluded":<Boolean_value>}, ...],
            "sslenabled":<Boolean_value>,
            "srcipaddresses":[{
                  "srcipaddress":{
                        "left":<String_value>,
                        "right":<String_value>,
                        "ipaddress":<String_value>,
                        "ipaddressmask":<String_value>,
                        "rangetype":<String_value>},
                  "excluded":<Boolean_value>}, ...],
            "vlans":[{
                  "vlanid":<Integer_value>,
                  "excluded":<Boolean_value>}, ...],
            "diffservices":[{
                  "excluded":<Boolean_value>,
                  "bitsvalue":<String_value>}, ...],
            "directiontype":<String_value>}, ...],
      "qospolicy":<String_value>,
      "classname":<String_value>,
      "accelerationpolicy":<String_value>,
      "enabled":<Boolean_value>}}
```

Response Payload: JSON

```json
{ "service_class":{
      "qoslinkpolicies":[{
            "qospolicyname":<String_value>,
            "linkname":<String_value>}, ...],
      "classid":<Integer_value>,
      "filterrules":[{
            "sslprofiles":<String_value>,
            "dstipaddresses":[{
                  "excluded":<Boolean_value>,
                  "dstipaddress":{
                        "left":<String_value>,
                        "right":<String_value>,
                        "ipaddress":<String_value>,
                        "ipaddressmask":<String_value>,
                        "rangetype":<String_value>}}, ...],
            "applications":[{
                  "appname":<String_value>,
                  "excluded":<Boolean_value>}, ...],
            "sslenabled":<Boolean_value>,
            "srcipaddresses":[{
                  "srcipaddress":{
                        "left":<String_value>,
                        "right":<String_value>,
                        "ipaddress":<String_value>,
                        "ipaddressmask":<String_value>,
                        "rangetype":<String_value>},
                  "excluded":<Boolean_value>}, ...],
            "vlans":[{
                  "vlanid":<Integer_value>,
                  "excluded":<Boolean_value>}, ...],
            "diffservices":[{
                  "excluded":<Boolean_value>,
                  "bitsvalue":<String_value>}, ...],
            "directiontype":<String_value>}, ...],
      "qospolicy":<String_value>,
      "modified":<Boolean_value>,
      "classname":<String_value>,
      "propertyflags":<String_value>,
      "index":<Integer_value>,
      "accelerationpolicy":<String_value>,
      "order":<Integer_value>,
      "enabled":<Boolean_value>}}
```

### <a name="delete">Delete</a>

URL: `http://<CBIP>/cb/nitro/v1/config/service_class/<classname>`

HTTP Method: DELETE

Response Payload: EMPTY

### <a name="getall">Get (All)</a>

URL: `http://<CBIP>/cb/nitro/v1/config/service_class`

HTTP Method: GET

Response Payload: JSON

```json
{ "service_class":[{
      "qoslinkpolicies":[{
            "qospolicyname":<String_value>,
            "linkname":<String_value>}, ...],
      "classid":<Integer_value>,
      "filterrules":[{
            "sslprofiles":<String_value>,
            "dstipaddresses":[{
                  "excluded":<Boolean_value>,
                  "dstipaddress":{
                        "left":<String_value>,
                        "right":<String_value>,
                        "ipaddress":<String_value>,
                        "ipaddressmask":<String_value>,
                        "rangetype":<String_value>}}, ...],
            "applications":[{
                  "appname":<String_value>,
                  "excluded":<Boolean_value>}, ...],
            "sslenabled":<Boolean_value>,
            "srcipaddresses":[{
                  "srcipaddress":{
                        "left":<String_value>,
                        "right":<String_value>,
                        "ipaddress":<String_value>,
                        "ipaddressmask":<String_value>,
                        "rangetype":<String_value>},
                  "excluded":<Boolean_value>}, ...],
            "vlans":[{
                  "vlanid":<Integer_value>,
                  "excluded":<Boolean_value>}, ...],
            "diffservices":[{
                  "excluded":<Boolean_value>,
                  "bitsvalue":<String_value>}, ...],
            "directiontype":<String_value>}, ...],
      "qospolicy":<String_value>,
      "modified":<Boolean_value>,
      "classname":<String_value>,
      "propertyflags":<String_value>,
      "index":<Integer_value>,
      "accelerationpolicy":<String_value>,
      "order":<Integer_value>,
      "enabled":<Boolean_value>}, ...]}
```

### <a name="get">Get</a>

URL: `http://<CBIP>/cb/nitro/v1/config/service_class/<classname>`

HTTP Method: GET

Response Payload: JSON

```json
{ "service_class":{
      "qoslinkpolicies":[{
            "qospolicyname":<String_value>,
            "linkname":<String_value>}, ...],
      "classid":<Integer_value>,
      "filterrules":[{
            "sslprofiles":<String_value>,
            "dstipaddresses":[{
                  "excluded":<Boolean_value>,
                  "dstipaddress":{
                        "left":<String_value>,
                        "right":<String_value>,
                        "ipaddress":<String_value>,
                        "ipaddressmask":<String_value>,
                        "rangetype":<String_value>}}, ...],
            "applications":[{
                  "appname":<String_value>,
                  "excluded":<Boolean_value>}, ...],
            "sslenabled":<Boolean_value>,
            "srcipaddresses":[{
                  "srcipaddress":{
                        "left":<String_value>,
                        "right":<String_value>,
                        "ipaddress":<String_value>,
                        "ipaddressmask":<String_value>,
                        "rangetype":<String_value>},
                  "excluded":<Boolean_value>}, ...],
            "vlans":[{
                  "vlanid":<Integer_value>,
                  "excluded":<Boolean_value>}, ...],
            "diffservices":[{
                  "excluded":<Boolean_value>,
                  "bitsvalue":<String_value>}, ...],
            "directiontype":<String_value>}, ...],
      "qospolicy":<String_value>,
      "modified":<Boolean_value>,
      "classname":<String_value>,
      "propertyflags":<String_value>,
      "index":<Integer_value>,
      "accelerationpolicy":<String_value>,
      "order":<Integer_value>,
      "enabled":<Boolean_value>}}
```

### <a name="modify">Modify</a>

URL: `http://<CBIP>/cb/nitro/v1/config/service_class/<classname>`

HTTP Method: PUT

Request Payload: JSON

```json
{"service_class":{
      "qoslinkpolicies":[{
            "qospolicyname":<String_value>,
            "linkname":<String_value>}, ...],
      "filterrules":[{
            "sslprofiles":<String_value[]>,
            "dstipaddresses":[{
                  "excluded":<Boolean_value>,
                  "dstipaddress":{
                        "left":<String_value>,
                        "right":<String_value>,
                        "ipaddress":<String_value>,
                        "ipaddressmask":<String_value>,
                        "rangetype":<String_value>}}, ...],
            "applications":[{
                  "appname":<String_value>,
                  "excluded":<Boolean_value>}, ...],
            "sslenabled":<Boolean_value>,
            "srcipaddresses":[{
                  "srcipaddress":{
                        "left":<String_value>,
                        "right":<String_value>,
                        "ipaddress":<String_value>,
                        "ipaddressmask":<String_value>,
                        "rangetype":<String_value>},
                  "excluded":<Boolean_value>}, ...],
            "vlans":[{
                  "vlanid":<Integer_value>,
                  "excluded":<Boolean_value>}, ...],
            "diffservices":[{
                  "excluded":<Boolean_value>,
                  "bitsvalue":<String_value>}, ...],
            "directiontype":<String_value>}, ...],
      "qospolicy":<String_value>,,
      "accelerationpolicy":<String_value>,
      "enabled":<Boolean_value>}}
```

Response Payload: JSON

```json
{ "service_class":{
      "qoslinkpolicies":[{
            "qospolicyname":<String_value>,
            "linkname":<String_value>}, ...],
      "classid":<Integer_value>,
      "filterrules":[{
            "sslprofiles":<String_value>,
            "dstipaddresses":[{
                  "excluded":<Boolean_value>,
                  "dstipaddress":{
                        "left":<String_value>,
                        "right":<String_value>,
                        "ipaddress":<String_value>,
                        "ipaddressmask":<String_value>,
                        "rangetype":<String_value>}}, ...],
            "applications":[{
                  "appname":<String_value>,
                  "excluded":<Boolean_value>}, ...],
            "sslenabled":<Boolean_value>,
            "srcipaddresses":[{
                  "srcipaddress":{
                        "left":<String_value>,
                        "right":<String_value>,
                        "ipaddress":<String_value>,
                        "ipaddressmask":<String_value>,
                        "rangetype":<String_value>},
                  "excluded":<Boolean_value>}, ...],
            "vlans":[{
                  "vlanid":<Integer_value>,
                  "excluded":<Boolean_value>}, ...],
            "diffservices":[{
                  "excluded":<Boolean_value>,
                  "bitsvalue":<String_value>}, ...],
            "directiontype":<String_value>}, ...],
      "qospolicy":<String_value>,
      "modified":<Boolean_value>,
      "classname":<String_value>,
      "propertyflags":<String_value>,
      "index":<Integer_value>,
      "accelerationpolicy":<String_value>,
      "order":<Integer_value>,
      "enabled":<Boolean_value>}}
```