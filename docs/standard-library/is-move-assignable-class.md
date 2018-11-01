---
title: is_move_assignable sınıfı
ms.date: 11/04/2016
f1_keywords:
- type_traits/std::is_move_assignable
helpviewer_keywords:
- is_move_assignable
ms.assetid: f33137f2-0639-4912-8745-bc0f9fd18d28
ms.openlocfilehash: da4734507bac14ecf0278117deb7668518305be0
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50610372"
---
# <a name="ismoveassignable-class"></a>is_move_assignable sınıfı

Atanan türü olabilir, testleri taşıyın.

## <a name="syntax"></a>Sözdizimi

```cpp
template <class T>
struct is_move_assignable;
```

### <a name="parameters"></a>Parametreler

*T*<br/>
Sorgulanacak tür.

## <a name="remarks"></a>Açıklamalar

Bir türü taşıma atanabilir ise bir başvuru türü bir rvalue başvuru türüne atanabilir. Tür koşulu eşdeğerdir `is_assignable<T&, T&&>`. Atanabilir türleri başvurulabilir skaler türler ve taşıma atama işleçleri derleyici tarafından oluşturulan veya kullanıcı tanımlı olan sınıf türleri taşıyın.

## <a name="requirements"></a>Gereksinimler

**Başlık:** \<type_traits >

**Namespace:** std

## <a name="see-also"></a>Ayrıca bkz.

[<type_traits>](../standard-library/type-traits.md)<br/>
