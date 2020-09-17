---
title: "Reading Properties from a PowerPoint Presentation"
type: docs
url: /reading-properties-from-a-powerpoint-presentation/
weight: 10
---

## **Introduction**
Aspose.Slides Cloud allows reading of document properties from a PowerPoint Presentation. 
### **API Information**

|**API**|**Type**|**Description**|**Swagger Link**|
| :- | :- | :- | :- |
|/slides/{name}/documentproperties|GET|Read all document properties from a presentation|[GetSlidesDocumentProperties](https://apireference.aspose.cloud/slides/#/Properties/GetSlidesDocumentProperties)|
|/slides/{name}/documentproperties/{propertyName}|GET|Read a document property by name|[GetSlidesDocumentProperty](https://apireference.aspose.cloud/slides/#/Properties/GetSlidesDocumentProperty)|
### **cURL Example**
{{% alert color="primary" %}} 

In this example we are querying about the documents author using the resource **/slides/destination.pptx/documentProperties/Author.** You can read all properties at once using the **/slides/{name}/documentproperties** resource instead

{{% /alert %}} 

{{< tabs tabTotal="2" tabID="1" tabName1="Request" tabName2="Response" >}}

{{< tab tabNum="1" >}}

**Create Authentication Token**

```java

curl -v "https://api.aspose.cloud/oauth2/token" -X POST -d "grant\_type=client\_credentials&client\_id=78946fb4-3bd4-4d3e-b309-f9e2ff9ac6f9&client\_secret=b125f13bf6b76ed81ee990142d84119"-H "Content-Type: application/x-www-form-urlencoded"-H "Accept: application/json"

```

```java

curl  -v -X GET "https://api.aspose.cloud/v3.0/slides/destination.pptx/documentProperties/Author" -H "Content-Type: application/json" -H "Authorization: Bearer eyJhbGciOiJSUzI1NiIsInR5cCI6IkpXVCJ9.eyJuYmYiOjE1NjAwMTkxMzEsImV4cCI6MTU2MDEwNTUzMSwiaXNzIjoiaHR0cHM6Ly9hcGkuYXNwb3NlLmNsb3VkIiwiYXVkIjpbImh0dHBzOi8vYXBpLmFzcG9zZS5jbG91ZC9yZXNvdXJjZXMiLCJhcGkucGxhdGZvcm0iLCJhcGkucHJvZHVjdHMiXSwiY2xpZW50X2lkIjoiNzg5NDZmYjQtM2JkNC00ZDNlLWIzMDktZjllMmZmOWFjNmY5Iiwic2NvcGUiOlsiYXBpLnBsYXRmb3JtIiwiYXBpLnByb2R1Y3RzIl19.PiLqxtzZkOgEOWLVqJS\_kx7lSpBRXloM123sMdCq2flAFv4nkyhXYAHV-3CsDgLCCxKsmfMuB-Ptd1UAOUnTSoe5G7jhF2gdvKhJu1cq7VK7FQko3YSn-z14UAHvrscLrKz0gp3Ikoh1I9m8xkrqMH92dg4yIP95bvIlBRh1HeSvZXKmg-WobbA9tkQFCPzFQwpKo65v4xqg9eXBMkosdi5IvP5XyHqKx2o-5r-64ut9LHv2MGchU72zn3Iz0bL-4luEeNWSKF5Nk-nU82EsxwfVNFzNGaH6J4NrwwRk2HhnOEOEXsuj-pfr1EnMDjvEkoKvY4D6ZZsEoP5lxQr2jw" --ssl-no-revoke

```

{{< /tab >}}

{{< tab tabNum="2" >}}

```java

{

   "name":"Author",

   "value":"Xander Cage",

   "builtIn":true,

   "selfUri":{

      "href":"https://api.aspose.cloud/v3.0/slides/destination.pptx/documentProperties/Author",

      "relation":"self"

   }

}

```

{{< /tab >}}

{{< /tabs >}}


## **SDK Source**
The Aspose.Slide Cloud SDKs can be downloaded from the following page: [Available SDKs](/slides/available-sdks/)
## **SDK Examples**
