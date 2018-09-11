# license_file

## Description

Configuration for License File resource. This NITRO resource is applicable for CloudBridge 4000 and 5000 platforms only.

## Read/write properties

`file_location_path <String>`

File Location on Client for upload/download.
Minimum length = 1

`file_name <String>`

File Name.
Minimum length = 1
Maximum length = 256

## Read only properties

`file_size <Integer>`

File size.

`file_last_modified <String>`

Last Modified.

## Operations

**Note:** In request payload, Mandatory parameters are marked red and bold.

The following parameters can be used in the nitro request:

`onerror   <String_value>`

Use this parameter to set the onerror status for nitro request. Applicable only for bulk requests.

Default value: EXIT
Possible values = EXIT, CONTINUE

* [upload](#upload)
* [delete](#delete)
* [get(all)](#getall)
* [get](#get)
* [download](#download)

### <a name="delete">Delete</a>

URL: `http://<SDXIP>/nitro/v1/config/license_file/file_name_value<String>`

HTTP Method: DELETE

Response Payload: JSON

```json
{ "errorcode": 0, "message": "Done", "severity": <String_value> }
```

### <a name="getall">Get (All)</a>

URL: `http://<SDXIP>/nitro/v1/config/license_file`

HTTP Method: GET

Response Payload: JSON

```json
{ "errorcode": 0, "message": "Done", "severity": <String_value>, "license_file":[{
      "file_location_path":<String_value>,
      "file_size":<Integer_value>,
      "file_name":<String_value>,
      "file_last_modified":<String_value>}]}
```

### <a name="get">Get</a>

URL: `http://<SDXIP>/nitro/v1/config/license_file/file_name_value<String>`

HTTP Method: GET

Response Payload: JSON

```json
{ "errorcode": 0, "message": "Done", "severity": <String_value>, "license_file":[{
      "file_location_path":<String_value>,
      "file_size":<Integer_value>,
      "file_name":<String_value>,
      "file_last_modified":<String_value>}]}
```

### <a name="upload">Upload</a>

URL: `http://<SDXIP>/nitro/v1/upload/license_file`

HTTP Method: POST

Request Payload: Multi-part form data with File Stream

Response Payload: JSON

```json
{ "errorcode": 0, "message": "Done }
```

### <a name="download">Download</a>

URL: `http://<SDXIP>/nitro/v1/download/license_file/file_name_value<String>`

HTTP Method: GET

Response Payload: Binary Stream