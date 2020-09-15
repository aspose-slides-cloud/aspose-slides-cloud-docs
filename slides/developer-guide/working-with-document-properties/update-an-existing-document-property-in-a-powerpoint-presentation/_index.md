---
title: "Update an existing document property in a PowerPoint Presentation"
type: docs
url: /update-an-existing-document-property-in-a-powerpoint-presentation/
weight: 30
---

## **Introduction**
Aspose.Slides allows you to update a document property within a PowerPoint Presentation

{{% alert color="primary" %}} 

Please note that you cannot set values against the **Application** and **Producer** fields, because Aspose Ltd. and Aspose.Slides for Cloud x.x.x will be displayed against these fields.

{{% /alert %}} 
### **API Information**

|**API**|**Type**|**Description**|**Swagger Link**|
| :- | :- | :- | :- |
|/slides/{name}/documentproperties/{propertyName}|PUT|Updates a existing property or creates a new one if it does not exist|[PutSlidesSetDocumentProperty](https://apireference.aspose.cloud/slides/#/Properties/PutSlidesSetDocumentProperty)|
### **cURL Example**
{{% alert color="primary" %}} 

We are updating the Author property for the presentation using the following object in the PUT request body

```java

{

  "Name": "Author",

  "Value": "H.G. Wells"

}

```

{{% /alert %}} 

{{< tabs tabTotal="2" tabID="2" tabName1="Request" tabName2="Response" >}}

{{< tab tabNum="1" >}}

**Create Authentication Header**

```java

curl -v "https://api.aspose.cloud/connect/token" -X POST -d "grant\_type=client\_credentials&client\_id=78946fb4-3bd4-4d3e-b309-f9e2ff9ac6f9&client\_secret=b125f13bf6b76ed81ee990142d841195" -H "Content-Type: application/x-www-form-urlencoded" -H "Accept: application/json"

```

```java

curl  -v -X PUT "https://api.aspose.cloud/v3.0/slides/destination.pptx/documentProperties/author" -H "Content-Type: application/json" -H "Authorization: Bearer eyJhbGciOiJSUzI1NiIsInR5cCI6IkpXVCJ9.eyJuYmYiOjE1NjAwMzAxODIsImV4cCI6MTU2MDExNjU4MiwiaXNzIjoiaHR0cHM6Ly9hcGkuYXNwb3NlLmNsb3VkIiwiYXVkIjpbImh0dHBzOi8vYXBpLmFzcG9zZS5jbG91ZC9yZXNvdXJjZXMiLCJhcGkucGxhdGZvcm0iLCJhcGkucHJvZHVjdHMiXSwiY2xpZW50X2lkIjoiNzg5NDZmYjQtM2JkNC00ZDNlLWIzMDktZjllMmZmOWFjNmY5Iiwic2NvcGUiOlsiYXBpLnBsYXRmb3JtIiwiYXBpLnByb2R1Y3RzIl19.B7t3H8soqjjEpA9L66rUtVpD8Z5cOETu\_A0bzTRAzF2RVa5zA9OvOvErrjkTYF\_6mqyM\_-1bzH2ARAkPPS14FpDclZuZ3NTpuzJjMbE0Gt02OMGFyXcPIuhpah5Y\_yxb7pLB0MUvn9U2HDdAGmRqxusGzaoacQhmHYBH6Y39NAkomTp1J6Qu-FHRC19JER-Y\_WdXqGRYbi\_IULgGxZ9jaATjvzFaG27ao6UKzem\_SOD7mauudJOaLMQ5n17\_Jjj3FGISuxMdiyjf3NEMGBK9pBcwtzrlBJvcW1YsFU5v6tujGFOaDIuTGGQYAjgGB2I3VPjjGxmguTxjT9Xm6mORZw" --ssl-no-revoke -d "{'Name': 'Author', 'Value': 'H.G. Wells'}"

```

{{< /tab >}}

{{< tab tabNum="2" >}}

```java

{

   "name":"author",

   "value":"H.G. Wells",

   "builtIn":false,

   "selfUri":{

      "href":"https://api.aspose.cloud/v3.0/slides/destination.pptx/documentProperties/author",

      "relation":"self"

   }

}

```

{{< /tab >}}

{{< /tabs >}}
## **SDK Source**
The Aspose.Slide Cloud SDKs can be downloaded from the following page: [Available SDKs](/slidescloud/available-sdks/)
## **SDK Examples**
