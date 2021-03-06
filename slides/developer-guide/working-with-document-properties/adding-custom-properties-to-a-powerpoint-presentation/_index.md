---
title: "Adding Custom Properties to a PowerPoint Presentation"
type: docs
url: /adding-custom-properties-to-a-powerpoint-presentation/
weight: 20
---

## **Introduction**
Aspose.Slides Cloud allows you to add custom properties to a PowerPoint Presentation
### **API Information**

|**API**|**Type**|**Description**|**Swagger Link**|
| :- | :- | :- | :- |
|/slides/{name}/documentproperties|POST|Add a custom property|[PostSlidesSetDocumentProperties](https://apireference.aspose.cloud/slides/#/Properties/PostSlidesSetDocumentProperties)|
### **cURL Example**

In this example we add a 2 new custom properties to the PowerPoint Presentation.

```java

{

   "List":[

      {

         "Name":"Processed By Office",

         "Value":"Scotland Team"

      },

      {

         "Name":"Another Custom Property",

         "Value":"Example Value"

      }

   ]

}

```

{{< tabs tabTotal="2" tabID="2" tabName1="Request" tabName2="Response" >}}

{{< tab tabNum="1" >}}

**Create Authentication Token**

```java

curl -v "https://api.aspose.cloud/connect/token" -X POST -d "grant_type=client_credentials&client_id=78946fb4-3bd4-4d3e-b309-f9e2ff9ac6f9&client_secret=b125f13bf6b76ed81ee990142d841195" -H "Content-Type: application/x-www-form-urlencoded" -H "Accept: application/json"

```

```java

curl  -v -X POST "https://api.aspose.cloud/v3.0/slides/destination.pptx/documentProperties" -H "Content-Type: application/json" -H "Authorization: Bearer eyJhbGciOiJSUzI1NiIsInR5cCI6IkpXVCJ9.eyJuYmYiOjE1NjAwMjkwNjEsImV4cCI6MTU2MDExNTQ2MSwiaXNzIjoiaHR0cHM6Ly9hcGkuYXNwb3NlLmNsb3VkIiwiYXVkIjpbImh0dHBzOi8vYXBpLmFzcG9zZS5jbG91ZC9yZXNvdXJjZXMiLCJhcGkucGxhdGZvcm0iLCJhcGkucHJvZHVjdHMiXSwiY2xpZW50X2lkIjoiNzg5NDZmYjQtM2JkNC00ZDNlLWIzMDktZjllMmZmOWFjNmY5Iiwic2NvcGUiOlsiYXBpLnBsYXRmb3JtIiwiYXBpLnByb2R1Y3RzIl19.mNYcPQW8t9rhc1YybQXgAlpW-KyiwyEgaVOgGnaPiH_wr8d6Uq9i6Gj9K_CNY4EWn5vkme2U4o9TcqNmnaB7x9EFWjFDO19R7nBem3RcD64Ww5NTv8ocd5Crf27ZX2AoI69e0j7wpGxTJYjcGtcCUhAg4Nez64XiVG-3Hh2WwDREegI2X9nptjr0OYd9wyT0av_G5Tr-ZkjClUQbh09aBbySiWjC9W3R0o1IwKMNmrCqcnGjehdU0d_KqShwLGx-_Itbp2SRP3S8A1KPZsOzrnfZO-XwHzKioqSv4nzv8q8Ewx1nmvOgPXsCtGQ9aFWdR2CSSqg6_9IXnp3x41GcPA" --ssl-no-revoke -d "{'List': [{'Name': 'Processed By Office', 'Value': 'Scotland Team'}, {'Name': 'Another Custom Property', 'Value': 'Example Value'} ] }"

```

{{< /tab >}}

{{< tab tabNum="2" >}}

```java

{

   "list":[

      {

         "name":"Author",

         "value":"Xander Cage",

         "builtIn":true,

         "selfUri":{

            "href":"https://api.aspose.cloud/v3.0/slides/destination.pptx/documentProperties/Author",

            "relation":"self"

         }

      },

      {

         "name":"Category",

         "value":"",

         "builtIn":true,

         "selfUri":{

            "href":"https://api.aspose.cloud/v3.0/slides/destination.pptx/documentProperties/Category",

            "relation":"self"

         }

      },

      {

         "name":"Comments",

         "value":"",

         "builtIn":true,

         "selfUri":{

            "href":"https://api.aspose.cloud/v3.0/slides/destination.pptx/documentProperties/Comments",

            "relation":"self"

         }

      },

      {

         "name":"Company",

         "value":"",

         "builtIn":true,

         "selfUri":{

            "href":"https://api.aspose.cloud/v3.0/slides/destination.pptx/documentProperties/Company",

            "relation":"self"

         }

      },

      {

         "name":"Keywords",

         "value":"",

         "builtIn":true,

         "selfUri":{

            "href":"https://api.aspose.cloud/v3.0/slides/destination.pptx/documentProperties/Keywords",

            "relation":"self"

         }

      },

      {

         "name":"LastSavedBy",

         "value":"Xander",

         "builtIn":true,

         "selfUri":{

            "href":"https://api.aspose.cloud/v3.0/slides/destination.pptx/documentProperties/LastSavedBy",

            "relation":"self"

         }

      },

      {

         "name":"Manager",

         "value":"",

         "builtIn":true,

         "selfUri":{

            "href":"https://api.aspose.cloud/v3.0/slides/destination.pptx/documentProperties/Manager",

            "relation":"self"

         }

      },

      {

         "name":"NameOfApplication",

         "value":"Aspose.Slides for .NET",

         "builtIn":true,

         "selfUri":{

            "href":"https://api.aspose.cloud/v3.0/slides/destination.pptx/documentProperties/NameOfApplication",

            "relation":"self"

         }

      },

      {

         "name":"RevisionNumber",

         "value":"4",

         "builtIn":true,

         "selfUri":{

            "href":"https://api.aspose.cloud/v3.0/slides/destination.pptx/documentProperties/RevisionNumber",

            "relation":"self"

         }

      },

      {

         "name":"Subject",

         "value":"",

         "builtIn":true,

         "selfUri":{

            "href":"https://api.aspose.cloud/v3.0/slides/destination.pptx/documentProperties/Subject",

            "relation":"self"

         }

      },

      {

         "name":"Template",

         "value":"",

         "builtIn":true,

         "selfUri":{

            "href":"https://api.aspose.cloud/v3.0/slides/destination.pptx/documentProperties/Template",

            "relation":"self"

         }

      },

      {

         "name":"Title",

         "value":"PowerPoint Presentation",

         "builtIn":true,

         "selfUri":{

            "href":"https://api.aspose.cloud/v3.0/slides/destination.pptx/documentProperties/Title",

            "relation":"self"

         }

      },

      {

         "name":"TotalEditingTime",

         "value":"PT0S",

         "builtIn":true,

         "selfUri":{

            "href":"https://api.aspose.cloud/v3.0/slides/destination.pptx/documentProperties/TotalEditingTime",

            "relation":"self"

         }

      },

      {

         "name":"CreatedTime",

         "value":"2019-03-29T13:21:33Z",

         "builtIn":true,

         "selfUri":{

            "href":"https://api.aspose.cloud/v3.0/slides/destination.pptx/documentProperties/CreatedTime",

            "relation":"self"

         }

      },

      {

         "name":"LastPrinted",

         "value":"0001-01-01T00:00:00Z",

         "builtIn":true,

         "selfUri":{

            "href":"https://api.aspose.cloud/v3.0/slides/destination.pptx/documentProperties/LastPrinted",

            "relation":"self"

         }

      },

      {

         "name":"LastSavedTime",

         "value":"2019-06-08T20:36:18Z",

         "builtIn":true,

         "selfUri":{

            "href":"https://api.aspose.cloud/v3.0/slides/destination.pptx/documentProperties/LastSavedTime",

            "relation":"self"

         }

      },

      {

         "name":"Another Custom Property",

         "value":"Example Value",

         "builtIn":false,

         "selfUri":{

            "href":"https://api.aspose.cloud/v3.0/slides/destination.pptx/documentProperties/Another%20Custom%20Property",

            "relation":"self"

         }

      },

      {

         "name":"Processed By Office",

         "value":"Scotland Team",

         "builtIn":false,

         "selfUri":{

            "href":"https://api.aspose.cloud/v3.0/slides/destination.pptx/documentProperties/Processed%20By%20Office",

            "relation":"self"

         }

      }

   ],

   "selfUri":{

      "href":"https://api.aspose.cloud/v3.0/slides/destination.pptx/documentProperties",

      "relation":"self"

   }

}

```

{{< /tab >}}

{{< /tabs >}}


## **SDK Source**
The Aspose.Slide Cloud SDKs can be downloaded from the following page: [Available SDKs](/slides/available-sdks/)
## **SDK Examples**
{{< tabs tabTotal="9" tabID="5" tabName1="C#" tabName2="Java" tabName3="PHP" tabName4="Ruby" tabName5="Python" tabName6="Node.js" tabName7="Android" tabName8="C++" tabName9="Perl" >}}

{{< tab tabNum="1" >}}

{{< gist "" "a41a3c7c75241129b94faf7179d42527" "GetSlidesThemeFonts.cs" >}}

{{< /tab >}}

{{< tab tabNum="2" >}}

{{< gist "" "17b08f624ccca40e351e7204e318237e" "GetSlidesThemeFonts.java" >}}

{{< /tab >}}

{{< tab tabNum="3" >}}

{{< gist "" "67ba57c9ba0134d2e8c8ed2132d6515f" "GetSlidesThemeFonts.php" >}}

{{< /tab >}}

{{< tab tabNum="4" >}}

{{< gist "" "2cc36b05065a88cb0737424e4f38f68e" "GetSlidesThemeFonts.rb" >}}

{{< /tab >}}

{{< tab tabNum="5" >}}

{{< gist "" "88b9472c3f741eae6c606abdd003c791" "GetSlidesThemeFonts.py" >}}

{{< /tab >}}

{{< tab tabNum="6" >}}

{{< gist "" "bc650902bdc45144b1727d329023dcba" "GetSlidesThemeFonts.js" >}}

{{< /tab >}}

{{< tab tabNum="7" >}}

{{< gist "" "2b52dabd204b301389d1f4234e9bb0d5" "GetSlidesThemeFonts.java" >}}

{{< /tab >}}

{{< tab tabNum="8" >}}

{{< gist "" "a41a3c7c75241129b94faf7179d42527" "Coming_Soon.txt" >}}

{{< /tab >}}

{{< tab tabNum="9" >}}

{{< gist "" "a41a3c7c75241129b94faf7179d42527" "Coming_Soon.txt" >}}

{{< /tab >}}

{{< /tabs >}}
