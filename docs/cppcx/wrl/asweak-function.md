---
description: 'Daha fazla bilgi edinin: Aszayıf Işlev'
title: AsWeak İşlevi
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- client/Microsoft::WRL::AsWeak
helpviewer_keywords:
- AsWeak function
ms.assetid: a6f10cfc-c1d6-4761-adb9-1a119cc99913
ms.openlocfilehash: a02776f06aab4d7505b38fbb1120c36a82e97368
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97175852"
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

*T*<br/>
*P* parametresinin türüne yönelik bir işaretçi.

*Lama*<br/>
Bir türün örneği.

*Zayıftır*<br/>
Bu işlem tamamlandığında, *p* parametresine zayıf başvuruya yönelik bir işaretçi.

## <a name="return-value"></a>Dönüş Değeri

S_OK, bu işlem başarılı olursa, Aksi takdirde, hatanın nedenini gösteren bir HRESULT hatası.

## <a name="requirements"></a>Gereksinimler

**Üstbilgi:** Client. h

**Ad alanı:** Microsoft:: WRL

## <a name="see-also"></a>Ayrıca bkz.

[Microsoft:: WRL ad alanı](microsoft-wrl-namespace.md)
