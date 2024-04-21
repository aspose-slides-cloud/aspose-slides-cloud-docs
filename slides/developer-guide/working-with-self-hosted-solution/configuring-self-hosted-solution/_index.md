---
title: "Configuring Self-Hosted Solution"
keywords: "PowerPoint, presentation, REST API, Cloud API, docker, self-hosted solution"
type: docs
url: /configuring-self-hosted-solution/
weight: 20
---

You can configure you Aspose.Slides Cloud [Docker Container](https://hub.docker.com/r/aspose/slides-cloud) with a number of volumes and environment variables. None of them are required to run the container, though some are necessary for the API to be fully-functional. Below is the complete list.

## Volumes

**storage** volume is used to mount a file storage on the host computer. Unless you [use a third-party Cloud storage](/slides/using-storage-with-self-hosted-solution/), you are recommended to mount this volume.

**fonts** volume is used to install custom fonts for the container. Copy any additional fonts you need to a folder on the host and mount this folder as **fonts** volume.

## Environment Variables

**LicensePublicKey** and **LicensePrivateKey** variables are used to specify your Metered license keys. If those variables are not specified the application is executed in trial mode.

**ApiBaseUrl** variable is used to generate URIs of resources returned by the API methods (*SelfUri* field and other fields of the kind). The default value is *https://api.aspose.cloud*. This field has no effect on the actual URL that is being used by your application, but you may wish to adjust its value so that the URLs contained in JSON responses correspond to the real URL.

**StorageRootFolder** variable contains the path to the local file storage. It defaults to */storage*. If you change its value, you need to change the name of *storage* volume accordingly.

**FontsRootFolder** variable contains the path to custom fonts folder. It defaults to */fonts*. If you change its value, you need to change the name of *fonts* volume accordingly.

**MaxRequestBodySize** variable contains the upper request body size limit. It defaults to *int.MaxValue*. Set its value if you wish to limit request size.

**MultipartBodyLengthLimit** variable contains the upper multipart body size limit. It defaults to *int.MaxValue*. Set its value if you wish to limit multipart body size.

**FFMpegTimeout** variable contains timeout for ffmpeg calls, in milliseconds. The default value is 60000, i.e. one minute. Ffmpeg is used with [Converting presentations to video](/slides/convert-a-presentation-to-a-video/).

**ClientId** and **ClientSecret** variables can be used used to enable JWT authentication for your application. By default, those variables are not set, and the authentication is disabled. You may set those variables to whatever you like, and if they set, the client requests to your app will need to be authorized with JWT token. See more about enabling authorization [here](/slides/authorizing-requests-to-self-hosted-solution/).

**AuthTokenSigningKey** variable can be used to set the value for signing auth token. It has a default value, which is not shared with the clients. You may wish to override it.

**AWSS3_ACCESS_KEY**, **AWSS3_SECRET_KEY**, **AWSS3_REGION** and **AWSS3_ENDPOINT** variables are used to set AWS S3 instead of local file storage. See more info [here](/slides/using-storage-with-self-hosted-solution/#using-aws-s3).

**GOOGLE_APPLICATION_CREDENTIALS** and **GOOGLE_STORAGE_BUCKET** variables are used to set Google Cloud instead of local file storage. See more info [here](/slides/using-storage-with-self-hosted-solution/#using-google-cloud-storage).
