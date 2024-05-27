---
title: "Merge Table Cells"
keywords:
- PowerPoint
- presentation
- REST API
- cloud API
- table
- merge cells
type: docs
url: /merge-table-cells/
weight: 40
---

## **Introduction**

Merging table cells in PowerPoint documents is the process of combining two or more cells into one larger cell. This is useful for creating headers, improving the appearance of the table, and enhancing data readability. After merging the cells, you can adjust the formatting of the merged cell to make it look appropriate. This includes changing the font size, text alignment, etc. Use the following method to merge table cells in a presentation.

## **MergeTableCells**

### **API Information**

|**API**|**Type**|**Description**|**Resource**|
| :- | :- | :- | :- |
|/slides/{name}/slides/{slideIndex}/shapes/{shapeIndex}/mergeCells|POST|Merges table cells in a presentation saved in a storage.|[MergeTableCells](https://reference.aspose.cloud/slides/#/Table/MergeTableCells)|

**Request Parameters**

|**Name**|**Type**|**Location**|**Required**|**Description**|
| :- | :- | :- | :- | :- |
|name|string|path|true|The name of a presentation file.|
|slideIndex|integer|path|true|The 1-based index of a slide.|
|shapeIndex|integer|path|true|The 1-based index of a shape (must be a table).|
|tableCellMergeOptions|`TableCellMergeOptions`|body|true|The data transfer object with merge parameters.|
|password|string|header|false|The password to open the presentation.|
|folder|string|query|false|The path to the folder containing the presentation file.|
|storage|string|query|false|The name of the storage contaning the folder.|

### **Examples**

In the **default** storage, the document **MyPresentation.pptx** contains a table with 3 columns and 4 rows. Merge the four cells **(1,1)**, **(1,2)**, **(2,1)**, and **(2,2)** into one cell.

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

**Merge the Cells**

```sh
curl -X POST "https://api.aspose.cloud/v3.0/slides/MyPresentation.pptx/slides/1/shapes/2/mergeCells" \
     -H "authorization: Bearer MyAccessToken" \
     -H "Content-Type: application/json" \
     -d @MergeCells.json
```

MergeCells.json content:
```json
{
  "FirstRowIndex": 1,
  "FirstCellIndex": 1,
  "LastRowIndex": 2,
  "LastCellIndex": 2
}
```

{{< /tab >}}

{{< tab tabNum="2" >}}

```text
Code: 200
Returns table info.
```

{{< /tab >}}

{{< /tabs >}}

**SDK Solutions**

{{< tabs tabTotal="9" tabID="11" tabName1="C#" tabName2="Java" tabName3="PHP" tabName4="Ruby" tabName5="Python" tabName6="Node.js" tabName7="C++" tabName8="Perl" tabName9="Go" >}}

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

        TableCellMergeOptions mergeOptions = new TableCellMergeOptions
        {
            FirstRowIndex = 1,
            FirstCellIndex = 1,
            LastRowIndex = 2,
            LastCellIndex = 2
        };

        Table table = slidesApi.MergeTableCells(fileName, slideIndex, shapeIndex, mergeOptions);

        TableCell cell = table.Rows[0].Cells[0];
        Console.WriteLine("Column span: " + cell.ColSpan); // 2
        Console.WriteLine("Row span: " + cell.RowSpan);    // 2
    }
}
```

{{< /tab >}}

{{< tab tabNum="2" >}}

```java
import com.aspose.slides.ApiException;
import com.aspose.slides.api.SlidesApi;
import com.aspose.slides.model.TableCell;
import com.aspose.slides.model.TableCellMergeOptions;
import com.aspose.slides.model.Table;

public class Application {
    public static void main(String[] args) throws ApiException {
        SlidesApi slidesApi = new SlidesApi("MyClientId", "MyClientSecret");

        String fileName = "MyPresentation.pptx";
        int slideIndex = 1;
        int shapeIndex = 2;

        TableCellMergeOptions mergeOptions = new TableCellMergeOptions();
        mergeOptions.setFirstRowIndex(1);
        mergeOptions.setFirstCellIndex(1);
        mergeOptions.setLastRowIndex(2);
        mergeOptions.setLastCellIndex(2);

        Table table = slidesApi.mergeTableCells(fileName, slideIndex, shapeIndex, mergeOptions, null, null, null);

        TableCell cell = table.getRows().get(0).getCells().get(0);
        System.out.println("Column span: " + cell.getColSpan()); // 2
        System.out.println("Row span: " + cell.getRowSpan());    // 2
    }
}
```

{{< /tab >}}

{{< tab tabNum="3" >}}

```php
use Aspose\Slides\Cloud\Sdk\Api\Configuration;
use Aspose\Slides\Cloud\Sdk\Api\SlidesApi;
use Aspose\Slides\Cloud\Sdk\Model\TableCellMergeOptions;

$configuration = new Configuration();
$configuration->setAppSid("MyClientId");
$configuration->setAppKey("MyClientSecret");

$slidesApi = new SlidesApi(null, $configuration);

$fileName = "MyPresentation.pptx";
$slideIndex = 1;
$shapeIndex = 2;

$mergeOptions = new TableCellMergeOptions();
$mergeOptions->setFirstRowIndex(1);
$mergeOptions->setFirstCellIndex(1);
$mergeOptions->setLastRowIndex(2);
$mergeOptions->setLastCellIndex(2);

$table = $slidesApi->mergeTableCells($fileName, $slideIndex, $shapeIndex, $mergeOptions);

$cell = $table->getRows()[0]->getCells()[0];
echo "Column span: " . $cell->getColSpan() . "\n"; // 2
echo "Row span: " . $cell->getRowSpan() . "\n";    // 2
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

merge_options = TableCellMergeOptions.new
merge_options.first_row_index = 1
merge_options.first_cell_index = 1
merge_options.last_row_index = 2
merge_options.last_cell_index = 2

table = slides_api.merge_table_cells(file_name, slide_index, shape_index, merge_options)

cell = table.rows[0].cells[0]
puts "Column span: #{cell.col_span}" # 2
puts "Row span: #{cell.row_span}"    # 2
```

{{< /tab >}}

{{< tab tabNum="5" >}}

```py
from asposeslidescloud.apis import SlidesApi
from asposeslidescloud.models import TableCellMergeOptions

slides_api = SlidesApi(None, "MyClientId", "MyClientSecret")

file_name = "MyPresentation.pptx"
slide_index = 1
shape_index = 2

merge_options = TableCellMergeOptions()
merge_options.first_row_index = 1
merge_options.first_cell_index = 1
merge_options.last_row_index = 2
merge_options.last_cell_index = 2

table = slides_api.merge_table_cells(file_name, slide_index, shape_index, merge_options)

cell = table.rows[0].cells[0]
print("Column span:", cell.col_span)  # 2
print("Row span:", cell.row_span)     # 2
```

{{< /tab >}}

{{< tab tabNum="6" >}}

```js
const cloudSdk = require("asposeslidescloud");

const slidesApi = new cloudSdk.SlidesApi("MyClientId", "MyClientSecret");

fileName = "MyPresentation.pptx";
slideIndex = 1;
shapeIndex = 2;

mergeOptions = new cloudSdk.TableCellMergeOptions();
mergeOptions.firstRowIndex = 1;
mergeOptions.firstCellIndex = 1;
mergeOptions.lastRowIndex = 2;
mergeOptions.lastCellIndex = 2;

slidesApi.mergeTableCells(fileName, slideIndex, shapeIndex, mergeOptions).then(table => {
    cell = table.body.rows[0].cells[0]
    console.log("Column span:", cell.colSpan); // 2
    console.log("Row span:", cell.rowSpan);    // 2
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

    std::shared_ptr<TableCellMergeOptions> mergeOptions = std::make_shared<TableCellMergeOptions>();
    mergeOptions->setFirstRowIndex(1);
    mergeOptions->setFirstCellIndex(1);
    mergeOptions->setLastRowIndex(2);
    mergeOptions->setLastCellIndex(2);

    std::shared_ptr<Table> table = slidesApi->mergeTableCells(fileName, slideIndex, shapeIndex, mergeOptions).get();

    std::shared_ptr<TableCell> cell = table->getRows()[0]->getCells()[0];
    std::wcout << L"Column span: " << cell->getColSpan() << std::endl; // 2
    std::wcout << L"Row span: " << cell->getRowSpan() << std::endl;    // 2
}
```

{{< /tab >}}

{{< tab tabNum="8" >}}

```pl
use AsposeSlidesCloud::Configuration;
use AsposeSlidesCloud::SlidesApi;
use AsposeSlidesCloud::Object::TableCellMergeOptions;

my $configuration = AsposeSlidesCloud::Configuration->new();
$configuration->{app_sid} = "MyClientId";
$configuration->{app_key} = "MyClientSecret";

my $slides_api = AsposeSlidesCloud::SlidesApi->new(config => $configuration);

my $file_name = "MyPresentation.pptx";
my $slide_index = 1;
my $shape_index = 2;

my $merge_options = AsposeSlidesCloud::Object::TableCellMergeOptions->new();
$merge_options->{first_row_index} = 1;
$merge_options->{first_cell_index} = 1;
$merge_options->{last_row_index} = 2;
$merge_options->{last_cell_index} = 2;

my $table = $slides_api->merge_table_cells(
    name => $file_name, slide_index => $slide_index, shape_index => $shape_index, table_cell_merge_options => $merge_options);

my $cell = $table->{rows}[0]{cells}[0];
print "Column span: $cell->{col_span}\n"; # 2
print "Row span: $cell->{row_span}\n";    # 2
```

{{< /tab >}}

{{< tab tabNum="9" >}}

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

	mergeOptions := asposeslidescloud.NewTableCellMergeOptions()
	mergeOptions.FirstRowIndex = 1
	mergeOptions.FirstCellIndex = 1
	mergeOptions.LastRowIndex = 2
	mergeOptions.LastCellIndex = 2

	table, _, _ := slidesApi.MergeTableCells(fileName, slideIndex, shapeIndex, mergeOptions, "", "", "")

	cell := table.GetRows()[0].GetCells()[0]
	fmt.Println("Column span:", cell.GetColSpan()) // 2
	fmt.Println("Row span:", cell.GetRowSpan())    // 2
}
```

{{< /tab >}}

{{< /tabs >}}

The result:

![The table](output.png)

## **SDKs**

Check [Available SDKs](/slides/available-sdks/) to learn how to add an SDK to your project.
