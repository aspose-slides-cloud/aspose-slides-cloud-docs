---
title: "Features Not Available In Self-Hosted Solution"
type: docs
url: /features-not-available-in-self-hosted-solution/
weight: 30
---

The API available in the [Docker Hub](https://hub.docker.com/r/aspose/slides-cloud) version of the Slides Cloud application is basically the same as that at api.aspose.cloud.
However, some features are available only at api.aspose.cloud. They are,

* [Asynchronous API](/slides/track-conversion-status/). The **/slides/async/...** API methods are not served by the container.
* multiple storages are not supported. The default storage is always used. This may be a local file storage, or a third-party cloud storage, depending on the way storage is [configured](/slides/using-storage-with-self-hosted-solution/) for the image. But it is always one single storage. Therefore, *storage* parameter is ignored by the API.
* file versioning is not supported. *version* parameter for storage methods is ignored.
* [StorageExists](https://reference.aspose.cloud/slides/#/Storage/StorageExists) method is not supported.
* the Windows fonts are not available, as it is a linux image. As a partial reparation, you can mount **fonts** volume with custom fonts you nedd for your app.

In the dockerhub version of the application, you can use [GetApiInfo](https://reference.aspose.cloud/slides/#/General/GetApiInfo) method to retrieve the metered consumption info. You can check **ApiInfo** class that contains **MeteredConsumptionCredit** and **MeteredConsumptionQuantity** properties.