---
title: ActivateInstance İşlevi
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- client/Windows::Foundation::ActivateInstance
- client/ABI::Windows::Foundation::ActivateInstance
helpviewer_keywords:
- ActivateInstance function
ms.assetid: 8cfd1dd9-5fda-4cc2-acf8-d40e783b3875
ms.openlocfilehash: 43aa34153f0e71dd665090243ff2288bff704404
ms.sourcegitcommit: c7f90df497e6261764893f9cc04b5d1f1bf0b64b
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/05/2019
ms.locfileid: "59029086"
---
# <a name="activateinstance-function"></a>ActivateInstance İşlevi

Kaydeder ve belirtilen sınıf kimliğinde tanımlanan belirli bir türün bir örneğini alır.

## <a name="syntax"></a>Sözdizimi

```cpp
template<typename T>
inline HRESULT ActivateInstance(
   _In_ HSTRING activatableClassId,
   _Out_ Microsoft::WRL::Details::ComPtrRef<T> instance
);
```

### <a name="parameters"></a>Parametreler

*T*<br/>
Etkinleştirmek için bir tür.

*activatableClassId*<br/>
Parametre tanımlayan sınıf kimliği adını *T*.

*örnek*<br/>
Bu işlem tamamlandığında, bir başvuru örneğine *T*.

## <a name="return-value"></a>Dönüş Değeri

Başarılıysa S_OK; Aksi takdirde, hatanın nedenini gösteren HRESULT hatası.

## <a name="requirements"></a>Gereksinimler

**Başlık:** client.h

**Namespace:** Windows::Foundation

## <a name="see-also"></a>Ayrıca bkz.

[Windows::Foundation Ad Alanı](windows-foundation-namespace.md)