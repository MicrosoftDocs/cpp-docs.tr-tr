---
description: 'Daha fazla bilgi edinin: ActivateInstance Işlevi'
title: ActivateInstance İşlevi
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- client/Windows::Foundation::ActivateInstance
- client/ABI::Windows::Foundation::ActivateInstance
helpviewer_keywords:
- ActivateInstance function
ms.assetid: 8cfd1dd9-5fda-4cc2-acf8-d40e783b3875
ms.openlocfilehash: 03d7b67810ee2ab287072546b098f81f43687233
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97287859"
---
# <a name="activateinstance-function"></a>ActivateInstance İşlevi

Belirtilen bir sınıf KIMLIĞINDE tanımlanan belirli bir türün bir örneğini kaydeder ve alır.

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
Etkinleştirilecek bir tür.

*Activatableclassıd*<br/>
*T* parametresini TANıMLAYAN sınıf kimliğinin adı.

*Instance*<br/>
Bu işlem tamamlandığında *T* örneğine bir başvuru.

## <a name="return-value"></a>Dönüş Değeri

Başarılı olursa S_OK; Aksi takdirde, hatanın nedenini gösteren bir HRESULT hatası.

## <a name="requirements"></a>Gereksinimler

**Üstbilgi:** Client. h

**Ad alanı:** Windows:: Foundation

## <a name="see-also"></a>Ayrıca bkz.

[Windows:: Foundation ad alanı](windows-foundation-namespace.md)
