---
title: "Working with Text Portions"
type: docs
url: /working-with-text-portions-on-a-special-slide/
weight: 30
---

## **Introduction**

Aspose.Slides Cloud API allows you to read, add, modify and delete text portions on special slides (Master, Layout, Notes) in a PowerPoint presentation. To do this, you can use the following set of methods, identical to those that work with regular slides.

## **API Information**

|**API**|**Type**|**Description**|**Resource**|
| :- | :- | :- | :- |
|/slides/{name}/slides/{slideIndex}/{slideType}/shapes/{shapeIndex}/paragraphs/{paragraphIndex}/portions|GET|Reads information about text portions in a paragraph in a shape on a special slide.|[GetSpecialSlidePortions](https://apireference.aspose.cloud/slides/#/SpecialSlideShapes/GetSpecialSlidePortions)|
|/slides/{name}/slides/{slideIndex}/{slideType}/shapes/{shapeIndex}/paragraphs/{paragraphIndex}/portions/{portionIndex}|GET|Reads information about a text portion in a paragraph in a shape on a special slide.|[GetSpecialSlidePortion](https://apireference.aspose.cloud/slides/#/SpecialSlideShapes/GetSpecialSlidePortion)|
|/slides/{name}/slides/{slideIndex}/{slideType}/shapes/{shapeIndex}/paragraphs/{paragraphIndex}/portions|POST|Adds a new text portion to a paragraph in a shape on a special slide.|[CreateSpecialSlidePortion](https://apireference.aspose.cloud/slides/#/SpecialSlideShapes/CreateSpecialSlidePortion)|
|/slides/{name}/slides/{slideIndex}/{slideType}/shapes/{shapeIndex}/paragraphs/{paragraphIndex}/portions/{portionIndex}|PUT|Updates a text portion in a paragraph in a shape on a special slide.|[UpdateSpecialSlidePortion](https://apireference.aspose.cloud/slides/#/SpecialSlideShapes/UpdateSpecialSlidePortion)|
|/slides/{name}/slides/{slideIndex}/{slideType}/shapes/{shapeIndex}/paragraphs/{paragraphIndex}/portions|DELETE|Deletes text portions from a paragraph in a shape on a special slide.|[DeleteSpecialSlidePortions](https://reference.aspose.cloud/slides/#/SpecialSlideShapes/DeleteSpecialSlidePortions)|
|/slides/{name}/slides/{slideIndex}/{slideType}/shapes/{shapeIndex}/paragraphs/{paragraphIndex}/portions/{portionIndex}|DELETE|Deletes a text portion from a paragraph in a shape on a special slide.|[DeleteSpecialSlidePortion](https://apireference.aspose.cloud/slides/#/SpecialSlideShapes/DeleteSpecialSlidePortion)|

{{< expand-list title="GetSpecialSlidePortions Request Parameters" >}}
|**Name**|**Type**|**Location**|**Required**|**Description**|
| :- | :- | :- | :- | :- |
|name|string|path|true|The name of a presentation file saved in a storage.|
|slideIndex|integer|path|true|The 1-based index of a regular slide.|
|slideType|`MasterSlide` or `LayoutSlide` or `NotesSlide`|path|true|The type of a special slide.|
|shapeIndex|integer|path|true|The 1-based index of a shape.|
|paragraphIndex|integer|path|true|The 1-based index of a paragraph.|
|password|string|header|false|The password to open the presentation.|
|folder|string|query|false|The path to a folder containing the presentation.|
|storage|string|query|false|The name of the storage contaning the folder.|
|subShape|string|query|false|The path to a child shape (e.g. "3", "3/shapes/2").|
{{< /expand-list >}}

{{< expand-list title="GetSpecialSlidePortion Request Parameters" >}}
|**Name**|**Type**|**Location**|**Required**|**Description**|
| :- | :- | :- | :- | :- |
|name|string|path|true|The name of a presentation file saved in a storage.|
|slideIndex|integer|path|true|The 1-based index of a regular slide.|
|slideType|`MasterSlide` or `LayoutSlide` or `NotesSlide`|path|true|The type of a special slide.|
|shapeIndex|integer|path|true|The 1-based index of a shape.|
|paragraphIndex|integer|path|true|The 1-based index of a paragraph.|
|portionIndex|integer|path|true|The 1-based index of a text portion.|
|password|string|header|false|The password to open the presentation.|
|folder|string|query|false|The path to a folder containing the presentation.|
|storage|string|query|false|The name of the storage contaning the folder.|
|subShape|string|query|false|The path to a child shape (e.g. "3", "3/shapes/2").|
{{< /expand-list >}}

{{< expand-list title="CreateSpecialSlidePortion Request Parameters" >}}
|**Name**|**Type**|**Location**|**Required**|**Description**|
| :- | :- | :- | :- | :- |
|name|string|path|true|The name of a presentation file saved in a storage.|
|slideIndex|integer|path|true|The 1-based index of a regular slide.|
|slideType|`MasterSlide` or `LayoutSlide` or `NotesSlide`|path|true|The type of a special slide.|
|shapeIndex|integer|path|true|The 1-based index of a shape.|
|paragraphIndex|integer|path|true|The 1-based index of a paragraph.|
|dto|`Portion`|body|true|The data transfer object with parameters for a new text portion.|
|position|integer|query|false|The position of the new text portion in the list. By default, the text portion is added to the end of the list.|
|password|string|header|false|The password to open the presentation.|
|folder|string|query|false|The path to a folder containing the presentation.|
|storage|string|query|false|The name of the storage contaning the folder.|
|subShape|string|query|false|The path to a child shape (e.g. "3", "3/shapes/2").|
{{< /expand-list >}}

{{< expand-list title="UpdateSpecialSlidePortion Request Parameters" >}}
|**Name**|**Type**|**Location**|**Required**|**Description**|
| :- | :- | :- | :- | :- |
|name|string|path|true|The name of a presentation file saved in a storage.|
|slideIndex|integer|path|true|The 1-based index of a regular slide.|
|slideType|`MasterSlide` or `LayoutSlide` or `NotesSlide`|path|true|The type of a special slide.|
|shapeIndex|integer|path|true|The 1-based index of a shape.|
|paragraphIndex|integer|path|true|The 1-based index of a paragraph.|
|portionIndex|integer|path|true|The 1-based index of a text portion.|
|dto|`Portion`|body|true|The data transfer object with parameters for the text portion.|
|password|string|header|false|The password to open the presentation.|
|folder|string|query|false|The path to a folder containing the presentation.|
|storage|string|query|false|The name of the storage contaning the folder.|
|subShape|string|query|false|The path to a child shape (e.g. "3", "3/shapes/2").|
{{< /expand-list >}}

{{< expand-list title="DeleteSpecialSlidePortions Request Parameters" >}}
|**Name**|**Type**|**Location**|**Required**|**Description**|
| :- | :- | :- | :- | :- |
|name|string|path|true|The name of a presentation file saved in a storage.|
|slideIndex|integer|path|true|The 1-based index of a regular slide.|
|slideType|`MasterSlide` or `LayoutSlide` or `NotesSlide`|path|true|The type of a special slide.|
|shapeIndex|integer|path|true|The 1-based index of a shape.|
|paragraphIndex|integer|path|true|The 1-based index of a paragraph.|
|portions|string|query|false|The indices of the text portions to be deleted. Delete all by default.|
|password|string|header|false|The password to open the presentation.|
|folder|string|query|false|The path to a folder containing the presentation.|
|storage|string|query|false|The name of the storage contaning the folder.|
|subShape|string|query|false|The path to a child shape (e.g. "3", "3/shapes/2").|
{{< /expand-list >}}

{{< expand-list title="DeleteSpecialSlidePortion Request Parameters" >}}
|**Name**|**Type**|**Location**|**Required**|**Description**|
| :- | :- | :- | :- | :- |
|name|string|path|true|The name of a presentation file saved in a storage.|
|slideIndex|integer|path|true|The 1-based index of a regular slide.|
|slideType|`MasterSlide` or `LayoutSlide` or `NotesSlide`|path|true|The type of a special slide.|
|shapeIndex|integer|path|true|The 1-based index of a shape.|
|paragraphIndex|integer|path|true|The 1-based index of a paragraph.|
|portionIndex|integer|path|true|The 1-based index of a text portion.|
|password|string|header|false|The password to open the presentation.|
|folder|string|query|false|The path to a folder containing the presentation.|
|storage|string|query|false|The name of the storage contaning the folder.|
|subShape|string|query|false|The path to a child shape (e.g. "3", "3/shapes/2").|
{{< /expand-list >}}

## **Examples**

The following examples demonstrate manipulating text portions on a Master slide. You can access text portions on a Layout or Notes slide the same way, just change the value of the **slideType** parameter accordingly.

**cURL Examples**

{{< tabs tabTotal="2" tabID="1" tabName1="Request" tabName2="Response" >}}

{{< tab tabNum="1" >}}

**Get an Access Token**

```sh
curl -X POST "https://api.aspose.cloud/connect/token" \
     -d "grant_type=client_credentials&client_id=MyClientId&client_secret=MyClientSecret" \
     -H "Content-Type: application/x-www-form-urlencoded"
```

**Get a Text Portion List**

```sh
curl -X GET "https://api.aspose.cloud/v3.0/slides/MyPresentation.pptx/slides/1/masterSlide/shapes/2/paragraphs/3/portions" \
     -H "authorization: Bearer MyAccessToken"
```

**Add a Text Portion**

```sh
curl -X POST "https://api.aspose.cloud/v3.0/slides/MyPresentation.pptx/slides/1/masterSlide/shapes/2/paragraphs/3/portions" \
     -H "authorization: Bearer MyAccessToken" \
     -d "@portion.json" \
     -H "Content-Type: text/json"
```

**Update the Text Portion**

```sh
curl -X PUT "https://api.aspose.cloud/v3.0/slides/MyPresentation.pptx/slides/1/masterSlide/shapes/2/paragraphs/3/portions/2" \
     -H "authorization: Bearer MyAccessToken" \
     -d "@portion.json" \
     -H "Content-Type: text/json"
```

**Delete the Text Portion**

```sh
curl -X DELETE "https://api.aspose.cloud/v3.0/slides/MyPresentation.pptx/slides/1/masterSlide/shapes/2/paragraphs/3/portions/2" \
     -H "authorization: Bearer MyAccessToken"
```

**portion.json example**

```json
{
    "fontBold": "True",
    "fontHeight": 22,
    "text": "New portion"
}
```

{{< /tab >}}

{{< tab tabNum="2" >}}

```json
{
    "text": "New portion",
    "fontBold": "True",
    "fontHeight":22.0,
    "selfUri": {
        "href": "https://api.aspose.cloud/v3.0/slides/MyPresentation.pptx/slides/1/masterSlide/shapes/2/paragraphs/3/portions/1",
        "relation": "self"
    }
}
```

{{< /tab >}}

{{< /tabs >}}

**SDK Examples**

{{< tabs tabTotal="10" tabID="5" tabName1="C#" tabName2="Java" tabName3="PHP" tabName4="Ruby" tabName5="Python" tabName6="Node.js" tabName7="Go" tabName8="C++" tabName9="Perl" tabName10="Swift" >}}

{{< tab tabNum="1" >}}

```csharp
SlidesApi api = new SlidesApi("MyClientId", "MyClientSecret");

string fileName = "MyPresentation.pptx";
int slideIndex = 1;
SpecialSlideType slideType = SpecialSlideType.MasterSlide;
int shapeIndex = 2;
int paragraphIndex = 3;

Portions portions = api.GetSpecialSlidePortions(fileName, slideIndex, slideType, shapeIndex, paragraphIndex);
int portionCount = portions.Items.Count;

Portion dto = new Portion
{
    FontBold = Portion.FontBoldEnum.True,
    Text = "New portion"
};

Portion portion = api.CreateSpecialSlidePortion(fileName, slideIndex, slideType, shapeIndex, paragraphIndex, dto);
Console.WriteLine(portion.FontBold); // True
Console.WriteLine(portion.Text); // New portion

dto = new Portion
{
    FontHeight = 22,
    Text = "Updated portion"
};

portion = api.UpdateSpecialSlidePortion(fileName, slideIndex, slideType, shapeIndex, paragraphIndex, portionCount + 1, dto);
Console.WriteLine(portion.FontBold); // True
Console.WriteLine(portion.FontHeight); // 22.0
Console.WriteLine(portion.Text); // Updated portion

api.DeleteSpecialSlidePortion(fileName, slideIndex, slideType, shapeIndex, paragraphIndex, portionCount + 1);
```

{{< /tab >}}

{{< tab tabNum="2" >}}

```java
SlidesApi api = new SlidesApi("MyClientId", "MyClientSecret");

String fileName = "MyPresentation.pptx";
int slideIndex = 1;
SpecialSlideType slideType = SpecialSlideType.MASTERSLIDE;
int shapeIndex = 2;
int paragraphIndex = 3;

Portions portions = api.getSpecialSlidePortions(fileName, slideIndex, slideType, shapeIndex, paragraphIndex, null, null, null, null);
int portionCount = portions.getItems().size();

Portion dto = new Portion();
dto.setFontBold(Portion.FontBoldEnum.TRUE);
dto.setText("New portion");

Portion portion = api.createSpecialSlidePortion(fileName, slideIndex, slideType, shapeIndex, paragraphIndex, dto, null, null, null, null, null);
System.out.println(portion.getFontBold()); // True
System.out.println(portion.getText()); // New portion

dto.setFontHeight(22.0);
dto.setText("Updated portion");

portion = api.updateSpecialSlidePortion(fileName, slideIndex, slideType, shapeIndex, paragraphIndex, portionCount + 1, dto, null, null, null, null);
System.out.println(portion.getFontBold()); // True
System.out.println(portion.getFontHeight()); // 22.0
System.out.println(portion.getText()); // Updated portion

api.deleteSpecialSlidePortion(fileName, slideIndex, slideType, shapeIndex, paragraphIndex, portionCount + 1, null, null, null, null);
```

{{< /tab >}}

{{< tab tabNum="3" >}}

```php
use Aspose\Slides\Cloud\Sdk\Api\Configuration;
use Aspose\Slides\Cloud\Sdk\Api\SlidesApi;
use Aspose\Slides\Cloud\Sdk\Model\Portion;
use Aspose\Slides\Cloud\Sdk\Model\SpecialSlideType;

$config = new Configuration();
$config->setAppSid("MyClientId");
$config->setAppKey("MyClientSecret");

$api = new SlidesApi(null, $config);

$fileName = "MyPresentation.pptx";
$slideIndex = 1;
$slideType = SpecialSlideType::MASTER_SLIDE;
$shapeIndex = 2;
$paragraphIndex = 3;

$portions = $api->GetSpecialSlidePortions($fileName, $slideIndex, $slideType, $shapeIndex, $paragraphIndex);
$portionCount = count($portions->getItems());

$dto = new Portion();
$dto->setFontBold("True");
$dto->setText("New portion");

$portion = $api->CreateSpecialSlidePortion($fileName, $slideIndex, $slideType, $shapeIndex, $paragraphIndex, $dto);
print($portion->getFontBold()); // True
print($portion->getText()); // New portion

$dto = new Portion();
$dto->setFontHeight(22);
$dto->setText("Updated portion");

$portion = $api->UpdateSpecialSlidePortion($fileName, $slideIndex, $slideType, $shapeIndex, $paragraphIndex, $portionCount + 1, $dto);
print($portion->getFontBold()); // True
print($portion->getFontHeight()); // 22.0
print($portion->getText()); // Updated portion

$api->DeleteSpecialSlidePortion($fileName, $slideIndex, $slideType, $shapeIndex, $paragraphIndex, $portionCount + 1);
```

{{< /tab >}}

{{< tab tabNum="4" >}}

```ruby
require "aspose_slides_cloud"

include AsposeSlidesCloud

configuration = Configuration.new
configuration.app_sid = "MyClientId"
configuration.app_key = "MyClientSecret"

api = SlidesApi.new(configuration)

file_name = "MyPresentation.pptx"
slide_index = 1
slide_type = "MasterSlide"
shape_index = 2
paragraph_index = 3

portions = api.get_special_slide_portions(file_name, slide_index, slide_type, shape_index, paragraph_index)
portion_count = portions.items.length()

dto = Portion.new()
dto.font_bold = "True"
dto.text = "New portion"

portion = api.create_special_slide_portion(file_name, slide_index, slide_type, shape_index, paragraph_index, dto)
puts portion.font_bold # True
puts portion.text # New portion

dto = Portion.new()
dto.font_height = 22
dto.text = "Updated portion"

portion = api.update_special_slide_portion(file_name, slide_index, slide_type, shape_index, paragraph_index, portion_count + 1, dto)
puts portion.font_bold # True
puts portion.font_height # 22.0
puts portion.text # Updated portion

api.delete_special_slide_portion(file_name, slide_index, slide_type, shape_index, paragraph_index, portion_count + 1)
```

{{< /tab >}}

{{< tab tabNum="5" >}}

```python
import asposeslidescloud

from asposeslidescloud.configuration import Configuration
from asposeslidescloud.apis.slides_api import SlidesApi
from asposeslidescloud.models.portion import Portion

configuration = Configuration()
configuration.app_sid = "MyClientId"
configuration.app_key = "MyClientSecret"

api = SlidesApi(configuration)

file_name = "MyPresentation.pptx"
slide_index = 1
slide_type = "MasterSlide"
shape_index = 2
paragraph_index = 3

portions = api.get_special_slide_portions(file_name, slide_index, slide_type, shape_index, paragraph_index)
portion_count = len(portions.items)

dto = Portion()
dto.font_bold = "True"
dto.text = "New portion"

portion = api.create_special_slide_portion(file_name, slide_index, slide_type, shape_index, paragraph_index, dto)
print(portion.font_bold) # True
print(portion.text) # New portion

dto = Portion()
dto.font_height = 22
dto.text = "Updated portion"

portion = api.update_special_slide_portion(file_name, slide_index, slide_type, shape_index, paragraph_index, portion_count + 1, dto)
print(portion.font_bold) # True
print(portion.font_height) # 22.0
print(portion.text) # Updated portion

api.delete_special_slide_portion(file_name, slide_index, slide_type, shape_index, paragraph_index, portion_count + 1)
```

{{< /tab >}}

{{< tab tabNum="6" >}}

```javascript
const CloudSdk = require("asposeslidescloud");

const api = new CloudSdk.SlidesApi("MyClientId", "MyClientSecret");

const fileName = "MyPresentation.pptx";
const slideIndex = 1;
const slideType = CloudSdk.SpecialSlideType.MasterSlide;
const shapeIndex = 2;
const paragraphIndex = 3;

api.getSpecialSlidePortions(fileName, slideIndex, slideType, shapeIndex, paragraphIndex).then((result) => {
    const portionCount = result.body.items.length;

    var dto = new CloudSdk.Portion();
    dto.fontBold = CloudSdk.Portion.FontBoldEnum.True;
    dto.text = "New portion";

    api.createSpecialSlidePortion(fileName, slideIndex, slideType, shapeIndex, paragraphIndex, dto).then((postResult) => {
        console.log(postResult.body.fontBold); // True
        console.log(postResult.body.text); // New portion

        dto = new CloudSdk.Portion();
        dto.fontHeight = 22;
        dto.text = "Updated portion";

        api.updateSpecialSlidePortion(fileName, slideIndex, slideType, shapeIndex, paragraphIndex, portionCount + 1, dto).then((putResult) => {
            console.log(postResult.body.fontBold); // True
            console.log(postResult.body.fontHeight); // 22.0
            console.log(postResult.body.text); // Updated portion

            api.deleteSpecialSlidePortion(fileName, slideIndex, slideType, shapeIndex, paragraphIndex, portionCount + 1);
        });
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
var slideIndex int32 = 1
slideType := "MasterSlide"
var shapeIndex int32 = 2
var paragraphIndex int32 = 3

portions, _, e := api.SlidesApi.GetSpecialSlidePortions(fileName, slideIndex, slideType, shapeIndex, paragraphIndex, "", "", "", "")
if e != nil {
    fmt.Printf("Error: %v.", e)
    return
}
portionCount := len(portions.GetItems())

dto := asposeslidescloud.NewPortion()
dto.Text = "New portion"
dto.FontBold = "True"

portion, _, e := api.SlidesApi.CreateSpecialSlidePortion(fileName, slideIndex, slideType, shapeIndex, paragraphIndex, dto, nil, "", "", "", "")
if e != nil {
    fmt.Printf("Error: %v.", e)
    return
}
fmt.Printf("Error: %v.", portion.GetFontBold()) // True
fmt.Printf("Error: %v.", portion.GetText()) // New portion

dto = asposeslidescloud.NewPortion()
dto.Text = "Updated portion"
dto.FontHeight = 22

portion, _, e = api.SlidesApi.UpdateSpecialSlidePortion(fileName, slideIndex, slideType, shapeIndex, paragraphIndex, int32(portionCount + 1), dto, "", "", "", "")
if e != nil {
    fmt.Printf("Error: %v.", e)
    return
}
fmt.Printf("Error: %v.", portion.GetFontBold()) // True
fmt.Printf("Error: %v.", portion.GetFontHeight()) // 22.0
fmt.Printf("Error: %v.", portion.GetText()) // Updated portion

_, _, e = api.SlidesApi.DeleteSpecialSlidePortion(fileName, slideIndex, slideType, shapeIndex, paragraphIndex, int32(portionCount + 1), "", "", "", "")
if e != nil {
    fmt.Printf("Error: %v.", e)
    return
}
```

{{< /tab >}}

{{< tab tabNum="8" >}}

```cpp
#include "asposeslidescloud/api/SlidesApi.h"

using namespace asposeslidescloud::api;

int main()
{
    std::shared_ptr<SlidesApi> api = std::make_shared<SlidesApi>(L"MyClientId", L"MyClientSecret");

    const wchar_t* fileName = L"MyPresentation.pptx";
    const int slideIndex = 1;
    const wchar_t* slideType = L"MasterSlide";
    const int shapeIndex = 2;
    const int paragraphIndex = 3;

    std::shared_ptr<Portions> portions = api->getSpecialSlidePortions(fileName, slideIndex, slideType, shapeIndex, paragraphIndex).get();
    int portionCount = portions->getItems().size();

    std::shared_ptr<Portion> dto = std::make_shared<Portion>();
    dto->setFontBold(L"True");
    dto->setText(L"New portion");

    std::shared_ptr<Portion> portion = api->createSpecialSlidePortion(fileName, slideIndex, slideType, shapeIndex, paragraphIndex, dto).get();
    std::wcout << portion->getFontBold() << "\r\n"; // True
    std::wcout << portion->getText() << "\r\n"; // New portion

    dto->setFontHeight(22.0);
    dto->setText(L"Updated portion");

    portion = api->updateSpecialSlidePortion(fileName, slideIndex, slideType, shapeIndex, paragraphIndex, portionCount + 1, dto).get();
    std::wcout << portion->getFontBold() << "\r\n"; // True
    std::wcout << portion->getFontHeight() << "\r\n"; // 22
    std::wcout << portion->getText(); // Updated portion

    api->deleteSpecialSlidePortion(fileName, slideIndex, slideType, shapeIndex, paragraphIndex, portionCount + 1).get();
}
```

{{< /tab >}}

{{< tab tabNum="9" >}}

```perl
use AsposeSlidesCloud::Configuration;
use AsposeSlidesCloud::SlidesApi;
use AsposeSlidesCloud::Object::Portion;

my $config = AsposeSlidesCloud::Configuration->new();
$config->{app_sid} = "MyClientId";
$config->{app_key} = "MyClientSecret";

my $api = AsposeSlidesCloud::SlidesApi->new(config => $config);

my $file_name = "MyPresentation.pptx";
my $slide_index = 1;
my $slide_type = "MasterSlide";
my $shape_index = 2;
my $paragraph_index = 3;

my %parameters = (name => $file_name, slide_index => $slide_index, slide_type => $slide_type, shape_index => $shape_index, paragraph_index => $paragraph_index);
my $portions = $api->get_special_slide_portions(%parameters);
my $portion_count = @{$portions->{items}};

my $dto = AsposeSlidesCloud::Object::Portion->new();
$dto->{font_bold} = "True";
$dto->{text} = "New portion";

my %parameters = (name => $file_name, slide_index => $slide_index, slide_type => $slide_type, shape_index => $shape_index, paragraph_index => $paragraph_index, dto => $dto);
$portion = $api->create_special_slide_portion(%parameters);
print($portion->{font_bold}, "\n"); # True
print($portion->{text}, "\n"); # New portion

$dto = AsposeSlidesCloud::Object::Portion->new();
$dto->{font_height} = 22;
$dto->{text} = "Updated portion";

my %parameters = (name => $file_name, slide_index => $slide_index, slide_type => $slide_type, shape_index => $shape_index, paragraph_index => $paragraph_index, portion_index => $portion_count + 1, dto => $dto);
$portion = $api->update_special_slide_portion(%parameters);
print($portion->{font_bold}, "\n"); # True
print($portion->{font_height}, "\n"); # 22
print($portion->{text}); # Updated portion

my %parameters = (name => $file_name, slide_index => $slide_index, slide_type => $slide_type, shape_index => $shape_index, paragraph_index => $paragraph_index, portion_index => $portion_count + 1);
$api->delete_special_slide_portion(%parameters);
```

{{< /tab >}}

{{< tab tabNum="10" >}}

{{< /tab >}}

{{< /tabs >}}

## **SDKs**

Check [Available SDKs](/slides/available-sdks/) to learn how to add an SDK to your project.
