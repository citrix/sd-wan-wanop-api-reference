# application

## Description

Application classifier definition

## Read/write properties

`classifierparamvalue <String>`

Value of the classifier parameter

`appgroup <[String,...]>`

Application group to which the application belongs

Possible values = [Backup and Replication,Citrix Protocols,Client-Server,Content Delivery,Custom,Database and Enterprise Resource Planning (ERP) Software,Directory Services,Email and Collaboration,File Server,Games,General Classifiers,Host Access,Infrastructure,IP Protocols,Legacy Or Non-IP,Messaging,Middleware,Multimedia,Network Management,Peer-to-Peer (P2P) Applications,Routing Protocols,Security Protocols,Servers,Session,Video Websites,Voice Over IP (VOIP),Web]

`name <String>`

Name of application

`description <String>`

Description of application..

`classifiertype <String>`

Type of classification to be done. eg. IP based, TCP based etc.

Possible values = [Web Address,Dynamic TCP,ICA Published App,UDP,IP,TCP,Ethertype]

## Read only properties

`classifierparamname <String>`

Name of classifier parameter. Depending on classifiertype value classifierparamname can take vlues Web Address,Published App Name, UDP Port, Protocol, TCP Port, Ethertype respectively. For classifiertype Dynamic TCP classifierparamname will not be present..

## Operations

**Note:** In request payload, Mandatory parameters are marked red and bold.

* [add](#add)
* [delete](#delete)
* [get(all)](#getall)
* [get](#get)
* [modify](#modify)

### <a name="add">Add</a>

URL: `http://<CBIP>/cb/nitro/v1/config/application`

HTTP Method: POST

Request Payload: JSON

```json
{"application":{
      "classifierparamvalue":<String_value>,
      "appgroup":<String_value>,
      "name":<String_value>,
      "description":<String_value>,
      "classifiertype":<String_value>}}
```

Response Payload: JSON

```json
{ "application":{
      "classifierparamvalue":<String_value>,
      "classifierparamname":<String_value>,
      "appgroup":<String_value>,
      "name":<String_value>,
      "description":<String_value>,
      "classifiertype":<String_value>}}
```

### <a name="delete">Delete</a>

URL: `http://<CBIP>/cb/nitro/v1/config/application/<name>`

HTTP Method: DELETE

Response Payload: EMPTY

### <a name="getall">Get (All)</a>

URL: `http://<CBIP>/cb/nitro/v1/config/application`

HTTP Method: GET

Response Payload: JSON

```json
{ "application":[{
      "classifierparamvalue":<String_value>,
      "classifierparamname":<String_value>,
      "appgroup":<String_value>,
      "name":<String_value>,
      "description":<String_value>,
      "classifiertype":<String_value>}, ...]}

```
### <a name="get">Get</a>

URL: `http://<CBIP>/cb/nitro/v1/config/application/<name>`

HTTP Method: GET

Response Payload: JSON

```json
{ "application":{
      "classifierparamvalue":<String_value>,
      "classifierparamname":<String_value>,
      "appgroup":<String_value>,
      "name":<String_value>,
      "description":<String_value>,
      "classifiertype":<String_value>}}
```

### <a name="modify">Modify</a>

URL: `http://<CBIP>/cb/nitro/v1/config/application/<name>`

HTTP Method: PUT

Request Payload: JSON

```json
{"application":{
      "classifierparamvalue":<String_value>,
      "appgroup":<String_value>,,
      "description":<String_value>,
      "classifiertype":<String_value>}}
```

Response Payload: JSON

```json
{ "application":{
      "classifierparamvalue":<String_value>,
      "classifierparamname":<String_value>,
      "appgroup":<String_value>,
      "name":<String_value>,
      "description":<String_value>,
      "classifiertype":<String_value>}}
```