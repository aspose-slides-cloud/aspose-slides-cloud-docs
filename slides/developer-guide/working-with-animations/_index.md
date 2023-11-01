---
title: "Working with Animations"
type: docs
url: /working-with-animations/
weight: 40
---

## **Introduction**
Aspose.Slides Cloud allows you to read and modify animations in a PowerPoint slide. The resource properties are explained below
### **Resource Properties**

|**Property Name**|**Type**|**Description**|
| :- | :- | :- |
|MainSequence|Effect array|The list of main sequence effects.|
|InteractiveSequences|InteractiveSequence array|The list of interactive sequences.|

#### **InteractiveSequence properties**

|**Property Name**|**Type**|**Description**|
| :- | :- | :- |
|Effects|Effect array|The list of sequence effects.|
|TriggerShapeIndex|int|The index of the shape that triggers the sequence.|
#### **Effect properties**

|**Property Name**|**Type**|**Description**|
| :- | :- | :- |
|Type|EffectType enum|Effect type.|
|Subtype|Subtype enum|Effect subtype.|
|PresetClassType|EffectPresetClassType enum|Preset class type.|
|ShapeIndex|int|The index of the shape to which the effect applies.|
|ParagraphIndex|int|The index of the paragraph to which the effect applies.|
|TriggerType|EffectTriggerType enum|Effect trigger type.|
|Accelerate|float|The percentage of duration accelerate behavior effect.|
|Decelerate|float|The percentage of duration decelerate behavior effect.|
|AutoReverse|bool|True to automatically play the animation in reverse after playing it in the forward direction.|
|Duration|float|The duration of animation effect.|
|RepeatCount|float|The number of times the effect should repeat.|
|RepeatDuration|float|The duration at which the effect should repeat.|
|Restart|enum|The way for a effect to restart after complete.|
|Speed|float|The percentage by which to speed up (or slow down) the timing.|
|TriggerDelayTime|float|Delay time after trigger.|
#### **EffectType, EffectSubtype and EffectPresetClassType**

|**Type**|**Valid subtypes**|**Valid classes**|
| :- | :- | :- |
|Appear|None|Entrance or Exit|
|CurveUpDown|None|Entrance or Exit|
|Ascend|None|Entrance or Exit|
|Blast|None|Emphasis|
|Blinds|Horizontal or Vertical|Entrance or Exit|
|Blink|None|Emphasis|
|BoldFlash|None|Emphasis|
|BoldReveal|None|Emphasis|
|Boomerang|None|Entrance or Exit|
|Bounce|None|Entrance or Exit|
|Box|In or Out|Entrance or Exit|
|BrushOnColor|None|Emphasis|
|BrushOnUnderline|None|Emphasis|
|CenterRevolve|None|Entrance or Exit|
|ChangeFillColor|Instant, Gradual, GradualAndCycleClockwise or GradualAndCycleCounterClockwise|Emphasis|
|ChangeFont|Instant or Gradual|Emphasis|
|ChangeFontColor|Instant, Gradual, GradualAndCycleClockwise or GradualAndCycleCounterClockwise|Emphasis|
|ChangeFontSize|Instant or Gradual|Emphasis|
|ChangeFontStyle|FontBold, FontItalic or FontUnderline|Emphasis|
|ChangeLineColor|Instant, Gradual, GradualAndCycleClockwise or GradualAndCycleCounterClockwise|Emphasis|
|Checkerboard|Vertical or Across|Entrance or Exit|
|Circle|In or Out|Entrance or Exit|
|ColorBlend|None|Emphasis|
|ColorTypewriter|None|Entrance or Exit|
|ColorWave|None|Emphasis|
|ComplementaryColor|None|Emphasis|
|ComplementaryColor2|None|Emphasis|
|Compress|None|Entrance or Exit|
|ContrastingColor|None|Emphasis|
|Crawl|Right, Left, Top or Bottom|Entrance or Exit|
|Credits|None|Entrance or Exit|
|Credits|None|Entrance or Exit|
|Darken|None|Emphasis|
|Desaturate|None|Emphasis|
|Descend|None|Entrance or Exit|
|Diamond|In or Out|Entrance or Exit|
|Dissolve|None|Entrance or Exit|
|EaseInOut|None|Entrance or Exit|
|Expand|None|Entrance or Exit|
|Fade|None|Entrance or Exit|
|FadedSwivel|None|Entrance or Exit|
|FadedZoom|None|Entrance or Exit|
|FlashBulb|None|Emphasis|
|FlashOnce|None|Entrance or Exit|
|FlashBulb|None|Emphasis|
|Flicker|None|Emphasis|
|Flip|None|Entrance or Exit|
|Float|None|Entrance or Exit|
|Fly|Right, Left, Top, Bottom, TopLeft, TopRight, BottomLeft or BottomRight|Entrance or Exit|
|Fold|None|Entrance or Exit|
|Glide|None|Entrance or Exit|
|GrowAndTurn|None|Entrance or Exit|
|GrowShrink|None|Emphasis|
|GrowWithColor|None|Emphasis|
|Lighten|None|Emphasis|
|LightSpeed|None|Entrance or Exit|
|MediaPause|None|Media (applicable to video frames and audio frames)|
|MediaPlay|None|Media (applicable to video frames and audio frames)|
|MediaStop|None|Media (applicable to video frames and audio frames)|
|Path4PointStar|None|Path|
|Path5PointStar|None|Path|
|Path6PointStar|None|Path|
|Path8PointStar|None|Path|
|PathArcDown|None|Path|
|PathArcLeft|None|Path|
|PathArcRight|None|Path|
|PathArcUp|None|Path|
|PathBean|None|Path|
|PathBounceLeft|None|Path|
|PathBounceRight|None|Path|
|PathBuzzsaw|None|Path|
|PathCircle|None|Path|
|PathCrescentMoon|None|Path|
|PathCurvedSquare|None|Path|
|PathCurvedX|None|Path|
|PathCurvyLeft|None|Path|
|PathCurvyRight|None|Path|
|PathCurvyStar|None|Path|
|PathDecayingWave|None|Path|
|PathDiagonalDownRight|None|Path|
|PathDiagonalUpRight|None|Path|
|PathDiamond|None|Path|
|PathDown|None|Path|
|PathEqualTriangle|None|Path|
|PathFigure8Four|None|Path|
|PathFootball|None|Path|
|PathFunnel|None|Path|
|PathHeart|None|Path|
|PathHeartbeat|None|Path|
|PathHexagon|None|Path|
|PathHorizontalFigure8|None|Path|
|PathInvertedSquare|None|Path|
|PathInvertedTriangle|None|Path|
|PathLeft|None|Path|
|PathLoopdeLoop|None|Path|
|PathNeutron|None|Path|
|PathOctagon|None|Path|
|PathParallelogram|None|Path|
|PathPeanut|None|Path|
|PathPentagon|None|Path|
|PathPlus|None|Path|
|PathPointyStar|None|Path|
|PathRight|None|Path|
|PathRightTriangle|None|Path|
|PathSCurve1|None|Path|
|PathSCurve2|None|Path|
|PathSineWave|None|Path|
|PathSpiralLeft|None|Path|
|PathSpiralRight|None|Path|
|PathSpring|None|Path|
|PathSquare|None|Path|
|PathStairsDown|None|Path|
|PathSwoosh|None|Path|
|PathTeardrop|None|Path|
|PathTrapezoid|None|Path|
|PathTurnDown|None|Path|
|PathTurnRight|None|Path|
|PathTurnUp|None|Path|
|PathTurnUpRight|None|Path|
|PathUp|None|Path|
|PathWave|None|Path|
|PathZigzag|None|Path|
|Peek|None|Entrance or Exit|
|Pinwheel|None|Entrance or Exit|
|Plus|In or Out|Entrance or Exit|
|RandomBars|Horizontal or Vertical|Entrance or Exit|
|RandomEffects|None|Entrance or Exit|
|RizeUp|None|Entrance|
|Shimmer|None|Emphasis|
|Sling|None|Entrance or Exit|
|Spin|None|Emphasis|
|Spinner|None|Emphasis|
|Spiral|None|Entrance or Exit|
|Split|HorizontalIn, HorizontalOut, VerticalIn or VerticalOut|Entrance or Exit|
|Stretch|Right, Left, Top, Bottom or Across|Entrance or Exit|
|Strips|UpLeft, UpRight, DownLeft or DownRight|Entrance or Exit|
|StyleEmphasis|None|Emphasis|
|Swish|None|Entrance or Exit|
|Swivel|Horizontal or Vertical|Entrance or Exit|
|Teeter|None|Emphasis|
|Thread|None|Emphasis|
|Transparency|None|Emphasis|
|Unfold|None|Entrance or Exit|
|VerticalGrow|None|Emphasis|
|Wave|None|Emphasis|
|Wedge|None|Entrance or Exit|
|Wheel|Wheel1, Wheel2, EffectSubtype.Wheel3, EffectSubtype.Wheel4 or EffectSubtype.Wheel8|None|
|Whip|None|Entrance or Exit|
|Wipe|Right, Left, Top or Bottom|Entrance or Exit|
|Magnify|None|Entrance or Exit|
|Zoom|In, Out, InCenter, OutBottom - only for Entrance class, OutSlightly, InSlightly, OutCenter or InBottom - only for Exit class|Entrance or Exit|
|OLEObjectShow|None|OLEActionVerbs (applicable to OLE object frames)|
|OLEObjectEdit|None|OLEActionVerbs (applicable to OLE object frames)|
|OLEObjectOpen|None|OLEActionVerbs (applicable to OLE object frames)|

### **Resource Demonstration**

- [Read Animation Properties](/slides/read-animation-properties/)
- [Update an Interactive Sequence](/slides/update-an-interactive-sequence/)
- [Update a Main Sequence](/slides/update-a-main-sequence/)
- [Animation on a Special Slide](/slides/animation-on-a-special-slide/)
- [Paragraph Animation](/slides/paragraph-animation/)
