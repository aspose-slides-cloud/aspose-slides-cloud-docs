---
title: "Delete Text Portions"
keywords:
- PowerPoint
- REST API
- cloud API
- text box
- delete text
- format text
- text formatting
type: docs
url: /delete-text-portions-on-a-special-slide/
weight: 40
---

## **Introduction**

Aspose.Slides Cloud API allows you to read, add, and modify text portions on special slides (Master, Layout, Notes) in PowerPoint presentations. Use the following methods to delete text portions within paragraphs.

## **DeleteSpecialSlidePortions**

### **API Information**

|**API**|**Type**|**Description**|**Resource**|
| :- | :- | :- | :- |
|/slides/{name}/slides/{slideIndex}/{slideType}/shapes/{shapeIndex}/paragraphs/{paragraphIndex}/portions|DELETE|Deletes text portions from a paragraph in a shape located on a special slide in a presentation saved in a storage.|[DeleteSpecialSlidePortions](https://reference.aspose.cloud/slides/#/SpecialSlideShapes/DeleteSpecialSlidePortions)|

**Request Parameters**

|**Name**|**Type**|**Location**|**Required**|**Description**|
| :- | :- | :- | :- | :- |
|name|string|path|true|The name of a presentation file.|
|slideIndex|integer|path|true|The 1-based index of a regular slide.|
|slideType|`SpecialSlideType`|path|true|The type of a special slide.|
|shapeIndex|integer|path|true|The 1-based index of a shape.|
|paragraphIndex|integer|path|true|The 1-based index of a paragraph.|
|portions|string|query|false|The indices of the text portions to be deleted. Delete all by default.|
|password|string|header|false|The password to open the presentation.|
|folder|string|query|false|The path to the folder containing the presentation.|
|storage|string|query|false|The name of the storage contaning the folder.|
|subShape|string|query|false|The path to a child shape (e.g. "3", "3/shapes/2").|

## **DeleteSpecialSlidePortion**

### **API Information**

|**API**|**Type**|**Description**|**Resource**|
| :- | :- | :- | :- |
|/slides/{name}/slides/{slideIndex}/{slideType}/shapes/{shapeIndex}/paragraphs/{paragraphIndex}/portions/{portionIndex}|DELETE|Deletes a text portion from a paragraph in a shape located on a special slide in a presentation saved in a storage.|[DeleteSpecialSlidePortion](https://reference.aspose.cloud/slides/#/SpecialSlideShapes/DeleteSpecialSlidePortion)|

**Request Parameters**

|**Name**|**Type**|**Location**|**Required**|**Description**|
| :- | :- | :- | :- | :- |
|name|string|path|true|The name of a presentation file.|
|slideIndex|integer|path|true|The 1-based index of a regular slide.|
|slideType|`SpecialSlideType`|path|true|The type of a special slide.|
|shapeIndex|integer|path|true|The 1-based index of a shape.|
|paragraphIndex|integer|path|true|The 1-based index of a paragraph.|
|portionIndex|integer|path|true|The 1-based index of a text portion to be deleted.|
|password|string|header|false|The password to open the presentation.|
|folder|string|query|false|The path to the folder containing the presentation.|
|storage|string|query|false|The name of the storage contaning the folder.|
|subShape|string|query|false|The path to a child shape (e.g. "3", "3/shapes/2").|

### **Examples**

The document **MyPresentation.pptx** saved in the **default** storage contains two text boxes on the **Layout** of the **first** slide. The **second** text box contains three paragraphs. Delete the **first** text portion from the **first** paragraph.

![Layout slide](input.png)

**cURL Solution**

{{< tabs tabTotal="2" tabID="1" tabName1="Request" tabName2="Response" >}}

{{< tab tabNum="1" >}}

**Get an Access Token**

```sh
curl POST "https://api.aspose.cloud/connect/token" \
     -d "grant_type=client_credentials&client_id=MyClientId&client_secret=MyClientSecret" \
     -H "Content-Type: application/x-www-form-urlencoded"
```

**Delete the Text Portion**

```sh
curl -X DELETE "https://api.aspose.cloud/v3.0/slides/MyPresentation.pptx/slides/1/LayoutSlide/shapes/2/paragraphs/1/portions/1" \
     -H "authorization: Bearer MyAccessToken"
```

{{< /tab >}}

{{< tab tabNum="2" >}}

**Response Example**

```json
{
  "items": [
    {
      "text": "The third paragraph",
      "highlightColor": "#0",
      "fontHeight": "NaN",
      "languageId": "en-US",
      "selfUri": {
        "href": "https://api.aspose.cloud/v3.0/slides/MyPresentation.pptx/layoutSlides/1/shapes/2/paragraphs/1/portions/1",
        "relation": "self",
        "shapeIndex": 2
      }
    },
    {
      "text": ".",
      "highlightColor": "#0",
      "fontHeight": "NaN",
      "languageId": "en-US",
      "selfUri": {
        "href": "https://api.aspose.cloud/v3.0/slides/MyPresentation.pptx/layoutSlides/1/shapes/2/paragraphs/1/portions/1",
        "relation": "self",
        "shapeIndex": 2
      }
    }
  ],
  "selfUri": {
    "href": "https://api.aspose.cloud/v3.0/slides/MyPresentation.pptx/layoutSlides/1/shapes/1/paragraphs/1/portions",
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
        SpecialSlideType slideType = SpecialSlideType.LayoutSlide;
        int shapeIndex = 2;
        int paragraphIndex = 1;
        int portionIndex = 1;

        Portions textPortions = slidesApi.DeleteSpecialSlidePortion(fileName, slideIndex, slideType, shapeIndex, paragraphIndex, portionIndex);

        int portionCount = textPortions.Items.Count;
        Console.WriteLine("Number of text portions: " + portionCount); // 2
    }
}
```

{{< /tab >}}

{{< tab tabNum="2" >}}

```java
import com.aspose.slides.ApiException;
import com.aspose.slides.api.SlidesApi;
import com.aspose.slides.model.Portions;
import com.aspose.slides.model.SpecialSlideType;

public class Application {
    public static void main(String[] args) throws ApiException {
        SlidesApi slidesApi = new SlidesApi("MyClientId", "MyClientSecret");

        String fileName = "MyPresentation.pptx";
        int slideIndex = 1;
        SpecialSlideType slideType = SpecialSlideType.LAYOUTSLIDE;
        int shapeIndex = 2;
        int paragraphIndex = 1;
        int portionIndex = 1;

        Portions textPortions = slidesApi.deleteSpecialSlidePortion(fileName, slideIndex, slideType, shapeIndex, paragraphIndex, portionIndex, null, null, null, null);

        int portionCount = textPortions.getItems().size();
        System.out.println("Number of text portions: " + portionCount); // 2
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
$slideType = SpecialSlideType::LAYOUT_SLIDE;
$shapeIndex = 2;
$paragraphIndex = 1;
$portionIndex = 1;

$textPortions = $slidesApi->deleteSpecialSlidePortion($fileName, $slideIndex, $slideType, $shapeIndex, $paragraphIndex, $portionIndex);

$portionCount = count($textPortions->getItems());
echo "Number of text portions: ", $portionCount; // 2
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
slide_type = SpecialSlideType::LAYOUT_SLIDE
shape_index = 2
paragraph_index = 1
portion_index = 1

text_portions = slides_api.delete_special_slide_portion(file_name, slide_index, slide_type, shape_index, paragraph_index, portion_index)

portion_count = text_portions.items.length()
print "Number of text portions: ", portion_count # 2
```

{{< /tab >}}

{{< tab tabNum="5" >}}

```python
from asposeslidescloud.apis import SlidesApi
from asposeslidescloud.models import SpecialSlideType

slides_api = SlidesApi(None, "MyClientId", "MyClientSecret")

file_name = "MyPresentation.pptx"
slide_index = 1
slide_type = SpecialSlideType.LAYOUTSLIDE
shape_index = 2
paragraph_index = 1
portion_index = 1

text_portions = slides_api.delete_special_slide_portion(file_name, slide_index, slide_type, shape_index, paragraph_index, portion_index)

portion_count = len(text_portions.items)
print("Number of text portions:", portion_count)  # 2
```

{{< /tab >}}

{{< tab tabNum="6" >}}

```js
const cloudSdk = require("asposeslidescloud");

const slidesApi = new cloudSdk.SlidesApi("MyClientId", "MyClientSecret");

fileName = "MyPresentation.pptx";
slideIndex = 1;
slideType = cloudSdk.SpecialSlideType.LayoutSlide;
shapeIndex = 2;
paragraphIndex = 1;
portionIndex = 1;

slidesApi.deleteSpecialSlidePortion(fileName, slideIndex, slideType, shapeIndex, paragraphIndex, portionIndex).then(textPortions => {
    portionCount = textPortions.body.items.length;
    console.log("Number of text portions:", portionCount); // 2
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
    const wchar_t* slideType = L"LayoutSlide";
    int shapeIndex = 2;
    int paragraphIndex = 1;
    int portionIndex = 1;

    std::shared_ptr<Portions> textPortions = slidesApi->deleteSpecialSlidePortion(fileName, slideIndex, slideType, shapeIndex, paragraphIndex, portionIndex).get();

    int portionCount = textPortions->getItems().size();
    std::wcout << L"Number of text portions: " << portionCount; // 2
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
my $slide_type = "LayoutSlide";
my $shape_index = 2;
my $paragraph_index = 1;
my $portion_index = 1;

my $text_portions = $slides_api->delete_special_slide_portion(
    name => $file_name, slide_index => $slide_index, slide_type => $slide_type, shape_index => $shape_index, paragraph_index => $paragraph_index, portion_index => $portion_index);

my $portion_count = @{$text_portions->{items}};
print("Number of text portions: ", $portion_count); # 2
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
	slideType := string(asposeslidescloud.SpecialSlideType_LayoutSlide)
	var shapeIndex int32 = 2
	var paragraphIndex int32 = 1
	var portionIndex int32 = 1

	textPortions, _, _ := slidesApi.DeleteSpecialSlidePortion(fileName, slideIndex, slideType, shapeIndex, paragraphIndex, portionIndex, "", "", "", "")

	portionCount := len(textPortions.GetItems())
	fmt.Println("Number of text portions:", portionCount) // 2
}
```

{{< /tab >}}

{{< /tabs >}}

The result:

![Layout slide](output.png)

## **SDKs**

Check [Available SDKs](/slides/available-sdks/) to learn how to add an SDK to your project.
