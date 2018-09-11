# ssl\_partner

## Description

Configuration for setting up secure partner

## Read/write properties

`ciphers<String>`

Configured cipher specification.

`autodiscovery<Boolean>`

IP-Adress:Port configured on remoted side to listen-on for signalling connections..
Possible values = [true,false]

`publishenabled<Boolean>`

Enable/Disable publishing NAT IPs.
Possible values = [true,false]

`securepeerenabled<Boolean>`

Enable/disable secure peering.
Possible values = [true,false]

`listenon<[String,...]>`

IP-Adress:Port configured to listen-on for signalling connections. This parameter is not configurable on CloudBridge 4000 and 5000 IP-reduced platforms. This parameter will be ignored even if it is present in input payload for CloudBridge 4000 and 5000 IP-reduced platforms..

`certverifycommonnames<[String,...]>`

List of black/white listed server CN.

`castorename<String>`

Ca store used for authenticating negotiation with secure peer.

`certkeyname<String>`

Certificate/Key pair to be use for secure tunneling..

`connectto<[String,...]>`

Remote host with which the connection should be established..

`certverifyaction<String>`

Verify action for list of CN in certverifycommonnames.
Possible values = [white_list,black_list,allow_all,sig_exp_only]

`publish<[String,...]>`

List of IP/port tuples being published for peer to connect to..

## Read only properties

`availablecipherlist<String>`

Avialable cipher list for negotiation with secure partner.

`defaultport<Integer>`

Default port for listening..

`valid<Boolean>`

Valid configuration for signalling channel negotiation..

`listenonchoices<[String,...]>`

IP subnet vailable to chose listening IP from..

`cipherlist<String>`

Configured cipher list for negotiation with secure partner.

`discoveredpeers<[String,...]>`

List of yet discovered peers..

## Operations

**NOTE:** In request payload, Mandatory parameters are marked red and bold.

* [get](#get)
* [modify](#modify)

### <a name="get">Get</a>

**URL:** `http://<CBIP>/cb/nitro/v1/config/ssl_partner`

**HTTP Method:** GET

**Response Payload:** JSON

```json
{ "ssl_partner":{
      "ciphers":<String_value>,
      "availablecipherlist":<String_value>,
      "autodiscovery":<Boolean_value>,
      "defaultport":<Integer_value>,
      "valid":<Boolean_value>,
      "listenonchoices":<String_value>,
      "cipherlist":<String_value>,
      "discoveredpeers":<String_value>,
      "publishenabled":<Boolean_value>,
      "securepeerenabled":<Boolean_value>,
      "listenon":<String_value>,
      "certverifycommonnames":<String_value>,
      "castorename":<String_value>,
      "certkeyname":<String_value>,
      "connectto":<String_value>,
      "certverifyaction":<String_value>,
      "publish":<String_value>}}
```

### <a name="modify">Modify</a>

**URL:** `http://<CBIP>/cb/nitro/v1/config/ssl_partner`

**HTTP Method:** PUT

**Request Payload:** JSON

```json
{"ssl_partner":{
      "listenon":<String_value>,,,,,,}}
```

**Response Payload:** JSON

```json
{ "ssl_partner":{
      "ciphers":<String_value>,
      "availablecipherlist":<String_value>,
      "autodiscovery":<Boolean_value>,
      "defaultport":<Integer_value>,
      "valid":<Boolean_value>,
      "listenonchoices":<String_value>,
      "cipherlist":<String_value>,
      "discoveredpeers":<String_value>,
      "publishenabled":<Boolean_value>,
      "securepeerenabled":<Boolean_value>,
      "listenon":<String_value>,
      "certverifycommonnames":<String_value>,
      "castorename":<String_value>,
      "certkeyname":<String_value>,
      "connectto":<String_value>,
      "certverifyaction":<String_value>,
      "publish":<String_value>}}
```