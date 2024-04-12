---
title: "Update Text Portions"
keywords: "PowerPoint, REST API, update text, format text, text formatting, text box, text color, bold font, italic font, font height"
type: docs
url: /update-text-portions-on-a-special-slide/
weight: 30
---

## **Introduction**

Aspose.Slides Cloud API allows you to read, add, modify and delete text portions from special slides (Master, Layout, Notes) in PowerPoint presentations. Use the following method to update a text portion within a paragraph.

## **UpdateSpecialSlidePortion**

### **API Information**

|**API**|**Type**|**Description**|**Resource**|
| :- | :- | :- | :- |
|/slides/{name}/slides/{slideIndex}/{slideType}/shapes/{shapeIndex}/paragraphs/{paragraphIndex}/portions/{portionIndex}|PUT|Updates a text portion within a paragraph in a shape located on a special slide in a presentation saved in a storage.|[UpdateSpecialSlidePortion](https://reference.aspose.cloud/slides/#/SpecialSlideShapes/UpdateSpecialSlidePortion)|

**Request Parameters**

|**Name**|**Type**|**Location**|**Required**|**Description**|
| :- | :- | :- | :- | :- |
|name|string|path|true|The name of a presentation file.|
|slideIndex|integer|path|true|The 1-based index of a regular slide.|
|slideType|`SpecialSlideType`|path|true|The type of a special slide.|
|shapeIndex|integer|path|true|The 1-based index of a shape.|
|paragraphIndex|integer|path|true|The 1-based index of a paragraph.|
|portionIndex|integer|path|true|The 1-based index of a text portion.|
|dto|`Portion`|body|true|The data transfer object with parameters for the text portion.|
|password|string|header|false|The password to open the presentation.|
|folder|string|query|false|The path to the folder containing the presentation.|
|storage|string|query|false|The name of the storage contaning the folder.|
|subShape|string|query|false|The path to a child shape (e.g. "3", "3/shapes/2").|

### **Examples**

The document **MyPresentation.pptx** saved in the **default** storage contains two text boxes on the **Layout** of the **first** slide. The **second** text box contains three paragraphs. Set the following options for the **second** text portion in the **third** paragraph:
- font: Times New Roman
- font size: 32

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

**Update the Text Portion**

```sh
curl -X PUT "https://api.aspose.cloud/v3.0/slides/MyPresentation.pptx/slides/1/LayoutSlide/shapes/2/paragraphs/3/portions/2" \
     -H "authorization: Bearer MyAccessToken" \
     -H "Content-Type: application/json" \
     -d @TextPortion.json
```

TextPortion.json content:
```json
{
  "LatinFont": "Times New Roman",
  "FontHeight": 32
}
```

{{< /tab >}}

{{< tab tabNum="2" >}}

**Response Example**

```json
{
  "text": "the second text portion.",
  "fontItalic": "True",
  "fontColor": "#FFFF0000",
  "highlightColor": "#0",
  "fontHeight": 32,
  "languageId": "en-US",
  "fillFormat": {
    "type": "Solid",
    "color": "#FFFF0000"
  },
  "latinFont": "Times New Roman",
  "selfUri": {
    "href": "https://api.aspose.cloud/v3.0/slides/MyPresentation.pptx/layoutSlides/1/shapes/2/paragraphs/3/portions/2",
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
        int paragraphIndex = 3;
        int portionIndex = 2;

        Portion textPortion = new Portion
        {
            LatinFont = "Times New Roman",
            FontHeight = 32
        };

        Portion updatedPortion = slidesApi.UpdateSpecialSlidePortion(fileName, slideIndex, slideType, shapeIndex, paragraphIndex, portionIndex, textPortion);

        Console.WriteLine("Font name: " + updatedPortion.LatinFont);  // Times New Roman
        Console.WriteLine("Font size: " + updatedPortion.FontHeight); // 32
    }
}
```

{{< /tab >}}

{{< tab tabNum="2" >}}

```java
import com.aspose.slides.ApiException;
import com.aspose.slides.api.SlidesApi;
import com.aspose.slides.model.Portion;
import com.aspose.slides.model.SpecialSlideType;

public class Application {
    public static void main(String[] args) throws ApiException {
        SlidesApi slidesApi = new SlidesApi("MyClientId", "MyClientSecret");

        String fileName = "MyPresentation.pptx";
        int slideIndex = 1;
        SpecialSlideType slideType = SpecialSlideType.LAYOUTSLIDE;
        int shapeIndex = 2;
        int paragraphIndex = 3;
        int portionIndex = 2;

        Portion textPortion = new Portion();
        textPortion.setLatinFont("Times New Roman");
        textPortion.setFontHeight(32d);

        Portion updatedPortion = slidesApi.updateSpecialSlidePortion(fileName, slideIndex, slideType, shapeIndex, paragraphIndex, portionIndex, textPortion, null, null, null, null);

        System.out.println("Font name: " + updatedPortion.getLatinFont());  // Times New Roman
        System.out.println("Font size: " + updatedPortion.getFontHeight()); // 32
    }
}
```

{{< /tab >}}

{{< tab tabNum="3" >}}

```php
use Aspose\Slides\Cloud\Sdk\Api\Configuration;
use Aspose\Slides\Cloud\Sdk\Api\SlidesApi;
use Aspose\Slides\Cloud\Sdk\Model\SpecialSlideType;
use Aspose\Slides\Cloud\Sdk\Model\Portion;

$configuration = new Configuration();
$configuration->setAppSid("MyClientId");
$configuration->setAppKey("MyClientSecret");

$slidesApi = new SlidesApi(null, $configuration);

$fileName = "MyPresentation.pptx";
$slideIndex = 1;
$slideType = SpecialSlideType::LAYOUT_SLIDE;
$shapeIndex = 2;
$paragraphIndex = 3;
$portionIndex = 2;

$textPortion = new Portion();
$textPortion->setLatinFont("Times New Roman");
$textPortion->setFontHeight(32);

$updatedPortion = $slidesApi->updateSpecialSlidePortion($fileName, $slideIndex, $slideType, $shapeIndex, $paragraphIndex, $portionIndex, $textPortion);

echo "Font name: ", $updatedPortion->getLatinFont(), "\n"; // Times New Roman
echo "Font size: ", $updatedPortion->getFontHeight();      // 32
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
paragraph_index = 3
portion_index = 2

text_portion = Portion.new
text_portion.latin_font = "Times New Roman"
text_portion.font_height = 32

updated_portion = slides_api.update_special_slide_portion(file_name, slide_index, slide_type, shape_index, paragraph_index, portion_index, text_portion)

puts "Font name: #{updated_portion.latin_font}"  # Times New Roman
puts "Font size: #{updated_portion.font_height}" # 32
```

{{< /tab >}}

{{< tab tabNum="5" >}}

```python
from asposeslidescloud.apis import SlidesApi
from asposeslidescloud.models import SpecialSlideType
from asposeslidescloud.models import Portion

slides_api = SlidesApi(None, "MyClientId", "MyClientSecret")

file_name = "MyPresentation.pptx"
slide_index = 1
slide_type = SpecialSlideType.LAYOUTSLIDE
shape_index = 2
paragraph_index = 3
portion_index = 2

text_portion = Portion()
text_portion.latin_font = "Times New Roman"
text_portion.font_height = 32

updated_portion = slides_api.update_special_slide_portion(file_name, slide_index, slide_type, shape_index, paragraph_index, portion_index, text_portion)

print("Font name:", updated_portion.latin_font)   # Times New Roman
print("Font size:", updated_portion.font_height)  # 32
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
paragraphIndex = 3;
portionIndex = 2;

textPortion = new cloudSdk.Portion();
textPortion.latinFont = "Times New Roman";
textPortion.fontHeight = 32;

slidesApi.updateSpecialSlidePortion(fileName, slideIndex, slideType, shapeIndex, paragraphIndex, portionIndex, textPortion).then(updatedPortion => {
    console.log("Font name:", updatedPortion.body.latinFont);  // Times New Roman
    console.log("Font size:", updatedPortion.body.fontHeight); // 32
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
    int paragraphIndex = 3;
    int portionIndex = 2;

    std::shared_ptr<Portion> textPortion = std::make_shared<Portion>();
    textPortion->setLatinFont(L"Times New Roman");
    textPortion->setFontHeight(32);

    std::shared_ptr<Portion> updatedPortion = slidesApi->updateSpecialSlidePortion(fileName, slideIndex, slideType, shapeIndex, paragraphIndex, portionIndex, textPortion).get();

    std::wcout << L"Font name: " << updatedPortion->getLatinFont() << L"\n"; // Times New Roman
    std::wcout << L"Font size: " << updatedPortion->getFontHeight();         // 32
}
```

{{< /tab >}}

{{< tab tabNum="8" >}}

```perl
use AsposeSlidesCloud::Configuration;
use AsposeSlidesCloud::SlidesApi;
use AsposeSlidesCloud::Object::Portion;

my $configuration = AsposeSlidesCloud::Configuration->new();
$configuration->{app_sid} = "MyClientId";
$configuration->{app_key} = "MyClientSecret";

my $slides_api = AsposeSlidesCloud::SlidesApi->new(config => $configuration);

my $file_name = "MyPresentation.pptx";
my $slide_index = 1;
my $slide_type = "LayoutSlide";
my $shape_index = 2;
my $paragraph_index = 3;
my $portion_index = 2;

my $text_portion = AsposeSlidesCloud::Object::Portion->new();
$text_portion->{latin_font} = "Times New Roman";
$text_portion->{font_height} = 32;

my $updated_portion = $slides_api->update_special_slide_portion(
    name => $file_name, slide_index => $slide_index, slide_type => $slide_type, shape_index => $shape_index, paragraph_index => $paragraph_index, portion_index => $portion_index, dto => $text_portion);

print("Font name: ", $updated_portion->{latin_font}, "\n"); # Times New Roman
print("Font size: ", $updated_portion->{font_height});      # 32
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
	var paragraphIndex int32 = 3
	var portionIndex int32 = 2

	textPortion := asposeslidescloud.NewPortion()
	textPortion.LatinFont = "Times New Roman"
	textPortion.FontHeight = 32

	updatedPortion, _, _ := slidesApi.UpdateSpecialSlidePortion(fileName, slideIndex, slideType, shapeIndex, paragraphIndex, portionIndex, textPortion, "", "", "", "")

	fmt.Println("Font name:", updatedPortion.GetLatinFont())  // Times New Roman
	fmt.Println("Font size:", updatedPortion.GetFontHeight()) // 32
}
```

{{< /tab >}}

{{< /tabs >}}

The result:

![Layout slide](output.png)

## **SDKs**

Check [Available SDKs](/slides/available-sdks/) to learn how to add an SDK to your project.
