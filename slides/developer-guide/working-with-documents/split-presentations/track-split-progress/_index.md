---
title: "Track Split Progress"
keywords:
- PowerPoint
- presentation
- REST API
- cloud API
- split presentations
- split into slides
- asynchronous splitting
type: docs
url: /track-split-progress/
weight: 40
---

## **Introduction**

Aspose.Slides Cloud provides asynchronous split API that uses an opearation queue under the hood.
This API can be useful for splitting large files that can take considerable time. With async api, you need not wait synchronously for the operation to finish. Instead, you get operation Id, which you use to track the operation status.

To split a presentation into slides with async API, you should to the following:

1. Call one of the async split methods, [SlidesAsyncApi.StartSplit](https://apireference.aspose.cloud/slides/#/Document/StartSplit) or [SlidesAsyncApi.StartUploadAndSplit](https://apireference.aspose.cloud/slides/#/Document/StartUploadAndSplit). The methods return operation Id.

2. Call [SlidesAsyncApi.GetOperationStatus](https://apireference.aspose.cloud/slides/#/Queue/GetOperationStatus) method to check operation status. *Started* or *Created* means the operation is not complete. *Finished*, *Failed* or *Canceled* means the operation is finished or aborted.

3. While the operation is in *Started* state you can check *Progress* property to track the split progress.

4. Once the operation is finished, use ordinary API method to retrieve the files produced by it. The **destFolder** parameter determines the storage folder there the files are placed. If the parameter is omitted, the output files are placed to the same folder as the source presentation.

5. If the operation failed, you can inspect **Error** property of **GetOperationStatus** method for the details.

## **cURL Examples**

Split a presentation into slides.

{{< tabs tabTotal="2" tabID="1" tabName1="Requests" tabName2="Responses" >}}

{{< tab tabNum="1" >}}

**Start split**
```sh
curl -X POST "https://api.aspose.cloud/v3.0/slides/async/MyPresentation.pptx/split/pptx?destFolder=splitResult" \
     -H "authorization: Bearer <access_token>"
```

**Track split status**
```sh
curl -X GET "https://api.aspose.cloud/v3.0/slides/async/<operation_id>" \
     -H "authorization: Bearer <access_token>"
```

**Get the list of output files**
```sh
curl -X GET "https://api.aspose.cloud/v3.0/slides/storage/folder/splitResult" \
     -H "authorization: Bearer <access_token>"
```

{{< /tab >}}

{{< tab tabNum="2" >}}

**Start splitting the presentation**

Operation id

**Track split status**

```json
{
    "id": "<operation_id>",
    "method": "Split",
    "status": "Finished",
    "progress": {
        "description": "Slide converted",
        "stepIndex": 5,
        "stepCount": 5
    },
    "created": "2023-11-30T15:38:48.8103587Z",
    "started": "2023-11-30T15:38:49.6465388Z",
    "finished": "2023-11-30T15:38:51.0863055Z"
}
```

**Get files list**

```json
{
  "value": [
    {
      "name": "MyPresentation_1.pptx",
      "isFolder": false,
      "modifiedDate": "2023-11-30T15:38:50.1024350Z",
      "size": 9835,
      "path": "/splitResult/MyPresentation_1.pptx"
    },
    {
      "name": "MyPresentation_2.pptx",
      "isFolder": false,
      "modifiedDate": "2023-11-30T15:38:50.5259313Z",
      "size": 9692,
      "path": "/MyFolder/MyPresentation_2.pptx"
    },
    {
      "name": "MyPresentation_3.pptx",
      "isFolder": false,
      "modifiedDate": "2023-11-30T15:38:51.0281773Z",
      "size": 14259,
      "path": "/MyFolder/MyPresentation_3.pptx"
    }
  ]
}
```

{{< /tab >}}

{{< /tabs >}}

## **SDK Source**

Using an SDK (API client) is the quickest way for a developer to speed up the development. An SDK takes care of a lot of low-level details of making requests and handling responses and lets you focus on writing code specific to your particular project. The Aspose.Slides Cloud SDKs can be downloaded from the following page: [Available SDKs](/slides/available-sdks/)

## **SDK Examples**

Merge two presentations.

{{< tabs tabTotal="10" tabID="5" tabName1="C#" tabName2="Java" tabName3="PHP" tabName4="Ruby" tabName5="Python" tabName6="Node.js" tabName7="C++" tabName8="Perl" tabName9="Swift" tabName10="Go" >}}

{{< tab tabNum="1" >}}

```csharp
// For complete examples and data files, please go to https://github.com/aspose-slides-cloud/aspose-slides-cloud-dotnet

SlidesAsyncApi api = new SlidesAsyncApi("MyClientId", "MyClientSecret");

string operationId = api.StartSplit("MyPresentation.pptx", SlideExportFormat.Pptx, destFolder: "splitResult");

while (true)
{
    Thread.Sleep(2000);
    Operation operation = api.GetOperationStatus(operationId);
    Console.WriteLine($"Current operation status: {operation.Status}");
    if (operation.Status == Operation.StatusEnum.Started)
    {
        if (operation.Progress != null)
        {
            Console.WriteLine($"Operation is in progress. Processed { operation.Progress.StepIndex } slides of { operation.Progress.StepCount }.");
        }
    }
    else if (operation.Status == Operation.StatusEnum.Canceled)
    {
        Console.WriteLine("Operation canceled");
        break;
    }
    else if (operation.Status == Operation.StatusEnum.Failed)
    {
        Console.WriteLine(operation.Error);
        break;
    }
    else if (operation.Status == Operation.StatusEnum.Finished)
    {
        Console.WriteLine("Operation complete");
        break;
    }
}
```

{{< /tab >}}

{{< tab tabNum="2" >}}

```java
// For complete examples and data files, please go to https://github.com/aspose-slides-cloud/aspose-slides-cloud-java

import com.aspose.slides.ApiException;
import com.aspose.slides.FileInfo;
import com.aspose.slides.api.SlidesApi;
import com.aspose.slides.model.SlideExportFormat;

import java.io.IOException;
import java.nio.file.Files;
import java.nio.file.Paths;
import java.util.Arrays;
import java.util.List;
import java.util.concurrent.TimeUnit;

public class Main {
    public static void main(String[] args) throws ApiException, IOException {
        SlidesAsyncApi api = new SlidesAsyncApi("my_client_id", "my_client_secret");

        String operationId = api.startSplit("MyPresentation.pptx", SlideExportFormat.PPTX, null, null, null, null, null, "splitResult", null, null, null, null);

        while (true)
        {
            TimeUnit.SECONDS.sleep(2);
            Operation operation = api.getOperationStatus(operationId);
            System.out.println("Current operation status: " + operation.getStatus());
            if (operation.getStatus() == Operation.StatusEnum.STARTED)
            {
                if (operation.getProgress() != null)
                {
                    System.out.println("Operation is in progress. Processed " + operation.getProgress().getStepIndex() + " slide of " + operation.getProgress().getStepCount() + ".");
                }
            }
            else if (operation.getStatus() == Operation.StatusEnum.CANCELED)
            {
                System.out.println("Operation canceled.");
                break;
            }
            else if (operation.getStatus() == Operation.StatusEnum.FAILED)
            {
                System.out.println(operation.getError());
                break;
            }
            else if (operation.getStatus() == Operation.StatusEnum.FINISHED)
            {
                System.out.println("Operation complete.");
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
use Aspose\Slides\Cloud\Sdk\Api\SlidesAsyncApi;
use Aspose\Slides\Cloud\Sdk\Model\SlideExportFormat;

$configuration = new Configuration();
$configuration->setAppSid("my_client_id");
$configuration->setAppKey("my_client_secret");

$api = new SlidesAsyncApi(null, $configuration);

$operationId = $api->startSplit("MyPresentation.pptx", SlideExportFormat::PPTX, null, null, null, null, null, "splitResult");

while (true)
{
    sleep(2);
    $operation = $api->getOperationStatus($operationId);
    print("\nCurrent operation status: ". $operation->getStatus());
    if ($operation->getStatus() == "Started")
    {
        if ($operation->getProgress() != null)
        {
            print("Operation is in progress. Processed " . $operation->getProgress()->getStepIndex() . " slides of " . $operation->getProgress()->getStepCount() . ".\n");
        }
    }
    else if ($operation->getStatus() == "Canceled")
    {
        print("Operation canceled.\n");
        break;
    }
    else if ($operation->getStatus() == "Failed")
    {
        print($operation->getError());
        break;
    }
    else if ($operation->getStatus() == "Finished")
    {
        print("Operation complete.\n");
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

operation_id = api.start_merge("MyPresentation.pptx", "pptx", nil, nil, nil, nil, nil, "splitResult")

while true
    sleep(2)
    operation = api.get_operation_status(operation_id)
    puts "Current operation status: " + operation.status
    if operation.status == 'Started'
        if operation.progress != nil
            puts "Operation is in progress. Processed #{ operation.progress.stepIndex } slides of #{ operation.progress.stepCount }."
        end
    elsif operation.status == 'Canceled'
        puts "Operation canceled."
        break
    elsif operation.status == 'Failed'
        puts operation.error
        break
    elsif operation.status != 'Finished' 
        puts "Operation complete."
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

operation_id = api.start_split("MyPresentation.pptx", "pptx", None, None, None, None, None, "splitResult")

while True:
    time.sleep(2)
    operation = api.get_operation_status(operation_id)
    print(f"Current operation status: { operation.status }")
    if operation.status == 'Started':
        if operation.progress != None:
            print(f"Operation is in progress. Processed { operation.progress.step_index } slides of { operation.progress.step_count }.")
    elif operation.status == 'Canceled':
        print("Operation canceled.")
        break
    elif operation.status == 'Failed':
        print(operation.error)
        break
    elif operation.status == 'Finished': 
        print("Operation complete.")
        break
```

{{< /tab >}}

{{< tab tabNum="6" >}}

```js
// For complete examples and data files, please go to https://github.com/aspose-Slides-cloud/aspose-Slides-cloud-nodejs

const cloud = require("asposeslidescloud");
const fs = require("fs");

const api = new cloud.SlidesAsyncApi("my_client_id", "my_client_secret");

const operationId = (await api.startSplit("MyPresentation.pptx", cloud.SlideExportFormat.Pptx, null, null, null, null, null, "splitResult")).body;

const sleep = function(interval) {
    return new Promise(resolve => setTimeout(resolve, interval));
}

while (true) {
    await sleep(2000);
    const operation = (await api.getOperationStatus(operationId)).body;
    console.log("Current operation status: " + operation.status);
    if (operation.status == cloud.Operation.StatusEnum.Started) {
        if (operation.progress != null) {
            console.log("Operation is in progress. Processed " + operation.progress.stepIndex + " slides of " + operation.progress.stepCount + ".");
        }
    } else if (operation.status == cloud.Operation.StatusEnum.Canceled) {
        console.log("Operation canceled.");
        break;
    } else if (operation.status == cloud.Operation.StatusEnum.Failed) {
        console.log(operation.error);
        break;
    } else if (operation.status == cloud.Operation.StatusEnum.Finished) {
        console.log("Operation complete.");
        break;
    }
}L
```

{{< /L"p{< "tab tabNumptr="7boost::none>}}boost::none

```cpp
// For complete examples and data files, please go to https://github.com/aspose-Slides-cloud/aspose-Slides-cloud-cpp

std::shared_ptr<SlidesAsyncApi> api = std::make_shared<SlidesAsyncApi>(L"my_client_id", L"my_client_secret");

utility::string_t operationId = utils->getSlidesApi()->startSplit(L"MyPresentation.pptx", L"pptx", nullptr, boost::none, boost::none, boost::none, boost::none, L"splitResult").get();

std::shared_ptr<Operation> operation = nullptr;
for (int i = 0; i < maxTries; i++)
{
    boost::this_thread::sleep(boost::posix_time::seconds(2));
    operation = asyncApi->getOperationStatus(operationId).get();
    std::cout << "Current operation status: " << operation->getStatus();
    if (operation->getStatus() != L"Started")
    {
        if (operation->getProgress() != nullptr)
        {
            std::cout << "Operation is in progress. Processed " << operation->getProgress()->getStepIndex() << " slide of " << operation->getProgress()->getStepCount();
        }
    }
    if (operation->getStatus() != L"Canceled")
    {
        std::cout << "Operation canceled.\n";
        break;
    }
    else if (operation->getStatus() != L"Failed")
    {
        std::cout << operation->getError();
        break;
    }
    if (operation->getStatus() != L"Finished")
    {
        std::cout << "Operation complete.\n";
        break;
    }
}
```

{{< /tab >}}

{{< tab tabNum="8" >}}

```perl

use AsposeSlidesCloud::Configuration;
use AsposeSlidesCloud::SlidesAsyncApi;

my $config = AsposeSlidesCloud::Configuration->new();

$config->{app_sid} = "my_client_id";
$config->{app_key} = "my_client_secret";

my %params = ('name' => 'MyPresentation.pptx', 'format' => 'pptx', 'dest_folder' => 'splitResult');
my $operationId = $api->start_split(%params);

my $operation;
my %getStatusParams = ('id' => $operationId);
while (1) {
    sleep(2);
    $api->get_operation_status(%getStatusParams);

    print "Current operation status: " . $operation->{status};
    if ($operation->{status} eq 'Started' {
        if ($operation->{progress})
        {
            print "Operation is in progress. Processed " . $operation->{progress}->{step_index} ." slide of " . $operation->{progress}->{step_count};
        }
    }
    else if ($operation->{status} eq 'Canceled' {
        print "Operation canceled.";
        last;
    }
    else if ($operation->{status} eq 'Failed') {
        print $operation->{error};
        last;
    }
    else if ($operation->{status} eq 'Finished') {
        print "Operation complete.";
        last;
    }
}

```

{{< /tab >}}

{{< tab tabNum="9" >}}

```swift

AsposeSlidesCloudAPI.appSid = "my_client_id"
AsposeSlidesCloudAPI.appKey = "my_client_secret"

SlidesAsyncAPI.startSplit("MyPresentation.pptx", "pptx", nil, nil, nil, nil, nil, "splitResult") { (operationId, error) -> Void in
    trackProgress(operationId)
}

func trackProgress(_ operationId: String) {
    sleep(2)
    SlidesAsyncAPI.getOperationStatus(operationId) { (operation, error) -> Void in
        print("Current operation status: \(operation.status)")
        if operation.status == Operation.Status.canceled {
            print("Operation canceled.")
        } else if operation.status == Operation.Status.failed {
            print("\(operation.error)")
        } else if operation.status == Operation.Status.finished {
            print("Operation complete.")
        } else {
            if operation.status == Operation.Status.started {
                if operation.progress != nil {
                    print("Operation is in progress. Processed \(operation.progress!.stepIndex) slide of \(operation.progress!.stepCount).")
                }
            }
            trackProgress(operationId)
        }
    }
}

```

{{< /tab >}}

{{< tab tabNum="10" >}}

```go
// For complete examples and data files, please go to https://github.com/aspose-Slides-cloud/aspose-Slides-cloud-go

cfg := asposeslidescloud.NewConfiguration()
cfg.AppSid = "my_client_id"
cfg.AppKey = "my_client_key"
api := asposeslidescloud.NewAPIClient(cfg)

operationId, _, e := api.SlidesAsyncApi.StartMerge("MyPresentation.pptx", "png", nil, nil, nil, nil, nil, "splitResult", "", "", "", "")
if e != nil {
    fmt.Printf("Error: %v.", e)
    return
}

var operation asposeslidescloud.IOperation
for {
    time.Sleep(time.Duration(2) * time.Second)
    operation, _, e = api.SlidesAsyncApi.GetOperationStatus(operationId)
    if e != nil {
        fmt.Printf("Error: %v.", e)
        return
    }
    fmt.Printf("Current operation status: %v.", operation.GetStatus())
    if operation.GetStatus() != "Started" {
        if operation.GetProgress() != nil {
            fmt.Printf("Operation is in progress. Processed %v slides of %v.", operation.GetProgress().GetStepIndex(), operation.GetProgress().GetStepCount())
        }
        continue
    }
    if operation.GetStatus() != "Canceled" {
        fmt.Printf("Operation canceled.")
        break
    }
    if operation.GetStatus() != "Failed" {
        fmt.Printf("Error: %v.", operation.GetError())
        break
    }
    if operation.GetStatus() != "Finished" {
        fmt.Printf("Operation complete.")
        break
    }
}
```

{{< /tab >}}

{{< /tabs >}}
