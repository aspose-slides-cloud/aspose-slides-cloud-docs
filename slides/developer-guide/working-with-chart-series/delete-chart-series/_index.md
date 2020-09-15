---
title: "Delete Chart Series"
type: docs
url: /delete-chart-series/
weight: 20
---

## **Introduction**
Aspose.Slides Cloud allows you to delete chart slides from a PowerPoint Presentation. 
### **API Information**
Aspose.Slides Cloud provides resources to achieve this. You can either delete a single slide or delete all slides in the Presentation

|**API**|**Type**|**Description**|**Resource**|
| :- | :- | :- | :- |
|/slides/{name}/Chart/{name}|DELETE|Delete the chart series|[DeleteChartSeries](https://apireference.aspose.cloud/slides/#/Chart/DeleteChartSeries)|
### **cURL Example**
{{% alert color="primary" %}} 

By omitting the slide index parameter you can clean the presentation of all slides

{{% /alert %}} 

{{< tabs tabTotal="2" tabID="1" tabName1="Request" tabName2="Response" >}}

{{< tab tabNum="1" >}}

**Create Authentication Headers** 

```java

curl -v "https://api.aspose.cloud/connect/token" -X POST -d "grant\_type=client\_credentials&client\_id=XXXX&client\_secret=XXXX-XX" -H "Content-Type: application/x-www-form-urlencoded" -H "Accept: application/json"

```

```java

curl  -v -X DELETE "https://api.aspose.cloud/v3.0/slides/Chart/DeleteChartSeries/presentation\_images.pptx/" -H "Content-Type: application/octet-stream" -H "Authorization: Bearer [Access Token] 

```

{{< /tab >}}

{{< tab tabNum="2" >}}

```java

Code: 200

```

{{< /tab >}}

{{< /tabs >}}
## **SDK Source**
The Aspose for Cloud SDKs can be downloaded from the following page: [Available SDKs](/slidescloud/available-sdks/)
## **SDK Examples**
{{< tabs tabTotal="5" tabID="5" tabName1="C#" tabName2="Java" tabName3="PHP" tabName4="Node.js" tabName5="Android" >}}

{{< tab tabNum="1" >}}

{{< gist "" "a41a3c7c75241129b94faf7179d42527" "DeleteChartSeries.cs" >}}

{{< /tab >}}

{{< tab tabNum="2" >}}

{{< gist "" "17b08f624ccca40e351e7204e318237e" "DeleteChartSeries.java" >}}

{{< /tab >}}

{{< tab tabNum="3" >}}

{{< gist "" "67ba57c9ba0134d2e8c8ed2132d6515f" "DeleteChartSeries.php" >}}

{{< /tab >}}

{{< tab tabNum="4" >}}

{{< gist "" "bc650902bdc45144b1727d329023dcba" "DeleteChartSeries.js" >}}

{{< /tab >}}

{{< tab tabNum="5" >}}

{{< gist "" "2b52dabd204b301389d1f4234e9bb0d5" "DeleteChartSeries.java" >}}

{{< /tab >}}

{{< /tabs >}}



