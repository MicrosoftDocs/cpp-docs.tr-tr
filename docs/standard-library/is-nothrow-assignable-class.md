---
title: is_nothrow_assignable sınıfı
ms.date: 11/04/2016
f1_keywords:
- type_traits/std::is_nothrow_assignable
helpviewer_keywords:
- is_nothrow_assignable
ms.assetid: aa3aca92-308b-4b1d-b3f3-c54216c48fe7
ms.openlocfilehash: 7130079ff58820ec5a8893fd248c5b98fc10c93c
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/27/2020
ms.locfileid: "87222374"
---
# <a name="is_nothrow_assignable-class"></a>is_nothrow_assignable sınıfı

*Türden bir* değerin türüne atanıp atanamayacağını ve atamanın *throw olarak* bilinmediğini sınar.

## <a name="syntax"></a>Söz dizimi

```cpp
template <class To, class From>
struct is_nothrow_assignable;
```

### <a name="parameters"></a>Parametreler

*Hedef*\
Atamayı alan nesnenin türü.

*Kaynak*\
Değer sağlayan nesnenin türü.

## <a name="remarks"></a>Açıklamalar

İfade `declval<To>() = declval<From>()` iyi biçimlendirilmiş olmalıdır ve derleyicinin throw olmaması için bilinmesi gerekir. Hem *öğesinden* hem *de* ' nin, bilinmeyen bir tür, **`void`** veya dizileri olması gerekir.

## <a name="requirements"></a>Gereksinimler

**Üst bilgi:**\<type_traits>

**Ad alanı:** std

## <a name="see-also"></a>Ayrıca bkz.

[<type_traits>](../standard-library/type-traits.md)
