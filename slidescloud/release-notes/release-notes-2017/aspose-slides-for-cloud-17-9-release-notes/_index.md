---
title: "Aspose.Slides for Cloud 17.9 Release Notes"
type: docs
url: /aspose-slides-for-cloud-17-9-release-notes/
weight: 30
---

|**Key**|**Summary**|**Category**|
| :- | :- | :- |
|SLIDESCLOUD-301|Saving presentation as OTP template|Feature|
|SLIDESCLOUD-302|Add EffectFormat property to Shape & Background resources|Feature|
|SLIDESCLOUD-308|Implement Slide resizing|Feature|
|SLIDESCLOUD-296|Use Aspose.Slides for .NET 17.9 features|Feature|
|SLIDESCLOUD-303|Add Reset task to the Pipeline resource|Feature|
|SLIDESCLOUD-304|Add ShowMasterShapes property to slide resource|Feature|
|SLIDESCLOUD-305|Implement InvertedSolidFillColor for Chart Series|Feature|
|SLIDESCLOUD-273|Aspose.Slides fails on loading large files|Bug|
|SLIDESCLOUD-276|Can't retrieve Korean text items|Bug|
## **Public API Changes**
- EffectFormat property is added to shape and background resources. It is a complex type object that represents effects like blur, glow, reflection, soft edge et al.
- SlideSize PUT subresource is added to Presentation resource. It allows to set slide size for the presentation.
- ResestSlide task is added to pipeline resource. It allows to reset a slide in the presentation.
- otp is added to valid values of format parameter for slide and convert resources and for Save task of the pipeline resources. It allows to save or download a slide or a presentation in Open Document Template format.
- InvertedSolidFillColor string property is added to Chart Series type. It allows to get or set the color for inverted values in a series.
- ShowMasterShapes boolean property is added to slide resource. It determines whether shapes from master slide are shown on the slide.
