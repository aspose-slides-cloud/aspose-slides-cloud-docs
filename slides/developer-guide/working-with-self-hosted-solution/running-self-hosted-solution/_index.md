---
title: "Running Self-Hosted Solution"
keywords:
- PowerPoint
- presentation
- REST API
- cloud API
- docker
- self-hosted solution
type: docs
url: /running-self-hosted-solution/
weight: 10
---

**Docker** technology is designed to automate the deployment of applications by using lightweight containers.
Developers can use **Docker Container** to wrap the application with all of its libraries and dependencies and deploy everything as a single package.

Aspose.Slides Cloud team has published Docker Image on [Docker Hub](https://hub.docker.com/r/aspose/slides-cloud) to facilitate Docker users.

You can host your own Slides Cloud API instance using this image. It offers most functionality available at *api.aspose.cloud*, though the solutions differ in [some aspects](/slides/features-not-available-in-self-hosted-solution/).

To use Slides Cloud docker image, you should obtain [Metered license](https://purchase.aspose.com/faqs/licensing/metered/). Without license, the application will run in trial mode.

## Run Container using Command Line

You can use the following command to run the container after pulling it from [Docker Hub](https://href.li/?https://hub.docker.com/r/aspose/slides-cloud).

```sh
docker run -p 8088:80 -e "LicensePublicKey=public_key" -e "LicensePrivateKey=private_key" -v "/data:/storage" aspose/slides-cloud
```

In the example above, the *data* folder of the host computer is used as file storage. There are other options to [use storage with self-hosted solution](/slides/using-storage-with-self-hosted-solution/).

## Configuration for Docker-Compose Tool

You can write the following configuration in your yaml file for Docker-Compose tool:

```sh
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

See the list of available configuration options [here](/slides/configuring-self-hosted-solution/).

## Call the container using Slides.Cloud API

Once your container is running, you can make Slides.Cloud REST API requests to it just like you do it with Slides.Cloud online application.
Below is an example cURL command to convert a presentation to PDF format.

```sh
curl -X POST "http://localhost:8088/v3.0/slides/convert/pdf" --data-binary "@presentation.pptx" -H "Content-Type: application/octet-stream" -o "presentation.pdf"
```
