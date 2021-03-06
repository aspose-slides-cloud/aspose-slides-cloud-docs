---
title: "Convert PowerPoint Documents to other File Formats"
type: docs
url: /convert-powerpoint-documents-to-other-file-formats/
weight: 10
---

## **Convert**

## **Introduction**
This example allows you to save a presentation to different other formats using Aspose.Slides Cloud API in your applications. The Slides Cloud API supports two types of conversion
## **Using Storage**
### **API Information**

|**API**|**Type**|**Description**|**Swagger Link**|
| :- | :- | :- | :- |
|/slides/convert/{format}|PUT|Convert the file to the desired format and saves file on Cloud Storage|[PutSlidesConvert](https://apireference.aspose.cloud/slides/#/General/PutSlidesConvert)|
### **cURL Example**
{{< tabs tabTotal="2" tabID="1" tabName1="Request" tabName2="Response" >}}

{{< tab tabNum="1" >}}

**Create Request Token**

```java

curl -v "https://api.aspose.cloud/connect/token" -X POST -d "grant_type=client_credentials&client_id=XXXX&client_secret=XXXX-XX" -H "Content-Type: application/x-www-form-urlencoded" -H "Accept: application/json"

```

```java

curl  -v -X PUT "https://api.aspose.cloud/v4.0/slides/convert/pdf?outPath=myabc.pdf" --data-binary @test.pptx -H "Content-Type: application/octet-stream" -H "Authorization: Bearer CwEsXL_ddljbOuknQ2d-grMMRhNcAUhsDDEbBfORflhLt7zZZEVDIC15mmk99AjMBlSywCpPiFcvPqJ0dc2SJBEhdGNcDBTQ1rbuy08Wa6LGvcASPRXXmj04WxgC4nkzuoJN4UTTECNruH1n85P3V1s2hwFXqCVWxcushRupPXr1L9bpALlG9uEQq9_1OAF_m_REnrTSF51YKKr1NJkzcL0YuZqPsu4ER4qu9Y132ipP4SruqjrHWnkbgQ0JcE81Zuw7hmCXjb8SJDi0xsfKWBfhQOPT-Ff9-OnrmMJ1m6KyaqLTpGmhgrSMVYf5KXbRNspaBdTgKMToKH-rUOukIdMWOjV7VF8L0libDd2YaMzleJdo6DVRLQN12oBZDYDXPL3QDkD3doi9aq848rNSw_Mj_3aHQ1xaGehBMPk7ea_WuKMf" --ssl-no-revoke

```

{{< /tab >}}

{{< tab tabNum="2" >}}

```java

{response-data}

```

{{< /tab >}}

{{< /tabs >}}

## **Without using Storage**
### **API Information**

|**API**|**Type**|**Description**|**Swagger Link**|
| :- | :- | :- | :- |
|/slides/convert/{format}|PUT|Convert the file to the desired format and saves a file on Cloud Storage|[PostSlidesConvert](https://apireference.aspose.cloud/slides/#/General/PostSlidesConvert)|

Where {format} - conversion format. [You can see all valid values for this parameter here]()

#### **Request parameters**
| **Parameter Name** | **HTTP Method(s)** | **Type** | **Optional/Required** | **Description** |
| :- | :- | :- | :- | :- |
|password|POST/PUT|string|Optional|Presentation password if required.|
|outPath|PUT|string|Required|Local storage path for the output file (required).|
|fontsFolder|POST/PUT|string|Optional|Storage folder containing custom fonts to be used with the presentation.|

#### **HTTP GET**
Not supported.

#### **HTTP PUT**
Convert presentation in request body to specified format and save it to the specified storage location.

##### **Example 1**
This examples converts presentation to TIFF image and saves output picture on server.
```
PUT https://api.aspose.cloud/v3.0/slides/convert/tiff?outPath=SomeFolder/result.tiff 
```
###### **Request body:**
Contains the presentation to convert data.

###### **Response:**
OK status code.

###### **C# SDK Code:**

```csharp
SlidesApi api = new SlidesApi("MyAppSid", "MyAppKey");
Stream file = File.OpenRead("MyPresentation.pptx");
Stream response = api.Convert(file, ExportFormat.Tiff);
response.CopyTo(File.Create("MyPresentation.tiff"));
```

##### **Example 2**
This examples converts presentation to PDF document using custom fonts contained in *customFonts* storage folder.

```
POST https://api.aspose.cloud/v3.0/slides/convert/pdf?fontsFolder=customFonts 
```

###### **Request body:**
Contains the presentation to convert data.

###### **Response:**
Contains the conversion to PDF result.

###### **C# SDK Code:**

```csharp
SlidesApi api = new SlidesApi("MyClientId", "MyClientSecret");
const string fontsFolder = "customFonts";
api.CreateFolder(fontsFolder);
Stream font = File.OpenRead("custom.ttf");
api.UploadFile(font, $"{fontsFolder}/custom.ttf");
Stream file = File.OpenRead("customfont.pptx");
Stream response = api.Convert(file, ExportFormat.Pdf, fontsFolder: fontsFolder);
response.CopyTo(File.Create("customfont.pdf"));
```

#### **HTTP DELETE**
Not supported.

#### **cURL Example**
{{< tabs tabTotal="2" tabID="5" tabName1="Request" tabName2="Response" >}}

{{< tab tabNum="1" >}}

**Create Request Token**

```java

curl -v "https://api.aspose.cloud/connect/token" -X POST -d "grant_type=client_credentials&client_id=XXXX&client_secret=XXXX-XX" -H "Content-Type: application/x-www-form-urlencoded" -H "Accept: application/json"

```

```java

curl  -v -X POST "https://api.aspose.cloud/v3.0/slides/convert/pdf" --data-binary @test.pptx -H "Content-Type: application/octet-stream" -H "Accept: Multipart/Form data" -H "Authorization: Bearer eyJhbGciOiJSUzI1NiIsInR5cCI6IkpXVCJ9.eyJuYmYiOjE1NTk3NjMxNTUsImV4cCI6MTU1OTg0OTU1NSwiaXNzIjoiaHR0cHM6Ly9hcGkuYXNwb3NlLmNsb3VkIiwiYXVkIjpbImh0dHBzOi8vYXBpLmFzcG9zZS5jbG91ZC9yZXNvdXJjZXMiLCJhcGkucGxhdGZvcm0iLCJhcGkucHJvZHVjdHMiXSwiY2xpZW50X2lkIjoiNzg5NDZmYjQtM2JkNC00ZDNlLWIzMDktZjllMmZmOWFjNmY5Iiwic2NvcGUiOlsiYXBpLnBsYXRmb3JtIiwiYXBpLnByb2R1Y3RzIl19.qashpcOro6uHwPqYauzYEQ_zNHUPx9SOuBN1HVf3z3vOK_4ctWsLYyaNETUjPaWDzAhQAGJbG2IBE1hNQk4uS_rjTMdbe5SzcVy_w6DPwGELVe6erOqBVOxyZML3zL43a5sy9XEpjjp5S3N54l3kL2KJY86AAgh5ShTFx4I9kKx4vkqOGtJCjqZ0XWcS0D3BmnL6sOtBa9rNEc-f3ICzynOXo-ACkomKrRlNuQz8HiZlMDXILhKt1N0c0Kco9CuclPYwynuFAmthvSlmcVfRTF9V5Mz2MnQSFVIlg-ql7wvtkJJybYmxlwd8Fp4gKytyV8x2lDLTOuNJZxVqS7vMqg" --ssl-no-revoke --output outfile.pdf

```

{{< /tab >}}

{{< tab tabNum="2" >}}

```java

{response-data}

```

{{< /tab >}}

{{< /tabs >}}
# **SDKs**
Using an SDK (API client) is the quickest way for a developer to speed up the development. An SDK takes care of a lot of low-level details of making requests and handling responses and lets you focus on writing code specific to your particular project. Check out our [GitHub repository](https://github.com/aspose-slides-cloud) for a complete list of Aspose.Slides Cloud SDKs along with working examples, to get you started in no time. Please check [Available SDKs](/slides/available-sdks/) article to learn how to add an SDK to your project.
## **SDK Examples**
{{< tabs tabTotal="9" tabID="5" tabName1="C#" tabName2="Java" tabName3="PHP" tabName4="Ruby" tabName5="Python" tabName6="Node.js" tabName7="Android" tabName8="C++" tabName9="Perl" >}}

{{< tab tabNum="1" >}}

{{< gist "" "a41a3c7c75241129b94faf7179d42527" "ConvertToOtherFormat.cs" >}}

{{< /tab >}}

{{< tab tabNum="2" >}}

{{< gist "" "17b08f624ccca40e351e7204e318237e" "ConvertToOtherFormat.java" >}}

{{< /tab >}}

{{< tab tabNum="3" >}}

{{< gist "" "67ba57c9ba0134d2e8c8ed2132d6515f" "ConvertToOtherFormat.php" >}}

{{< /tab >}}

{{< tab tabNum="4" >}}

{{< gist "" "2cc36b05065a88cb0737424e4f38f68e" "ConvertToOtherFormat.rb" >}}

{{< /tab >}}

{{< tab tabNum="5" >}}

{{< gist "" "88b9472c3f741eae6c606abdd003c791" "ConvertToOtherFormat.py" >}}

{{< /tab >}}

{{< tab tabNum="6" >}}

{{< gist "" "bc650902bdc45144b1727d329023dcba" "ConvertToOtherFormat.js" >}}

{{< /tab >}}

{{< tab tabNum="7" >}}

{{< gist "" "2b52dabd204b301389d1f4234e9bb0d5" "ConvertToOtherFormat.java" >}}

{{< /tab >}}

{{< tab tabNum="8" >}}

{{< gist "" "a41a3c7c75241129b94faf7179d42527" "Coming_Soon.txt" >}}

{{< /tab >}}

{{< tab tabNum="9" >}}

{{< gist "" "a41a3c7c75241129b94faf7179d42527" "Coming_Soon.txt" >}}

{{< /tab >}}

{{< /tabs >}}


## **Conversion Formats**
The Aspose.Slides Cloud API supports the following format conversions


|**File Type**|**Extension**|
| :- | :- |
|PowerPoint Presentation|pptx|
|PowerPoint Presentation|ppt|
|Microsoft PowerPoint Open XML Macro-Enabled Presentation File|pptm|
|Microsoft PowerPoint Open XML Slide Show File|ppsx|
|Microsoft PowerPoint Show File|pps|
|Microsoft PowerPoint Open XML Macro-enabled Slide Show File |ppsm|
|Microsoft PowerPoint Open XML Template File |potx|
|Microsoft PowerPoint Macro-Enabled Template|potm|
|OpenDocument Presentation file|odp|
|Open Office / Star Office Presentation|otp|
|Portable Document Format|pdf|
|HTML File|html|
|Open XML Paper Specification|xps|
|Shockwave Flash File|swf|
|Scalable Vector Graphics File|svg|
|Tiff Image|tiff|
|JPEG Image|jpeg|
|PNG File|png|
|GIF Image|gif|
|Bitmap File|bmp|

## **SDK Source**
The Aspose Cloud SDK's can be downloaded from the following page: [Available SDK's](/slides/available-sdks/)
