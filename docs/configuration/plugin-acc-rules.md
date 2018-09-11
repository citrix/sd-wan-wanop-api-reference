# plugin_acc_rules

## Description

Configuration of plugin acceleration rules.

## Read/write properties

`destsubnet <String>`

IP subnet for which the rule is defined (IPv4/IPv6 string).
Bitmask = Optional (format IP[/bitmask])

`order <Integer>`

Order specifies the priority in which the rules are applied. Lower the order, higher the priority. If order is not provided in ADD or the order is bigger than order of the lowest rule, order is automatically truncated to be that of one more than the existing maximum..
Minimum value = 1

`portrange <String>`

Comma seprated port ranges for which the rule is defined.Eg. 3000,4000-5000,6000. For all ports use: all/All.

`ruletype <String>`

Rule type to define if the rule is used to enable acceleration or exclude traffic.
Possible values = [accelerate,exclude]

## Read only properties

## Operations

**Note:** In request payload, Mandatory parameters are marked red and bold.

* [add](#add)
* [delete](#delete)
* [get(all)](#getall)
* [get](#get)
* [modify](#modify)

### <a name="add">Add</a>

URL: `http://<CBIP>/cb/nitro/v1/config/plugin_acc_rules`

HTTP Method: POST

Request Payload: JSON

```json
{"plugin_acc_rules":{
      "destsubnet":<String_value>,
      "order":<Integer_value>,
      "portrange":<String_value>,
      "ruletype":<String_value>}}
```

Response Payload: JSON

```json
{ "plugin_acc_rules":{
      "destsubnet":<String_value>,
      "order":<Integer_value>,
      "portrange":<String_value>,
      "ruletype":<String_value>}}
```

### <a name="delete">Delete</a>

URL: `http://<CBIP>/cb/nitro/v1/config/plugin_acc_rules/destsubnet=<String>,ruletype=<String>`

HTTP Method: DELETE

Response Payload: EMPTY

### <a name="getall">Get (All)</a>

URL: `http://<CBIP>/cb/nitro/v1/config/plugin_acc_rules`

HTTP Method: GET

Response Payload: JSON

```json
{ "plugin_acc_rules":[{
      "destsubnet":<String_value>,
      "order":<Integer_value>,
      "portrange":<String_value>,
      "ruletype":<String_value>}, ...]}
```

### <a name="get">Get</a>

URL: `http://<CBIP>/cb/nitro/v1/config/plugin_acc_rules/destsubnet=<String>,ruletype=<String>`

HTTP Method: GET

Response Payload: JSON

```json
{ "plugin_acc_rules":{
      "destsubnet":<String_value>,
      "order":<Integer_value>,
      "portrange":<String_value>,
      "ruletype":<String_value>}}
```

### <a name="modify">Modify</a>

URL: `http://<CBIP>/cb/nitro/v1/config/plugin_acc_rules/<destsubnet>`

HTTP Method: PUT

Request Payload: JSON

```json
{"plugin_acc_rules":{
      "order":<Integer_value>,
      "portrange":<String_value>,}}
```

Response Payload: JSON

```json
{ "plugin_acc_rules":{
      "destsubnet":<String_value>,
      "order":<Integer_value>,
      "portrange":<String_value>,
      "ruletype":<String_value>}}
```