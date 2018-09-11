# radius_servers

## Description

Configuration of RADIUS server. This NITRO resource is applicable for CloudBridge 400, 800, 1000, 2000, 2000WS, 3000, 4000, and 5000 platforms only.

## Read/write properties

`defaultauthenticationgroup <String>`

This is the default group that is chosen when the authentication succeeds in addition to extracted groups..

`groupseparator <String>`

Group separator string that delimits group names within a RADIUS attribute for RADIUS group extraction..

`nasid <String>`

NAS ID..

`passencoding <String>`

Enable password encoding in RADIUS packets send to the RADIUS server..

`key <String>`

Key of radius server.

`authtimeout <String>`

The maximum number of seconds the system will wait for a response from the RADIUS server..

`pwdvendorid <String>`

Vendor ID of the password in the RADIUS response. Used to extract the user password..

`attributetype <String>`

Attribute type for RADIUS group extraction..

`pwdattributetype <String>`

The attribute type of the password attribute in a RADIUS response..

`groupsprefix <String>`

Prefix string that precedes group names within a RADIUS attribute for RADIUS group extraction..

`ipvendorid <String>`

The vendor ID of the attribute in the RADIUS response which denotes the intranet IP..

`name <String>`

Name of RADIUS server..

`port <String>`

RADIUS server port.

`vendorid <String>`

Vendor ID for RADIUS group extraction..

`enablenasip <String>`

Enable NAS IP extraction..
Possible values = [true,false]

`accounting <String>`

Enable accounting in the radius server..
Possible values = [true,false]

`ipaddress <String>`

RADIUS server IP address..

`ipattributetype <String>`

The attribute type of the remote IP address attribute in a RADIUS response..

## Read only properties

## Operations

**Note:** In request payload, Mandatory parameters are marked red and bold.

* [add](#add)
* [delete](#delete)
* [get(all)](#getall)
* [get](#get)
* [modify](#modify)

### <a name="add">Add</a>

URL: `http://<CBIP>/cb/nitro/v1/config/radius_servers`

HTTP Method: POST

Request Payload: JSON

```json
{"radius_servers":{
      "defaultauthenticationgroup":<String_value>,
      "groupseparator":<String_value>,
      "nasid":<String_value>,
      "passencoding":<String_value>,
      "key":<String_value>,
      "authtimeout":<String_value>,
      "pwdvendorid":<String_value>,
      "attributetype":<String_value>,
      "pwdattributetype":<String_value>,
      "groupsprefix":<String_value>,
      "ipvendorid":<String_value>,
      "name":<String_value>,
      "port":<String_value>,
      "vendorid":<String_value>,
      "enablenasip":<String_value>,
      "accounting":<String_value>,
      "ipaddress":<String_value>,
      "ipattributetype":<String_value>}}
```

Response Payload: JSON

```json
{ "radius_servers":{
      "defaultauthenticationgroup":<String_value>,
      "groupseparator":<String_value>,
      "nasid":<String_value>,
      "passencoding":<String_value>,
      "key":<String_value>,
      "authtimeout":<String_value>,
      "pwdvendorid":<String_value>,
      "attributetype":<String_value>,
      "pwdattributetype":<String_value>,
      "groupsprefix":<String_value>,
      "ipvendorid":<String_value>,
      "name":<String_value>,
      "port":<String_value>,
      "vendorid":<String_value>,
      "enablenasip":<String_value>,
      "accounting":<String_value>,
      "ipaddress":<String_value>,
      "ipattributetype":<String_value>}}
```

### <a name="delete">Delete</a>

URL: `http://<CBIP>/cb/nitro/v1/config/radius_servers/<name>`

HTTP Method: DELETE

Response Payload: EMPTY

### <a name="getall">Get (All)</a>

URL: `http://<CBIP>/cb/nitro/v1/config/radius_servers`

HTTP Method: GET

Response Payload: JSON

```json
{ "radius_servers":[{
      "defaultauthenticationgroup":<String_value>,
      "groupseparator":<String_value>,
      "nasid":<String_value>,
      "passencoding":<String_value>,
      "key":<String_value>,
      "authtimeout":<String_value>,
      "pwdvendorid":<String_value>,
      "attributetype":<String_value>,
      "pwdattributetype":<String_value>,
      "groupsprefix":<String_value>,
      "ipvendorid":<String_value>,
      "name":<String_value>,
      "port":<String_value>,
      "vendorid":<String_value>,
      "enablenasip":<String_value>,
      "accounting":<String_value>,
      "ipaddress":<String_value>,
      "ipattributetype":<String_value>}, ...]}
```

### <a name="get">Get</a>

URL: `http://<CBIP>/cb/nitro/v1/config/radius_servers/<name>`

HTTP Method: GET

Response Payload: JSON

```json
{ "radius_servers":{
      "defaultauthenticationgroup":<String_value>,
      "groupseparator":<String_value>,
      "nasid":<String_value>,
      "passencoding":<String_value>,
      "key":<String_value>,
      "authtimeout":<String_value>,
      "pwdvendorid":<String_value>,
      "attributetype":<String_value>,
      "pwdattributetype":<String_value>,
      "groupsprefix":<String_value>,
      "ipvendorid":<String_value>,
      "name":<String_value>,
      "port":<String_value>,
      "vendorid":<String_value>,
      "enablenasip":<String_value>,
      "accounting":<String_value>,
      "ipaddress":<String_value>,
      "ipattributetype":<String_value>}}
```

### <a name="modify">Modify</a>

URL: `http://<CBIP>/cb/nitro/v1/config/radius_servers/<name>`

HTTP Method: PUT

Request Payload: JSON

```json
{"radius_servers":{
      "defaultauthenticationgroup":<String_value>,
      "groupseparator":<String_value>,
      "nasid":<String_value>,
      "passencoding":<String_value>,
      "key":<String_value>,
      "authtimeout":<String_value>,
      "pwdvendorid":<String_value>,
      "attributetype":<String_value>,
      "pwdattributetype":<String_value>,
      "groupsprefix":<String_value>,
      "ipvendorid":<String_value>,,
      "port":<String_value>,
      "vendorid":<String_value>,
      "enablenasip":<String_value>,
      "accounting":<String_value>,
      "ipaddress":<String_value>,
      "ipattributetype":<String_value>}}
```

Response Payload: JSON

```json
{ "radius_servers":{
      "defaultauthenticationgroup":<String_value>,
      "groupseparator":<String_value>,
      "nasid":<String_value>,
      "passencoding":<String_value>,
      "key":<String_value>,
      "authtimeout":<String_value>,
      "pwdvendorid":<String_value>,
      "attributetype":<String_value>,
      "pwdattributetype":<String_value>,
      "groupsprefix":<String_value>,
      "ipvendorid":<String_value>,
      "name":<String_value>,
      "port":<String_value>,
      "vendorid":<String_value>,
      "enablenasip":<String_value>,
      "accounting":<String_value>,
      "ipaddress":<String_value>,
      "ipattributetype":<String_value>}}
```