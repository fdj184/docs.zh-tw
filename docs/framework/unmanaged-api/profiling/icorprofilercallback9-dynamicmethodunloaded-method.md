---
title: ICorProfilerCallback9::DynamicMethodUnloaded 方法
ms.date: 04/10/2018
api_name:
- ICorProfilerCallback9.DynamicMethodUnloaded
api_location:
- mscorwks.dll
- corprof.idl
api_type:
- COM
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 16b3334647922f845645e6eb58db3146f4c9b936
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/04/2018
ms.locfileid: "33452399"
---
# <a name="icorprofilercallback9dynamicmethodunloaded-method"></a><span data-ttu-id="55db4-102">ICorProfilerCallback9::DynamicMethodUnloaded 方法</span><span class="sxs-lookup"><span data-stu-id="55db4-102">ICorProfilerCallback9::DynamicMethodUnloaded Method</span></span>
<span data-ttu-id="55db4-103">[在.NET Framework 4.7.2 和更新版本中支援]</span><span class="sxs-lookup"><span data-stu-id="55db4-103">[Supported in the .NET Framework 4.7.2 and later versions]</span></span>  
  
<span data-ttu-id="55db4-104">記憶體回收，並接著卸載動態方法時，通知分析工具。</span><span class="sxs-lookup"><span data-stu-id="55db4-104">Notifies the profiler whenever a dynamic method is garbage collected and subsequently unloaded.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="55db4-105">語法</span><span class="sxs-lookup"><span data-stu-id="55db4-105">Syntax</span></span>  
  
```  
HRESULT DynamicMethodUnloaded(  
     [in]  FunctionID  functionId
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="55db4-106">參數</span><span class="sxs-lookup"><span data-stu-id="55db4-106">Parameters</span></span>  
<span data-ttu-id="55db4-107">[輸入] `functionId`</span><span class="sxs-lookup"><span data-stu-id="55db4-107">[in] `functionId`</span></span>  
<span data-ttu-id="55db4-108">記憶體中函式已經過記憶體回收，並卸載的識別項。</span><span class="sxs-lookup"><span data-stu-id="55db4-108">The identifier of the in-memory function that has been garbage collected and unloaded.</span></span>   

## <a name="requirements"></a><span data-ttu-id="55db4-109">需求</span><span class="sxs-lookup"><span data-stu-id="55db4-109">Requirements</span></span>  
 <span data-ttu-id="55db4-110">**平台：** 看到[系統需求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="55db4-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="55db4-111">**標頭：** CorProf.idl、CorProf.h</span><span class="sxs-lookup"><span data-stu-id="55db4-111">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="55db4-112">**程式庫：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="55db4-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="55db4-113">**.NET framework 版本：** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span><span class="sxs-lookup"><span data-stu-id="55db4-113">**.NET Framework Versions:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="55db4-114">另請參閱</span><span class="sxs-lookup"><span data-stu-id="55db4-114">See Also</span></span>  
[<span data-ttu-id="55db4-115">ICorProfilerCallback8.DynamicMethodJITCompilationStarted 方法</span><span class="sxs-lookup"><span data-stu-id="55db4-115">ICorProfilerCallback8.DynamicMethodJITCompilationStarted Method</span></span>](icorprofilercallback8-dynamicmethodjitcompilationstarted-method.md)  
[<span data-ttu-id="55db4-116">ICorProfilerCallback8.DynamicMethodJITCompilationFinished 方法</span><span class="sxs-lookup"><span data-stu-id="55db4-116">ICorProfilerCallback8.DynamicMethodJITCompilationFinished Method</span></span>](icorprofilercallback8-dynamicmethodjitcompilationfinished-method.md)  
<span data-ttu-id="55db4-117">[ICorProfilerCallback9 介面](icorprofilercallback9-interface.md) </span><span class="sxs-lookup"><span data-stu-id="55db4-117">[ICorProfilerCallback9 Interface](icorprofilercallback9-interface.md) </span></span>  
[<span data-ttu-id="55db4-118">COR_PRF_HIGH_MONITOR_DYNAMIC_FUNCTION_UNLOADS</span><span class="sxs-lookup"><span data-stu-id="55db4-118">COR_PRF_HIGH_MONITOR_DYNAMIC_FUNCTION_UNLOADS</span></span>](cor-prf-high-monitor-enumeration.md)