---
title: "Working with Headers and Footers"
type: docs
url: /working-with-headers-and-footers-on-a-notes-slide/
weight: 50
---

## **Introduction**

When talking about headers and footers within a Notes slide context, we are referring to the minor elements located at the upper and lower regions of your Notes slides. These elements typically encompass a text header, date, text footer, and slide number. This article shows methods to manage headers and footers within Notes slides.

## **API Information**

|**API**|**Type**|**Description**|**Resource**|
| :- | :- | :- | :- |
|/slides/{name}/slides/{slideIndex}/notesSlide/headerFooter|GET|Reads the header and footer information from the Notes slide.|[GetNotesSlideHeaderFooter](https://reference.aspose.cloud/slides/#/NotesSlide/GetNotesSlideHeaderFooter)|
|/slides/{name}/slides/{slideIndex}/notesSlide/headerFooter|PUT|Sets a header and footer to the Notes slide.|[SetNotesSlideHeaderFooter](https://reference.aspose.cloud/slides/#/NotesSlide/SetNotesSlideHeaderFooter)|

**Request Parameters**

{{< expand-list title="GetNotesSlideHeaderFooter" >}}
|**Name**|**Type**|**Location**|**Required**|**Description**|
| :- | :- | :- | :- | :- |
|name|string|path|true|The name of a presentation file.|
|slideIndex|integer|path|true|The 1-based index of the Notes slide.|
|password|string|header|false|The password to open the presentation.|
|folder|string|query|false|The path to the folder containing the presentation.|
|storage|string|query|false|The name of the storage contaning the `folder`.|
{{< /expand-list >}}

{{< expand-list title="SetNotesSlideHeaderFooter" >}}
|**Name**|**Type**|**Location**|**Required**|**Description**|
| :- | :- | :- | :- | :- |
|name|string|path|true|The name of a presentation file.|
|slideIndex|integer|path|true|The 1-based index of the Notes slide.|
|dto|object|body|true|The data transfer object with parameters for the header and footer.|
|password|string|header|false|The password to open the presentation.|
|folder|string|query|false|The path to the folder containing the presentation.|
|storage|string|query|false|The name of the storage contaning the `folder`.|
{{< /expand-list >}}

## **Examples**

In **MyPresentation.pptx** document, enable the header with the value **"This is my header"**, the date/time with the value **"1/1/2023"**, footer with the value **"This is my footer"**, and slide numbers for the **first** Notes slide. Read the header text, date/time text, and footer text.

**cURL Solution**

{{< tabs tabTotal="2" tabID="1" tabName1="Request" tabName2="Response" >}}

{{< tab tabNum="1" >}}

**Get an Access Token**

```sh
curl -X POST "https://api.aspose.cloud/connect/token" \
     -d "grant_type=client_credentials&client_id=MyClientId&client_secret=MyClientSecret" \
     -H "Content-Type: application/x-www-form-urlencoded"
```

**Set the Header and Footer to the Notes Slide**

```sh
curl -X PUT "https://api.aspose.cloud/v3.0/slides/MyPresentation.pptx/slides/1/notesSlide/headerFooter" \
     -H "authorization: Bearer MyAccessToken" \
     -H "accept: application/json" \
     -H "Content-Type: application/json" \
     -d @HeaderFooter.json
```

HeaderFooter.json content:

```json
{
    "IsHeaderVisible": true,
    "IsDateTimeVisible": true,
    "IsFooterVisible": true,
    "IsSlideNumberVisible": true,
    "HeaderText": "This is my header",
    "DateTimeText": "1/1/2023",
    "FooterText": "This is my footer"
}
```

{{< /tab >}}

**Get the Header and Footer from the Notes Slide**

```sh
curl -X GET "https://api.aspose.cloud/v3.0/slides/MyPresentation.pptx/slides/1/notesSlide/headerFooter" \
     -H "authorization: Bearer MyAccessToken" \
     -H "accept: application/json"
```

{{< tab tabNum="2" >}}

**Set the Header and Footer to the Notes Slide**

```json
{
    "isDateTimeVisible": true,
    "isFooterVisible": true,
    "isHeaderVisible": true,
    "isSlideNumberVisible": true,
    "selfUri": {
        "href": "https://api.aspose.cloud/v3.0/slides/MyPresentation.pptx/slides/1/notesSlide/headerFooter",
        "relation": "self",
        "slideIndex": 1
    }
}
```

**Get the Header and Footer from the Notes Slide**

```json
{
    "isDateTimeVisible": true,
    "isFooterVisible": true,
    "isHeaderVisible": true,
    "isSlideNumberVisible": true,
    "selfUri": {
        "href": "https://api.aspose.cloud/v3.0/slides/MyPresentation.pptx/slides/1/notesSlide/headerFooter",
        "relation": "self",
        "slideIndex": 1
    }
}
```

{{< /tab >}}

{{< /tabs >}}

**SDK Solutions**

{{< tabs tabTotal="11" tabID="11" tabName1="C#" tabName2="Java" tabName3="PHP" tabName4="Ruby" tabName5="Python" tabName6="Node.js" tabName7="C++" tabName8="Perl" tabName9="Swift" tabName10="Go" >}}

{{< tab tabNum="1" >}}

```csharp
var slidesApi = new SlidesApi("MyClientId", "MyClientSecret");

var fileName = "MyPresentation.pptx";
var slideIndex = 1;

// The header and footer settings.
var headerFooter = new NotesSlideHeaderFooter
{
    IsHeaderVisible = true,
    IsDateTimeVisible = true,
    IsFooterVisible = true,
    IsSlideNumberVisible = true,
    HeaderText = "This is my header",
    DateTimeText = "1/1/2023",
    FooterText = "This is my footer"
};

// Set the header and footer for the first Notes slide.
slidesApi.SetNotesSlideHeaderFooter(fileName, slideIndex, headerFooter);

// Get the header and footer from the first Notes slide.
headerFooter = slidesApi.GetNotesSlideHeaderFooter(fileName, slideIndex);

Console.WriteLine("Header text: " + headerFooter.HeaderText);
Console.WriteLine("Date and time text: " + headerFooter.DateTimeText);
Console.WriteLine("Footer text: " + headerFooter.FooterText);
```

{{< /tab >}}

{{< tab tabNum="2" >}}

```java
var slidesApi = new SlidesApi("MyClientId", "MyClientSecret");

var fileName = "MyPresentation.pptx";
var slideIndex = 1;

// The header and footer settings.
var headerFooter = new NotesSlideHeaderFooter();
headerFooter.setIsHeaderVisible(true);
headerFooter.setIsDateTimeVisible(true);
headerFooter.setIsFooterVisible(true);
headerFooter.setIsSlideNumberVisible(true);
headerFooter.setHeaderText("This is my header");
headerFooter.setDateTimeText("1/1/2023");
headerFooter.setFooterText("This is my footer");

// Set the header and footer for the first Notes slide.
slidesApi.setNotesSlideHeaderFooter(fileName, slideIndex, headerFooter, null, null, null);

// Get the header and footer from the first Notes slide.
headerFooter = slidesApi.getNotesSlideHeaderFooter(fileName, slideIndex, null, null, null);

System.out.println("Header text: " + headerFooter.getHeaderText());
System.out.println("Date and time text: " + headerFooter.getDateTimeText());
System.out.println("Footer text: " + headerFooter.getFooterText());
```

{{< /tab >}}

{{< tab tabNum="3" >}}

```php
use Aspose\Slides\Cloud\Sdk\Api\Configuration;
use Aspose\Slides\Cloud\Sdk\Api\SlidesApi;
use Aspose\Slides\Cloud\Sdk\Model\NotesSlideHeaderFooter;

$configuration = new Configuration();
$configuration->setAppSid("MyClientId");
$configuration->setAppKey("MyClientSecret");

$slidesApi = new SlidesApi(null, $configuration);

$fileName = "MyPresentation.pptx";
$slideIndex = 1;

// The header and footer settings.
$headerFooter = new NotesSlideHeaderFooter();
$headerFooter->setIsHeaderVisible(true);
$headerFooter->setIsDateTimeVisible(true);
$headerFooter->setIsFooterVisible(true);
$headerFooter->setIsSlideNumberVisible(true);
$headerFooter->setHeaderText("This is my header");
$headerFooter->setDateTimeText("1/1/2023");
$headerFooter->setFooterText("This is my footer");

// Set the header and footer for the first Notes slide.
$slidesApi->setNotesSlideHeaderFooter($fileName, $slideIndex, $headerFooter);

// Get the header and footer from the first Notes slide.
$headerFooter = $slidesApi->getNotesSlideHeaderFooter($fileName, $slideIndex);

echo "Header text: ", $headerFooter->getHeaderText(), "\r\n";
echo "Date and time text: ", $headerFooter->getDateTimeText(), "\r\n";
echo "Footer text: ", $headerFooter->getFooterText(), "\r\n";
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

file_name = "MyPresentation.pptx"
slide_index = 1

# The header and footer settings.
header_footer = NotesSlideHeaderFooter.new
header_footer.is_header_visible = true
header_footer.is_date_time_visible = true
header_footer.is_footer_visible = true
header_footer.is_slide_number_visible = true
header_footer.header_text = "This is my header"
header_footer.date_time_text = "1/1/2023"
header_footer.footer_text = "This is my footer"

# Set the header and footer for the first Notes slide.
slides_api.set_notes_slide_header_footer(file_name, slide_index, header_footer)

# Get the header and footer from the first Notes slide.
header_footer = slides_api.get_notes_slide_header_footer(file_name, slide_index)

print "Header text: ", header_footer.header_text, "\n"
print "Date and time text: ", header_footer.date_time_text, "\n"
print "Footer text: ", header_footer.footer_text, "\n"
```

{{< /tab >}}

{{< tab tabNum="5" >}}

```python
import asposeslidescloud

from asposeslidescloud.apis.slides_api import SlidesApi
from asposeslidescloud.models import NotesSlideHeaderFooter

slides_api = SlidesApi(None, "MyClientId", "MyClientSecret")

file_name = "MyPresentation.pptx"
slide_index = 1

# The header and footer settings.
header_footer = NotesSlideHeaderFooter()
header_footer.is_header_visible = True
header_footer.is_date_time_visible = True
header_footer.is_footer_visible = True
header_footer.is_slide_number_visible = True
header_footer.header_text = "This is my header"
header_footer.date_time_text = "1/1/2023"
header_footer.footer_text = "This is my footer"

# Set the header and footer for the first Notes slide.
slides_api.set_notes_slide_header_footer(file_name, slide_index, header_footer)

# Get the header and footer from the first Notes slide.
header_footer = slides_api.get_notes_slide_header_footer(file_name, slide_index)

print("Header text:", header_footer.header_text)
print("Date and time text:", header_footer.date_time_text)
print("Footer text:", header_footer.footer_text)
```

{{< /tab >}}

{{< tab tabNum="6" >}}

```js
const cloud = require("asposeslidescloud");

const slidesApi = new cloud.SlidesApi("MyClientId", "MyClientSecret");

const fileName = "MyPresentation.pptx";
const slideIndex = 1;

// The header and footer settings.
const headerFooter = new cloud.NotesSlideHeaderFooter();
headerFooter.isHeaderVisible = true;
headerFooter.isDateTimeVisible = true;
headerFooter.isFooterVisible = true;
headerFooter.isSlideNumberVisible = true;
headerFooter.headerText = "This is my header";
headerFooter.dateTimeText = "1/1/2023";
headerFooter.footerText = "This is my footer";

// Set the header and footer for the first Notes slide.
slidesApi.setNotesSlideHeaderFooter(fileName, slideIndex, headerFooter).then(() => {
    // Get the header and footer from the first Notes slide.
    slidesApi.getNotesSlideHeaderFooter(fileName, slideIndex).then((response) => {
        console.log("Header text:" + response.headerText);
        console.log("Date and time text:" + response.dateTimeText);
        console.log("Footer text:" + response.footerText);
    });
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

    auto fileName = L"MyPresentation.pptx";
    auto slideIndex = 1;

    // The header and footer settings.
    auto headerFooter = std::make_shared<NotesSlideHeaderFooter>();
    headerFooter->setIsHeaderVisible(true);
    headerFooter->setIsDateTimeVisible(true);
    headerFooter->setIsFooterVisible(true);
    headerFooter->setIsSlideNumberVisible(true);
    headerFooter->setHeaderText(L"This is my header");
    headerFooter->setDateTimeText(L"1/1/2023");
    headerFooter->setFooterText(L"This is my footer");

    // Set the header and footer for the first Notes slide.
    slidesApi->setNotesSlideHeaderFooter(fileName, slideIndex, headerFooter).get();

    // Get the header and footer from the first Notes slide.
    headerFooter = slidesApi->getNotesSlideHeaderFooter(fileName, slideIndex).get();

    std::wcout << L"Header text: " << headerFooter->getHeaderText() << L"\r\n";
    std::wcout << L"Date and time text: " << headerFooter->getDateTimeText() << L"\r\n";
    std::wcout << L"Footer text: " << headerFooter->getFooterText() << L"\r\n";
}
```

{{< /tab >}}

{{< tab tabNum="8" >}}

```perl
use AsposeSlidesCloud::Configuration;
use AsposeSlidesCloud::SlidesApi;
use AsposeSlidesCloud::Object::NotesSlideHeaderFooter;

my $config = AsposeSlidesCloud::Configuration->new();
$config->{app_sid} = "MyClientId";
$config->{app_key} = "MyClientSecret";

my $slides_api = AsposeSlidesCloud::SlidesApi->new(config => $config);

my $file_name = "MyPresentation.pptx";
my $slide_index = 1;

# The header and footer settings.
my $header_footer = AsposeSlidesCloud::Object::NotesSlideHeaderFooter->new();
$header_footer->{is_header_visible} = true;
$header_footer->{is_date_time_visible} = true;
$header_footer->{is_footer_visible} = true;
$header_footer->{is_slide_number_visible} = true;
$header_footer->{header_text} = "This is my header";
$header_footer->{date_time_text} = "1/1/2023";
$header_footer->{footer_text} = "This is my footer";

# Set the header and footer for the first Notes slide.
my %set_params = (name => $file_name, slide_index => $slide_index, dto => $header_footer);
$slides_api->set_notes_slide_header_footer(%set_params);

# Get the header and footer from the first Notes slide.
my %get_params = (name => $file_name, slide_index => $slide_index);
$header_footer = $slides_api->get_notes_slide_header_footer(%get_params);

print("Header text: " . $header_footer->{header_text} . "\n");
print("Date and time text: " . $header_footer->{date_time_text} . "\n");
print("Footer text: " . $header_footer->{footer_text} . "\n");
```

{{< /tab >}}

{{< tab tabNum="9" >}}

{{< /tab >}}

{{< tab tabNum="10" >}}

{{< /tab >}}

{{< /tabs >}}

## **SDKs**

Check [Available SDKs](/slides/available-sdks/) to learn how to add an SDK to your project.
