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
ms.openlocfilehash: 65648d62657bf989d4a08660e0fd7724511350c1
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50666303"
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

*örneği*<br/>
Bu işlem tamamlandığında, bir başvuru örneğine *T*.

## <a name="return-value"></a>Dönüş Değeri

Başarılıysa S_OK; Aksi takdirde, hatanın nedenini gösteren HRESULT hatası.

## <a name="requirements"></a>Gereksinimler

**Başlık:** client.h

**Namespace:** Windows::Foundation

## <a name="see-also"></a>Ayrıca Bkz.

[Windows::Foundation Ad Alanı](../windows/windows-foundation-namespace.md)