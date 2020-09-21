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

We are updating the Author property for the presentation using the following object in the PUT request body

```java

{

  "Name": "Author",

  "Value": "H.G. Wells"

}

```


{{< tabs tabTotal="2" tabID="2" tabName1="Request" tabName2="Response" >}}

{{< tab tabNum="1" >}}

**Create Authentication Header**

```java

curl -v "https://api.aspose.cloud/connect/token" -X POST -d "grant_type=client_credentials&client_id=78946fb4-3bd4-4d3e-b309-f9e2ff9ac6f9&client_secret=b125f13bf6b76ed81ee990142d841195" -H "Content-Type: application/x-www-form-urlencoded" -H "Accept: application/json"

```

```java

curl  -v -X PUT "https://api.aspose.cloud/v3.0/slides/destination.pptx/documentProperties/author" -H "Content-Type: application/json" -H "Authorization: Bearer eyJhbGciOiJSUzI1NiIsInR5cCI6IkpXVCJ9.eyJuYmYiOjE1NjAwMzAxODIsImV4cCI6MTU2MDExNjU4MiwiaXNzIjoiaHR0cHM6Ly9hcGkuYXNwb3NlLmNsb3VkIiwiYXVkIjpbImh0dHBzOi8vYXBpLmFzcG9zZS5jbG91ZC9yZXNvdXJjZXMiLCJhcGkucGxhdGZvcm0iLCJhcGkucHJvZHVjdHMiXSwiY2xpZW50X2lkIjoiNzg5NDZmYjQtM2JkNC00ZDNlLWIzMDktZjllMmZmOWFjNmY5Iiwic2NvcGUiOlsiYXBpLnBsYXRmb3JtIiwiYXBpLnByb2R1Y3RzIl19.B7t3H8soqjjEpA9L66rUtVpD8Z5cOETu_A0bzTRAzF2RVa5zA9OvOvErrjkTYF_6mqyM_-1bzH2ARAkPPS14FpDclZuZ3NTpuzJjMbE0Gt02OMGFyXcPIuhpah5Y_yxb7pLB0MUvn9U2HDdAGmRqxusGzaoacQhmHYBH6Y39NAkomTp1J6Qu-FHRC19JER-Y_WdXqGRYbi_IULgGxZ9jaATjvzFaG27ao6UKzem_SOD7mauudJOaLMQ5n17_Jjj3FGISuxMdiyjf3NEMGBK9pBcwtzrlBJvcW1YsFU5v6tujGFOaDIuTGGQYAjgGB2I3VPjjGxmguTxjT9Xm6mORZw" --ssl-no-revoke -d "{'Name': 'Author', 'Value': 'H.G. Wells'}"

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
The Aspose.Slide Cloud SDKs can be downloaded from the following page: [Available SDKs](/slides/available-sdks/)
## **SDK Examples**
{{< tabs tabTotal="9" tabID="5" tabName1="C#" tabName2="Java" tabName3="PHP" tabName4="Ruby" tabName5="Python" tabName6="Node.js" tabName7="Android" tabName8="C++" tabName9="Perl" >}}

{{< tab tabNum="1" >}}

{{< gist "" "a41a3c7c75241129b94faf7179d42527" "GetSlidesThemeFonts.cs" >}}

{{< /tab >}}

{{< tab tabNum="2" >}}

{{< gist "" "17b08f624ccca40e351e7204e318237e" "GetSlidesThemeFonts.java" >}}

{{< /tab >}}

{{< tab tabNum="3" >}}

{{< gist "" "67ba57c9ba0134d2e8c8ed2132d6515f" "GetSlidesThemeFonts.php" >}}

{{< /tab >}}

{{< tab tabNum="4" >}}

{{< gist "" "a41a3c7c75241129b94faf7179d42527" "Coming_Soon.txt" >}}

{{< /tab >}}

{{< tab tabNum="5" >}}

{{< gist "" "a41a3c7c75241129b94faf7179d42527" "Coming_Soon.txt" >}}

{{< /tab >}}

{{< tab tabNum="6" >}}

{{< gist "" "bc650902bdc45144b1727d329023dcba" "GetSlidesThemeFonts.js" >}}

{{< /tab >}}

{{< tab tabNum="7" >}}

{{< gist "" "2b52dabd204b301389d1f4234e9bb0d5" "GetSlidesThemeFonts.java" >}}

{{< /tab >}}

{{< tab tabNum="8" >}}

{{< gist "" "a41a3c7c75241129b94faf7179d42527" "Coming_Soon.txt" >}}

{{< /tab >}}

{{< tab tabNum="9" >}}

{{< gist "" "a41a3c7c75241129b94faf7179d42527" "Coming_Soon.txt" >}}

{{< /tab >}}

{{< /tabs >}}
