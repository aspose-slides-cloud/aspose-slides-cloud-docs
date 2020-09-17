---
title: "Read TextItems from a PowerPoint Presentation"
type: docs
url: /read-textitems-from-a-powerpoint-presentation/
weight: 10
---

## **Introduction**
Aspose.Slides Cloud lets you easily read Text items from a PowerPoint Presentation. Aspose.Slides Cloud provides REST interfaces for reading items from a individual slide or from a presentation as whole
### **API Information**

|**API**|**Type**|**Description**|**Swagger Link**|
| :- | :- | :- | :- |
|/slides/{name}/textItems|GET|Read TextItems from a PowerPoint Presentation|[GetSlidesPresentationTextItems](https://apireference.aspose.cloud/slides/#/Text/GetSlidesPresentationTextItems)|
|/slides/{name}/slides/{slideIndex}/textItems|GET|Read TextItems from a slide within a PowerPoint Presentation|[GetSlidesSlideTextItems](https://apireference.aspose.cloud/slides/#/Text/GetSlidesSlideTextItems)|
### **cURL Examples**
{{% alert color="primary" %}} 

You need to get the Authentication Token before using these resources

**Get Authentication Token**

```java

curl -v "https://api.aspose.cloud/connect/token" -X POST -d "grant\_type=client\_credentials&client\_id=78946fb4-3bd4-4d3e-b309-f9e2ff9ac6f9&client\_secret=b125f13bf6b76ed81ee990142d841195" -H "Content-Type: application/x-www-form-urlencoded" -H "Accept: application/json" 

```

{{% /alert %}} 
#### **Reading TextItems from a Presentation**
{{< tabs tabTotal="2" tabID="2" tabName1="Request" tabName2="Response" >}}

{{< tab tabNum="1" >}}

```java

curl  -v -X GET "https://api.aspose.cloud/v3.0/slides/destination.pptx/textItems" -H "Content-Type: application/json" -H "Authorization: Bearer eyJhbGciOiJSUzI1NiIsInR5cCI6IkpXVCJ9.eyJuYmYiOjE1NjAwMzA4ODMsImV4cCI6MTU2MDExNzI4MywiaXNzIjoiaHR0cHM6Ly9hcGkuYXNwb3NlLmNsb3VkIiwiYXVkIjpbImh0dHBzOi8vYXBpLmFzcG9zZS5jbG91ZC9yZXNvdXJjZXMiLCJhcGkucGxhdGZvcm0iLCJhcGkucHJvZHVjdHMiXSwiY2xpZW50X2lkIjoiNzg5NDZmYjQtM2JkNC00ZDNlLWIzMDktZjllMmZmOWFjNmY5Iiwic2NvcGUiOlsiYXBpLnBsYXRmb3JtIiwiYXBpLnByb2R1Y3RzIl19.bhURwSdcASMrRj4ukvG5rWTT\_O2JpzVKH436ekU1CW6ZO7wOqGnE8wtkMdq6oivVzazs8xwbeuJmluFpHLNBco7A0vU56\_UXZ5cIsfNCIpTOp6e\_lmeHYgOD1rnW8f6y9jWLRoerup2vzqppjbF-8KXZ2HgCOXpos4lzy7GLqWmElW9TGd2uOd3cFEu1rXmkiJzuyjEi1dFdZtvRPvNyqon5R9ZS5rxQ09GhaiRA6DW4HwFTS-jTAPQo0QGfv87b4Gg\_DvnUu\_JjWlAhIeqWIM72-xmvFQ\_20mk-s6H7foiyvJSC65w-XN5AqUyAyE8rAZduIwcS7BuYiQuOqqen4w" --ssl-no-revoke

```

{{< /tab >}}

{{< tab tabNum="2" >}}

```java

{

   "items":[

      {

         "uri":{

            "href":"https://api.aspose.cloud/v3.0/slides/destination.pptx/slides/1/shapes/1",

            "relation":"parent"

         },

         "text":"This is a slide"

      },

      {

         "uri":{

            "href":"https://api.aspose.cloud/v3.0/slides/destination.pptx/slides/1/shapes/2",

            "relation":"parent"

         },

         "text":"test"

      },

      {

         "uri":{

            "href":"https://api.aspose.cloud/v3.0/slides/destination.pptx/slides/2/shapes/1",

            "relation":"parent"

         },

         "text":"This is a slide"

      },

      {

         "uri":{

            "href":"https://api.aspose.cloud/v3.0/slides/destination.pptx/slides/2/shapes/2",

            "relation":"parent"

         },

         "text":"test"

      }

   ],

   "selfUri":{

      "href":"https://api.aspose.cloud/v3.0/slides/destination.pptx/textItems",

      "relation":"self"

   }

}

```

{{< /tab >}}

{{< /tabs >}}
#### **Reading TextItems from a Slide**
{{< tabs tabTotal="2" tabID="5" tabName1="Request" tabName2="Response" >}}

{{< tab tabNum="1" >}}

```java

curl  -v -X GET "https://api.aspose.cloud/v3.0/slides/destination.pptx/slides/1/textItems" -H "Content-Type: application/json" -H "Authorization: Bearer eyJhbGciOiJSUzI1NiIsInR5cCI6IkpXVCJ9.eyJuYmYiOjE1NjAwMzA4ODMsImV4cCI6MTU2MDExNzI4MywiaXNzIjoiaHR0cHM6Ly9hcGkuYXNwb3NlLmNsb3VkIiwiYXVkIjpbImh0dHBzOi8vYXBpLmFzcG9zZS5jbG91ZC9yZXNvdXJjZXMiLCJhcGkucGxhdGZvcm0iLCJhcGkucHJvZHVjdHMiXSwiY2xpZW50X2lkIjoiNzg5NDZmYjQtM2JkNC00ZDNlLWIzMDktZjllMmZmOWFjNmY5Iiwic2NvcGUiOlsiYXBpLnBsYXRmb3JtIiwiYXBpLnByb2R1Y3RzIl19.bhURwSdcASMrRj4ukvG5rWTT\_O2JpzVKH436ekU1CW6ZO7wOqGnE8wtkMdq6oivVzazs8xwbeuJmluFpHLNBco7A0vU56\_UXZ5cIsfNCIpTOp6e\_lmeHYgOD1rnW8f6y9jWLRoerup2vzqppjbF-8KXZ2HgCOXpos4lzy7GLqWmElW9TGd2uOd3cFEu1rXmkiJzuyjEi1dFdZtvRPvNyqon5R9ZS5rxQ09GhaiRA6DW4HwFTS-jTAPQo0QGfv87b4Gg\_DvnUu\_JjWlAhIeqWIM72-xmvFQ\_20mk-s6H7foiyvJSC65w-XN5AqUyAyE8rAZduIwcS7BuYiQuOqqen4w" --ssl-no-revoke

```

{{< /tab >}}

{{< tab tabNum="2" >}}

```java

 {

   "items":[

      {

         "uri":{

            "href":"https://api.aspose.cloud/v3.0/slides/destination.pptx/slides/1/shapes/1",

            "relation":"parent"

         },

         "text":"This is a slide"

      },

      {

         "uri":{

            "href":"https://api.aspose.cloud/v3.0/slides/destination.pptx/slides/1/shapes/2",

            "relation":"parent"

         },

         "text":"test"

      }

   ],

   "selfUri":{

      "href":"https://api.aspose.cloud/v3.0/slides/destination.pptx/slides/1/textItems",

      "relation":"self"

   }

}

```





{{< /tab >}}

{{< /tabs >}}
## **SDK Source**
The Aspose.Slides Cloud SDKs can be downloaded from the following page: [Available SDKs](/slides/available-sdks/)
## **SDK Examples**
