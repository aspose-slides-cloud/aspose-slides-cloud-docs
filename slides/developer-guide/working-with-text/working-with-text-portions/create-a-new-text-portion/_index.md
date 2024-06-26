---
title: "Create a New Text Portion"
keywords:
- PowerPoint
- REST API
- cloud API
- add text
- format text
- text formatting
- text box
- text color
- bold font
- italic font
- font height
type: docs
url: /create-a-new-text-portion/
weight: 20
---

## **Introduction**

Aspose.Slides Cloud API allows you to read, add, modify and delete text portions from PowerPoint presentation slides. Use the following method to add new text portions to paragraphs.

## **CreatePortion**

### **API Information**

|**API**|**Type**|**Description**|**Resource**|
| :- | :- | :- | :- |
|/slides/{name}/slides/{slideIndex}/shapes/{shapeIndex}/paragraphs/{paragraphIndex}/portions|POST|Adds a new text portion to a paragraph in a shape located in a presentation saved in a storage.|[CreatePortion](https://reference.aspose.cloud/slides/#/Shapes/CreatePortion)|

**Request Parameters**

|**Name**|**Type**|**Location**|**Required**|**Description**|
| :- | :- | :- | :- | :- |
|name|string|path|true|The name of a presentation file.|
|slideIndex|integer|path|true|The 1-based index of a slide.|
|shapeIndex|integer|path|true|The 1-based index of a shape.|
|paragraphIndex|integer|path|true|The 1-based index of a paragraph.|
|dto|`Portion`|body|true|The data transfer object with parameters for a new text portion.|
|position|integer|query|false|The position of the new text portion in the list. By default, the text portion is added to the end of the list.|
|password|string|header|false|The password to open the presentation.|
|folder|string|query|false|The path to the folder containing the presentation file.|
|storage|string|query|false|The name of the storage contaning the folder.|
|subShape|string|query|false|The path to a child shape (e.g. "3", "3/shapes/2").|

### **Examples**

The document **MyPresentation.pptx** saved in the **default** storage contains two text boxes on the **first** slide. The **second** text box contains three paragraphs. Add text to the **third** paragraph with the following options:
- text: " The second text portion."
- set font to italic
- set font color to #FF4472C4

![Slide](input.png)

**cURL Solution**

{{< tabs tabTotal="2" tabID="1" tabName1="Request" tabName2="Response" >}}

{{< tab tabNum="1" >}}

**Get an Access Token**

```sh
curl POST "https://api.aspose.cloud/connect/token" \
     -d "grant_type=client_credentials&client_id=MyClientId&client_secret=MyClientSecret" \
     -H "Content-Type: application/x-www-form-urlencoded"
```

**Add the New Text Portion**

```sh
curl -X POST "https://api.aspose.cloud/v3.0/slides/MyPresentation.pptx/slides/1/shapes/2/paragraphs/3/portions" \
     -H "authorization: Bearer MyAccessToken" \
     -H "Content-Type: application/json" \
     -d @TextPortion.json
```

TextPortion.json content:
```json
{
  "Text": " The second text portion.",
  "FontItalic": "True",
  "FontColor": "#FF4472C4"
}
```

{{< /tab >}}

{{< tab tabNum="2" >}}

**Response Example**

```json
{
  "text": " The second text portion.",
  "fontItalic": "True",
  "fontColor": "#FF4472C4",
  "highlightColor": "#0",
  "fontHeight": "NaN",
  "fillFormat": {
    "type": "Solid",
    "color": "#FF4472C4"
  },
  "selfUri": {
    "href": "https://api.aspose.cloud/v3.0/slides/MyPresentation.pptx/slides/1/shapes/2/paragraphs/3/portions/2",
    "relation": "self",
    "slideIndex": 1,
    "shapeIndex": 2
  }
}
```

{{< /tab >}}

{{< /tabs >}}

**SDK Solutions**

{{< tabs tabTotal="10" tabID="11" tabName1="C#" tabName2="Java" tabName3="PHP" tabName4="Ruby" tabName5="Python" tabName6="Node.js" tabName7="C++" tabName8="Perl" tabName9="Swift" tabName10="Go" >}}

{{< tab tabNum="1" >}}

```cs
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
        int shapeIndex = 2;
        int paragraphIndex = 3;

        Portion textPortion = new Portion
        {
            Text = " The second text portion.",
            FontItalic = Portion.FontItalicEnum.True,
            FontColor = "#FF4472C4"
        };

        Portion newPortion = slidesApi.CreatePortion(fileName, slideIndex, shapeIndex, paragraphIndex, textPortion);

        Console.WriteLine("Italic font: " + newPortion.FontItalic); // True
        Console.WriteLine("Font color: " + newPortion.FontColor);   // #FF4472C4
    }
}
```

{{< /tab >}}

{{< tab tabNum="2" >}}

```java
import com.aspose.slides.ApiException;
import com.aspose.slides.api.SlidesApi;
import com.aspose.slides.model.Portion;

public class Application {
    public static void main(String[] args) throws ApiException {
        SlidesApi slidesApi = new SlidesApi("MyClientId", "MyClientSecret");

        String fileName = "MyPresentation.pptx";
        int slideIndex = 1;
        int shapeIndex = 2;
        int paragraphIndex = 3;

        Portion textPortion = new Portion();
        textPortion.setText(" The second text portion.");
        textPortion.setFontItalic(Portion.FontItalicEnum.TRUE);
        textPortion.setFontColor("#FF4472C4");

        Portion newPortion = slidesApi.createPortion(fileName, slideIndex, shapeIndex, paragraphIndex, textPortion, null, null, null, null, null);

        System.out.println("Italic font: " + newPortion.getFontItalic()); // True
        System.out.println("Font color: " + newPortion.getFontColor());   // #FF4472C4
    }
}
```

{{< /tab >}}

{{< tab tabNum="3" >}}

```php
use Aspose\Slides\Cloud\Sdk\Api\Configuration;
use Aspose\Slides\Cloud\Sdk\Api\SlidesApi;
use Aspose\Slides\Cloud\Sdk\Model\Portion;

$configuration = new Configuration();
$configuration->setAppSid("MyClientId");
$configuration->setAppKey("MyClientSecret");

$slidesApi = new SlidesApi(null, $configuration);

$fileName = "MyPresentation.pptx";
$slideIndex = 1;
$shapeIndex = 2;
$paragraphIndex = 3;

$textPortion = new Portion();
$textPortion->setText(" The second text portion.");
$textPortion->setFontItalic(Portion::FONT_ITALIC_TRUE);
$textPortion->setFontColor("#FF4472C4");

$newPortion = $slidesApi->createPortion($fileName, $slideIndex, $shapeIndex, $paragraphIndex, $textPortion);

echo "Italic font: ", $newPortion->getFontItalic(), "\n"; // True
echo "Font color: ", $newPortion->getFontColor();         // #FF4472C4
```

{{< /tab >}}

{{< tab tabNum="4" >}}

```rb
require "aspose_slides_cloud"

include AsposeSlidesCloud

configuration = Configuration.new
configuration.app_sid = "MyClientId"
configuration.app_key = "MyClientSecret"

slides_api = SlidesApi.new(configuration)

file_name = "MyPresentation.pptx"
slide_index = 1
shape_index = 2
paragraph_index = 3

text_portion = Portion.new
text_portion.text = " The second text portion."
text_portion.font_italic = "True"
text_portion.font_color = "#FF4472C4"

new_portion = slides_api.create_portion(file_name, slide_index, shape_index, paragraph_index, text_portion)

puts "Italic font: #{new_portion.font_italic}" # True
puts "Font color: #{new_portion.font_color}"   # #FF4472C4
```

{{< /tab >}}

{{< tab tabNum="5" >}}

```py
from asposeslidescloud.apis import SlidesApi
from asposeslidescloud.models import Portion

slides_api = SlidesApi(None, "MyClientId", "MyClientSecret")

file_name = "MyPresentation.pptx"
slide_index = 1
shape_index = 2
paragraph_index = 3

text_portion = Portion()
text_portion.text = " The second text portion."
text_portion.font_italic = "True"
text_portion.font_color = "#FF4472C4"

new_portion = slides_api.create_portion(file_name, slide_index, shape_index, paragraph_index, text_portion)

print("Italic font:", new_portion.font_italic)  # True
print("Font color:", new_portion.font_color)    # #FF4472C4
```

{{< /tab >}}

{{< tab tabNum="6" >}}

```js
const cloudSdk = require("asposeslidescloud");

const slidesApi = new cloudSdk.SlidesApi("MyClientId", "MyClientSecret");

fileName = "MyPresentation.pptx";
slideIndex = 1;
shapeIndex = 2;
paragraphIndex = 3;

textPortion = new cloudSdk.Portion();
textPortion.text = " The second text portion.";
textPortion.fontItalic = cloudSdk.Portion.FontItalicEnum.True;
textPortion.fontColor = "#FF4472C4";

slidesApi.createPortion(fileName, slideIndex, shapeIndex, paragraphIndex, textPortion).then(newPortion => {
    console.log("Italic font:", newPortion.body.fontItalic); // True
    console.log("Font color:", newPortion.body.fontColor);   // #FF4472C4
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
    int shapeIndex = 2;
    int paragraphIndex = 3;

    std::shared_ptr<Portion> textPortion = std::make_shared<Portion>();
    textPortion->setText(L" The second text portion.");
    textPortion->setFontItalic(L"True");
    textPortion->setFontColor(L"#FF4472C4");

    std::shared_ptr<Portion> newPortion = slidesApi->createPortion(fileName, slideIndex, shapeIndex, paragraphIndex, textPortion).get();

    std::wcout << L"Italic font: " << newPortion->getFontItalic() << L"\n"; // True
    std::wcout << L"Font color: " << newPortion->getFontColor();            // #FF4472C4
}
```

{{< /tab >}}

{{< tab tabNum="8" >}}

```pl
use AsposeSlidesCloud::Configuration;
use AsposeSlidesCloud::SlidesApi;
use AsposeSlidesCloud::Object::Portion;

my $configuration = AsposeSlidesCloud::Configuration->new();
$configuration->{app_sid} = "MyClientId";
$configuration->{app_key} = "MyClientSecret";

my $slides_api = AsposeSlidesCloud::SlidesApi->new(config => $configuration);

my $file_name = "MyPresentation.pptx";
my $slide_index = 1;
my $shape_index = 2;
my $paragraph_index = 3;

my $text_portion = AsposeSlidesCloud::Object::Portion->new();
$text_portion->{text} = " The second text portion.";
$text_portion->{font_italic} = "True";
$text_portion->{font_color} = "#FF4472C4";

my $new_portion = $slides_api->create_portion(
    name => $file_name, slide_index => $slide_index, shape_index => $shape_index, paragraph_index => $paragraph_index, dto => $text_portion);

print("Italic font: ", $new_portion->{font_italic}, "\n"); # True
print("Font color: ", $new_portion->{font_color});         # #FF4472C4
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
	var shapeIndex int32 = 2
	var paragraphIndex int32 = 3

	textPortion := asposeslidescloud.NewPortion()
	textPortion.Text = " The second text portion."
	textPortion.FontItalic = "True"
	textPortion.FontColor = "#FF4472C4"

	newPortion, _, _ := slidesApi.CreatePortion(fileName, slideIndex, shapeIndex, paragraphIndex, textPortion, nil, "", "", "", "")

	fmt.Println("Italic font:", newPortion.GetFontItalic()) // True
	fmt.Println("Font color:", newPortion.GetFontColor())   // #FF4472C4
}
```

{{< /tab >}}

{{< /tabs >}}

The result:

![Slide](output.png)

## **SDKs**

Check [Available SDKs](/slides/available-sdks/) to learn how to add an SDK to your project.
