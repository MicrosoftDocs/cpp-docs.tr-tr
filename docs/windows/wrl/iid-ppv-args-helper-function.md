---
title: IID_PPV_ARGS_Helper İşlevi
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- client/IID_PPV_ARGS_Helper
helpviewer_keywords:
- IID_PPV_ARGS_Helper function
ms.assetid: afee9b23-8df1-4575-903f-e9ba748418f0
ms.openlocfilehash: 5ef4dd6c9db2d19e0c8a4143c5b4ed3f0ac75f6a
ms.sourcegitcommit: c85c8a1226d8fbbaa29f4691ed719f8e6cc6575c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/24/2019
ms.locfileid: "54894126"
---
# <a name="iidppvargshelper-function"></a>IID_PPV_ARGS_Helper İşlevi

Belirtilen bağımsız değişken türü öğesinden türetilen doğrular `IUnknown` arabirimi.

> [!IMPORTANT]
> Bu şablon uzmanlığı WRL altyapısını destekler ve doğrudan kodunuzdan kullanılmaya yönelik değildir. Kullanım [IID_PPV_ARGS](/windows/desktop/api/combaseapi/nf-combaseapi-iid_ppv_args) yerine.

## <a name="syntax"></a>Sözdizimi

```cpp
template<typename T>
void** IID_PPV_ARGS_Helper(
   _Inout_ Microsoft::WRL::Details::ComPtrRef<T> pp
);
```

### <a name="parameters"></a>Parametreler

*T*<br/>
Bağımsız değişken türünü *pp*.

*PP*<br/>
Karakteriyle dolaylı bir işaretçi.

## <a name="return-value"></a>Dönüş Değeri

Bağımsız değişken *pp* işaretçi-için-a-işaretçisine dönüştürme **void**.

## <a name="remarks"></a>Açıklamalar

Bir derleme zamanı hatası oluşturulur şablon parametresi *T* öğesinden türetilen değil `IUnknown`.

## <a name="requirements"></a>Gereksinimler

**Başlık:** client.h

