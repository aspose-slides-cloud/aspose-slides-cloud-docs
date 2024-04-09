---
title: "Delete Paragraphs"
type: docs
url: /delete-paragraphs-on-a-special-slide/
weight: 40
---

## **Introduction**

Aspose.Slides Cloud API allows you to read, add, modify and delete text paragraphs from shapes located on special slides (Master, Layout, Notes) in PowerPoint presentations. Use the following methods to delete paragraphs from presentation shapes.

## **DeleteSpecialSlideParagraphs**

### **API Information**

|**API**|**Type**|**Description**|**Resource**|
| :- | :- | :- | :- |
|/slides/{name}/slides/{slideIndex}/{slideType}/shapes/{shapeIndex}/paragraphs|DELETE|Deletes all paragraphs from a shape located on a special slide in a presentation saved in a storage.|[DeleteSpecialSlideParagraphs](https://reference.aspose.cloud/slides/#/SpecialSlideShapes/DeleteSpecialSlideParagraphs)|

**Request Parameters**

|**Name**|**Type**|**Location**|**Required**|**Description**|
| :- | :- | :- | :- | :- |
|name|string|path|true|The name of a presentation file.|
|slideIndex|integer|path|true|The 1-based index of a regular slide.|
|slideType|`SpecialSlideType`|path|true|The type of a special slide.|
|shapeIndex|integer|path|true|The 1-based index of a shape.|
|paragraphs|string|query|false|The indices of the paragraphs to be deleted. Delete all by default.|
|password|string|header|false|The password to open the presentation.|
|folder|string|query|false|The path to the folder containing the presentation file.|
|storage|string|query|false|The name of the storage contaning the folder.|
|subShape|string|query|false|The path to a child shape (e.g. "3", "3/shapes/2").|

## **DeleteSpecialSlideParagraph**

### **API Information**

|**API**|**Type**|**Description**|**Resource**|
| :- | :- | :- | :- |
|/slides/{name}/slides/{slideIndex}/{slideType}/shapes/{shapeIndex}/paragraphs/{paragraphIndex}|DELETE|Deletes a paragraph from a shape located on a special slide in a presentation saved in a storage.|[DeleteSpecialSlideParagraph](https://reference.aspose.cloud/slides/#/SpecialSlideShapes/DeleteSpecialSlideParagraph)|

**Request Parameters**

|**Name**|**Type**|**Location**|**Required**|**Description**|
| :- | :- | :- | :- | :- |
|name|string|path|true|The name of a presentation file.|
|slideIndex|integer|path|true|The 1-based index of a regular slide.|
|slideType|`SpecialSlideType`|path|true|The type of a special slide.|
|shapeIndex|integer|path|true|The 1-based index of a shape.|
|paragraphIndex|integer|path|true|The 1-based index of a paragraph to be deleted.|
|password|string|header|false|The password to open the presentation.|
|folder|string|query|false|The path to the folder containing the presentation.|
|storage|string|query|false|The name of the storage contaning the folder.|
|subShape|string|query|false|The path to a child shape (e.g. "3", "3/shapes/2").|

### **Examples**

The document **MyPresentation.pptx** saved in the **default** storage contains two text boxes on the **Master** of the **first** slide. The **second** text box contains four paragraphs. Delete the **third** paragraph.

![Master Slide](input.png)

**cURL Solution**

{{< tabs tabTotal="2" tabID="1" tabName1="Request" tabName2="Response" >}}

{{< tab tabNum="1" >}}

**Get an Access Token**

```sh
curl POST "https://api.aspose.cloud/connect/token" \
     -d "grant_type=client_credentials&client_id=MyClientId&client_secret=MyClientSecret" \
     -H "Content-Type: application/x-www-form-urlencoded"
```

**Delete the Paragraph**

```sh
curl -X DELETE "https://api.aspose.cloud/v3.0/slides/MyPresentation.pptx/slides/1/MasterSlide/shapes/2/paragraphs/3" \
     -H "authorization: Bearer MyAccessToken"
```

{{< /tab >}}

{{< tab tabNum="2" >}}

**Response Example**

```json
{
  "paragraphLinks": [
    {
      "href": "https://api.aspose.cloud/v3.0/slides/MyPresentation.pptx/masterSlides/1/shapes/2/paragraphs/1",
      "relation": "self",
      "shapeIndex": 2
    },
    {
      "href": "https://api.aspose.cloud/v3.0/slides/MyPresentation.pptx/masterSlides/1/shapes/2/paragraphs/2",
      "relation": "self",
      "shapeIndex": 2
    },
    {
      "href": "https://api.aspose.cloud/v3.0/slides/MyPresentation.pptx/masterSlides/1/shapes/2/paragraphs/3",
      "relation": "self",
      "shapeIndex": 2
    }
  ],
  "selfUri": {
    "href": "https://api.aspose.cloud/v3.0/slides/MyPresentation.pptx/masterSlides/1/shapes/2/paragraphs",
    "relation": "self",
    "shapeIndex": 2
  }
}
```

{{< /tab >}}

{{< /tabs >}}

**SDK Solutions**

{{< tabs tabTotal="10" tabID="11" tabName1="C#" tabName2="Java" tabName3="PHP" tabName4="Ruby" tabName5="Python" tabName6="Node.js" tabName7="C++" tabName8="Perl" tabName9="Swift" tabName10="Go" >}}

{{< tab tabNum="1" >}}

```csharp
using System;

using Aspose.Slides.Cloud.Sdk;
using Aspose.Slides.Cloud.Sdk.Model;

class Application
{
    static void Main(string[] args)
    {
        SlidesApi slidesApi = new SlidesApi("MyClientId", "MyClientSecret");

        string fileName = "MyPresentation.pptx";
        int slideIndex = 1;
        SpecialSlideType slideType = SpecialSlideType.MasterSlide;
        int shapeIndex = 2;
        int paragraphIndex = 3;

        Paragraphs paragraps = slidesApi.DeleteSpecialSlideParagraph(fileName, slideIndex, slideType, shapeIndex, paragraphIndex);

        int paragraphCount = paragraps.ParagraphLinks.Count;
        Console.WriteLine("Paragraph count: " + paragraphCount); // 3
    }
}
```

{{< /tab >}}

{{< tab tabNum="2" >}}

```java
import com.aspose.slides.ApiException;
import com.aspose.slides.api.SlidesApi;
import com.aspose.slides.model.Paragraphs;
import com.aspose.slides.model.SpecialSlideType;

public class Application {
    public static void main(String[] args) throws ApiException {
        SlidesApi slidesApi = new SlidesApi("MyClientId", "MyClientSecret");

        String fileName = "MyPresentation.pptx";
        int slideIndex = 1;
        SpecialSlideType slideType = SpecialSlideType.MASTERSLIDE;
        int shapeIndex = 2;
        int paragraphIndex = 3;

        Paragraphs paragraphs = slidesApi.deleteSpecialSlideParagraph(fileName, slideIndex, slideType, shapeIndex, paragraphIndex, null, null, null, null);

        int paragraphCount = paragraphs.getParagraphLinks().size();
        System.out.println("Paragraph count: " + paragraphCount); // 3
    }
}
```

{{< /tab >}}

{{< tab tabNum="3" >}}

```php
use Aspose\Slides\Cloud\Sdk\Api\Configuration;
use Aspose\Slides\Cloud\Sdk\Api\SlidesApi;
use Aspose\Slides\Cloud\Sdk\Model\SpecialSlideType;

$configuration = new Configuration();
$configuration->setAppSid("MyClientId");
$configuration->setAppKey("MyClientSecret");

$slidesApi = new SlidesApi(null, $configuration);

$fileName = "MyPresentation.pptx";
$slideIndex = 1;
$slideType = SpecialSlideType::MASTER_SLIDE;
$shapeIndex = 2;
$paragraphIndex = 3;

$paragraphs = $slidesApi->deleteSpecialSlideParagraph($fileName, $slideIndex, $slideType, $shapeIndex, $paragraphIndex);

$paragraphCount = count($paragraphs->getParagraphLinks());
echo "Paragraph count: ", $paragraphCount; // 3
```

{{< /tab >}}

{{< tab tabNum="4" >}}

```ruby
require "aspose_slides_cloud"

include AsposeSlidesCloud

configuration = Configuration.new
configuration.app_sid = "MyClientId"
configuration.app_key = "MyClientSecret"

slides_api = SlidesApi.new(configuration)

file_name = "MyPresentation.pptx"
slide_index = 1
slide_type = SpecialSlideType::MASTER_SLIDE
shape_index = 2
paragraph_index = 3

paragraphs = slides_api.delete_special_slide_paragraph(file_name, slide_index, slide_type, shape_index, paragraph_index)

paragraph_count = paragraphs.paragraph_links.length()
print "Paragraph count: ", paragraph_count # 3
```

{{< /tab >}}

{{< tab tabNum="5" >}}

```python
from asposeslidescloud.apis import SlidesApi
from asposeslidescloud.models import SpecialSlideType

slides_api = SlidesApi(None, "MyClientId", "MyClientSecret")

file_name = "MyPresentation.pptx"
slide_index = 1
slide_type = SpecialSlideType.MASTERSLIDE
shape_index = 2
paragraph_index = 3

paragraphs = slides_api.delete_special_slide_paragraph(file_name, slide_index, slide_type, shape_index, paragraph_index)

paragraph_count = len(paragraphs.paragraph_links)
print("Paragraph count:", paragraph_count)  # 3
```

{{< /tab >}}

{{< tab tabNum="6" >}}

```js
const cloudSdk = require("asposeslidescloud");

const slidesApi = new cloudSdk.SlidesApi("MyClientId", "MyClientSecret");

fileName = "MyPresentation.pptx";
slideIndex = 1;
slideType = cloudSdk.SpecialSlideType.MasterSlide;
shapeIndex = 2;
paragraphIndex = 3;

slidesApi.deleteSpecialSlideParagraph(fileName, slideIndex, slideType, shapeIndex, paragraphIndex).then(paragraphs => {
    paragraphCount = paragraphs.body.paragraphLinks.length;
    console.log("Paragraph count:", paragraphCount); // 3
});
```

{{< /tab >}}

{{< tab tabNum="7" >}}

```cpp
#include "asposeslidescloud/api/SlidesApi.h"

using namespace asposeslidescloud::api;

int main()
{
    std::shared_ptr<SlidesApi> slidesApi = std::make_shared<SlidesApi>(L"MyClientId", L"MyClientSecret");

    const wchar_t* fileName = L"MyPresentation.pptx";
    int slideIndex = 1;
    const wchar_t* slideType = L"MasterSlide";
    int shapeIndex = 2;
    int paragraphIndex = 3;

    std::shared_ptr<Paragraphs> paragraphs = slidesApi->deleteSpecialSlideParagraph(fileName, slideIndex, slideType, shapeIndex, paragraphIndex).get();

    int paragraphCount = paragraphs->getParagraphLinks().size();
    std::wcout << L"Paragraph count: " << paragraphCount; // 3
}
```

{{< /tab >}}

{{< tab tabNum="8" >}}

```perl
use AsposeSlidesCloud::Configuration;
use AsposeSlidesCloud::SlidesApi;

my $configuration = AsposeSlidesCloud::Configuration->new();
$configuration->{app_sid} = "MyClientId";
$configuration->{app_key} = "MyClientSecret";

my $slides_api = AsposeSlidesCloud::SlidesApi->new(config => $configuration);

my $file_name = "MyPresentation.pptx";
my $slide_index = 1;
my $slide_type = "MasterSlide";
my $shape_index = 2;
my $paragraph_index = 3;

$paragraphs = $slides_api->delete_special_slide_paragraph(
    name => $file_name, slide_index => $slide_index, slide_type => $slide_type, shape_index => $shape_index, paragraph_index => $paragraph_index);

my $paragraph_count = @{$paragraphs->{paragraph_links}};
print("Paragraph count: ", $paragraph_count); # 3
```

{{< /tab >}}

{{< tab tabNum="9" >}}

{{< /tab >}}

{{< tab tabNum="10" >}}

```go
import (
	"fmt"

	asposeslidescloud "github.com/aspose-slides-cloud/aspose-slides-cloud-go/v24"
)

func main() {
	configuration := asposeslidescloud.NewConfiguration()
	configuration.AppSid = "MyClientId"
	configuration.AppKey = "MyClientSecret"

	slidesApi := asposeslidescloud.NewAPIClient(configuration).SlidesApi

	fileName := "MyPresentation.pptx"
	var slideIndex int32 = 1
	slideType := string(asposeslidescloud.SpecialSlideType_MasterSlide)
	var shapeIndex int32 = 2
	var paragraphIndex int32 = 3

	paragraphs, _, _ := slidesApi.DeleteSpecialSlideParagraph(fileName, slideIndex, slideType, shapeIndex, paragraphIndex, "", "", "", "")

	paragraphCount := len(paragraphs.GetParagraphLinks())
	fmt.Println("Paragraph count:", paragraphCount) // 3
}
```

{{< /tab >}}

{{< /tabs >}}

The result:

![Master Slide](output.png)

## **SDKs**

Check [Available SDKs](/slides/available-sdks/) to learn how to add an SDK to your project.
