---
title: "Add a Notes Slide"
keywords:
- PowerPoint
- presentation
- REST API
- cloud API
- slide notes
- speaker notes
- add notes
type: docs
url: /add-a-notes-slide/
weight: 20
---

## **Introduction**

The following API method allows you to add speaker notes to a PowerPoint presentation. The notes will appear in Notes pane below a slide.

## **CreateNotesSlide**

### **API Information**

|**API**|**Type**|**Description**|**Resource**|
| :- | :- | :- | :- |
|/slides/{name}/slides/{slideIndex}/notesSlide|POST|Adds notes to a presentation slide.|[CreateNotesSlide](https://apireference.aspose.cloud/slides/#/NotesSlide/CreateNotesSlide)|

**Request Parameters**

|**Name**|**Type**|**Location**|**Required**|**Description**|
| :- | :- | :- | :- | :- |
|name|string|path|true|The name of a presentation file.|
|slideIndex|integer|path|true|The 1-based index of the slide.|
|dto|object|body|true|The data object containing notes information.|
|password|string|header|false|The password to open the presentation.|
|folder|string|query|false|The path to the folder containing the presentation.|
|storage|string|query|false|The name of the storage contaning the `folder`.|

*In case of Amazon S3 storage folder path starts with Amazon S3 bucket name.*

### **Examples**

Add notes with the text "Start with our company." to the **second** slide in the document **MyFolder/MyPresentation.pptx** saved to the default storage.

**cURL Solution**

{{< tabs tabTotal="2" tabID="1" tabName1="Request" tabName2="Response" >}}

{{< tab tabNum="1" >}}

**Get an Access Token**

```sh
curl POST "https://api.aspose.cloud/connect/token" \
     -d "grant_type=client_credentials&client_id=MyClientId&client_secret=MyClientSecret" \
     -H "Content-Type: application/x-www-form-urlencoded"
```

**Add Notes to the Slide**

```sh
curl POST "https://api.aspose.cloud/v3.0/slides/MyPresentation.pptx/slides/2/notesSlide?folder=MyFolder" \
     -H "authorization: Bearer MyAccessToken" \
     -H "Content-Type: application/json" \
     -d @SlideNotes.json
```

SlideNotes.json content:

```json
{
    "Text": "Start with our company."
}
```

{{< /tab >}}

{{< tab tabNum="2" >}}

**Response Example**

```json
{
    "text": "Start with our company.",
    "shapes": {
        "href": "https://api.aspose.cloud/v3.0/slides/MyPresentation.pptx/slides/2/notesSlide/shapes?folder=MyFolder",
        "relation": "self",
        "slideIndex": 2
    },
    "selfUri": {
        "href": "https://api.aspose.cloud/v3.0/slides/MyPresentation.pptx/slides/2/notesSlide?folder=MyFolder",
        "relation": "self",
        "slideIndex": 2
    }
}
```

{{< /tab >}}

{{< /tabs >}}

**SDK Solutions**

{{< tabs tabTotal="11" tabID="11" tabName1="C#" tabName2="Java" tabName3="PHP" tabName4="Ruby" tabName5="Python" tabName6="Node.js" tabName7="C++" tabName8="Perl" tabName9="Swift" tabName10="Go" >}}

{{< tab tabNum="1" >}}

```csharp
// For complete examples and data files, please go to https://github.com/aspose-Slides-cloud/aspose-Slides-cloud-dotnet

using Aspose.Slides.Cloud.Sdk;
using Aspose.Slides.Cloud.Sdk.Model;
using System;

class Application
{
    static void Main()
    {
        var slidesApi = new SlidesApi("MyClientId", "MyClientSecret");

        // Prepare notes for the slide.
        var notesSlide = new NotesSlide
        {
            Text = "Start with our company."
        };

        // Create the notes for the second slide.
        var currentNotesSlide = slidesApi.CreateNotesSlide("MyPresentation.pptx", 2, notesSlide, null, "MyFolder");

        // Print the resource reference for the notes slide.
        Console.WriteLine(currentNotesSlide.SelfUri.Href);
    }
}
```

{{< /tab >}}

{{< tab tabNum="2" >}}

```java
// For complete examples and data files, please go to https://github.com/aspose-Slides-cloud/aspose-Slides-cloud-java

import com.aspose.slides.ApiException;
import com.aspose.slides.api.SlidesApi;
import com.aspose.slides.model.*;

public class Application {
    public static void main(String[] args) throws ApiException {
        SlidesApi slidesApi = new SlidesApi("MyClientId", "MyClientSecret");

        // Prepare notes for the slide.
        NotesSlide notesSlide = new NotesSlide();
        notesSlide.setText("Start with our company.");

        // Create the notes for the second slide.
        NotesSlide currentNotesSlide = slidesApi.createNotesSlide("MyPresentation.pptx", 2, notesSlide, null, "MyFolder", null);

        // Print the resource reference for the notes slide.
        System.out.println(currentNotesSlide.getSelfUri().getHref());
    }
}
```

{{< /tab >}}

{{< tab tabNum="3" >}}

```php
// For complete examples and data files, please go to https://github.com/aspose-Slides-cloud/aspose-Slides-cloud-php

use Aspose\Slides\Cloud\Sdk\Api\Configuration;
use Aspose\Slides\Cloud\Sdk\Api\SlidesApi;
use Aspose\Slides\Cloud\Sdk\Model\NotesSlide;

$configuration = new Configuration();
$configuration->setAppSid("MyClientId");
$configuration->setAppKey("MyClientSecret");

$slidesApi = new SlidesApi(null, $configuration);

// Prepare notes for the slide.
$notesSlide = new NotesSlide();
$notesSlide->setText("Start with our company.");

// Create the notes for the second slide.
$currentNotesSlide = $slidesApi->createNotesSlide("MyPresentation.pptx", 2, $notesSlide, null, "MyFolder");

// Print the resource reference for the notes slide.
echo $currentNotesSlide->getSelfUri()->getHref();
```

{{< /tab >}}

{{< tab tabNum="4" >}}

```ruby
# For complete examples and data files, please go to https://github.com/aspose-Slides-cloud/aspose-Slides-cloud-ruby

require "aspose_slides_cloud"

include AsposeSlidesCloud

configuration = AsposeSlidesCloud::Configuration.new
configuration.app_sid = "MyClientId"
configuration.app_key = "MyClientSecret"

slides_api = AsposeSlidesCloud::SlidesApi.new(configuration)

# Prepare notes for the slide.
notes_slide = AsposeSlidesCloud::NotesSlide.new
notes_slide.text = "Start with our company."

# Create the notes for the second slide.
current_notes_slide = slides_api.create_notes_slide("MyPresentation.pptx", 2, notes_slide, nil, "MyFolder")

# Print the resource reference for the notes slide.
print current_notes_slide.self_uri.href
```

{{< /tab >}}

{{< tab tabNum="5" >}}

```python
# For complete examples and data files, please go to https://github.com/aspose-Slides-cloud/aspose-Slides-cloud-python

import asposeslidescloud

from asposeslidescloud.apis.slides_api import SlidesApi
from asposeslidescloud.models.notes_slide import NotesSlide

slides_api = SlidesApi(None, "MyClientId", "MyClientSecret")

# Prepare notes for the slide.
notes_slide = NotesSlide()
notes_slide.text = "Start with our company."

# Create the notes for the second slide.
current_notes_slide = slides_api.create_notes_slide("MyPresentation.pptx", 2, notes_slide, None, "MyFolder")

# Print the resource reference for the notes slide.
print(current_notes_slide.self_uri.href)
```

{{< /tab >}}

{{< tab tabNum="6" >}}

```js
// For complete examples and data files, please go to https://github.com/aspose-Slides-cloud/aspose-Slides-cloud-nodejs

const cloud = require("asposeslidescloud");

const slidesApi = new cloud.SlidesApi("MyClientId", "MyClientSecret");

// Prepare notes for the slide.
const notesSlide = new cloud.NotesSlide();
notesSlide.text = "Start with our company.";

// Create the notes for the second slide.
slidesApi.createNotesSlide("MyPresentation.pptx", 2, notesSlide, null, "MyFolder").then(currentNotesSlide => {
    // Print the resource reference for the notes slide.
    console.log(currentNotesSlide.body.selfUri.href);
});
```

{{< /tab >}}

{{< tab tabNum="7" >}}

```cpp
// For complete examples and data files, please go to https://github.com/aspose-Slides-cloud/aspose-Slides-cloud-cpp

#include "asposeslidescloud/api/SlidesApi.h"

using namespace asposeslidescloud::api;

int main()
{
    auto slidesApi = std::make_shared<SlidesApi>(L"MyClientId", L"MyClientSecret");

    // Prepare notes for the slide.
    auto notesSlide = std::make_shared<NotesSlide>();
    notesSlide->setText(L"Start with our company.");

    // Create the notes for the second slide.
    auto currentNotesSlide = slidesApi->createNotesSlide(L"MyPresentation.pptx", 2, notesSlide, L"", L"MyFolder").get();

    // Print the resource reference for the notes slide.
    std::wcout << currentNotesSlide->getSelfUri()->getHref();

    return 0;
}
```

{{< /tab >}}

{{< tab tabNum="8" >}}

```perl
# For complete examples and data files, please go to https://github.com/aspose-Slides-cloud/aspose-Slides-cloud-perl

use AsposeSlidesCloud::Configuration;
use AsposeSlidesCloud::SlidesApi;
use AsposeSlidesCloud::Object::NotesSlide;

my $config = AsposeSlidesCloud::Configuration->new();
$config->{app_sid} = "MyClientId";
$config->{app_key} = "MyClientSecret";

my $slides_api = AsposeSlidesCloud::SlidesApi->new(config => $config);

# Prepare notes for the slide.
my $notes_slide = AsposeSlidesCloud::Object::NotesSlide->new();
$notes_slide->{text} = "Start with our company.";

# Create the notes for the second slide.
my %parameters = (name => "MyPresentation.pptx", slide_index => 2, dto => $notes_slide, folder => "MyFolder");
my $current_notes_slide = $slides_api->create_notes_slide(%parameters);

# Print the resource reference for the notes slide.
print $current_notes_slide->{self_uri}->{href};
```

{{< /tab >}}

{{< tab tabNum="9" >}}

{{< /tab >}}

{{< tab tabNum="10" >}}

{{< /tab >}}

{{< /tabs >}}

## **SDKs**

Check [Available SDKs](/slides/available-sdks/) to learn how to add an SDK to your project.
