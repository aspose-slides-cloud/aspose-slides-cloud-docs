---
title: "Using SDKs With Self-Hosted Solution"
keywords:
- PowerPoint
- presentation
- REST API
- cloud API
- self-hosted solution
type: docs
url: /using-sdks-with-self-hosted-solution/
weight: 50
---

You can use Slides Cloud SDKs with the self-hosted Slides Cloud solution.
Check [Available SDKs](/slides/available-sdks/) to learn how to add an SDK to your project.

The way you use SDKs with self-hosted solution is no different from the way it is used with api.aspose.cloud, not methioning these points:

* You should specify the base url of the Slides API at the initialization stage (if you don't, api.aspose.cloud will be used by default)
* You need not provide ClientId and ClientSecret (unless you use [authorization](/slides/authorizing-requests-to-self-hosted-solution) with your application)
* Some methods and parameters are unavailable. See the [list of unavailable features](/slides/features-not-available-in-self-hosted-solution).

Below is an example of conversion a presentation to PDF using .NET SDK.

```csharp
Configuration config = new Configuration();
config.ApiBaseUrl = "http://localhost:8088";
SlidesApi api = new SlidesApi(config);
Stream file = File.OpenRead("presentation.pptx");
PostSlidesConvertRequest request = new PostSlidesConvertRequest { Format = ExportFormat.Pdf, Document = file };
Stream response = api.PostSlidesConvert(request);
response.CopyTo(File.Create("presentation.pdf"));
```

If you use [authorization](/slides/authorizing-requests-to-self-hosted-solution), you also set ClientId and ClientSecret:

```csharp
Configuration config = new Configuration();
config.ApiBaseUrl = "http://localhost:8088";
config.ClientId = "MyClientId";
config.ClientSecret = "MyClientSecret";
SlidesApi api = new SlidesApi(config);
... // My API requests
```
