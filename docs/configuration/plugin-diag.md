# plugin_diag

## Description

Configuration of FTP server/path for uploading plugin diagnostics.

## Read/write properties

`diagautoupload <String>`

Automatically upload diagnostic reports.

`diagemail <String>`

Email account to send plugin diagnostic notification.

`diagftppassword <String>`

FTP password..

`diagftpport <Integer>`

FTP Server port.
Minimum value = 1
Maximum value = 65535

`diagftpuser <String>`

FTP username..

`diagftpdirectory <String>`

Path on the FTP server to upload files.

`diagftpserver <String>`

IP address of FTP Server.

`diagpopups <Boolean>`

Allow pop ups on the plugin to prompt user for uploading diagnostic report..
Possible values = [true,false]

## Read only properties

## Operations

**Note:** In request payload, Mandatory parameters are marked red and bold.

* [get](#get)
* [modify](#modify)

### <a name="get">Get</a>

URL: `http://<CBIP>/cb/nitro/v1/config/plugin_diag`

HTTP Method: GET

Response Payload: JSON

```json
{ "plugin_diag":{
      "diagautoupload":<String_value>,
      "diagemail":<String_value>,
      "diagftppassword":<String_value>,
      "diagftpport":<Integer_value>,
      "diagftpuser":<String_value>,
      "diagftpdirectory":<String_value>,
      "diagftpserver":<String_value>,
      "diagpopups":<Boolean_value>}}
```

### <a name="modify">Modify</a>

URL: `http://<CBIP>/cb/nitro/v1/config/plugin_diag`

HTTP Method: PUT

Request Payload: JSON

```json
{"plugin_diag":{
      "diagautoupload":<String_value>,
      "diagemail":<String_value>,
      "diagftppassword":<String_value>,
      "diagftpport":<Integer_value>,
      "diagftpuser":<String_value>,
      "diagftpdirectory":<String_value>,
      "diagftpserver":<String_value>,
      "diagpopups":<Boolean_value>}}
```

Response Payload: JSON

```json
{ "plugin_diag":{
      "diagautoupload":<String_value>,
      "diagemail":<String_value>,
      "diagftppassword":<String_value>,
      "diagftpport":<Integer_value>,
      "diagftpuser":<String_value>,
      "diagftpdirectory":<String_value>,
      "diagftpserver":<String_value>,
      "diagpopups":<Boolean_value>}}
```