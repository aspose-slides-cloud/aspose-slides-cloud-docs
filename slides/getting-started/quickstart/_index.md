---
title: "Quickstart"
keywords:
- PowerPoint
- presentation
- REST API
- cloud API
- quickstart
- account
- cloud account
- account settings
- dashboard
- API reference
- SDK
type: docs
url: /quickstart/
weight: 20
---

To use Aspose.Slides Cloud, you need to have an Aspose Cloud account.

## Create an Aspose Cloud Account

To create an Aspose Cloud account, go to [Aspose Cloud Dashboard](https://dashboard.aspose.cloud/).
You can sign in with your Google or Microsoft account, or create an account using **Sign up** button and providing the required information.

Once you have provided all the required details, you will be able to access the Dashboard.
You can adjust your [Account Settings](https://id.containerize.com/admin/) by selecting **Account Settings** from the top right menu.

Now you have an Aspose Cloud account. The next step is to create an application.

## Create an Application

To create an application,

1. At the [Dashboard](https://dashboard.aspose.cloud/), go to [Applications](https://dashboard.aspose.cloud/applications) page by selecting **Applications** tab in the left-side menu.
2. Click **Create New Application** button.
3. Enter a name for your application, select your default storage for files, and click **Save** button.
4. Now, at the bottom of the Application page, you can see a pane for the application you have just created. Click it to see the app details, including **ClientId** and **ClientSecret**.

Now you are ready to make Cloud API calls.

## Make an API Request

You can see and test the available Aspose.Slides Cloud API methods using the [API Reference](https://apireference.aspose.cloud/slides).
You may like to make a simple API request to check your new Cloud account. Below are the steps to create an empty presentation using the API.

1. Open the [API Reference](https://apireference.aspose.cloud/slides).
2. Click **Authorize**, enter Client Id and Client Secret for your application and click **Close**.
3. Select a method. We will select `CreatePresentation` method - click the topmost **Post** button in the **Document** section.
4. Click **Try it out**.
5. Fill in the parameters. Enter a name for the new presentation, e.g. "MyPresentation.pptx".
6. Click **Execute** button.

Wait for a while. You should see request and response details. The successful response code for the request above is 201.

After the method is executed, a new presentation file is created and available on the storage.

## Manage Your Storage Files

You can go to [Files](https://dashboard.aspose.cloud/files) page by selecting the **Files** tab in the left-side dashboard menu.
If you made the API request described above, you should be able to see the newly created file there. You can download, upload, copy, move or delete files at the Files page. You can also do those using [Cloud API](https://apireference.aspose.cloud/slides/#/File).

## Use SDK

You can use Cloud API in your applications with [Aspose.Slide Cloud SDKs](https://products.aspose.cloud/slides/family). They are available for most popular programming languages. Choose the SDK for the language you use and install it using the corresponding package manager.
Making requests to Cloud API with SDK is as simple as calling `SlidesApi` class methods.

All the SDK sources are hosted on [GitHub](https://github.com/aspose-slides-cloud/).

## Check the Documentation

Use the [Developer Guide](https://docs.aspose.cloud/slides/developer-guide/) for details and examples of usage of the Cloud API.

## Ask for Support

Feel free to share your problems and ask questions on our [Cloud Forums](http://forum.aspose.cloud/). Aspose technical support team is ready to help you. Have a note that Aspose does not provide technical support over the phone. Phone support is available only for sales and purchase questions.
