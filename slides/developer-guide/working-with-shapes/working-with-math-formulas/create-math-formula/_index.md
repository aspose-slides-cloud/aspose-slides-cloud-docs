---
title: "Create a Math Formula"
type: docs
url: /create-math-formula/
weight: 10
---

## **Introduction**
A math formula (equation) is a kind of portion. So, you add formulas just like you add ordinary portion to your shape. The difference is that you have to set the portion's **MathParagraph** property.

### **cURL Example**
{{< tabs tabTotal="2" tabID="1" tabName1="Request" tabName2="Response" >}}

{{< tab tabNum="1" >}}

**Create Request Token**

```java
curl -X POST "https://api.aspose.cloud/connect/token" -d "grant_type=client_credentials&client_id=MyClientId&client_secret=MyClientSecret" -H "Content-Type: application/x-www-form-urlencoded" -H "Accept: application/json"
```

**Add Portion**

```java
curl -X POST "https://api.aspose.cloud/v3.0/slides/MyPresentation.pptx/slides/1/shapes/2/paragraphs/3/portions" -d "@portion.json" -H "Content-Type: text/json" -H "Authorization: Bearer AuthToken"
```

**portion.json example**

```javascript
{
    "mathParagraph": {
        "mathBlockList": [
            {
                "type": "Block",
                "mathElementList": [
                    {
                        "type": "Function",
                        "name": {
                            "type": "Limit",
                            "base": {
                                "type": "Text",
                                "value": "lim"
                            },
                            "limit": {
                                "type": "Text",
                                "value": "x->0"
                            }
                        },
                        "base": {
                            "type": "Fraction",
                            "numerator": {
                                "type": "Function",
                                "name": {
                                    "type": "Text",
                                    "value": "sin"
                                },
                                "base": {
                                    "type": "Text",
                                    "value": "x"
                                },
                            },
                            "denominator": {
                                "type": "Text",
                                "value": "x"
                            }
                        }
                    }
                ]
            }
        ]
    }
}
```

{{< /tab >}}

{{< tab tabNum="2" >}}

```javascript
{
    "text": "",
    "mathParagraph": {
        "mathBlockList": [
            {
                "type": "Block",
                "mathElementList": [
                    {
                        "type": "Function",
                        "name": {
                            "type": "Limit",
                            "base": {
                                "type": "Text",
                                "value": "lim"
                            },
                            "limit": {
                                "type": "Text",
                                "value": "x->0"
                            }
                        },
                        "base": {
                            "type": "Fraction",
                            "numerator": {
                                "type": "Function",
                                "name": {
                                    "type": "Text",
                                    "value": "sin"
                                },
                                "base": {
                                    "type": "Text",
                                    "value": "x"
                                },
                            },
                            "denominator": {
                                "type": "Text",
                                "value": "x"
                            }
                        }
                    }
                ]
            }
        ]
    },
    "fontColor": "#FF000000",
    "highlightColor": "#0",
    "fontHeight": 18,
    "selfUri": {
        "href": "https://api.aspose.cloud/v3.0/slides/MyPresentation.pptx/slides/1/shapes/2/paragraphs/3/portions/1",
        "relation": "self"
    }
}
```

{{< /tab >}}

{{< /tabs >}}
## **SDKs**
Using an SDK (API client) is the quickest way for a developer to speed up the development. An SDK takes care of a lot of low-level details of making requests and handling responses and lets you focus on writing code specific to your particular project. Check out our [GitHub repository](https://github.com/aspose-slides-cloud) for a complete list of Aspose.Slides Cloud SDKs along with working examples, to get you started in no time. Please check [Available SDKs](/slides/available-sdks/) article to learn how to add an SDK to your project.
### **SDK Examples**
{{< tabs tabTotal="10" tabID="5" tabName1="C#" tabName2="Java" tabName3="PHP" tabName4="Ruby" tabName5="Python" tabName6="Node.js" tabName7="Go" tabName8="C++" tabName9="Perl" tabName10="Swift" >}}

{{< tab tabNum="1" >}}

```csharp
string fileName = "MyPresentation.pptx";
int slideIndex = 1;
int shapeIndex = 2;
int paragraphIndex = 1;
SlidesApi api = new SlidesApi("MyClientId", "MyClientSecret");

Portion dto = new Portion
{
    MathParagraph = new MathParagraph
    {
        MathBlockList = new List<BlockElement>
        {
            new BlockElement
            {
                MathElementList = new List<MathElement>
                {
                    new FunctionElement
                    {
                        Name = new LimitElement { Base = new TextElement { Value = "lim" }, Limit = new TextElement { Value = "x->0" } },
                        Base = new FractionElement
                        {
                            Numerator = new FunctionElement { Name = new TextElement { Value = "sin" }, Base = new TextElement { Value = "x" } },
                            Denominator = new TextElement { Value = "x" }
                        }
                    }
                }
            }
        }
    }
};
Portion portion = api.CreatePortion(fileName, slideIndex, shapeIndex, paragraphIndex, dto);
Console.WriteLine(portion.MathParagraph.MathBlockList.Count); //1
```

{{< /tab >}}

{{< tab tabNum="2" >}}

```java
String fileName = "MyPresentation.pptx";
int slideIndex = 1;
int shapeIndex = 2;
int paragraphIndex = 1;
SlidesApi api = new SlidesApi("MyClientId", "MyClientSecret");

Portion dto = new Portion();
MathParagraph mathParagraph = new MathParagraph();
List<BlockElement> mathBlocks = new ArrayList<BlockElement>();
BlockElement blockElement = new BlockElement();
List<MathElement> mathElements = new ArrayList<MathElement>();
FunctionElement functionElement = new FunctionElement();
LimitElement limitElement = new LimitElement();
TextElement text1 = new TextElement();
text1.setValue("lim");
limitElement.setBase(text1);

TextElement text2 = new TextElement();
text2.setValue("x->0");
limitElement.setLimit(text2);
functionElement.setName(limitElement);

FractionElement fractionElement = new FractionElement();
FunctionElement sinusElement = new FunctionElement();
TextElement text3 = new TextElement();
text3.setValue("sin");
sinusElement.setName(text3);

TextElement text4 = new TextElement();
text4.setValue("x");
sinusElement.setBase(text4);
fractionElement.setNumerator(sinusElement);

TextElement text5 = new TextElement();
text5.setValue("x");
limitElement.setLimit(text5);
fractionElement.setDenominator(fractionElement);
functionElement.setBase(fractionElement);
mathElements.add(functionElement);
blockElement.setMathElementList(mathElements);
mathBlocks.add(blockElement);
mathParagraph.setMathBlockList(mathBlocks);
dto.setMathParagraph(mathParagraph);

Portion portion = api.createPortion(fileName, slideIndex, shapeIndex, paragraphIndex, dto, null, null, null, null);
System.out.println(portion.getMathParagraph().getMathBlockList().size()); //1
```

{{< /tab >}}

{{< tab tabNum="3" >}}

```php
use Aspose\Slides\Cloud\Sdk\Api\Configuration;
use Aspose\Slides\Cloud\Sdk\Api\SlidesApi;
use Aspose\Slides\Cloud\Sdk\Model\Portion;
use Aspose\Slides\Cloud\Sdk\Model\MathParagraph;
use Aspose\Slides\Cloud\Sdk\Model\BlockElement;
use Aspose\Slides\Cloud\Sdk\Model\FunctionElement;
use Aspose\Slides\Cloud\Sdk\Model\FractionElement;
use Aspose\Slides\Cloud\Sdk\Model\LimitElement;
use Aspose\Slides\Cloud\Sdk\Model\TextElement;

$config = new Configuration();
$config->setAppSid("MyClientId");
$config->setAppKey("MyClientSecret");
$api = new SlidesApi(null, $config);

$fileName = "MyPresentation.pptx";
$slideIndex = 1;
$shapeIndex = 2;
$paragraphIndex = 1;

$dto = new Portion();
$math = new MathParagraph();
$block = new BlockElement();
$function = new FunctionElement();
$limit = new LimitElement();
$text1 = new TextElement();
$text1->setValue("lim");
$limit->setBase($text1);

$text2 = new TextElement();
$text2->setValue("x->0");
$limit->setLimit($text2);
$function->setName($limit);

$fraction = new FractionElement();
$sinus = new FunctionElement();
$text3 = new TextElement();
$text3->setValue("sin");
$sinus->setName($text3);

$text4 = new TextElement();
$text4->setValue("x");
$sinus->setBase($text4);
$fraction->setNumerator($sinus);

$text5 = new TextElement();
$text5->setValue("x");
$fraction->setDenominator($text5);
$function->setBase($fraction);
$block->setMathElementList([ $function ]);
$math->setMathBlockList([ $block ]);
$dto->setMathParagraph($math);

$portion = $api->CreatePortion($fileName, $slideIndex, $shapeIndex, $paragraphIndex, $dto);
print(count($portion->getMathParagraph()->getMathBlockList())); //1
```

{{< /tab >}}

{{< tab tabNum="4" >}}

{{< /tab >}}

{{< tab tabNum="5" >}}

```python
import asposeslidescloud

from asposeslidescloud.configuration import Configuration
from asposeslidescloud.apis.slides_api import SlidesApi
from asposeslidescloud.models.portion import Portion
from asposeslidescloud.models.math_paragraph import MathParagraph
from asposeslidescloud.models.block_element import BlockElement
from asposeslidescloud.models.function_element import FunctionElement
from asposeslidescloud.models.fraction_element import FractionElement
from asposeslidescloud.models.limit_element import LimitElement
from asposeslidescloud.models.text_element import TextElement

configuration = Configuration()
configuration.app_sid = 'MyClientId'
configuration.app_key = 'MyClientSecret'
api = SlidesApi(configuration)

file_name = "MyPresentation.pptx"
slide_index = 1
shape_index = 2
paragraph_index = 1

dto = Portion()
math_paragraph = MathParagraph()
math_block = BlockElement()
function_element = FunctionElement()
limit_element = LimitElement()
text1 = TextElement()
text1.value = "lim"
limit_element.base = text1

text2 = TextElement()
text2.value = "x->0"
limit_element.limit = text2
function_element.name = limit_element

fraction_element = FractionElement()
sinus_element = FunctionElement()
text3 = TextElement()
text3.value = "sin"
sinus_element.name = text3

text4 = TextElement()
text4.value = "x"
sinus_element.name = text4
fraction_element.numerator = sinus_element

text5 = TextElement()
text5.value = "x"
fraction_element.denominator = text5
function_element.base = fraction_element
math_block.math_element_list = [ function_element ]
math_paragraph.math_block_list = [ math_block ]
dto.math_paragraph = math_paragraph

portion = api.create_portion(file_name, slide_index, shape_index, paragraph_index, None, dto)
print(len(portion.math_paragraph.math_block_list)) #1
```

{{< /tab >}}

{{< tab tabNum="6" >}}

```javascript
const CloudSdk = require("asposeslidescloud");
const api = new CloudSdk.SlidesApi("MyClientId", "MyClientSecret");

const fileName = "MyPresentation.pptx";
const slideIndex = 1;
const shapeIndex = 2;
const paragraphIndex = 1;

const dto = new CloudSdk.Portion();
const mathParagraph = new CloudSdk.MathParagraph();
const blockElement = new CloudSdk.BlockElement();
const functionElement = new CloudSdk.FunctionElement();
const limitElement = new CloudSdk.LimitElement();
const textElement1 = new CloudSdk.TextElement();
textElement1.value = "lim";
limitElement.base = textElement1;

const textElement2 = new CloudSdk.TextElement();
textElement2.value = "x->0";
limitElement.limit = textElement2;
functionElement.name = limitElement;

const fractionElement = new CloudSdk.FractionElement();
const sinusElement = new CloudSdk.FunctionElement();
const textElement3 = new CloudSdk.TextElement();
textElement3.value = "sin";
sinusElement.name = textElement3;

const textElement4 = new CloudSdk.TextElement();
textElement4.value = "x";
sinusElement.base = textElement4;
fractionElement.numerator = sinusElement;

const textElement5 = new CloudSdk.TextElement();
textElement5.value = "x";
fractionElement.denominator = textElement5;
functionElement.base = fractionElement;

blockElement.mathElementList = [ functionElement ];
mathParagraph.mathBlockList = [ blockElement ];
dto.mathParagraph = mathParagraph;

api.createPortion(fileName, slideIndex, shapeIndex, paragraphIndex, dto).then(result => {
    console.log(result.body.mathParagraph.mathBlockList.length); //1
});
```

{{< /tab >}}

{{< tab tabNum="7" >}}

```go
cfg := asposeslidescloud.NewConfiguration()
cfg.AppSid = "MyClientId"
cfg.AppKey = "MyClientSecret"
api := asposeslidescloud.NewAPIClient(cfg)

fileName := "MyPresentation.pptx"
var slideIndex int32 = 1
var shapeIndex int32 = 2
var paragraphIndex int32 = 1

dto := NewPortion()
mathParagraph := NewMathParagraph()
blockElement := NewBlockElement()
functionElement := NewFunctionElement()
limitElement := NewLimitElement()
text1 := NewTextElement()
text1.Value = "lim"
limitElement.Base = text1

text2 := NewTextElement()
text2.Value = "x->0"
limitElement.Limit = text2
functionElement.Name = limitElement

fractionElement := NewFractionElement()
sinusElement := NewFunctionElement()
text3 := NewTextElement()
text3.Value = "sin"
sinusElement.Name = text3

text4 := NewTextElement()
text4.Value = "x"
sinusElement.Base = text4
fractionElement.Numerator = sinusElement

text5 := NewTextElement()
text5.Value = "x"
fractionElement.Denominator = text5
functionElement.Base = fractionElement
blockElement.MathElementList = []IMathElement { functionElement }
mathParagraph.MathBlockList = []IBlockElement { blockElement }
dto.MathParagraph = mathParagraph

portion, _, e := c.SlidesApi.CreatePortion(fileName, slideIndex, shapeIndex, paragraphIndex, dto, nil, "", "", "")
if e != nil {
    fmt.Printf("Error: %v.", e)
    return
}
fmt.Printf("Math Block Count: %v.", len(portion.getMathParagraph().getMathBlockList())) //1
```

{{< /tab >}}

{{< tab tabNum="8" >}}

{{< /tab >}}

{{< tab tabNum="9" >}}

{{< /tab >}}

{{< tab tabNum="10" >}}

{{< /tab >}}

{{< /tabs >}}

### **SDK Source**
The Aspose Cloud SDK's can be downloaded from the following page: [Available SDK's](/slides/available-sdks/)
