---
ms.openlocfilehash: 3cff9bfbb1adb6004921903276d75f641c7e703c
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 04/18/2019
ms.locfileid: "59774135"
---
### <a name="contractinvariant-or-contractrequirestexception-do-not-consider-stringisnullorempty-to-be-pure"></a>Contract.Invariant 或 Contract.Requires\<TException> 不會將 String.IsNullOrEmpty 視為 pure

|   |   |
|---|---|
|詳細資料|針對以 .NET Framework 4.6.1 為目標的應用程式，如果 <xref:System.Diagnostics.Contracts.Contract.Invariant%2A?displayProperty=nameWithType> 的非變異合約或 <xref:System.Diagnostics.Contracts.Contract.Requires%2A?displayProperty=nameWithType)> 的前置條件合約呼叫 <xref:System.String.IsNullOrEmpty%2A?displayProperty=nameWithType> 方法，重寫器會發出編譯器警告 CC1036：在方法中沒有 [Pure] 的情況下&quot;偵測到對方法呼叫 <xref:System.String.IsNullOrWhiteSpace%2A?displayProperty=nameWithType>。&quot;這是編譯器警告，不是編譯器錯誤。|
|建議|[GitHub 問題 #339](https://github.com/Microsoft/CodeContracts/issues/339) 中已解決這種行為。 若要移除這個警告，您可以從 [GitHub](https://github.com/Microsoft/CodeContracts/blob/master/README.md) 下載並編譯程式碼合約工具原始程式碼的更新版本。 您可以在頁面底部找到下載資訊。|
|範圍|次要|
|版本|4.6.1|
|類型|執行階段|
|受影響的 API|<ul><li><xref:System.Diagnostics.Contracts.Contract.Invariant(System.Boolean)?displayProperty=nameWithType></li><li><xref:System.Diagnostics.Contracts.Contract.Requires(System.Boolean)?displayProperty=nameWithType></li></ul>|
