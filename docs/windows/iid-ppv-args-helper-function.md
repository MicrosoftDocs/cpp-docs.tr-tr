---
title: IID_PPV_ARGS_Helper İşlevi
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- client/IID_PPV_ARGS_Helper
helpviewer_keywords:
- IID_PPV_ARGS_Helper function
ms.assetid: afee9b23-8df1-4575-903f-e9ba748418f0
ms.openlocfilehash: cae29c70c551701a351cdcf404342ed1634a0e3b
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50467424"
---
# <a name="iidppvargshelper-function"></a>IID_PPV_ARGS_Helper İşlevi

Belirtilen bağımsız değişken türü öğesinden türetilen doğrular `IUnknown` arabirimi.

> [!IMPORTANT]
> Bu şablon uzmanlığı WRL altyapısını destekler ve doğrudan kodunuzdan kullanılmaya yönelik değildir. Kullanım [IID_PPV_ARGS](https://msdn.microsoft.com/library/windows/desktop/ee330727.aspx) yerine.

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

