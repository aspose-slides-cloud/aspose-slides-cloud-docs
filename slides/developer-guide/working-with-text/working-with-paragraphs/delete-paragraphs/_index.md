---
title: "Delete Paragraphs"
type: docs
url: /delete-paragraphs/
weight: 70
---

## **Introduction**

Deletion of paragraphs typically pertains to editing text blocks in slides. The following methods allow you to delete a specific paragraph or range of paragraphs.

## **DeleteParagraph**

### **API Information**

|**API**|**Type**|**Description**|**Resource**|
| :- | :- | :- | :- |
|/slides/{name}/slides/{slideIndex}/shapes/{shapeIndex}/paragraphs/{paragraphIndex}|DELETE|Deletes a paragraph in a shape.|[DeleteParagraph](https://apireference.aspose.cloud/slides/#/Shapes/DeleteParagraph)|

**Request Parameters**

|**Name**|**Type**|**Location**|**Required**|**Description**|
| :- | :- | :- | :- | :- |
|name|string|path|true|The presentation file name.|
|slideIndex|integer|path|true|The 1-based index of the presentation slide.|
|shapeIndex|integer|path|true|The 1-based index of the shape.|
|paragraphIndex|integer|path|true|The 1-based index of the paragraph.|
|password|string|header|false|The password to open the presentation.|
|folder|string|query|false|The folder where the presentation file is located.|
|storage|string|query|false|The storage where the presentation file is located.|
|subShape|string|query|false|The sub-shape path (e.g. "3", "3/shapes/2").|

*In case of Amazon S3 storage folder path starts with Amazon S3 bucket name.*

### **Examples**

In the document **MyPresentation.pptx**, the **first** slide contains **one** shape (text box) with **three** paragraphs. Delete the **second** paragraph from the shape.

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
curl -X DELETE "https://api.aspose.cloud/v3.0/slides/MyPresentation.pptx/slides/1/shapes/1/paragraphs/2" \
     -H "authorization: Bearer MyAccessToken"
```

{{< /tab >}}

{{< tab tabNum="2" >}}

**Response Example**

```json
{
  "paragraphLinks": [
    {
      "href": "https://api.aspose.cloud/v3.0/slides/MyPresentation.pptx/slides/1/shapes/1/paragraphs/1",
      "relation": "self",
      "slideIndex": 1,
      "shapeIndex": 1
    },
    {
      "href": "https://api.aspose.cloud/v3.0/slides/MyPresentation.pptx/slides/1/shapes/1/paragraphs/2",
      "relation": "self",
      "slideIndex": 1,
      "shapeIndex": 1
    }
  ],
  "selfUri": {
    "href": "https://api.aspose.cloud/v3.0/slides/MyPresentation.pptx/slides/1/shapes/1/paragraphs",
    "relation": "self",
    "slideIndex": 1,
    "shapeIndex": 1
  }
}
```

{{< /tab >}}

{{< /tabs >}}

**SDK Solutions**

{{< tabs tabTotal="11" tabID="11" tabName1="C#" tabName2="Java" tabName3="PHP" tabName4="Ruby" tabName5="Python" tabName6="Node.js" tabName7="C++" tabName8="Perl" tabName9="Swift" tabName10="Go" >}}

{{< tab tabNum="1" >}}

```csharp
using System;
using Aspose.Slides.Cloud.Sdk;

class Application
{
    static void Main(string[] args)
    {
        var slidesApi = new SlidesApi("MyClientId", "MyClientSecret");

        var documentName = "MyPresentation.pptx";
        var slideIndex = 1;
        var shapeIndex = 1;
        var paragraphIndex = 2;

        var paragraphsInfo = slidesApi.DeleteParagraph(documentName, slideIndex, shapeIndex, paragraphIndex);

        var paragraphCount = paragraphsInfo.ParagraphLinks.Count;
        Console.WriteLine("Number of remaining paragraphs: " + paragraphCount); // 2
    }
}
```

{{< /tab >}}

{{< tab tabNum="2" >}}

```java
import com.aspose.slides.ApiException;
import com.aspose.slides.api.SlidesApi;

public class Application {
    public static void main(String[] args) throws ApiException {
        var slidesApi = new SlidesApi("MyClientId", "MyClientSecret");

        var documentName = "MyPresentation.pptx";
        var slideIndex = 1;
        var shapeIndex = 1;
        var paragraphIndex = 2;

        var paragraphsInfo = slidesApi.deleteParagraph(documentName, slideIndex, shapeIndex, paragraphIndex, null, null, null, null);

        var paragraphCount = paragraphsInfo.getParagraphLinks().size();
        System.out.println("Number of remaining paragraphs: " + paragraphCount); // 2
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

$documentName = "MyPresentation.pptx";
$slideIndex = 1;
$shapeIndex = 1;
$paragraphIndex = 2;

$paragraphsInfo = $slidesApi->deleteParagraph($documentName, $slideIndex, $shapeIndex, $paragraphIndex);

$paragraphCount = count($paragraphsInfo->getParagraphLinks());
echo "Number of remaining paragraphs: ", $paragraphCount; // 2
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

document_name = "MyPresentation.pptx"
slide_index = 1
shape_index = 1
paragraph_index = 2

paragraphs_info = slides_api.delete_paragraph(document_name, slide_index, shape_index, paragraph_index)

paragraph_count = paragraphs_info.paragraph_links.length()
print "Number of remaining paragraphs: ", paragraph_count # 2
```

{{< /tab >}}

{{< tab tabNum="5" >}}

```python
from asposeslidescloud.apis.slides_api import SlidesApi

slides_api = SlidesApi(None, "MyClientId", "MyClientSecret")

document_name = "MyPresentation.pptx"
slide_index = 1
shape_index = 1
paragraph_index = 2

paragraphs_info = slides_api.delete_paragraph(document_name, slide_index, shape_index, paragraph_index)

paragraph_count = len(paragraphs_info.paragraph_links)
print("Number of remaining paragraphs:", paragraph_count)  # 2
```

{{< /tab >}}

{{< tab tabNum="6" >}}

```js
const cloud = require("asposeslidescloud");

const slidesApi = new cloud.SlidesApi("MyClientId", "MyClientSecret");

const documentName = "MyPresentation.pptx";
const slideIndex = 1;
const shapeIndex = 1;
const paragraphIndex = 2;

slidesApi.deleteParagraph(documentName, slideIndex, shapeIndex, paragraphIndex).then(paragraphsInfo => {
    const paragraphCount = paragraphsInfo.body.paragraphLinks.length;
    console.log("Number of remaining paragraphs:", paragraphCount); // 2
})
.catch(error => {
    console.error(error.message);
});
```

{{< /tab >}}

{{< tab tabNum="7" >}}

```cpp
#include "asposeslidescloud/api/SlidesApi.h"

using namespace asposeslidescloud::api;

int main()
{
    auto slidesApi = std::make_shared<SlidesApi>(L"MyClientId", L"MyClientSecret");

    auto documentName = L"MyPresentation.pptx";
    auto slideIndex = 1;
    auto shapeIndex = 1;
    auto paragraphIndex = 2;

    auto paragraphsInfo = slidesApi->deleteParagraph(documentName, slideIndex, shapeIndex, paragraphIndex).get();

    auto paragraphCount = paragraphsInfo->getParagraphLinks().size();
    std::cout << "Number of remaining paragraphs: " << paragraphCount; // 2
}
```

{{< /tab >}}

{{< tab tabNum="8" >}}

```perl
use AsposeSlidesCloud::Configuration;
use AsposeSlidesCloud::SlidesApi;

my $config = AsposeSlidesCloud::Configuration->new();
$config->{app_sid} = "MyClientId";
$config->{app_key} = "MyClientSecret";

my $slides_api = AsposeSlidesCloud::SlidesApi->new(config => $config);

my %parameters = (name => "MyPresentation.pptx", slide_index => 1, shape_index => 1, paragraph_index => 2);

my $paragraphs_info = $slides_api->delete_paragraph(%parameters);
 
my $paragraph_count = @{$paragraphs_info->{paragraph_links}};
print("Number of remaining paragraphs: ", $paragraph_count); # 2
```

{{< /tab >}}

{{< tab tabNum="9" >}}

{{< /tab >}}

{{< tab tabNum="10" >}}

{{< /tab >}}

{{< /tabs >}}

## **DeleteParagraphs**

### **API Information**

|**API**|**Type**|**Description**|**Resource**|
| :- | :- | :- | :- |
|/slides/{name}/slides/{slideIndex}/shapes/{shapeIndex}/paragraphs|DELETE|Deletes a range of paragraphs in a shape.|[DeleteParagraphs](https://apireference.aspose.cloud/slides/#/Shapes/DeleteParagraphs)|

**Request Parameters**

|**Name**|**Type**|**Location**|**Required**|**Description**|
| :- | :- | :- | :- | :- |
|name|string|path|true|The presentation file name.|
|slideIndex|integer|path|true|The 1-based index of the presentation slide.|
|shapeIndex|integer|path|true|The 1-based index of the shape.|
|paragraphs|string|query|false|The indices of paragraphs to be deleted. Delete all by default.|
|password|string|header|false|The password to open the presentation.|
|folder|string|query|false|The folder where the presentation file is located.|
|storage|string|query|false|The storage where the presentation file is located.|
|subShape|string|query|false|The sub-shape path (e.g. "3", "3/shapes/2").|

*In case of Amazon S3 storage folder path starts with Amazon S3 bucket name.*

### **Examples**

In the document **MyPresentation.pptx**, the **second** slide contains **one** shape (text box) with **five** paragraphs. Delete the paragraphs with indices **1**, **3**, and **5**.

**cURL Solution**

{{< tabs tabTotal="2" tabID="1" tabName1="Request" tabName2="Response" >}}

{{< tab tabNum="1" >}}

**Get an Access Token**

```sh
curl POST "https://api.aspose.cloud/connect/token" \
     -d "grant_type=client_credentials&client_id=MyClientId&client_secret=MyClientSecret" \
     -H "Content-Type: application/x-www-form-urlencoded"
```

**Delete the Paragraphs**

```sh
curl -X DELETE "https://api.aspose.cloud/v3.0/slides/MyPresentation.pptx/slides/2/shapes/1/paragraphs?paragraphs=1,3,5" \
     -H "authorization: Bearer MyAccessToken"
```

{{< /tab >}}

{{< tab tabNum="2" >}}

**Response Example**

```json
{
  "paragraphLinks": [
    {
      "href": "https://api.aspose.cloud/v3.0/slides/MyPresentation.pptx/slides/2/shapes/1/paragraphs/1",
      "relation": "self",
      "slideIndex": 2,
      "shapeIndex": 1
    },
    {
      "href": "https://api.aspose.cloud/v3.0/slides/MyPresentation.pptx/slides/2/shapes/1/paragraphs/2",
      "relation": "self",
      "slideIndex": 2,
      "shapeIndex": 1
    }
  ],
  "selfUri": {
    "href": "https://api.aspose.cloud/v3.0/slides/MyPresentation.pptx/slides/2/shapes/1/paragraphs",
    "relation": "self",
    "slideIndex": 2,
    "shapeIndex": 1
  }
}
```

{{< /tab >}}

{{< /tabs >}}


**SDK Solutions**

{{< tabs tabTotal="11" tabID="11" tabName1="C#" tabName2="Java" tabName3="PHP" tabName4="Ruby" tabName5="Python" tabName6="Node.js" tabName7="C++" tabName8="Perl" tabName9="Swift" tabName10="Go" >}}

{{< tab tabNum="1" >}}

```csharp
using System;
using System.Collections.Generic;
using Aspose.Slides.Cloud.Sdk;

class Application
{
    static void Main(string[] args)
    {
        var slidesApi = new SlidesApi("MyClientId", "MyClientSecret");

        var documentName = "MyPresentation.pptx";
        var slideIndex = 2;
        var shapeIndex = 1;
        var paragraphIndices = new List<int> { 1, 3, 5 };

        var paragraphsInfo = slidesApi.DeleteParagraphs(documentName, slideIndex, shapeIndex, paragraphIndices);

        var paragraphCount = paragraphsInfo.ParagraphLinks.Count;
        Console.WriteLine("Number of remaining paragraphs: " + paragraphCount); // 2
    }
}
```

{{< /tab >}}

{{< tab tabNum="2" >}}

```java
import com.aspose.slides.ApiException;
import com.aspose.slides.api.SlidesApi;
import java.util.Arrays;

public class Application {
    public static void main(String[] args) throws ApiException {
        var slidesApi = new SlidesApi("MyClientId", "MyClientSecret");

        var documentName = "MyPresentation.pptx";
        var slideIndex = 2;
        var shapeIndex = 1;
        var paragraphIndices = Arrays.asList(1, 3, 5);

        var paragraphsInfo = slidesApi.deleteParagraphs(documentName, slideIndex, shapeIndex, paragraphIndices, null, null, null, null);

        var paragraphCount = paragraphsInfo.getParagraphLinks().size();
        System.out.println("Number of remaining paragraphs: " + paragraphCount); // 2
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

$documentName = "MyPresentation.pptx";
$slideIndex = 2;
$shapeIndex = 1;
$paragraphIndices = [1, 3, 5];

$paragraphsInfo = $slidesApi->deleteParagraphs($documentName, $slideIndex, $shapeIndex, $paragraphIndices);

$paragraphCount = count($paragraphsInfo->getParagraphLinks());
echo "Number of remaining paragraphs: ", $paragraphCount; // 2
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

document_name = "MyPresentation.pptx"
slide_index = 2
shape_index = 1
paragraph_indices = [1, 3, 5]

paragraphs_info = slides_api.delete_paragraphs(document_name, slide_index, shape_index, paragraph_indices)

paragraph_count = paragraphs_info.paragraph_links.length()
print "Number of remaining paragraphs: ", paragraph_count # 2
```

{{< /tab >}}

{{< tab tabNum="5" >}}

```python
from asposeslidescloud.apis.slides_api import SlidesApi

slides_api = SlidesApi(None, "MyClientId", "MyClientSecret")

document_name = "MyPresentation.pptx"
slide_index = 2
shape_index = 1
paragraph_indices = [1, 3, 5]

paragraphs_info = slides_api.delete_paragraphs(document_name, slide_index, shape_index, paragraph_indices)

paragraph_count = len(paragraphs_info.paragraph_links)
print("Number of remaining paragraphs:", paragraph_count)  # 2
```

{{< /tab >}}

{{< tab tabNum="6" >}}

```js
const cloud = require("asposeslidescloud");

const slidesApi = new cloud.SlidesApi("MyClientId", "MyClientSecret");

const documentName = "MyPresentation.pptx";
const slideIndex = 2;
const shapeIndex = 1;
const paragraphIndices = [1, 3, 5];

slidesApi.deleteParagraphs(documentName, slideIndex, shapeIndex, paragraphIndices).then(paragraphsInfo => {
    const paragraphCount = paragraphsInfo.body.paragraphLinks.length;
    console.log("Number of remaining paragraphs:", paragraphCount); // 2
})
.catch(error => {
    console.error(error.message);
});
```

{{< /tab >}}

{{< tab tabNum="7" >}}

```cpp
#include "asposeslidescloud/api/SlidesApi.h"

using namespace asposeslidescloud::api;

int main()
{
    auto slidesApi = std::make_shared<SlidesApi>(L"MyClientId", L"MyClientSecret");

    auto documentName = L"MyPresentation.pptx";
    auto slideIndex = 2;
    auto shapeIndex = 1;
    auto paragraphIndices = { 1, 3, 5 };

    auto paragraphsInfo = slidesApi->deleteParagraphs(documentName, slideIndex, shapeIndex, paragraphIndices).get();

    auto paragraphCount = paragraphsInfo->getParagraphLinks().size();
    std::cout << "Number of remaining paragraphs: " << paragraphCount; // 2
}
```

{{< /tab >}}

{{< tab tabNum="8" >}}

```perl
use AsposeSlidesCloud::Configuration;
use AsposeSlidesCloud::SlidesApi;

my $config = AsposeSlidesCloud::Configuration->new();
$config->{app_sid} = "MyClientId";
$config->{app_key} = "MyClientSecret";

my $slides_api = AsposeSlidesCloud::SlidesApi->new(config => $config);

my @paragraph_indices = (1, 3, 5);
my %parameters = (name => "MyPresentation.pptx", slide_index => 2, shape_index => 1, paragraphs => \@paragraph_indices);

my $paragraphs_info = $slides_api->delete_paragraphs(%parameters);
 
my $paragraph_count = @{$paragraphs_info->{paragraph_links}};
print("Number of remaining paragraphs: ", $paragraph_count); # 2
```

{{< /tab >}}

{{< tab tabNum="9" >}}

{{< /tab >}}

{{< tab tabNum="10" >}}

{{< /tab >}}

{{< /tabs >}}

## **SDKs**

Check [Available SDKs](/slides/available-sdks/) to learn how to add an SDK to your project.
