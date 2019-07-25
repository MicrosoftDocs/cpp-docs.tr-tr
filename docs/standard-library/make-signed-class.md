---
title: make_signed Sınıfı
ms.date: 11/04/2016
f1_keywords:
- type_traits/std::make_signed
helpviewer_keywords:
- make_signed class
- make_signed
ms.assetid: 686247c0-247c-496b-9b1b-ba9dcd633621
ms.openlocfilehash: c3c35e28dec3270299329c0186273e324effc2bb
ms.sourcegitcommit: 0dcab746c49f13946b0a7317fc9769130969e76d
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/24/2019
ms.locfileid: "68453679"
---
# <a name="makesigned-class"></a>make_signed Sınıfı

Türü veya en küçük işaretli türü, türe eşit veya ondan büyük olur.

## <a name="syntax"></a>Sözdizimi

```cpp
template <class T>
struct make_signed;

template <class T>
using make_signed_t = typename make_signed<T>::type;
```

### <a name="parameters"></a>Parametreler

*ŞI*\
Değiştirilecek tür.

## <a name="remarks"></a>Açıklamalar

Tür değiştiricisinin bir örneği, doğru `is_signed<T>` tutuyorsa *T* olan bir değiştirilmiş türü tutar. Aksi takdirde, `sizeof (T) <= sizeof (UT)`için en küçük işaretsiz `UT` türdür.

## <a name="requirements"></a>Gereksinimler

**Üst bilgi:** \<type_traits >

**Ad alanı:** std

## <a name="see-also"></a>Ayrıca bkz.

[<type_traits>](../standard-library/type-traits.md)
