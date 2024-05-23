---
title: "Working with View Properties"
keywords:
- PowerPoint
- presentation
- REST API
- cloud API
- view properties
- last view
- horizontal bar state
- vertical bar state
- single view
- view scale
- show comments
- handout view
- outline view
- slide view
- slide master view
- notes master view
- slide thumbnail view
type: docs
url: /working-with-view-properties/
weight: 60
---

## **Introduction**

In PowerPoint documents, view properties refer to the various viewing modes available that allow you to work with your presentation in different ways, depending on your current needs. Use the following methods to get and update the view properties of a presentation. 

## **GetViewProperties**

### **API Information**

|**API**|**Type**|**Description**|**Resource**|
| :- | :- | :- | :- |
|/slides/{name}/viewProperties|GET|Returns the view properties from a presentation saved in a storage.|[GetViewProperties](https://reference.aspose.cloud/slides/#/Document/GetViewProperties)|

**Request Parameters**

|**Name**|**Type**|**Location**|**Required**|**Description**|
| :- | :- | :- | :- | :- |
|name|string|path|true|The name of a presentation file.|
|password|string|header|false|The password to open the presentation.|
|folder|string|query|false|The path to the folder containing the presentation file.|
|storage|string|query|false|The name of the storage contaning the folder.|

### **Examples**

Retrieve the view properties from the document **MyPresentation.pptx** saved in the **default** storage.

**cURL Solution**

{{< tabs tabTotal="2" tabID="1" tabName1="Request" tabName2="Response" >}}

{{< tab tabNum="1" >}}

**Get an Access Token**

```sh
curl -X POST "https://api.aspose.cloud/connect/token" \
     -d "grant_type=client_credentials&client_id=MyClientId&client_secret=MyClientSecret" \
     -H "Content-Type: application/x-www-form-urlencoded"
```

**Get the View Properties**

```sh
curl -X GET "https://api.aspose.cloud/v3.0/slides/MyPresentation.pptx/viewProperties" \
     -H "authorization: Bearer MyAccessToken"
```

{{< /tab >}}

{{< tab tabNum="2" >}}

**Response Example**

```json
{
  "lastView": "SlideView",
  "horizontalBarState": "Restored",
  "verticalBarState": "Restored",
  "preferSingleView": false,
  "restoredLeft": {
    "autoAdjust": true,
    "dimensionSize": 15.62
  },
  "restoredTop": {
    "autoAdjust": true,
    "dimensionSize": 94.66
  },
  "slideViewProperties": {
    "scale": 93,
    "variableScale": true
  },
  "notesViewProperties": {
    "scale": 1,
    "variableScale": false
  },
  "showComments": "True",
  "selfUri": {
    "href": "https://api.aspose.cloud/v3.0/slides/MyPresentation.pptx/viewProperties",
    "relation": "self"
  }
}
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

        ViewProperties viewProperties = slidesApi.GetViewProperties("MyPresentation.pptx");

        Console.WriteLine("Horizontal bar state: " + viewProperties.HorizontalBarState);
        Console.WriteLine("Last view: " + viewProperties.LastView);
        Console.WriteLine("Notes view scale: " + viewProperties.NotesViewProperties.Scale);
        Console.WriteLine("Prefer single view: " + viewProperties.PreferSingleView);
        Console.WriteLine("Show comments: " + viewProperties.ShowComments);
        Console.WriteLine("Slide view scale: " + viewProperties.SlideViewProperties.Scale);
        Console.WriteLine("Vertical bar state: " + viewProperties.VerticalBarState);
    }
}

// Example output:
//
// Horizontal bar state: Restored
// Last view: SlideView
// Notes view scale: 1
// Prefer single view: False
// Show comments: True
// Slide view scale: 93
// Vertical bar state: Restored
```

{{< /tab >}}

{{< tab tabNum="2" >}}

```java
import com.aspose.slides.ApiException;
import com.aspose.slides.api.SlidesApi;
import com.aspose.slides.model.ViewProperties;

public class Application {
    public static void main(String[] args) throws ApiException {
        SlidesApi slidesApi = new SlidesApi("MyClientId", "MyClientSecret");

        ViewProperties viewProperties = slidesApi.getViewProperties("MyPresentation.pptx", null, null, null);

        System.out.println("Horizontal bar state: " + viewProperties.getHorizontalBarState());
        System.out.println("Last view: " + viewProperties.getLastView());
        System.out.println("Notes view scale: " + viewProperties.getNotesViewProperties().getScale());
        System.out.println("Prefer single view: " + viewProperties.isPreferSingleView());
        System.out.println("Show comments: " + viewProperties.getShowComments());
        System.out.println("Slide view scale: " + viewProperties.getSlideViewProperties().getScale());
        System.out.println("Vertical bar state: " + viewProperties.getVerticalBarState());
    }
}

// Example output:
//
// Horizontal bar state: Restored
// Last view: SlideView
// Notes view scale: 1
// Prefer single view: false
// Show comments: True
// Slide view scale: 93
// Vertical bar state: Restored
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

$viewProperties = $slidesApi->getViewProperties("MyPresentation.pptx");

print("Horizontal bar state: " . $viewProperties->getHorizontalBarState()) . "\r\n";
print("Last view: " . $viewProperties->getLastView() . "\r\n");
print("Notes view scale: " . $viewProperties->getNotesViewProperties()->getScale() . "\r\n");
print("Prefer single view: " . $viewProperties->getPreferSingleView() . "\r\n");
print("Show comments: " . $viewProperties->getShowComments() . "\r\n");
print("Slide view scale: " . $viewProperties->getSlideViewProperties()->getScale() . "\r\n");
print("Vertical bar state: " . $viewProperties->getVerticalBarState() . "\r\n");

// Example output:
//
// Horizontal bar state: Restored
// Last view: SlideView
// Notes view scale: 1
// Prefer single view: 
// Show comments: True
// Slide view scale: 93
// Vertical bar state: Restored
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

view_properties = slides_api.get_view_properties("MyPresentation.pptx")

puts "Horizontal bar state: #{view_properties.horizontal_bar_state}"
puts "Last view: #{view_properties.last_view}"
puts "Notes view scale: #{view_properties.notes_view_properties.scale}"
puts "Prefer single view: #{view_properties.prefer_single_view}"
puts "Show comments: #{view_properties.show_comments}"
puts "Slide view scale: #{view_properties.slide_view_properties.scale}"
puts "Vertical bar state: #{view_properties.vertical_bar_state}"

# Example output:
#
# Horizontal bar state: Restored
# Last view: SlideView
# Notes view scale: 1
# Prefer single view: false
# Show comments: True
# Slide view scale: 93
# Vertical bar state: Restored
```

{{< /tab >}}

{{< tab tabNum="5" >}}

```py
from asposeslidescloud.apis import SlidesApi

slides_api = SlidesApi(None, "MyClientId", "MyClientSecret")

view_properties = slides_api.get_view_properties("MyPresentation.pptx")

print("Horizontal bar state:", view_properties.horizontal_bar_state)
print("Last view:", view_properties.last_view)
print("Notes view scale:", view_properties.notes_view_properties.scale)
print("Prefer single view:", view_properties.prefer_single_view)
print("Show comments:", view_properties.show_comments)
print("Slide view scale:", view_properties.slide_view_properties.scale)
print("Vertical bar state:", view_properties.vertical_bar_state)

# Example output:
#
# Horizontal bar state: Restored
# Last view: SlideView
# Notes view scale: 1
# Prefer single view: False
# Show comments: True
# Slide view scale: 93
# Vertical bar state: Restored
```

{{< /tab >}}

{{< tab tabNum="6" >}}

```js
const cloudSdk = require("asposeslidescloud");

const slidesApi = new cloudSdk.SlidesApi("MyClientId", "MyClientSecret");

slidesApi.getViewProperties("MyPresentation.pptx").then(viewProperties => {
    console.log("Horizontal bar state:", viewProperties.body.horizontalBarState);
    console.log("Last view:", viewProperties.body.lastView);
    console.log("Notes view scale:", viewProperties.body.notesViewProperties.scale);
    console.log("Prefer single view:", viewProperties.body.preferSingleView);
    console.log("Show comments:", viewProperties.body.showComments);
    console.log("Slide view scale:", viewProperties.body.slideViewProperties.scale);
    console.log("Vertical bar state:", viewProperties.body.verticalBarState);
});

// Example output:
//
// Horizontal bar state: Restored
// Last view: SlideView
// Notes view scale: 1
// Prefer single view: false
// Show comments: True
// Slide view scale: 93
// Vertical bar state: Restored
```

{{< /tab >}}

{{< tab tabNum="7" >}}

```cpp
#include "asposeslidescloud/api/SlidesApi.h"

using namespace asposeslidescloud::api;

int main()
{
    std::shared_ptr<SlidesApi> slidesApi = std::make_shared<SlidesApi>(L"MyClientId", L"MyClientSecret");

    std::shared_ptr<ViewProperties> viewProperties = slidesApi->getViewProperties(L"MyPresentation.pptx").get();

    std::wcout << L"Horizontal bar state: " << viewProperties->getHorizontalBarState() << std::endl;
    std::wcout << L"Last view: " << viewProperties->getLastView() << std::endl;
    std::wcout << L"Notes view scale: " << viewProperties->getNotesViewProperties()->getScale() << std::endl;
    std::wcout << L"Prefer single view: " << viewProperties->isPreferSingleView() << std::endl;
    std::wcout << L"Show comments: " << viewProperties->getShowComments() << std::endl;
    std::wcout << L"Slide view scale: " << viewProperties->getSlideViewProperties()->getScale() << std::endl;
    std::wcout << L"Vertical bar state: " << viewProperties->getVerticalBarState() << std::endl;
}

// Example output:
//
// Horizontal bar state: Restored
// Last view: SlideView
// Notes view scale: 1
// Prefer single view: 0
// Show comments: True
// Slide view scale: 93
// Vertical bar state: Restored
```

{{< /tab >}}

{{< tab tabNum="8" >}}

```pl
use AsposeSlidesCloud::Configuration;
use AsposeSlidesCloud::SlidesApi;

my $configuration = AsposeSlidesCloud::Configuration->new();
$configuration->{app_sid} = "MyClientId";
$configuration->{app_key} = "MyClientSecret";

my $slides_api = AsposeSlidesCloud::SlidesApi->new(config => $configuration);

my $view_properties = $slides_api->get_view_properties(name => "MyPresentation.pptx");

print "Horizontal bar state: $view_properties->{horizontal_bar_state}\n";
print "Last view: $view_properties->{last_view}\n";
print "Notes view scale: $view_properties->{notes_view_properties}{scale}\n";
print "Prefer single view: $view_properties->{prefer_single_view}\n";
print "Show comments: $view_properties->{show_comments}\n";
print "Slide view scale: $view_properties->{slide_view_properties}{scale}\n";
print "Vertical bar state: $view_properties->{vertical_bar_state}\n";

# Example output:
#
# Horizontal bar state: Restored
# Last view: SlideView
# Notes view scale: 1
# Prefer single view: 0
# Show comments: True
# Slide view scale: 93
# Vertical bar state: Restored
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

	viewProperties, _, _ := slidesApi.GetViewProperties("MyPresentation.pptx", "", "", "")

	fmt.Println("Horizontal bar state:", viewProperties.GetHorizontalBarState())
	fmt.Println("Last view:", viewProperties.GetLastView())
	fmt.Println("Notes view scale:", viewProperties.GetNotesViewProperties().GetScale())
	fmt.Println("Prefer single view:", viewProperties.GetPreferSingleView())
	fmt.Println("Show comments:", viewProperties.GetShowComments())
	fmt.Println("Slide view scale:", viewProperties.GetSlideViewProperties().GetScale())
	fmt.Println("Vertical bar state:", viewProperties.GetVerticalBarState())
}

// Example output:
//
// Horizontal bar state: Restored
// Last view: SlideView
// Notes view scale: 1
// Prefer single view: false
// Show comments: True
// Slide view scale: 93
// Vertical bar state: Restored
```

{{< /tab >}}

{{< /tabs >}}

## **SetViewProperties**

### **API Information**

|**API**|**Type**|**Description**|**Resource**|
| :- | :- | :- | :- |
|/slides/{name}/viewProperties|PUT|Updates the view properties of a presentation saved in a storage.|[SetViewProperties](https://reference.aspose.cloud/slides/#/Document/SetViewProperties)|

**Request Parameters**

|**Name**|**Type**|**Location**|**Required**|**Description**|
| :- | :- | :- | :- | :- |
|name|string|path|true|The name of a presentation file.|
|dto|`ViewProperties`|body|true|The data transfer object with the view properties.|
|password|string|header|false|The password to open the presentation.|
|folder|string|query|false|The path to the folder containing the presentation file.|
|storage|string|query|false|The name of the storage contaning the folder.|

### **Examples**

**Hide comments** and set the **slide view scale** to **50** in the document **MyPresentation.pptx** saved in the **default** storage.

**cURL Solution**

{{< tabs tabTotal="2" tabID="2" tabName1="Request" tabName2="Response" >}}

{{< tab tabNum="1" >}}

**Get an Access Token**

```sh
curl -X POST "https://api.aspose.cloud/connect/token" \
     -d "grant_type=client_credentials&client_id=MyClientId&client_secret=MyClientSecret" \
     -H "Content-Type: application/x-www-form-urlencoded"
```

**Set the View Properties**

```sh
curl -X PUT "https://api.aspose.cloud/v3.0/slides/MyPresentation.pptx/viewProperties" \
     -H "authorization: Bearer MyAccessToken" \
     -H "Content-Type: application/json" \
     -d @ViewProperties.json
```

ViewProperties.json content:

```json
{
  "ShowComments": "False",
  "SlideViewProperties": {
	"Scale": 50
  }
}
```

{{< /tab >}}

{{< tab tabNum="2" >}}

**Response Example**

```json
{
  "lastView": "SlideView",
  "horizontalBarState": "Maximized",
  "verticalBarState": "Restored",
  "preferSingleView": false,
  "restoredLeft": {
    "autoAdjust": false,
    "dimensionSize": 15.62
  },
  "restoredTop": {
    "autoAdjust": false,
    "dimensionSize": 94.66
  },
  "slideViewProperties": {
    "scale": 50,
    "variableScale": true
  },
  "notesViewProperties": {
    "scale": 75,
    "variableScale": true
  },
  "showComments": "False",
  "selfUri": {
    "href": "https://api.aspose.cloud/v3.0/slides/MyPresentation.pptx/viewProperties",
    "relation": "self"
  }
}
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

        ViewProperties viewProperties = new ViewProperties
        {
            ShowComments = ViewProperties.ShowCommentsEnum.False,
            SlideViewProperties = new CommonSlideViewProperties
            {
                Scale = 50
            }
        };

        ViewProperties updatedProperties = slidesApi.SetViewProperties(fileName, viewProperties);

        Console.WriteLine("Show comments: " + updatedProperties.ShowComments);                 // False
        Console.WriteLine("Slide view scale: " + updatedProperties.SlideViewProperties.Scale); // 50
    }
}
```

{{< /tab >}}

{{< tab tabNum="2" >}}

```java
import com.aspose.slides.ApiException;
import com.aspose.slides.api.SlidesApi;
import com.aspose.slides.model.ViewProperties;
import com.aspose.slides.model.CommonSlideViewProperties;

public class Application {
    public static void main(String[] args) throws ApiException {
        SlidesApi slidesApi = new SlidesApi("MyClientId", "MyClientSecret");

        String fileName = "MyPresentation.pptx";

        ViewProperties viewProperties = new ViewProperties();
        viewProperties.setShowComments(ViewProperties.ShowCommentsEnum.FALSE);
        viewProperties.setSlideViewProperties(new CommonSlideViewProperties());
        viewProperties.getSlideViewProperties().setScale(50);

        ViewProperties updatedProperties = slidesApi.setViewProperties(fileName, viewProperties, null, null, null);

        System.out.println("Show comments: " + updatedProperties.getShowComments());                      // False
        System.out.println("Slide view scale: " + updatedProperties.getSlideViewProperties().getScale()); // 50
    }
}
```

{{< /tab >}}

{{< tab tabNum="3" >}}

```php
use Aspose\Slides\Cloud\Sdk\Api\Configuration;
use Aspose\Slides\Cloud\Sdk\Api\SlidesApi;
use Aspose\Slides\Cloud\Sdk\Model\ViewProperties;
use Aspose\Slides\Cloud\Sdk\Model\CommonSlideViewProperties;

$configuration = new Configuration();
$configuration->setAppSid("MyClientId");
$configuration->setAppKey("MyClientSecret");

$slidesApi = new SlidesApi(null, $configuration);

$fileName = "MyPresentation.pptx";

$viewProperties = new ViewProperties();
$viewProperties->setShowComments("False");
$viewProperties->setSlideViewProperties(new CommonSlideViewProperties());
$viewProperties->getSlideViewProperties()->setScale(50);

$updatedProperties = $slidesApi->setViewProperties($fileName, $viewProperties);

print("Show comments: " . $updatedProperties->getShowComments() . "\n");                        // False
print("Slide view scale: " . $updatedProperties->getSlideViewProperties()->getScale() . "\n");  // 50
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

view_properties = ViewProperties.new
view_properties.show_comments = "False"
view_properties.slide_view_properties = CommonSlideViewProperties.new
view_properties.slide_view_properties.scale = 50

updated_properties = slides_api.set_view_properties(file_name, view_properties)

puts "Show comments: #{updated_properties.show_comments}"                   # False
puts "Slide view scale: #{updated_properties.slide_view_properties.scale}"  # 50
```

{{< /tab >}}

{{< tab tabNum="5" >}}

```py
from asposeslidescloud.apis import SlidesApi
from asposeslidescloud.models import ViewProperties
from asposeslidescloud.models import CommonSlideViewProperties

slides_api = SlidesApi(None, "MyClientId", "MyClientSecret")

file_name = "MyPresentation.pptx"

view_properties = ViewProperties()
view_properties.show_comments = "False"
view_properties.slide_view_properties = CommonSlideViewProperties()
view_properties.slide_view_properties.scale = 50

updated_properties = slides_api.set_view_properties(file_name, view_properties)

print("Show comments:", updated_properties.show_comments)                   # False
print("Slide view scale:", updated_properties.slide_view_properties.scale)  # 50
```

{{< /tab >}}

{{< tab tabNum="6" >}}

```js
const cloudSdk = require("asposeslidescloud");

const slidesApi = new cloudSdk.SlidesApi("MyClientId", "MyClientSecret");

fileName = "MyPresentation.pptx";

viewProperties = new cloudSdk.ViewProperties();
viewProperties.showComments = cloudSdk.ViewProperties.ShowCommentsEnum.False;
viewProperties.slideViewProperties = new cloudSdk.CommonSlideViewProperties();
viewProperties.slideViewProperties.scale = 50;

slidesApi.setViewProperties(fileName, viewProperties).then(updatedProperties => {
    console.log("Show comments:", updatedProperties.body.showComments);                 // False
    console.log("Slide view scale:", updatedProperties.body.slideViewProperties.scale); // 50
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

    std::shared_ptr<ViewProperties> viewProperties = std::make_shared<ViewProperties>();
    viewProperties->setShowComments(L"False");
    viewProperties->setSlideViewProperties(std::make_shared<CommonSlideViewProperties>());
    viewProperties->getSlideViewProperties()->setScale(50);

    std::shared_ptr<ViewProperties> updatedProperties = slidesApi->setViewProperties(fileName, viewProperties).get();

    std::wcout << L"Show comments: " << updatedProperties->getShowComments() << std::endl;                        // False
    std::wcout << L"Slide view scale: " << updatedProperties->getSlideViewProperties()->getScale() << std::endl;  // 50
}
```

{{< /tab >}}

{{< tab tabNum="8" >}}

```pl
use AsposeSlidesCloud::Configuration;
use AsposeSlidesCloud::SlidesApi;
use AsposeSlidesCloud::Object::ViewProperties;
use AsposeSlidesCloud::Object::CommonSlideViewProperties;

my $configuration = AsposeSlidesCloud::Configuration->new();
$configuration->{app_sid} = "MyClientId";
$configuration->{app_key} = "MyClientSecret";

my $slides_api = AsposeSlidesCloud::SlidesApi->new(config => $configuration);

my $file_name = "MyPresentation.pptx";

my $view_properties = AsposeSlidesCloud::Object::ViewProperties->new();
$view_properties->{show_comments} = "False";
$view_properties->{slide_view_properties} = AsposeSlidesCloud::Object::CommonSlideViewProperties->new();
$view_properties->{slide_view_properties}{scale} = 50;

my $updated_properties = $slides_api->set_view_properties(name => $file_name, dto => $view_properties);

print "Show comments: $updated_properties->{show_comments}\n";                      # False
print "Slide view scale: $updated_properties->{slide_view_properties}{scale}\n";    # 50
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

	viewProperties := asposeslidescloud.NewViewProperties()
	viewProperties.SetShowComments("False")
	viewProperties.SetSlideViewProperties(asposeslidescloud.NewCommonSlideViewProperties())
	viewProperties.GetSlideViewProperties().SetScale(50)

	updatedProperties, _, _ := slidesApi.SetViewProperties(fileName, viewProperties, "", "", "")

	fmt.Println("Show comments:", updatedProperties.GetShowComments())                      // False
	fmt.Println("Slide view scale:", updatedProperties.GetSlideViewProperties().GetScale()) // 50
}
```

{{< /tab >}}

{{< /tabs >}}

## **SDKs**

Check [Available SDKs](/slides/available-sdks/) to learn how to add an SDK to your project.
