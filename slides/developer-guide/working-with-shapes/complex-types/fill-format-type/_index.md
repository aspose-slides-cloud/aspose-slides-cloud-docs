---
title: "FillFormat"
keywords:
- PowerPoint
- presentation
- REST API
- cloud API
- fill
- fill format
type: docs
url: /fill-format-type/
weight: 20
---

## **FillFormat Type**
This complex type represents a fill format. There are 5 different types of fill format:

- [NoFill](#no-fill)
- [SolidFill](#solid-fill)
- [GradientFill](#gradient-fill)
- [PatternFill](#pattern-fill)
- [NoFill](#picture-fill)

### No Fill
Represents FillFormat with no fill.

{{< tabs tabTotal="2" tabID="1" tabName1="JSON" tabName2="XML" >}}

{{< tab tabNum="1" >}}
```
{ "Type": "NoFill" }
```
{{< /tab >}}

{{< tab tabNum="2" >}}
```
<FillFormat xsi:type="NoFill" />
```
{{< /tab >}}

{{< /tabs >}}

### Solid Fill
Represents FillFormat with solid color fill.

| **Property Name** | **Type** | **Description** |
| :- | :- | :- | 
| Color   | string  |  Solid color. |

*Color represents hexadecimal triplets representing opacity and colors red, green, and blue (#OORRGGBB). Ex. #FFFF0000 - red color.*

{{< tabs tabTotal="2" tabID="2" tabName1="JSON" tabName2="XML" >}}

{{< tab tabNum="1" >}}
```
{"Type":"Solid","Color":"#FF385D8A"}
```
{{< /tab >}}

{{< tab tabNum="2" >}}
```
<FillFormat xsi:type="SolidFill">
   <Color>#91FF0000</Color>
</FillFormat>
```
{{< /tab >}}

{{< /tabs >}}

### **Gradient Fill**
Represents FillFormat with gradient color fill.

| **Property Name** | **Type** | **Description** |
| :- | :- | :- | 
| Direction |NotDefined / FromCorner1 / FromCorner2 / FromCorner3 / FromCorner4 / FromCenter | Gradient direction. |
| Shape | NotDefined / Linear / Rectangle / Radial / Path | Gradient shape type. |
| LinearAngle | float | Linear gradient angle. |
| IsScaled | bool | Is linear gradient scaled. |
| TileFlip | NotDefined / NoFlip / FlipX / FlipY / FlipBoth | Gradient tile type. |
| Stops | List | List of [GradientStop](#gradient-stop) items. |

#### **Gradient Stop**
| **Property Name** | **Type** | **Description** |
| :- | :- | :- | 
| Position | float | The relative (0..1) offset of gradient stop. |
| Color | string | Solid color. |

*Color represents hexadecimal triplets representing opacity and colors red, green, and blue (#OORRGGBB). Ex. #FFFF0000 - red color.*

{{< tabs tabTotal="2" tabID="3" tabName1="JSON" tabName2="XML" >}}

{{< tab tabNum="1" >}}
```
{
  "Type": "Gradient",
  "Direction": "NotDefined",
  "Shape": "Linear",
  "Stops": [
      {
          "Color": "#FF03D4A8",
          "Position": 0.0099999997764825821
      },
      {
          "Color": "#FF21D6E0",
          "Position": 0.25
      },
      {
          "Color": "#FF0087E6",
          "Position": 0.75
      },
      {
          "Color": "#FF005CBF",
          "Position": 1.0
      }
  ],
  "LinearAngle": 50.0,
  "IsScaled": false,
  "TileFlip": "NoFlip"
}
```
{{< /tab >}}

{{< tab tabNum="2" >}}
```
<FillFormat xsi:type="GradientFill">
  <Direction>NotDefined</Direction>
  <Shape>Linear</Shape>
  <Stops>
    <Color>#FF03D4A8</Color>
    <Position>0.0099999997764825821</Position>
  </Stops>
  <Stops>
    <Color>#FF21D6E0</Color>
    <Position>0.25</Position>
  </Stops>
  <Stops>
    <Color>#FF0087E6</Color>
    <Position>0.75</Position>
  </Stops>
  <Stops>
    <Color>#FF005CBF</Color>
    <Position>1</Position>
  </Stops>
  <LinearAngle>50</LinearAngle>
  <IsScaled>false</IsScaled>
  <TileFlip>NoFlip</TileFlip>
</FillFormat>
```
{{< /tab >}}

{{< /tabs >}}

### Pattern Fill
Represents FillFormat with pattern color fill.

| **Property Name** | **Type** | **Description** |
| :- | :- | :- | 
| BackColor | string | Background solid color. | 
| ForeColor | string | Foreground solid color. | 
| Style | enum | Style of the pattern. |

*Color represents hexadecimal triplets representing opacity and colors red, green, and blue (#OORRGGBB). Ex. #FFFF0000 - red color.*

{{< expand-list title="Style Values:" >}}

- NotDefined
- Unknown
- Percent05
- Percent10
- Percent20
- Percent25
- Percent30
- Percent40
- Percent50
- Percent60
- Percent70
- Percent75
- Percent80
- Percent90
- DarkHorizontal
- DarkVertical
- DarkDownwardDiagonal
- DarkUpwardDiagonal
- SmallCheckerBoard
- Trellis
- LightHorizontal
- LightVertical
- LightDownwardDiagonal
- LightUpwardDiagonal
- SmallGrid
- DottedDiamond
- WideDownwardDiagonal
- WideUpwardDiagonal
- DashedUpwardDiagonal
- DashedDownwardDiagonal
- NarrowVertical
- NarrowHorizontal
- DashedVertical
- DashedHorizontal
- LargeConfetti
- LargeGrid
- HorizontalBrick
- LargeCheckerBoard
- SmallConfetti
- Zigzag
- SolidDiamond
- DiagonalBrick
- OutlinedDiamond
- Plaid
- Sphere
- Weave
- DottedGrid
- Divot
- Shingle
- Wave
- Horizontal
- Vertical
- Cross
- DownwardDiagonal
- UpwardDiagonal
- DiagonalCross

{{< /expand-list >}}

{{< tabs tabTotal="2" tabID="4" tabName1="JSON" tabName2="XML" >}}

{{< tab tabNum="1" >}}
```
{
    "Type": "Pattern",
    "BackColor": "#FFFFFFFF",
    "ForeColor": "#FF000000",
    "Style": "Percent90"
}
```
{{< /tab >}}

{{< tab tabNum="2" >}}
```
<FillFormat xsi:type="PatternFill">
  <BackColor>#FFFFFFFF</BackColor>
  <ForeColor>#FF000000</ForeColor>
  <Style>Percent90</Style>
</FillFormat>
```
{{< /tab >}}

{{< /tabs >}}

### Picture Fill
Represents FillFormat with picture fill.

|**Property Name**|**Type**|**Description**|
| :- | :- | :- | 
| CropBottom | float | Relative (0..1) crop from bottom. |
| CropLeft | float | Relative (0..1) crop from left. |
| CropRight | float | Relative (0..1) crop from right. |
| CropTop | float | Relative (0..1) crop from top. |
| Dpi | int | Image Dpi if set. |
| PictureFillMode | Tile / Stretch | Fill mode of picture. |
| Image | Resource | Link to the Image picture format referenced to. In operations for update background, shape fill or create picture can be used to refer to the existing image in the presentation instead of Base64Data or SvgData |
| Base64Data | string | Used only in operations for update background, shape fill, or create pictures. Represents a base64 encoded picture. In GET operations this property is omitted |
| SvgData | string | Used only in operations for update background, shape fill, or create pictures. Represents an SVG image. In GET operations this property is omitted. Ignored if Base64Data is specified |
| Resolution | float | Used only in operations for update background, shape fill, or create pictures. Prescribes to compress the image at the specified resolution (in Dpi). |
| DeletePictureCroppedAreas | boolean | Used only in operations for update background, shape fill, or create pictures. If set to true, prescribes to delete picture cropped areas. |

{{< tabs tabTotal="2" tabID="5" tabName1="JSON" tabName2="XML" >}}

{{< tab tabNum="1" >}}
```
{
    "Type": "Picture",
    "CropBottom": 0.0,
    "CropLeft": 0.0,
    "CropRight": 0.0,
    "CropTop": 0.0,
    "Dpi": 0,
    "Image": {
        "Uri": {
            "Href": "https://api.aspose.com/v3.0/slides/myPresentation.pptx/images/1",
            "Relation": "self"
        }
    },
    "PictureFillMode": "Tile"
}
```
{{< /tab >}}

{{< tab tabNum="2" >}}
```
<FillFormat xsi:type="PictureFill">
  <CropBottom>0</CropBottom>
  <CropLeft>0</CropLeft>
  <CropRight>0</CropRight>
  <CropTop>0</CropTop>
  <Dpi>0</Dpi>
  <Image>
    <link href="https://api.aspose.com/v3.0/slides/myPresentation.pptx/images/1" rel="self" />
  </Image>
  <PictureFillMode>Tile</PictureFillMode>
</FillFormat>
```
{{< /tab >}}

{{< /tabs >}}














