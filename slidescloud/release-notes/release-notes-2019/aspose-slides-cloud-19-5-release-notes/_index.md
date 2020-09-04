---
title: "Aspose.Slides Cloud 19.5 release notes"
type: docs
url: /aspose-slides-cloud-19-5-release-notes/
weight: 70
---

## **New features**
- SLIDESCLOUD-561 - Implement Aspose.Slides as containerized microservice
- SLIDESCLOUD-457 - Animation API
## **Public API changes**
- Aspose.Slides for Cloud 19.5 uses cloud API v3.0. Use [https:/api.aspose.cloud/v3.0/slides](http://https/api.aspose.cloud/v3.0/slides) instead of [http:/api.aspose.cloud/v1.1/slides](http://http/api.aspose.cloud/v1.1/slides). Cloud API v1.1, including Slides for Cloud v19.4, will remain available.
- Storage API is now available as part of Slides API.
- Animation API has been added. You can use the following methods /slides/[pres.pptx/slides/](http://pres.pptx/slides/)index/animation resource and subresources to manage animation.
- **format** query string parameter and **saveAs** resource are replaced by **format** path parameter.
  E.g.instead of GET /slides/pres.pptx?format=pdf use GET /slides/[pres.pptx/pdf](http://pres.pptx/pdf).
  instead of POST /slides/[pres.pptx/slides/1?format=pdf](http://pres.pptx/slides/1?format=pdf) and /slides/[pres.pptx/slides/1/saveas/pdf](http://pres.pptx/slides/1/saveas/pdf) use /slides/[pres.pptx/slides/1/saveas/pdf](http://pres.pptx/slides/1/saveas/pdf)
  This applies to presentation, slide, notes slide, shape and image.
  Format in **convert** resource is also specified in path instead of query.
  I.e. instead of /slides/convert?format=pdf use /slides/convert/pdf
  To download image as is, use /slides/{name}/images/{index} resource.
  To download image in a specified format, use /slides/{name}/images/{index}/{format} instead of /slides/{name}/images/{index}?format={format}
- a new PUT method is created for presesentation download, slide download, notes slide download, shape download and convert resources. It has a mandatory **outPath** field and saves conversion result to storage t the specified path. **outPath** is no longer available for POST method of these resources.
  I.e. instead of POST /slides/[mypres.pptx/saveas/pdf?outpath=myfolder/mypres.pdf](http://mypres.pptx/saveas/pdf?outpath=myfolder/mypres.pdf) use PUT /slides/[mypres.pptx/saveas/pdf?outpath=myfolder/mypres.pdf](http://mypres.pptx/saveas/pdf?outpath=myfolder/mypres.pdf).
- **presentation** POST method id used to create empty presentations or presentations from template in request body.
- **fromSource** subresource is added to **presentation** resource. Its POST method allows to create presentations using templates from the storage.
- **fromTemplate** subresource is added to **presentation** resource. Its POST resource allows to create presentations from templates and XML data using template engine.
- PUT method is added to **fromHtml** resource to update existing presentations. POST method now only creates new documents.
  I.e.
  to create an empty presentation, instead of PUT /slides/mypres.pptx use POST /slides/mypres.pptx.
  to create a presentation from data in request body, instead of PUT /slides/mypres.pptx use POST /slides/mypres.pptx.
  to create a presentation from a template on storage, instead of PUT /slides/mypres.pptx?templatePath=template.potx use POST /slides/[mypres.pptx/fromsource?sourcePath=template.potx](http://mypres.pptx/fromsource?sourcePath=template.potx).
  to create a presentation from a template and XML data, instead of POST /slides/mypres.pptx?templatePath=template.potx use POST /slides/[mypres.pptx/fromTemplate?templatePath=template.potx](http://mypres.pptx/fromTemplate?templatePath=template.potx)
  to create a presentation from html, use POST /slides/[mypres.pptx/fromHtml](http://mypres.pptx/fromHtml), as before
  to update a presentation from html, instead of POST /slides/[mypres.pptx/fromHtml](http://mypres.pptx/fromHtml), use PUT /slides/[mypres.pptx/fromHtml](http://mypres.pptx/fromHtml).
- POST method for **slide** resources only adds new slides. Use subresources for all the rest. **add** subresource is removed from **slide** resource.
  I.e.
  to add a new slide, only POST slides/[mypres.pptx/slides](http://mypres.pptx/slides) method is available. POST slides/[mypres.pptx/slides/add](http://mypres.pptx/slides/add) method is removed.
  to clone a new slide, only POST slides/[mypres.pptx/slides/copy](http://mypres.pptx/slides/copy) method is available. You can no longer use POST slides/[mypres.pptx/slides](http://mypres.pptx/slides) method with **slideToClone** and **source** query parameters.
  to reorder a slide, only POST slides/mypres.pptx/slides/{index}/move method is available. You can no longer use POST slides/[mypres.pptx/slides](http://mypres.pptx/slides) method with **oldPosition** and **newPosition** query parameters.
  to reorder multiple slides, only POST slides/[mypres.pptx/slides/reorder](http://mypres.pptx/slides/reorder) method is available. You can no longer use POST slides/[mypres.pptx/slides](http://mypres.pptx/slides) with **oldPositions** and **newPositions** query parameters.
- **backgroundColor** subresource is added to **slide** resource. To specify a background color for a slide, use PUT method of this resource.
  i.e. instead of PUT /slides/[mypres.pptx/slides/1/background?color=FFFFCCCC](http://mypres.pptx/slides/1/background?color=FFFFCCCC) use PUT /slides/[mypres.pptx/slides/1/backgroundColor?color=FFFFCCCC](http://mypres.pptx/slides/1/backgroundColor?color=FFFFCCCC)
  To set slide background properties from background DTO in request body, use **background** resource as earlier.
- All response objects have the following changes:
  - **Code** and **Status** properties are removed. Inspect HTTP response to retrieve them.
  - the data properties are moved level up. Their properties are now root properties of response DTO. These removed data properties are,
    - **Document** in document response, also in presentation string replace response.
    - **Slides** in slides response.
    - **Slide** in slide response, also in slide string replace response.
    - **ShapeList** in shapes response.
    - **Shape** in shape response.
    - **Paragraphs** in paragraphs response.
    - **Paragraph** in paragraph response.
    - **Portions** in portions response.
    - **Portion** in portion response.
    - **Images** in images response.
    - **Image** in image response.
    - **Placeholders** in placeholders response.
    - **Placeholder** in placeholder response.
    - **DocumentProperties** in document properties response.
    - **DocumentProperty** in document property response.
    - **Background** in slide background response.
    - **SlideComments** in slide comments response.
    - **SplitResult** in split result response.
    - **TextItems** in text items response.
