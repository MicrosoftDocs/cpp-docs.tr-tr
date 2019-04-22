---
title: AsWeak İşlevi
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- client/Microsoft::WRL::AsWeak
helpviewer_keywords:
- AsWeak function
ms.assetid: a6f10cfc-c1d6-4761-adb9-1a119cc99913
ms.openlocfilehash: 45df6332fccb2a22284eb6478c7554d87318ca78
ms.sourcegitcommit: 72583d30170d6ef29ea5c6848dc00169f2c909aa
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/18/2019
ms.locfileid: "59021404"
---
# <a name="asweak-function"></a>AsWeak İşlevi

Belirtilen bir örneğe zayıf bir başvuru alır.

## <a name="syntax"></a>Sözdizimi

```cpp
template<typename T>
HRESULT AsWeak(
   _In_ T* p,
   _Out_ WeakRef* pWeak
);
```

### <a name="parameters"></a>Parametreler

*T*<br/>
Parametresinin türü için bir işaretçi *p*.

*p*<br/>
Bir tür örneği.

*pWeak*<br/>
Bu işlem tamamlandığında, zayıf bir başvuru parametresi için bir işaretçiye *p*.

## <a name="return-value"></a>Dönüş Değeri

Bu işlem başarılı olursa S_OK; Aksi takdirde, hatanın nedenini gösteren HRESULT hatası.

## <a name="requirements"></a>Gereksinimler

**Başlık:** client.h

**Namespace:** Microsoft::WRL

## <a name="see-also"></a>Ayrıca bkz.

[Microsoft::WRL Ad Alanı](microsoft-wrl-namespace.md)