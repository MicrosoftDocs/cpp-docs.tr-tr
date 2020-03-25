---
title: AsWeak İşlevi
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- client/Microsoft::WRL::AsWeak
helpviewer_keywords:
- AsWeak function
ms.assetid: a6f10cfc-c1d6-4761-adb9-1a119cc99913
ms.openlocfilehash: d11f55d57f4053fd6d46b727a8ed91b340d1764b
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/24/2020
ms.locfileid: "80214181"
---
# <a name="asweak-function"></a>AsWeak İşlevi

Belirtilen örneğe zayıf bir başvuru alır.

## <a name="syntax"></a>Sözdizimi

```cpp
template<typename T>
HRESULT AsWeak(
   _In_ T* p,
   _Out_ WeakRef* pWeak
);
```

### <a name="parameters"></a>Parametreler

*Şı*<br/>
*P*parametresinin türüne yönelik bir işaretçi.

*Lama*<br/>
Bir türün örneği.

*Zayıftır*<br/>
Bu işlem tamamlandığında, *p*parametresine zayıf başvuruya yönelik bir işaretçi.

## <a name="return-value"></a>Dönüş Değeri

S_OK, bu işlem başarılı olursa, Aksi takdirde, hatanın nedenini gösteren bir HRESULT hatası.

## <a name="requirements"></a>Gereksinimler

**Üstbilgi:** Client. h

**Ad alanı:** Microsoft:: WRL

## <a name="see-also"></a>Ayrıca bkz.

[Microsoft::WRL Ad Alanı](microsoft-wrl-namespace.md)
