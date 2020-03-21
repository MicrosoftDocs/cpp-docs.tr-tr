---
title: IID_PPV_ARGS_Helper İşlevi
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- client/IID_PPV_ARGS_Helper
helpviewer_keywords:
- IID_PPV_ARGS_Helper function
ms.assetid: afee9b23-8df1-4575-903f-e9ba748418f0
ms.openlocfilehash: 68dbd0b5b2e9d4fc04821a7e7e0193840b55e312
ms.sourcegitcommit: 8e285a766523e653aeeb34d412dc6f615ef7b17b
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/21/2020
ms.locfileid: "80077134"
---
# <a name="iid_ppv_args_helper-function"></a>IID_PPV_ARGS_Helper İşlevi

Belirtilen bağımsız değişkenin türünün `IUnknown` arabiriminden türediğini doğrular.

> [!IMPORTANT]
> Bu şablon özelleştirmesi WRL altyapısını destekler ve doğrudan kodunuzdan kullanılmaya yönelik değildir. Bunun yerine [IID_PPV_ARGS](/windows/win32/api/combaseapi/nf-combaseapi-iid_ppv_args) kullanın.

## <a name="syntax"></a>Sözdizimi

```cpp
template<typename T>
void** IID_PPV_ARGS_Helper(
   _Inout_ Microsoft::WRL::Details::ComPtrRef<T> pp
);
```

### <a name="parameters"></a>Parametreler

*Şı*<br/>
*PP*bağımsız değişkeninin türü.

*Sy*<br/>
Düzenli olarak dolaylı bir işaretçi.

## <a name="return-value"></a>Dönüş Değeri

Bağımsız değişkeni, **void**işaretçisine bir işaretçiden işaretçisine *PP* .

## <a name="remarks"></a>Açıklamalar

Derleme zamanı hatası, *T* şablon parametresi `IUnknown`türetilmezse oluşturulur.

## <a name="requirements"></a>Gereksinimler

**Üstbilgi:** Client. h
