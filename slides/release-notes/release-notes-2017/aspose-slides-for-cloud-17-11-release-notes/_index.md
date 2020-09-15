---
title: "Aspose.Slides for Cloud 17.11 Release Notes"
type: docs
url: /aspose-slides-for-cloud-17-11-release-notes/
weight: 10
---

## **New Features and Enhancements**
- SLIDESCLOUD-317 - Text portion formatting
- SLIDESCLOUD-318 - Support ParagraphFormat properties
- SLIDESCLOUD-298 - Use Aspose.Slides for .NET 17.11 features
- SLIDESCLOUD-335 - Delete shapes by index list
- SLIDESCLOUD-340 - Generate proper HttpStatusCode values




## **Public API Changes**
- DELETE method is added to shapes resource to delete a set of shapes from a shape list. You can delete all shapes or specify (comma-separated) indices of shapes using optional shapes parameter.
- PUT method is added to paragraph resource to set paragraph properties such as margin, spacing, text alignment et al.
- MarginLeft, MarginRight, SpaceBefore, SpaceAfter, SpaceWithin, Indent, Alignment, FontAlignment, DefaultTabSize, Depth, BulletChar, BulletHeight, BulletType, NumberedBulletStartWith, NumberedBulletStyle, HangingPunctuation, EastAsianLineBreak, LatinLineBreak, RightToLeft properties are added to paragraph resource. They allow to get and set formatting properties of a paragraph such as margins, alignment, bulleting et al.
- FontBold, FontItalic, FontUnderline, StrikethroughType, TextCapType, Escapement, Spacing, HighlightColor, NormaliseHeight, ProofDisabled, SmartTagClean, KerningMinimalSize, Kumimoji, LanguageId,AlternativeLanguageId, IsHardUnderlineFill, IsHardUnderlineLine, FillFormat, EffectFormat, LineFormat, UnderlineFillFormat, UnderlineLineFormat properties are added to portion resource. They allow to get and set formatting properties of a text portion such as font weight, style, decoration et al.
