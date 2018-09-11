# plugin_config

## Description

Configuration of Redirector IP/port etc to establish signalling channel.

## Read/write properties

`redirectorenabled <Boolean>`

Plugin enabled.
Possible values = [true,false]

`connectionmode <String>`

Plugin redirection mode.
Possible values = [transparent,redirector]

`landetectrttthreshold <Integer>`

RTT below which enviroment for connection is assumed to be LAN.
Minimum value = 1
Maximum value = 50

`filteringlist <[{...},...]>`

Filtering list to allow/disallow traffic from configured subnets.

`allow <Boolean>`

IP address of FTP Server.
Possible values = [true,false]

`subnet <String>`

Filtering list subnet (IPv4/IPv6 string).
Bitmask = Optional (format IP[/bitmask])

`redirectorport <Integer>`

Listening port for signalling connections.
Minimum value = 1
Maximum value = 65535

`lanwandetectenabled <Boolean>`

Enable/disable detection of LAN/WAN enviroment.
Possible values = [true,false]

`redirectorip <String>`

IP address for signalling connections (IPv4/IPv6 string).

`filteringenabled <Boolean>`

Enable/disable source filtering.
Possible values = [true,false]

`redirectoripprefix <Integer>`

Signaling IP prefix.
Minimum value = 1
Maximum value = 31

## Read only properties

`redirectorstatus <String>`

Informatory status of plugin feature.

## Operations

**Note:** In request payload, Mandatory parameters are marked red and bold.

* [get](#get)
* [modify](#modify)

### <a name="get">Get</a>

URL: `http://<CBIP>/cb/nitro/v1/config/plugin_config`

HTTP Method: GET

Response Payload: JSON

```json
{ "plugin_config":{
      "redirectorenabled":<Boolean_value>,
      "connectionmode":<String_value>,
      "landetectrttthreshold":<Integer_value>,
      "filteringlist":[{
            "allow":<Boolean_value>,
            "subnet":<String_value>}, ...],
      "redirectorport":<Integer_value>,
      "redirectorstatus":<String_value>,
      "lanwandetectenabled":<Boolean_value>,
      "redirectorip":<String_value>,
      "filteringenabled":<Boolean_value>,
      "redirectoripprefix":<Integer_value>}}
```

### <a name="modify">Modify</a>

URL: `http://<CBIP>/cb/nitro/v1/config/plugin_config`

HTTP Method: PUT

Request Payload: JSON

```json
{"plugin_config":{
      "redirectorenabled":<Boolean_value>,
      "connectionmode":<String_value>,
      "landetectrttthreshold":<Integer_value>,
      "filteringlist":[{
            "allow":<Boolean_value>,
            "subnet":<String_value>}, ...],
      "redirectorport":<Integer_value>,
      "lanwandetectenabled":<Boolean_value>,
      "redirectorip":<String_value>,
      "filteringenabled":<Boolean_value>,
      "redirectoripprefix":<Integer_value>}}
```

Response Payload: JSON

```json
{ "plugin_config":{
      "redirectorenabled":<Boolean_value>,
      "connectionmode":<String_value>,
      "landetectrttthreshold":<Integer_value>,
      "filteringlist":[{
            "allow":<Boolean_value>,
            "subnet":<String_value>}, ...],
      "redirectorport":<Integer_value>,
      "redirectorstatus":<String_value>,
      "lanwandetectenabled":<Boolean_value>,
      "redirectorip":<String_value>,
      "filteringenabled":<Boolean_value>,
      "redirectoripprefix":<Integer_value>}}
```