---
title: "Aspose.Slides for Cloud 1.6.0 Release Notes"
type: docs
url: /aspose-slides-for-cloud-1-6-0-release-notes/
weight: 50
---

We are pleased to announce the release of Aspose.Slides for Cloud 1.6.0 with following improvements.
### **Major Changes**

|**Key** |**Summary** |**Category** |
| :- | :- | :- |
|SAASSLIDES-164 |Add support for tables |New Feature |
|SAASSLIDES-203 |Add support for PictureFrame |New Feature |
### **API Changes**

New resource Image has been added. It allows export individual image in specified format.

Property **ContentType** has been added to each **Image** DTO in Images resource.

Property **Base64Data** has been added to class **PictureFill**. It allows change fill of a shape, pictureFrame or background of a slide.

POST method of **Shapes** resource can receive **PictureFrame** DTO to add new pictures into slide.

Property **PictureFillFormat** added to **PictureFrame** DTO. It represents image of the picture frame and allows GET picture info or update bitmap providing base64 data or relative link in PUT request.

POST method of **Shapes** resource can receive **Table** DTO to add new table into slide.

**Table** class has been extended to hold columns and rows information of the table. Table can be updated in PUT request like any other shape.


