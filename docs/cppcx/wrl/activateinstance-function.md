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
ms.openlocfilehash: d1109e769352d412df8348822e05b66063159ee8
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/24/2020
ms.locfileid: "80214233"
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

*Şı*<br/>
Etkinleştirilecek bir tür.

*Activatableclassıd*<br/>
*T*parametresini TANıMLAYAN sınıf kimliğinin adı.

*Instance*<br/>
Bu işlem tamamlandığında *T*örneğine bir başvuru.

## <a name="return-value"></a>Dönüş Değeri

Başarılı olursa S_OK; Aksi takdirde, hatanın nedenini gösteren bir HRESULT hatası.

## <a name="requirements"></a>Gereksinimler

**Üstbilgi:** Client. h

**Ad alanı:** Windows:: Foundation

## <a name="see-also"></a>Ayrıca bkz.

[Windows::Foundation Ad Alanı](windows-foundation-namespace.md)
