---
title: make_unsigned Sınıfı
ms.date: 11/04/2016
f1_keywords:
- type_traits/std::make_unsigned
helpviewer_keywords:
- make_unsigned class
- make_unsigned
ms.assetid: 7a6a3c4f-1a4c-47e8-9ee2-ac1f7b669353
ms.openlocfilehash: 4c0224bd5fd7dc8c6589ae474bb9acb9a8f09cf6
ms.sourcegitcommit: 0dcab746c49f13946b0a7317fc9769130969e76d
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/24/2019
ms.locfileid: "68456318"
---
# <a name="makeunsigned-class"></a>make_unsigned Sınıfı

Türü veya en küçük işaretsiz türü, türe eşit veya ondan büyük olur.

## <a name="syntax"></a>Sözdizimi

```cpp
template <class T>
struct make_unsigned;

template <class T>
using make_unsigned_t = typename make_unsigned<T>::type;
```

### <a name="parameters"></a>Parametreler

|Parametre|Açıklama|
|---------------|-----------------|
|*ŞI*|Değiştirilecek tür.|

## <a name="remarks"></a>Açıklamalar

Tür değiştiricisinin bir örneği, doğru `is_unsigned<T>` tutuyorsa *T* olan bir değiştirilmiş türü tutar. Aksi takdirde, `sizeof (T) <= sizeof (ST)`için en küçük imzalı `ST` türüdür.

## <a name="requirements"></a>Gereksinimler

**Üst bilgi:** \<type_traits >

**Ad alanı:** std

## <a name="see-also"></a>Ayrıca bkz.

[<type_traits>](../standard-library/type-traits.md)
