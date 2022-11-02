---
title: "Adding SmartArt Node"
type: docs
url: /adding-smartart-node/
weight: 20
---

## **Introduction**

This article shows you how to add a new node to SmartArt graphic using Aspose.Slides Cloud in your applications. The node can be added on any level of the SmartArt object. To specify parent node for the new node, use "subNode" parameter (e.g., "1", "1/nodes/2") or leave it empty if the new node is a root node.
The method uses a smartArtIndex parameter, which targets a specific SmartArt object among objects of the same type. Let's say the slide contains ten shapes of various types and only two SmartArt objects among them, the indexes of the SmartArt objects will be 1 and 2 respectively. 

### **API Information**
|**API**|**Type**|**Description**|**Resource**|
| :- | :- | :- | :- |
/slides/{name}/slides/{slideIndex}/smartArts/{smartArtIndex}/nodes|POST|Add SmartArt node.|[CreateSmartArtNode]()|
### **cURL Example**

The code examples below shows how to create a sub-node for the root node of the SmartArt object, and place it at position 1.

{{< tabs tabTotal="2" tabID="1" tabName1="Request" tabName2="Response" >}}

{{< tab tabNum="1" >}}

**Create Authentication Headers**
```sh
curl -v "https://api.aspose.cloud/connect/token" -X POST -d "grant_type=client_credentials&client_id=XXXX&client_secret=XXXX-XX" -H "Content-Type: application/x-www-form-urlencoded" -H "Accept: application/json"
```

```sh
curl -X POST "https://api.aspose.cloud/v3.0/slides/MyPresentation.pptx/slides/7/smartArts/nodes?subNode=1&position=1&text=new%20sub%20node" -H "Authorization: Bearer [Access Token]"
```

{{< /tab >}}

{{< tab tabNum="2" >}}

```sh

Code: 200
Returns SmartArt info.

```

{{< /tab >}}

{{< /tabs >}}

## **SDK Source**

The Aspose for Cloud SDKs can be downloaded from the following page: [Available SDKs](/slides/available-sdks/)

## **SDK Examples**
{{< tabs tabTotal="10" tabID="5" tabName1="C#" tabName2="Java" tabName3="PHP" tabName4="Ruby" tabName5="Python" tabName6="Node.js" tabName7="Go" tabName8="C++" tabName9="Perl" tabName10="Swift" >}}
{{< tab tabNum="1" >}}

```csharp
SlidesApi api = new SlidesApi("MyClientId", "MyClientSecret");
int slideIndex = 7;
int smartArtIndex = 1;
string subNodePath = "1";
string newSubNodeText = "New sub-node";
int position = 1;
SmartArt response = api.CreateSmartArtNode("MyPresentation.pptx", slideIndex, smartArtIndex, subNodePath, newSubNodeText, position);

Console.WriteLine("Root node contains " + response.Nodes[0].Nodes.Count + " sub-nodes.");
```

{{< /tab >}}
{{< tab tabNum="2" >}}

```java
SlidesApi api = new SlidesApi("MyClientId", "MyClientSecret");
int slideIndex = 7;
int smartArtIndex = 1;
String newSubNodeText = "New sub-node";
String subNodePath = "1";
int position = 1;

SmartArt response = api.createSmartArtNode("MyPresentation.pptx", slideIndex, smartArtIndex, subNodePath, newSubNodeText,
                position, null, null, null);

System.out.println("Root node contains " + response.getNodes().get(0).getNodes().size() + " sub-nodes.");
```

{{< /tab >}}
{{< tab tabNum="3" >}}

```php
use Aspose\Slides\Cloud\Sdk\Api\Configuration;
use Aspose\Slides\Cloud\Sdk\Api\SlidesApi;
use Aspose\Slides\Cloud\Sdk\Model\SmartArt;

$config = new Configuration();
$config->setAppSid("MyClientId");
$config->setAppKey("MyClientSecret");
$api = new SlidesApi(null, $config);

$slideIndex = 7;
$smartArtIndex = 1;
$subNodePath = "1";
$newSubNodeText = "New sub-node";
$position = 1;
$response = $api->createSmartArtNode("MyPresentation.pptx", $slideIndex, $smartArtIndex, $subNodePath, $newSubNodeText, $position);
        
print("Root node contains " . count($response->getNodes()[0]->getNodes()) . " sub-nodes.");
```

{{< /tab >}}
{{< tab tabNum="4" >}}

```ruby
configuration = AsposeSlidesCloud::Configuration.new
configuration.app_sid = "MyClientId"
configuration.app_key = "MyClientSecret"
api = AsposeSlidesCloud::SlidesApi.new(configuration)
slide_index = 7
smart_art_index = 1
sub_node_path = "1"
position = 1
new_node_text = "New-sub-node"
response = api.create_smart_art_node("MyPresentation.pptx", slide_index, smart_art_index, sub_node_path, new_node_text, position)

print "Root node contains " + response.nodes[0].nodes.length + " sub-nodes."
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

slide_index = 7
smart_art_index = 1
sub_node_path = "1"
new_sub_node_text = "New sub-node"
position = 1
response = api.create_smart_art_node("MyPresentation.pptx", slide_index, smart_art_index, sub_node_path, new_sub_node_text, position)

print(f"Root node contains { len(response.nodes[0].nodes) } sub-nodes.")
```

{{< /tab >}}
{{< tab tabNum="6" >}}

```javascript
const CloudSdk = require("asposeslidescloud");
const api = new CloudSdk.SlidesApi("MyClientId", "MyClientSecret");

const slideIndex = 7;
const smartArtIndex = 1;
const subNodePath = "1";
const newSubNodeText = "New sub-node";
const position = 1;
const response = await api.createSmartArtNode("MyPresentation.pptx", slideIndex, smartArtIndex, subNodePath, newSubNodeText, position);
      
console.log("Root node contains " + response.body.nodes[0].nodes.length + " sub-nodes.");
```
{{< /tab >}}
{{< tab tabNum="7" >}}

```go
cfg := asposeslidescloud.NewConfiguration()
cfg.AppSid = "MyClientId"
cfg.AppKey = "MyClientSecret"
api := asposeslidescloud.NewAPIClient(cfg)

var slideIndex int32 = 7
var smartArtIndex int32 = 1
newSubNodeText := "New sub-node"
subNodePath := "1"
var position int32 = 1

response, _, e := api.CreateSmartArtNode("MyPresentation.pptx", slideIndex, smartArtIndex, subNodePath, newSubNodeText,
		&position, "", "", "")
	if e != nil {
		t.Errorf("Error: %v.", e)
		return
	}

fmt.Printf("Root node contains " + len(response.GetNodes()[0].GetNodes()) + " sub-nodes.")
```

{{< /tab >}}
{{< tab tabNum="8" >}}

{{< /tab >}}

{{< tab tabNum="9" >}}

```perl
use AsposeSlidesCloud::Configuration;
use AsposeSlidesCloud::SlidesApi;
use AsposeSlidesCloud::Object::SlideComment;

my $config = AsposeSlidesCloud::Configuration->new();
$config->{app_sid} = "MyClientId";
$config->{app_key} = "MyClientSecret";
my $api = AsposeSlidesCloud::SlidesApi->new(config => $config);

#Code example will be added soon.
```

{{< /tab >}}

{{< tab tabNum="10" >}}

{{< /tab >}}

{{< /tabs >}}
