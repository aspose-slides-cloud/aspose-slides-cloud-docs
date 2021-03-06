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

curl -v "https://api.aspose.cloud/oauth2/token" -X POST -d "grant_type=client_credentials&client_id=78946fb4-3bd4-4d3e-b309-f9e2ff9ac6f9&client_secret=b125f13bf6b76ed81ee990142d84119"-H "Content-Type: application/x-www-form-urlencoded"-H "Accept: application/json" 

```

```java

curl -v "http://api.aspose.cloud/v1.1/slides/convert?format=pdf&fontsLocation=fonts" --data-binary @sample.pptx  

-X PUT -H "Accept:application/json"  -H "Authorization: Bearer -Ou_UHdVStdZldtjaeFUAowQ3x2KLlSHd5ovZfDtZqpgdC6FLlalPmO8VJ58HXp8sgGhLqMqlnzEzIF2fEhEyJ3D7xzaw_c8cAuk3qoag3g7bghMHw_pe_RTxxJ9r04R9YAGFbbAcoU1ddPvrPz0e1FSakagM42Ie2eA8D1MyBVJ1D-RZJrfebPePuOLvR_hOD8Doqk5SBi_j-efODJK_PmGUxj0onOrUUx8Tj_GuUKrG6DcBnpl84_UykdOP87IeHnT2_NZCHQIgOY0vtfW6AUGfP9jO5W1mBS_q3lthTDRMg2LuZ6s0r9MKlwVJ_n7sn3TUCrr8kGmUB3k0mL0rrd5TSKm7yjx8hhjap43PlFhwk-r9g7guWsuFLoeDqPa4JNJ1NFM54qQvgWKCp5oDj4dZfbc7qhfIelNh1gW4VYwfmgz"

```

{{< /tab >}}

{{< tab tabNum="2" >}}

```java

{response-data}

```

{{< /tab >}}

{{< /tabs >}}

## **SDK Examples**
{{< tabs tabTotal="9" tabID="5" tabName1="C#" tabName2="Java" tabName3="PHP" tabName4="Ruby" tabName5="Python" tabName6="Node.js" tabName7="Android" tabName8="C++" tabName9="Perl" >}}

{{< tab tabNum="1" >}}

{{< gist "" "a41a3c7c75241129b94faf7179d42527" "AddNewSlideWithCustomFont.cs" >}}

{{< /tab >}}

{{< tab tabNum="2" >}}

{{< gist "" "17b08f624ccca40e351e7204e318237e" "AddNewSlideWithCustomFont.java" >}}

{{< /tab >}}

{{< tab tabNum="3" >}}

{{< gist "" "2cc36b05065a88cb0737424e4f38f68e" "AddNewSlideWithCustomFont.php" >}}

{{< /tab >}}

{{< tab tabNum="4" >}}

{{< gist "" "a41a3c7c75241129b94faf7179d42527" "AddNewSlideWithCustomFont.rb" >}}

{{< /tab >}}

{{< tab tabNum="5" >}}

{{< gist "" "88b9472c3f741eae6c606abdd003c791" "AddNewSlideWithCustomFont.py" >}}

{{< /tab >}}

{{< tab tabNum="6" >}}

{{< gist "" "bc650902bdc45144b1727d329023dcba" "AddNewSlideWithCustomFont.js" >}}

{{< /tab >}}

{{< tab tabNum="7" >}}

{{< gist "" "2b52dabd204b301389d1f4234e9bb0d5" "AddNewSlideWithCustomFont.java" >}}

{{< /tab >}}

{{< tab tabNum="8" >}}

{{< gist "" "a41a3c7c75241129b94faf7179d42527" "Coming_Soon.txt" >}}

{{< /tab >}}

{{< tab tabNum="9" >}}

{{< gist "" "a41a3c7c75241129b94faf7179d42527" "Coming_Soon.txt" >}}

{{< /tab >}}

{{< /tabs >}}
