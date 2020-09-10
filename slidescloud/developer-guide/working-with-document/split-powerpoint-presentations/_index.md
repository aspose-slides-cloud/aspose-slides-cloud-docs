---
title: "Split PowerPoint Presentations"
type: docs
url: /split-powerpoint-presentations/
weight: 30
---

## **Introduction**
The article explains how to split a PowerPoint Presentation and export the resultant splits into various formats. 
### **API Information**

|**API**|**Type**|**Description**|**Resource Link**|
| :- | :- | :- | :- |
|/slides/{name}/split|POST|Splits a file and stores the resultant parts on Storage|[PostSlidesSplit](https://apireference.aspose.cloud/slides/#/Document/PostSlidesSplit)|
### **cURL Example**
{{% alert color="primary" %}} 

By skipping the **to** and **from** parameters in the request URL, the whole document is split page by page into the desired format.

{{% /alert %}} 

{{< tabs tabTotal="2" tabID="1" tabName1="Request" tabName2="Response" >}}

{{< tab tabNum="1" >}}

**Get Authetication Code**

```java

curl -v "https://api.aspose.cloud/connect/token" -X POST -d "grant\_type=client\_credentials&client\_id=XXXX&client\_secret=XXXX-XX" -H "Content-Type: application/x-www-form-urlencoded" -H "Accept: application/json"

```

```java

curl  -v -X POST "https://api.aspose.cloud/v3.0/slides/source.pptx/split?from=1&to=2&format=png" -H "Content-Type: application/json" -H "Authorization: Bearer eyJhbGciOiJSUzI1NiIsInR5cCI6IkpXVCJ9.eyJuYmYiOjE1NTk3Njc2NjYsImV4cCI6MTU1OTg1NDA2NiwiaXNzIjoiaHR0cHM6Ly9hcGkuYXNwb3NlLmNsb3VkIiwiYXVkIjpbImh0dHBzOi8vYXBpLmFzcG9zZS5jbG91ZC9yZXNvdXJjZXMiLCJhcGkucGxhdGZvcm0iLCJhcGkucHJvZHVjdHMiXSwiY2xpZW50X2lkIjoiNzg5NDZmYjQtM2JkNC00ZDNlLWIzMDktZjllMmZmOWFjNmY5Iiwic2NvcGUiOlsiYXBpLnBsYXRmb3JtIiwiYXBpLnByb2R1Y3RzIl19.ostZtFSAtDFwvFygXzgg9optoSgYcrZWu2K2YPordXS7MRCbpSVV0wBuUPineb\_\_3VdobkasIL5WGavlVTLa4d1R1\_MxjZ5Wcv6Uth\_lMir5bvngnECv3SREE3e0XHEtZQWy4uh23UmWnqu1UTM60NS-onYRLQ0-eqXYmMSts7yl8oTq\_P1gepffW8oVssD6TZvcNqcUIPUCtC5sQXCEy7edlEsHOR611N\_772RJZaZ-yd6BDUkBLZGrek9POLQvcM85uGK4uQ53uuzoV\_5iYXE73jrYOXHgUIfcX1UDHhoJ4utt06sKH0FtugU5jT6rGqRuEi6LbahI2\_63IVE7LQ" --ssl-no-revoke

```

{{< /tab >}}

{{< tab tabNum="2" >}}

```java

{

   "slides":[

      {

         "href":"https://api.aspose.cloud/v3.0/slides/storage/file/source\_1.png",

         "relation":"self",

         "linkType":"image/png",

         "title":"Slide 1"

      },

      {

         "href":"https://api.aspose.cloud/v3.0/slides/storage/file/source\_2.png",

         "relation":"self",

         "linkType":"image/png",

         "title":"Slide 2"

      }

   ],

   "selfUri":{

      "href":"https://api.aspose.cloud/v3.0/slides/source.pptx",

      "relation":"self"

   }

}



```

{{< /tab >}}

{{< /tabs >}}
## **SDKs**
Using an SDK (API client) is the quickest way for a developer to speed up the development. An SDK takes care of a lot of low-level details of making requests and handling responses and lets you focus on writing code specific to your particular project. Check out our [GitHub repository](https://github.com/aspose-slides-cloud) for a complete list of Aspose.Slides Cloud SDKs along with working examples, to get you started in no time. Please check [Available SDKs](/slidescloud/available-sdks/) article to learn how to add an SDK to your project.
### **SDK Examples**
{{< tabs tabTotal="5" tabID="5" tabName1="C#" tabName2="Java" tabName3="PHP" tabName4="Node.js" tabName5="Android" >}}

{{< tab tabNum="1" >}}

{{< gist "" "a41a3c7c75241129b94faf7179d42527" "SplitPresentations.cs" >}}

{{< /tab >}}

{{< tab tabNum="2" >}}

{{< gist "" "17b08f624ccca40e351e7204e318237e" "SplitPresentations.java" >}}

{{< /tab >}}

{{< tab tabNum="3" >}}

{{< gist "" "67ba57c9ba0134d2e8c8ed2132d6515f" "SplitPresentations.php" >}}

{{< /tab >}}

{{< tab tabNum="4" >}}

{{< gist "" "bc650902bdc45144b1727d329023dcba" "SplitPresentations.js" >}}

{{< /tab >}}

{{< tab tabNum="5" >}}

{{< gist "" "2b52dabd204b301389d1f4234e9bb0d5" "SplitPresentations.java" >}}

{{< /tab >}}

{{< /tabs >}}
