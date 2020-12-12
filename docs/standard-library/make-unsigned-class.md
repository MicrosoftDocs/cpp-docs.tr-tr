---
description: 'Hakkında daha fazla bilgi edinin: make_unsigned sınıfı'
title: make_unsigned Sınıfı
ms.date: 11/04/2016
f1_keywords:
- type_traits/std::make_unsigned
helpviewer_keywords:
- make_unsigned class
- make_unsigned
ms.assetid: 7a6a3c4f-1a4c-47e8-9ee2-ac1f7b669353
ms.openlocfilehash: 3767a9971c17667b5d2fe545e524f563df2a7f42
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97277524"
---
# <a name="make_unsigned-class"></a>make_unsigned Sınıfı

Türü veya en küçük işaretsiz türü, türe eşit veya ondan büyük olur.

## <a name="syntax"></a>Sözdizimi

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
