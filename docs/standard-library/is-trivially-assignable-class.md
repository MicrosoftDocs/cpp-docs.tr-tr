---
title: is_trivially_assignable sınıfı
ms.date: 11/04/2016
f1_keywords:
- type_traits/std::is_trivially_assignable
helpviewer_keywords:
- is_trivially_assignable
ms.assetid: 1284a8f7-4093-426d-9c9a-dabb46f90d6d
ms.openlocfilehash: 14a3ee638bd6df3b52e7327ca6e3c77f4a0e8b71
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/27/2020
ms.locfileid: "87224870"
---
# <a name="is_trivially_assignable-class"></a>is_trivially_assignable sınıfı

Türünde bir değerin, türe göre bir değere `From` atanıp atanamayacağını test eder `To`

## <a name="syntax"></a>Söz dizimi

```cpp
template <class To, class From>
struct is_trivially_assignable;
```

### <a name="parameters"></a>Parametreler

*Hedef*\
Atamayı alan nesnenin türü.

*Kaynak*\
Değer sağlayan nesnenin türü.

## <a name="remarks"></a>Açıklamalar

İfade `declval<To>() = declval<From>()` iyi biçimlendirilmiş olmalıdır ve önemsiz olmayan işlemler gerektirmeyen derleyici tarafından bilinmelidir. Her ikisi de `From` `To` , **`void`** ya da bilinmeyen bir şekilde sınırlı türler veya diziler olmalıdır.

## <a name="requirements"></a>Gereksinimler

**Üst bilgi:**\<type_traits>

**Ad alanı:** std

## <a name="see-also"></a>Ayrıca bkz.

[<type_traits>](../standard-library/type-traits.md)
