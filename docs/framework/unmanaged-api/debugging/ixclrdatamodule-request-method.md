---
title: IXCLRDataModule::Request 方法
ms.date: 01/16/2019
api.name:
- IXCLRDataModule::Request Method
api.location:
- mscordacwks.dll
api.type:
- COM
f1.keywords:
- IXCLRDataModule::Request Method
helpviewer.keywords:
- IXCLRDataModule::Request Method [.NET Framework debugging]
topic_type:
- apiref
author: cshung
ms.author: andrewau
ms.openlocfilehash: 0226a11b142515296d976e3d645cb2475d634420
ms.sourcegitcommit: b56d59ad42140d277f2acbd003b74d655fdbc9f1
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/19/2019
ms.locfileid: "54416338"
---
# <a name="ixclrdatamodulerequest-method"></a>IXCLRDataModule::Request 方法

填入指定模組的資料緩衝區的要求。

[!INCLUDE[debugging-api-recommended-note](../../../../includes/debugging-api-recommended-note.md)]

## <a name="syntax"></a>語法
```
HRESULT Request([in] ULONG32 reqCode,
    [in] ULONG32 inBufferSize,
    [in, size_is(inBufferSize)] BYTE* inBuffer,
    [in] ULONG32 outBufferSize,
    [out, size_is(outBufferSize)] BYTE* outBuffer);
```

### <a name="parameters"></a>參數

`reqCode` [in]要求傳送的型別。

`inBufferSize` [in] 要傳入的輸入緩衝區的大小。

`inBuffer` [in、 size_is(inBufferSize)]若要在要求中傳送未經處理資料的緩衝區指標。

`outBufferSize` [in]輸出緩衝區的大小。

`outBuffer` [out，size_is(outBufferSize)]用來儲存要求回應的緩衝區指標。

## <a name="remarks"></a>備註

提供的方法是一部分`IXCLRDataModule`介面，並對應至 36th 虛擬方法表的位置。

## <a name="requirements"></a>需求

**平台：** 請參閱[系統需求](../../../../docs/framework/get-started/system-requirements.md)。  
**標頭：** 無   
**程式庫：** 無  
**.NET framework 版本：**[!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]  

## <a name="see-also"></a>另請參閱
- [偵錯](../../../../docs/framework/unmanaged-api/debugging/index.md)
- [IXCLRDataModule 介面](../../../../docs/framework/unmanaged-api/debugging/ixclrdatamodule-interface.md)