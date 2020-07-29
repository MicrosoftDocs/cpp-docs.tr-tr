---
title: is_assignable sınıfı
ms.date: 11/04/2016
f1_keywords:
- type_traits/std::is_assignable
helpviewer_keywords:
- is_assignable
ms.assetid: 53444287-c8be-4ad2-9487-a85c066a4f84
ms.openlocfilehash: 2137f6bfb63e93da2c1367a21f608c113e80d196
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/27/2020
ms.locfileid: "87215731"
---
# <a name="is_assignable-class"></a>is_assignable sınıfı

Bir türe bir tür değeri `From` atanıp atanamayacağını sınar `To` .

## <a name="syntax"></a>Söz dizimi

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

Değerlendirilmeyecek ifade `declval<To>() = declval<From>()` düzgün biçimlendirilmiş olmalıdır. Her ikisi de `From` `To` , **`void`** ya da bilinmeyen bir şekilde sınırlı türler veya diziler olmalıdır.

## <a name="requirements"></a>Gereksinimler

**Üst bilgi:**\<type_traits>

**Ad alanı:** std

## <a name="see-also"></a>Ayrıca bkz.

[<type_traits>](../standard-library/type-traits.md)
