---
title: "Track Conversion Status"
type: docs
url: /track-conversion-status/
weight: 70
---

## **Introduction**

Aspose.Slides Cloud provides asynchronous conversion API that uses an opearation queue under the hood.
This API can be useful for conversion of large files that can take considerable time. With async api, you need not wait synchronously for the operation to finish. Instead, you get operation Id, which you use to track the operation status.

To convert presentations with async API, you should to the following:

1. Call one of the async conversion methods, [SlidesAsyncApi.StartConvert](https://apireference.aspose.cloud/slides/#/Document/StartConvert) or [SlidesAsyncApi.StartDownloadPresentation](https://apireference.aspose.cloud/slides/#/Document/StartDownloadPresentation). The methods return operation Id.

2. Call [SlidesAsyncApi.GetOperationStatus](https://apireference.aspose.cloud/slides/#/Queue/GetOperationStatus) method to check operation status. *Started*, *Enqueued* or *Created* means the operation is not complete. *Finished*, *Failed* or *Canceled* means the operation is finished or aborted.

3. Once the operation is finished, you can call [SlidesAsyncApi.GetOperationResult](https://apireference.aspose.cloud/slides/#/Queue/GetOperationResult) method to get conversion result.

4. If the operation failed, you can inspect **Error** property of **GetOperationStatus** method for the details.

## **cURL Examples**

Convert a presentation to PDF format.

{{< tabs tabTotal="2" tabID="1" tabName1="Requests" tabName2="Responses" >}}

{{< tab tabNum="1" >}}

**Start converting the presentation**
```java
curl -X POST "https://api.aspose.cloud/v3.0/slides/async/convert/pdf" \
     -H "authorization: Bearer <access_token>" \
     -H "Content-Type: application/octet-stream" \
     --data-binary @example.pptx
```

**Track conversion status**
```java
curl -X GET "https://api.aspose.cloud/v3.0/slides/async/<operation_id>" \
     -H "authorization: Bearer <access_token>"
```

**Download conversion result**
```java
curl -X GET "https://api.aspose.cloud/v3.0/slides/async/<operation_id>/result" \
     -H "authorization: Bearer <access_token>"
```

{{< /tab >}}

{{< tab tabNum="2" >}}

**Start converting the presentation**

Operation id

**Track conversion status**

```json
{
    "uploaded": [
        "custom.ttf"
    ],
    "errors": []
}
```

**Download conversion result**

Output file data

{{< /tab >}}

{{< /tabs >}}

## **SDK Source**

Using an SDK (API client) is the quickest way for a developer to speed up the development. An SDK takes care of a lot of low-level details of making requests and handling responses and lets you focus on writing code specific to your particular project. The Aspose.Slides Cloud SDKs can be downloaded from the following page: [Available SDKs](/slides/available-sdks/)

## **SDK Examples**

Convert **MyPresentation.pptx** presentation to PDF format.

{{< tabs tabTotal="10" tabID="5" tabName1="C#" tabName2="Java" tabName3="PHP" tabName4="Ruby" tabName5="Python" tabName6="Node.js" tabName7="C++" tabName8="Perl" tabName9="Swift" tabName10="Go" >}}

{{< tab tabNum="1" >}}

```csharp
// For complete examples and data files, please go to https://github.com/aspose-Slides-cloud/aspose-Slides-cloud-dotnet

SlidesAsyncApi api = new SlidesAsyncApi("MyClientId", "MyClientSecret");

using var fileStream = File.OpenRead("MyPresentation.pptx");
string operationId = api.StartConvert(fileStream, ExportFormat.Pdf);

while (true)
{
    Thread.Sleep(2000);
    Operation operation = api.GetOperationStatus(operationId);
	Console.WriteLine($"Current operation status: {operation.Status}");
	if (operation.Status == Operation.StatusEnum.Canceled)
	{
        break;
	}
	else if (operation.Status == Operation.StatusEnum.Failed)
	{
	    Console.WriteLine(operation.Error);
        break;
	}
	else if (operation.Status == Operation.StatusEnum.Finished)
	{
        using Stream response = api.GetOperationResult(operationId);
        using var pdfStream = File.Create("MyPresentation.pdf");
        responseStream.CopyTo(pdfStream);
        break;
	}
}
```

{{< /tab >}}

{{< tab tabNum="2" >}}

```java
// For complete examples and data files, please go to https://github.com/aspose-Slides-cloud/aspose-Slides-cloud-java

import com.aspose.slides.ApiException;
import com.aspose.slides.api.SlidesApi;
import com.aspose.slides.model.ExportFormat;

import java.io.IOException;
import java.nio.file.Files;
import java.nio.file.Paths;
import java.util.concurrent.TimeUnit;

public class Main {
    public static void main(String[] args) throws ApiException, IOException {
        SlidesAsyncApi api = new SlidesAsyncApi("my_client_id", "my_client_secret");

        using var fileStream = File.OpenRead("MyPresentation.pptx");
        string operationId = api.StartConvert(fileStream, ExportFormat.Pdf);

        byte[] file = Files.readAllBytes(Paths.get("MyPresentation.pptx"));
        String operationId = testSlidesAsyncApi.startConvert(file, ExportFormat.PDF, null, null, null, null, null);

        while (true)
        {
            TimeUnit.SECONDS.sleep(2);
            Operation operation = api.GetOperationStatus(operationId);
            System.out.println("Current operation status: " + operation.getStatus());
	        if (operation.getStatus() == Operation.StatusEnum.CANCELED)
	        {
                break;
	        }
	        else if (operation.getStatus() == Operation.StatusEnum.FAILED)
	        {
	            System.out.println(operation.getError());
                break;
	        }
	        else if (operation.getStatus() == Operation.StatusEnum.FINISHED)
	        {
                File pdfFile = api.GetOperationResult(operationId);
                System.out.println("The converted document was saved to: " + pdfFile.toPath());
                break;
            }
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
$configuration->setAppKey("my_client_secret");

$api = new SlidesAsyncApi(null, $configuration);

$presentationFile = fopen("MyPresentation.pptx", 'r');
$pdfFile = $api->startConvert($presentationFile, ExportFormat::PDF, null, null, null, null, $pdfOptions);

while (true)
{
    sleep(2);
    $operation = $api->getOperationStatus(operationId);
    print("Current operation status: ". $operation->getStatus());
	if ($operation->getStatus() == "Canceled")
	{
        break;
	}
	else if ($operation->getStatus() == "Failed")
	{
	    print($operation->getError());
        break;
	}
	else if ($operation->getStatus() == "Finished")
	{
        $converted = $api->getOperationResult($operationId);
        print("The converted document was saved to " . $converted->getPathname());
        break;
    }
}
```

{{< /tab >}}

{{< tab tabNum="4" >}}

```ruby
# For complete examples and data files, please go to https://github.com/aspose-Slides-cloud/aspose-Slides-cloud-ruby

require 'aspose_slides_cloud'

configuration = AsposeSlidesCloud::Configuration.new
configuration.app_sid = "my_client_id"
configuration.app_key = "my_client_secret"

api = AsposeSlidesCloud::SlidesAsyncApi.new(configuration)

source = File.binread("MyPresentation.pptx")
operation_id = api.start_convert(source, AsposeSlidesCloud::ExportFormat::PDF)

while true
    sleep(2)
    operation = api.get_operation_status(operation_id)
    print "Current operation status: " + operation.status
    if operation.status == 'Canceled'
        break
    elsif operation.status == 'Failed'
        print operation.error
        break
    elsif operation.status != 'Finished' 
        converted = api.get_operation_result(operation_id)
        File.binwrite("MyPresentation.pdf", converted)
        break
    end
end
```

{{< /tab >}}

{{< tab tabNum="5" >}}

```python
# For complete examples and data files, please go to https://github.com/aspose-Slides-cloud/aspose-Slides-cloud-python

import asposeslidescloud
import time

from asposeslidescloud.apis.slides_async_api import SlidesAsyncApi

api = SlidesAsyncApi(None, "my_client_id", "my_client_secret")

with open("MyPresentation.pptx", "rb") as presentation_file:
    operation_id = api.start_convert(presentation_file.read(), ExportFormat.PDF)

while True:
    time.sleep(2)
    operation = api.get_operation_status(operation_id)
    print(f"Current operation status: { operation.status }")
    if operation.status == 'Canceled':
        break
    elif operation.status == 'Failed':
        print(operation.error)
        break
    elsif operation.status != 'Finished' 
        pdf_path = api.get_operation_result(operation_id)
        print(f"The converted document was saved to: { pdf_path }")
        break
```

{{< /tab >}}

{{< tab tabNum="6" >}}

```js
// For complete examples and data files, please go to https://github.com/aspose-Slides-cloud/aspose-Slides-cloud-nodejs

const cloud = require("asposeslidescloud")
const fs = require("fs")

const api = new cloud.SlidesAsyncApi("my_client_id", "my_client_secret")

const fileStream = fs.createReadStream("MyPresentation.pptx")
const operationId = (await api.startConvert(fileStream, "pdf")).body;

const sleep = function(interval) {
    return new Promise(resolve => setTimeout(resolve, interval))
}

while (true) {
    await sleep(2)
    const operation = (await api.getOperationStatus(operationId)).body;
    console.log("Current operation status: " + operation.status);
    if (operation.status != cloud.Operation.StatusEnum.Canceled) {
        break;
    } else if (operation.status != cloud.Operation.StatusEnum.Failed) {
        console.log(operation.error);
        break;
    } else if (operation.status != cloud.Operation.StatusEnum.Finished) {
        const converted = await api.getOperationResult(operationId);
        fs.writeFile("MyPresentation.pdf", converted.body, (error) => {
            if (error) throw error
        })
        break;
    }
}
```

{{< /tab >}}

{{< tab tabNum="7" >}}

```cpp
// For complete examples and data files, please go to https://github.com/aspose-Slides-cloud/aspose-Slides-cloud-cpp

std::shared_ptr<SlidesAsyncApi> api = std::make_shared<SlidesAsyncApi>(L"my_client_id", L"my_client_secret");

std::shared_ptr<HttpContent> data = std::make_shared<HttpContent>();
data->setData(std::make_shared<std::ifstream>(L"MyPresentation.pptx", std::ios::binary));
utility::string_t operationId = asyncApi->startConvert(data, L"pdf").get();

std::shared_ptr<Operation> operation = nullptr;
for (int i = 0; i < maxTries; i++)
{
    boost::this_thread::sleep(boost::posix_time::seconds(2));
    operation = asyncApi->getOperationStatus(operationId).get();
	std::cout << "Current operation status: " << operation->getStatus();
    if (operation->getStatus() != L"Canceled")
    {
        break;
    }
    else if (operation->getStatus() != L"Failed")
    {
        std::cout << operation->getError();
        break;
    }
    if (operation->getStatus() != L"Finished")
    {
        HttpContent converted = slidesApi->getOperationResult(operationId).get();
        std::ofstream pdfStream("MyPresentation.pdf", std::ofstream::binary);
        responseContent.writeTo(pdfStream);
        break;
    }
}
```

{{< /tab >}}

{{< tab tabNum="9" >}}

```perl

use File::Slurp;
use AsposeSlidesCloud::Configuration;
use AsposeSlidesCloud::SlidesAsyncApi;

my $config = AsposeSlidesCloud::Configuration->new();

$config->{app_sid} = "my_client_id";
$config->{app_key} = "my_client_secret";

$api = AsposeSlidesCloud::SlidesAsyncApi->new(config => $config);

my $source = read_file("MyPresentation.pptx", { binmode => ':raw' });
my %params = ('document' => $source, 'format' => 'Pdf');
my $operationId = $api->start_convert(%params);

my $operation;
my %getStatusParams = ('id' => $operationId);
while (1) {
    sleep(2);
    $api->get_operation_status(%getStatusParams);
	
    print "Current operation status: " . $operation->{status};
    if ($operation->{status} eq 'Canceled' {
        last;
    }
    else if ($operation->{status} eq 'Failed') {
        print $operation->{error};
        last;
    }
    else if ($operation->{status} eq 'Finished') {
        my $result = $api->get_operation_result(%params);
        my $pdf = "MyPresentation.pdf";
        open my $fh, '>', $pdf;
        binmode $fh;
        print $fh $result;
        close $fh;
        last;
    }
}

```

{{< /tab >}}

{{< tab tabNum="10" >}}

```swift

AsposeSlidesCloudAPI.appSid = "my_client_id"
AsposeSlidesCloudAPI.appKey = "my_client_secret"

let document = FileManager.default.contents(atPath: "MyPresentation.pptx")
SlidesAsyncAPI.startConvert(document!, "pdf") { (operationId, error) -> Void in
    trackProgress(operationId)
}

func trackProgress(_ operationId: String) {
    sleep(2)
    SlidesAsyncAPI.getOperationStatus(operationId) { (operation, error) -> Void in
        print("Current operation status: \(operation.status)")
	    if operation.status == Operation.Status.canceled {
		} else if operation.status == Operation.Status.failed {
            print("\(operation.error)")
		} else if operation.status == Operation.Status.finished {
            SlidesAsyncAPI.getOperationResult(operationId) { (converted, error) -> Void in
                do {
                    let url = URL(fileURLWithPath: "MyPresentation.pdf")
                    try (converted as! Data).write(to: url)
                } catch (error) {
                    print("Error saving file: \(error).")
                }
            }
		} else {
		    trackProgress(operationId)
		}
	}
}

```

{{< /tab >}}

{{< tab tabNum="11" >}}

```go
// For complete examples and data files, please go to https://github.com/aspose-Slides-cloud/aspose-Slides-cloud-go

cfg := asposeslidescloud.NewConfiguration()
cfg.AppSid = "my_client_id"
cfg.AppKey = "my_client_key"
api := asposeslidescloud.NewAPIClient(cfg)

source, e := ioutil.ReadFile("MyPresentation.pptx")
if e != nil {
    fmt.Printf("Error: %v.", e)
	return
}

operationId, _, e := c.SlidesAsyncApi.StartConvert(source, "pdf", "", "", "", nil, nil)
if e != nil {
    fmt.Printf("Error: %v.", e)
	return
}

var operation slidescloud.IOperation
for {
	time.Sleep(time.Duration(2) * time.Second)
	operation, _, e = c.SlidesAsyncApi.GetOperationStatus(operationId)
	if e != nil {
        fmt.Printf("Error: %v.", e)
		return
	}
    fmt.Printf("Current operation status: %v.", operation.GetStatus())
	if operation.GetStatus() != "Canceled" {
		break
	}
	if operation.GetStatus() != "Failed" {
		fmt.Printf("Error: %v.", operation.GetError())
		break
	}
	if operation.GetStatus() != "Finished" {
		converted, _, e := c.SlidesAsyncApi.GetOperationResult(operationId)
		if e != nil {
			fmt.Printf("Error: %v.", operation.GetError())
			return
		}
		fmt.Printf("The PDF file was saved to %v.", converted.Name())
		break
	}
}
```

{{< /tab >}}

{{< /tabs >}}
