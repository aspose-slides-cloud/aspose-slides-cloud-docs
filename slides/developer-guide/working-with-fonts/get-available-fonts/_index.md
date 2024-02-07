---
title: "Get Available Fonts"
type: docs
url: /get-available-fonts/
weight: 30
---
## **Introduction**
Aspose.Slides Cloud API provides a method that allows getting list of fonts installed in the system. You can optionally pass **fontsFolder** parameter to this method specifying a storage folder that contains custom fonts. The fonts contained in that folder are added to the result list. You can check **FontData.IsCustom** property of any item in the returned list to determine whether it is a custom font.

## **GetAvailableFonts**
### **API Information**
|**API**|**Type**|**Description**|**Resource**|
| :- | :- | :- | :- |
/slides/fonts/available|Get|Returns system fonts info.|[GetAvailableFonts](https://apireference.aspose.cloud/slides/#/Fonts/GetAvailableFonts)|

### **Examples**

**cURL Example**

The code example below show how to obtain the list of available fonts.

{{< tabs tabTotal="2" tabID="1" tabName1="Request" tabName2="Response" >}}

{{< tab tabNum="1" >}}

**Create Authentication Headers**
```sh
curl -v "https://api.aspose.cloud/connect/token" -X POST -d "grant_type=client_credentials&client_id=XXXX&client_secret=XXXX-XX" -H "Content-Type: application/x-www-form-urlencoded" -H "Accept: application/json"
```

```sh
curl -X GET "https://api.aspose.cloud/v3.0/slides/fonts/available?fontsFolder=customFonts" -H "Authorization: Bearer [Access Token]"
```

{{< /tab >}}

{{< tab tabNum="2" >}}

```json

{
    "list": [
        { "fontName": "Arial" },
        { "fontName": "Arial Black" },
        ...
        {"fontName": "Yu Gothic UI Semibold" },
        {"fontName": "Yu Gothic UI Semilight" },
        {"fontName": "Helvetica", "isCustom": true },
        {"fontName": "Yu Mincho", "isCustom": true }
    ]
}
```
{{< /tab >}}

{{< /tabs >}}


**SDK Examples**

{{< tabs tabTotal="10" tabID="11" tabName1="C#" tabName2="Java" tabName3="PHP" tabName4="Ruby" tabName5="Python" tabName6="Node.js" tabName7="Go" tabName8="C++" tabName9="Perl" tabName10="Swift" >}}
{{< tab tabNum="1" >}}

```csharp
SlidesApi api = new SlidesApi("MyClientId", "MyClientSecret");

FontsData fonts = api.GetAvailableFonts("customFonts");
Console.WriteLine("List of available fonts:");
foreach (FontData font in fonts.List)
{
    Console.Write(font.FontName);
    if (font.IsCustom == true)
    {
        Console.Write(" (custom)");
    }
    Console.WriteLine();
}
```

{{< /tab >}}
{{< tab tabNum="2" >}}

```java
SlidesApi api = new SlidesApi("MyClientId", "MyClientSecret");

System.out.println("List of available fonts:");
FontsData fonts = api.getAvailableFonts("customFonts", null);
for (FontData font : fonts.getList()) {
    System.out.print(font.getFontName());
    if (font.getIsCustom() != null && font.getIsCustom())
    {
        System.out.print(" (custom)");
    }
    System.out.println();
}
```

{{< /tab >}}
{{< tab tabNum="3" >}}

```php
use Aspose\Slides\Cloud\Sdk\Api\Configuration;
use Aspose\Slides\Cloud\Sdk\Api\SlidesApi;

$config = new Configuration();
$config->setAppSid("MyClientId");
$config->setAppKey("MyClientSecret");
$api = new SlidesApi(null, $config);

$fonts = $api->getAvailableFonts("customFonts");
print("List of available fonts:\n");
foreach ($fonts->getList() as $font)
{
    print($font->getFontName());
    if ($font->getIsCustom())
    {
        print(" (custom)");
    }
    print("\n");
}
```

{{< /tab >}}
{{< tab tabNum="4" >}}

```ruby
configuration = AsposeSlidesCloud::Configuration.new
configuration.app_sid = "MyClientId"
configuration.app_key = "MyClientSecret"
api = AsposeSlidesCloud::SlidesApi.new(configuration)

fonts = api.get_available_fonts("customFonts")
puts("List of available fonts:")
for font in fonts.list
    print(font.font_name)
    if font.is_custom
        print(" (custom)")
    end
    puts("")
end
```

{{< /tab >}}
{{< tab tabNum="5" >}}

```python
import asposeslidescloud

from asposeslidescloud.configuration import Configuration
from asposeslidescloud.apis.slides_api import SlidesApi

configuration = Configuration()
configuration.app_sid = 'MyClientId'
configuration.app_key = 'MyClientSecret'
api = SlidesApi(configuration)

fonts = api.get_available_fonts("customFonts")
print("List of available fonts:")
for font in fonts.list:
    print(font.font_name, end = "")
    if font.is_custom:
        print(" (custom)", end = "")
    print("")
```

{{< /tab >}}
{{< tab tabNum="6" >}}

```javascript
const CloudSdk = require("asposeslidescloud");
const api = new CloudSdk.SlidesApi("MyClientId", "MyClientSecret");

let fonts = await api.getAvailableFonts("customFonts");
console.log("List of available fonts:");
for (var i = 0; i < fonts.body.list; i++) {
    process.stdout.write(fonts.body.list[i].font_name);
    if (fonts.body.list[i].isCustom) {
        process.stdout.write(" (custom)");
    }
    console.log("");
}        
```
{{< /tab >}}
{{< tab tabNum="7" >}}

```go
cfg := asposeslidescloud.NewConfiguration()
cfg.AppSid = "MyClientId"
cfg.AppKey = "MyClientSecret"
api := asposeslidescloud.NewAPIClient(cfg)

fonts, _, e := api.SlidesApi.GetAvailableFonts("customFonts", "")
if e != nil {
    fmt.Printf("Error: %v.", e)
    return
}

fmt.Printf("List of available fonts:\n")
for _, font := range fonts.GetList() {
    fmt.Printf("%v", font.GetFontName())
    if font.GetIsCustom() {
        fmt.Printf(" (custom)")
    }
    fmt.Printf("\n")
}
```

{{< /tab >}}
{{< tab tabNum="8" >}}

{{< /tab >}}

{{< tab tabNum="9" >}}

```perl
use AsposeSlidesCloud::Configuration;
use AsposeSlidesCloud::SlidesApi;

my $config = AsposeSlidesCloud::Configuration->new();
$config->{app_sid} = "MyClientId";
$config->{app_key} = "MyClientSecret";
my $api = AsposeSlidesCloud::SlidesApi->new(config => $config);

my %params = ('fonts_folder' => 'customFonts');
my $fonts = $api->get_available_fonts(%params);
print "List of available fonts:\n";
foreach my $font (@($fonts->{list})) {
    print $font->{font_name};
    if ($font->{is_custom}) {
        print " (custom)";
    }
    print "\n";
}
```

{{< /tab >}}

{{< tab tabNum="10" >}}

{{< /tab >}}

{{< /tabs >}}

## **SDK Source**

The Aspose for Cloud SDKs can be downloaded from the following page: [Available SDKs](/slides/available-sdks/)