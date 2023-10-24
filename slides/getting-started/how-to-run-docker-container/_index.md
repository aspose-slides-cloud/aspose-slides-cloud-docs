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

### Authorization

By default (when ClientId and ClientSecret are not specified) the requests are not authorized, so anyone who has access to the container has access to the API hosted there.

You may specify ClientId and ClientSecret invented by you as environment parameters for the container (not to be mixed with license public & private keys that you get from Aspose).

```JAVA
docker run -p 8088:80 -e "LicensePublicKey=public_key" -e "LicensePrivateKey=private_key" -e "ClientId=MyClientId" -e "ClientSecret=MyClientSecret" -v "/data:/storage" aspose/slides-cloud
```

When you start the container with ClientId and ClientSecret set, you must get auth token using /connect/token URL to do API requests.

```JAVA
curl -X POST "http://localhost:8088/connect/token" -d "grant_type=client_credentials&client_id=MyClientId&client_secret=MyClientSecret"
```

Then you provide the token in the Authorizatrion header for API requests just the way you authenticate cloud requests at api.aspose.cloud.

### Use SDKs with the container

You can use SDKs with your docker container. You should specify the base url (if you don't, api.aspose.cloud will be used by default) and you need not provide ClientId and ClientSecret (unless you specify those parameters in docker run command).
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

If you use [authorization](#authorization), you also set ClientId and ClientSecret:

```csharp
Configuration config = new Configuration();
config.ApiBaseUrl = "http://localhost:8088";
config.ClientId = "MyClientId";
config.ClientSecret = "MyClientSecret";
SlidesApi api = new SlidesApi(config);
... // My API requests
```

### Using Cloud Storages

Instead of storing files in a host computer's folder, you can use a third-party Cloud storage with your docker container.

#### Use Google Cloud Storage

To use Google Cloud storage, specify path to the credentials file and the bucket name in GOOGLE_APPLICATION_CREDENTIALS and GOOGLE_STORAGE_BUCKET enviromnent variables.

```JAVA
docker run -p 8088:80 -e "LicensePublicKey=public_key" -e "LicensePrivateKey=private_key" \
-e "GOOGLE_APPLICATION_CREDENTIALS=/creds/myCreds.json" -e "GOOGLE_STORAGE_BUCKET=myBucket" \
-v "/home/user/google-cloud-creds:/creds" \
aspose/slides-cloud
```

#### Use AWS S3

To use AWS S3, specify credentials and the bucket name in AWSS3_ACCESS_KEY, AWSS3_SECRET_KEY, AWSS3_REGION and AWSS3_BUCKET environment variables.

```JAVA
docker run -p 8088:80 -e "LicensePublicKey=public_key" -e "LicensePrivateKey=private_key" \
-e "AWSS3_ACCESS_KEY=myS3AccessKey" -e "AWSS3_SECRET_KEY=myS3SecretKey" -e "AWSS3_REGION=us-east-2" -e "AWSS3_BUCKET=myBucket" \
aspose/slides-cloud
```

To use an AWS S3 endpoint, specify its URL in AWSS3_ENDPOINT environment variable.

```JAVA
docker run -p 8088:80 -e "LicensePublicKey=public_key" -e "LicensePrivateKey=private_key" \
-e "AWSS3_ACCESS_KEY=myS3AccessKey" -e "AWSS3_SECRET_KEY=myS3SecretKey" -e "AWSS3_ENDPOINT=http://min.io:9000" -e "AWSS3_BUCKET=myBucket" \
aspose/slides-cloud
```
