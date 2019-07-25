---
title: is_assignable sınıfı
ms.date: 11/04/2016
f1_keywords:
- type_traits/std::is_assignable
helpviewer_keywords:
- is_assignable
ms.assetid: 53444287-c8be-4ad2-9487-a85c066a4f84
ms.openlocfilehash: 33b0ce6112119c935ff70e5d619b284acc6ee8c2
ms.sourcegitcommit: 0dcab746c49f13946b0a7317fc9769130969e76d
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/24/2019
ms.locfileid: "68456675"
---
# <a name="isassignable-class"></a>is_assignable sınıfı

Bir türe bir tür değeri `From` atanıp atanamayacağını `To` sınar.

## <a name="syntax"></a>Sözdizimi

```cpp
template <class To, class From>
struct is_assignable;
```

### <a name="parameters"></a>Parametreler

*Hedef*\
Atamayı alan nesnenin türü.

*Kaynak*\
Değer sağlayan nesnenin türü.

## <a name="remarks"></a>Açıklamalar

Değerlendirilmeyecek ifade `declval<To>() = declval<From>()` düzgün biçimlendirilmiş olmalıdır. Her ikisi de `From` , bilinmeyen türler, **void**veya diziler türünde olmalıdır.`To`

## <a name="requirements"></a>Gereksinimler

**Üst bilgi:** \<type_traits >

**Ad alanı:** std

## <a name="see-also"></a>Ayrıca bkz.

[<type_traits>](../standard-library/type-traits.md)
