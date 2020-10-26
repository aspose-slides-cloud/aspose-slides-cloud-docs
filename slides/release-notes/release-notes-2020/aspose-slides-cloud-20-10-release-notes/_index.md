---
title: "Aspose.Slides Cloud 20.10 Release Notes"
type: docs
url: /aspose-slides-cloud-20-10-release-notes/
weight: 12
---

{{% alert color="primary" %}}

The page contains release notes for Aspose.Slides Cloud 20.10 – [API Reference](https://apireference.aspose.cloud/slides/)

{{% /alert %}}

## **Other improvements and changes**

- SLIDESCLOUD-1023 Remove redundant ResourceUriElement
- SLIDESCLOUD-855 Refactor Type & ShapeType properies for Shape
- SLIDESCLOUD-912 Make nullable parameter optional in Swift SDK requests
- SLIDESCLOUD-810 Remove semicolon from downloaded file names in SDKs

## **Public API changes**

### **1. ResourceUriElement Excluded**
***ResourceUriElement*** class contained a single ***ResourceUri*** property. Now it is replaced directly by ***ResourceUri*** to avoid excessive nesting.
#### **2. ShapeType property excluded**
***ShapeType*** property duplicated ***GeometryShapeType*** for geometry shapes, and ***Type*** property for all the rest. Thus it was redundant and is now excluded for all shapes except ***GeometryShape***. For ***GeometryShape****, ***GeometryShapeType*** is excluded.
