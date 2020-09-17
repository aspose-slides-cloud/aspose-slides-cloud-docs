---
title: "Read NoteSlide information from a PowerPoint Presentation"
type: docs
url: /read-noteslide-information-from-a-powerpoint-presentation/
weight: 30
---

## **Introduction**
Aspose.Slides Cloud API allows you to read NoteSlide information from a PowerPoint Presentation. 
### **API Information**

|**API**|**Type**|**Description**|**Swagger Link**|
| :- | :- | :- | :- |
|/slides/{name}/slides/{slideIndex}/notesSlide|GET|Read NoteSlide information from a PowerPoint Presentation|[GetNotesSlide](https://apireference.aspose.cloud/slides/#/NotesSlide/GetNotesSlide)|
### **cURL Example**
{{< tabs tabTotal="2" tabID="1" tabName1="Request" tabName2="Response" >}}

{{< tab tabNum="1" >}}

**Create Request Token**

```java

curl -v "https://api.aspose.cloud/connect/token" -X POST -d "grant_type=client_credentials&client_id=78946fb4-3bd4-4d3e-b309-f9e2ff9ac6f9&client_secret=b125f13bf6b76ed81ee990142d841195" -H "Content-Type: application/x-www-form-urlencoded" -H "Accept: application/json"

```

```java

curl  -v -X GET "https://api.aspose.cloud/v3.0/slides/presentation_images.pptx/slides/1/notesSlide/" -H "Content-Type: application/json" -H "Authorization: Bearer eyJhbGciOiJSUzI1NiIsInR5cCI6IkpXVCJ9.eyJuYmYiOjE1NjAwOTI0MzUsImV4cCI6MTU2MDE3ODgzNSwiaXNzIjoiaHR0cHM6Ly9hcGkuYXNwb3NlLmNsb3VkIiwiYXVkIjpbImh0dHBzOi8vYXBpLmFzcG9zZS5jbG91ZC9yZXNvdXJjZXMiLCJhcGkucGxhdGZvcm0iLCJhcGkucHJvZHVjdHMiXSwiY2xpZW50X2lkIjoiNzg5NDZmYjQtM2JkNC00ZDNlLWIzMDktZjllMmZmOWFjNmY5Iiwic2NvcGUiOlsiYXBpLnBsYXRmb3JtIiwiYXBpLnByb2R1Y3RzIl19.B-97utZQ3cy0KUQCnKt_bB_3V5Qov8RYt2gTDT9heSEuqNBgDOHDjzyWEGlN8NufcXWVELQ53ti2Xu9f_f7QXeicMf6Kvh1fLrlr7W0_9SG5tDoSO_raAE8ZMzpxmXJBH6mdqUBsG2aTlsd06BPT-evjmakNn57PjyX5AAGN2NXLMCuzdx_wZvCKUcgiziSq5tlO1ohNAK7UI7P0JEA2_R_jd4xTxtE1sO--eioNNJoS5JEQtgbh7XlF-SG4EnLk5nhjl0dlNRKngQKgjUSekLSO45rdyzOIIBO1ssUMQqmBm0CgNmUGrwXv_ruq7HATsKYNb-1IGMGB-s2SVBAuuA" --ssl-no-revoke

```

{{< /tab >}}

{{< tab tabNum="2" >}}

```java

{

   "text":"This is first note",

   "shapes":{

      "uri":{

         "href":"https://api.aspose.cloud/v3.0/slides/presentation_images.pptx/slides/1/notesSlide/shapes",

         "relation":"self"

      }

   },

   "selfUri":{

      "href":"https://api.aspose.cloud/v3.0/slides/presentation_images.pptx/slides/1/notesSlide",

      "relation":"self"

   }

}

```

{{< /tab >}}

{{< /tabs >}}
## **SDKs**
Using an SDK (API client) is the quickest way for a developer to speed up the development. An SDK takes care of a lot of low-level details of making requests and handling responses and lets you focus on writing code specific to your particular project. Check out our [GitHub repository](https://github.com/aspose-slides-cloud) for a complete list of Aspose.Slides Cloud SDKs along with working examples, to get you started in no time. Please check [Available SDKs](/slides/available-sdks/) article to learn how to add an SDK to your project.
### **SDK Examples**
{{< tabs tabTotal="9" tabID="5" tabName1="C#" tabName2="Java" tabName3="PHP" tabName4="Ruby" tabName5="Python" tabName6="Node.js" tabName7="Android" tabName8="C++" tabName9="Perl" >}}

{{< tab tabNum="1" >}}

{{< gist "" "a41a3c7c75241129b94faf7179d42527" "GetNotesSlideWithFormats.cs" >}}

{{< /tab >}}

{{< tab tabNum="2" >}}

{{< gist "" "17b08f624ccca40e351e7204e318237e" "GetNotesSlideWithFormats.java" >}}

{{< /tab >}}

{{< tab tabNum="3" >}}

{{< gist "" "67ba57c9ba0134d2e8c8ed2132d6515f" "GetNotesSlideWithFormats.php" >}}

{{< /tab >}}

{{< tab tabNum="4" >}}

{{< gist "" "a41a3c7c75241129b94faf7179d42527" "Coming_Soon.txt" >}}

{{< /tab >}}

{{< tab tabNum="5" >}}

{{< gist "" "a41a3c7c75241129b94faf7179d42527" "Coming_Soon.txt" >}}

{{< /tab >}}

{{< tab tabNum="6" >}}

{{< gist "" "bc650902bdc45144b1727d329023dcba" "GetNotesSlideWithFormats.js" >}}

{{< /tab >}}

{{< tab tabNum="7" >}}

{{< gist "" "2b52dabd204b301389d1f4234e9bb0d5" "GetNotesSlideWithFormats.java" >}}

{{< /tab >}}

{{< tab tabNum="8" >}}

{{< gist "" "a41a3c7c75241129b94faf7179d42527" "Coming_Soon.txt" >}}

{{< /tab >}}

{{< tab tabNum="9" >}}

{{< gist "" "a41a3c7c75241129b94faf7179d42527" "Coming_Soon.txt" >}}

{{< /tab >}}

{{< /tabs >}}
### **SDK Source**
The Aspose Cloud SDK's can be downloaded from the following page: [Available SDK's](/slides/available-sdks/)
