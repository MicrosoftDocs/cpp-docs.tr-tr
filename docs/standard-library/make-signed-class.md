---
description: 'Hakkında daha fazla bilgi edinin: make_signed sınıfı'
title: make_signed Sınıfı
ms.date: 11/04/2016
f1_keywords:
- type_traits/std::make_signed
helpviewer_keywords:
- make_signed class
- make_signed
ms.assetid: 686247c0-247c-496b-9b1b-ba9dcd633621
ms.openlocfilehash: 2f11fe3223e6193613772d2c4abbf0182215a17d
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97277563"
---
# <a name="make_signed-class"></a>make_signed Sınıfı

Türü veya en küçük işaretli türü, türe eşit veya ondan büyük olur.

## <a name="syntax"></a>Sözdizimi

```cpp
template <class T>
struct make_signed;

template <class T>
using make_signed_t = typename make_signed<T>::type;
```

### <a name="parameters"></a>Parametreler

*Şı*\
Değiştirilecek tür.

## <a name="remarks"></a>Açıklamalar

Tür değiştiricisinin bir örneği, doğru tutuyorsa *T* olan bir değiştirilmiş türü tutar `is_signed<T>` . Aksi takdirde, için en küçük işaretsiz türdür `UT` `sizeof (T) <= sizeof (UT)` .

## <a name="requirements"></a>Gereksinimler

**Üst bilgi:**\<type_traits>

**Ad alanı:** std

## <a name="see-also"></a>Ayrıca bkz.

[<type_traits>](../standard-library/type-traits.md)
