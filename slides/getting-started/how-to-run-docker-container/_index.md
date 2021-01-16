---
title: "How to Run Docker Container"
second_title: "Aspose Slides Cloud Docs"
type: docs
url: /getting-started/how-to-run-docker-container/
aliases: [/how-to-run-docker-container/]
description: "How to run Docker container"
weight: 100
---

**Docker** technology is designed to automate the deployment of applications by using lightweight containers. 
Developers can use **Docker Container** to wrap the application with all of its libraries and dependencies and deploy everything as a single package.

Aspose.Slides Cloud team has published Docker Container on [Docker Hub](https://hub.docker.com/r/aspose/slides-cloud) to facilitate Docker users.

## Container Configuration

### Required Volumes

|Mount path in container|Description|
| :- | :- |
|/storage|File storage folder|

### Parameters

|Name|Description|
| :- | :- |
|LicensePublicKey|Public key of the license|
|LicensePrivateKey|Private key of the license|
|ClientId|Username|
|ClientSecret|Password|

If "License" parameters are omitted, the app will work in trial mode. If "ClientId" parameter is set, each request requires "Authorization" header (JWT authentication). 
The URL to obtain the token is "/connect/token".

### Run Container using Command Line

You can use the following command to run the container after pulling it from [Docker Hub](https://href.li/?https://hub.docker.com/r/aspose/slides-cloud).

```JAVA
docker run -p 8088:80 -e "LicensePublicKey=public_key" -e "LicensePrivateKey=private_key" -v "/data:/storage" aspose/slides-cloud
```

### Configuration for Docker-Compose Tool

You can write the following configuration in your yaml file for Docker-Compose tool:

```JAVA
AsposeSlidesCloud:
      image: aspose/slides-cloud
      ports: ["8088:80"]
      volumes: [
        "./storage:/storage",
      ]
      environment:
        "ClientId": "User"
        "ClientSecret": "Password"
        "LicensePublicKey": "public_key"
        "LicensePrivateKey": "private_key"
```

### Call the container using Slides.Cloud API

Once your container is running, you can make Slides.Cloud REST API requests to it just like you do it with Slides.Cloud online application.
Below is an example cURL command to convert a presentation to PDF format.

```JAVA
curl -X POST "http://localhost:8088/v3.0/slides/convert/pdf" --data-binary "@presentation.pptx" -H "Content-Type: application/octet-stream" -o "presentation.pdf"
```

### Use SDKs with the container

You can use SDKs with your docker container. You should specify the base url (if you don't, api.aspose.cloud will be used by default) and you need not provide ClientId and ClientSecret (unless you specify those parameters in docker run command).
Below is an example of conversion a presentation to PDF using .NET SDK.

```scharp
Configuration config = new Configuration();
config.ApiBaseUrl = "http://localhost:8088";
SlidesApi api = new SlidesApi(config);
Stream file = File.OpenRead("presentation.pptx");
PostSlidesConvertRequest request = new PostSlidesConvertRequest { Format = ExportFormat.Pdf, Document = file };
Stream response = api.PostSlidesConvert(request);
response.CopyTo(File.Create("presentation.pdf"));
```
