---
title: "Using Storage With Self-Hosted Solution"
keywords: "PowerPoint, presentation, REST API, Cloud API, self-hosted solution, storage, file storage, cloud storage"
type: docs
url: /using-storage-with-self-hosted-solution/
weight: 60
---

Slides.Cloud self-hosted solution does not support multiple storages. The application uses one default storage. Therefore, *storage* parameter for API methods is redundant. If you specify it, it will be just ignored.

However, you can choose the kind of the storage used with your Cloud application.

By default, Cloud data is stored in the *storage* folder inside the container, which is not recommended. The appropriate way is one of the options below.

## Using Host Storage

You can use a folder in the host computer for the storage. Mount it as *storage* volume in your container. For example, to store Cloud data in *data* folder of the host, run the container using the command like as follows:

```sh
docker run -p 8088:80 -e "LicensePublicKey=public_key" -e "LicensePrivateKey=private_key" -v "/data:/storage" aspose/slides-cloud
```

If you wish to use another name for the storage folder, you can use *StorageFolder* environment variable, like as follows:

```sh
docker run -p 8088:80 -e "LicensePublicKey=public_key" -e "LicensePrivateKey=private_key" -e "StorageFolder=files" -v "/data:/files" aspose/slides-cloud
```

## Using Google Cloud Storage

To use Google Cloud storage, specify path to the credentials file and the bucket name in GOOGLE_APPLICATION_CREDENTIALS and GOOGLE_STORAGE_BUCKET enviromnent variables.

```sh
docker run -p 8088:80 -e "LicensePublicKey=public_key" -e "LicensePrivateKey=private_key" \
-e "GOOGLE_APPLICATION_CREDENTIALS=/creds/myCreds.json" -e "GOOGLE_STORAGE_BUCKET=myBucket" \
-v "/home/user/google-cloud-creds:/creds" \
aspose/slides-cloud
```

The example implies that */home/user/google-cloud-creds* folder in the host computer contains *myCreds.json* file with credentials obtained from Google Cloud.

## Using AWS S3

To use AWS S3, specify credentials and the bucket name in AWSS3_ACCESS_KEY, AWSS3_SECRET_KEY, AWSS3_REGION and AWSS3_BUCKET environment variables.

```sh
docker run -p 8088:80 -e "LicensePublicKey=public_key" -e "LicensePrivateKey=private_key" \
-e "AWSS3_ACCESS_KEY=myS3AccessKey" -e "AWSS3_SECRET_KEY=myS3SecretKey" -e "AWSS3_REGION=us-east-2" -e "AWSS3_BUCKET=myBucket" \
aspose/slides-cloud
```

To use an AWS S3 endpoint, specify its URL in AWSS3_ENDPOINT environment variable.

```sh
docker run -p 8088:80 -e "LicensePublicKey=public_key" -e "LicensePrivateKey=private_key" \
-e "AWSS3_ACCESS_KEY=myS3AccessKey" -e "AWSS3_SECRET_KEY=myS3SecretKey" -e "AWSS3_ENDPOINT=http://min.io:9000" -e "AWSS3_BUCKET=myBucket" \
aspose/slides-cloud
```
