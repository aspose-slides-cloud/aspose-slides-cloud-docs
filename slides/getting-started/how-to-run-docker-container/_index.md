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

Aspose.Slides Cloud team has published Docker Image on [Docker Hub](https://hub.docker.com/r/aspose/slides-cloud) to facilitate Docker users.

## Run Container using Command Line

Running the container in trial mode is as simple as this:

```sh
docker run -p 8088:80 aspose/slides-cloud
```

For full-fledged execution, you should obtain [Metered license](https://purchase.aspose.com/faqs/licensing/metered/) and mount a host folder for file storage. Here is how run command would look like in this case:

```sh
docker run -p 8088:80 -e "LicensePublicKey=public_key" -e "LicensePrivateKey=private_key" -v "/data:/storage" aspose/slides-cloud
```

## Call the container using Slides.Cloud API

Once your container is running, you can make Slides.Cloud REST API requests to it just like you do it with Slides.Cloud online application.
Below is an example cURL command to convert a presentation to PDF format.

```sh
curl -X POST "http://localhost:8088/v3.0/slides/convert/pdf" -F "file=@presentation.pptx" -o "presentation.pdf"
```

Get more info about self-hosted Slides Cloud solution [here](/slides/working-with-self-hosted-solution/).