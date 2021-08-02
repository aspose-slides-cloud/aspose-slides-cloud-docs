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

curl -v "https://api.aspose.cloud/connect/token" -X POST -d "grant_type=client_credentials&client_id=XXXX&client_secret=XXXX-XX" -H "Content-Type: application/x-www-form-urlencoded" -H "Accept: application/json"

```

```java

curl  -v -X DELETE "https://api.aspose.cloud/v3.0/slides/presentation_images.pptx/slides/1/shapes/1/series/2" -H "Content-Type: application/octet-stream" -H "Authorization: Bearer [Access Token]

```

{{< /tab >}}

{{< tab tabNum="2" >}}

```java

Code: 200

```

{{< /tab >}}

{{< /tabs >}}
## **SDK Source**
The Aspose for Cloud SDKs can be downloaded from the following page: [Available SDKs](/slides/available-sdks/)
## **SDK Examples**
{{< tabs tabTotal="9" tabID="5" tabName1="C#" tabName2="Java" tabName3="PHP" tabName4="Ruby" tabName5="Python" tabName6="Node.js" tabName7="Android" tabName8="C++" tabName9="Perl" >}}

{{< tab tabNum="1" >}}

```csharp
SlidesApi api = new SlidesApi("MyClientId", "MyClientSecret");
Chart chart = api.DeleteChartSeries("myPresentaion.pptx", 1, 1, 2);
Console.WriteLine(chart.Series.Count);
```

{{< /tab >}}

{{< tab tabNum="2" >}}

{{< gist "" "17b08f624ccca40e351e7204e318237e" "DeleteChartSeries.java" >}}

{{< /tab >}}

{{< tab tabNum="3" >}}

{{< gist "" "67ba57c9ba0134d2e8c8ed2132d6515f" "DeleteChartSeries.php" >}}

{{< /tab >}}

{{< tab tabNum="4" >}}

{{< gist "" "2cc36b05065a88cb0737424e4f38f68e" "DeleteChartSeries.rb" >}}

{{< /tab >}}

{{< tab tabNum="5" >}}

{{< gist "" "88b9472c3f741eae6c606abdd003c791" "DeleteChartSeries.py" >}}

{{< /tab >}}

{{< tab tabNum="6" >}}

{{< gist "" "bc650902bdc45144b1727d329023dcba" "DeleteChartSeries.js" >}}

{{< /tab >}}

{{< tab tabNum="7" >}}

{{< gist "" "2b52dabd204b301389d1f4234e9bb0d5" "DeleteChartSeries.java" >}}

{{< /tab >}}

{{< tab tabNum="8" >}}

{{< gist "" "a41a3c7c75241129b94faf7179d42527" "Coming_Soon.txt" >}}

{{< /tab >}}

{{< tab tabNum="9" >}}

{{< gist "" "a41a3c7c75241129b94faf7179d42527" "Coming_Soon.txt" >}}

{{< /tab >}}

{{< /tabs >}}
