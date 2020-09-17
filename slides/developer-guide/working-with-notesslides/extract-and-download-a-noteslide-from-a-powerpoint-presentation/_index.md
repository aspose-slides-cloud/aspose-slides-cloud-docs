---
title: "Extract and Download a NoteSlide from a PowerPoint Presentation"
type: docs
url: /extract-and-download-a-noteslide-from-a-powerpoint-presentation/
weight: 20
---

## **Introduction**
Aspose.Slides Cloud API allows you to export and download a NoteSlide to a desired format
### **API Information**

|**API**|**Type**|**Description**|**Swagger Link**|
| :- | :- | :- | :- |
|/slides/{name}/slides/{slideIndex}/notesSlide/{format}|GET|Download a NoteSlide in a desired format|[GetNotesSlideWithFormat](https://apireference.aspose.cloud/slides/#/NotesSlide/GetNotesSlideWithFormat)|
### **cURL Example**
{{% alert color="primary" %}} 

For available formats to export a NoteSlide in please visit [Supported Document Formats](/slides/supported-document-formats/) section of our documentation guide

{{% /alert %}} 

{{< tabs tabTotal="1" tabID="1" tabName1="Request" >}}

{{< tab tabNum="1" >}}

**Create Request Token**

```java

curl -v "https://api.aspose.cloud/connect/token" -X POST -d "grant\_type=client\_credentials&client\_id=[]&client\_secret=[]" -H "Content-Type: application/x-www-form-urlencoded" -H "Accept: application/json"

```

```java

curl  -v -X GET "https://api.aspose.cloud/v3.0/slides/presentation\_images.pptx/slides/1/notesSlide/jpeg" -H "Content-Type: application/json" -H "Authorization: Bearer eyJhbGciOiJSUzI1NiIsInR5cCI6IkpXVCJ9.eyJuYmYiOjE1NjAwOTI3OTcsImV4cCI6MTU2MDE3OTE5NywiaXNzIjoiaHR0cHM6Ly9hcGkuYXNwb3NlLmNsb3VkIiwiYXVkIjpbImh0dHBzOi8vYXBpLmFzcG9zZS5jbG91ZC9yZXNvdXJjZXMiLCJhcGkucGxhdGZvcm0iLCJhcGkucHJvZHVjdHMiXSwiY2xpZW50X2lkIjoiNzg5NDZmYjQtM2JkNC00ZDNlLWIzMDktZjllMmZmOWFjNmY5Iiwic2NvcGUiOlsiYXBpLnBsYXRmb3JtIiwiYXBpLnByb2R1Y3RzIl19.rFS4KehYAg1yOVGmteeinIh-AFq7nVEmtUr\_cDltIfk0iN0JJJ3o6TK1StpnItAAqlkb\_QtF0WcY5D8NCjeyTVKL1oewdIshjjODoPEN1tmCsRXceHGYTG5f--B8sWrMuZtOqSzlbr-x3\_Mat9Fy7xcNbS6nNNmBv7mo3suRDF4xdUZWdIY7bO6yBptc-qyhIFb0olNMxdeAZPsN8sPLW0XIbEGf8CaE16p9al\_O5SjWLtEZT7APuvDesJwWYOSPtG6hCsXtHItphKDAcMULEnqJ-QW\_QpzBxybTnQ1VNzundQWOYM\_viYzU8hOlf6VTE4YQKyCmgz72Ena8KZx0VA" --ssl-no-revoke -d "{'text':'This was updated'}"

```

{{< /tab >}}

{{< /tabs >}}
## **SDKs**
Using an SDK (API client) is the quickest way for a developer to speed up the development. An SDK takes care of a lot of low-level details of making requests and handling responses and lets you focus on writing code specific to your particular project. Check out our [GitHub repository](https://github.com/aspose-slides-cloud) for a complete list of Aspose.Slides Cloud SDKs along with working examples, to get you started in no time. Please check [Available SDKs](/slides/available-sdks/) article to learn how to add an SDK to your project.
### **SDK Examples**
{{< tabs tabTotal="9" tabID="4" tabName1="C#" tabName2="Java" tabName3="PHP" tabName4="Ruby" tabName5="Python" tabName6="Node.js" tabName7="Android" tabName8="C++" tabName9="Perl" >}}

{{< tab tabNum="1" >}}

{{< gist "" "a41a3c7c75241129b94faf7179d42527" "GetNotesSlides.cs" >}}

{{< /tab >}}

{{< tab tabNum="2" >}}

{{< gist "" "17b08f624ccca40e351e7204e318237e" "GetNotesSlides.java" >}}

{{< /tab >}}

{{< tab tabNum="3" >}}

{{< gist "" "67ba57c9ba0134d2e8c8ed2132d6515f" "GetNotesSlides.php" >}}

{{< /tab >}}

{{< tab tabNum="4" >}}

{{< gist "" "a41a3c7c75241129b94faf7179d42527" "Coming\_Soon.txt" >}}

{{< /tab >}}

{{< tab tabNum="5" >}}

{{< gist "" "a41a3c7c75241129b94faf7179d42527" "Coming\_Soon.txt" >}}

{{< /tab >}}

{{< tab tabNum="6" >}}

{{< gist "" "bc650902bdc45144b1727d329023dcba" "GetNotesSlides.js" >}}

{{< /tab >}}

{{< tab tabNum="7" >}}

{{< gist "" "2b52dabd204b301389d1f4234e9bb0d5" "GetNotesSlides.java" >}}

{{< /tab >}}

{{< tab tabNum="8" >}}

{{< gist "" "a41a3c7c75241129b94faf7179d42527" "Coming\_Soon.txt" >}}

{{< /tab >}}

{{< tab tabNum="9" >}}

{{< gist "" "a41a3c7c75241129b94faf7179d42527" "Coming\_Soon.txt" >}}

{{< /tab >}}

{{< /tabs >}}
### **SDK Source**
The Aspose Cloud SDK's can be downloaded from the following page: [Available SDK's](/slides/available-sdks/)
