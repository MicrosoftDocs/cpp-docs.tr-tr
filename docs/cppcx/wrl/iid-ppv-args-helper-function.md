---
title: IID_PPV_ARGS_Helper İşlevi
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- client/IID_PPV_ARGS_Helper
helpviewer_keywords:
- IID_PPV_ARGS_Helper function
ms.assetid: afee9b23-8df1-4575-903f-e9ba748418f0
ms.openlocfilehash: 6b1ab2e8e93fda194532fbc8d6f484aaa91249d8
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/27/2020
ms.locfileid: "87212975"
---
# <a name="iid_ppv_args_helper-function"></a>IID_PPV_ARGS_Helper İşlevi

Belirtilen bağımsız değişkenin türünün arabiriminden türediğini doğrular `IUnknown` .

> [!IMPORTANT]
> Bu şablon özelleştirmesi WRL altyapısını destekler ve doğrudan kodunuzdan kullanılmaya yönelik değildir. Bunun yerine [IID_PPV_ARGS](/windows/win32/api/combaseapi/nf-combaseapi-iid_ppv_args) kullanın.

## <a name="syntax"></a>Söz dizimi

```cpp
template<typename T>
void** IID_PPV_ARGS_Helper(
   _Inout_ Microsoft::WRL::Details::ComPtrRef<T> pp
);
```

### <a name="parameters"></a>Parametreler

*T*<br/>
*PP*bağımsız değişkeninin türü.

*Sy*<br/>
Düzenli olarak dolaylı bir işaretçi.

## <a name="return-value"></a>Dönüş Değeri

Bağımsız değişkeni, işaretçisine bir işaretçiden işaretçiden işaretçisine *PP* **`void`** .

## <a name="remarks"></a>Açıklamalar

Derleme zamanı hatası, *T* şablon parametresi öğesinden türetilmezse oluşturulur `IUnknown` .

## <a name="requirements"></a>Gereksinimler

**Üstbilgi:** Client. h
