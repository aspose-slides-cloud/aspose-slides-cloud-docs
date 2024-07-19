---
title: "Delete a Text Portion"
keywords:
- PowerPoint
- presentation
- REST API
- cloud API
- table
- cell
- table cell
- text
- remove
- delete
- remove text
- delete text
type: docs
url: /delete-a-text-portion-from-a-table-cell/
weight: 50
---

## **Introduction**

In PowerPoint table cells, you can work with individual parts of text by changing their formatting independently. For example, you can select a portion of text and change its font, size, color, or style (bold, italic, underline) without affecting the rest of the text. Use the following method to delete text portions from table cells.

## **DeleteTableCellPortion**

### **API Information**

|**API**|**Type**|**Description**|**Resource**|
| :- | :- | :- | :- |
|/slides/{name}/slides/{slideIndex}/shapes/{shapeIndex}/rows/{rowIndex}/cells/{cellIndex}/paragraphs/{paragraphIndex}/portions/{portionIndex}|DELETE|Deletes a text portion from a paragraph in a table cell in a presentation saved in a storage.|[DeleteTableCellPortion](https://reference.aspose.cloud/slides/#/Table/DeleteTableCellPortion)|

**Request Parameters**

|**Name**|**Type**|**Location**|**Required**|**Description**|
| :- | :- | :- | :- | :- |
|name|string|path|true|The name of a presentation file.|
|slideIndex|integer|path|true|The 1-based index of a slide.|
|shapeIndex|integer|path|true|The 1-based index of a shape (must be a table).|
|rowIndex|integer|path|true|The 1-based index of a row.|
|cellIndex|integer|path|true|The 1-based index of a cell.|
|paragraphIndex|integer|path|true|The 1-based index of a paragraph.|
|portionIndex|integer|path|true|The 1-based index of a text portion.|
|password|string|header|false|The password to open the presentation.|
|folder|string|query|false|The path to the folder containing the presentation file.|
|storage|string|query|false|The name of the storage contaning the folder.|

### **Examples**

In the **default** storage, the document **MyPresentation.pptx** contains a table (the **first** shape) with four columns and three rows on the **ninth** slide. The cell **(2, 2)** contains three paragraphs. Delete the **second** text portion from the **third** paragraph.

![The table](input.png)

**cURL Solution**

{{< tabs tabTotal="2" tabID="1" tabName1="Request" tabName2="Response" >}}

{{< tab tabNum="1" >}}
**Get an Access Token**
```sh
curl -X POST "https://api.aspose.cloud/connect/token" \
     -d "grant_type=client_credentials&client_id=MyClientId&client_secret=MyClientSecret" \
     -H "Content-Type: application/x-www-form-urlencoded"
```

**Delete the Text Portion**
```sh
curl -X DELETE "https://api.aspose.cloud/v3.0/slides/MyPresentation.pptx/slides/9/shapes/1/rows/2/cells/2/paragraphs/3/portions/2" \
     -H "authorization: Bearer MyAccessToken"
```
{{< /tab >}}

{{< tab tabNum="2" >}}
```json
{
  "items": [
    {
      "text": "The first text portion. ",
      "fontBold": "False",
      "highlightColor": "#0",
      "fontHeight": 18,
      "languageId": "en-US",
      "selfUri": {
        "href": "https://api.aspose.cloud/v3.0/slides/MyPresentation.pptx/slides/9/shapes/1/rows/3/cells/3/paragraphs/3/portions/1",
        "relation": "self",
        "slideIndex": 9,
        "shapeIndex": 1
      }
    }
  ],
  "selfUri": {
    "href": "https://api.aspose.cloud/v3.0/slides/MyPresentation.pptx/slides/9/shapes/1/rows/3/cells/3/paragraphs/3/portions",
    "relation": "self",
    "slideIndex": 9,
    "shapeIndex": 1
  }
}
```
{{< /tab >}}

{{< /tabs >}}

**SDK Solutions**

{{< tabs tabTotal="9" tabID="11" tabName1="C#" tabName2="Java" tabName3="PHP" tabName4="Ruby" tabName5="Python" tabName6="Node.js" tabName7="Go" tabName8="C++" tabName9="Perl" >}}

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
        int slideIndex = 9;
        int shapeIndex = 1;
        int rowIndex = 2;
        int cellIndex = 2;
        int paragraphIndex = 3;
        int portionIndex = 2;

        Portions textPortions = slidesApi.DeleteTableCellPortion(fileName, slideIndex, shapeIndex, rowIndex, cellIndex, paragraphIndex, portionIndex);

        int portionCount = textPortions.Items.Count;
        Console.WriteLine("Number of text portions: " + portionCount); // 1
    }
}
```
{{< /tab >}}

{{< tab tabNum="2" >}}
```java
import com.aspose.slides.ApiException;
import com.aspose.slides.api.SlidesApi;
import com.aspose.slides.model.Portions;

public class Application {
    public static void main(String[] args) throws ApiException {
        SlidesApi slidesApi = new SlidesApi("MyClientId", "MyClientSecret");

        String fileName = "MyPresentation.pptx";
        int slideIndex = 9;
        int shapeIndex = 1;
        int rowIndex = 2;
        int cellIndex = 2;
        int paragraphIndex = 3;
        int portionIndex = 2;

        Portions textPortions = slidesApi.deleteTableCellPortion(fileName, slideIndex, shapeIndex, rowIndex, cellIndex, paragraphIndex, portionIndex, null, null, null);

        int portionCount = textPortions.getItems().size();
        System.out.println("Number of text portions: " + portionCount); // 1
    }
}
```
{{< /tab >}}

{{< tab tabNum="3" >}}
```php
use Aspose\Slides\Cloud\Sdk\Api\Configuration;
use Aspose\Slides\Cloud\Sdk\Api\SlidesApi;

$configuration = new Configuration();
$configuration->setAppSid("MyClientId");
$configuration->setAppKey("MyClientSecret");

$slidesApi = new SlidesApi(null, $configuration);

$fileName = "MyPresentation.pptx";
$slideIndex = 9;
$shapeIndex = 1;
$rowIndex = 2;
$cellIndex = 2;
$paragraphIndex = 3;
$portionIndex = 2;

$textPortions = $slidesApi->deleteTableCellPortion($fileName, $slideIndex, $shapeIndex, $rowIndex, $cellIndex, $paragraphIndex, $portionIndex);

$portionCount = count($textPortions->getItems());
print("Number of text portions: " . $portionCount); // 1
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
slide_index = 9
shape_index = 1
row_index = 2
cell_index = 2
paragraph_index = 3
portion_index = 2

text_portions = slides_api.delete_table_cell_portion(file_name, slide_index, shape_index, row_index, cell_index, paragraph_index, portion_index)

portion_count = text_portions.items.length
print "Number of text portions: ", portion_count # 1
```
{{< /tab >}}

{{< tab tabNum="5" >}}
```py
from asposeslidescloud.apis import SlidesApi
from asposeslidescloud.models import Portion

slides_api = SlidesApi(None, "MyClientId", "MyClientSecret")

file_name = "MyPresentation.pptx"
slide_index = 9
shape_index = 1
row_index = 2
cell_index = 2
paragraph_index = 3
portion_index = 2

text_portions = slides_api.delete_table_cell_portion(file_name, slide_index, shape_index, row_index, cell_index, paragraph_index, portion_index)

portion_count = len(text_portions.items)
print("Number of text portions:", portion_count)  # 1
```
{{< /tab >}}

{{< tab tabNum="6" >}}
```js
const cloudSdk = require("asposeslidescloud");

const slidesApi = new cloudSdk.SlidesApi("MyClientId", "MyClientSecret");

fileName = "MyPresentation.pptx";
slideIndex = 9;
shapeIndex = 1;
rowIndex = 2;
cellIndex = 2;
paragraphIndex = 3;
portionIndex = 2;

slidesApi.deleteTableCellPortion(fileName, slideIndex, shapeIndex, rowIndex, cellIndex, paragraphIndex, portionIndex).then(textPortions => {
    portionCount = textPortions.body.items.length;
    console.log("Number of text portions: " + portionCount); // 1
});
```
{{< /tab >}}

{{< tab tabNum="7" >}}
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
	var slideIndex int32 = 9
	var shapeIndex int32 = 1
	var rowIndex int32 = 2
	var cellIndex int32 = 2
	var paragraphIndex int32 = 3
	var portionIndex int32 = 2

	textPortions, _, _ := slidesApi.DeleteTableCellPortion(fileName, slideIndex, shapeIndex, rowIndex, cellIndex, paragraphIndex, portionIndex, "", "", "")

	portionCount := len(textPortions.GetItems())
	fmt.Println("Number of text portions:", portionCount) // 1
}
```
{{< /tab >}}

{{< tab tabNum="8" >}}
```cpp
#include "asposeslidescloud/api/SlidesApi.h"

using namespace asposeslidescloud::api;

int main()
{
    std::shared_ptr<SlidesApi> slidesApi = std::make_shared<SlidesApi>(L"MyClientId", L"MyClientSecret");

    const wchar_t* fileName = L"MyPresentation.pptx";
    int slideIndex = 9;
    int shapeIndex = 1;
    int rowIndex = 2;
    int cellIndex = 2;
    int paragraphIndex = 3;
    int portionIndex = 2;

    std::shared_ptr<Portions> textPortions = slidesApi->deleteTableCellPortion(fileName, slideIndex, shapeIndex, rowIndex, cellIndex, paragraphIndex, portionIndex).get();

    int portionCount = textPortions->getItems().size();
    std::wcout << L"Number of text portions: " << portionCount; // 1
}
```
{{< /tab >}}

{{< tab tabNum="9" >}}
```pl
use AsposeSlidesCloud::Configuration;
use AsposeSlidesCloud::SlidesApi;

my $configuration = AsposeSlidesCloud::Configuration->new();
$configuration->{app_sid} = "MyClientId";
$configuration->{app_key} = "MyClientSecret";

my $slides_api = AsposeSlidesCloud::SlidesApi->new(config => $configuration);

my $file_name = "MyPresentation.pptx";
my $slide_index = 9;
my $shape_index = 1;
my $row_index = 2;
my $cell_index = 2;
my $paragraph_index = 3;
my $portion_index = 2;

my $text_portions = $slides_api->delete_table_cell_portion(
    name => $file_name, slide_index => $slide_index, shape_index => $shape_index, row_index => $row_index, cell_index => $cell_index, paragraph_index => $paragraph_index, portion_index => $portion_index);

my $portion_count = @{$text_portions->{items}};
print "Number of text portions: ", $portion_count; # 1
```
{{< /tab >}}

{{< /tabs >}}

The result:

![The table](output.png)

## **SDKs**

Check [Available SDKs](/slides/available-sdks/) to learn how to add an SDK to your project.
