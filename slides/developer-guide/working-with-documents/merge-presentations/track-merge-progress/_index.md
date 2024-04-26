---
title: "Track Merge Progress"
keywords: "PowerPoint, presentation, REST API, Cloud API, merge presentations, merge slides, asynchronous merging"
type: docs
url: /track-merge-progress/
weight: 50
---

## **Introduction**

Aspose.Slides Cloud provides asynchronous merge API that uses an opearation queue under the hood.
This API can be useful for merging large files that can take considerable time. With async api, you need not wait synchronously for the operation to finish. Instead, you get operation Id, which you use to track the operation status.

To merge presentations with async API, you should to the following:

1. Call one of the async merge methods, [SlidesAsyncApi.StartMerge](https://apireference.aspose.cloud/slides/#/MergeDocument/StartMerge) or [SlidesAsyncApi.StartMergeAndSave](https://apireference.aspose.cloud/slides/#/MergeDocument/StartMergeAndSave). The methods return operation Id.

2. Call [SlidesAsyncApi.GetOperationStatus](https://apireference.aspose.cloud/slides/#/Queue/GetOperationStatus) method to check operation status. *Started*, *Enqueued* or *Created* means the operation is not complete. *Finished*, *Failed* or *Canceled* means the operation is finished or aborted.

3. While the operation is in *Started* state you can check *Progress* property to track the merge progress.

4. Once the operation is finished, you can get merge result. For **StartMerge**, use [SlidesAsyncApi.GetOperationResult](https://apireference.aspose.cloud/slides/#/Queue/GetOperationResult) method. For  **StartMergeAndSave**, use [SlidesAsyncApi.DownloadFile](https://reference.aspose.cloud/slides/#/File/DownloadFile) method. The  **path** parameter of **DownloadFile** method should be set to the value that you used as **outPath** parameter for **SlidesAsyncApi.StartMergeAndSave** method. Don't use **GetOperationResult** methods to get the result of operations that have **outPath** parameter.

5. If the operation failed, you can inspect **Error** property of **GetOperationStatus** method for the details.

## **cURL Examples**

Merge two presentations.

{{< tabs tabTotal="2" tabID="1" tabName1="Requests" tabName2="Responses" >}}

{{< tab tabNum="1" >}}

**Start merging the presentations**
```java
curl -X POST "https://api.aspose.cloud/v3.0/slides/async/merge" \
     -H "authorization: Bearer <access_token>" \
     -F "file1=@presentation1.pptx" \
     -F "file2=@presentation2.pptx"
```

**Track merge status**
```java
curl -X GET "https://api.aspose.cloud/v3.0/slides/async/<operation_id>" \
     -H "authorization: Bearer <access_token>"
```

**Download merge result**
```java
curl -X GET "https://api.aspose.cloud/v3.0/slides/async/<operation_id>/result" \
     -H "authorization: Bearer <access_token>"
```

{{< /tab >}}

{{< tab tabNum="2" >}}

**Start merging the presentation**

Operation id

**Track merge status**

```json
{
    "id": "<operation_id>",
	"method": "Merge",
	"status": "Finished",
	"progress": {
	    "description": "Processed presentation2.pptx",
		"stepIndex": 2,
		"stepCount": 2
	},
	"created": "2023-11-30T15:38:48.8103587Z",
	"enqueued": "2023-11-30T15:38:49.5378625Z",
	"started": "2023-11-30T15:38:49.6465388Z",
	"finished": "2023-11-30T15:38:51.0863055Z"
}
```

**Download merge result**

Output file data

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

FileInfo file1 = new FileInfo { Content = File.OpenRead("presentation1.pptx") };
FileInfo file2 = new FileInfo { Content = File.OpenRead("presentation2.pptx") };

string operationId = api.StartMerge(new List<FileInfo> { file1, file2 });

while (true)
{
    Thread.Sleep(2000);
    Operation operation = api.GetOperationStatus(operationId);
    Console.WriteLine($"Current operation status: {operation.Status}");
    if (operation.Status == Operation.StatusEnum.Started)
    {
        if (operation.Progress != null)
        {
            Console.WriteLine($"Operation is in progress. Merged { operation.Progress.StepIndex } of { operation.Progress.StepCount }.");
        }
    }
    else if (operation.Status == Operation.StatusEnum.Canceled)
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
        using Stream mergedFile = File.Create("merged.pptx");
        response.CopyTo(mergedFile);
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
import com.aspose.slides.model.ExportFormat;

import java.io.IOException;
import java.nio.file.Files;
import java.nio.file.Paths;
import java.util.Arrays;
import java.util.List;
import java.util.concurrent.TimeUnit;

public class Main {
    public static void main(String[] args) throws ApiException, IOException {
        SlidesAsyncApi api = new SlidesAsyncApi("my_client_id", "my_client_secret");

        FileInfo file1 = new FileInfo();
        file1.setName("presentation1.pptx");
        file1.setData(Files.readAllBytes(Paths.get("presentation1.pptx")));
        FileInfo file2 = new FileInfo();
        file2.setName("presentation2.pptx");
        file2.setData(Files.readAllBytes(Paths.get("presentation2.pptx")));
        List<FileInfo> files = Arrays.asList(file1, file2);
        String operationId = api.startMerge(files, null, null);

        while (true)
        {
            TimeUnit.SECONDS.sleep(2);
            Operation operation = api.getOperationStatus(operationId);
            System.out.println("Current operation status: " + operation.getStatus());
            if (operation.getStatus() == Operation.StatusEnum.STARTED)
            {
                if (operation.getProgress() != null)
                {
                    System.out.println("Operation is in progress. Merged " + operation.getProgress().getStepIndex() + " of " + operation.getProgress().getStepCount() + ".");
                }
            }
            else if (operation.getStatus() == Operation.StatusEnum.CANCELED)
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
                File pdfFile = api.getOperationResult(operationId);
                System.out.println("The merged document was saved to: " + pdfFile.toPath());
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
use Aspose\Slides\Cloud\Sdk\Model\ExportFormat;

$configuration = new Configuration();
$configuration->setAppSid("my_client_id");
$configuration->setAppKey("my_client_secret");

$api = new SlidesAsyncApi(null, $configuration);

$files = [ fopen("presentation1.pptx", 'r'), fopen("presentation2.pptx", 'r') ];
$operationId = $api->startMerge($files);

while (true)
{
    sleep(2);
    $operation = $api->getOperationStatus($operationId);
    print("\nCurrent operation status: ". $operation->getStatus());
    if ($operation->getStatus() == "Started")
    {
        if ($operation->getProgress() != null)
        {
            print("Operation is in progress. Merged " . $operation->getProgress()->getStepIndex() . " of " . $operation->getProgress()->getStepCount() . ".");
        }
    }
    else if ($operation->getStatus() == "Canceled")
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
        $merged = $api->getOperationResult($operationId);
        print("\nThe merged document was saved to " . $merged->getPathname());
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

source1 = File.binread("presentation1.pptx")
source2 = File.binread("presentation2.pptx")
files = [ source1, source2 ]
operation_id = api.start_merge(files)

while true
    sleep(2)
    operation = api.get_operation_status(operation_id)
    puts "Current operation status: " + operation.status
    if operation.status == 'Started'
        if operation.progress != nil
            puts "Operation is in progress. Merged #{ operation.progress.stepIndex } of #{ operation.progress.stepCount }."
        end
    elsif operation.status == 'Canceled'
        break
    elsif operation.status == 'Failed'
        puts operation.error
        break
    elsif operation.status != 'Finished' 
        merged = api.get_operation_result(operation_id)
        File.binwrite("MyPresentation.pdf", merged)
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

with open("presentation1.pptx", 'rb') as f:
    source1 = f.read()
with open("presentation2.pptx", 'rb') as f:
    source2 = f.read()
files = [ source1, source2 ]
operation_id = api.start_merge(files)

while True:
    time.sleep(2)
    operation = api.get_operation_status(operation_id)
    print(f"Current operation status: { operation.status }")
    if operation.status == 'Started':
        if operation.progress != None:
            print(f"Operation is in progress. Merged { operation.progress.step_index } of { operation.progress.step_count }.")
    elif operation.status == 'Canceled':
        break
    elif operation.status == 'Failed':
        print(operation.error)
        break
    elif operation.status == 'Finished': 
        result_path = api.get_operation_result(operation_id)
        print(f"The merged document was saved to: { result_path }")
        break
```

{{< /tab >}}

{{< tab tabNum="6" >}}

```js
// For complete examples and data files, please go to https://github.com/aspose-Slides-cloud/aspose-Slides-cloud-nodejs

const cloud = require("asposeslidescloud");
const fs = require("fs");

const api = new cloud.SlidesAsyncApi("my_client_id", "my_client_secret");

const files = [fs.createReadStream("presentation1.pptx"), fs.createReadStream("presentation2.pptx")];
const operationId = (await api.startMerge(files)).body;

const sleep = function(interval) {
    return new Promise(resolve => setTimeout(resolve, interval));
}

while (true) {
    await sleep(2000);
    const operation = (await api.getOperationStatus(operationId)).body;
    console.log("Current operation status: " + operation.status);
    if (operation.status == cloud.Operation.StatusEnum.Started) {
        if (operation.progress != null) {
            console.log("Operation is in progress. Merged " + operation.progress.stepIndex + " of " + operation.progress.stepCount + ".");
        }
    } else if (operation.status == cloud.Operation.StatusEnum.Canceled) {
        break;
    } else if (operation.status == cloud.Operation.StatusEnum.Failed) {
        console.log(operation.error);
        break;
    } else if (operation.status == cloud.Operation.StatusEnum.Finished) {
        const merged = await api.getOperationResult(operationId);
        fs.writeFile("merged.pptx", merged.body, (error) => {
            if (error) throw error;
        });
        break;
    }
}
```

{{< /tab >}}

{{< tab tabNum="7" >}}

```cpp
// For complete examples and data files, please go to https://github.com/aspose-Slides-cloud/aspose-Slides-cloud-cpp

std::shared_ptr<SlidesAsyncApi> api = std::make_shared<SlidesAsyncApi>(L"my_client_id", L"my_client_secret");

std::shared_ptr<HttpContent> data1 = std::make_shared<HttpContent>();
data1->setData(std::make_shared<std::ifstream>(L"presentation1.pptx", std::ios::binary));
std::shared_ptr<HttpContent> data2 = std::make_shared<HttpContent>();
data2->setData(std::make_shared<std::ifstream>(L"presentation2.pptx", std::ios::binary));
utility::string_t operationId = utils->getSlidesApi()->startMerge({ data1, data2 }).get();

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
            std::cout << "Operation is in progress. Merged " << operation->getProgress()->getStepIndex() << " of " << operation->getProgress()->getStepCount();
        }
    }
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
        HttpContent mergedContent = slidesApi->getOperationResult(operationId).get();
        std::ofstream mergedStream("merged.pptx", std::ofstream::binary);
        mergedContent.writeTo(mergedStream);
        break;
    }
}
```

{{< /tab >}}

{{< tab tabNum="8" >}}

```perl

use File::Slurp;
use AsposeSlidesCloud::Configuration;
use AsposeSlidesCloud::SlidesAsyncApi;

my $config = AsposeSlidesCloud::Configuration->new();

$config->{app_sid} = "my_client_id";
$config->{app_key} = "my_client_secret";

my $source1 = read_file("presentation1.pptx", { binmode => ':raw' });
my $source2 = read_file("presentation2.pptx", { binmode => ':raw' });
my @files = ( $source1, $source2 );
my %params = ('files' => \@files);
my $operationId = $api->start_merge(%params);

my $operation;
my %getStatusParams = ('id' => $operationId);
while (1) {
    sleep(2);
    $api->get_operation_status(%getStatusParams);

    print "Current operation status: " . $operation->{status};
    if ($operation->{status} eq 'Started' {
        if ($operation->{progress})
        {
            print "Operation is in progress. Merged " . $operation->{progress}->{step_index} ." of " . $operation->{progress}->{step_count};
        }
    }
    else if ($operation->{status} eq 'Canceled' {
        last;
    }
    else if ($operation->{status} eq 'Failed') {
        print $operation->{error};
        last;
    }
    else if ($operation->{status} eq 'Finished') {
        my $result = $api->get_operation_result(%params);
        my $merged = "Merged.pptx";
        open my $fh, '>', $merged;
        binmode $fh;
        print $fh $result;
        close $fh;
        last;
    }
}

```

{{< /tab >}}

{{< tab tabNum="9" >}}

```swift

AsposeSlidesCloudAPI.appSid = "my_client_id"
AsposeSlidesCloudAPI.appKey = "my_client_secret"

let source1 = FileManager.default.contents(atPath: "presentation1.pptx")
let source2 = FileManager.default.contents(atPath: "presentation2.pptx")
let files = [ source1!, source2! ]
SlidesAsyncAPI.startMerge(files) { (operationId, error) -> Void in
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
            SlidesAsyncAPI.getOperationResult(operationId) { (merged, error) -> Void in
                do {
                    let url = URL(fileURLWithPath: "Merged.pptx")
                    try (merged as! Data).write(to: url)
                } catch (error) {
                    print("Error saving file: \(error).")
                }
            }
        } else {
            if operation.status == Operation.Status.started {
                if operation.progress != nil {
                    print("Operation is in progress. Merged \(operation.progress!.stepIndex) of \(operation.progress!.stepCount).")
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

source1, e := ioutil.ReadFile("presentation1.pptx")
if e != nil {
    fmt.Printf("Error: %v.", e)
    return
}
source2, e := ioutil.ReadFile("presentation2.pptx")
if e != nil {
    fmt.Printf("Error: %v.", e)
    return
}

operationId, _, e := api.SlidesAsyncApi.StartMerge([][]byte{source1, source2}, nil, "")
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
            fmt.Printf("Operation is in progress. Merged %v of %v.", operation.GetProgress().GetStepIndex(), operation.GetProgress().GetStepCount())
        }
        continue
    }
    if operation.GetStatus() != "Canceled" {
        break
    }
    if operation.GetStatus() != "Failed" {
        fmt.Printf("Error: %v.", operation.GetError())
        break
    }
    if operation.GetStatus() != "Finished" {
        merged, _, e := api.SlidesAsyncApi.GetOperationResult(operationId)
        if e != nil {
            fmt.Printf("Error: %v.", operation.GetError())
            return
        }
        fmt.Printf("The merged file was saved to %v.", merged.Name())
        break
    }
}
```

{{< /tab >}}

{{< /tabs >}}
