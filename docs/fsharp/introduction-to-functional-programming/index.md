---
title: F# 函式程式設計簡介
description: 了解函式程式設計的基本概念F#。
ms.date: 10/29/2018
ms.openlocfilehash: 84022e58c0f17b9e9875402c653c31e494e940da
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 04/23/2019
ms.locfileid: "61772784"
---
# <a name="introduction-to-functional-programming-in-f"></a>在 F 中的函式程式設計簡介\#

功能性程式設計是程式設計的樣式的強調函式和不可變的資料使用。 具型別功能性程式設計是當函式程式設計會結合具有靜態類型，例如F#。 一般情況下，函式程式設計中強調下列概念：

* 為您所使用的主要建構函式
* 運算式，而不是陳述式
* 透過變數不可變的值
* 透過命令式程式設計的宣告式程式設計

在此系列中，您將探索概念和模式中功能的程式設計使用F#。 過程中，您將了解一些F#太。

## <a name="terminology"></a>用語

功能性程式設計，類似其他程式設計典範，隨附於您最終需要了解的詞彙。 以下是時間的一些常見術語，您會看到所有:

* **函式**-函式是一種建構，會產生輸出時指定的輸入。 更正式的說法，它_對應_從其中一個項目設定為另一個集合。 此形式放在許多方面，具體，尤其是當使用資料集合上的運作之函式。 它是最基本的 （且重要的） 中概念函式程式設計。 
* **運算式**-運算式是產生值的程式碼中的建構。 在F#，這個值必須是繫結或明確地被忽略。 運算式可透過極簡方式取代函式呼叫。
* **單純性**-單純性是函式的屬性，使其傳回值一律為適用於相同的引數，和其評估沒有任何副作用。 純虛擬函式完全取決於其引數。
* **參考的透明度**-參考透明度是運算式的屬性，使得取代其輸出而不會影響程式的行為。
* **不變性**-不變性，表示值不能變更就地。 這是相較於可以就地變更的變數。

## <a name="examples"></a>範例

下列範例會示範下列核心概念。

### <a name="functions"></a>函式

最常見和基本建構函式程式設計中的是函式。 以下是簡單的函式，將 1 加上整數：

```fsharp
let addOne x = x + 1
```

其型別簽章如下所示：

```fsharp
val addOne: x:int -> int
```

簽章可讀取，為 「`addOne`接受`int`名為`x`並將產生`int`"。 更正式的說法`addOne`已_對應_整數的集合中的值，以整數的集合。 `->`語彙基元表示這個對應。 在F#，您通常可以查看函式簽章，以了解針對其用途。

因此，為何簽章重要？ 在具型別功能性程式設計中，函式的實作小於通常比實際的型別簽章重要 ！ 事實上，`addOne`新增為整數值 1 值得在執行階段，但當您建構的程式，在於它會接受並傳回`int`是什麼會通知您實際使用此函式方式。 此外，一旦使用此函式正確 （相對於其型別簽章中） 時，診斷任何問題可以只在主體內`addOne`函式。 這是具類型的函式程式設計背後的推動力量。

### <a name="expressions"></a>運算式

運算式是評估為值的建構。 相較於陳述式，用以執行的動作，運算式可以視為執行動作，讓傳回的值。 運算式幾乎一律會使用由函式程式設計中的陳述式。

請考慮先前的函式， `addOne`。 主體`addOne`運算式：

```fsharp
// 'x + 1' is an expression!
let addOne x = x + 1
```

它是定義的結果型別，這個運算式的結果`addOne`函式。 比方說，此函式所組成的運算式無法變更為不同的類型，例如`string`:

```fsharp
let addOne x = x.ToString() + "1"
```

函式的簽章現在是：

```fsharp
val addOne: x:'a -> string
```

自中的任何類型F#可以有`ToString()`它的型別上呼叫`x`發出泛型 (稱為[自動一般化](../language-reference/generics/automatic-generalization.md))，且結果類型為`string`。

運算式不是函式的主體。 您可以產生您在其他地方使用的值的運算式。 其中一個是通用`if`:

```fsharp
// Checks if 'x' is odd by using the mod operator
let isOdd x = x % 2 <> 0

let addOneIfOdd input =
    let result =
        if isOdd input then
            input + 1
        else
            input

    result
```

`if`運算式會產生一個值，稱為`result`。 請注意，您可以省略`result`，請完全進行`if`運算式主體的`addOneIfOdd`函式。 運算式，必須注意的重點是，它們會產生值。

沒有特殊的型別， `unit`，沒有要傳回項目時使用的。 例如，請考慮這個簡單的函式：

```fsharp
let printString (str: string) =
    printfn "String is: %s" str
```

簽章看起來像這樣：

```fsharp
val printString: str:string -> unit
```

`unit`類型表示沒有任何傳回的實際值。 這是很有用，就必須在常式 「 運作 」 而不論是否不具有任何值，以傳回該工作的結果。

這是在程式明確對比，命令式程式設計中，其中對等項目`if`建構是一個陳述式，並產生值通常是與變更的變數。 例如，在C#，可能會撰寫程式碼，就像這樣：

```csharp
bool IsOdd(int x) => x % 2 != 0;

int AddOneIfOdd(int input)
{
    var result = input;

    if (IsOdd(input))
    {
        result = input + 1;
    }

    return result;
}
```

值得注意的是， C# ，而且支援其他的 C 樣式語言[三元運算式](../../csharp/language-reference/operators/conditional-operator.md)，這可讓您以運算式為基礎的條件式程式設計。

在功能程式設計中，很少變動陳述式的值。 雖然有些功能的語言支援陳述式和變動，但是它並不常見函式程式設計中使用這些概念。

### <a name="pure-functions"></a>純虛擬函式

如先前所述，純虛擬函式是函式：

* 一律評估為相同的輸入相同的值。
* 沒有任何副作用。

您最好將此內容中的數學函式。 在數學，函式只相依於其引數，而且沒有任何副作用。 數學函式中`f(x) = x + 1`，值`f(x)`僅取決於值`x`。 在函式程式設計中的純虛擬函式是相同的方式。

當撰寫純虛擬函式，函式必須只相依於其引數，並不執行任何會產生副作用的動作。

因為這取決於全域、 可變動狀態，以下是一個非純虛擬函式範例：

```fsharp
let mutable value = 1

let addOneToValue x = x + value
```

`addOneToValue`清楚地非純虛擬函式，是因為`value`可能有不同的值比 1，隨時變更。 是函式程式設計中避免這種模式的全域值而定。

以下是非純虛擬函式的另一個範例，因為它會執行副作用：

```fsharp
let addOneToValue x = 
    printfn "x is %d" x
    x + 1
```

雖然此函式不依存於一個全域值，它的值寫入`x`程式的輸出。 雖然沒有任何原本就是問題，這項操作，意思函式不是純虛擬。 如果您的程式的另一部分取決於某個外部程式，例如輸出緩衝區，然後呼叫此函式可能會影響您的程式，另一部分。

移除`printfn`陳述式讓純虛擬函式：

```fsharp
let addOneToValue x = x + 1
```

雖然此函式本質上並非_較佳_比使用舊版`printfn`陳述式，它可以確實保證此函式的作用是傳回值。 任何數次呼叫此函式會產生相同的結果： 只會產生值。 根據單純性可預測性是許多功能的程式設計人員尋求的項目。

### <a name="immutability"></a>不變性

最後，其中一個具型別功能性程式設計的最基本的概念是不變性。 在F#，所有值都是不可變的預設值。 這表示它們不能變更，除非您將它們明確標示為可變動。

在實務上，使用不可變的值會表示程式設計變更您的方法，請從 「 我需要變更某些項目 」，以 「 我需要產生新的值 」。

例如，新增 1 的值表示產生新的值，不變更現有的憑證：

```fsharp
let value = 1
let secondValue = value + 1
```

在F#，下列程式碼會執行**不**變動`value`函式; 相反地，它會執行相等檢查：

```fsharp
let value = 1
value = value + 1 // Produces a 'bool' value!
```

某些功能的程式設計語言並不支援變動。 在F#，它支援，但它不是值的預設行為。

這個概念延伸甚至進一步資料結構。 在功能性程式設計，不可變的資料結構例如集 （和更多） 有不同的實作比您一開始可能預期。 就概念而言，如下的項目加入一組不會變更集，它會產生_新_設定的附加價值。 實際上，這是通常透過不同的資料結構，以便有效率地追蹤的值，因此，因此可以提供適當的表示法的資料。

這種使用值和資料結構而言很重要，因為它會強制您將修改的項目，如同它會建立新的版本的任何作業。 這可讓相等和比較等的項目，以便在程式中一致。

## <a name="next-steps"></a>後續步驟

下一節會徹底探討函式中，瀏覽不同的方式，您可以在函式程式設計中使用它們。

[第一級函式](first-class-functions.md)將探索功能深入，顯示如何使用它們在不同內容中。

## <a name="further-reading"></a>進一步閱讀

[功能思考](https://fsharpforfunandprofit.com/posts/thinking-functionally-intro/)系列是另一個絕佳的資源，若要了解功能性程式設計與F#。 它涵蓋函式程式設計的基本概念了 pragmatic 和容易閱讀的方式，使用F#功能，可說明的概念。
