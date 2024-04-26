---
title: "Export a Math Formula"
keywords: "PowerPoint, presentation, REST API, Cloud API, math, formula, equation, math formula, export formula, MathML, LaTeX"
type: docs
url: /export-a-math-formula/
weight: 20
---

## **Introduction**
You can export (download or save to the storage) math formulas in MathML format. You use **mathMl** subresource of **portion** resource for that. You can not export ordinary text portions for which **MathParagraph** property is not set. You will get an exception if you try to export such a portion.

### **API Information**

|**API**|**Type**|**Description**|**Resource Link**|
| :- | :- | :- | :- |
|/slides/{name}/slides/{slideIndex}/shapes/{shapeIndex}/paragraphs/{paragraphIndex}/portions/{portionIndex}/{format}|POST|Converts math formula to MathML or LaTeX format.|[DownloadMathPortion](https://apireference.aspose.cloud/slides/#/Shapes/DownloadMathPortion)|
|/slides/{name}/slides/{slideIndex}/shapes/{shapeIndex}/paragraphs/{paragraphIndex}/portions/{portionIndex}/{format}|PUT|Converts math formula to MathML or LaTeX format and saves result to the storage.|[SaveMathPortion](https://apireference.aspose.cloud/slides/#/Shapes/SaveMathPortion)|

{{< expand-list title="Request Parameters" >}}

| **Parameter Name** | **HTTP Method(s)** | **Type** | **Optional/Required** | **Description** |
| :- | :- | :- | :- | :- |
|folder|POST/PUT|string (query)|Optional|Presentation folder.|
|storage|POST/PUT|string (query)|Optional|Presentation storage.|
|password|POST/PUT|string (header)|Optional|Presentation password.|
|outPath|PUT|string (query)|Required|A path to save the result.|

*In case of Amazon S3 storage folder path starts with Amazon S3 bucket name.*

{{< /expand-list >}}

### **cURL Example**
{{< tabs tabTotal="2" tabID="1" tabName1="Request" tabName2="Response" >}}

{{< tab tabNum="1" >}}

**Create Request Token**

```java
curl -X POST "https://api.aspose.cloud/connect/token" -d "grant_type=client_credentials&client_id=MyClientId&client_secret=MyClientSecret" -H "Content-Type: application/x-www-form-urlencoded" -H "Accept: application/json"
```

**Convert to MathML**

```java
curl -X POST "https://api.aspose.cloud/v3.0/slides/MyPresentation.pptx/slides/1/shapes/2/paragraphs/3/portions/2/mathml" -d "" -H "" -H "Authorization: Bearer AuthToken"
```

{{< /tab >}}

{{< tab tabNum="2" >}}

```xml
<?xml version="1.0" encoding="utf-8"?>
<math display="block" xmlns="http://www.w3.org/1998/Math/MathML">
	<mrow>
		<munder>
			<mrow>
				<mi>l</mi>
				<mi>i</mi>
				<mi>m</mi>
			</mrow>
			<mrow>
				<mi>x</mi>
				<mo>−</mo>
				<mo>&gt;</mo>
				<mn>0</mn>
			</mrow>
		</munder>
		<mo>⁡</mo>
		<mfrac>
			<mrow>
				<mrow>
					<mi>s</mi>
					<mi>i</mi>
					<mi>n</mi>
				</mrow>
				<mo>⁡</mo>
				<mi>x</mi>
			</mrow>
			<mi>x</mi>
		</mfrac>
	</mrow>
</math>
```

{{< /tab >}}

{{< /tabs >}}
## **SDKs**
Using an SDK (API client) is the quickest way for a developer to speed up the development. An SDK takes care of a lot of low-level details of making requests and handling responses and lets you focus on writing code specific to your particular project. Check out our [GitHub repository](https://github.com/aspose-slides-cloud) for a complete list of Aspose.Slides Cloud SDKs along with working examples, to get you started in no time. Please check [Available SDKs](/slides/available-sdks/) article to learn how to add an SDK to your project.
### **SDK Examples**
{{< tabs tabTotal="10" tabID="5" tabName1="C#" tabName2="Java" tabName3="PHP" tabName4="Ruby" tabName5="Python" tabName6="Node.js" tabName7="Go" tabName8="C++" tabName9="Perl" tabName10="Swift" >}}

{{< tab tabNum="1" >}}

```csharp
string fileName = "MyPresentation.pptx";
int slideIndex = 2;
int shapeIndex = 3;
int paragraphIndex = 1;
int portionIndex = 1;
SlidesApi api = new SlidesApi("MyClientId", "MyClientSecret");

using Stream mathMl = api.DownloadMathPortion(fileName, slideIndex, shapeIndex, paragraphIndex, portionIndex, Mathformat.MathML);
using Stream fileStream = File.Open("equation.xml", FileMode.Create);
mathMl.CopyTo(fileStream);
```

{{< /tab >}}

{{< tab tabNum="2" >}}

```java
String fileName = "MyPresentation.pptx";
int slideIndex = 2;
int shapeIndex = 3;
int paragraphIndex = 1;
int portionIndex = 1;
SlidesApi api = new SlidesApi("MyClientId", "MyClientSecret");

File mathMl = api.downloadMathPortion(fileName, slideIndex, shapeIndex, paragraphIndex, portionIndex, MathFormat.MATHML, null, null, null);
System.out.println("The converted file was saved to " + mathMl.getPath());
```

{{< /tab >}}

{{< tab tabNum="3" >}}

```php
use Aspose\Slides\Cloud\Sdk\Api\Configuration;
use Aspose\Slides\Cloud\Sdk\Api\SlidesApi;

$config = new Configuration();
$config->setAppSid("MyClientId");
$config->setAppKey("MyClientSecret");
$api = new SlidesApi(null, $config);

$fileName = "MyPresentation.pptx";
$slideIndex = 2;
$shapeIndex = 3;
$paragraphIndex = 1;
$portionIndex = 1;

$mathMl = $api->downloadMathPortion($fileName, $slideIndex, $shapeIndex, $paragraphIndex, $portionIndex, "MathML");
print("The converted file was saved to " . $mathMl->getPathname());
```

{{< /tab >}}

{{< tab tabNum="4" >}}

{{< /tab >}}

{{< tab tabNum="5" >}}

```python
import asposeslidescloud

from asposeslidescloud.configuration import Configuration
from asposeslidescloud.apis.slides_api import SlidesApi

configuration = Configuration()
configuration.app_sid = 'MyClientId'
configuration.app_key = 'MyClientSecret'
api = SlidesApi(configuration)

file_name = "MyPresentation.pptx"
slide_index = 2
shape_index = 3
paragraph_index = 1
portion_index = 1

mathMl = api.download_math_portion(file_name, slide_index, shape_index, paragraph_index, portion_index, "MathML")
print('The converted file was saved to ' + mathMl)
```

{{< /tab >}}

{{< tab tabNum="6" >}}

```javascript
const CloudSdk = require("asposeslidescloud");
const fs = require("fs");
const api = new CloudSdk.SlidesApi("MyClientId", "MyClientSecret");

const fileName = "MyPresentation.pptx";
const slideIndex = 2;
const shapeIndex = 3;
const paragraphIndex = 1;
const portionIndex = 1;

api.downloadMathPortion(fileName, slideIndex, shapeIndex, paragraphIndex, portionIndex, "MathML").then(result => {
    fs.writeFile("equation.xml", result.body, (err) => {
        if (err) throw err;
    });
});
```

{{< /tab >}}

{{< tab tabNum="7" >}}

```go
cfg := asposeslidescloud.NewConfiguration()
cfg.AppSid = "MyClientId"
cfg.AppKey = "MyClientSecret"
api := asposeslidescloud.NewAPIClient(cfg)

fileName := "MyPresentation.pptx"
var slideIndex int32 = 2
var shapeIndex int32 = 3
var paragraphIndex int32 = 1
var portionIndex int32 = 1

mathMl, _, e := api.SlidesApi.DownloadMathPortion(fileName, slideIndex, shapeIndex, paragraphIndex, portionIndex, "MathML", "", "", "")
if e != nil {
    fmt.Printf("Error: %v.", e)
    return
}
fmt.Printf("The converted file was saved to  %v.", mathMl.Name())
```

{{< /tab >}}

{{< tab tabNum="8" >}}

{{< /tab >}}

{{< tab tabNum="9" >}}

{{< /tab >}}

{{< tab tabNum="10" >}}

{{< /tab >}}

{{< /tabs >}}

### **SDK Source**
The Aspose Cloud SDK's can be downloaded from the following page: [Available SDK's](/slides/available-sdks/)
