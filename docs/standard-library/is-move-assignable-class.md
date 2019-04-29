---
title: is_move_assignable sınıfı
ms.date: 11/04/2016
f1_keywords:
- type_traits/std::is_move_assignable
helpviewer_keywords:
- is_move_assignable
ms.assetid: f33137f2-0639-4912-8745-bc0f9fd18d28
ms.openlocfilehash: da4734507bac14ecf0278117deb7668518305be0
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62351072"
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
