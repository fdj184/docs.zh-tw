---
title: 作法：建立列舉類型的新方法 - C# 程式設計手冊
ms.custom: seodec18
ms.date: 07/20/2015
helpviewer_keywords:
- enumerations [C#]
- extension methods [C#], for enums
- enum extensibility [C#]
ms.assetid: 100106f9-1e54-462c-8ebe-3892fe23b6eb
ms.openlocfilehash: ebd0433efda43c65ea6d9494a8ec25e8263f5b43
ms.sourcegitcommit: 40364ded04fa6cdcb2b6beca7f68412e2e12f633
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/28/2019
ms.locfileid: "56968118"
---
# <a name="how-to-create-a-new-method-for-an-enumeration-c-programming-guide"></a>作法：建立列舉類型的新方法 (C# 程式設計手冊)
您可以使用擴充方法來新增專屬於特定列舉類型的功能。  
  
## <a name="example"></a>範例  
 在下例中，`Grades` 列舉代表班上學生可能得到的字母分級成績。 已將名為 `Passing` 的擴充方法新增至 `Grades` 類型，以便該類型的每個執行個體現在都「知道」它是否代表傳遞等級。  
  
 [!code-csharp[csProgGuideExtensionMethods#2](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideExtensionMethods/cs/extensionmethods.cs#2)]  
  
 請注意，`Extensions` 類別也包含動態更新的靜態變數，以及反映該變數目前值的擴充方法傳回值。 本例示範，在幕後直接對定義所在的靜態類別叫用擴充方法。  
  
## <a name="compiling-the-code"></a>編譯程式碼  
 若要執行此程式碼，請將它複製並貼到已在 Visual Studio 中建立的 Visual C# 主控台應用程式專案。 根據預設，此專案是以 [!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)] 3.5 版為目標，且有 System.Core.dll 的參考，以及 System.Linq 的 `using` 指示詞。 如果專案中遺漏上述一或多個需求，您可以手動新增這些需求。  
  
## <a name="see-also"></a>另請參閱

- [C# 程式設計指南](../../../csharp/programming-guide/index.md)
- [擴充方法](../../../csharp/programming-guide/classes-and-structs/extension-methods.md)
