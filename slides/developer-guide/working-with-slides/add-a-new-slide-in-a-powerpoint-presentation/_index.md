---
title: "Add a New Slide in a PowerPoint Presentation"
type: docs
url: /add-a-new-slide-in-a-powerpoint-presentation/
weight: 40
---

## **Introduction**
This example allows you to add new slides in a presentation using Aspose.Slides for Cloud API in your applications. You can use our REST API with any language: .NET, Java, PHP, Ruby, Rails, Python, jQuery and much more.

### **API Information**

|**API**|**Type**|**Description**|**Resource**|
| :- | :- | :- | :- |
|/slides/{name}/slides|POST|Create a slide.|[PostSlidesAdd](https://apireference.aspose.cloud/slides/#/Slides/PostSlidesAdd)|

{{< expand-list title="Request Parameters" >}}

| **Parameter Name** | **HTTP Method(s)** | **Type** | **Optional/Required** | **Description** |
| :- | :- | :- | :- | :- |
|password | GET/POST/DELETE | string | Optional | Presentation password |
|folder | GET/POST/DELETE | string | Optional | Presentation folder |
|storage | GET/POST/DELETE | string | Optional | Presentation storage |
|slides | DELETE | int[] | Optional | Comma separated index list of slides to be deleted. Delete all by default |
|position | POST | int | Optional | Position of the new slide. Adds a slide to the end by default.  |
|layoutAlias | POST | string | Optional | Alias of layout slide for new slide. Alias could be the type of layout, name of layout slide or index |

*In case of Amazon S3 storage folder path starts with Amazon S3 bucket name.*

{{< /expand-list >}}

#### **HTTP POST**
Adds a new slide to the presentation.

{{< tabs tabTotal="3" tabID="2" tabName1="Example 1" tabName2="Example 2" tabName2="Example 3">}}

{{< tab tabNum="1" >}}

##### **Adds new empty slide to the presentation.**

###### **Request**
```
POST https://api.aspose.cloud/v3.0/slides/myPresentation.pptx/slides
```

###### **Response** 

{{< expand-list title="Full Slides response that includes new slide" >}}

{{< tabs tabTotal="2" tabID="3" tabName1="JSON" tabName2="XML" >}}

{{< tab tabNum="1" >}}
```
{
    "slideList": [
        {
            "href": "https://api.aspose.cloud/v3.0/slides/myPresentation.pptx/slides/1?folder=myFolder",
            "relation":"self"
        },
        {
            "href": "https://api.aspose.cloud/v3.0/slides/myPresentation.pptx/slides/2?folder=myFolder",
            "relation":"self"
        },
        {
            "href": "https://api.aspose.cloud/v3.0/slides/myPresentation.pptx/slides/3?folder=myFolder",
            "relation":"self"
        },
        {
            "href": "https://api.aspose.cloud/v3.0/slides/myPresentation.pptx/slides/4?folder=myFolder",
            "relation":"self"
        }
    ],
    "selfUri": {
        "href": "https://api.aspose.cloud/v3.0/slides/myPresentation.pptx/slides?folder=myFolder",
        "relation":"self"
    }
}
```
{{< /tab >}}

{{< tab tabNum="2" >}}
```
<Slides xmlns:xsd="http://www.w3.org/2001/XMLSchema" xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance">
    <link href="https://api.aspose.cloud/v3.0/slides/myPresentation.pptx/slides?folder=myFolder" rel="self" />
    <Slide href="https://api.aspose.cloud/v3.0/slides/myPresentation.pptx/slides/1?folder=myFolder" rel="self" />
    <Slide href="https://api.aspose.cloud/v3.0/slides/myPresentation.pptx/slides/2?folder=myFolder" rel="self" />
    <Slide href="https://api.aspose.cloud/v3.0/slides/myPresentation.pptx/slides/3?folder=myFolder" rel="self" />
    <Slide href="https://api.aspose.cloud/v3.0/slides/myPresentation.pptx/slides/4?folder=myFolder" rel="self" />
</Slides>
```
{{< /tab >}}

{{< /tabs >}}

{{< /expand-list >}}


###### **.Net SDK Code:**
```csharp
SlidesApi api = new SlidesApi("MyAppSid", "MyAppKey");
PostSlidesAddRequest request = new PostSlidesAddRequest { Name = "myPresentation.pptx" };
Slides response = api.PostSlidesAdd(request);
foreach (ResourceUriElement slide in response.SlideList)
{
    Console.WriteLine(slide.Uri.Href); //https://api.aspose.cloud/v3.0/slides/myPresentation.pptx/slides/1 etc.
}
```

{{< /tab >}}

{{< tab tabNum="2" >}}

##### **Adds a slide to the specified position. If position is not specified then the slide will be added to the end of the slides list.**

###### **Request**
```
POST https://api.aspose.cloud/v3.0/slides/myPresentation.pptx/slides?position=1 
```

###### **Response** 

{{< expand-list title="Full Slides response that includes new slide" >}}

{{< tabs tabTotal="2" tabID="4" tabName1="JSON" tabName2="XML" >}}

{{< tab tabNum="1" >}}
```
{
    "slideList": [
        {
            "href": "https://api.aspose.cloud/v3.0/slides/myPresentation.pptx/slides/1?folder=myFolder",
            "relation":"self"
        },
        {
            "href": "https://api.aspose.cloud/v3.0/slides/myPresentation.pptx/slides/2?folder=myFolder",
            "relation":"self"
        },
        {
            "href": "https://api.aspose.cloud/v3.0/slides/myPresentation.pptx/slides/3?folder=myFolder",
            "relation":"self"
        },
        {
            "href": "https://api.aspose.cloud/v3.0/slides/myPresentation.pptx/slides/4?folder=myFolder",
            "relation":"self"
        }
    ],
    "selfUri": {
        "href": "https://api.aspose.cloud/v3.0/slides/myPresentation.pptx/slides?folder=myFolder",
        "relation":"self"
    }
}
```
{{< /tab >}}

{{< tab tabNum="2" >}}
```
<Slides xmlns:xsd="http://www.w3.org/2001/XMLSchema" xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance">
    <link href="https://api.aspose.cloud/v3.0/slides/myPresentation.pptx/slides?folder=myFolder" rel="self" />
    <Slide href="https://api.aspose.cloud/v3.0/slides/myPresentation.pptx/slides/1?folder=myFolder" rel="self" />
    <Slide href="https://api.aspose.cloud/v3.0/slides/myPresentation.pptx/slides/2?folder=myFolder" rel="self" />
    <Slide href="https://api.aspose.cloud/v3.0/slides/myPresentation.pptx/slides/3?folder=myFolder" rel="self" />
    <Slide href="https://api.aspose.cloud/v3.0/slides/myPresentation.pptx/slides/4?folder=myFolder" rel="self" />
</Slides>
```
{{< /tab >}}

{{< /tabs >}}

{{< /expand-list >}}


###### **.Net SDK Code:**
```csharp
SlidesApi api = new SlidesApi("MyAppSid", "MyAppKey");
PostSlidesAddRequest request = new PostSlidesAddRequest { Name = "myPresentation.pptx", Position = 1 };
Slides response = api.PostSlidesAdd(request);
foreach (ResourceUriElement slide in response.SlideList)
{
    Console.WriteLine(slide.Uri.Href); //https://api.aspose.cloud/v3.0/slides/myPresentation.pptx/slides/1 etc.
}
```

{{< /tab >}}

{{< tab tabNum="3" >}}

##### **Adds new empty slide to the presentation with layout TextAndChart.**

###### **Request**
```
POST https://api.aspose.cloud/v3.0/slides/myPresentation.pptx/slides?layoutAlias=TextAndChart
```

###### **Response** 

{{< expand-list title="Full Slides response that includes new slide" >}}

{{< tabs tabTotal="2" tabID="6" tabName1="JSON" tabName2="XML" >}}

{{< tab tabNum="1" >}}
```
{
    "slideList": [
        {
            "href": "https://api.aspose.cloud/v3.0/slides/myPresentation.pptx/slides/1?folder=myFolder",
            "relation":"self"
        },
        {
            "href": "https://api.aspose.cloud/v3.0/slides/myPresentation.pptx/slides/2?folder=myFolder",
            "relation":"self"
        },
        {
            "href": "https://api.aspose.cloud/v3.0/slides/myPresentation.pptx/slides/3?folder=myFolder",
            "relation":"self"
        },
        {
            "href": "https://api.aspose.cloud/v3.0/slides/myPresentation.pptx/slides/4?folder=myFolder",
            "relation":"self"
        }
    ],
    "selfUri": {
        "href": "https://api.aspose.cloud/v3.0/slides/myPresentation.pptx/slides?folder=myFolder",
        "relation":"self"
    }
}
```
{{< /tab >}}

{{< tab tabNum="2" >}}
```
<Slides xmlns:xsd="http://www.w3.org/2001/XMLSchema" xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance">
    <link href="https://api.aspose.cloud/v3.0/slides/myPresentation.pptx/slides?folder=myFolder" rel="self" />
    <Slide href="https://api.aspose.cloud/v3.0/slides/myPresentation.pptx/slides/1?folder=myFolder" rel="self" />
    <Slide href="https://api.aspose.cloud/v3.0/slides/myPresentation.pptx/slides/2?folder=myFolder" rel="self" />
    <Slide href="https://api.aspose.cloud/v3.0/slides/myPresentation.pptx/slides/3?folder=myFolder" rel="self" />
    <Slide href="https://api.aspose.cloud/v3.0/slides/myPresentation.pptx/slides/4?folder=myFolder" rel="self" />
</Slides>
```
{{< /tab >}}

{{< /tabs >}}

{{< /expand-list >}}


###### **.Net SDK Code:**
```csharp
SlidesApi api = new SlidesApi("MyAppSid", "MyAppKey");
PostSlidesAddRequest request = new PostSlidesAddRequest { Name = "myPresentation.pptx", LayoutAlias = "TextAndChart" };
Slides response = api.PostSlidesAdd(request);
foreach (ResourceUriElement slide in response.SlideList)
{
    Console.WriteLine(slide.Uri.Href); //https://api.aspose.cloud/v3.0/slides/myPresentation.pptx/slides/1 etc.
}
```

{{< /tab >}}

{{< /tabs >}}

## **Resource**
The following Aspose.Slides for Cloud REST API resource has been used in the examples: [Slides](https://apireference.aspose.cloud/slides/).
## **REST Methods References**
We are referring to some common methods in the REST examples to perform general operations. These methods can be found on the following page: [REST API Methods](https://apireference.aspose.cloud/slides/) 
## **cURL Example**
{{< tabs tabTotal="2" tabID="1" tabName1="Request" tabName2="Response" >}}

{{< tab tabNum="1" >}}

**Create Authentication Headers**

```java

curl -v "https://api.aspose.cloud/oauth2/token" -X POST -d "grant_type=client_credentials&client_id=XXX&client_secret=XXXX-XX"-H "Content-Type: application/x-www-form-urlencoded"-H "Accept: application/json"

```

```java

curl -v "http://api.aspose.cloud/v1.1/slides/sample.pptx/slides"-X POST -H "Content-Type: application/json"-H "Accept: application/json" -H "Authorization: Bearer -Ou_UHdVStdZldtjaeFUAowQ3x2KLlSHd5ovZfDtZqpgdC6FLlalPmO8VJ58HXp8sgGhLqMqlnzEzIF2fEhEyJ3D7xzaw_c8cAuk3qoag3g7bghMHw_pe_RTxxJ9r04R9YAGFbbAcoU1ddPvrPz0e1FSakagM42Ie2eA8D1MyBVJ1D-RZJrfebPePuOLvR_hOD8Doqk5SBi_j-efODJK_PmGUxj0onOrUUx8Tj_GuUKrG6DcBnpl84_UykdOP87IeHnT2_NZCHQIgOY0vtfW6AUGfP9jO5W1mBS_q3lthTDRMg2LuZ6s0r9MKlwVJ_n7sn3TUCrr8kGmUB3k0mL0rrd5TSKm7yjx8hhjap43PlFhwk-r9g7guWsuFLoeDqPa4JNJ1NFM54qQvgWKCp5oDj4dZfbc7qhfIelNh1gW4VYwfmgz"

```

{{< /tab >}}

{{< tab tabNum="2" >}}

```java
{
   "Slides":{
      "SlideList":[
         {
            "Uri":{
               "Href":"http://api.aspose.cloud/v1.1/slides/sample.pptx/slides/1",
               "Relation":"self",
               "LinkType":null,
               "Title":null
            }
         }
      ],
      "SelfUri":{
         "Href":"http://api.aspose.cloud/v1.1/slides/sample.pptx/slides",
         "Relation":"self",
         "LinkType":null,
         "Title":null
      },
      "AlternateLinks":[
      ],
      "Links":[
         {
            "Href":"http://api.aspose.cloud/v1.1/slides/sample.pptx/slides",
            "Relation":"self",
            "LinkType":null,
            "Title":null
         }
      ]
   },
   "Code":200,
   "Status":"OK"
}
```

{{< /tab >}}

{{< /tabs >}}
## **SDK Source**
The Aspose for Cloud SDKs can be downloaded from the following page: [Available SDKs](/slides/available-sdks/)
### **SDK Examples**
{{< tabs tabTotal="9" tabID="5" tabName1="C#" tabName2="Java" tabName3="PHP" tabName4="Ruby" tabName5="Python" tabName6="Node.js" tabName7="Android" tabName8="C++" tabName9="Perl" >}}

{{< tab tabNum="1" >}}

{{< gist "" "a41a3c7c75241129b94faf7179d42527" "AddNewSlide.cs" >}}

{{< /tab >}}

{{< tab tabNum="2" >}}

{{< gist "" "17b08f624ccca40e351e7204e318237e" "AddNewSlide.java" >}}

{{< /tab >}}

{{< tab tabNum="3" >}}

{{< gist "" "67ba57c9ba0134d2e8c8ed2132d6515f" "AddNewSlide.php" >}}

{{< /tab >}}

{{< tab tabNum="4" >}}

{{< gist "" "a41a3c7c75241129b94faf7179d42527" "Coming_Soon.txt" >}}

{{< /tab >}}

{{< tab tabNum="5" >}}

{{< gist "" "a41a3c7c75241129b94faf7179d42527" "Coming_Soon.txt" >}}

{{< /tab >}}

{{< tab tabNum="6" >}}

{{< gist "" "bc650902bdc45144b1727d329023dcba" "AddNewSlide.js" >}}

{{< /tab >}}

{{< tab tabNum="7" >}}

{{< gist "" "2b52dabd204b301389d1f4234e9bb0d5" "AddNewSlide.java" >}}

{{< /tab >}}

{{< tab tabNum="8" >}}

{{< gist "" "a41a3c7c75241129b94faf7179d42527" "Coming_Soon.txt" >}}

{{< /tab >}}

{{< tab tabNum="9" >}}

{{< gist "" "a41a3c7c75241129b94faf7179d42527" "Coming_Soon.txt" >}}

{{< /tab >}}

{{< /tabs >}}
