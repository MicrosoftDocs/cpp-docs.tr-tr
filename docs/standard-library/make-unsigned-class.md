---
title: make_unsigned Sınıfı
ms.date: 11/04/2016
f1_keywords:
- type_traits/std::make_unsigned
helpviewer_keywords:
- make_unsigned class
- make_unsigned
ms.assetid: 7a6a3c4f-1a4c-47e8-9ee2-ac1f7b669353
ms.openlocfilehash: 46b785b20d2ca8ff2de0dfa678b543fa7493aa92
ms.sourcegitcommit: 1839405b97036891b6e4d37c99def044d6f37eff
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/18/2020
ms.locfileid: "88561758"
---
# <a name="make_unsigned-class"></a>make_unsigned Sınıfı

Türü veya en küçük işaretsiz türü, türe eşit veya ondan büyük olur.

## <a name="syntax"></a>Söz dizimi

```cpp
template <class T>
struct make_unsigned;

template <class T>
using make_unsigned_t = typename make_unsigned<T>::type;
```

### <a name="parameters"></a>Parametreler

*Şı*\
Değiştirilecek tür.

## <a name="remarks"></a>Açıklamalar

Tür değiştiricisinin bir örneği, doğru tutuyorsa *T* olan bir değiştirilmiş türü tutar `is_unsigned<T>` . Aksi takdirde, için en küçük imzalı türüdür `ST` `sizeof (T) <= sizeof (ST)` .

## <a name="requirements"></a>Gereksinimler

**Üst bilgi:**\<type_traits>

**Ad alanı:** std

## <a name="see-also"></a>Ayrıca bkz.

[<type_traits>](../standard-library/type-traits.md)
