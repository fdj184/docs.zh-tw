---
title: HOW TO：繫結兩個控制項的屬性
ms.date: 03/30/2017
helpviewer_keywords:
- data binding [WPF], binding properties of two controls
- binding properties of two controls [WPF]
- controls [WPF], binding properties of
ms.assetid: 06318fac-6afd-4c7d-a277-6d7ef50f47bc
ms.openlocfilehash: 0dd7b817b632758cfca8b5c45d88e333510485f6
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 04/18/2019
ms.locfileid: "59222056"
---
# <a name="how-to-bind-the-properties-of-two-controls"></a>HOW TO：繫結兩個控制項的屬性
此範例示範如何具現化控制項屬性繫結至另一個使用<xref:System.Windows.Data.Binding.ElementName%2A>屬性。  
  
## <a name="example"></a>範例  
 下列範例示範如何繫結<xref:System.Windows.Controls.Panel.Background%2A>的屬性<xref:System.Windows.Controls.Canvas>至<xref:System.Windows.Controls.Primitives.Selector.SelectedItem%2A>。<xref:System.Windows.Controls.ContentControl.Content%2A> 屬性<xref:System.Windows.Controls.ComboBox>:  
  
 [!code-xaml[BindDptoDp#1](~/samples/snippets/csharp/VS_Snippets_Wpf/BindDPtoDP/CS/Window1.xaml#1)]  
  
 此範例轉譯後會如同以下所示︰  
  
 ![具有綠色背景的畫布](./media/databindingbindingdpssample.PNG "DataBindingBindingDPsSample")  
  
 **附註**繫結目標屬性 (在此範例中，<xref:System.Windows.Controls.Panel.Background%2A>屬性) 必須是相依性屬性。 如需詳細資訊，請參閱 [資料繫結概觀](data-binding-overview.md)。  
  
## <a name="see-also"></a>另請參閱

- [指定繫結來源](how-to-specify-the-binding-source.md)
- [HOW-TO 主題](data-binding-how-to-topics.md)
