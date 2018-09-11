# Citrix NetScaler SD-WAN WANOP 10.1 API

The Citrix SD-WAN WANOP NITRO API allows you to configure and monitor the appliance
programmatically. NITRO provides its functionality through Representational State
Transfer (REST) interfaces. Therefore, NITRO applications can be developed in any
programming language.


**Note:** You must have a basic understanding of the SD-WAN WANOP appliance before using
the NITRO API.

To use the NITRO API, the client application needs only the following:

* Access to a SD-WAN WANOP appliance, version 7.4 or later.
* Have a system to generate HTTP or HTTPS requests (payload in JSON format) to the
SD-WAN WANOP appliance. You can use any programming language or tool.

The detailed description of all NITRO resources is provided in the tar file that is
provided on the Downloads tab of SD-WAN WANOP Graphical User Interface.

## How NITRO Works

The NITRO infrastructure consists of a client application and the NITRO Web service
running on a SD-WAN WANOP appliance. The communication between the client application
and the NITRO web service is based on REST architecture using HTTP or HTTPS.

As shown in the above figure, a NITRO request is executed as follows:

1. The client application sends REST request message to the NITRO web service.
2. The web service processes the REST request message.
3. The NITRO web service returns the corresponding REST response message to the client application.

NITRO APIs are synchronous in nature. This means that the client application waits for a response from
the NITRO web service before executing another NITRO API.

## General API Usage

REST (Representational State Transfer) is an architectural style based on simple HTTPS requests and
responses between the client and the server. REST is used to query or change the state of objects on the
server side. In REST, the server side is modelled as a set of entities where each entity is identified by a
unique URL.

Each resource also has a state on which the following operations can be performed:

* **Create:** Clients can create new server-side resources on a "container" resource. You can think of
container resources as folders, and child resources as files or subfolders. The calling client provides the state for the resource to be created. The state can be specified in the request by
using JSON format. The HTTPS method used for create requests is POST.
* **Read:** Clients can retrieve the state of a resource by specifying its URL with the HTTPS GET
method. The response message contains the resource state, expressed in JSON format.
* **Update:** You can update the state of an existing resource by specifying the URL that identifies
that object and its new state in JSON, using the PUT HTTPS method.
* **Delete:** You can destroy a resource that exists on the server-side by using the DELETE HTTPS
method and the URL identifying the resource to be removed.

In addition to the above four operations, resources can support other operations or actions. These
operations use the HTTPS POST method, with the request body (if applicable) in JSON specifying the
details of the operation.

Before going into the details of the NITRO operations, you must be aware of the
following functionality:

* Every NITRO request must be authenticated by providing the credentials in the
request header. The credentials must be provided in base64 encoded format as
follows:
Authorization: Basic <*base64 encoded(username:password)*>
* Resources are identified by unique identifiers. Some resources have a single key
acting as unique identifier and a few resources have multiple keys forming the
unique identifier.
    * For resources which have a single key acting as the unique identifier, you can get
its details or delete it by providing the URL as follows:
https://<cb_ip>/cb/nitro/v1/config/<resource>/<value_of_unique_id>

    * For resources which have multiple keys as the unique identifier, you can get its
details or delete it by providing the identifiers in the URL as follows:
https://<cb_ip>/cb/nitro/v1/config/<resource>/<unique-id1>=<value>&<uniqueid2>=<
value>
* All NITRO operations are logged in the /var/log/nitro.log file on the
SD-WAN WANOP appliance.

### Adding a SD-WAN WANOP Resource
The request and response formats to add a single resource. The URL must specify the
type of resource to be added. The request header must provide the base64 encoded
username and password.

**Note:** The examples in this documentation use the "*user_account*" resource type.
* Request

    **HTTP Method** - POST
    
    **URL** - https://<cb_ip>/cb/nitro/v1/config/user_account

    **Request Headers**
        
        Authorization: Basic <base64 encoded(username:password)>Content-Type: application/ vnd.com.citrix.cloudbridge.user_account+json Accept: <Optional but validated if given. Can either be */* or same as the content-type.>
    **Request Payload**

```json
    {

    "user_account":
        {
            "username":"test1",
            "privilege":"admin",
            "password":"123"
        }
    }
```
* **Response:**
    
    **HTTP Status Code on Success** - 201 Created
    
    **HTTP Status Code on Failure** - 4xx <string> or 5xx <string>. The response provides details of the error. See Error
Handling.

    **Response Header**
        
    Content Type: application/vnd.com.citrix.cloudbridge.user_account+json

    **Request Payload**

    ```json
    {

    "user_account":
        {
            "username":"test1",
            "privilege":"admin",
                    }
    }
    ```
### Retrieving SD-WAN WANOP Resource Details

Resource details can be obtained as follows:

* Retrieving Details of a Single Resource
* Retrieving Details of All Resources

**Note:** All examples in this documentation use the *"user_account"* resource type.

#### Retrieving Details of a Single Resource

The request and response formats to get the details of a single resource. The URL must
specify the type and name of the resource to be retrieved. The request header must
provide the base64 encoded username and password.

* **Request:**

    **HTTP Method** - GET 

    **URL** - https://<cb_ip>/cb/nitro/v1/config/user_account/test1

    **Request Headers**

         Authorization: Basic <base64 encoded(username:password)>
         Content-Type: <Not Required. Ignored if given.
         Accept: <Must either be */* or application/
         vnd.com.citrix.cloudbridge.user_account+json.>

* **Response**

    **HTTP Status Code on Success** -  200 OK
   
    **HTTP Status Code on Failure** - 4xx <string> or 5xx <string>. The response provides details of the error. See Error
Handling.

    **Response Header**
    
        Content-Type: application/
        vnd.com.citrix.cloudbridge.user_account+json

    **Reponse Payload**
     ```json
    {

    "user_account":
        {
            "username":"test1",
            "privilege":"admin",
                    }
    }
    ```
    #### Retrieving Details of All Resources
    The request and response formats to get the details of all resources of a specific
resource type. The URL must specify the type of the resource to be retrieved. The
request header must provide the base64 encoded username and password.

 * **Request:**

 
    **HTTP Method** - GET 

    **URL** - https://<cb_ip>/cb/nitro/v1/config/user_account

    **Request Headers**

         Authorization: Basic <base64 encoded(username:password)>
         Content-Type: <Not Required. Ignored if given.
         Accept: <Must either be */* or application/
         vnd.com.citrix.cloudbridge.user_account_list+json.>

* **Response**

    **HTTP Status Code on Success** -  200 OK
   
    **HTTP Status Code on Failure** - 4xx <string> or 5xx <string>. The response provides details of the error. See Error
Handling.

    **Response Header**
    
        Content-Type: application/
        vnd.com.citrix.cloudbridge.user_account_list+json

    **Reponse Payload**
     ```json
    {

    "user_account":
       [
            {
             "username":"test1",
             "privilege":"admin",
            },
            { 
             "username":"test2",
             "privilege":"admin"
            }
       ]
    }
    ```
### Updating a SD-WAN WANOP Resource
The request and response formats to update a single resource. The URL must specify
the type and name of the resource to be modified. The request header must provide
the base64 encoded username and password.

**Note:** The examples in this documentation use the "user_account" resource type.

* **Request:**

     **HTTP Method** - PUT 

    **URL** - https://<cb_ip>/cb/nitro/v1/config/user_account/test1

    **Request Headers**

         Authorization: Basic <base64 encoded(username:password)>
         Content-Type: application/
         vnd.com.citrix.cloudbridge.user_account+json
         Accept: <Optional but validated if given. Can either  be*/* or same as the content-type.>
    **Request Payload**
     ```json
    {

    "user_account":
    
        {
          "privilege":"admin",
          "password":"123",
        }
    }
    ```
* **Response**

    **HTTP Status Code on Success** -  200 OK
   
    **HTTP Status Code on Failure** - 4xx <string> or 5xx <string>. The response provides details of the error. See Error
Handling.

    **Response Header**
    
        Content-Type: application/
        vnd.com.citrix.cloudbridge.user_account+json

    **Reponse Payload**
     ```json
    {

    "user_account":
        {
         "username":"test1",
         "privilege":"admin",
        }
    }
    ```

### Deleting a SD-WAN WANOP Resource
The request and response formats to delete a single resource. The resource to be
deleted must be specified in the URL. The request header must provide the base64
encoded username and password.

**Note:** The examples in this documentation use the "user_account" resource type.

* **Request:**

     **HTTP Method** - DELETE 

    **URL** - https://<cb_ip>/cb/nitro/v1/config/user_account/test1

    **Request Headers**

         Authorization: Basic <base64 encoded(username:password)>
         
   
* **Response**

    **HTTP Status Code on Success** -  200 OK
   
    **HTTP Status Code on Failure** - 4xx <string> or 5xx <string>. The response provides details of the error. See Error
Handling.

## Usage Scenarios
The above sections explain basic usage of SD-WAN WANOP NITRO API. Here, we document
some scenarios that you might come across while using NITRO.

**Note:** More scenarios will be incrementally added.
### Adding SNMP Users

SNMP users must be associated with a SNMP view. Therefore, first check if the required
SNMP view is already available and then add the SNMP user.

1. Get the list of configured SNMP views.

* **Request:**

     **HTTP Method** - GET 

    **URL** - https://<cb_ip>/cb/nitro/v1/config/snmp_view

    **Request Headers**

         Authorization: Basic <base64 encoded(username:password)>
         
   
* **Response**

    **HTTP Status Code on Success** -  200 OK
   
    **HTTP Status Code on Failure** - 4xx <string> or 5xx <string>. The response provides details of the error. See Error
Handling.

  **Response Header**
    
        Content-Type: application/
        vnd.com.citrix.cloudbridge.snmp_view_list+json

    **Reponse Payload**
     ```json
    {

    "snmp view":
        [
         ...
         ...
        ]
    }
    ```
    **Note:** If the required SNMP view is available in the response payload, then
skip to step 3. Else, add the required SNMP as shown in step 2.

2. Add the required SNMP view.
* **Request:**

     **HTTP Method** - POST 

    **URL** - https://<cb_ip>/cb/nitro/v1/config/snmp_view

    **Request Headers**

         Authorization: Basic <base64 encoded(username:password)>
         Content-Type: application/
         vnd.com.citrix.cloudbridge.snmp_view+json
    **Request Payload**
     ```json
    {

    "snmp_view":
    
        {
          "name":"view1",
          "subtree":"1.1",
          "include":"true"
        }
    }
    ```
* **Response**

    **HTTP Status Code on Success** -  201 Created
   
    **HTTP Status Code on Failure** - 4xx <string> or 5xx <string>. The response provides details of the error. See
Error Handling.

3. Add the SNMP user.
* **Request:**

     **HTTP Method** - POST 

    **URL** - https://<cb_ip>/cb/nitro/v1/config/snmp_user

    **Request Headers**

         Authorization: Basic <base64 encoded(username:password)>
         Content-Type: application/
         vnd.com.citrix.cloudbridge.snmp_user+json
    **Request Payload**
     ```json
    {

    "snmp_view":
    
        {
          "username":"snmp_user1",
          "authprotocol":"MD5",
          "authpassword":"password",
          "viewname":"view1"
        }
    }
    ```
* **Response**

    **HTTP Status Code on Success** -  201 Created
   
    **HTTP Status Code on Failure** - 4xx <string> or 5xx <string>. The response provides details of the error. See
Error Handling.

### Enabling SNMP on the SD-WAN WANOP Appliance
To enable SNMP on the SD-WAN WANOP appliance, you must simply set the status of the
snmp object to true. Optionally, you can first check if SNMP is already enabled.
1. Get status of SNMP.
* **Request:**

     **HTTP Method** - GET 

    **URL** - https://<cb_ip>/cb/nitro/v1/config/snmp

    **Request Headers**

         Authorization: Basic <base64 encoded(username:password)>
         
   
* **Response**

    **HTTP Status Code on Success** -  200 OK
   
    **HTTP Status Code on Failure** - 4xx <string> or 5xx <string>. The response provides details of the error. See Error
Handling.

  **Response Header**
    
        Content-Type: application/
        vnd.com.citrix.cloudbridge.snmp+json

    **Reponse Payload**
     ```json
    {

    "snmp":
        {
        "status":"false"
        }
    }
    ```
    **Note:** The "status=false" value in the response payload indicates that SNMP is
not enabled.
2. Enable SNMP.
* **Request:**

     **HTTP Method** - PUT 

    **URL** - https://<cb_ip>/cb/nitro/v1/config/snmp

    **Request Headers**

         Authorization: Basic <base64 encoded(username:password)>
         Content-Type: application/
         vnd.com.citrix.cloudbridge.snmp+json
    **Request Payload**
     ```json
    {

    "snmp":
    
        {
          "status":"true",
        }
    }
    ```
* **Response**

    **HTTP Status Code on Success** -  200 OK
   
    **HTTP Status Code on Failure** - 4xx <string> or 5xx <string>. The response provides details of the error. See
Error Handling.


### Creating a Service Class
To add a service class on the SD-WAN WANOP appliance, you must use the "service_class"
object.

1. Add a new service class named SC1.
* **Request:**

     **HTTP Method** - POST 

    **URL** - https://<cb_ip>/cb/nitro/v1/config/service_class

    **Request Headers**

        Authorization: Basic <base64 encoded(username:password)>
        Content-Type: application/
        vnd.com.citrix.cloudbridge.service_class+json
    **Request Payload**
     ```json
    {

    "service_class":
    {
        "classname":"SC1",
        "accelerationpolicy":"disk",
        "qospolicy":"Very High Priority Traffic",
        "enabled":"true",
        "filterrules":
        [
            {
                "applications":
                [
                    {
                        "appname":"UDP"
                    },
                    {
                        "appname":"TCP"
                    }
                ]
            }
        ]
    }
    }
    ```     
   
* **Response**

    **HTTP Status Code on Success** -  201 Created
   
    **HTTP Status Code on Failure** - 4xx <string> or 5xx <string>. The response provides details of the error. See Error
Handling.

    **Response Header**
    
        Content-Type: application/
        vnd.com.citrix.cloudbridge.service_class+json

    **Reponse Payload**
     ```json
    {

        "service_class":
        {
         ...
         ...
        }
    }
    ```
2. Modify the newly created service class SC1 by specifying the required changes. This
example shows the modification of accelerationpolicy to memory, qospolicy to Very
Low Priority, and add some filter rules.
* **Request:**

     **HTTP Method** - PUT

    **URL** - https://<cb_ip>/cb/nitro/v1/config/service_class/SC1

    **Request Headers**

        Authorization: Basic <base64 encoded(username:password)>
        Content-Type: application/
        vnd.com.citrix.cloudbridge.service_class+json
    **Request Payload**
     ```json
    {

     "service_class":
    {
        "accelerationpolicy":"memory",
        "qospolicy":"Very Low Priority Traffic",
        "filterrules":
        [
            {
                "srcipaddresses":
                [
                    {
                        "srcipaddress":
                            {
                                "ipaddressmask":"172.16.1.0/24",
                                "rangetype":"ipmask"
                            }
                    },
                    {
                        "srcipaddress":
                            {
                                "left":"172.16.1.10",
                                "right":"172.16.1.20",
                                "rangetype":"hyphen seperated"
                            },
                            "excluded":"true"
                    }
                ]
            }
    ]
    }
    }
    ```     
   
* **Response**

    **HTTP Status Code on Success** -  200 OK
   
    **HTTP Status Code on Failure** - 4xx <string> or 5xx <string>. The response provides details of the error. See Error
Handling.

    **Response Header**
    
        Content-Type: application/
        vnd.com.citrix.cloudbridge.service_class+json

    **Reponse Payload**
     ```json
    {

        "service_class":
        {
         ...
         ...
        }
    }
    ```
## Error Handling
In case of a failed request, NITRO provides the required information through the
response.

* Error in a Single Resource Operation
* Warnings

### Error in a Single Resource Operation

The response for an erroneous request is as follows:

* **Header**.

    HTTP status: <appropriate error status>
    
    Content-Type: application/vnd.com.citrix.cloudbridge.error+json 

* **Payload**.

        {
            "errorcode":<integer>,
            "message":<string>,
            "severity":"ERROR"
        }

### Warnings

When an operation takes some time to execute, SD-WAN WANOP NITRO provides an interim
response that indicates the process is in operation. This is shown as a warning.

* **Header**.

    HTTP status: 202
    
    Content-Type: application/vnd.com.citrix.cloudbridge.warning+json

* **Payload**.

        {
            "errorcode":<integer>,
            "message":"Operation in progress",
            "severity":"WARNING"
        }
