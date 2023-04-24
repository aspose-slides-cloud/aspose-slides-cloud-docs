---
title: "Aspose.Slides Cloud 23.4 Release Notes"
type: docs
url: /aspose-slides-cloud-23-4-release-notes/
weight: 90
---

## **Improvements and Changes**

- **SLIDESCLOUD-967** Add methods to modify table elements (columns & rows)
- **SLIDESCLOUD-1727** Enable manipulating table text at paragraph & portion level
- **SLIDESCLOUD-1728** Enable text formatting at table cell level
- **SLIDESCLOUD-1729** Add methods to add/delete table elements (columns & rows)

## **Public API changes**

Added **CreateTableRow**, **UpdateTableRow** and **DeleteTableRow** methods to add, update and delete table rows. See [documentation](/slides/working-with-table-rows/) for more info.

Added **UpdateTableCell** method to update table cells. See [documentation](/slides/update-table-cell/) for more info.

Added  **MergeTableCells** and **SplitTableCell** methods to merge &amp; split table cells. See [documentation](/slides/merge-table-cells/) for more info.

Added methods to get, add, modify and delete paragraphs & portions within table cells: **GetTableCellParagraph**, **GetTableCellParagraphs**, **GetTableCellPortion**, **GetTableCellPortions**, **CreateTableCellParagraph**, **CreateTableCellPortion**, **UpdateTableCellPortion**, **UpdateTableCellParagraph**, **DeleteTableCellParagraph**,  **DeleteTableCellPortion**. See [documentation](/slides/working-with-table-cell-text/) for more info.

New **TextFrameFormat** property in **TableCell** class allows to specify text format for table cells.