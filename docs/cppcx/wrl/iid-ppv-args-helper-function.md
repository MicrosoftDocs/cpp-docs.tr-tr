---
title: IID_PPV_ARGS_Helper İşlevi
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- client/IID_PPV_ARGS_Helper
helpviewer_keywords:
- IID_PPV_ARGS_Helper function
ms.assetid: afee9b23-8df1-4575-903f-e9ba748418f0
ms.openlocfilehash: e7733ae6084b64c20dff5a2c35d7a31c614d6e44
ms.sourcegitcommit: fcb48824f9ca24b1f8bd37d647a4d592de1cc925
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/15/2019
ms.locfileid: "69500501"
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

*ŞI*<br/>
*PP*bağımsız değişkeninin türü.

*Sy*<br/>
Düzenli olarak dolaylı bir işaretçi.

## <a name="return-value"></a>Dönüş Değeri

Bağımsız değişkeni, **void**işaretçisine bir işaretçiden işaretçisine *PP* .

## <a name="remarks"></a>Açıklamalar

Derleme zamanı hatası, *T* şablon parametresi öğesinden `IUnknown`türetilmezse oluşturulur.

## <a name="requirements"></a>Gereksinimler

**Üstbilgi:** Client. h

