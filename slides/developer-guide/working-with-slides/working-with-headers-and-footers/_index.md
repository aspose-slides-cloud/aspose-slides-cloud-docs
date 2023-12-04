---
title: "Working with Headers and Footers"
type: docs
url: /working-with-headers-and-footers/
weight: 100
---

## **Introduction**

When talking about headers and footers within a presentation context, we are referring to the minor elements located at the upper and lower regions of your slides. These elements typically encompass a slide number, text footer, and date. The specific placement of headers and footers may vary based on the chosen theme and slide layout. This article shows methods to manage headers and footers in PowerPoint presentations.

## **API Information**

|**API**|**Type**|**Description**|**Resource**|
| :- | :- | :- | :- |
|/slides/{name}/slides/{slideIndex}/headerFooter|GET|Reads the header and footer information from the slide.|[GetSlideHeaderFooter](https://reference.aspose.cloud/slides/#/Slides/GetSlideHeaderFooter)|
|/slides/{name}/slides/{slideIndex}/headerFooter|PUT|Sets a header and footer to the slide.|[SetSlideHeaderFooter](https://reference.aspose.cloud/slides/#/Slides/SetSlideHeaderFooter)|
|/slides/{name}/headerFooter|PUT|Sets a header and footer to presentation slides.|[SetPresentationHeaderFooter](https://reference.aspose.cloud/slides/#/Document/SetPresentationHeaderFooter)|

**Request Parameters**

{{< expand-list title="GetSlideHeaderFooter" >}}
|**Name**|**Type**|**Location**|**Required**|**Description**|
| :- | :- | :- | :- | :- |
|name|string|path|true|The name of a presentation file.|
|slideIndex|integer|path|true|The 1-based index of the slide.|
|password|string|header|false|The password to open the presentation.|
|folder|string|query|false|The path to the folder containing the presentation.|
|storage|string|query|false|The name of the storage contaning the `folder`.|
{{< /expand-list >}}

{{< expand-list title="SetSlideHeaderFooter" >}}
|**Name**|**Type**|**Location**|**Required**|**Description**|
| :- | :- | :- | :- | :- |
|name|string|path|true|The name of a presentation file.|
|slideIndex|integer|path|true|The 1-based index of the slide.|
|dto|object|body|true|The data transfer object with parameters for the header and footer.|
|password|string|header|false|The password to open the presentation.|
|folder|string|query|false|The path to the folder containing the presentation.|
|storage|string|query|false|The name of the storage contaning the `folder`.|
{{< /expand-list >}}

{{< expand-list title="SetPresentationHeaderFooter" >}}
|**Name**|**Type**|**Location**|**Required**|**Description**|
| :- | :- | :- | :- | :- |
|name|string|path|true|The name of a presentation file.|
|dto|object|body|true|The data transfer object with parameters for the header and footer.|
|password|string|header|false|The password to open the presentation.|
|folder|string|query|false|The path to the folder containing the presentation.|
|storage|string|query|false|The name of the storage contaning the `folder`.|
{{< /expand-list >}}

## **Examples**

A **MyPresentation.pptx** document contains three slides. Enable the date/time with the value **"1/2/2023"**, footer with the value **"A general footer."**, and slide numbers for **all** presentation slides but hide the date/time and the slide number for the **first** slide, set the footer text for the **first** slide to **"The first footer."**.

**cURL Solution**

{{< tabs tabTotal="2" tabID="1" tabName1="Request" tabName2="Response" >}}

{{< tab tabNum="1" >}}

**Get an Access Token**

```sh
curl -X POST "https://api.aspose.cloud/connect/token" \
     -d "grant_type=client_credentials&client_id=MyClientId&client_secret=MyClientSecret" \
     -H "Content-Type: application/x-www-form-urlencoded"
```

**Set the Settings for All Slides**

```sh
curl -X PUT "https://api.aspose.cloud/v3.0/slides/MyPresentation.pptx/headerFooter" \
     -H "authorization: Bearer MyAccessToken" \
     -H "accept: application/json" \
     -H "Content-Type: application/json" \
     -d @GeneralFooter.json
```

GeneralFooter.json content:

```json
{
    "IsDateTimeVisible": true,
    "IsFooterVisible": true,
    "IsSlideNumberVisible": true,
    "DateTimeText": "1/2/2023",
    "FooterText": "A general footer."
}
```

**Set the Settings for the First Slide**

```sh
curl -X PUT "https://api.aspose.cloud/v3.0/slides/MyPresentation.pptx/slides/1/headerFooter" \
     -H "authorization: Bearer MyAccessToken" \
     -H "accept: application/json" \
     -H "Content-Type: application/json" \
     -d @FirstFooter.json
```

FirstFooter.json content:

```json
{
    "IsDateTimeVisible": false,
    "IsSlideNumberVisible": false,
    "FooterText": "The first footer."
}
```

**Get Settings from the First Slide**

```sh
curl -X GET "https://api.aspose.cloud/v3.0/slides/MyPresentation.pptx/slides/1/headerFooter" \
     -H "authorization: Bearer MyAccessToken" \
     -H "accept: application/json"
```

{{< /tab >}}

{{< tab tabNum="2" >}}

**Set the Settings for All Slides**

```json
{
    "documentProperties": {
        "href": "https://api.aspose.cloud/v3.0/slides/MyPresentation.pptx/documentProperties",
        "relation": "self"
    },
    "viewProperties": {
        "href": "https://api.aspose.cloud/v3.0/slides/MyPresentation.pptx/viewProperties",
        "relation": "self"
    },
    "slides": {
        "href": "https://api.aspose.cloud/v3.0/slides/MyPresentation.pptx/slides",
        "relation": "self"
    },
    "images": {
        "href": "https://api.aspose.cloud/v3.0/slides/MyPresentation.pptx/images",
        "relation": "self"
    },
    "layoutSlides": {
        "href": "https://api.aspose.cloud/v3.0/slides/MyPresentation.pptx/layoutSlides",
        "relation": "self"
    },
    "masterSlides": {
        "href": "https://api.aspose.cloud/v3.0/slides/MyPresentation.pptx/masterSlides",
        "relation": "self"
    },
    "selfUri": {
        "href": "https://api.aspose.cloud/v3.0/slides/MyPresentation.pptx",
        "relation": "self"
    },
    "alternateLinks": [
        {
            "href": "https://api.aspose.cloud/v3.0/slides/MyPresentation.pptx/odp",
            "relation": "alternate",
            "linkType": "application/vnd.oasis.opendocument.presentation",
            "title": "Download as Odp"
        },
        {
            "href": "https://api.aspose.cloud/v3.0/slides/MyPresentation.pptx/fodp",
            "relation": "alternate",
            "linkType": "application/vnd.oasis.opendocument.presentation",
            "title": "Download as Fodp"
        },
        {
            "href": "https://api.aspose.cloud/v3.0/slides/MyPresentation.pptx/ppt",
            "relation": "alternate",
            "linkType": "application/vnd.ms-powerpoint",
            "title": "Download as Ppt"
        },
        {
            "href": "https://api.aspose.cloud/v3.0/slides/MyPresentation.pptx/pdf",
            "relation": "alternate",
            "linkType": "application/pdf",
            "title": "Download as Pdf"
        },
        {
            "href": "https://api.aspose.cloud/v3.0/slides/MyPresentation.pptx/tiff",
            "relation": "alternate",
            "linkType": "image/tiff",
            "title": "Download as Tiff"
        },
        {
            "href": "https://api.aspose.cloud/v3.0/slides/MyPresentation.pptx/xps",
            "relation": "alternate",
            "linkType": "application/vnd.ms-xpsdocument",
            "title": "Download as Xps"
        },
        {
            "href": "https://api.aspose.cloud/v3.0/slides/MyPresentation.pptx/pps",
            "relation": "alternate",
            "linkType": "application/vnd.ms-powerpoint",
            "title": "Download as Pps"
        },
        {
            "href": "https://api.aspose.cloud/v3.0/slides/MyPresentation.pptx/ppsx",
            "relation": "alternate",
            "linkType": "application/vnd.openxmlformats-officedocument.presentationml.slideshow",
            "title": "Download as Ppsx"
        },
        {
            "href": "https://api.aspose.cloud/v3.0/slides/MyPresentation.pptx/pptm",
            "relation": "alternate",
            "linkType": "application/vnd.ms-powerpoint.presentation.macroEnabled.12",
            "title": "Download as Pptm"
        },
        {
            "href": "https://api.aspose.cloud/v3.0/slides/MyPresentation.pptx/ppsm",
            "relation": "alternate",
            "linkType": "application/vnd.ms-powerpoint.slideshow.macroEnabled.12",
            "title": "Download as Ppsm"
        },
        {
            "href": "https://api.aspose.cloud/v3.0/slides/MyPresentation.pptx/pot",
            "relation": "alternate",
            "linkType": "application/vnd.ms-powerpoint",
            "title": "Download as Pot"
        },
        {
            "href": "https://api.aspose.cloud/v3.0/slides/MyPresentation.pptx/potx",
            "relation": "alternate",
            "linkType": "application/vnd.openxmlformats-officedocument.presentationml.template",
            "title": "Download as Potx"
        },
        {
            "href": "https://api.aspose.cloud/v3.0/slides/MyPresentation.pptx/potm",
            "relation": "alternate",
            "linkType": "application/vnd.ms-powerpoint.template.macroEnabled.12",
            "title": "Download as Potm"
        },
        {
            "href": "https://api.aspose.cloud/v3.0/slides/MyPresentation.pptx/otp",
            "relation": "alternate",
            "linkType": "application/vnd.oasis.opendocument.presentation-template",
            "title": "Download as Otp"
        },
        {
            "href": "https://api.aspose.cloud/v3.0/slides/MyPresentation.pptx/html",
            "relation": "alternate",
            "linkType": "text/html",
            "title": "Download as Html"
        }
    ]
}
```

**Set the Settings for the First Slide**

```json
{
    "isDateTimeVisible": false,
    "isFooterVisible": true,
    "isSlideNumberVisible": false,
    "dateTimeText": "1/2/2023",
    "footerText": "The first footer.",    
    "selfUri": {
        "href": "https://api.aspose.cloud/v3.0/slides/MyPresentation.pptx/slides/1/headerFooter",
        "relation": "self",
        "slideIndex": 1
    }
}
```

**Get Settings from the First Slide**

```json
{
    "isDateTimeVisible": false,
    "isFooterVisible": true,
    "isSlideNumberVisible": false,
    "dateTimeText": "1/2/2023",
    "footerText": "The first footer.",
    "selfUri": {
        "href": "https://api.aspose.cloud/v3.0/slides/MyPresentation.pptx/slides/1/headerFooter",
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

// The settings for all slides.
var generalFooter = new HeaderFooter
{
    IsDateTimeVisible = true,
    IsFooterVisible = true,
    IsSlideNumberVisible = true,
    DateTimeText = "1/2/2023",
    FooterText = "A general footer.",
};

// Set the settings for all slides.
slidesApi.SetPresentationHeaderFooter(fileName, generalFooter);

// The special settings for the first slide.
var firstFooter = new HeaderFooter
{
    IsDateTimeVisible = false,
    IsSlideNumberVisible = false,
    FooterText = "The first footer."
};

// Set the settings for the first slide.
slidesApi.SetSlideHeaderFooter(fileName, 1, firstFooter);

// Get settings from the first slide.
firstFooter = slidesApi.GetSlideHeaderFooter(fileName, 1);

Console.WriteLine("Date and time visibility: " + firstFooter.IsDateTimeVisible); // False
Console.WriteLine("Footer visibility: " + firstFooter.IsFooterVisible); // True
Console.WriteLine("Slide number visibility: " + firstFooter.IsSlideNumberVisible); // False
Console.WriteLine("Date and time: " + firstFooter.DateTimeText); // 1/2/2023
Console.WriteLine("Footer text: " + firstFooter.FooterText); // "The first footer."
```

{{< /tab >}}

{{< tab tabNum="2" >}}

```java
SlidesApi slidesApi = new SlidesApi("MyClientId", "MyClientSecret");

String fileName = "MyPresentation.pptx";

// The settings for all slides.
HeaderFooter generalFooter = new HeaderFooter();
generalFooter.setIsDateTimeVisible(true);
generalFooter.setIsFooterVisible(true);
generalFooter.setIsSlideNumberVisible(true);
generalFooter.setDateTimeText("1/2/2023");
generalFooter.setFooterText("A general footer.");

// Set the settings for all slides.
slidesApi.setPresentationHeaderFooter(fileName, generalFooter, null, null, null);

// The special settings for the first slide.
HeaderFooter firstFooter = new HeaderFooter();
firstFooter.setIsDateTimeVisible(false);
firstFooter.setIsSlideNumberVisible(false);
firstFooter.setFooterText("The first footer.");

// Set the settings for the first slide.
slidesApi.setSlideHeaderFooter(fileName, 1, firstFooter, null, null, null);

// Get settings from the first slide.
firstFooter = slidesApi.getSlideHeaderFooter(fileName, 1, null, null, null);

System.out.println("Date and time visibility: " + firstFooter.isIsDateTimeVisible()); // False
System.out.println("Footer visibility: " + firstFooter.isIsFooterVisible()); // True
System.out.println("Slide number visibility: " + firstFooter.isIsSlideNumberVisible()); // False
System.out.println("Date and time: " + firstFooter.getDateTimeText()); // 1/2/2023
System.out.println("Footer text: " + firstFooter.getFooterText()); // "The first footer."
```

{{< /tab >}}

{{< tab tabNum="3" >}}

```php
use Aspose\Slides\Cloud\Sdk\Api\Configuration;
use Aspose\Slides\Cloud\Sdk\Api\SlidesApi;
use Aspose\Slides\Cloud\Sdk\Model\HeaderFooter;

$configuration = new Configuration();
$configuration->setAppSid("MyClientId");
$configuration->setAppKey("MyClientSecret");

$slidesApi = new SlidesApi(null, $configuration);

$fileName = "MyPresentation.pptx";

// The settings for all slides.
$generalFooter = new HeaderFooter();
$generalFooter->setIsDateTimeVisible(true);
$generalFooter->setIsFooterVisible(true);
$generalFooter->setIsSlideNumberVisible(true);
$generalFooter->setDateTimeText("1/2/2023");
$generalFooter->setFooterText("A general footer.");

// Set the settings for all slides.
$slidesApi->setPresentationHeaderFooter($fileName, $generalFooter);

// The special settings for the first slide.
$firstFooter = new HeaderFooter();
$firstFooter->setIsDateTimeVisible(false);
$firstFooter->setIsSlideNumberVisible(false);
$firstFooter->setFooterText("The first footer.");

// Set the settings for the first slide.
$slidesApi->setSlideHeaderFooter($fileName, 1, $firstFooter);

// Get settings from the first slide.
$firstFooter = $slidesApi->getSlideHeaderFooter($fileName, 1);

echo "Date and time visibility: ", $firstFooter->getIsDateTimeVisible(), "\r\n"; // False
echo "Footer visibility: ", $firstFooter->getIsFooterVisible(), "\r\n"; // True
echo "Slide number visibility: ", $firstFooter->getIsSlideNumberVisible(), "\r\n"; // False
echo "Date and time: ", $firstFooter->getDateTimeText(), "\r\n"; // 1/2/2023
echo "Footer text: ", $firstFooter->getFooterText(), "\r\n"; // "The first footer."
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

# The settings for all slides.
general_footer = HeaderFooter.new
general_footer.is_date_time_visible = true
general_footer.is_footer_visible = true
general_footer.is_slide_number_visible = true
general_footer.date_time_text = "1/2/2023"
general_footer.footer_text = "A general footer."

# Set the settings for all slides.
slides_api.set_presentation_header_footer(file_name, general_footer)

# The special settings for the first slide.
first_footer = HeaderFooter.new
first_footer.is_date_time_visible = false
first_footer.is_slide_number_visible = false
first_footer.footer_text = "The first footer."

# Set the settings for the first slide.
slides_api.set_slide_header_footer(file_name, 1, first_footer)

# Get settings from the first slide.
first_footer = slides_api.get_slide_header_footer(file_name, 1)

print "Date and time visibility: ", first_footer.is_date_time_visible, "\n" # False
print "Footer visibility: ", first_footer.is_footer_visible, "\n" # True
print "Slide number visibility: ", first_footer.is_slide_number_visible, "\n" # False
print "Date and time: ", first_footer.date_time_text, "\n" # 1/2/2023
print "Footer text: ", first_footer.footer_text, "\n" # "The first footer."
```

{{< /tab >}}

{{< tab tabNum="5" >}}

```python
import asposeslidescloud

from asposeslidescloud.apis.slides_api import SlidesApi
from asposeslidescloud.models import HeaderFooter

slides_api = SlidesApi(None, "MyClientId", "MyClientSecret")

file_name = "MyPresentation.pptx"

# The settings for all slides.
general_footer = HeaderFooter()
general_footer.is_date_time_visible = True
general_footer.is_footer_visible = True
general_footer.is_slide_number_visible = True
general_footer.date_time_text = "1/2/2023"
general_footer.footer_text = "A general footer."

# Set the settings for all slides.
slides_api.set_presentation_header_footer(file_name, general_footer)

# The special settings for the first slide.
first_footer = HeaderFooter()
first_footer.is_date_time_visible = False
first_footer.is_slide_number_visible = False
first_footer.footer_text = "The first footer."

# Set the settings for the first slide.
slides_api.set_slide_header_footer(file_name, 1, first_footer)

# Get settings from the first slide.
first_footer = slides_api.get_slide_header_footer(file_name, 1)

print("Date and time visibility:", first_footer.is_date_time_visible)  # False
print("Footer visibility:", first_footer.is_footer_visible)  # True
print("Slide number visibility:", first_footer.is_slide_number_visible)  # False
print("Date and time:", first_footer.date_time_text)  # 1/2/2023
print("Footer text:", first_footer.footer_text)  # "The first footer."
```

{{< /tab >}}

{{< tab tabNum="6" >}}

```js
const cloud = require("asposeslidescloud");

const slidesApi = new cloud.SlidesApi("MyClientId", "MyClientSecret");

const fileName = "MyPresentation.pptx";

// The settings for all slides.
const generalFooter = new cloud.HeaderFooter();
generalFooter.isDateTimeVisible = true;
generalFooter.isFooterVisible = true;
generalFooter.isSlideNumberVisible = true;
generalFooter.dateTimeText = "1/2/2023";
generalFooter.footerText = "A general footer.";

// The special settings for the first slide.
const firstFooter = new cloud.HeaderFooter();
firstFooter.isDateTimeVisible = false;
firstFooter.isFooterVisible = true;
firstFooter.isSlideNumberVisible = false;
firstFooter.footerText = "The first footer.";

// Set the settings for all slides.
slidesApi.setPresentationHeaderFooter(fileName, generalFooter).then(() => {
    // Set the settings for the first slide.
    slidesApi.setSlideHeaderFooter(fileName, 1, firstFooter).then(() => {
        // Get settings from the first slide.
        slidesApi.getSlideHeaderFooter(fileName, 1).then(response => {
            console.log("Date and time visibility:", response.isDateTimeVisible); // False
            console.log("Footer visibility:", response.isFooterVisible); // True
            console.log("Slide number visibility:", response.isSlideNumberVisible); // False
            console.log("Date and time:", response.dateTimeText); // 1/2/2023
            console.log("Footer text:", response.footerText); // "The first footer."
        });
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

    // The settings for all slides.
    auto generalFooter = std::make_shared<HeaderFooter>();
    generalFooter->setIsDateTimeVisible(true);
    generalFooter->setIsFooterVisible(true);
    generalFooter->setIsSlideNumberVisible(true);
    generalFooter->setDateTimeText(L"1/2/2023");
    generalFooter->setFooterText(L"A general footer.");

    // Set the settings for all slides.
    slidesApi->setPresentationHeaderFooter(fileName, generalFooter).get();

    // The special settings for the first slide.
    auto firstFooter = std::make_shared<HeaderFooter>();
    firstFooter->setIsDateTimeVisible(false);
    firstFooter->setIsSlideNumberVisible(false);
    firstFooter->setFooterText(L"The first footer.");

    // Set the settings for the first slide.
    slidesApi->setSlideHeaderFooter(fileName, 1, firstFooter).get();

    // Get settings from the first slide.
    firstFooter = slidesApi->getSlideHeaderFooter(fileName, 1).get();

    std::wcout << L"Date and time visibility: " << firstFooter->isDateTimeVisible() << L"\r\n"; // False
    std::wcout << L"Footer visibility: " << firstFooter->isFooterVisible() << L"\r\n"; // True
    std::wcout << L"Slide number visibility: " << firstFooter->isSlideNumberVisible() << L"\r\n"; // False
    std::wcout << "Date and time: " << firstFooter->getDateTimeText() << L"\r\n"; // 1/2/2023
    std::wcout << L"Footer text: " + firstFooter->getFooterText() << L"\r\n"; // "The first footer."
}
```

{{< /tab >}}

{{< tab tabNum="8" >}}

```perl
use AsposeSlidesCloud::Configuration;
use AsposeSlidesCloud::SlidesApi;
use AsposeSlidesCloud::Object::HeaderFooter;

my $config = AsposeSlidesCloud::Configuration->new();
$config->{app_sid} = "MyClientId";
$config->{app_key} = "MyClientSecret";

my $slides_api = AsposeSlidesCloud::SlidesApi->new(config => $config);

my $file_name = "MyPresentation.pptx";

# The settings for all slides.
my $general_footer = AsposeSlidesCloud::Object::HeaderFooter->new();
$general_footer->{is_date_time_visible} = true;
$general_footer->{is_footer_visible} = true;
$general_footer->{is_slide_number_visible} = true;
$general_footer->{date_time_text} = "1/2/2023";
$general_footer->{footer_text} = "A general footer.";

# Set the settings for all slides.
my %general_params = (name => $file_name, dto => $general_footer);
$slides_api->set_presentation_header_footer(%general_params);

# The special settings for the first slide.
$first_footer = AsposeSlidesCloud::Object::HeaderFooter->new();
$first_footer->{is_date_time_visible} = false;
$first_footer->{is_slide_number_visible} = false;
$first_footer->{footer_text} = "The first footer.";

# Set the settings for the first slide.
my %first_params = (name => $file_name, slide_index => 1, dto => $first_footer);
$slides_api->set_slide_header_footer(%first_params);

# Get settings from the first slide.
%first_params = (name => $file_name, slide_index => 1);
$first_footer = $slides_api->get_slide_header_footer(%first_params);

print("Date and time visibility: " . $first_footer->{is_date_time_visible} . "\n"); # False
print("Footer visibility: " . $first_footer->{is_footer_visible} . "\n"); # True
print("Slide number visibility: " . $first_footer->{is_slide_number_visible} . "\n"); # False
print("Date and time: " . $first_footer->{date_time_text} . "\n"); # 1/2/2023
print("Footer text: " . $first_footer->{footer_text} . "\n"); # "The first footer."
```

{{< /tab >}}

{{< tab tabNum="9" >}}

{{< /tab >}}

{{< tab tabNum="10" >}}

{{< /tab >}}

{{< /tabs >}}

## **SDKs**

Check [Available SDKs](/slides/available-sdks/) to learn how to add an SDK to your project.
