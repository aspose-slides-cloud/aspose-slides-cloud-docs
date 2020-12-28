---
title: "EffectFormat"
type: docs
url: /effect-format-type/
weight: 10
---

## **EffectFormat Type**
This complex type represents an effect format. Allows to get and set effects such as blur, glow, reflection, soft edge et al.

### **Properties**

| **Property Name** | **Type** | **Description** | 
| :- | :- | :- |  
|  Blur  | [BlurEffect](#blur-effect) | Blur effect.  | 
|  Glow  | [GlowEffect](#glow-effect) | Glow effect.  | 
|  InnerShadow  | [InnerShadowEffect](#inner-shadow-effect) | Inner shadow effect.  | 
|  OuterShadow  | [OuterShadowEffect](#outer-shadow-effect) | Outer shadow effect.  | 
|  PresetShadow  | [PresetShadowEffect](#preset-shadow-effect) | Preset shadow effect.  | 
|  SoftEdge | [SoftEdgeEffect](#soft-edge-effect) | Soft edge effect.  | 
|  Reflection  | [ReflectionEffect](#reflection-effect) | Reflection effect.  | 
|  FillOverlay  | [FillOverlayEffect](#fill-overlay-effect) | Fill overlay effect.  | 

#### Blur Effect
Represents blur effect parameters.

| **Property Name** | **Type** | **Description** | 
| :- | :- | :- |  
| Radius | double | radius  | 
| Grow | bool | true if the bounds are grown  | 

{{< tabs tabTotal="2" tabID="3" tabName1="JSON" tabName2="XML" >}}

{{< tab tabNum="1" >}}
```
{
    "Blur": {
        "Radius": 7.5,
        "Grow": "true"
    }
}
```
{{< /tab >}}

{{< tab tabNum="2" >}}
```
<EffectFormat>
    <Blur>
        <Radius>7.5</Radius>
        <Grow>true</Grow>
    </Blur>
</EffectFormat>
```
{{< /tab >}}

{{< /tabs >}}

#### Glow Effect
Represents glow effect parameters.

| **Property Name** | **Type** | **Description** | 
| :- | :- | :- | 
| Radius | double | radius | 
| Color | string  | color | 

*Color represents hexadecimal triplets representing opacity and colors red, green, and blue (#OORRGGBB). Ex. #FFFF0000 - red color.*

{{< tabs tabTotal="2" tabID="4" tabName1="JSON" tabName2="XML" >}}

{{< tab tabNum="1" >}}
```
{
    "Glow": {
        "Radius": 7.5,
        "Color": "#91FF0000"
    }
}
```
{{< /tab >}}

{{< tab tabNum="2" >}}
```
<EffectFormat>
    <Glow>
        <Radius>7.5</Radius>
        <Color>#91FF0000</Color>
    </Glow>
</EffectFormat>
```
{{< /tab >}}

{{< /tabs >}}

#### Inner Shadow Effect
Represents inner shadow effect parameters.

| **Property Name** | **Type** | **Description** | 
| :- | :- | :- | 
| Direction | float | shadow direction (in 60000ths of a degree)  | 
| Distance | double | specifies how far to offset the shadow  | 
| BlurRadius | double | blur radius  | 
| ShadowColor | string | shadow color  | 

*ShadowColor represents hexadecimal triplets representing opacity and colors red, green, and blue (#OORRGGBB). Ex. #FFFF0000 - red color.*

{{< tabs tabTotal="2" tabID="5" tabName1="JSON" tabName2="XML" >}}

{{< tab tabNum="1" >}}
```
{
    "InnerShadow": {
        "Direction": 9000000,
        "Distance": 12.5,
        "BlurRadius": 7.5,
        "ShadowColor": "#91FF0000"
    }
}
```
{{< /tab >}}

{{< tab tabNum="2" >}}
```
<EffectFormat>
    <InnerShadow>
        <Direction>9000000</Direction>
        <Distance>12.5</Distance>
        <BlurRadius>7.5</BlurRadius>
        <ShadowColor>#91FF0000</ShadowColor>
    </InnerShadow>
</EffectFormat>
```
{{< /tab >}}

{{< /tabs >}}

#### Outer Shadow Effect
Represents outer shadow effect parameters.

| **Property Name** | **Type** | **Description** | 
| :- | :- | :- | 
| Direction | float | shadow direction (in 60000ths of a degree)  | 
| Distance | double | specifies how far to offset the shadow  | 
| BlurRadius | double | blur radius  | 
| ShadowColor | string | shadow color  | 

*ShadowColor represents hexadecimal triplets representing opacity and colors red, green, and blue (#OORRGGBB). Ex. #FFFF0000 - red color.*

{{< tabs tabTotal="2" tabID="6" tabName1="JSON" tabName2="XML" >}}

{{< tab tabNum="1" >}}
```
{
    "OuterShadow": {
        "Direction": 9000000,
        "Distance": 12.5,
        "BlurRadius": 7.5,
        "ShadowColor": "#91FF0000"
    }
}
```
{{< /tab >}}

{{< tab tabNum="2" >}}
```
<EffectFormat>
    <OuterShadow>
        <Direction>9000000</Direction>
        <Distance>12.5</Distance>
        <BlurRadius>7.5</BlurRadius>
        <ShadowColor>#91FF0000</ShadowColor>
    </OuterShadow>
</EffectFormat>
```
{{< /tab >}}

{{< /tabs >}}

#### Preset Shadow Effect
Represents preset shadow effect parameters.

| **Property Name** | **Type** | **Description** | 
| :- | :- | :- | 
| Direction | float | shadow direction (in 60000ths of a degree)  | 
| Distance | double | specifies how far to offset the shadow  | 
| Preset | string | [preset shadow type.](#preset-shadow-type)  | 
| ShadowColor | string | shadow color | 

*ShadowColor represents hexadecimal triplets representing opacity and colors red, green, and blue (#OORRGGBB). Ex. #FFFF0000 - red color.*

##### Preset Shadow Type
{{< expand-list title="Available values for Preset property:" >}}


| **Parameter Value** | **Preset Size Type**  | 
| :- | :- | 
| TopLeftDropShadow | Top Left Drop Shadow  | 
| TopLeftLargeDropShadow | Top Left Large Drop Shadow  | 
| BackLeftLongPerspectiveShadow | Back Left Long Perspective Shadow  | 
| BackRightLongPerspectiveShadow | Back Right Long Perspective Shadow  | 
| TopLeftDoubleDropShadow | Top Left Double Drop Shadow  | 
| BottomRightSmallDropShadow | Bottom Right Small Drop Shadow  | 
| FrontLeftLongPerspectiveShadow | Front Left Long Perspective Shadow  | 
| FrontRightLongPerspectiveShadow | Front Right Long Perspective Shadow  | 
| OuterBoxShadow3D | Outer Box Shadow 3D  | 
| InnerBoxShadow3D | Inner Box Shadow 3D  | 
| BackCenterPerspectiveShadow | Back Center Perspective Shadow  | 
| TopRightDropShadow | Top Right Drop Shadow  | 
| FrontBottomShadow | Front Bottom Shadow  | 
| BackLeftPerspectiveShadow | Back Left Perspective Shadow  | 
| BackRightPerspectiveShadow | Back Right Perspective Shadow  | 
| BottomLeftDropShadow | Bottom Left Drop Shadow  | 
| BottomRightDropShadow | Bottom Right Drop Shadow  | 
| FrontLeftPerspectiveShadow | Front Left Perspective Shadow  | 
| FrontRightPerspectiveShadow | Front Right Perspective Shadow  | 
| TopLeftSmallDropShadow | Top Left Small Drop Shadow  | 


{{< /expand-list >}}

{{< tabs tabTotal="2" tabID="7" tabName1="JSON" tabName2="XML" >}}

{{< tab tabNum="1" >}}
```
{
    "PresetShadow": {
        "Direction": 9000000,
        "Distance": 12.5,
        "Preset": "FrontLeftLongPerspectiveShadow",
        "ShadowColor": "#91FF0000"
    }
}
```
{{< /tab >}}

{{< tab tabNum="2" >}}
```
<EffectFormat>
    <PresetShadow>
        <Direction>9000000</Direction>
        <Distance>12.5</Distance>
        <Preset>FrontLeftLongPerspectiveShadow</Preset>
        <ShadowColor>#91FF0000</ShadowColor>
    </PresetShadow>
</EffectFormat>
```
{{< /tab >}}

{{< /tabs >}}

#### Soft Edge Effect
Represents soft edge effect parameters.

| **Property Name** | **Type** | **Description** | 
| :- | :- | :- | 
| Radius | double | radius | 


{{< tabs tabTotal="2" tabID="8" tabName1="JSON" tabName2="XML" >}}

{{< tab tabNum="1" >}}
```
{
    "SoftEdge": {
        "Radius": 12.5
    }
}
```
{{< /tab >}}

{{< tab tabNum="2" >}}
```
<EffectFormat>
    <SoftEdge>
        <Radius>12.5</Radius>
    </SoftEdge>
</EffectFormat>
```
{{< /tab >}}

{{< /tabs >}}

#### Reflection Effect
Represents reflection effect parameters.

| **Property Name** | **Type** | **Description** | 
| :- | :- | :- | 
| Direction | float | shadow direction (in 60000ths of a degree)  | 
| FadeDirection | float | reflection direction (in 60000ths of a degree)  | 
| Distance | double | specifies how far to offset the shadow  | 
| BlurRadius | double | blur radius  | 
| ScaleHorizontal | double | horizontal scaling factor (as percentage)  | 
| ScaleVertical | double | vertical scaling factor (as percentage)  | 
| SkewHorizontal | double | horizontal skew angle (in 60000ths of a degree)  | 
| SkewVertical | double | vertical skew angle (in 60000ths of a degree)  | 
| StartPosAlpha | float | start position of the start alpha value (as percentage)  | 
| EndPosAlpha | float | end position of the end alpha value (as percentage)  | 
| StartReflectionOpacity | float | starting reflection opacity (as percentage)  | 
| EndReflectionOpacity | float | ending reflection opacity (as percentage)  | 
| RectangleAlign | string | [shadow alignment](#rectangle-align-values) | 
| RotateShadowWithShape | bool | specifies whether reflection should rotate when the shape is rotated   | 


##### Rectangle Align Values
{{< expand-list title="Available values for RectangleAlign property:" >}}


| **Parameter Value** | **Alignment**  | 
| :- | :- | 
| TopLeft |  Top Left  | 
| Top | Top  | 
| TopRight | Top Right  | 
| Left | Left  | 
| Center | Center  | 
| Right | Right  | 
| BottomLeft | Bottom Left  | 
| Bottom | Bottom  | 
| BottomRight | Bottom Right  | 


{{< /expand-list >}}

{{< tabs tabTotal="2" tabID="9" tabName1="JSON" tabName2="XML" >}}

{{< tab tabNum="1" >}}
```
{
    "Reflection": {
        "BlurRadius": 6350,
        "StartReflectionOpacity": 50000,
        "EndReflectionOpacity": 300,
        "EndPosAlpha": 90000,
        "Direction": 5400000,
        "SkewVertical": -100000,
        "RectangleAlign": "BottomLeft",
        "RotateWithShape": false
    }
}
```
{{< /tab >}}

{{< tab tabNum="2" >}}
```
<EffectFormat>
    <Reflection>
        <BlurRadius>6350</BlurRadius>
        <StartReflectionOpacity>50000</StartReflectionOpacity>
        <EndReflectionOpacity>300</EndReflectionOpacity>
        <EndPosAlpha>90000</EndPosAlpha>
        <Direction>5400000</Direction>
        <SkewVertical>-100000</SkewVertical>
        <RectangleAlign>BottomLeft</RectangleAlign>
        <RotateWithShape>false</RotateWithShape>
    </Reflection>
</EffectFormat>
```
{{< /tab >}}

{{< /tabs >}}

#### Fill Overlay Effect
Represents fill overlay effect parameters.

| **Property Name** | **Type** | **Description** | 
| :- | :- | :- | 
| Blend  | string  | [Fill blend mode](#fill-blend-mode)  | 

##### Rectangle Align Values
{{< expand-list title="Available values for Blend property:" >}}

| **Parameter Value** | **Blend Mode**  | 
| :- | :- | 
| Darken | Darken  | 
| Lighten | Lighten  | 
| Multiply | Multiply  | 
| Overlay | Overlay  | 
| Screen | Screen  | 

{{< /expand-list >}}

{{< tabs tabTotal="2" tabID="10" tabName1="JSON" tabName2="XML" >}}

{{< tab tabNum="1" >}}
```
{
    "Reflection": {
        "FillOverlay": "Lighten"
    }
}
```
{{< /tab >}}

{{< tab tabNum="2" >}}
```
<EffectFormat>
    <FillOverlay>
        <Blend>Lighten</Blend>
    </FillOverlay>
</EffectFormat>
```
{{< /tab >}}

{{< /tabs >}}
