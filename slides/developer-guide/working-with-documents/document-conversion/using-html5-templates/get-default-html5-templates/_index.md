---
title: "Get Default HTML5 Templates"
keywords:
- PowerPoint
- presentation
- REST API
- cloud API
- convert a presentation
- export a presentation
type: docs
url: /get-default-html5-templates/
weight: 20
---
## **Introduction**

Presentations are converted to HTML5 using html (Razor) templates. You can use **GetHtml5Templates** method to download those templates as a ZIP archive. You can use them to create custom templates for your own implementation of HTML5 export.

See the example below.

## **cURL Example**

{{< tabs tabTotal="2" tabID="1" tabName1="Request" tabName2="Response" >}}

{{< tab tabNum="1" >}}

**Get Authentication Token**

```sh
curl -v "https://api.aspose.cloud/connect/token" -X POST -d "grant_type=client_credentials&client_id=XXXX&client_secret=XXXX-XX" -H "Content-Type: application/x-www-form-urlencoded" -H "Accept: application/json"
```

**Download Templates**

```sh
curl  -v "https://api.aspose.cloud/v3.0/slides/html5Templates" -d "" -H "Authorization: Bearer [Access Token]
```

{{< /tab >}}

{{< tab tabNum="2" >}}

```java

Code: 200
Returns the templates as a ZIP archive.

```

{{< /tab >}}

{{< /tabs >}}

## **SDK Source**
The Aspose for Cloud SDKs can be downloaded from the following page: [Available SDKs](/slides/available-sdks/)
## **SDK Examples**
{{< tabs tabTotal="8" tabID="5" tabName1="C#" tabName2="Java" tabName3="PHP" tabName4="Ruby" tabName5="Python" tabName6="Node.js" tabName7="Go" tabName8="Perl" >}}

{{< tab tabNum="1" >}}

```csharp
SlidesApi api = new SlidesApi("MyClientId", "MyClientSecret");
Stream response = api.GetHtml5Templates();
using Stream outFile = File.Create("Html5Templates.zip");
response.CopyTo(outFile);
```

{{< /tab >}}

{{< tab tabNum="2" >}}

```java
SlidesApi api = new SlidesApi("MyClientId", "MyClientSecret");
File response = api.getHtml5Templates();
System.out.println("The templates were saved to " + response.getPath());
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

$response = $api->getHtml5Templates();
print("The templates were saved to " . $result->getPathname());
```

{{< /tab >}}

{{< tab tabNum="4" >}}

```ruby
configuration = AsposeSlidesCloud::Configuration.new
configuration.app_sid = "MyClientId"
configuration.app_key = "MyClientSecret"
api = AsposeSlidesCloud::SlidesApi.new(configuration)

result = api.get_html5_templates()
File.binwrite("Html5Templates.zip", result)
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

result = api.get_html5_templates()
print('The templates were saved to ' + result)
```

{{< /tab >}}

{{< tab tabNum="6" >}}

```javascript
const CloudSdk = require("asposeslidescloud");
const fs = require("fs");
const api = new CloudSdk.SlidesApi("MyClientId", "MyClientSecret");

api.getHtml5Templates().then(response => {
    fs.writeFile("Html5Templates.zip", response.body, (err) => {
        if (err) throw err;
    });
});
```

{{< /tab >}}

{{< tab tabNum="7" >}}

```go
cfg := asposeslidescloud.NewConfiguration()
cfg.AppSid = "MyClientId"
cfg.AppKey = "MyClientSecret"
api := asposeslidescloud.NewAPIClient(cfg)

result, _, e := api.SlidesApi.GetHtml5Templates()
if e != nil {
    fmt.Printf("Error: %v.", e)
    return
}
fmt.Printf("The templates were saved to %v.", result.Name())
```

{{< /tab >}}

{{< tab tabNum="8" >}}

```perl
use File::Slurp;

use AsposeSlidesCloud::Configuration;
use AsposeSlidesCloud::SlidesApi;

my $config = AsposeSlidesCloud::Configuration->new();
$config->{app_sid} = "MyClientId";
$config->{app_key} = "MyClientSecret";
my $api = AsposeSlidesCloud::SlidesApi->new(config => $config);

my $result = $api->get_html5_templates();
my $zip = "Html5Templates.zip";
open my $fh, '>', $zip;
binmode $fh;
print $fh $result;
close $fh;
```

{{< /tab >}}

{{< /tabs >}}
