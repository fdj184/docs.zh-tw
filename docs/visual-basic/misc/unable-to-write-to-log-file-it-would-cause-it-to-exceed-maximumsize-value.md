---
title: 無法寫入記錄檔，因為如果寫入，會使它超過 MaximumSize 值
ms.date: 07/20/2015
f1_keywords:
- vbrApplicationLog_FileExceedsMaximumSize
ms.assetid: 61747a9c-e460-424b-a365-73cdba9dd428
ms.openlocfilehash: 587b35282c7e78da1fdf4ccf9d08214e5665119c
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 04/18/2019
ms.locfileid: "59298600"
---
# <a name="unable-to-write-to-log-file-because-writing-to-it-would-cause-it-to-exceed-maximumsize-value"></a>無法寫入記錄檔，因為如果寫入，會使它超過 MaximumSize 值
<xref:Microsoft.VisualBasic.Logging.FileLogTraceListener> 類別無法寫入記錄檔，因為：  
  
-   記錄檔大小 (以位元組為單位) 大於 <xref:Microsoft.VisualBasic.Logging.FileLogTraceListener.MaxFileSize%2A> 屬性的值  
  
     —且—  
  
-   <xref:Microsoft.VisualBasic.Logging.FileLogTraceListener.DiskSpaceExhaustedBehavior%2A> 屬性的值是 <xref:Microsoft.VisualBasic.Logging.DiskSpaceExhaustedOption.ThrowException>。  
  
## <a name="to-correct-this-error"></a>更正這個錯誤  
  
1. 封存現有的記錄檔並將其從電腦中移除，讓 <xref:Microsoft.VisualBasic.Logging.FileLogTraceListener> 物件可以建立新的記錄檔。  
  
2. 變更 <xref:Microsoft.VisualBasic.Logging.FileLogTraceListener.MaxFileSize%2A> 屬性的值以允許較大的記錄檔。  
  
3. 將 <xref:Microsoft.VisualBasic.Logging.FileLogTraceListener.DiskSpaceExhaustedBehavior%2A> 屬性設定為 <xref:Microsoft.VisualBasic.Logging.DiskSpaceExhaustedOption.DiscardMessages> ，以在記錄檔太大時，捨棄訊息而不發出警告。  
  
## <a name="see-also"></a>另請參閱

- <xref:Microsoft.VisualBasic.Logging.FileLogTraceListener.MaxFileSize%2A>
- <xref:Microsoft.VisualBasic.Logging.FileLogTraceListener.DiskSpaceExhaustedBehavior%2A>
- <xref:Microsoft.VisualBasic.Logging.FileLogTraceListener>
- [My.Application.Log](xref:Microsoft.VisualBasic.ApplicationServices.ApplicationBase.Log)
- [My.Application.Info.DirectoryPath](xref:Microsoft.VisualBasic.ApplicationServices.ApplicationBase.Log)
