---
ms.openlocfilehash: 190bca720504535cb54e498ca8da23fbb6634ad4
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 04/18/2019
ms.locfileid: "59803485"
---
### <a name="currentculture-is-not-preserved-across-wpf-dispatcher-operations"></a>CurrentCulture 無法跨 WPF 發送器作業保留

|   |   |
|---|---|
|詳細資料|從 .NET Framework 4.6 開始，在 <xref:System.Windows.Threading.Dispatcher?displayProperty=name> 內對 <xref:System.Globalization.CultureInfo.CurrentCulture?displayProperty=name> 或 <xref:System.Globalization.CultureInfo.CurrentUICulture?displayProperty=name> 所做的變更，將會在發送器作業結束時遺失。 同樣地，在發送器作業外部對 <xref:System.Globalization.CultureInfo.CurrentCulture?displayProperty=name> 或 <xref:System.Globalization.CultureInfo.CurrentUICulture?displayProperty=name> 所做的變更，不會在執行該作業時反映出來。實際上，這表示 <xref:System.Globalization.CultureInfo.CurrentCulture?displayProperty=name> 和 <xref:System.Globalization.CultureInfo.CurrentUICulture?displayProperty=name> 變更可能不會在 WPF UI 回呼與 WPF 應用程式的其他程式碼之間流動。這是因為從以 .NET Framework 4.6 為目標的應用程式開始，<xref:System.Threading.ExecutionContext?displayProperty=name> 的變更會導致 <xref:System.Globalization.CultureInfo.CurrentCulture?displayProperty=name> 和 <xref:System.Globalization.CultureInfo.CurrentUICulture?displayProperty=name> 儲存在執行內容中。 WPF 發送器作業會儲存用來開始作業的執行內容，並在作業完成時還原先前的內容。 因為 <xref:System.Globalization.CultureInfo.CurrentCulture?displayProperty=name> 和 <xref:System.Globalization.CultureInfo.CurrentUICulture?displayProperty=name> 現在是該內容的一部分，所以在發送器作業內對其進行的變更不會保留到作業外。|
|建議|您可以將所需的 <xref:System.Globalization.CultureInfo.CurrentCulture?displayProperty=name> 或 <xref:System.Globalization.CultureInfo.CurrentUICulture?displayProperty=name> 儲存在欄位中，然後簽入設定正確 <xref:System.Globalization.CultureInfo.CurrentCulture?displayProperty=name> 和 <xref:System.Globalization.CultureInfo.CurrentUICulture?displayProperty=name> 的所有發送器作業主體 (包括 UI 事件回呼處理常式)，來解決受此變更影響的應用程式。 此外，由於此 WPF 變更的基本 ExecutionContext 變更只會影響以 .NET Framework 4.6 或更新版本為目標的應用程式，因此您可以將目標設為 .NET Framework 4.5.2 來避免此中斷情況。以 .NET Framework 4.6 或更新版本為目標的應用程式，也可以設定下列相容性參數來解決此問題：<pre><code class="lang-csharp">AppContext.SetSwitch(&quot;Switch.System.Globalization.NoAsyncCurrentCulture&quot;, true);&#13;&#10;</code></pre>.NET Framework 4.6.2 中的 WPF 已修正此問題。 .NET Frameworks 4.6、4.6.1 也已透過 [KB 3139549](https://support.microsoft.com/kb/3139549) 進行修正。 以 .NET Framework 4.6 或更新版本為目標的應用程式將在 WPF 應用程式中自動取得正確的行為 - <xref:System.Globalization.CultureInfo.CurrentCulture?displayProperty=name>/<xref:System.Globalization.CultureInfo.CurrentUICulture?displayProperty=name> 會跨發送器作業保留。|
|範圍|次要|
|版本|4.6|
|類型|正在重定目標|
