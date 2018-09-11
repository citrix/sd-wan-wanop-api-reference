# ssl\_store

## Description

Configuration of SSL Store

## Read/write properties

`storeopened<Boolean>`

Boolean used to get/set state of store. Store open needs a storepassword..
Possible values = [true,false]

`passwordenabled<Boolean>`

Boolean used to get/set state of store password. Should be accompanied with a storeopened and storepassword keys..
Possible values = [true,false]

`diskencryption<Boolean>`

Boolean to get/set state of disk encryption. Turn ON needs an open key store..
Possible values = [true,false]

`storepassword<String>`

Password used to enable password or disable (once enabled) password or open key store once password is set. To change password, first disable password and then enable using new password..

## Read only properties

`passwordconfigured<Boolean>`

Boolean stating if password has been ever configured on the box. Use key passwordenabled to either enable password or disable using password..

## Operations

NOTE: In request payload, Mandatory parameters are marked red and bold.

* [get](#get)
* [modify](#modify)


### <a name="get">get</a>

**URL:** `http://<CBIP>/cb/nitro/v1/config/ssl_store`

**HTTP Method:** GET

**Response Payload:** JSON

```json
{ "ssl_store":{
      "passwordconfigured":<Boolean_value>,
      "storeopened":<Boolean_value>,
      "passwordenabled":<Boolean_value>,
      "diskencryption":<Boolean_value>,
      "storepassword":<String_value>}}
```

### <a name="modify">Modify</a>

**URL:** `http://<CBIP>/cb/nitro/v1/config/ssl_store`

**HTTP Method:** PUT

**Request Payload:** JSON

```json
{"ssl_store":{
      "storeopened":<Boolean_value>,
      "passwordenabled":<Boolean_value>,
      "diskencryption":<Boolean_value>,
      "storepassword":<String_value>}}
```

**Response Payload:** JSON

```json
{ "ssl_store":{
      "passwordconfigured":<Boolean_value>,
      "storeopened":<Boolean_value>,
      "passwordenabled":<Boolean_value>,
      "diskencryption":<Boolean_value>,
      "storepassword":<String_value>}}
```