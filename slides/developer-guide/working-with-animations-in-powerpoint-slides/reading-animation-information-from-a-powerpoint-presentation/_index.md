---
title: "Reading Animation Information from a PowerPoint Presentation"
type: docs
url: /reading-animation-information-from-a-powerpoint-presentation/
weight: 10
---

## **Introduction**
Aspose.Slides Cloud allows you to read information from a Power Point Presentation. 
### **API Information**

|**API**|**Type**|**Description**|**Swagger Link**|
| :- | :- | :- | :- |
|/slides/{name}/slides/{slideIndex}/animation|GET|Get Animation Information from a PowerPoint Slide|[GetSlideAnimation](https://apireference.aspose.cloud/slides/#/Animation/GetSlideAnimation)|
### **cURL Example**
{{< tabs tabTotal="2" tabID="1" tabName1="Request" tabName2="Response" >}}

{{< tab tabNum="1" >}}

**Create Request Token**

```java

curl -v "https://api.aspose.cloud/connect/token" -X POST -d "grant_type=client_credentials&client_id=xxxx&client_secret=xxx-xx" -H "Content-Type: application/x-www-form-urlencoded" -H "Accept: application/json"

```

```java

curl -v -X GET "https://api.aspose.cloud/v3.0/slides/animation.pptx/slides/1/animation" -H "Content-Type:application/json" -H "Authorization: Bearer eyJhbGciOiJSUzI1NiIsInR5cCI6IkpXVCJ9.eyJuYmYiOjE1NjEwNjM0NTAsImV4cCI6MTU2MTE0OTg1MCwiaXNzIjoiaHR0cHM6Ly9hcGkuYXNwb3NlLmNsb3VkIiwiYXVkIjpbImh0dHBzOi8vYXBpLmFzcG9zZS5jbG91ZC9yZXNvdXJjZXMiLCJhcGkucGxhdGZvcm0iLCJhcGkucHJvZHVjdHMiXSwiY2xpZW50X2lkIjoiNzg5NDZmYjQtM2JkNC00ZDNlLWIzMDktZjllMmZmOWFjNmY5Iiwic2NvcGUiOlsiYXBpLnBsYXRmb3JtIiwiYXBpLnByb2R1Y3RzIl19.XURcZFFwPs__A4GHgzncfsCI5_F6R0NIWrTbdGcQqTKBV24jqbQYwe7POYMU8QT3_CKQ9zrlCX47Gtzx3XZ-1LyZAx3v6e6__r7HG9DsVCrzGXxzcIaYBwo9XohkfO5At9XcmXMqw1YoZvWskHUjhIAXzlg6Kt-k1hIPCL-0A1A0WkbdtWOJtWpTEVnIR2kBfXkUcNHLREq3S4JVshLmnjdPF6YViBM5AkV91diC33yj2Fwz-j572SjgwEuHkKNRLTngwsnu9DFEtfiN6bCCPBhulq6XG4DuqLrAtxyodD0Et5Y0YegUHUWOvf4-ZFbUd1ZHzU_rQ06dXzP6SDzMjg" --ssl-no-revoke

```

{{< /tab >}}

{{< tab tabNum="2" >}}

```java

{

   "mainSequence":[

      {

         "type":"Appear",

         "subtype":"None",

         "presetClassType":"Entrance",

         "shapeIndex":1,

         "triggerType":"OnClick",

         "triggerDelayTime":0.0

      },

      {

         "type":"Bounce",

         "subtype":"None",

         "presetClassType":"Entrance",

         "shapeIndex":2,

         "triggerType":"OnClick",

         "triggerDelayTime":0.0

      },

      {

         "type":"Fly",

         "subtype":"Bottom",

         "presetClassType":"Entrance",

         "shapeIndex":3,

         "triggerType":"OnClick",

         "triggerDelayTime":0.0

      }

   ],

   "interactiveSequences":[

      {

         "effects":[

            {

               "type":"Fly",

               "subtype":"Bottom",

               "presetClassType":"Entrance",

               "shapeIndex":5,

               "triggerType":"OnClick",

               "triggerDelayTime":0.0

            }

         ],

         "triggerShapeIndex":1

      }

   ],

   "selfUri":{

      "href":"https://api.aspose.cloud/v3.0/slides/animation.pptx/slides/1/animation",

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

```csharp
SlidesApi api = new SlidesApi("MyClientId", "MyClientSecret");
SlideAnimation response = api.GetSlideAnimation("myPresentation.pptx", 1, folder: "MyStorageFolder");
foreach (Effect effect in response.MainSequence)
{
    Console.WriteLine(effect.Type);
}
```

{{< /tab >}}

{{< tab tabNum="2" >}}

{{< gist "" "17b08f624ccca40e351e7204e318237e" "GetSlideAnimations.java" >}}

{{< /tab >}}

{{< tab tabNum="3" >}}

{{< gist "" "67ba57c9ba0134d2e8c8ed2132d6515f" "GetSlideAnimations.php" >}}

{{< /tab >}}

{{< tab tabNum="4" >}}

{{< gist "" "2cc36b05065a88cb0737424e4f38f68e" "GetSlideAnimations.rb" >}}

{{< /tab >}}

{{< tab tabNum="5" >}}

{{< gist "" "88b9472c3f741eae6c606abdd003c791" "GetSlideAnimations.py" >}}

{{< /tab >}}

{{< tab tabNum="6" >}}

{{< gist "" "bc650902bdc45144b1727d329023dcba" "GetSlideAnimations.js" >}}

{{< /tab >}}

{{< tab tabNum="7" >}}

{{< gist "" "2b52dabd204b301389d1f4234e9bb0d5" "GetSlideAnimations.java" >}}

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
