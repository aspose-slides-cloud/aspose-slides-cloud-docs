---
title: "Read Paragraph Properties"
type: docs
url: /read-paragraph-properties/
weight: 40
---

## **Introduction**
This article shows you how you can read options of a paragraph by index from a PowerPoint presentation using Aspose.Slides for Cloud API. Paragraph options are commonly used to change the appearance of text. These options include alignments, indents, spacing, etc. Some options allow you to create bulleted and numbered lists from paragraphs. You can use our REST API with any language: .NET, Java, PHP, Ruby, Python, С++, and much more.

## **API Information**

|**API**|**Type**|**Description**|**Resource**|
| :- | :- | :- | :- |
|/slides/{name}/slides/{slideIndex}/shapes/{shapeIndex}/paragraphs/{paragraphIndex}|GET|Reads properties of a paragraph in a shape.|[GetParagraph](https://apireference.aspose.cloud/slides/#/Shapes/GetParagraph)|

### **Request Parameters**

|**Name**|**Type**|**Location**|**Required**|**Description**|
| :- | :- | :- | :- | :- |
|name|string|path|true|The presentation file name.|
|slideIndex|integer|path|true|The 1-based index of the presentation slide.|
|shapeIndex|integer|path|true|The 1-based index of the shape.|
|paragraphIndex|integer|path|true|The 1-based index of the paragraph.|
|password|string|header|false|The password to open the presentation.|
|folder|string|query|false|The folder where the presentation file is located.|
|storage|string|query|false|The storage where the presentation file is located.|
|subShape|string|query|false|Sub-shape path (e.g. "3", "3/shapes/2)

*In case of Amazon S3 storage folder path starts with Amazon S3 bucket name.*

## **cURL Example**
Read properties of a paragraph at index 3 from a shape at index 2 on a slide at index 1 in example.pptx. The storage is ‘Main’. The folder is ‘Data’.

{{< tabs tabTotal="2" tabID="1" tabName1="Request" tabName2="Response" >}}

{{< tab tabNum="1" >}}

```
curl -v -X GET "https://api.aspose.cloud/v3.0/slides/example.pptx/slides/1/shapes/2/paragraphs/3?folder=Data&storage=Main" -H "accept: application/json" -H %token% --ssl-no-revoke
```

{{< /tab >}}

{{< tab tabNum="2" >}}

```
{
  "spaceBefore": -18,
  "alignment": "Right",
  "portionList": [
    {
      "text": "Text on the right.",
      "fontColor": "#FF000000",
      "highlightColor": "#0",
      "fontHeight": 28,
      "languageId": "en-US",
      "selfUri": {
        "href": "https://api.aspose.cloud/v3.0/slides/example.pptx/slides/1/shapes/2/paragraphs/3/portions/1?folder=Data",
        "relation": "self"
      }
    }
  ],
  "selfUri": {
    "href": "https://api.aspose.cloud/v3.0/slides/example.pptx/slides/1/shapes/2/paragraphs/3?folder=Data",
    "relation": "self"
  }
}
}
```

{{< /tab >}}

{{< /tabs >}}

## **SDK Source**
The Aspose for Cloud SDKs can be downloaded from the following page: [Available SDKs](https://docs.aspose.cloud/slides/available-sdks/).

## **SDK Examples**
Read properties of a paragraph at index 3 from a shape at index 2 on a slide at index 1 in example.pptx. The storage is ‘Main’. The folder is ‘Data’.

{{< tabs tabTotal="11" tabID="5" tabName1="C#" tabName2="Java" tabName3="PHP" tabName4="Ruby" tabName5="Python" tabName6="Node.js" tabName7="Android" tabName8="C++" tabName9="Perl" tabName10="Swift" tabName11="Go" >}}

{{< tab tabNum="1" >}}

```csharp
// For complete examples and data files, please go to https://github.com/aspose-Slides-cloud/aspose-Slides-cloud-dotnet

using System;
using System.IO;
using Aspose.Slides.Cloud.Sdk;

class Test
{
    static void Main()
    {
        var slidesApi = new SlidesApi("my_client_id", "my_client_key");

        var fileName = "example.pptx";
        var storageName = "Main";
        var folderName = "Data";
        var slideIndex = 1;
        var shapeIndex = 2;
        var paragraphIndex = 3;
        var password = "";

        try
        {
            // The path to the presentation file in the storage.
            var filePath = Path.Combine(folderName, fileName);

            // Upload the presentation to the storage.
            using (var fileStream = File.OpenRead(fileName))
                slidesApi.UploadFile(filePath, fileStream, storageName);

            // Get properties of the specified paragraph.
            var paragraph = slidesApi.GetParagraph(
                fileName, slideIndex, shapeIndex, paragraphIndex, password, folderName, storageName);

            // Display some paragraph properties.
            Console.WriteLine($"Text alignment: {paragraph.Alignment}");
            Console.WriteLine($"Spacing before: {paragraph.SpaceBefore}");

        }
        catch (ApiException e)
        {
            Console.WriteLine(e);
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
        SlidesApi slidesApi = new SlidesApi("my_client_id", "my_client_key");

        String fileName = "example.pptx";
        String storageName = "Main";
        String folderName = "Data";
        int slideIndex = 1;
        int shapeIndex = 2;
        int paragraphIndex = 3;
        String password = "";

        try {
            // The path to the presentation file in the storage.
            String filePath = Paths.get(folderName, fileName).toString().replace('\\', '/');

            // Upload the presentation to the storage.
            byte[] fileData = Files.readAllBytes(new File(fileName).toPath());
            slidesApi.uploadFile(filePath, fileData, storageName);

            // Get properties of the specified paragraph.
            Paragraph paragraph = slidesApi.getParagraph(
                fileName, slideIndex, shapeIndex, paragraphIndex, password, folderName, storageName, null);

            // Display some paragraph properties.
            System.out.println("Text alignment: " + paragraph.getAlignment());
            System.out.println("Spacing before: " + paragraph.getSpaceBefore());
        } catch (Exception e) {
            e.printStackTrace();
        }
    }
}
```

{{< /tab >}}

{{< tab tabNum="3" >}}

```php
// For complete examples and data files, please go to https://github.com/aspose-slides-cloud/aspose-slides-cloud-php

use Aspose\Slides\Cloud\Sdk\Api\Configuration;
use Aspose\Slides\Cloud\Sdk\Api\SlidesApi;
use Aspose\Slides\Cloud\Sdk\Api\ApiException;

$configuration = new Configuration();
$configuration->setAppSid("my_client_id");
$configuration->setAppKey("my_client_key");

$slidesApi = new SlidesApi(null, $configuration);

$fileName = "example.pptx";
$storageName = "Main";
$folderName = "Data";
$slideIndex = 1;
$shapeIndex = 2;
$paragraphIndex = 3;
$password = "";

try {
    // The path to the presentation file in the storage.
    $filePath = join("/", array($folderName, $fileName));

    // Upload the presentation to the storage.
    $fileStream = fopen($fileName, 'r');
    $slidesApi->uploadFile($filePath, $fileStream, $storageName);

    // Get properties of the specified paragraph.
    $paragraph = $slidesApi->getParagraph(
        $fileName, $slideIndex, $shapeIndex, $paragraphIndex, $password, $folderName, $storageName);

    // Display some paragraph properties.
    echo "\r\n", "Text alignment: ", $paragraph->getAlignment();
    echo "\r\n", "Spacing before: ", $paragraph->getSpaceBefore();
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

from asposeslidescloud.apis.slides_api import SlidesApi
from asposeslidescloud.rest import ApiException

slides_api = SlidesApi(None, "my_client_id", "my_client_key")

file_name = "example.pptx"
storage_name = "Main"
folder_name = "Data"
slide_index = 1
shape_index = 2
paragraph_index = 3
password = ""

try:
    # The path to the presentation file in the storage.
    file_path = os.path.join(folder_name, file_name)

    # Upload the presentation to the storage.
    with open(file_name, "rb") as file_stream:
        slides_api.upload_file(file_path, file_stream, storage_name)

    # Get properties of the specified paragraph.
    paragraph = slides_api.get_paragraph(
        file_name, slide_index, shape_index, paragraph_index, password, folder_name, storage_name)

    # Display some paragraph properties.
    print("Text alignment: ", paragraph.alignment)
    print("Spacing before: ", paragraph.space_before)
except ApiException as e:
	print(e)
```

{{< /tab >}}

{{< tab tabNum="6" >}}

```js
// For complete examples and data files, please go to https://github.com/aspose-Slides-cloud/aspose-Slides-cloud-nodejs

const api = require("asposeslidescloud")
const fs = require("fs")
const path = require("path")

const slidesApi = new api.SlidesApi("my_client_id", "my_client_key")

const fileName = "example.pptx"
const storageName = "Main"
const folderName = "Data"
const slideIndex = 1
const shapeIndex = 2
const paragraphIndex = 3
const password = ""

// The path to the presentation file in the storage.
const filePath = path.join(folderName, fileName)

// Upload the presentation to the storage.
const fileStream = fs.createReadStream(fileName)
slidesApi.uploadFile(filePath, fileStream, storageName).then(() => {

    // Get properties of the specified paragraph.
    slidesApi.getParagraph(fileName, slideIndex, shapeIndex, paragraphIndex, password, folderName, storageName).then((paragraph) => {

        // Display some paragraph properties.
        console.log("Text alignment: ", paragraph.body.alignment)
        console.log("Spacing before: ", paragraph.body.spaceBefore)
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
// For complete examples and data files, please go to https://github.com/aspose-Slides-cloud/aspose-Slides-cloud-java

import com.aspose.slides.api.SlidesApi;
import java.io.File;
import java.nio.file.Files;
import java.nio.file.Paths;

public class Main {
    public static void main(String[] args) {
        SlidesApi slidesApi = new SlidesApi("my_client_id", "my_client_key");

        String fileName = "example.pptx";
        String storageName = "Main";
        String folderName = "Data";
        int slideIndex = 1;
        int shapeIndex = 2;
        int paragraphIndex = 3;
        String password = "";

        try {
            // The path to the presentation file in the storage.
            String filePath = Paths.get(folderName, fileName).toString().replace('\\', '/');

            // Upload the presentation to the storage.
            byte[] fileData = Files.readAllBytes(new File(fileName).toPath());
            slidesApi.uploadFile(filePath, fileData, storageName);

            // Get properties of the specified paragraph.
            Paragraph paragraph = slidesApi.getParagraph(
                fileName, slideIndex, shapeIndex, paragraphIndex, password, folderName, storageName);

            // Display some paragraph properties.
            System.out.println("Text alignment: " + paragraph.getAlignment());
            System.out.println("Spacing before: " + paragraph.getSpaceBefore());
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

#include "asposeslidescloud/api/SlidesApi.h"

using namespace utility::conversions;
using namespace asposeslidescloud::api;

int main()
{
	auto slidesApi = std::make_shared<SlidesApi>(to_string_t("my_client_id"), to_string_t("m_client_key"));

	auto fileName = to_string_t("example.pptx");
	auto storageName = to_string_t("Main");
	auto folderName = to_string_t("Data");
	auto slideIndex = 1;
	auto shapeIndex = 2;
	auto paragraphIndex = 3;
	auto password = to_string_t("");
		
	try
	{
		// The path to the presentation file in the storage.
		auto filePath = folderName + to_string_t("/") + fileName;

		// Upload the presentation to the storage.
		auto fileStream = std::make_shared<std::ifstream>(fileName, std::ios::binary);		
		auto uploadContent = std::make_shared<HttpContent>();
		uploadContent->setData(fileStream);
		slidesApi->uploadFile(filePath, uploadContent, storageName).wait();

		// Get properties of the specified paragraph.
		auto paragraph = slidesApi->getParagraph(
			fileName, slideIndex, shapeIndex, paragraphIndex, password, folderName, storageName).get();

		std::cout << "Text alignment: " << to_utf8string(paragraph->getAlignment()) << std::endl;
		std::cout << "Spacing before: " << paragraph->getSpaceBefore();
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

## **Paragraph properties**
The following table describes the parameters that you can use to get and update the properties of a paragraph.

{{% alert color="primary" %}} 

Some other text formatting options are only available for text portions by `Portion` class.

{{% /alert %}} 

|**Parameter**|**Type**|**Description**|
| :- | :- | :- |
|Alignment|AlignmentEnum|One of the [AlignmentEnum](#alignmentenum) values that determines a horizontal placement of the text.|
|AlternateLinks|List\<ResourceUri\>|The collection of alternate links related to this resource. Inherited from `ResourceBase`.|
|BulletChar|string|The symbol for a bulleted list.|
|BulletHeight|double|The height of a bullet symbol.|
|BulletType|BulletTypeEnum|One of the [BulletTypeEnum](#bullettypeenum) values that determines a bullet type.|
|DefaultTabSize|double|The size of default tab stops.|
|Depth|int|The indent level.|
|EastAsianLineBreak|EastAsianLineBreakEnum|One of the [EastAsianLineBreakEnum](#eastasianlinebreakenum) values that determines line breaks for East Asian text.|
|FontAlignment|FontAlignmentEnum|One of the [FontAlignmentEnum](#fontalignmentenum) values that determines vertical text alignment for Asian typography.|
|HangingPunctuation|HangingPunctuationEnum|One of the [HangingPunctuationEnum](#hangingpunctuationenum) values that determines hanging punctuation for the text.|
|Indent|double|The indent for the first line of the text (hanging indent). The parameter can be set to negative values.|
|LatinLineBreak|LatinLineBreakEnum|One of the [LatinLineBreakEnum](#latinlinebreakenum) values that determines text wrapping in the middle of a word.|
|MarginLeft|double|The indentation before the text.|
|MarginRight|double|The indentation after the text.|
|NumberedBulletStartWith|int|The first number for a numbered list.|
|NumberedBulletStyle|NumberedBulletStyleEnum|One of the [NumberedBulletStyleEnum](#numberedbulletstyleenum) values that determines a bullet style of a numbered list.|
|PortionList|List\<Portion\>|The collection of text portions.|
|RightToLeft|RightToLeftEnum|One of the [RightToLeftEnum](#righttoleftenum) values that determines right-to-left direction for the text.|
|SelfUri|ResourceUri|The main part of an URL used to get the object. Inherited from `ResourceBase`.|
|SpaceAfter|double|The text spacing after the last line of the paragraph. A positive value specifies the percentage of the font size. A negative value specifies the size in points.|
|SpaceBefore|double|The text spacing before the first line of the paragraph. A positive value specifies the percentage of the font size. A negative value specifies the size in points.|
|SpaceWithin|double|The text spacing between base lines of the paragraph. A positive value specifies the percentage of the font size. A negative value specifies the size in points.|

{{% alert color="primary" %}} 

The following enumerations describe parameter values with names for .NET SDK. The member names can differ for other Aspose.Slides SDKs according to their naming convention.

{{% /alert %}} 

### **AlignmentEnum**
Specifies the horizontal placement of a text.

**Members**

|**Name**|**Value**|**Description**|
| :- | :- | :- |
|Center|1|Aligns a paragraph horizontally to the center.|
|Distributed|5|Distributes a paragraph text evenly between the left and right margins, adding spaces between characters and words.|
|Justify|3|Distributes a paragraph text evenly between the left and right margins.|
|JustifyLow|4|Lengthens kashidas in Arabic text slightly.|
|Left|0|Aligns a paragraph horizontally to the left.|
|NotDefined|6|The horizontal alignment is not defined.|
|Right|2|Aligns a paragraph horizontally to the right.|

### **BulletTypeEnum**
Specifies a bullet type for a list item.

**Members**

|**Name**|**Value**|**Description**|
| :- | :- | :- |
|None|0|Specifies the default effective value.|
|NotDefined|4|The bullet type is not defined.|
|Numbered|2|Specifies a number for a bullet.|
|Picture|3|Specifies a picture for a bullet.|
|Symbol|1|Specifies a character for a bullet.|

### **EastAsianLineBreakEnum**
Specifies line breaks for East Asian text.

**Members**

|**Name**|**Value**|**Description**|
| :- | :- | :- |
|False|0|Do not apply line breaks.|
|NotDefined|2|The line breaks are not defined.|
|True|1|Apply line breaks.|

### **FontAlignmentEnum**
Specifies vertical text alignment for Asian typography.

**Members**

|**Name**|**Value**|**Description**|
| :- | :- | :- |
|Automatic|0|Specifies automatic alignment for a font.|
|Baseline|4|Specifies alignment to the baseline of a font.|
|Bottom|3|Specifies alignment to the bottom of a font.|
|Center|2|Specifies alignment to the center of a font.|
|Default|5|Specifies a default alignment.|
|Top|1|Specifies alignment to the top of a font.|

### **HangingPunctuationEnum**
Specifies hanging punctuation for a text.

**Members**

|**Name**|**Value**|**Description**|
| :- | :- | :- |
|False|0|Do not apply hanging punctuation.|
|NotDefined|2|The hanging punctuation is not defined.|
|True|1|Apply hanging punctuation.|

### **LatinLineBreakEnum**
Specifies text wrapping in the middle of a word.

**Members**

|**Name**|**Value**|**Description**|
| :- | :- | :- |
|False|0|Do not apply text wrapping.|
|NotDefined|2|The text wrapping is not defined.|
|True|1|Apply text wrapping.|

### **NumberedBulletStyleEnum**
Specifies a bullet style of a numbered list.

**Members**

|**Name**|**Value**|**Description**|
| :- | :- | :- |
|BulletAlphaLCParenBoth|8|Specifies lowercase alphabetical letters with both parentheses. Sample: (a), (b), (c), ...|
|BulletAlphaLCParenRight|9|Specifies lowercase alphabetical letters with a closing parenthesis. Sample: a), b), c), ...|
|BulletAlphaLCPeriod|0|Specifies lowercase alphabetical letters with a period. Sample: a., b., c., ...|
|BulletAlphaUCParenBoth|10|Specifies uppercase alphabetical letters with both parentheses. Sample: (A), (B), (C), ...|
|BulletAlphaUCParenRight|11|Specifies uppercase alphabetical letters with a closing parenthesis. Sample: A), B), C), ...|
|BulletAlphaUCPeriod|1|Specifies uppercase alphabetical letters with a period. Sample: A., B., C., ...|
|BulletArabicAbjadDash|24|Specifies Arabic abjad alphabetical letters with a dash.|
|BulletArabicAlphaDash|23|Specifies Arabic alphabetical letters with a dash.|
|BulletArabicDBPeriod|29|Specifies double-byte Arabic numbering scheme with a double-byte period.|
|BulletArabicDBPlain|28|Specifies double-byte Arabic numbering scheme (no punctuation).|
|BulletArabicParenBoth|12|Specifies Arabic numbers with both parentheses. Sample: (1), (2), (3), ...|
|BulletArabicParenRight|2|Specifies Arabic numbers with a closing parenthesis. Sample: 1), 2), 3), ...|
|BulletArabicPeriod|3|Specifies Arabic numbers with a period. Sample: 1., 2., 3., ...|
|BulletArabicPlain|13|Specifies Arabic numbers. Sample: 1, 2, 3, ...|
|BulletCircleNumDBPlain|18|Specifies double-byte circled number for values up to 10. From  11 - Arabic numbers.|
|BulletCircleNumWDBlackPlain|20|Specifies numbers on a disk (Wingdings black circled numbers).|
|BulletCircleNumWDWhitePlain|19|Specifies circled numbers (Wingdings white circled numbers). From 11 - Arabic numbers.|
|BulletHebrewAlphaDash|25|Specifies Hebrew alphabetical letters with a dash.|
|BulletHindiAlpha1Period|40|Specifies consonant letters from Hindi alphabet with a period.|
|BulletHindiAlphaPeriod|36|Specifies vowel letters from Hindi alphabet with a period.|
|BulletHindiNumParenRight|39|Specifies Hindi numbers with a closing parenthesis.|
|BulletHindiNumPeriod|37|Specifies Hindi numbers with a period.|
|BulletKanjiKoreanPeriod|27|Specifies Japanese/Korean numbers with a period.|
|BulletKanjiKoreanPlain|26|Specifies Japanese/Korean numbers.|
|BulletKanjiSimpChinDBPeriod|38|Specifies Kanji Simple Chinese characters with a period.|
|BulletRomanLCParenBoth|4|Specifies lowercase Roman numbers with both parentheses. Sample: (i), (ii), (iii), ...|
|BulletRomanLCParenRight|5|Specifies lowercase Roman numbers with a closing parenthesis. Sample: i), ii), iii), ...|
|BulletRomanLCPeriod|6|Specifies lowercase Roman numbers with a period. Sample: i., ii., iii., ...|
|BulletRomanUCParenBoth|14|Specifies uppercase Roman numbers with both parentheses. Sample: (I), (II), (III), ...|
|BulletRomanUCParenRight|15|Specifies uppercase Roman numbers with a closing parenthesis. Sample: I), II), III), ...|
|BulletRomanUCPeriod|7|Specifies uppercase Roman numbers with a period. Sample: I., II., III., ...|
|BulletSimpChinPeriod|17|Specifies simplified Chinese characters with a period.|
|BulletSimpChinPlain|16|Specifies simplified Chinese characters.|
|BulletThaiAlphaParenBoth|32|Specifies Thai alphabetical letters with both parentheses.|
|BulletThaiAlphaParenRight|31|Specifies Thai alphabetical letters with a closing parenthesis.|
|BulletThaiAlphaPeriod|30|Specifies Thai alphabetical letters with a period.|
|BulletThaiNumParenBoth|35|Specifies Thai numbers with both parentheses.|
|BulletThaiNumParenRight|34|Specifies Thai numbers with a closing parenthesis.|
|BulletThaiNumPeriod|33|Specifies Thai numbers with a period.|
|BulletTradChinPeriod|22|Specifies traditional Chinese characters with a period.|
|BulletTradChinPlain|21|Specifies traditional Chinese characters.|
|NotDefined|41|The bullet style is not defined.|

### **RightToLeftEnum**
Specifies right-to-left direction for a text.

**Members**

|**Name**|**Value**|**Description**|
| :- | :- | :- |
|False|0|Do not apply right-to-left direction.|
|NotDefined|2|Right-to-left direction is not defined.|
|True|1|Apply right-to-left direction.|

{{% alert color="primary" %}} 

When you request a paragraph from a PowerPoint presentation, some of its parameters may be `null`. This means that the parameter has a default value or the value is not defined (inherited from a parent object).

{{% /alert %}}
