---
title: HOW TO：以程式設計方式變更內容的 FlowDirection
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- FlowDirection property [WPF], changing programmatically
- documents [WPF], changing FlowDirection property programmatically
ms.assetid: 02f5a8ba-f8c0-4e5a-84b9-4c5bf12922a2
ms.openlocfilehash: ec159ed0efce8b5514788331e8715a55e7a8a638
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 04/23/2019
ms.locfileid: "61776554"
---
# <a name="how-to-change-the-flowdirection-of-content-programmatically"></a>HOW TO：以程式設計方式變更內容的 FlowDirection
此範例示範如何以程式設計方式變更<xref:System.Windows.FrameworkElement.FlowDirection%2A>屬性<xref:System.Windows.Controls.FlowDocumentReader>。  
  
## <a name="example"></a>範例  
 兩個<xref:System.Windows.Controls.Button>建立項目，每個均代表的可能值的其中一個<xref:System.Windows.FlowDirection>。 當按一下按鈕時，相關聯的屬性值會套用至的內容<xref:System.Windows.Controls.FlowDocumentReader>名為`tf1`。  屬性值也會寫入<xref:System.Windows.Controls.TextBlock>名為`txt1`。  
  
 [!code-xaml[FlowDirectionSnippets#_FlowDirectionXAML](~/samples/snippets/csharp/VS_Snippets_Wpf/FlowDirectionSnippets/CSharp/Window1.xaml#_flowdirectionxaml)]  
  
## <a name="example"></a>範例  
 按下按鈕即可上面定義相關聯的事件處理C#程式碼後置檔案。  
  
 [!code-csharp[FlowDirectionSnippets#_FlowDirection](~/samples/snippets/csharp/VS_Snippets_Wpf/FlowDirectionSnippets/CSharp/Window1.xaml.cs#_flowdirection)]
 [!code-vb[FlowDirectionSnippets#_FlowDirection](~/samples/snippets/visualbasic/VS_Snippets_Wpf/FlowDirectionSnippets/VisualBasic/Window1.xaml.vb#_flowdirection)]
