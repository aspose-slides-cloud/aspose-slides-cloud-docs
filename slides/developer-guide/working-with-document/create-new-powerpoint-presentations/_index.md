---
title: "Create new PowerPoint Presentations"
type: docs
url: /create-new-powerpoint-presentations/
weight: 20
---

## **Introduction**
This example allows you to create a new empty presentation from scratch using Aspose.Slides Cloud API in your applications. Aspose.Slides Cloud API lets you create a new presentation from the following resources 

## **Create a new presentation.**
### **Resource URI**
```
/slides/{file-name}
```
#### **Request Parameters**
| **Parameter Name** | **HTTP Method(s)** | **Type** | **Optional/Required** | **Description** |
| :- | :- | :- | :- | :- |
|format|GET|string|Optional|Return the presentation in the specified format.|
|password|POST|string|Optional|Password to create an encrypted presentation |
|inputPassword|POST|string|Optional|Password to open the presentation that is passed in request body |
|folder|GET/POST|string|Optional|Presentation folder |
|storage|POST|string|Optional|Presentation storage|
|fontsFolder|GET|string|Optional|Storage folder containing custom fonts to be used to save the presentation in a specified format. |

*In case of Amazon S3 storage folder path starts with Amazon S3 bucket name.*

#### **HTTP GET**
Returns a JSON/XML representation of the presentation, unless a specific format is provided in which case it will return the presentation in the specified format (either source presentation, converted presentation or rendered presentation).

The different representations of a Presentation are basically the formats to which the presentation can be converted. So to achieve a conversion all a user has to do is use one of these links.

##### **Example**
```
GET https://api.aspose.cloud/v3.0/slides/myPresentation.pptx?folder=myFolder
```

##### **Response:**
Full resource representation:
**JSON**
```
{
    "documentProperties": {
        "href": "https://api.aspose.cloud/v3.0/slides/myPresentation.pptx/documentProperties?folder=myFolder",
        "relation": "self"
    },
    "slides": {
        "href": "https://api.aspose.cloud/v3.0/slides/myPresentation.pptx/slides?folder=myFolder",
        "relation": "self"
    },
    "images": {
        "href": "https://api.aspose.cloud/v3.0/slides/myPresentation.pptx/images?folder=myFolder",
        "relation": "self"
    },
    "layoutSlides": {
        "href": "https://api.aspose.cloud/v3.0/slides/myPresentation.pptx/layoutSlides?folder=myFolder",
        "relation": "self"
    },
    "masterSlides": {
        "href": "https://api.aspose.cloud/v3.0/slides/myPresentation.pptx/masterSlides?folder=myFolder",
        "relation": "self"
    },
    "selfUri": {
        "href": "https://api.aspose.cloud/v3.0/slides/myPresentation.pptx?folder=myFolder",
        "relation": "self"
    },
    "alternateLinks": [
        {
            "href": "https://api.aspose.cloud/v3.0/slides/myPresentation.pptx/odp?folder=myFolder",
            "relation": "alternate",
            "linkType": "application/vnd.oasis.opendocument.presentation",
            "title":"Download as Odp"
        },
        {
            "href": "https://api.aspose.cloud/v3.0/slides/myPresentation.pptx/pptx?folder=myFolder",
            "relation": "alternate",
            "linkType": "application/vnd.openxmlformats-officedocument.presentationml.presentation",
            "title":"Download as Pptx"
        },
        {
            "href": "https://api.aspose.cloud/v3.0/slides/myPresentation.pptx/pdf?folder=myFolder",
            "relation": "alternate",
            "linkType": "application/pdf",
            "title":"Download as Pdf"
        },
        {
            "href": "https://api.aspose.cloud/v3.0/slides/myPresentation.pptx/tiff?folder=myFolder",
            "relation": "alternate",
            "linkType": "image/tiff",
            "title":"Download as Tiff"
        },
        {
            "href": "https://api.aspose.cloud/v3.0/slides/myPresentation.pptx/xps?folder=myFolder",
            "relation": "alternate",
            "linkType": "application/vnd.ms-xpsdocument",
            "title":"Download as Xps"
        },
        {
            "href": "https://api.aspose.cloud/v3.0/slides/myPresentation.pptx/pps?folder=myFolder",
            "relation": "alternate",
            "linkType": "application/vnd.ms-powerpoint",
            "title":"Download as Pps"
        },
        {
            "href": "https://api.aspose.cloud/v3.0/slides/myPresentation.pptx/ppsx?folder=myFolder",
            "relation": "alternate",
            "linkType": "application/vnd.openxmlformats-officedocument.presentationml.slideshow",
            "title":"Download as Ppsx"
        },
        {
            "href": "https://api.aspose.cloud/v3.0/slides/myPresentation.pptx/pptm?folder=myFolder",
            "relation": "alternate",
            "linkType": "application/vnd.ms-powerpoint.presentation.macroEnabled.12",
            "title":"Download as Pptm"
        },
        {
            "href": "https://api.aspose.cloud/v3.0/slides/myPresentation.pptx/ppsm?folder=myFolder",
            "relation": "alternate",
            "linkType": "application/vnd.ms-powerpoint.slideshow.macroEnabled.12",
            "title":"Download as Ppsm"
        },
        {
            "href": "https://api.aspose.cloud/v3.0/slides/myPresentation.pptx/potx?folder=myFolder",
            "relation": "alternate",
            "linkType": "application/vnd.openxmlformats-officedocument.presentationml.template",
            "title":"Download as Potx"
        },
        {
            "href": "https://api.aspose.cloud/v3.0/slides/myPresentation.pptx/potm?folder=myFolder",
            "relation": "alternate",
            "linkType": "application/vnd.ms-powerpoint.template.macroEnabled.12",
            "title":"Download as Potm"
        },
        {
            "href": "https://api.aspose.cloud/v3.0/slides/myPresentation.pptx/otp?folder=myFolder",
            "relation": "alternate",
            "linkType": "application/vnd.oasis.opendocument.presentation-template",
            "title":"Download as Otp"
        },
        {
            "href": "https://api.aspose.cloud/v3.0/slides/myPresentation.pptx/html?folder=myFolder",
            "relation": "alternate",
            "linkType": "text/html",
            "title":"Download as Html"
        }
    ]
}
```

**XML**
```
<?xml version="1.0" encoding="UTF-8"?>
<Document xmlns:xsd="http://www.w3.org/2001/XMLSchema" xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance">
   <link href="https://api.aspose.cloud/v3.0/slides/myPresentation.pptx?folder=myFolder" rel="self" />
   <link href="https://api.aspose.cloud/v3.0/slides/myPresentation.pptx/odp?folder=myFolder" rel="alternate" type="application/vnd.oasis.opendocument.presentation" title="Download as Odp" />
   <link href="https://api.aspose.cloud/v3.0/slides/myPresentation.pptx/pptx?folder=myFolder" rel="alternate" type="application/vnd.openxmlformats-officedocument.presentationml.presentation" title="Download as Pptx" />
   <link href="https://api.aspose.cloud/v3.0/slides/myPresentation.pptx/pdf?folder=myFolder" rel="alternate" type="application/pdf" title="Download as Pdf" />
   <link href="https://api.aspose.cloud/v3.0/slides/myPresentation.pptx/tiff?folder=myFolder" rel="alternate" type="image/tiff" title="Download as Tiff" />
   <link href="https://api.aspose.cloud/v3.0/slides/myPresentation.pptx/xps?folder=myFolder" rel="alternate" type="application/vnd.ms-xpsdocument" title="Download as Xps" />
   <link href="https://api.aspose.cloud/v3.0/slides/myPresentation.pptx/pps?folder=myFolder" rel="alternate" type="application/vnd.ms-powerpoint" title="Download as Pps" />
   <link href="https://api.aspose.cloud/v3.0/slides/myPresentation.pptx/ppsx?folder=myFolder" rel="alternate" type="application/vnd.openxmlformats-officedocument.presentationml.slideshow" title="Download as Ppsx" />
   <link href="https://api.aspose.cloud/v3.0/slides/myPresentation.pptx/pptm?folder=myFolder" rel="alternate" type="application/vnd.ms-powerpoint.presentation.macroEnabled.12" title="Download as Pptm" />
   <link href="https://api.aspose.cloud/v3.0/slides/myPresentation.pptx/ppsm?folder=myFolder" rel="alternate" type="application/vnd.ms-powerpoint.slideshow.macroEnabled.12" title="Download as Ppsm" />
   <link href="https://api.aspose.cloud/v3.0/slides/myPresentation.pptx/potx?folder=myFolder" rel="alternate" type="application/vnd.openxmlformats-officedocument.presentationml.template" title="Download as Potx" />
   <link href="https://api.aspose.cloud/v3.0/slides/myPresentation.pptx/potm?folder=myFolder" rel="alternate" type="application/vnd.ms-powerpoint.template.macroEnabled.12" title="Download as Potm" />
   <link href="https://api.aspose.cloud/v3.0/slides/myPresentation.pptx/otp?folder=myFolder" rel="alternate" type="application/vnd.oasis.opendocument.presentation-template" title="Download as Otp" />
   <link href="https://api.aspose.cloud/v3.0/slides/myPresentation.pptx/html?folder=myFolder" rel="alternate" type="text/html" title="Download as Html" />
   <DocumentProperties href="https://api.aspose.cloud/v3.0/slides/myPresentation.pptx/documentProperties?folder=myFolder" rel="self" />
   <Slides href="https://api.aspose.cloud/v3.0/slides/myPresentation.pptx/slides?folder=myFolder" rel="self" />
   <Images href="https://api.aspose.cloud/v3.0/slides/myPresentation.pptx/images?folder=myFolder" rel="self" />
   <LayoutSlides href="https://api.aspose.cloud/v3.0/slides/myPresentation.pptx/layoutSlides?folder=myFolder" rel="self" />
   <MasterSlides href="https://api.aspose.cloud/v3.0/slides/myPresentation.pptx/masterSlides?folder=myFolder" rel="self" />
</Document>
```

##### **C# SDK Code:**
```csharp
SlidesApi api = new SlidesApi("MyAppSid", "MyAppKey");
GetSlidesDocumentRequest request = new GetSlidesDocumentRequest { Name = "MyPresentation.pptx", Folder = "MyFolder" };
Document response = api.GetSlidesDocument(request);
Console.WriteLine(response.SelfUri.Href); //https://api.aspose.cloud/v3.0/slides/MyPresentation.pptx?folder=MyFolder
```

#### **HTTP POST**
Create a new presentation. File format will be determined based on extension.

To create Office 97-2003 compatible presentation file name must have ppt or ppx extension. For Office 2007-2010 compatible presentation (aka OpenXML) use Pptx, Pptm, Potx, Potm, Ppsx or Ppsm file extensions.

You can create an empty presentation or provide a source document in request body.

##### **Example 1.**
Creates empty Sales.pptx presentation.
```
POST https://api.aspose.cloud/v3.0/slides/Sales.pptx 
```

###### **Response:**
Full resource representation.

###### **C# SDK Code:**
```csharp
SlidesApi api = new SlidesApi("MyAppSid", "MyAppKey");
PostSlidesDocumentRequest request = new PostSlidesDocumentRequest { Name = "Sales.pptx", Folder = "MyFolder" };
Document response = api.PostSlidesDocument(request);
Console.WriteLine(response.SelfUri.Href); //https://api.aspose.cloud/v3.0/slides/Sales.pptx?folder=MyFolder
```

##### **Example 2.**
Creates Sales.pptx presentation from the presentation in request body.
```
POST https://api.aspose.cloud/v3.0/slides/Sales.pptx 
```

###### **Request body:**
Contains the input presentation.

###### **Response:**
Full resource representation.

###### **C# SDK Code:**
```csharp
SlidesApi api = new SlidesApi("MyAppSid", "MyAppKey");
Stream file = File.OpenRead("input.pptx");
PostSlidesDocumentRequest request = new PostSlidesDocumentRequest { Name = "Sales.pptx", Folder = "MyFolder", Data = file };
Document response = api.PostSlidesDocument(request);
Console.WriteLine(response.SelfUri.Href); //https://api.aspose.cloud/v3.0/slides/Sales.pptx?folder=MyFolder
```

#### **HTTP PUT**
Not supported.

#### **HTTP DELETE**
Not supported.


## **Using a Source**
Aspose.Slides Cloud allows you to create a PowerPoint Presentation using a source document as a starting point
### **API Information**

|**API**|**Type**|**Description**|**Resource Link**|
| :- | :- | :- | :- |
| /slides/{name}/fromSource | POST | Create a new presentation from a Source Document in storage| [PostSlidesDocumentFromSource](https://apireference.aspose.cloud/slides/#/Document/PostSlidesDocumentFromSource) |

#### **Request Parameters**
| **Parameter Name** | **HTTP Method(s)** | **Type** | **Optional/Required** | **Description** |
| :- | :- | :- | :- | :- |
|password|POST|string|Optional|Password to create an encrypted presentation |
|folder|POST|string|Optional|New presentation folder |
|storage|POST|string|Optional|New presentation storage name |
|sourcePassword|POST|string|Optional|Source presentation password |
|sourceStorage|POST|string|Optional|Source presentation storage name |
|sourcePath|POST|string|Required|Source presentation path |

*In case of Amazon S3 storage folder path starts with Amazon S3 bucket name.*

#### **HTTP GET**
Not supported.

#### **HTTP POST**
Create presentation from existing template.

##### **Example**
```
POST https://api.aspose.cloud/v3.0/slides/Sales.pptx?sourcePath=folder/SalesTemplate.potx&templateStorage=SomeAmazonS3Storage
```

###### **Response:**
Full resource representation.

###### **C# SDK Code:**

```csharp
SlidesApi api = new SlidesApi("MyClientId", "MyClientSecret");
PostSlidesDocumentFromSourceRequest request = new PostSlidesDocumentFromSourceRequest { Name = "Sales.pptx", Folder = "MyFolder", SourcePath = "MyFolder/SalesTemplate.potx" };
Document response = api.PostSlidesDocumentFromSource(request);
Console.WriteLine(response.SelfUri.Href); //https://api.aspose.cloud/v3.0/slides/Sales.pptx?folder=MyFolder
```

#### **HTTP PUT**
Not supported.

#### **HTTP DELETE**
Not supported.


#### **cURL Examples**
{{< tabs tabTotal="2" tabID="1" tabName1="Request" tabName2="Response" >}}

{{< tab tabNum="1" >}}

**Create Authentication Header**

```java

curl -v "https://api.aspose.cloud/connect/token" -X POST -d "grant_type=client_credentials&client_id=XXXX&client_secret=XXXX-XX" -H "Content-Type: application/x-www-form-urlencoded" -H "Accept: application/json"

```

```java

curl  -v -X POST "https://api.aspose.cloud/v3.0/slides/new_one_source.pptx/fromSource?sourcePath=destination.pptx" -H "Content-Type: application/json" -H "Authorization: Bearer eyJhbGciOiJSUzI1NiIsInR5cCI6IkpXVCJ9.eyJuYmYiOjE1NTk3NzMwMDQsImV4cCI6MTU1OTg1OTQwNCwiaXNzIjoiaHR0cHM6Ly9hcGkuYXNwb3NlLmNsb3VkIiwiYXVkIjpbImh0dHBzOi8vYXBpLmFzcG9zZS5jbG91ZC9yZXNvdXJjZXMiLCJhcGkucGxhdGZvcm0iLCJhcGkucHJvZHVjdHMiXSwiY2xpZW50X2lkIjoiNzg5NDZmYjQtM2JkNC00ZDNlLWIzMDktZjllMmZmOWFjNmY5Iiwic2NvcGUiOlsiYXBpLnBsYXRmb3JtIiwiYXBpLnByb2R1Y3RzIl19.uz9tjVx3LddNa1POM2MEM6xGz5L4z4BaQgGQnLX55YT-_5Dztj631qT19kWhLJcONgYDqMp-c8Tgv2lV0iGfoKs-ZLZsvjOlpv0Oq3QJywj17LoUWap8feZyRlIFZz6nxB-OQhdd8JHglHx3Fu_l_gEssp6TrhXX6wdOgPPmV3DOrNZJR8ylc-e8V2Fx8or47CVVJ21e35DVzVRJK2EM4W_D7bh28jMSZqbVIS9FlA-INUD_ZCjTG2ix7TlUcBxblkcMUykq-M6KbNk1rd34tS0wV3RopQ8YmL-xeDQyDu8KVqBoUUEwjzY5fI9Y5GvuvATW6PXLt_5hGWmtlF874Q" --ssl-no-revoke -d {}

```

{{< /tab >}}

{{< tab tabNum="2" >}}

```java
{
   "documentProperties":{
      "uri":{
         "href":"https://api.aspose.cloud/v3.0/slides/new_one.pptx/documentProperties",
         "relation":"self"
      }
   },
   "slides":{
      "uri":{
         "href":"https://api.aspose.cloud/v3.0/slides/new_one.pptx/slides",
         "relation":"self"
      }
   },
   "images":{
      "uri":{
         "href":"https://api.aspose.cloud/v3.0/slides/new_one.pptx/images",
         "relation":"self"
      }
   },
   "layoutSlides":{
      "uri":{
         "href":"https://api.aspose.cloud/v3.0/slides/new_one.pptx/layoutSlides",
         "relation":"self"
      }
   },
   "masterSlides":{
      "uri":{
         "href":"https://api.aspose.cloud/v3.0/slides/new_one.pptx/masterSlides",
         "relation":"self"
      }
   },
   "selfUri":{
      "href":"https://api.aspose.cloud/v3.0/slides/new_one.pptx",
      "relation":"self"
   },
   "alternateLinks":[
      {
         "href":"https://api.aspose.cloud/v3.0/slides/new_one.pptx/odp",
         "relation":"alternate",
         "linkType":"application/vnd.oasis.opendocument.presentation",
         "title":"Download as Odp"
      },
      {
         "href":"https://api.aspose.cloud/v3.0/slides/new_one.pptx/ppt",
         "relation":"alternate",
         "linkType":"application/vnd.ms-powerpoint",
         "title":"Download as Ppt"
      },
      {
         "href":"https://api.aspose.cloud/v3.0/slides/new_one.pptx/pdf",
         "relation":"alternate",
         "linkType":"application/pdf",
         "title":"Download as Pdf"
      },
      {
         "href":"https://api.aspose.cloud/v3.0/slides/new_one.pptx/tiff",
         "relation":"alternate",
         "linkType":"image/tiff",
         "title":"Download as Tiff"
      },
      {
         "href":"https://api.aspose.cloud/v3.0/slides/new_one.pptx/xps",
         "relation":"alternate",
         "linkType":"application/vnd.ms-xpsdocument",
         "title":"Download as Xps"
      },
      {
         "href":"https://api.aspose.cloud/v3.0/slides/new_one.pptx/pps",
         "relation":"alternate",
         "linkType":"application/vnd.ms-powerpoint",
         "title":"Download as Pps"
      },
      {
         "href":"https://api.aspose.cloud/v3.0/slides/new_one.pptx/ppsx",
         "relation":"alternate",
         "linkType":"application/vnd.openxmlformats-officedocument.presentationml.slideshow",
         "title":"Download as Ppsx"
      },
      {
         "href":"https://api.aspose.cloud/v3.0/slides/new_one.pptx/pptm",
         "relation":"alternate",
         "linkType":"application/vnd.ms-powerpoint.presentation.macroEnabled.12",
         "title":"Download as Pptm"
      },
      {
         "href":"https://api.aspose.cloud/v3.0/slides/new_one.pptx/ppsm",
         "relation":"alternate",
         "linkType":"application/vnd.ms-powerpoint.slideshow.macroEnabled.12",
         "title":"Download as Ppsm"
      },
      {
         "href":"https://api.aspose.cloud/v3.0/slides/new_one.pptx/potx",
         "relation":"alternate",
         "linkType":"application/vnd.openxmlformats-officedocument.presentationml.template",
         "title":"Download as Potx"
      },
      {
         "href":"https://api.aspose.cloud/v3.0/slides/new_one.pptx/potm",
         "relation":"alternate",
         "linkType":"application/vnd.ms-powerpoint.template.macroEnabled.12",
         "title":"Download as Potm"
      },
      {
         "href":"https://api.aspose.cloud/v3.0/slides/new_one.pptx/otp",
         "relation":"alternate",
         "linkType":"application/vnd.oasis.opendocument.presentation-template",
         "title":"Download as Otp"
      },
      {
         "href":"https://api.aspose.cloud/v3.0/slides/new_one.pptx/html",
         "relation":"alternate",
         "linkType":"text/html",
         "title":"Download as Html"
      }
   ]
}

```

{{< /tab >}}

{{< /tabs >}}
## **Using an HTML Document**
Aspose.Slides Cloud allows you to create a PowerPoint Presentation using an HTML document in the request body
### **API Information**

|**API**|**Type**|**Description**|**Resource Link**|
| :- | :- | :- | :- |
|/slides/{name}/fromHtml|POST|Create a new presentation from a HTML Document is the request body|[PostSlidesDocumentFromHtml](https://apireference.aspose.cloud/slides/#/Document/PostSlidesDocumentFromHtml)|


#### **Request Parameters**
| **Parameter Name** | **HTTP Method(s)** | **Type** | **Optional/Required** | **Description** |
| :- | :- | :- | :- | :- |
|password|POST|string|Optional|Password to create an encrypted presentation |
|folder|POST|string|Optional|New presentation folder |
|storage|POST|string|Optional|New presentation storage name |

#### **HTTP GET**
Not supported.

#### **HTTP POST**
Create new presentation.

##### **Example**
Create presentation from html.
```
POST https://api.aspose.cloud/v3.0/slides/Sales.pptx/fromHtml
```

###### **Request body:**
```xml
<html>
  <head></head>
  <body>
    <p>Html content</p>
  </body>
</html>
```

###### **Response:**
Full presentation resource representation.

###### **C# SDK Code:**
```csharp
SlidesApi api = new SlidesApi("MyAppSid", "MyAppKey");
string html = @"
<html>
  <head></head>
  <body>
    <p>Html content</p>
  </body>
</html>";
PostSlidesDocumentFromHtmlRequest request = new PostSlidesDocumentFromHtmlRequest { Name = "NewPresentation.pptx", Folder = "MyFolder", Html = html };
Document response = api.PostSlidesDocumentFromHtml(request);
Console.WriteLine(response.SelfUri.Href); //https://api.aspose.cloud/v3.0/slides/NewPresentation.pptx?folder=MyFolder
```

#### **HTTP PUT**
Update a presentation.

##### **Example**
```
PUT https://api.aspose.cloud/v3.0/slides/Sales.pptx/fromHtml
```

###### **Request body:**
```xml
<html>
  <head></head>
  <body>
    <p>Html content</p>
  </body>
</html>
```

###### **C# SDK Code:**
```csharp
SlidesApi api = new SlidesApi("MyAppSid", "MyAppKey");
string html = @"
<html>
  <head></head>
  <body>
    <p>Html content</p>
  </body>
</html>";
PutSlidesDocumentFromHtmlRequest request = new PutSlidesDocumentFromHtmlRequest { Name = "ExistingPresentation.pptx", Folder = "MyFolder", Html = html };
Document response = api.PutSlidesDocumentFromHtml(request);
Console.WriteLine(response.SelfUri.Href); //https://api.aspose.cloud/v3.0/slides/ExistingPresentation.pptx?folder=MyFolder
```

#### **HTTP DELETE**
Not supported.


#### **cURL Examples**
{{< tabs tabTotal="2" tabID="5" tabName1="Request" tabName2="Response" >}}

{{< tab tabNum="1" >}}

**Create Authentication Header**

```java

curl -v "https://api.aspose.cloud/connect/token" -X POST -d "grant_type=client_credentials&client_id=XXXX&client_secret=XXXX-XX" -H "Content-Type: application/x-www-form-urlencoded" -H "Accept: application/json"

```

```java

curl  -v -X POST "https://api.aspose.cloud/v3.0/slides/new_one.pptx/fromHTML" -H "Content-Type: application/json" -H "Authorization: Bearer eyJhbGciOiJSUzI1NiIsInR5cCI6IkpXVCJ9.eyJuYmYiOjE1NTk3NzMwMDQsImV4cCI6MTU1OTg1OTQwNCwiaXNzIjoiaHR0cHM6Ly9hcGkuYXNwb3NlLmNsb3VkIiwiYXVkIjpbImh0dHBzOi8vYXBpLmFzcG9zZS5jbG91ZC9yZXNvdXJjZXMiLCJhcGkucGxhdGZvcm0iLCJhcGkucHJvZHVjdHMiXSwiY2xpZW50X2lkIjoiNzg5NDZmYjQtM2JkNC00ZDNlLWIzMDktZjllMmZmOWFjNmY5Iiwic2NvcGUiOlsiYXBpLnBsYXRmb3JtIiwiYXBpLnByb2R1Y3RzIl19.uz9tjVx3LddNa1POM2MEM6xGz5L4z4BaQgGQnLX55YT-_5Dztj631qT19kWhLJcONgYDqMp-c8Tgv2lV0iGfoKs-ZLZsvjOlpv0Oq3QJywj17LoUWap8feZyRlIFZz6nxB-OQhdd8JHglHx3Fu_l_gEssp6TrhXX6wdOgPPmV3DOrNZJR8ylc-e8V2Fx8or47CVVJ21e35DVzVRJK2EM4W_D7bh28jMSZqbVIS9FlA-INUD_ZCjTG2ix7TlUcBxblkcMUykq-M6KbNk1rd34tS0wV3RopQ8YmL-xeDQyDu8KVqBoUUEwjzY5fI9Y5GvuvATW6PXLt_5hGWmtlF874Q" --ssl-no-revoke -d "<html> <head></head> <body> <p>Html content</p> </body> </html>"

```

{{< /tab >}}

{{< tab tabNum="2" >}}

```java
{
   "documentProperties":{
      "uri":{
         "href":"https://api.aspose.cloud/v3.0/slides/new_one.pptx/documentProperties",
         "relation":"self"
      }
   },
   "slides":{
      "uri":{
         "href":"https://api.aspose.cloud/v3.0/slides/new_one.pptx/slides",
         "relation":"self"
      }
   },
   "images":{
      "uri":{
         "href":"https://api.aspose.cloud/v3.0/slides/new_one.pptx/images",
         "relation":"self"
      }
   },
   "layoutSlides":{
      "uri":{
         "href":"https://api.aspose.cloud/v3.0/slides/new_one.pptx/layoutSlides",
         "relation":"self"
      }
   },
   "masterSlides":{
      "uri":{
         "href":"https://api.aspose.cloud/v3.0/slides/new_one.pptx/masterSlides",
         "relation":"self"
      }
   },
   "selfUri":{
      "href":"https://api.aspose.cloud/v3.0/slides/new_one.pptx",
      "relation":"self"
   },
   "alternateLinks":[
      {
         "href":"https://api.aspose.cloud/v3.0/slides/new_one.pptx/odp",
         "relation":"alternate",
         "linkType":"application/vnd.oasis.opendocument.presentation",
         "title":"Download as Odp"
      },
      {
         "href":"https://api.aspose.cloud/v3.0/slides/new_one.pptx/ppt",
         "relation":"alternate",
         "linkType":"application/vnd.ms-powerpoint",
         "title":"Download as Ppt"
      },
      {
         "href":"https://api.aspose.cloud/v3.0/slides/new_one.pptx/pdf",
         "relation":"alternate",
         "linkType":"application/pdf",
         "title":"Download as Pdf"
      },
      {
         "href":"https://api.aspose.cloud/v3.0/slides/new_one.pptx/tiff",
         "relation":"alternate",
         "linkType":"image/tiff",
         "title":"Download as Tiff"
      },
      {
         "href":"https://api.aspose.cloud/v3.0/slides/new_one.pptx/xps",
         "relation":"alternate",
         "linkType":"application/vnd.ms-xpsdocument",
         "title":"Download as Xps"
      },
      {
         "href":"https://api.aspose.cloud/v3.0/slides/new_one.pptx/pps",
         "relation":"alternate",
         "linkType":"application/vnd.ms-powerpoint",
         "title":"Download as Pps"
      },
      {
         "href":"https://api.aspose.cloud/v3.0/slides/new_one.pptx/ppsx",
         "relation":"alternate",
         "linkType":"application/vnd.openxmlformats-officedocument.presentationml.slideshow",
         "title":"Download as Ppsx"
      },
      {
         "href":"https://api.aspose.cloud/v3.0/slides/new_one.pptx/pptm",
         "relation":"alternate",
         "linkType":"application/vnd.ms-powerpoint.presentation.macroEnabled.12",
         "title":"Download as Pptm"
      },
      {
         "href":"https://api.aspose.cloud/v3.0/slides/new_one.pptx/ppsm",
         "relation":"alternate",
         "linkType":"application/vnd.ms-powerpoint.slideshow.macroEnabled.12",
         "title":"Download as Ppsm"
      },
      {
         "href":"https://api.aspose.cloud/v3.0/slides/new_one.pptx/potx",
         "relation":"alternate",
         "linkType":"application/vnd.openxmlformats-officedocument.presentationml.template",
         "title":"Download as Potx"
      },
      {
         "href":"https://api.aspose.cloud/v3.0/slides/new_one.pptx/potm",
         "relation":"alternate",
         "linkType":"application/vnd.ms-powerpoint.template.macroEnabled.12",
         "title":"Download as Potm"
      },
      {
         "href":"https://api.aspose.cloud/v3.0/slides/new_one.pptx/otp",
         "relation":"alternate",
         "linkType":"application/vnd.oasis.opendocument.presentation-template",
         "title":"Download as Otp"
      },
      {
         "href":"https://api.aspose.cloud/v3.0/slides/new_one.pptx/html",
         "relation":"alternate",
         "linkType":"text/html",
         "title":"Download as Html"
      }
   ]
}

```

{{< /tab >}}

{{< /tabs >}}
### **SDKs**
Using an SDK (API client) is the quickest way for a developer to speed up the development. An SDK takes care of a lot of low-level details of making requests and handling responses and lets you focus on writing code specific to your particular project. Check out our [GitHub repository](https://github.com/aspose-slides-cloud) for a complete list of Aspose.Slides Cloud SDKs along with working examples, to get you started in no time. Please check [Available SDKs](/slides/available-sdks/) article to learn how to add an SDK to your project.
#### **SDK Examples**
{{< tabs tabTotal="9" tabID="5" tabName1="C#" tabName2="Java" tabName3="PHP" tabName4="Ruby" tabName5="Python" tabName6="Node.js" tabName7="Android" tabName8="C++" tabName9="Perl" >}}

{{< tab tabNum="1" >}}

{{< gist "" "a41a3c7c75241129b94faf7179d42527" "CreateNewPresentationFromHTML.cs" >}}

{{< /tab >}}

{{< tab tabNum="2" >}}

{{< gist "" "17b08f624ccca40e351e7204e318237e" "CreateNewPresentationFromHTML.java" >}}

{{< /tab >}}

{{< tab tabNum="3" >}}

{{< gist "" "67ba57c9ba0134d2e8c8ed2132d6515f" "CreateNewPresentationFromHTML.php" >}}

{{< /tab >}}

{{< tab tabNum="4" >}}

{{< gist "" "a41a3c7c75241129b94faf7179d42527" "Coming_Soon.txt" >}}

{{< /tab >}}

{{< tab tabNum="5" >}}

{{< gist "" "a41a3c7c75241129b94faf7179d42527" "Coming_Soon.txt" >}}

{{< /tab >}}

{{< tab tabNum="6" >}}

{{< gist "" "bc650902bdc45144b1727d329023dcba" "CreateNewPresentationFromHTML.js" >}}

{{< /tab >}}

{{< tab tabNum="7" >}}

{{< gist "" "2b52dabd204b301389d1f4234e9bb0d5" "CreateNewPresentationFromHTML.java" >}}

{{< /tab >}}

{{< tab tabNum="8" >}}

{{< gist "" "a41a3c7c75241129b94faf7179d42527" "Coming_Soon.txt" >}}

{{< /tab >}}

{{< tab tabNum="9" >}}

{{< gist "" "a41a3c7c75241129b94faf7179d42527" "Coming_Soon.txt" >}}

{{< /tab >}}

{{< /tabs >}}


## **Using a Template**
Aspose.Slides Cloud allows you to create a PowerPoint Presentation from a Template and data in request body using template engine.
### **API Information**

|**API**|**Type**|**Description**|**Resource Link**|
| :- | :- | :- | :- |
|/slides/{file-name}/fromTemplate|POST|Create a new presentation from a template in storage|[PostSlidesDocumentFromTemplate](https://apireference.aspose.cloud/slides/#/Document/PostSlidesDocumentFromTemplate)|


#### **Request Parameters**
| **Parameter Name** | **HTTP Method(s)** | **Type** | **Optional/Required** | **Description** |
| :- | :- | :- | :- | :- |
|password|POST|string|Optional|Password to create an encrypted presentation |
|isImageDataEmbeeded|POST|bool|Optional|Set this parameter to true if user's data contains embedded images in Base64 format.|
|templatePassword|POST|string|Optional|Template password.| 
|templateStorage|POST|string|Optional|Template storage name.| 
|templatePath|POST|string|Required|Template file path.| 
|folder|POST|string|Optional|Presentation folder. |
|storage|POST|string|Optional|Presentation storage name. |

#### **HTTP GET**
Not supported.

#### **HTTP POST**
Create new presentation from template and data in request body.

##### **Example**
Creates new presentation JohnDoeCV.pptx from CVTemplate.potx and data in request body.

###### **Request:**
```
POST https://api.aspose.cloud/v3.0/slides/JohnDoeCV.pptx&templatePath=CVTemplate.potx
```

###### **Request body:**
```
<?xml version="1.0" encoding="UTF-8"?>
<staff>
   <person>
      <name>John Doe</name>
      <address>
         <line1>10 Downing Street</line1>
         <line2>London</line2>
      </address>
      <phone>+457 123456</phone>
      <bio>Hi, I'm John and this is my CV</bio>
      <skills>
         <skill>
            <title>C#</title>
            <level>Excellent</level>
         </skill>
         <skill>
            <title>Cpp</title>
            <level>Good</level>
         </skill>
         <skill>
            <title>Java</title>
            <level>Average</level>
         </skill>
      </skills>
   </person>
</staff>
```

###### **Response:**
Full resource representation.

###### **C# SDK Code:**
```csharp
SlidesApi api = new SlidesApi("MyAppSid", "MyAppKey");
string data = @"
<staff>
    <person>
        <name>John Doe</name>
        <address>
            <line1>10 Downing Street</line1>
            <line2>London</line2>
        </address>
        <phone>+457 123456</phone>
        <bio>Hi, I'm John and this is my CV</bio>
        <skills>
            <skill>
                <title>C#</title>
                <level>Excellent</level>
            </skill>
            <skill>
                <title>Cpp</title>
                <level>Good</level>
            </skill>
            <skill>
                <title>Java</title>
                <level>Average</level>
            </skill>
        </skills>
    </person>
</staff>";
PostSlidesDocumentFromTemplateRequest request = new PostSlidesDocumentFromTemplateRequest
{
    Name = "JohnDoeCV.pptx",
    Folder = "MyFolder",
    TemplatePath="MyFolder/TemplateCV.potx",
    Data = data
};
Document response = api.PostSlidesDocumentFromTemplate(request);
Console.WriteLine(response.SelfUri.Href); //https://api.aspose.cloud/v3.0/slides/JohnDoeCV.pptx?folder=MyFolder
```

#### **HTTP PUT**
Not supported.

#### **HTTP DELETE**
Not supported.

### **cURL Example**

You can download a sample template file from [TemplateCV.pptx](https://github.com/aspose-slides-cloud/aspose-slides-cloud-dotnet/blob/master/TestData/TemplateCV.pptx). The template is then populated with the below data. See the below cURL example to see how to use this information.

```java
<staff>
    <person>
        <name>John Doe</name>
        <address>
            <line1>10 Downing Street</line1>
            <line2>London</line2>
        </address>
        <phone>+457 123456</phone>
        <bio>Hi, I'm John and this is my CV</bio>
        <skills>
            <skill>
                <title>C#</title>
                <level>Excellent</level>
            </skill>
            <skill>
                <title>Cpp</title>
                <level>Good</level>
            </skill>
            <skill>
                <title>Java</title>
                <level>Average</level>
            </skill>
        </skills>
    </person>
</staff>
```

{{< tabs tabTotal="2" tabID="11" tabName1="Request" tabName2="Response" >}}

{{< tab tabNum="1" >}}

**Create Authentication Header**

```java

curl -v "https://api.aspose.cloud/connect/token" -X POST -d "grant_type=client_credentials&client_id=XXXX&client_secret=XXXX-XX" -H "Content-Type: application/x-www-form-urlencoded" -H "Accept: application/json"

```

```java

curl  -v -X POST "https://api.aspose.cloud/v3.0/slides/new_one_template.pptx/fromTemplate?templatePath=TemplateCV.pptx" -H "Content-Type: application/json" -H "Authorization: Bearer eyJhbGciOiJSUzI1NiIsInR5cCI6IkpXVCJ9.eyJuYmYiOjE1NTk3NzMwMDQsImV4cCI6MTU1OTg1OTQwNCwiaXNzIjoiaHR0cHM6Ly9hcGkuYXNwb3NlLmNsb3VkIiwiYXVkIjpbImh0dHBzOi8vYXBpLmFzcG9zZS5jbG91ZC9yZXNvdXJjZXMiLCJhcGkucGxhdGZvcm0iLCJhcGkucHJvZHVjdHMiXSwiY2xpZW50X2lkIjoiNzg5NDZmYjQtM2JkNC00ZDNlLWIzMDktZjllMmZmOWFjNmY5Iiwic2NvcGUiOlsiYXBpLnBsYXRmb3JtIiwiYXBpLnByb2R1Y3RzIl19.uz9tjVx3LddNa1POM2MEM6xGz5L4z4BaQgGQnLX55YT-_5Dztj631qT19kWhLJcONgYDqMp-c8Tgv2lV0iGfoKs-ZLZsvjOlpv0Oq3QJywj17LoUWap8feZyRlIFZz6nxB-OQhdd8JHglHx3Fu_l_gEssp6TrhXX6wdOgPPmV3DOrNZJR8ylc-e8V2Fx8or47CVVJ21e35DVzVRJK2EM4W_D7bh28jMSZqbVIS9FlA-INUD_ZCjTG2ix7TlUcBxblkcMUykq-M6KbNk1rd34tS0wV3RopQ8YmL-xeDQyDu8KVqBoUUEwjzY5fI9Y5GvuvATW6PXLt_5hGWmtlF874Q" --ssl-no-revoke -d "<staff> <person> <name>John Doe</name> <address> <line1>10 Downing Street</line1> <line2>London</line2> </address> <phone>+457 123456</phone> <bio>Hi, I'm John and this is my CV</bio> <skills> <skill> <title>C#</title> <level>Excellent</level> </skill> <skill> <title>C++</title> <level>Good</level> </skill> <skill> <title>Java</title> <level>Average</level> </skill> </skills> </person></staff>"

```

{{< /tab >}}

{{< tab tabNum="2" >}}

```java
{
   "documentProperties":{
      "uri":{
         "href":"https://api.aspose.cloud/v3.0/slides/new_one_template.pptx/documentProperties",
         "relation":"self"
      }
   },
   "slides":{
      "uri":{
         "href":"https://api.aspose.cloud/v3.0/slides/new_one_template.pptx/slides",
         "relation":"self"
      }
   },
   "images":{
      "uri":{
         "href":"https://api.aspose.cloud/v3.0/slides/new_one_template.pptx/images",
         "relation":"self"
      }
   },
   "layoutSlides":{
      "uri":{
         "href":"https://api.aspose.cloud/v3.0/slides/new_one_template.pptx/layoutSlides",
         "relation":"self"
      }
   },
   "masterSlides":{
      "uri":{
         "href":"https://api.aspose.cloud/v3.0/slides/new_one_template.pptx/masterSlides",
         "relation":"self"
      }
   },
   "selfUri":{
      "href":"https://api.aspose.cloud/v3.0/slides/new_one_template.pptx",
      "relation":"self"
   },
   "alternateLinks":[
      {
         "href":"https://api.aspose.cloud/v3.0/slides/new_one_template.pptx/odp",
         "relation":"alternate",
         "linkType":"application/vnd.oasis.opendocument.presentation",
         "title":"Download as Odp"
      },
      {
         "href":"https://api.aspose.cloud/v3.0/slides/new_one_template.pptx/ppt",
         "relation":"alternate",
         "linkType":"application/vnd.ms-powerpoint",
         "title":"Download as Ppt"
      },
      {
         "href":"https://api.aspose.cloud/v3.0/slides/new_one_template.pptx/pdf",
         "relation":"alternate",
         "linkType":"application/pdf",
         "title":"Download as Pdf"
      },
      {
         "href":"https://api.aspose.cloud/v3.0/slides/new_one_template.pptx/tiff",
         "relation":"alternate",
         "linkType":"image/tiff",
         "title":"Download as Tiff"
      },
      {
         "href":"https://api.aspose.cloud/v3.0/slides/new_one_template.pptx/xps",
         "relation":"alternate",
         "linkType":"application/vnd.ms-xpsdocument",
         "title":"Download as Xps"
      },
      {
         "href":"https://api.aspose.cloud/v3.0/slides/new_one_template.pptx/pps",
         "relation":"alternate",
         "linkType":"application/vnd.ms-powerpoint",
         "title":"Download as Pps"
      },
      {
         "href":"https://api.aspose.cloud/v3.0/slides/new_one_template.pptx/ppsx",
         "relation":"alternate",
         "linkType":"application/vnd.openxmlformats-officedocument.presentationml.slideshow",
         "title":"Download as Ppsx"
      },
      {
         "href":"https://api.aspose.cloud/v3.0/slides/new_one_template.pptx/pptm",
         "relation":"alternate",
         "linkType":"application/vnd.ms-powerpoint.presentation.macroEnabled.12",
         "title":"Download as Pptm"
      },
      {
         "href":"https://api.aspose.cloud/v3.0/slides/new_one_template.pptx/ppsm",
         "relation":"alternate",
         "linkType":"application/vnd.ms-powerpoint.slideshow.macroEnabled.12",
         "title":"Download as Ppsm"
      },
      {
         "href":"https://api.aspose.cloud/v3.0/slides/new_one_template.pptx/potx",
         "relation":"alternate",
         "linkType":"application/vnd.openxmlformats-officedocument.presentationml.template",
         "title":"Download as Potx"
      },
      {
         "href":"https://api.aspose.cloud/v3.0/slides/new_one_template.pptx/potm",
         "relation":"alternate",
         "linkType":"application/vnd.ms-powerpoint.template.macroEnabled.12",
         "title":"Download as Potm"
      },
      {
         "href":"https://api.aspose.cloud/v3.0/slides/new_one_template.pptx/otp",
         "relation":"alternate",
         "linkType":"application/vnd.oasis.opendocument.presentation-template",
         "title":"Download as Otp"
      },
      {
         "href":"https://api.aspose.cloud/v3.0/slides/new_one_template.pptx/html",
         "relation":"alternate",
         "linkType":"text/html",
         "title":"Download as Html"
      }
   ]
}

```

{{< /tab >}}

{{< /tabs >}}
### **SDKs**
Using an SDK (API client) is the quickest way for a developer to speed up the development. An SDK takes care of a lot of low-level details of making requests and handling responses and lets you focus on writing code specific to your particular project. Check out our [GitHub repository](https://github.com/aspose-slides-cloud) for a complete list of Aspose.Slides Cloud SDKs along with working examples, to get you started in no time. Please check [Available SDKs](/slides/available-sdks/) article to learn how to add an SDK to your project.
#### **SDK Examples**
{{< tabs tabTotal="9" tabID="5" tabName1="C#" tabName2="Java" tabName3="PHP" tabName4="Ruby" tabName5="Python" tabName6="Node.js" tabName7="Android" tabName8="C++" tabName9="Perl" >}}

{{< tab tabNum="1" >}}

{{< gist "" "a41a3c7c75241129b94faf7179d42527" "CreateNewPresentationFromTemplate.cs" >}}

{{< /tab >}}

{{< tab tabNum="2" >}}

{{< gist "" "17b08f624ccca40e351e7204e318237e" "CreateNewPresentationFromTemplate.java" >}}

{{< /tab >}}

{{< tab tabNum="3" >}}

{{< gist "" "67ba57c9ba0134d2e8c8ed2132d6515f" "CreateNewPresentationFromTemplate.php" >}}

{{< /tab >}}

{{< tab tabNum="4" >}}

{{< gist "" "a41a3c7c75241129b94faf7179d42527" "Coming_Soon.txt" >}}

{{< /tab >}}

{{< tab tabNum="5" >}}

{{< gist "" "a41a3c7c75241129b94faf7179d42527" "Coming_Soon.txt" >}}

{{< /tab >}}

{{< tab tabNum="6" >}}

{{< gist "" "bc650902bdc45144b1727d329023dcba" "CreateNewPresentationFromTemplate.js" >}}

{{< /tab >}}

{{< tab tabNum="7" >}}

{{< gist "" "2b52dabd204b301389d1f4234e9bb0d5" "CreateNewPresentationFromTemplate.java" >}}

{{< /tab >}}

{{< tab tabNum="8" >}}

{{< gist "" "a41a3c7c75241129b94faf7179d42527" "Coming_Soon.txt" >}}

{{< /tab >}}

{{< tab tabNum="9" >}}

{{< gist "" "a41a3c7c75241129b94faf7179d42527" "Coming_Soon.txt" >}}

{{< /tab >}}

{{< /tabs >}}


### **SDK Source**
The Aspose  Cloud SDKs can be downloaded from the following page: [Available SDKs](/slides/available-sdks/)
