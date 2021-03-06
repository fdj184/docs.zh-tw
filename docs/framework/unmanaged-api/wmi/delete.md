---
title: 刪除函式 （Unmanaged API 參考）
description: 刪除函式會從 CIM 類別定義中刪除指定的屬性和所有其限定詞。
ms.date: 11/06/2017
api_name:
- Delete
api_location:
- WMINet_Utils.dll
api_type:
- DLLExport
f1_keywords:
- Delete
helpviewer_keywords:
- Delete function [.NET WMI and performance counters]
topic_type:
- Reference
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: a1a26db7785a8a378fa541308ecc6aee30fa87ec
ms.sourcegitcommit: 0c48191d6d641ce88d7510e319cf38c0e35697d0
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/05/2019
ms.locfileid: "57367116"
---
# <a name="delete-function"></a>刪除函式

刪除指定的屬性和其限定詞的所有從 CIM 類別定義。

[!INCLUDE[internalonly-unmanaged](../../../../includes/internalonly-unmanaged.md)]

## <a name="syntax"></a>語法

```cpp
HRESULT Delete (
   [in] int               vFunc,
   [in] IWbemClassObject* ptr,
   [in] LPCWSTR           wszName
);
```

## <a name="parameters"></a>參數

`vFunc`\
[in]未使用此參數。

`ptr`\
[in]指標[IWbemClassObject](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemclassobject)執行個體。

`wszName`\
[in]要刪除之屬性的名稱。 `wszName` 必須是有效的指標`LPCWSTR`。

## <a name="return-value"></a>傳回值

此函式所傳回的下列值中定義*WbemCli.h*標頭檔，或者您可以將其定義為常數中程式碼：

|常數  |值  |描述  |
|---------|---------|---------|
| `WBEM_E_FAILED` | 0x80041001 | 發生未指定的錯誤。 |
| `WBEM_E_INVALID_OPERATION` | 0x80041016 | 無法刪除屬性。 |
| `WBEM_E_INVALID_PARAMETER` | 0x80041008 | `wszName` 無效。 |
| `WBEM_E_NOT_FOUND` | 0x80041002 | 指定的屬性不存在。 |
| `WBEM_E_OUT_OF_MEMORY` | 0x80041006 | 沒有足夠的記憶體來完成此作業。 |
| `WBEM_E_PROPAGATED_PROPERTY` | 0x8004101c | 屬性被繼承自基底類別。 |
| `WBEM_E_SYSTEM_PROPERTY` | | 系統屬性的屬性。 |
|`WBEM_S_NO_ERROR` | 0 | 函式呼叫成功。  |
| `WBEM_E_RESET_TO_DEFAULT` | 0x80041030 | 函式會刪除目前的類別覆寫預設值。 已重新啟動此父類別中屬性的預設值。 |

## <a name="remarks"></a>備註

此函式會包裝在呼叫[IWbemClassObject::Delete](/windows/desktop/api/wbemcli/nf-wbemcli-iwbemclassobject-delete)方法。

## <a name="requirements"></a>需求

**平台：** 請參閱[系統需求](../../../../docs/framework/get-started/system-requirements.md)。

**標頭：** WMINet_Utils.idl

**.NET framework 版本：**[!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]

## <a name="see-also"></a>另請參閱

- [WMI 和效能計數器 （Unmanaged API 參考）](index.md)