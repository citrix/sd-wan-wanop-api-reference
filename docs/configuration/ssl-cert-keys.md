# ssl\_cert\_keys

## Description

SSL Certificate-Key pair.

## Read/write properties

`name<String>`

Certificate Name.

`keypem<String>`

Key in pem format. Has to be decoded before applying, if password encrypted.

`certpem<String>`

Cert input in pem format. This is write only parameter. To fetch certicate pem text or other details, see certinfo parameter..

`modifyaction<String>`

Specifies whether to replace an existing key-type, add a new key-type or remove one of them when both are already present .
Possible values = [replace_rsa,replace_dsa,remove_rsa,remove_dsa,add_rsa,add_dsa]

## Read only properties

`certificatedetails<[String,...]>`

Certificate details text providing Version,Serial Number,Signature Algorithm,Issuer etc.

`keytype<String>`

Certificate/key type..

`certinfo<[{...},...]>`

Certificate pem text and expiry info for each certificate in the input bundle.

`certexpirydate<String>`

Certificate expiry date..

`certexpired<Boolean>`

Certificate expiry status..

`certcount<Integer>`

Certificate Count..

## Operations

**NOTE**: In request payload, Mandatory parameters are marked red and bold.

* [add](#get)
* [delete](#delete)
* [get(all)](#getall)
* [get](#get)
* [modify](#modify)

### <a name="add">Add</a>

**URL:**`http://<CBIP>/cb/nitro/v1/config/ssl_cert_keys`

**HTTP Method:** POST

**Request Payload:** JSON

```json
{"ssl_cert_keys":{
      "name":<String_value>,
      "keypem":<String_value>,
      "certpem":<String_value>,
      "modifyaction":<String_value>}}
```

**Response Payload:** JSON

```json
{ "ssl_cert_keys":{
      "certificatedetails":<String_value>,
      "name":<String_value>,
      "keytype":<String_value>,
      "certinfo":[{
            "certexpirydate":<String_value>,
            "certpem":<String_value>,
            "certexpired":<Boolean_value>}, ...],
      "keypem":<String_value>,
      "certpem":<String_value>,
      "modifyaction":<String_value>,
      "certcount":<Integer_value>}}
```

### <a name="delete">Delete</a>

**URL:**`http://<CBIP>/cb/nitro/v1/config/ssl_cert_keys/<name>`

**HTTP Method:** DELETE

**Response Payload:** EMPTY

### <a name="getall">Get(all)</a>

**URL:**`http://<CBIP>/cb/nitro/v1/config/ssl_cert_keys`

**HTTP Method:** GET

**Response Payload:** JSON

```json
{ "ssl_cert_keys":[{
      "certificatedetails":<String_value>,
      "name":<String_value>,
      "keytype":<String_value>,
      "certinfo":[{
            "certexpirydate":<String_value>,
            "certpem":<String_value>,
            "certexpired":<Boolean_value>}, ...],
      "keypem":<String_value>,
      "certpem":<String_value>,
      "modifyaction":<String_value>,
      "certcount":<Integer_value>}, ...]}
```

### <a name="get">Get</a>

**URL:**`http://<CBIP>/cb/nitro/v1/config/ssl_cert_keys/<name>`

**HTTP Method:** GET

**Response Payload:** JSON

```json
{ "ssl_cert_keys":{
      "certificatedetails":<String_value>,
      "name":<String_value>,
      "keytype":<String_value>,
      "certinfo":[{
            "certexpirydate":<String_value>,
            "certpem":<String_value>,
            "certexpired":<Boolean_value>}, ...],
      "keypem":<String_value>,
      "certpem":<String_value>,
      "modifyaction":<String_value>,
      "certcount":<Integer_value>}}
```

### <a name="modify">Modify</a>

**URL:**`http://<CBIP>/cb/nitro/v1/config/ssl_cert_keys/<name>`

**HTTP Method:** PUT

**Request Payload:** JSON

```json
{"ssl_cert_keys":{
      "keypem":<String_value>,
      "certpem":<String_value>,
      "modifyaction":<String_value>}}
```

**Response Payload:** JSON

```json
{ "ssl_cert_keys":{
      "certificatedetails":<String_value>,
      "name":<String_value>,
      "keytype":<String_value>,
      "certinfo":[{
            "certexpirydate":<String_value>,
            "certpem":<String_value>,
            "certexpired":<Boolean_value>}, ...],
      "keypem":<String_value>,
      "certpem":<String_value>,
      "modifyaction":<String_value>,
      "certcount":<Integer_value>}}
```