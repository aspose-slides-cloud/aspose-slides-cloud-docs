---
title: "Updating the interactive sequence of a PowerPoint Presentation"
type: docs
url: /updating-the-interactive-sequence-of-a-powerpoint-presentation/
weight: 20
---

## **Introduction**
Aspose.Slides Cloud allows you to update information from a Power Point Presentation. 
### **API Information**

|**API**|**Type**|**Description**|**Swagger Link**|
| :- | :- | :- | :- |
|/slides/{slide-index}/animation/interactiveSequences|GET|Get Animation Information from a PowerPoint Slide|[PostSlideAnimationInteractiveSequence](https://apireference.aspose.cloud/slides/#/Animation/PostSlideAnimationInteractiveSequence)|
### **cURL Example**
{{< tabs tabTotal="2" tabID="1" tabName1="Request" tabName2="Response" >}}

{{< tab tabNum="1" >}}

**Create Request Token**

```java

curl -v "https://api.aspose.cloud/connect/token" -X POST -d "grant\_type=client\_credentials&client\_id=78946fb4-3bd4-4d3e-b309-f9e2ff9ac6f9&client\_secret=b125f13bf6b76ed81ee990142d841195" -H "Content-Type: application/x-www-form-urlencoded" -H "Accept: application/json"

```

```java

curl -v -X POST "https://api.aspose.cloud/v3.0/slides/animation.pptx/slides/1/animation/interactiveSequences" -H "Content-Type:application/json" -H "Authorization: Bearer eyJhbGciOiJSUzI1NiIsInR5cCI6IkpXVCJ9.eyJuYmYiOjE1NjEwNjM0NTAsImV4cCI6MTU2MTE0OTg1MCwiaXNzIjoiaHR0cHM6Ly9hcGkuYXNwb3NlLmNsb3VkIiwiYXVkIjpbImh0dHBzOi8vYXBpLmFzcG9zZS5jbG91ZC9yZXNvdXJjZXMiLCJhcGkucGxhdGZvcm0iLCJhcGkucHJvZHVjdHMiXSwiY2xpZW50X2lkIjoiNzg5NDZmYjQtM2JkNC00ZDNlLWIzMDktZjllMmZmOWFjNmY5Iiwic2NvcGUiOlsiYXBpLnBsYXRmb3JtIiwiYXBpLnByb2R1Y3RzIl19.XURcZFFwPs\_\_A4GHgzncfsCI5\_F6R0NIWrTbdGcQqTKBV24jqbQYwe7POYMU8QT3\_CKQ9zrlCX47Gtzx3XZ-1LyZAx3v6e6\_\_r7HG9DsVCrzGXxzcIaYBwo9XohkfO5At9XcmXMqw1YoZvWskHUjhIAXzlg6Kt-k1hIPCL-0A1A0WkbdtWOJtWpTEVnIR2kBfXkUcNHLREq3S4JVshLmnjdPF6YViBM5AkV91diC33yj2Fwz-j572SjgwEuHkKNRLTngwsnu9DFEtfiN6bCCPBhulq6XG4DuqLrAtxyodD0Et5Y0YegUHUWOvf4-ZFbUd1ZHzU\_rQ06dXzP6SDzMjg" --ssl-no-revoke -d {"effects": [{"type": "Fly", "subtype": "Bottom", "presetClassType": "Entrance", "shapeIndex": 5, "triggerType": "OnClick"} ], "triggerShapeIndex": 1 }

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
Using an SDK (API client) is the quickest way for a developer to speed up the development. An SDK takes care of a lot of low-level details of making requests and handling responses and lets you focus on writing code specific to your particular project. Check out our [GitHub repository](https://github.com/aspose-slides-cloud) for a complete list of Aspose.Slides Cloud SDKs along with working examples, to get you started in no time. Please check [Available SDKs](/slidescloud/available-sdks/) article to learn how to add an SDK to your project.
### **SDK Examples**
{{< tabs tabTotal="9" tabID="5" tabName1="C#" tabName2="Java" tabName3="PHP" tabName4="Ruby" tabName5="Python" tabName6="Node.js" tabName7="Android" tabName8="C++" tabName9="Perl" >}}

{{< tab tabNum="1" >}}

{{< gist "" "a41a3c7c75241129b94faf7179d42527" "UpdateSlideAnimationInteractiveSequence.cs" >}}

{{< /tab >}}

{{< tab tabNum="2" >}}

{{< gist "" "17b08f624ccca40e351e7204e318237e" "UpdateSlideAnimationInteractiveSequence.java" >}}

{{< /tab >}}

{{< tab tabNum="3" >}}

{{< gist "" "67ba57c9ba0134d2e8c8ed2132d6515f" "UpdateSlideAnimationInteractiveSequence.php" >}}

{{< /tab >}}

{{< tab tabNum="4" >}}

{{< gist "" "a41a3c7c75241129b94faf7179d42527" "Coming\_Soon.txt" >}}

{{< /tab >}}

{{< tab tabNum="5" >}}

{{< gist "" "a41a3c7c75241129b94faf7179d42527" "Coming\_Soon.txt" >}}

{{< /tab >}}

{{< tab tabNum="6" >}}

{{< gist "" "bc650902bdc45144b1727d329023dcba" "UpdateSlideAnimationInteractiveSequence.js" >}}

{{< /tab >}}

{{< tab tabNum="7" >}}

{{< gist "" "2b52dabd204b301389d1f4234e9bb0d5" "UpdateSlideAnimationInteractiveSequence.java" >}}

{{< /tab >}}

{{< tab tabNum="8" >}}

{{< gist "" "a41a3c7c75241129b94faf7179d42527" "Coming\_Soon.txt" >}}

{{< /tab >}}

{{< tab tabNum="9" >}}

{{< gist "" "a41a3c7c75241129b94faf7179d42527" "Coming\_Soon.txt" >}}

{{< /tab >}}

{{< /tabs >}}
### **SDK Source**
The Aspose Cloud SDK's can be downloaded from the following page: [Available SDK's](/slidescloud/available-sdks/)
