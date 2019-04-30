---
title: make_signed Sınıfı
ms.date: 11/04/2016
f1_keywords:
- type_traits/std::make_signed
helpviewer_keywords:
- make_signed class
- make_signed
ms.assetid: 686247c0-247c-496b-9b1b-ba9dcd633621
ms.openlocfilehash: c9fe9d54d503f1aa1dfb3debfaeb7649f2e5c18d
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62413066"
---
# <a name="makesigned-class"></a>make_signed Sınıfı

Yapar yazın veya en küçük imzalı büyüktür yazın veya boyutu türü için eşittir.

## <a name="syntax"></a>Sözdizimi

```cpp
template <class T>
struct make_signed;

template <class T>
using make_signed_t = typename make_signed<T>::type;
```

### <a name="parameters"></a>Parametreler

*T*<br/>
Değiştirilecek tür.

## <a name="remarks"></a>Açıklamalar

Tür değiştiricinin bir örneği bir değişiklik-tür tutar *T* varsa `is_signed<T>` geçerlidir. Aksi takdirde, en küçük işaretsiz türe olan `UT` hangi `sizeof (T) <= sizeof (UT)`.

## <a name="requirements"></a>Gereksinimler

**Başlık:** \<type_traits >

**Namespace:** std

## <a name="see-also"></a>Ayrıca bkz.

[<type_traits>](../standard-library/type-traits.md)<br/>
