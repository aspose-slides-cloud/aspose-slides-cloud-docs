---
title: "Using fontsLocation Parameter to specify custom fonts"
type: docs
url: /using-fontslocation-parameter-to-specify-custom-fonts/
weight: 10
---

## **Introduction**
Aspose.Slides for Cloud allows you to specify a fontsLocation Parameter. The fontLocation parameter allows you to specify the location of a font file that is uploaded to Aspose Cloud Storage.
## **Resource**
The following Aspose.Slides for Cloud REST API resource has been used in the examples: [Presentation](https://apireference.aspose.cloud/slides/#!/SlidesDocument/SlidesDocument_PostSlidesSplit).
## **cURL Example**
{{< tabs tabTotal="2" tabID="1" tabName1="Request" tabName2="Response" >}}

{{< tab tabNum="1" >}}

**Create Authentication Header**

```java

curl -v "https://api.aspose.cloud/oauth2/token" -X POST -d "grant\_type=client\_credentials&client\_id=78946fb4-3bd4-4d3e-b309-f9e2ff9ac6f9&client\_secret=b125f13bf6b76ed81ee990142d84119"-H "Content-Type: application/x-www-form-urlencoded"-H "Accept: application/json" 

```

```java

curl -v "http://api.aspose.cloud/v1.1/slides/convert?format=pdf&fontsLocation=fonts" --data-binary @sample.pptx  

-X PUT -H "Accept:application/json"  -H "Authorization: Bearer -Ou\_UHdVStdZldtjaeFUAowQ3x2KLlSHd5ovZfDtZqpgdC6FLlalPmO8VJ58HXp8sgGhLqMqlnzEzIF2fEhEyJ3D7xzaw\_c8cAuk3qoag3g7bghMHw\_pe\_RTxxJ9r04R9YAGFbbAcoU1ddPvrPz0e1FSakagM42Ie2eA8D1MyBVJ1D-RZJrfebPePuOLvR\_hOD8Doqk5SBi\_j-efODJK\_PmGUxj0onOrUUx8Tj\_GuUKrG6DcBnpl84\_UykdOP87IeHnT2\_NZCHQIgOY0vtfW6AUGfP9jO5W1mBS\_q3lthTDRMg2LuZ6s0r9MKlwVJ\_n7sn3TUCrr8kGmUB3k0mL0rrd5TSKm7yjx8hhjap43PlFhwk-r9g7guWsuFLoeDqPa4JNJ1NFM54qQvgWKCp5oDj4dZfbc7qhfIelNh1gW4VYwfmgz"

```

{{< /tab >}}

{{< tab tabNum="2" >}}

```java

{response-data}

```

{{< /tab >}}

{{< /tabs >}}
## **SDK Examples**


{{< tabs tabTotal="9" tabID="5" tabName1="C#" tabName2="Java" tabName3="PHP" tabName4="Ruby" tabName5="Python" tabName6="Node.js" tabName7="Android" tabName8="Objective C" tabName9="Perl" >}}

{{< tab tabNum="1" >}}



{{< /tab >}}

{{< tab tabNum="2" >}}

{{< gist "aspose-slides" "74de7640c8f072fe50c273602772094b" "Examples-JAVA-SDK-src-main-java-com-aspose-slides-cloud-examples-convert-ConvertPowerPointDocuments-1.java" >}}

{{< /tab >}}

{{< tab tabNum="3" >}}



{{< /tab >}}

{{< tab tabNum="4" >}}



{{< /tab >}}

{{< tab tabNum="5" >}}



{{< gist "aspose-slides" "95a1eec70765177679d02f656365f1da" "ConvertPowerPointDocumentsToOtherStorageWithoutStorage.py" >}}

{{< /tab >}}

{{< tab tabNum="6" >}}



{{< /tab >}}

{{< tab tabNum="7" >}}

{{< gist "aspose-slides" "30c37de1e8d2221a42041040c9224f66" "Examples-Android-app-src-main-java-com-aspose-slides-cloud-examples-convert-ConvertPowerPointDocuments-1.java" >}}

{{< /tab >}}

{{< tab tabNum="8" >}}



{{< /tab >}}

{{< tab tabNum="9" >}}



{{< /tab >}}

{{< /tabs >}}

