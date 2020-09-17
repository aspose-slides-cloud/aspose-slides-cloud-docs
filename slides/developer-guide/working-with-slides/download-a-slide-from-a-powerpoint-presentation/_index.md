---
title: "Download a Slide from a PowerPoint Presentation"
type: docs
url: /download-a-slide-from-a-powerpoint-presentation/
weight: 10
---

## **Introduction**
Aspose.Slides Cloud allows you to easily export a particular slide from a PowerPoint Document. Aspose.Slides Cloud supports downloading in ppt, ppt, ppt, ppsx, pps, ppsm, potx, otm, odp, otp, pdf, html, xps, SWF, SVG, tiff, jpeg, png, gif, and BMP image formats. Aspose.Slides Cloud provides two methods to obtain the exported slide

### **Downloading the exported file**
#### **API Information**

|**API**|**Type**|**Description**|**Resource**|
| :- | :- | :- | :- |
|/slides/{name}/slides/{slideIndex}/{format}|POST|Download the slide in the desired format|[PostSlideSaveAs](https://apireference.aspose.cloud/slides/#/Slides/PostSlideSaveAs)|
#### **cURL Example**
{{% alert color="primary" %}} 

This request returns the slide in the response with the desired export format. You can use the **--output** flag for **cURL** to write response data to a file

{{% /alert %}} 

{{< tabs tabTotal="1" tabID="1" tabName1="Request" >}}

{{< tab tabNum="1" >}}

**Create Authentication Headers** 

```java

curl -v "https://api.aspose.cloud/connect/token" -X POST -d "grant_type=client_credentials&client_id=XXXX&client_secret=XXXX-XX" -H "Content-Type: application/x-www-form-urlencoded" -H "Accept: application/json"

```

```java

curl  -v -X GET "https://api.aspose.cloud/v3.0/slides/presentation_images.pptx/slides/1/pdf" -H "Content-Type: application/octet-stream" -H "Authorization: Bearer []Access Token" --ssl-no-revoke --output test_export_pdf.pdf

```

{{< /tab >}}

{{< /tabs >}}
### **Saving the exported file to Storage**
#### **API Information**

|**API**|**Type**|**Description**|**Resource**|
| :- | :- | :- | :- |
|/slides/{name}/slides/{slideIndex}/{format}|PUT|Download the slide in the desired format|[PutSlideSaveAs](https://apireference.aspose.cloud/slides/#/Slides/PutSlideSaveAs)|
#### **cURL Example**
{{% alert color="primary" %}} 

This request exports the slide to Storage. You have to provide the **outPath** parameter

{{% /alert %}} 

{{< tabs tabTotal="1" tabID="4" tabName1="Request" >}}

{{< tab tabNum="1" >}}

**Create Authentication Headers** 

```java

curl -v "https://api.aspose.cloud/connect/token" -X POST -d "grant_type=client_credentials&client_id=XXXX&client_secret=XXXX-XX" -H "Content-Type: application/x-www-form-urlencoded" -H "Accept: application/json"

```

```java

curl  -v -X PUT "https://api.aspose.cloud/v3.0/slides/presentation_images.pptx/slides/1/pdf?outPath=myFile.pdf" -H "Content-Type: application/octet-stream" -H "Authorization: Bearer [Access Token]

```

{{< /tab >}}

{{< /tabs >}}


## **SDKs**
Using an SDK (API client) is the quickest way for a developer to speed up the development. An SDK takes care of a lot of low-level details of making requests and handling responses and lets you focus on writing code specific to your particular project. Check out our [GitHub repository](https://github.com/aspose-slides-cloud) for a complete list of Aspose.Slides Cloud SDKs along with working examples, to get you started in no time. Please check [Available SDKs](/slides/available-sdks/) article to learn how to add an SDK to your project.
### **SDK Examples**
{{< tabs tabTotal="5" tabID="7" tabName1="C#" tabName2="Java" tabName3="PHP" tabName4="Node.js" tabName5="Android" >}}

{{< tab tabNum="1" >}}

{{< gist "" "a41a3c7c75241129b94faf7179d42527" "DownloadSlide.cs" >}}

{{< /tab >}}

{{< tab tabNum="2" >}}

{{< gist "" "17b08f624ccca40e351e7204e318237e" "DownloadSlide.java" >}}

{{< /tab >}}

{{< tab tabNum="3" >}}

{{< gist "" "67ba57c9ba0134d2e8c8ed2132d6515f" "DownloadSlide.php" >}}

{{< /tab >}}

{{< tab tabNum="4" >}}

{{< gist "" "bc650902bdc45144b1727d329023dcba" "DownloadSlide.js" >}}

{{< /tab >}}

{{< tab tabNum="5" >}}

{{< gist "" "2b52dabd204b301389d1f4234e9bb0d5" "DownloadSlide.java" >}}

{{< /tab >}}

{{< /tabs >}}
### **SDK Source**
The Aspose  Cloud SDKs can be downloaded from the following page: [Available SDKs](/slides/available-sdks/)


