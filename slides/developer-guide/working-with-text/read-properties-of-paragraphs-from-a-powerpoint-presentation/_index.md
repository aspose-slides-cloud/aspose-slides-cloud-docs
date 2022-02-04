---
title: "Read Properties of Paragraphs from a PowerPoint Presentation"
type: docs
url: /read-properties-of-paragraphs-from-a-powerpoint-presentation/
weight: 10
---

## **Introduction**
This article shows how you can read the formatting properties of paragraphs from PowerPoint presentations using Aspose.Slides for Cloud API. You can use our REST API with any language: .NET, Java, PHP, Ruby, Rails, Python, jQuery, and much more.

## **API Information**

|**API**|**Type**|**Description**|**Resource**|
| :- | :- | :- | :- |
|/slides/{name}/slides/{slideIndex}/shapes/{shapeIndex}/paragraphs|GET|Reads properties of paragraphs in a shape.|[GetParagraphs](https://apireference.aspose.cloud/slides/#/Shapes/GetParagraphs)|

### **Request Parameters**

|**Name**|**Type**|**Location**|**Required**|**Description**|
| :- | :- | :- | :- | :- |
|name|string|path|true|The presentation file name.|
|slideIndex|integer|path|true|The 1-based index of the presentation slide.|
|shapeIndex|integer|path|true|The 1-based index of the shape.|
|password|string|header|false|The password to open the presentation.|
|folder|string|query|false|The folder where the presentation file is located.|
|storage|string|query|false|The storage where the presentation file is located.|

*In case of Amazon S3 storage folder path starts with Amazon S3 bucket name.*

## **cURL Example**
Read information about paragraphs from a shape at index 3 on a slide at index 1 in example.pptx. The storage is 'Main'. The folder is 'Data'.

{{< tabs tabTotal="2" tabID="1" tabName1="Request" tabName2="Response" >}}

{{< tab tabNum="1" >}}

```
curl -v -X GET "https://api.aspose.cloud/v3.0/slides/example.pptx/slides/1/shapes/3/paragraphs?folder=Data&storage=Main" -H "Accept: application/json" -H %token% --ssl-no-revoke
```

{{< /tab >}}

{{< tab tabNum="2" >}}

```
{
  "paragraphLinks": [
    {
      "href": "https://api.aspose.cloud/v3.0/slides/example.pptx/slides/1/shapes/3/paragraphs/1?folder=Data",
      "relation": "self"
    },
    {
      "href": "https://api.aspose.cloud/v3.0/slides/example.pptx/slides/1/shapes/3/paragraphs/2?folder=Data",
      "relation": "self"
    }
  ],
  "selfUri": {
    "href": "https://api.aspose.cloud/v3.0/slides/example.pptx/slides/1/shapes/3/paragraphs?folder=Data",
    "relation": "self"
  }
}
```

{{< /tab >}}

{{< /tabs >}}

## **SDK Source**
The Aspose for Cloud SDKs can be downloaded from the following page: [Available SDKs](https://docs.aspose.cloud/slides/available-sdks/).

## **SDK Examples**
Read the number of paragraphs in a shape at index 3 on a slide at index 1 in example.pptx. The storage is 'Main'. The folder is 'Data'.

{{< tabs tabTotal="11" tabID="5" tabName1="C#" tabName2="Java" tabName3="PHP" tabName4="Ruby" tabName5="Python" tabName6="Node.js" tabName7="Android" tabName8="C++" tabName9="Perl" tabName10="Swift" tabName11="Go" >}}

{{< tab tabNum="1" >}}

```csharp
// For complete examples and data files, please go to https://github.com/aspose-Slides-cloud/aspose-Slides-cloud-dotnet

using System;
using System.IO;
using Aspose.Slides.Cloud.Sdk;

namespace SlidesCloudApp
{
    class Test
    {
        static void Main()
        {
            var slidesApi = new SlidesApi("my_client_id", "my_client_key");

            var fileName = "example.pptx";
            var folderName = "Data";
            var storageName = "Main";
            var filePath = Path.Combine(folderName, fileName);
            var slideIndex = 1;
            var shapeIndex = 3;
            string password = null;

            try
            {
                using (var fileStream = File.OpenRead(fileName))
                {
                    slidesApi.UploadFile(filePath, fileStream, storageName);
                }

                var paragraphs = slidesApi.GetParagraphs(fileName, slideIndex, shapeIndex, password, folderName, storageName);
                var paragraphCount = paragraphs.ParagraphLinks.Count;
                Console.WriteLine(paragraphCount);
            }
            catch (ApiException e)
            {
                Console.WriteLine(e);
            }
        }
    }
}
```

{{< /tab >}}

{{< tab tabNum="2" >}}

```java
// For complete examples and data files, please go to https://github.com/aspose-Slides-cloud/aspose-Slides-cloud-java

import com.aspose.slides.api.SlidesApi;
import java.io.File;
import java.nio.file.Files;
import java.nio.file.Paths;

public class Main {
    public static void main(String[] args) {
        var slidesApi = new SlidesApi("my_client_id", "my_client_key");

        var fileName = "example.pptx";
        var folderName = "Data";
        var storageName = "Main";
        var filePath = Paths.get(folderName, fileName).toString().replace('\\', '/');
        var slideIndex = 1;
        var shapeIndex = 3;
        String password = null;

        try {
            var fileData = Files.readAllBytes(new File(fileName).toPath());
            slidesApi.uploadFile(filePath, fileData, storageName);

            var paragraphs = slidesApi.getParagraphs(fileName, slideIndex, shapeIndex, password, folderName, storageName);
            var paragraphCount = paragraphs.getParagraphLinks().size();
            System.out.println(paragraphCount);
        } catch (Exception e) {
            e.printStackTrace();
        }
    }
}
```

{{< /tab >}}

{{< tab tabNum="3" >}}

```php
// For complete examples and data files, please go to https://github.com/aspose-Slides-cloud/aspose-Slides-cloud-php

use Aspose\Slides\Cloud\Sdk\Api\Configuration;
use Aspose\Slides\Cloud\Sdk\Api\SlidesApi;

$configuration = new Configuration();
$configuration->setAppSid("my_client_id");
$configuration->setAppKey("my_client_key");

$slidesApi = new SlidesApi(null, $configuration);

$fileName = "example.pptx";
$folderName = "Data";
$storageName = "Main";
$filePath = join("/", array($folderName, $fileName));
$slideIndex = 1;
$shapeIndex = 3;
$password = null;

try {
    $fileStream = fopen($fileName, 'r');
    $slidesApi->uploadFile($filePath, $fileStream, $storageName);

    $paragraphs = $slidesApi->getParagraphs($fileName, $slideIndex, $shapeIndex, $password, $folderName, $storageName);
    $paragraphCount = count($paragraphs->getParagraphLinks());
    echo $paragraphCount;
}
catch (ApiException $e) {
    echo $e;
}
```

{{< /tab >}}

{{< tab tabNum="4" >}}

```ruby

```

{{< /tab >}}

{{< tab tabNum="5" >}}

```python
# For complete examples and data files, please go to https://github.com/aspose-Slides-cloud/aspose-Slides-cloud-python

import asposeslidescloud
import os

from asposeslidescloud.configuration import Configuration
from asposeslidescloud.apis.slides_api import SlidesApi
from asposeslidescloud.rest import ApiException

configuration = Configuration()
configuration.app_sid = "my_client_id"
configuration.app_key = "my_client_key"

slidesApi = SlidesApi(configuration)

fileName = "example.pptx"
folderName = "Data"
storageName = "Main"
filePath = os.path.join(folderName, fileName)
slideIndex = 1
shapeIndex = 3
password = None

try:
    with open(fileName, "rb") as reader:
        document = reader.read()

    slidesApi.upload_file(filePath, document)

    paragraphs = slidesApi.get_paragraphs(fileName, slideIndex, shapeIndex, password, folderName, storageName)
    paragraphCount = len(paragraphs.paragraph_links)
    print(paragraphCount)
except ApiException as e:
	print(e)
```

{{< /tab >}}

{{< tab tabNum="6" >}}

```js
// https://github.com/aspose-Slides-cloud/aspose-Slides-cloud-nodejs

const api = require("asposeslidescloud")
const fs = require("fs")
const path = require("path")

const slidesApi = new api.SlidesApi("my_client_id", "my_client_key")

const fileName = "example.pptx"
const folderName = "Data"
const storageName = "Main"
const filePath = path.join(folderName, fileName)
const slideIndex = 1
const shapeIndex = 3
const password = null

const readStream = fs.createReadStream(fileName)

slidesApi.uploadFile(filePath, readStream, storageName).then(() => {
    slidesApi.getParagraphs(fileName, slideIndex, shapeIndex, password, folderName, storageName).then((paragraphs) => {
        const paragraphCount = paragraphs.body.paragraphLinks.length
        console.log(paragraphCount)
    })
    .catch(function (error) {
        console.error(error)
    })
})
.catch(function (error) {
    console.error(error)
})
```

{{< /tab >}}

{{< tab tabNum="7" >}}

```java
// For complete examples and data files, please go to https://github.com/aspose-Slides-cloud/aspose-Slides-cloud-android

import com.aspose.slides.api.SlidesApi;
import java.io.File;
import java.nio.file.Files;
import java.nio.file.Paths;

public class Main {
    public static void main(String[] args) {
        var slidesApi = new SlidesApi("my_client_id", "my_client_key");

        var fileName = "example.pptx";
        var folderName = "Data";
        var storageName = "Main";
        var filePath = Paths.get(folderName, fileName).toString().replace('\\', '/');
        var slideIndex = 1;
        var shapeIndex = 3;
        String password = null;

        try {
            var fileData = Files.readAllBytes(new File(fileName).toPath());
            slidesApi.uploadFile(filePath, fileData, storageName);

            var paragraphs = slidesApi.getParagraphs(fileName, slideIndex, shapeIndex, password, folderName, storageName);
            var paragraphCount = paragraphs.getParagraphLinks().size();
            System.out.println(paragraphCount);
        } catch (Exception e) {
            e.printStackTrace();
        }
    }
}
```

{{< /tab >}}

{{< tab tabNum="8" >}}

```cpp
// For complete examples and data files, please go to https://github.com/aspose-Slides-cloud/aspose-Slides-cloud-cpp

#include <asposeslidescloud/api/SlidesApi.h>

using namespace utility::conversions;
using namespace asposeslidescloud::api;

int main()
{
    auto configuration = std::make_shared<ApiConfiguration>();
    configuration->setAppSid(to_string_t("my_client_id"));
    configuration->setAppKey(to_string_t("my_client_key"));
    
    auto slidesApi = std::make_shared<SlidesApi>(configuration);

	auto fileName = to_string_t("example.pptx");
	auto folderName = to_string_t("Data");
	auto storageName = to_string_t("Main");
	auto filePath = folderName + to_string_t("/") + fileName;
	auto slideIndex = 1;
	auto shapeIndex = 3;
	auto password = utility::string_t();
	
	try
	{
		auto fileStream = std::make_shared<std::ifstream>(fileName, std::ios::binary);
		
		auto uploadContent = std::make_shared<HttpContent>();
		uploadContent->setData(fileStream);
		
		slidesApi->uploadFile(filePath, uploadContent, storageName).wait();
		
		auto paragraphs = slidesApi->getParagraphs(
			fileName, slideIndex, shapeIndex, password, folderName, storageName).get();

		auto paragraphCount = paragraphs->getParagraphLinks().size();
		std::cout << paragraphCount;
	}
	catch (const std::exception& e)
	{
		std::cout << e.what();
	}
	
	return 0;
}
```

{{< /tab >}}

{{< tab tabNum="9" >}}

```perl

```

{{< /tab >}}

{{< tab tabNum="10" >}}

```swift

```

{{< /tab >}}

{{< tab tabNum="11" >}}

```go

```

{{< /tab >}}

{{< /tabs >}}
