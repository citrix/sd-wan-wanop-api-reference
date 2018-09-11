# ssl\_ca

## Description

SSL CA store list.

## Read/write properties

`name<String>`

CA Store Name.

`certpem<String>`

Cert input in pem format. This is write only parameter. To fetch certicate pem text or other details, see certinfo parameter..

## Read only properties

`certificatedetails<String>`

Certificate details text providing Version,Serial Number,Signature Algorithm,Issuer etc.

`certcount<Integer>`

Certificate Count..

`certinfo<[{...},...]>`

Certificate pem text and expiry info for each certificate in the input bundle.

`certexpirydate<String>`

Certificate expiry date..

`certexpired<Boolean>`

Certificate expiry status..

## Operations

**NOTE**: In request payload, Mandatory parameters are marked red and bold.

* [add](#add)
* [delete](#delete)
* [get(all)](#getall)
* [get](#get)
* [modify](#modify)

### <a name="add">Add</a>

**URL:** `http://<CBIP>/cb/nitro/v1/config/ssl_ca`

**HTTP Method:** POST

**Request Payload:** JSON

```json
{"ssl_ca":{
      "name":<String_value>,
      "certpem":<String_value>}}
```

**Response Payload:** JSON

```json
{ "ssl_ca":{
      "certificatedetails":<String_value>,
      "name":<String_value>,
      "certcount":<Integer_value>,
      "certpem":<String_value>,
      "certinfo":[{
            "certexpirydate":<String_value>,
            "certpem":<String_value>,
            "certexpired":<Boolean_value>}, ...]}}
```

### <a name="delete">Delete</a>

**URL:** `http://<CBIP>/cb/nitro/v1/config/ssl_ca/<name>`

**HTTP Method:** DELETE

**Response Payload:** EMPTY

Get (all)

**URL:** `http://<CBIP>/cb/nitro/v1/config/ssl_ca`

**HTTP Method:** GET

**Response Payload:** JSON

```json
{ "ssl_ca":[{
      "certificatedetails":<String_value>,
      "name":<String_value>,
      "certcount":<Integer_value>,
      "certpem":<String_value>,
      "certinfo":[{
            "certexpirydate":<String_value>,
            "certpem":<String_value>,
            "certexpired":<Boolean_value>}, ...]}, ...]}
```

### <a name="get">Get</a>

**URL: **`http://<CBIP>/cb/nitro/v1/config/ssl_ca/<name>`

**HTTP Method:** GET

**Response Payload:** JSON

```json
{ "ssl_ca":{
      "certificatedetails":<String_value>,
      "name":<String_value>,
      "certcount":<Integer_value>,
      "certpem":<String_value>,
      "certinfo":[{
            "certexpirydate":<String_value>,
            "certpem":<String_value>,
            "certexpired":<Boolean_value>}, ...]}}
```

### <a name="modify">Modify</a>

**URL:** `http://<CBIP>/cb/nitro/v1/config/ssl_ca/<name>`

**HTTP Method:** PUT

**Request Payload:** JSON

```json
{"ssl_ca":{
      "certpem":<String_value>}}
```

**Response Payload:** JSON

```json
{ "ssl_ca":{
      "certificatedetails":<String_value>,
      "name":<String_value>,
      "certcount":<Integer_value>,
      "certpem":<String_value>,
      "certinfo":[{
            "certexpirydate":<String_value>,
            "certpem":<String_value>,
            "certexpired":<Boolean_value>}, ...]}}
```
