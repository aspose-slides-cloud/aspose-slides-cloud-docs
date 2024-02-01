---
title: "Working with Paragraphs on a Special Slide"
type: docs
url: /working-with-paragraphs-on-a-special-slide/
weight: 20
---

## **Introduction**

Aspose.Slides Cloud API allows you to read, add, modify and delete text paragraphs from shapes on special (Master, Layout, Notes) slides in a PowerPoint presentation. A set of methods identical to those that work with ordinary slides can be used to do that.

## **API Information**

|**API**|**Type**|**Description**|**Resource**|
| :- | :- | :- | :- |
|/slides/{name}/slides/{slideIndex}/{slideType}/shapes/{shapeIndex}/paragraphs|GET|Reads information about paragraphs in a shape on a special slide.|[GetSpecialSlideParagraphs](https://apireference.aspose.cloud/slides/#/SpecialSlideShapes/GetSpecialSlideParagraphs)|
|/slides/{name}/slides/{slideIndex}/{slideType}/shapes/{shapeIndex}/paragraphs/{paragraphIndex}|GET|Reads information about a paragraph in a shape on a special slide.|[GetSpecialSlideParagraph](https://apireference.aspose.cloud/slides/#/SpecialSlideShapes/GetSpecialSlideParagraph)|
|/slides/{name}/slides/{slideIndex}/{slideType}/shapes/{shapeIndex}/paragraphs|POST|Adds a new paragraph to a shape on a special slide.|[CreateSpecialSlideParagraph](https://apireference.aspose.cloud/slides/#/SpecialSlideShapes/CreateSpecialSlideParagraph)|
|/slides/{name}/slides/{slideIndex}/{slideType}/shapes/{shapeIndex}/paragraphs/{paragraphIndex}|PUT|Updates a paragraph in a shape on a special slide.|[UpdateSpecialSlideParagraph](https://apireference.aspose.cloud/slides/#/SpecialSlideShapes/UpdateSpecialSlideParagraph)|
|/slides/{name}/slides/{slideIndex}/{slideType}/shapes/{shapeIndex}/paragraphs|DELETE|Deletes paragraphs from a shape on a special slide.|[DeleteSpecialSlideParagraphs](https://apireference.aspose.cloud/slides/#/SpecialSlideShapes/DeleteSpecialSlideParagraphs)|
|/slides/{name}/slides/{slideIndex}/{slideType}/shapes/{shapeIndex}/paragraphs/{paragraphIndex}|DELETE|Deletes a paragraph from a shape on a special slide.|[DeleteSpecialSlideParagraph](https://reference.aspose.cloud/slides/#/SpecialSlideShapes/DeleteSpecialSlideParagraph)|

{{< expand-list title="GetSpecialSlideParagraphs Request Parameters" >}}
|**Name**|**Type**|**Location**|**Required**|**Description**|
| :- | :- | :- | :- | :- |
|name|string|path|true|The name of a presentation file saved in a storage.|
|slideIndex|integer|path|true|The 1-based index of a regular slide.|
|slideType|`MasterSlide` or `LayoutSlide` or `NotesSlide`|path|true|The type of a special slide.|
|shapeIndex|integer|path|true|The 1-based index of a shape.|
|password|string|header|false|The password to open the presentation.|
|folder|string|query|false|The path to a folder containing the presentation.|
|storage|string|query|false|The name of the storage contaning the folder.|
|subShape|string|query|false|The path to a child shape (e.g. "3", "3/shapes/2").|
{{< /expand-list >}}

{{< expand-list title="GetSpecialSlideParagraph Request Parameters" >}}
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

{{< expand-list title="CreateSpecialSlideParagraph Request Parameters" >}}
|**Name**|**Type**|**Location**|**Required**|**Description**|
| :- | :- | :- | :- | :- |
|name|string|path|true|The name of a presentation file saved in a storage.|
|slideIndex|integer|path|true|The 1-based index of a regular slide.|
|slideType|`MasterSlide` or `LayoutSlide` or `NotesSlide`|path|true|The type of a special slide.|
|shapeIndex|integer|path|true|The 1-based index of a shape.|
|dto|`Paragraph`|body|true|The data transfer object with parameters for a new paragraph.|
|position|integer|query|false|The position of the new paragraph in the list of paragraphs. By default, the paragraph is added to the end of the list.|
|password|string|header|false|The password to open the presentation.|
|folder|string|query|false|The path to a folder containing the presentation.|
|storage|string|query|false|The name of the storage contaning the folder.|
|subShape|string|query|false|The path to a child shape (e.g. "3", "3/shapes/2").|
{{< /expand-list >}}

{{< expand-list title="UpdateSpecialSlideParagraph Request Parameters" >}}
|**Name**|**Type**|**Location**|**Required**|**Description**|
| :- | :- | :- | :- | :- |
|name|string|path|true|The name of a presentation file saved in a storage.|
|slideIndex|integer|path|true|The 1-based index of a regular slide.|
|slideType|`MasterSlide` or `LayoutSlide` or `NotesSlide`|path|true|The type of a special slide.|
|shapeIndex|integer|path|true|The 1-based index of a shape.|
|paragraphIndex|integer|path|true|The 1-based index of a paragraph.|
|dto|`Paragraph`|body|true|The data transfer object with parameters for the paragraph.|
|password|string|header|false|The password to open the presentation.|
|folder|string|query|false|The path to a folder containing the presentation.|
|storage|string|query|false|The name of the storage contaning the folder.|
|subShape|string|query|false|The path to a child shape (e.g. "3", "3/shapes/2").|
{{< /expand-list >}}

{{< expand-list title="DeleteSpecialSlideParagraphs Request Parameters" >}}
|**Name**|**Type**|**Location**|**Required**|**Description**|
| :- | :- | :- | :- | :- |
|name|string|path|true|The name of a presentation file saved in a storage.|
|slideIndex|integer|path|true|The 1-based index of a regular slide.|
|slideType|`MasterSlide` or `LayoutSlide` or `NotesSlide`|path|true|The type of a special slide.|
|shapeIndex|integer|path|true|The 1-based index of a shape.|
|paragraphs|string|query|false|The indices of the paragraphs to be deleted. Delete all by default.|
|password|string|header|false|The password to open the presentation.|
|folder|string|query|false|The path to a folder containing the presentation.|
|storage|string|query|false|The name of the storage contaning the folder.|
|subShape|string|query|false|The path to a child shape (e.g. "3", "3/shapes/2").|
{{< /expand-list >}}

{{< expand-list title="DeleteSpecialSlideParagraph Request Parameters" >}}
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

## **Examples**

The following examples demonstrate manipulating text paragraphs on a Master slide. You can access paragraphs on a Layout or Notes slide the same way, just change the value of the **slideType** parameter accordingly.

**cURL Examples**
{{< tabs tabTotal="2" tabID="1" tabName1="Request" tabName2="Response" >}}

{{< tab tabNum="1" >}}

**Get an Access Token**

```sh
curl -X POST "https://api.aspose.cloud/connect/token" \
     -d "grant_type=client_credentials&client_id=MyClientId&client_secret=MyClientSecret" \
     -H "Content-Type: application/x-www-form-urlencoded"
```

**Get a Paragraph List**

```sh
curl -X GET "https://api.aspose.cloud/v3.0/slides/MyPresentation.pptx/slides/1/masterSlide/shapes/2/paragraphs" \
     -H "authorization: Bearer MyAccessToken"
```

**Add a Paragraph**

```sh
curl -X POST "https://api.aspose.cloud/v3.0/slides/MyPresentation.pptx/slides/1/masterSlide/shapes/2/paragraphs" \
     -H "authorization: Bearer MyAccessToken" \
     -d "@paragraph.json" \
     -H "Content-Type: text/json"
```

**Update the Paragraph**

```sh
curl -X PUT "https://api.aspose.cloud/v3.0/slides/MyPresentation.pptx/slides/1/masterSlide/shapes/2/paragraphs/6" \
     -H "authorization: Bearer MyAccessToken" \
     -d "@paragraph.json" \
     -H "Content-Type: text/json"
```

**Delete the Paragraph**

```sh
curl -X DELETE "https://api.aspose.cloud/v3.0/slides/MyPresentation.pptx/slides/1/masterSlide/shapes/2/paragraphs/6" \
     -H "authorization: Bearer MyAccessToken"
```

**paragraph.json example**

```json
{
    "alignment": "Center",
    "portions": {
        "text": "New paragraph"
    }
}
```

{{< /tab >}}

{{< tab tabNum="2" >}}

```json
{
    "alignment": "Center",
    "depth": 2,
    "portionList": [
        {
            "text": "New paragraph",
            "fontHeight": 20.0,
            "selfUri": {
                "href": "https://api.aspose.cloud/v3.0/slides/MyPresentation.pptx/slides/1/masterSlide/shapes/2/paragraphs/3/portions/1",
                "relation": "self"
            }
        }
    ],
    "selfUri": {
        "href": "https://api.aspose.cloud/v3.0/slides/MyPresentation.pptx/slides/1/masterSlide/shapes/2/paragraphs/3",
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

Paragraphs paragraphs = api.GetSpecialSlideParagraphs(fileName, slideIndex, slideType, shapeIndex);
int paragraphCount = paragraphs.ParagraphLinks.Count;

Paragraph dto = new Paragraph
{
    Alignment = Paragraph.AlignmentEnum.Right,
    PortionList = new List<Portion>
    {
        new Portion { Text = "New paragraph" }
    }
};

Paragraph paragraph = api.CreateSpecialSlideParagraph(fileName, slideIndex, slideType, shapeIndex, dto);
Console.WriteLine(paragraph.Alignment); // Right

dto.Alignment = Paragraph.AlignmentEnum.Center;
paragraph = api.UpdateSpecialSlideParagraph(fileName, slideIndex, slideType, shapeIndex, paragraphCount + 1, dto);
Console.WriteLine(paragraph.Alignment); // Center

api.DeleteSpecialSlideParagraph(fileName, slideIndex, slideType, shapeIndex, paragraphCount + 1);
```

{{< /tab >}}

{{< tab tabNum="2" >}}

```java
SlidesApi api = new SlidesApi("MyClientId", "MyClientSecret");

String fileName = "MyPresentation.pptx";
int slideIndex = 1;
SpecialSlideType slideType = SpecialSlideType.MASTERSLIDE;
int shapeIndex = 2;

Paragraphs paragraphs = api.getSpecialSlideParagraphs(fileName, slideIndex, slideType, shapeIndex, null, null, null, null);
int paragraphCount = paragraphs.getParagraphLinks().size();

Paragraph dto = new Paragraph();
dto.setAlignment(Paragraph.AlignmentEnum.RIGHT);
List<Portion> portions = new ArrayList<Portion>();
Portion portion = new Portion();
portion.setText("New paragraph");
portions.add(portion);
dto.setPortionList(portions);

Paragraph paragraph = api.createSpecialSlideParagraph(fileName, slideIndex, slideType, shapeIndex, dto, null, null, null, null, null);
System.out.println(paragraph.getAlignment()); // Right

dto.setAlignment(Paragraph.AlignmentEnum.CENTER);
paragraph = api.updateSpecialSlideParagraph(fileName, slideIndex, slideType, shapeIndex, paragraphCount + 1, dto, null, null, null, null);
System.out.println(paragraph.getAlignment()); // Center

api.deleteSpecialSlideParagraph(fileName, slideIndex, slideType, shapeIndex, paragraphCount + 1, null, null, null, null);
```

{{< /tab >}}

{{< tab tabNum="3" >}}

```php
use Aspose\Slides\Cloud\Sdk\Api\Configuration;
use Aspose\Slides\Cloud\Sdk\Api\SlidesApi;
use Aspose\Slides\Cloud\Sdk\Model\Paragraph;
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

$paragraphs = $api->GetSpecialSlideParagraphs($fileName, $slideIndex, $slideType, $shapeIndex);
$paragraphCount = count($paragraphs->getParagraphLinks());

$dto = new Paragraph();
$dto->setAlignment("Right");
$portion = new Portion();
$portion->setText("New paragraph");
$dto->setPortionList([ $portion ]);

$paragraph = $api->CreateSpecialSlideParagraph($fileName, $slideIndex, $slideType, $shapeIndex, $dto);
print($paragraph->getAlignment()); // Right

$dto->setAlignment("Center");
$paragraph = $api->UpdateSpecialSlideParagraph($fileName, $slideIndex, $slideType, $shapeIndex, $paragraphCount + 1, $dto);
print($paragraph->getAlignment()); // Center

$api->DeleteSpecialSlideParagraph($fileName, $slideIndex, $slideType, $shapeIndex, $paragraphCount + 1);
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

paragraphs = api.get_special_slide_paragraphs(file_name, slide_index, slide_type, shape_index)
paragraph_count = paragraphs.paragraph_links.length()

dto = Paragraph.new
dto.alignment = "Right"
portion = Portion.new
portion.text = "New paragraph"
dto.portion_list = [ portion ]

paragraph = api.create_special_slide_paragraph(file_name, slide_index, slide_type, shape_index, dto)
puts paragraph.alignment # Right

dto.alignment = "Center"
paragraph = api.update_special_slide_paragraph(file_name, slide_index, slide_type, shape_index, paragraph_count + 1, dto)
puts paragraph.alignment # Center

api.delete_special_slide_paragraph(file_name, slide_index, slide_type, shape_index, paragraph_count + 1)
```

{{< /tab >}}

{{< tab tabNum="5" >}}

```python
import asposeslidescloud

from asposeslidescloud.configuration import Configuration
from asposeslidescloud.apis.slides_api import SlidesApi
from asposeslidescloud.models.paragraph import Paragraph
from asposeslidescloud.models.portion import Portion

configuration = Configuration()
configuration.app_sid = "MyClientId"
configuration.app_key = "MyClientSecret"

api = SlidesApi(configuration)

file_name = "MyPresentation.pptx"
slide_index = 1
slide_type = "MasterSlide"
shape_index = 2

paragraphs = api.get_special_slide_paragraphs(file_name, slide_index, slide_type, shape_index)
paragraph_count = len(paragraphs.paragraph_links)

dto = Paragraph()
dto.alignment = "Right"
portion = Portion()
portion.text = "New paragraph"
dto.portion_list = [ portion ]

paragraph = api.create_special_slide_paragraph(file_name, slide_index, slide_type, shape_index, dto)
print(paragraph.alignment) # Right

dto.alignment = "Center"
paragraph = api.update_special_slide_paragraph(file_name, slide_index, slide_type, shape_index, paragraph_count + 1, dto)
print(paragraph.alignment) # Center

api.delete_special_slide_paragraph(file_name, slide_index, slide_type, shape_index, paragraph_count + 1)
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

api.getSpecialSlideParagraphs(fileName, slideIndex, slideType, shapeIndex).then((result) => {
    const paragraphCount = result.body.paragraphLinks.length;

    var dto = new CloudSdk.Paragraph();
    dto.alignment = "Right";
    const portion = new CloudSdk.Portion();
    portion.text = "New paragraph";
    dto.portionList = [ portion ];

    api.createSpecialSlideParagraph(fileName, slideIndex, slideType, shapeIndex, dto).then((postResult) => {
        console.log(postResult.body.alignment); // Right

        dto = new CloudSdk.Paragraph();
        dto.alignment = "Center";

        api.updateSpecialSlideParagraph(fileName, slideIndex, slideType, shapeIndex, paragraphCount + 1, dto).then((putResult) => {
            console.log(putResult.body.alignment); // Center

            api.deleteSpecialSlideParagraph(fileName, slideIndex, slideType, shapeIndex, paragraphCount + 1);
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

paragraphs, _, e := api.SlidesApi.GetSpecialSlideParagraphs(fileName, slideIndex, slideType, shapeIndex, "", "", "", "")
if e != nil {
    fmt.Printf("Error: %v.", e)
    return
}
paragraphCount := len(paragraphs.GetParagraphLinks())

dto := asposeslidescloud.NewParagraph()
dto.Alignment = "Right"
portion := asposeslidescloud.NewPortion()
portion.Text = "New paragraph"
dto.PortionList = []asposeslidescloud.IPortion { portion }

paragraph, _, e := api.SlidesApi.CreateSpecialSlideParagraph(fileName, slideIndex, slideType, shapeIndex, dto, nil, "", "", "", "")
if e != nil {
    fmt.Printf("Error: %v.", e)
    return
}
fmt.Printf("Error: %v.", paragraph.GetAlignment()) // Right

dto = asposeslidescloud.NewParagraph()
dto.Alignment = "Center"

paragraph, _, e = api.SlidesApi.UpdateSpecialSlideParagraph(fileName, slideIndex, slideType, shapeIndex, int32(paragraphCount + 1), dto, "", "", "", "")
if e != nil {
    fmt.Printf("Error: %v.", e)
    return
}
fmt.Printf("Error: %v.", paragraph.GetAlignment()) // Center

_, _, e = api.SlidesApi.DeleteSpecialSlideParagraph(fileName, slideIndex, slideType, shapeIndex, int32(paragraphCount + 1), "", "", "", "")
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

    std::shared_ptr<Paragraphs> paragraphs = api->getSpecialSlideParagraphs(fileName, slideIndex, slideType, shapeIndex).get();
    const int paragraphCount = paragraphs->getParagraphLinks().size();

    std::shared_ptr<Paragraph> dto = std::make_shared<Paragraph>();
    dto->setAlignment(L"Right");
    std::shared_ptr<Portion> portion = std::make_shared<Portion>();
    portion->setText(L"New paragraph");
    std::initializer_list<std::shared_ptr<Portion>> portions = { portion };
    dto->setPortionList(portions);

    std::shared_ptr<Paragraph> paragraph = api->createSpecialSlideParagraph(fileName, slideIndex, slideType, shapeIndex, dto).get();
    std::wcout << paragraph->getAlignment() << L"\r\n"; // Right

    dto->setAlignment(L"Center");
    paragraph = api->updateSpecialSlideParagraph(fileName, slideIndex, slideType, shapeIndex, paragraphCount + 1, dto).get();
    std::wcout << paragraph->getAlignment(); // Center

    api->deleteSpecialSlideParagraph(fileName, slideIndex, slideType, shapeIndex, paragraphCount + 1).get();
}
```

{{< /tab >}}

{{< tab tabNum="9" >}}

```perl
use AsposeSlidesCloud::Configuration;
use AsposeSlidesCloud::SlidesApi;
use AsposeSlidesCloud::Object::Paragraph;
use AsposeSlidesCloud::Object::Portion;

my $config = AsposeSlidesCloud::Configuration->new();
$config->{app_sid} = "MyClientId";
$config->{app_key} = "MyClientSecret";

my $api = AsposeSlidesCloud::SlidesApi->new(config => $config);

my $file_name = "MyPresentation.pptx";
my $slide_index = 1;
my $slide_type = "MasterSlide";
my $shape_index = 2;

my %parameters = (name => $file_name, slide_index => $slide_index, slide_type => $slide_type, shape_index => $shape_index);
my $paragraphs = $api->get_special_slide_paragraphs(%parameters);
my $paragraph_count = @{$paragraphs->{paragraph_links}};

my $dto = AsposeSlidesCloud::Object::Paragraph->new();
$dto->{alignment} = "Right";
my $portion = AsposeSlidesCloud::Object::Portion->new();
$portion->{text} = "New paragraph";
$dto->{portion_list} = [ $portion ];

my %parameters = (name => $file_name, slide_index => $slide_index, slide_type => $slide_type, shape_index => $shape_index, dto => $dto);
my $paragraph = $api->create_special_slide_paragraph(%parameters);
print($paragraph->{alignment}, "\n"); # Right

$dto->{alignment} = "Center";
my %parameters = (name => $file_name, slide_index => $slide_index, slide_type => $slide_type, shape_index => $shape_index, paragraph_index => $paragraph_count + 1, dto => $dto);
my $paragraph = $api->update_special_slide_paragraph(%parameters);
print($paragraph->{alignment}); # Center

my %parameters = (name => $file_name, slide_index => $slide_index, slide_type => $slide_type, shape_index => $shape_index, paragraph_index => $paragraph_count + 1);
$api->delete_special_slide_paragraph(%parameters);
```

{{< /tab >}}

{{< tab tabNum="10" >}}

{{< /tab >}}

{{< /tabs >}}

## **SDKs**

Check [Available SDKs](/slides/available-sdks/) to learn how to add an SDK to your project.
