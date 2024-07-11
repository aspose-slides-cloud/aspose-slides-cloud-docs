---
title: "Delete a Paragraph"
keywords:
- PowerPoint
- presentation
- REST API
- cloud API
- table
- cell
- table cell
- text
- paragraph
- remove a paragraph
- delete a paragraph
type: docs
url: /delete-a-paragraph-from-a-table-cell/
weight: 50
---

## **Introduction**

In PowerPoint table cells, you can add and change text, change the font, size, color, and style of the text, as well as adjust the alignment within the cells. Use the following method to delete paragraphs from table cells.

## **DeleteTableCellParagraph**

### **API Information**

|**API**|**Type**|**Description**|**Resource**|
| :- | :- | :- | :- |
|/slides/{name}/slides/{slideIndex}/shapes/{shapeIndex}/rows/{rowIndex}/cells/{cellIndex}/paragraphs/{paragraphIndex}|DELETE|Deletes a paragraph from a table cell in a presentation saved in a strorage.|[DeleteTableCellParagraph](https://reference.aspose.cloud/slides/#/Table/DeleteTableCellParagraph)|

**Request Parameters**

|**Name**|**Type**|**Location**|**Required**|**Description**|
| :- | :- | :- | :- | :- |
|name|string|path|true|The name of a presentation file.|
|slideIndex|integer|path|true|The 1-based index of a slide.|
|shapeIndex|integer|path|true|The 1-based index of a shape (must be a table).|
|rowIndex|integer|path|true|The 1-based index of a row.|
|cellIndex|integer|path|true|The 1-based index of a cell.|
|paragraphIndex|integer|path|true|The 1-based index of a paragraph to be deleted.|
|password|string|header|false|The password to open the presentation.|
|folder|string|query|false|The path to the folder containing the presentation file.|
|storage|string|query|false|The name of the storage contaning the folder.|

### **Examples**

In the **default** storage, the document **MyPresentation.pptx** contains a table (the **first** shape) with four columns and three rows on the **ninth** slide. The cell (2, 2) contains three paragraphs. Delete the **third** paragraph from the cell **(2, 2)**.

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

**Delete the Paragraph**
```sh
curl -X DELETE "https://api.aspose.cloud/v3.0/slides/MyPresentation.pptx/slides/9/shapes/1/rows/2/cells/2/paragraphs/3" \
     -H "authorization: Bearer MyAccessToken"
```
{{< /tab >}}

{{< tab tabNum="2" >}}
**Response Example**
```json
{
  "paragraphLinks": [
    {
      "href": "https://api.aspose.cloud/v3.0/slides/MyPresentation.pptx/slides/9/shapes/1/rows/3/cells/3/paragraphs/1",
      "relation": "self",
      "slideIndex": 9,
      "shapeIndex": 1
    },
    {
      "href": "https://api.aspose.cloud/v3.0/slides/MyPresentation.pptx/slides/9/shapes/1/rows/3/cells/3/paragraphs/2",
      "relation": "self",
      "slideIndex": 9,
      "shapeIndex": 1
    }
  ],
  "selfUri": {
    "href": "https://api.aspose.cloud/v3.0/slides/MyPresentation.pptx/slides/9/shapes/1/rows/3/cells/3/paragraphs",
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

        Paragraphs paragraphs = slidesApi.DeleteTableCellParagraph(fileName, slideIndex, shapeIndex, rowIndex, cellIndex, paragraphIndex);

        int paragraphCount = paragraphs.ParagraphLinks.Count;
        Console.WriteLine("Number of paragraphs: " + paragraphCount); // 2
    }
}
```
{{< /tab >}}

{{< tab tabNum="2" >}}
```java
import com.aspose.slides.ApiException;
import com.aspose.slides.api.SlidesApi;
import com.aspose.slides.model.Paragraphs;

public class Application {
    public static void main(String[] args) throws ApiException {
        SlidesApi slidesApi = new SlidesApi("MyClientId", "MyClientSecret");

        String fileName = "MyPresentation.pptx";
        int slideIndex = 9;
        int shapeIndex = 1;
        int rowIndex = 2;
        int cellIndex = 2;
        int paragraphIndex = 3;

        Paragraphs paragraphs = slidesApi.deleteTableCellParagraph(fileName, slideIndex, shapeIndex, rowIndex, cellIndex, paragraphIndex, null, null, null);

        int paragraphCount = paragraphs.getParagraphLinks().size();
        System.out.println("Number of paragraphs: " + paragraphCount); // 2
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

$paragraphs = $slidesApi->deleteTableCellParagraph($fileName, $slideIndex, $shapeIndex, $rowIndex, $cellIndex, $paragraphIndex);

$paragraphCount = count($paragraphs->getParagraphLinks());
print("Number of paragraphs: " . $paragraphCount); // 2
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

paragraphs = slides_api.delete_table_cell_paragraph(file_name, slide_index, shape_index, row_index, cell_index, paragraph_index)

paragraph_count = paragraphs.paragraph_links.length
puts "Number of paragraphs: #{paragraph_count}" # 2
```
{{< /tab >}}

{{< tab tabNum="5" >}}
```py
from asposeslidescloud.apis import SlidesApi

slides_api = SlidesApi(None, "MyClientId", "MyClientSecret")

file_name = "MyPresentation.pptx"
slide_index = 9
shape_index = 1
row_index = 2
cell_index = 2
paragraph_index = 3

paragraphs = slides_api.delete_table_cell_paragraph(file_name, slide_index, shape_index, row_index, cell_index, paragraph_index)

paragraph_count = len(paragraphs.paragraph_links)
print("Number of paragraphs: ", paragraph_count)  # 2
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

slidesApi.deleteTableCellParagraph(fileName, slideIndex, shapeIndex, rowIndex, cellIndex, paragraphIndex).then(paragraphs => {
    paragraphCount = paragraphs.body.paragraphLinks.length;
    console.log("Number of paragraphs:", paragraphCount); // 2
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

	paragraphs, _, _ := slidesApi.DeleteTableCellParagraph(fileName, slideIndex, shapeIndex, rowIndex, cellIndex, paragraphIndex, "", "", "")

	paragraphCount := len(paragraphs.GetParagraphLinks())
	fmt.Println("Paragraphs count:", paragraphCount) // 2
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

    std::shared_ptr<Paragraphs> paragraphs = slidesApi->deleteTableCellParagraph(fileName, slideIndex, shapeIndex, rowIndex, cellIndex, paragraphIndex).get();

    int paragraphCount = paragraphs->getParagraphLinks().size();
    std::wcout << L"Number of paragraphs: " << paragraphCount; // 2
}
```
{{< /tab >}}

{{< tab tabNum="9" >}}
```perl
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

my $paragraphs = $slides_api->delete_table_cell_paragraph(
    name => $file_name, slide_index => $slide_index, shape_index => $shape_index, row_index => $row_index, cell_index => $cell_index, paragraph_index => $paragraph_index);

my $paragraph_count = @{$paragraphs->{paragraph_links}};
print "Number of paragraphs: $paragraph_count"; # 2
```
{{< /tab >}}

{{< /tabs >}}

The result:

![The table](output.png)

## **SDKs**

Check [Available SDKs](/slides/available-sdks/) to learn how to add an SDK to your project.
