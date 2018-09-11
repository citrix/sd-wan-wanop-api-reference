# ssl\_profile

## Description

SSL profiles list.

## Read/write properties

`transparentkeyname<String>`

SSL key to be used in transparent mode to encrypty/decrypt SSL traffic for this profile.

`buildcertchain<Boolean>`

Toggle to switch certificate chain building for authenticating client side negotiations.
Possible values = [true,false]

`clientsiderenegotiation<String>`

Client renegotiation type.
Possible values = [denied,old,compatible,new,oldignored]

`serversideprotoversion<String>`

SSL protocol version supported for server side negotiation. Use sv2 for SSL v2, sv3 for SSL v3, tv10 for TLS 1.0 or sv23 for allowing all of these three.
Possible values = [sv2,sv3,tv10,sv23]

`keycertname<String>`

Key/cert pair to be used in split mode for optimization of SSL profile.

`serversideauthbuildcertchain<Boolean>`

Toggle to switch certificate chain building for authenticating server side negotiations.
Possible values = [true,false]

`serversideciphers<String>`

Chosen ciphers for server side.

`clientsideprotoversion<String>`

SSL protocol version supported for client side negotiation. Use sv2 for SSL v2, sv3 for SSL v3, tv10 for TLS 1.0 or sv23 for allowing all of these three.
Possible values = [sv2,sv3,tv10,sv23]

`certchainstorename<String>`

CA store to be used to validate client side negotiation.

`name<String>`

CA Store Name.

`certverifycommonnames<[String,...]>`

List of black/white listed server CN.

`serversideauthrequired<Boolean>`

Enable/disable server side authentication.
Possible values = [true,false]

`serversideauthkeycertname<String>`

Key/Cert to be used for server side authentication.

`certverifyaction<String>`

Verify action for list of CN in certverifycommonnames.
Possible values = [white_list,black_list,allow_all,sig_exp_only]

`caverifystorename<String>`

CA store to be used to validate server side negotiation.

`virtualhostname<String>`

Virtual host name of server for which the SSL profile is being configured.

`proxytype<String>`

Parameter to set proxy type for optimizing this SSL profile.
Possible values = [transparent,split]

`clientsideciphers<String>`

Chosen ciphers for client side.

`profileenabled<Boolean>`

Enable/Disable profile.
Possible values = [true,false]

`serversiderenegotiation<String>`

Server renegotiation type.
Possible values = [denied,old,compatible,new,oldignored]

## Read only properties

`availablecipherlist<String>`

List of all available ciphers.

`profileinuse<Boolean>`

Indicator stating if profile is in use or not.

`serversidecipherlist<String>`

List of available ciphers for server side negotiation.

`serviceclasses<[String,...]>`

Serive classes attached to the profile.

`clientsidecipherlist<String>`

List of available ciphers for client side negotiation.

## Operations

**NOTE:** In request payload, Mandatory parameters are marked red and bold.

* [add](#add)
* [delete](#delete)
* [get(all)](#getall)
* [get](#get)
* [modify](#modify)

### <a name="add">Add</a>

**URL:** `http://<CBIP>/cb/nitro/v1/config/ssl_profile`

**HTTP Method:** POST

**Request Payload:** JSON

```json
{"ssl_profile":{
      "transparentkeyname":<String_value>,
      "buildcertchain":<Boolean_value>,
      "clientsiderenegotiation":<String_value>,
      "serversideprotoversion":<String_value>,
      "keycertname":<String_value>,
      "serversideauthbuildcertchain":<Boolean_value>,
      "serversideciphers":<String_value>,
      "clientsideprotoversion":<String_value>,
      "certchainstorename":<String_value>,
      "name":<String_value>,
      "certverifycommonnames":<String_value>,
      "serversideauthrequired":<Boolean_value>,
      "serversideauthkeycertname":<String_value>,
      "certverifyaction":<String_value>,
      "caverifystorename":<String_value>,
      "virtualhostname":<String_value>,
      "proxytype":<String_value>,
      "clientsideciphers":<String_value>,
      "profileenabled":<Boolean_value>,
      "serversiderenegotiation":<String_value>}}
```

**Response Payload:** JSON

```json
{ "ssl_profile":{
      "availablecipherlist":<String_value>,
      "transparentkeyname":<String_value>,
      "profileinuse":<Boolean_value>,
      "buildcertchain":<Boolean_value>,
      "clientsiderenegotiation":<String_value>,
      "serversideprotoversion":<String_value>,
      "serversidecipherlist":<String_value>,
      "keycertname":<String_value>,
      "serversideauthbuildcertchain":<Boolean_value>,
      "serversideciphers":<String_value>,
      "clientsideprotoversion":<String_value>,
      "certchainstorename":<String_value>,
      "name":<String_value>,
      "certverifycommonnames":<String_value>,
      "serviceclasses":<String_value>,
      "serversideauthrequired":<Boolean_value>,
      "serversideauthkeycertname":<String_value>,
      "certverifyaction":<String_value>,
      "caverifystorename":<String_value>,
      "virtualhostname":<String_value>,
      "proxytype":<String_value>,
      "clientsidecipherlist":<String_value>,
      "clientsideciphers":<String_value>,
      "profileenabled":<Boolean_value>,
      "serversiderenegotiation":<String_value>}}
```

### <a name="delete">Delete</a>

**URL:** `http://<CBIP>/cb/nitro/v1/config/ssl_profile/<name>`

**HTTP Method:** DELETE

**Response Payload:** EMPTY

### <a name="getall">Get(all)</a>

**URL:** `http://<CBIP>/cb/nitro/v1/config/ssl_profile`

**HTTP Method:** GET

**Response Payload:** JSON

```json
{ "ssl_profile":[{
      "availablecipherlist":<String_value>,
      "transparentkeyname":<String_value>,
      "profileinuse":<Boolean_value>,
      "buildcertchain":<Boolean_value>,
      "clientsiderenegotiation":<String_value>,
      "serversideprotoversion":<String_value>,
      "serversidecipherlist":<String_value>,
      "keycertname":<String_value>,
      "serversideauthbuildcertchain":<Boolean_value>,
      "serversideciphers":<String_value>,
      "clientsideprotoversion":<String_value>,
      "certchainstorename":<String_value>,
      "name":<String_value>,
      "certverifycommonnames":<String_value>,
      "serviceclasses":<String_value>,
      "serversideauthrequired":<Boolean_value>,
      "serversideauthkeycertname":<String_value>,
      "certverifyaction":<String_value>,
      "caverifystorename":<String_value>,
      "virtualhostname":<String_value>,
      "proxytype":<String_value>,
      "clientsidecipherlist":<String_value>,
      "clientsideciphers":<String_value>,
      "profileenabled":<Boolean_value>,
      "serversiderenegotiation":<String_value>}, ...]}
```

### <a name="get">Get</a>

**URL:** `http://<CBIP>/cb/nitro/v1/config/ssl_profile/<name>`

**HTTP Method:** GET

**Response Payload:** JSON

```json
{ "ssl_profile":{
      "availablecipherlist":<String_value>,
      "transparentkeyname":<String_value>,
      "profileinuse":<Boolean_value>,
      "buildcertchain":<Boolean_value>,
      "clientsiderenegotiation":<String_value>,
      "serversideprotoversion":<String_value>,
      "serversidecipherlist":<String_value>,
      "keycertname":<String_value>,
      "serversideauthbuildcertchain":<Boolean_value>,
      "serversideciphers":<String_value>,
      "clientsideprotoversion":<String_value>,
      "certchainstorename":<String_value>,
      "name":<String_value>,
      "certverifycommonnames":<String_value>,
      "serviceclasses":<String_value>,
      "serversideauthrequired":<Boolean_value>,
      "serversideauthkeycertname":<String_value>,
      "certverifyaction":<String_value>,
      "caverifystorename":<String_value>,
      "virtualhostname":<String_value>,
      "proxytype":<String_value>,
      "clientsidecipherlist":<String_value>,
      "clientsideciphers":<String_value>,
      "profileenabled":<Boolean_value>,
      "serversiderenegotiation":<String_value>}}
```

### <a name="modify">Modify</a>

**URL:** `http://<CBIP>/cb/nitro/v1/config/ssl_profile/<name>`

**HTTP Method:** PUT

**Request Payload:** JSON

```json
{"ssl_profile":{
      "transparentkeyname":<String_value>,
      "buildcertchain":<Boolean_value>,
      "clientsiderenegotiation":<String_value>,
      "serversideprotoversion":<String_value>,
      "keycertname":<String_value>,
      "serversideauthbuildcertchain":<Boolean_value>,
      "serversideciphers":<String_value>,
      "clientsideprotoversion":<String_value>,
      "certchainstorename":<String_value>,,
      "certverifycommonnames":<String_value>,
      "serversideauthrequired":<Boolean_value>,
      "serversideauthkeycertname":<String_value>,
      "certverifyaction":<String_value>,
      "caverifystorename":<String_value>,
      "virtualhostname":<String_value>,
      "proxytype":<String_value>,
      "clientsideciphers":<String_value>,
      "profileenabled":<Boolean_value>,
      "serversiderenegotiation":<String_value>}}
```

**Response Payload:** JSON

```json
{ "ssl_profile":{
      "availablecipherlist":<String_value>,
      "transparentkeyname":<String_value>,
      "profileinuse":<Boolean_value>,
      "buildcertchain":<Boolean_value>,
      "clientsiderenegotiation":<String_value>,
      "serversideprotoversion":<String_value>,
      "serversidecipherlist":<String_value>,
      "keycertname":<String_value>,
      "serversideauthbuildcertchain":<Boolean_value>,
      "serversideciphers":<String_value>,
      "clientsideprotoversion":<String_value>,
      "certchainstorename":<String_value>,
      "name":<String_value>,
      "certverifycommonnames":<String_value>,
      "serviceclasses":<String_value>,
      "serversideauthrequired":<Boolean_value>,
      "serversideauthkeycertname":<String_value>,
      "certverifyaction":<String_value>,
      "caverifystorename":<String_value>,
      "virtualhostname":<String_value>,
      "proxytype":<String_value>,
      "clientsidecipherlist":<String_value>,
      "clientsideciphers":<String_value>,
      "profileenabled":<Boolean_value>,
      "serversiderenegotiation":<String_value>}}
```