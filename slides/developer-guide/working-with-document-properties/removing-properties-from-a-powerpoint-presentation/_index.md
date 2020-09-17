---
title: "Removing properties from a PowerPoint Presentation"
type: docs
url: /removing-properties-from-a-powerpoint-presentation/
weight: 40
---

## **Introduction**
Aspose.Slides Cloud allows you remove one or all properties from PowerPoint Presentation
### **API Information**

|**API**|**Type**|**Description**|**Swagger Link**|
| :- | :- | :- | :- |
|/slides/{name}/documentproperties|DELETE|Wipe a document clean of all properties|[DeleteSlidesDocumentProperties](https://apireference.aspose.cloud/slides/#/Properties/DeleteSlidesDocumentProperties)|
|/slides/{name}/documentproperties/{propertyName}|DELETE|Delete a named property|[DeleteSlidesDocumentProperty](https://apireference.aspose.cloud/slides/#/Properties/DeleteSlidesDocumentProperty)|

cURL Example

{{< tabs tabTotal="2" tabID="1" tabName1="Request" tabName2="Response" >}}

{{< tab tabNum="1" >}}

**Create Authentication Token**

```java

curl -v "https://api.aspose.cloud/connect/token" -X POST -d "grant\_type=client\_credentials&client\_id=78946fb4-3bd4-4d3e-b309-f9e2ff9ac6f9&client\_secret=b125f13bf6b76ed81ee990142d841195" -H "Content-Type: application/x-www-form-urlencoded" -H "Accept: application/json"

```

```java

curl  -v -X DELETE "https://api.aspose.cloud/v3.0/slides/destination.pptx/documentProperties/author" -H "Content-Type: application/json" -H "Authorization: Bearer eyJhbGciOiJSUzI1NiIsInR5cCI6IkpXVCJ9.eyJuYmYiOjE1NjAwMzA4ODMsImV4cCI6MTU2MDExNzI4MywiaXNzIjoiaHR0cHM6Ly9hcGkuYXNwb3NlLmNsb3VkIiwiYXVkIjpbImh0dHBzOi8vYXBpLmFzcG9zZS5jbG91ZC9yZXNvdXJjZXMiLCJhcGkucGxhdGZvcm0iLCJhcGkucHJvZHVjdHMiXSwiY2xpZW50X2lkIjoiNzg5NDZmYjQtM2JkNC00ZDNlLWIzMDktZjllMmZmOWFjNmY5Iiwic2NvcGUiOlsiYXBpLnBsYXRmb3JtIiwiYXBpLnByb2R1Y3RzIl19.bhURwSdcASMrRj4ukvG5rWTT\_O2JpzVKH436ekU1CW6ZO7wOqGnE8wtkMdq6oivVzazs8xwbeuJmluFpHLNBco7A0vU56\_UXZ5cIsfNCIpTOp6e\_lmeHYgOD1rnW8f6y9jWLRoerup2vzqppjbF-8KXZ2HgCOXpos4lzy7GLqWmElW9TGd2uOd3cFEu1rXmkiJzuyjEi1dFdZtvRPvNyqon5R9ZS5rxQ09GhaiRA6DW4HwFTS-jTAPQo0QGfv87b4Gg\_DvnUu\_JjWlAhIeqWIM72-xmvFQ\_20mk-s6H7foiyvJSC65w-XN5AqUyAyE8rAZduIwcS7BuYiQuOqqen4w" --ssl-no-revoke

```

{{< /tab >}}

{{< tab tabNum="2" >}}

```java

 {

   "list":[

      {

         "name":"Author",

         "value":"XANDER",

         "builtIn":true,

         "selfUri":{

            "href":"https://api.aspose.cloud/v3.0/slides/destination.pptx/documentProperties/Author",

            "relation":"self"

         }

      },

      {

         "name":"Category",

         "value":"",

         "builtIn":true,

         "selfUri":{

            "href":"https://api.aspose.cloud/v3.0/slides/destination.pptx/documentProperties/Category",

            "relation":"self"

         }

      },

      {

         "name":"Comments",

         "value":"",

         "builtIn":true,

         "selfUri":{

            "href":"https://api.aspose.cloud/v3.0/slides/destination.pptx/documentProperties/Comments",

            "relation":"self"

         }

      },

      {

         "name":"Company",

         "value":"",

         "builtIn":true,

         "selfUri":{

            "href":"https://api.aspose.cloud/v3.0/slides/destination.pptx/documentProperties/Company",

            "relation":"self"

         }

      },

      {

         "name":"Keywords",

         "value":"",

         "builtIn":true,

         "selfUri":{

            "href":"https://api.aspose.cloud/v3.0/slides/destination.pptx/documentProperties/Keywords",

            "relation":"self"

         }

      },

      {

         "name":"LastSavedBy",

         "value":"Xamder",

         "builtIn":true,

         "selfUri":{

            "href":"https://api.aspose.cloud/v3.0/slides/destination.pptx/documentProperties/LastSavedBy",

            "relation":"self"

         }

      },

      {

         "name":"Manager",

         "value":"",

         "builtIn":true,

         "selfUri":{

            "href":"https://api.aspose.cloud/v3.0/slides/destination.pptx/documentProperties/Manager",

            "relation":"self"

         }

      },

      {

         "name":"NameOfApplication",

         "value":"Aspose.Slides for .NET",

         "builtIn":true,

         "selfUri":{

            "href":"https://api.aspose.cloud/v3.0/slides/destination.pptx/documentProperties/NameOfApplication",

            "relation":"self"

         }

      },

      {

         "name":"RevisionNumber",

         "value":"4",

         "builtIn":true,

         "selfUri":{

            "href":"https://api.aspose.cloud/v3.0/slides/destination.pptx/documentProperties/RevisionNumber",

            "relation":"self"

         }

      },

      {

         "name":"Subject",

         "value":"",

         "builtIn":true,

         "selfUri":{

            "href":"https://api.aspose.cloud/v3.0/slides/destination.pptx/documentProperties/Subject",

            "relation":"self"

         }

      },

      {

         "name":"Template",

         "value":"",

         "builtIn":true,

         "selfUri":{

            "href":"https://api.aspose.cloud/v3.0/slides/destination.pptx/documentProperties/Template",

            "relation":"self"

         }

      },

      {

         "name":"Title",

         "value":"PowerPoint Presentation",

         "builtIn":true,

         "selfUri":{

            "href":"https://api.aspose.cloud/v3.0/slides/destination.pptx/documentProperties/Title",

            "relation":"self"

         }

      },

      {

         "name":"TotalEditingTime",

         "value":"PT0S",

         "builtIn":true,

         "selfUri":{

            "href":"https://api.aspose.cloud/v3.0/slides/destination.pptx/documentProperties/TotalEditingTime",

            "relation":"self"

         }

      },

      {

         "name":"CreatedTime",

         "value":"2019-03-29T13:21:33Z",

         "builtIn":true,

         "selfUri":{

            "href":"https://api.aspose.cloud/v3.0/slides/destination.pptx/documentProperties/CreatedTime",

            "relation":"self"

         }

      },

      {

         "name":"LastPrinted",

         "value":"0001-01-01T00:00:00Z",

         "builtIn":true,

         "selfUri":{

            "href":"https://api.aspose.cloud/v3.0/slides/destination.pptx/documentProperties/LastPrinted",

            "relation":"self"

         }

      },

      {

         "name":"LastSavedTime",

         "value":"2019-06-08T21:55:50Z",

         "builtIn":true,

         "selfUri":{

            "href":"https://api.aspose.cloud/v3.0/slides/destination.pptx/documentProperties/LastSavedTime",

            "relation":"self"

         }

      },

      {

         "name":"Another Custom Property",

         "value":"Example Value",

         "builtIn":false,

         "selfUri":{

            "href":"https://api.aspose.cloud/v3.0/slides/destination.pptx/documentProperties/Another%20Custom%20Property",

            "relation":"self"

         }

      },

      {

         "name":"Processed By Office",

         "value":"Scotland Team",

         "builtIn":false,

         "selfUri":{

            "href":"https://api.aspose.cloud/v3.0/slides/destination.pptx/documentProperties/Processed%20By%20Office",

            "relation":"self"

         }

      }

   ],

   "selfUri":{

      "href":"https://api.aspose.cloud/v3.0/slides/destination.pptx/documentProperties",

      "relation":"self"

   }

}

```

{{< /tab >}}

{{< /tabs >}}
## **SDK Source**
Aspose.Slides  Cloud SDKs can be downloaded from the following page: [Available SDKs](/slides/available-sdks/)
## **SDK Example**
