# tune_setting

## Description

Get and Set for parameters on tuning page

## Read/write properties

`ftpcontrolports<[Integer,...]>`

vector of FTP control ports.
Minimum value = 1
Maximum value = 65535

`privilegedportshighest<Integer>`

Upper value of privileged port range.
Minimum value = 1
Maximum value = 1023

`privilegedportslowest<Integer>`

lower value of privileged port range.
Minimum value = 1
Maximum value = 1023

`idletimeout<Double>`

Timeout in seconds. Precision of this field is upto microseconds, a value precised more than microsecond may not get handled..
Minimum value = 1e-06
Maximum value = 999999999.999

`fwdloopprevent<Boolean>`

Forwarding loop prevention flag.
Possible values = [true,false]

`wanscalelimit<Integer>`

WAN window scale limit.
Minimum value = 10
Maximum value = 27

`lanscalelimit<Integer>`

LAN window scale limit.
Minimum value = 10
Maximum value = 20

`virtualinlinemode<String>`

Virtual Inline mode.
Possible values = [SendToGateway,ReturnToEthernetSender]

`timeoutenabled<Boolean>`

Timeout Enabled flag.
Possible values = [true,false]

`tcpmaximummss<Integer>`

Maximum value of TCP MSS should be greater than or equal to tcpdefaultmss. Note: The range of MSS specified above is for when IPV6 is disabled. If IPV6 enabled range is between 1220 to 1380..
Minimum value = 536
Maximum value = 1380

`tcpdefaultmss<Integer>`

Default value of TCP MSS should be less than or equal to tcpmaximummss. Note: The range of MSS specified above is for when IPV6 is disabled. If IPV6 enabled range is between 1220 to 1380..
Minimum value = 536
Maximum value = 1380

`daisychain<Boolean>`

Daisy chain enabled flag.
Possible values = [true,false]

`rshellports<[Integer,...]>`

Vector of Rshell ports.
Minimum value = 1
Maximum value = 65535

## Read only properties

## Operations

NOTE: In request payload, Mandatory parameters are marked red and bold.

* [get](#get)
* [modify](#modify)

### <a name="get">Get</a>

**URL:** `http://<CBIP>/cb/nitro/v1/config/tune_setting`

**HTTP Method:** GET

**Response Payload:** JSON

```json
{ "tune_setting":{
      "ftpcontrolports":<Integer_value>,
      "privilegedportshighest":<Integer_value>,
      "privilegedportslowest":<Integer_value>,
      "idletimeout":<Double_value>,
      "fwdloopprevent":<Boolean_value>,
      "wanscalelimit":<Integer_value>,
      "lanscalelimit":<Integer_value>,
      "virtualinlinemode":<String_value>,
      "timeoutenabled":<Boolean_value>,
      "tcpmaximummss":<Integer_value>,
      "tcpdefaultmss":<Integer_value>,
      "daisychain":<Boolean_value>,
      "rshellports":<Integer_value>}}
```

### <a name="modify">Modify</a>

**URL:** `http://<CBIP>/cb/nitro/v1/config/tune_setting`

**HTTP Method:** PUT

**Request Payload:** JSON

```json
{"tune_setting":{
      "ftpcontrolports":<Integer_value>,
      "privilegedportshighest":<Integer_value>,
      "privilegedportslowest":<Integer_value>,
      "idletimeout":<Double_value>,
      "fwdloopprevent":<Boolean_value>,
      "wanscalelimit":<Integer_value>,
      "lanscalelimit":<Integer_value>,
      "virtualinlinemode":<String_value>,
      "timeoutenabled":<Boolean_value>,
      "tcpmaximummss":<Integer_value>,
      "tcpdefaultmss":<Integer_value>,
      "daisychain":<Boolean_value>,
      "rshellports":<Integer_value>}}
```

**Response Payload:** JSON

```json
{ "tune_setting":{
      "ftpcontrolports":<Integer_value>,
      "privilegedportshighest":<Integer_value>,
      "privilegedportslowest":<Integer_value>,
      "idletimeout":<Double_value>,
      "fwdloopprevent":<Boolean_value>,
      "wanscalelimit":<Integer_value>,
      "lanscalelimit":<Integer_value>,
      "virtualinlinemode":<String_value>,
      "timeoutenabled":<Boolean_value>,
      "tcpmaximummss":<Integer_value>,
      "tcpdefaultmss":<Integer_value>,
      "daisychain":<Boolean_value>,
      "rshellports":<Integer_value>}}
```