---
title: "Get a Paragraph Rectangle"
keywords:
- PowerPoint
- presentation
- REST API
- cloud API
- text
- paragraph
- coordinates
- text bounds
- paragraph bounds
- paragraph coordinates
- get bounds
- paragraph width
- paragraph height
type: docs
url: /get-a-paragraph-rectangle/
weight: 60
---

## **Introduction**

Coordinates and sizes of paragraphs in PowerPoint presentations play a major role in the visual organization and perception of information on a slide. Coordinates determine the position of the paragraph in a text box, and sizes define the width and height of the paragraph. Use the following method to get coordinates and size of a paragraph.

{{% alert color="primary" %}} 
There is [a similar method](/slides/get-a-rectangle-of-a-text-portion/) for getting the coordinates and dimensions of a text portion.
{{% /alert %}}

## **GetParagraphRectangle**

### **API Information**

|**API**|**Type**|**Description**|**Resource**|
| :- | :- | :- | :- |
|/slides/{name}/slides/{slideIndex}/shapes/{shapeIndex}/paragraphs/{paragraphIndex}/bounds|GET|Returns coordinates and dimensions of a paragraph from a presentation saved in a storage.|[GetParagraphRectangle](https://reference.aspose.cloud/slides/#/Shapes/GetParagraphRectangle)|

**Request Parameters**

|**Name**|**Type**|**Location**|**Required**|**Description**|
| :- | :- | :- | :- | :- |
|name|string|path|true|The name of a presentation file.|
|slideIndex|integer|path|true|The 1-based index of a slide.|
|shapeIndex|integer|path|true|The 1-based index of a shape.|
|paragraphIndex|integer|path|true|The 1-based index of a paragraph.|
|password|string|header|false|The password to open the presentation.|
|folder|string|query|false|The path to the folder containing the presentation file.|
|storage|string|query|false|The name of the storage contaning the folder.|

### **Examples**

In the **default** storage, the document **MyPresentation.pptx** contains a text box (the **first** shape) on the **first** slide. The text box contains two paragraphs. Get the coordinates and dimensions of the **second** paragraph.

![The slide](input.png)

**cURL Solution**

{{< tabs tabTotal="2" tabID="1" tabName1="Request" tabName2="Response" >}}

{{< tab tabNum="1" >}}
**Get an Access Token**
```sh
curl -X POST "https://api.aspose.cloud/connect/token" \
     -d "grant_type=client_credentials&client_id=MyClientId&client_secret=MyClientSecret" \
     -H "Content-Type: application/x-www-form-urlencoded"
```

**Get the Paragraph Bounds**
```sh
curl -X GET "https://api.aspose.cloud/v3.0/slides/MyPresentation.pptx/slides/1/shapes/1/paragraphs/2/bounds" \
     -H "authorization: Bearer MyAccessToken"
```
{{< /tab >}}

{{< tab tabNum="2" >}}

```json
{
  "x": 7.199997,
  "y": 25.199999,
  "width": 166.6123,
  "height": 21.599998
}
```
{{< /tab >}}

{{< /tabs >}}

**SDK Solutions**

{{< tabs tabTotal="9" tabID="5" tabName1="C#" tabName2="Java" tabName3="PHP" tabName4="Ruby" tabName5="Python" tabName6="Node.js" tabName7="Go" tabName8="C++" tabName9="Perl" >}}

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
        int shapeIndex = 1;
        int paragraphIndex = 2;

        TextBounds paragraphBounds = slidesApi.GetParagraphRectangle(fileName, slideIndex, shapeIndex, paragraphIndex);

        Console.WriteLine("X: " + paragraphBounds.X);
        Console.WriteLine($"Y: " + paragraphBounds.Y);
        Console.WriteLine($"Width: " + paragraphBounds.Width);
        Console.WriteLine($"Height: " + paragraphBounds.Height);
    }
}

// Example output:
//
// X: 7.199997
// Y: 25.199999
// Width: 166.6123
// Height: 21.599998
```
{{< /tab >}}

{{< tab tabNum="2" >}}
```java
import com.aspose.slides.ApiException;
import com.aspose.slides.api.SlidesApi;
import com.aspose.slides.model.TextBounds;

public class Application {
    public static void main(String[] args) throws ApiException {
        SlidesApi slidesApi = new SlidesApi("MyClientId", "MyClientSecret");

        String fileName = "MyPresentation.pptx";
        int slideIndex = 1;
        int shapeIndex = 1;
        int paragraphIndex = 2;

        TextBounds paragraphBounds = slidesApi.getParagraphRectangle(fileName, slideIndex, shapeIndex, paragraphIndex, null, null, null);

        System.out.println("X: " + paragraphBounds.getX());
        System.out.println("Y: " + paragraphBounds.getY());
        System.out.println("Width: " + paragraphBounds.getWidth());
        System.out.println("Height: " + paragraphBounds.getHeight());
    }
}

// Example output:
//
// X: 7.199997
// Y: 25.199999
// Width: 166.6123
// Height: 21.599998
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
$slideIndex = 1;
$shapeIndex = 1;
$paragraphIndex = 2;

$paragraphBounds = $slidesApi->getParagraphRectangle($fileName, $slideIndex, $shapeIndex, $paragraphIndex);

print("X: " . $paragraphBounds->getX() . "\n");
print("Y: " . $paragraphBounds->getY() . "\n");
print("Width: " . $paragraphBounds->getWidth() . "\n");
print("Height: " . $paragraphBounds->getHeight() . "\n");

// Example output:
//
// X: 7.199997
// Y: 25.199999
// Width: 166.6123
// Height: 21.599998
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
shape_index = 1
paragraph_index = 2

paragraph_bounds = slides_api.get_paragraph_rectangle(file_name, slide_index, shape_index, paragraph_index)

puts "X: #{paragraph_bounds.x}"
puts "Y: #{paragraph_bounds.y}"
puts "Width: #{paragraph_bounds.width}"
puts "Height: #{paragraph_bounds.height}"

# X: 7.199997
# Y: 25.199999
# Width: 166.6123
# Height: 21.599998
```
{{< /tab >}}

{{< tab tabNum="5" >}}
```py
from asposeslidescloud.apis import SlidesApi

slides_api = SlidesApi(None, "MyClientId", "MyClientSecret")

file_name = "MyPresentation.pptx"
slide_index = 1
shape_index = 1
paragraph_index = 2

paragraph_bounds = slides_api.get_paragraph_rectangle(file_name, slide_index, shape_index, paragraph_index)

print("X:", paragraph_bounds.x)
print("Y:", paragraph_bounds.y)
print("Width:", paragraph_bounds.width)
print("Height:", paragraph_bounds.height)

# X: 7.199997
# Y: 25.199999
# Width: 166.6123
# Height: 21.599998
```
{{< /tab >}}

{{< tab tabNum="6" >}}
```js
const cloudSdk = require("asposeslidescloud");

const slidesApi = new cloudSdk.SlidesApi("MyClientId", "MyClientSecret");

fileName = "MyPresentation.pptx";
slideIndex = 1;
shapeIndex = 1;
paragraphIndex = 2;

slidesApi.getParagraphRectangle(fileName, slideIndex, shapeIndex, paragraphIndex).then(paragraphBounds => {
    console.log("X:", paragraphBounds.body.x);
    console.log("Y:", paragraphBounds.body.y);
    console.log("Width:", paragraphBounds.body.width);
    console.log("Height:", paragraphBounds.body.height);
});

// Example output:
//
// X: 7.199997
// Y: 25.199999
// Width: 166.6123
// Height: 21.599998
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
	var slideIndex int32 = 1
	var shapeIndex int32 = 1
	var paragraphIndex int32 = 2

	paragraphBounds, _, _ := slidesApi.GetParagraphRectangle(fileName, slideIndex, shapeIndex, paragraphIndex, "", "", "")

	fmt.Println("X:", paragraphBounds.GetX())
	fmt.Println("Y:", paragraphBounds.GetY())
	fmt.Println("Width:", paragraphBounds.GetWidth())
	fmt.Println("Height:", paragraphBounds.GetHeight())
}

// Example output:
//
// X: 7.199997
// Y: 25.199999
// Width: 166.6123
// Height: 21.59999
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
    int slideIndex = 1;
    int shapeIndex = 1;
    int paragraphIndex = 2;

    std::shared_ptr<TextBounds> paragraphBounds = slidesApi->getParagraphRectangle(fileName, slideIndex, shapeIndex, paragraphIndex).get();

    std::wcout << L"X: " << paragraphBounds->getX() << std::endl;
    std::wcout << L"Y: " << paragraphBounds->getY() << std::endl;
    std::wcout << L"Width: " << paragraphBounds->getWidth() << std::endl;
    std::wcout << L"Height: " << paragraphBounds->getHeight() << std::endl;
}

// Example output:
//
// X: 7.2
// Y: 25.2
// Width: 166.612
// Height: 21.6
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

my $paragraph_bounds = $slides_api->get_paragraph_rectangle(
    name => "MyPresentation.pptx",
    slide_index => 1,
    shape_index => 1,
    paragraph_index => 2);

print "X: $paragraph_bounds->{x}\n";
print "Y: $paragraph_bounds->{y}\n";
print "Width: $paragraph_bounds->{width}\n";
print "Height: $paragraph_bounds->{height}\n";

# X: 7.199997
# Y: 25.199999
# Width: 166.6123
# Height: 21.599998
```

{{< /tab >}}

{{< /tabs >}}

## **SDKs**

Check [Available SDKs](/slides/available-sdks/) to learn how to add an SDK to your project.
