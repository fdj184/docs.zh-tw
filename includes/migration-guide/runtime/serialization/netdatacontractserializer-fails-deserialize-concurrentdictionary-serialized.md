### <a name="netdatacontractserializer-fails-to-deserialize-a-concurrentdictionary-serialized-with-a-different-net-version"></a><span data-ttu-id="3ba6b-101">NetDataContractSerializer 無法將使用不同 .NET 版本序列化的 ConcurrentDictionary 還原序列化</span><span class="sxs-lookup"><span data-stu-id="3ba6b-101">NetDataContractSerializer fails to deserialize a ConcurrentDictionary serialized with a different .NET version</span></span>

|   |   |
|---|---|
|<span data-ttu-id="3ba6b-102">詳細資料</span><span class="sxs-lookup"><span data-stu-id="3ba6b-102">Details</span></span>|<span data-ttu-id="3ba6b-103">根據設計，只有當序列化和還原序列化兩端共用相同的 CLR 類型時，才能使用 <xref:System.Runtime.Serialization.NetDataContractSerializer?displayProperty=name>。</span><span class="sxs-lookup"><span data-stu-id="3ba6b-103">By design, the <xref:System.Runtime.Serialization.NetDataContractSerializer?displayProperty=name> can be used only if both the serializing and deserializing ends share the same CLR types.</span></span> <span data-ttu-id="3ba6b-104">因此，不保證使用其中一個 .NET Framework 版本序列化的物件可以透過不同版本還原序列化。<xref:System.Collections.Concurrent.ConcurrentDictionary%602?displayProperty=name> 是使用 .NET Framework 4.5 或舊版序列化並使用 .NET Framework 4.5.1 或更新版本還原序列化時，無法正確還原序列化的已知類型。</span><span class="sxs-lookup"><span data-stu-id="3ba6b-104">Therefore, it is not guaranteed that an object serialized with one version of the .NET Framework can be deserialized by a different version.<xref:System.Collections.Concurrent.ConcurrentDictionary%602?displayProperty=name> is a type that is known to not to deserialize correctly if serialized with the .NET Framework 4.5 or earlier and deserialized with the .NET Framework 4.5.1 or later.</span></span>|
|<span data-ttu-id="3ba6b-105">建議</span><span class="sxs-lookup"><span data-stu-id="3ba6b-105">Suggestion</span></span>|<span data-ttu-id="3ba6b-106">此問題有許多可能的因應措施：</span><span class="sxs-lookup"><span data-stu-id="3ba6b-106">There are a number of possible work-arounds for this issue:</span></span><ul><li><span data-ttu-id="3ba6b-107">另升級序列化電腦以使用 .NET Framework 4.5.1。</span><span class="sxs-lookup"><span data-stu-id="3ba6b-107">Upgrade the serializing computer to use the .NET Framework 4.5.1, as well.</span></span></li><li><span data-ttu-id="3ba6b-108">使用 <xref:System.Runtime.Serialization.DataContractSerializer?displayProperty=name> 而不是 <xref:System.Runtime.Serialization.NetDataContractSerializer?displayProperty=name>，因為這不會預期在序列化和還原序列化的兩端具有完全相同的 CLR 類型。</span><span class="sxs-lookup"><span data-stu-id="3ba6b-108">Use <xref:System.Runtime.Serialization.DataContractSerializer?displayProperty=name> instead of <xref:System.Runtime.Serialization.NetDataContractSerializer?displayProperty=name> as this does not expect the exact same CLR types at both serializing and deserializing ends.</span></span></li><li><span data-ttu-id="3ba6b-109">使用 <xref:System.Collections.Generic.Dictionary%602?displayProperty=name> 而不是 <xref:System.Collections.Concurrent.ConcurrentDictionary%602?displayProperty=name>，因為它不會呈現這種特定的 4.5-&gt;4.5.1 中斷。</span><span class="sxs-lookup"><span data-stu-id="3ba6b-109">Use <xref:System.Collections.Generic.Dictionary%602?displayProperty=name> instead of <xref:System.Collections.Concurrent.ConcurrentDictionary%602?displayProperty=name> since it does not exhibit this particular 4.5-&gt;4.5.1 break.</span></span></li></ul>|
|<span data-ttu-id="3ba6b-110">範圍</span><span class="sxs-lookup"><span data-stu-id="3ba6b-110">Scope</span></span>|<span data-ttu-id="3ba6b-111">次要</span><span class="sxs-lookup"><span data-stu-id="3ba6b-111">Minor</span></span>|
|<span data-ttu-id="3ba6b-112">版本</span><span class="sxs-lookup"><span data-stu-id="3ba6b-112">Version</span></span>|<span data-ttu-id="3ba6b-113">4.5.1</span><span class="sxs-lookup"><span data-stu-id="3ba6b-113">4.5.1</span></span>|
|<span data-ttu-id="3ba6b-114">類型</span><span class="sxs-lookup"><span data-stu-id="3ba6b-114">Type</span></span>|<span data-ttu-id="3ba6b-115">執行階段</span><span class="sxs-lookup"><span data-stu-id="3ba6b-115">Runtime</span></span>|
|<span data-ttu-id="3ba6b-116">受影響的 API</span><span class="sxs-lookup"><span data-stu-id="3ba6b-116">Affected APIs</span></span>|<ul><li><xref:System.Runtime.Serialization.NetDataContractSerializer.Deserialize(System.IO.Stream)?displayProperty=nameWithType></li></ul>|
