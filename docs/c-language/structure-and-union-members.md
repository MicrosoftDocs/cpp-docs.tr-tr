---
title: Yapı ve Birleşim Üyeleri
ms.date: 11/04/2016
helpviewer_keywords:
- member-selection operators
- structure members, referencing
- -> operator, structure and union members
- dot operator (.)
- referencing structure members
- . operator
- operators [C], member selection
- structure member selection
ms.assetid: bb1fe304-af49-4f98-808d-afdc99b3e319
ms.openlocfilehash: b22f5a29a4dc088ea4f3db863d635badee048d2c
ms.sourcegitcommit: 6b749db14b4cf3a2b8d581fda6fdd8cb98bc3207
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/05/2020
ms.locfileid: "82825697"
---
# <a name="structure-and-union-members"></a>Yapı ve Birleşim Üyeleri

"Üye seçim ifadesi", yapıların ve birleşimlerin üyelerine başvurur. Böyle bir ifade, seçilen üyenin değerine ve türüne sahiptir.

> *sonek ifadesi* **.** *Tanımlayıcısını*\
> *sonek-ifade* **->** *tanımlayıcısı*

Bu liste, üye seçim ifadelerinin iki biçimini açıklar:

1. İlk formda, *sonek ifadesi* bir **struct** veya **Union** türü değerini temsil eder ve *tanımlayıcı* adları belirtilen yapının veya birleşimin bir üyesi. İşlemin değeri, *tanımlayıcıdır* ve *sonek ifadesi* bir l-değeri ise bir l değeri olur. Daha fazla bilgi için bkz. [L-Value ve R-Value ifadeleri](../c-language/l-value-and-r-value-expressions.md) .

1. İkinci formda, *sonek ifadesi* bir yapıya veya birleşime yönelik bir işaretçi temsil eder ve *tanımlayıcı* adları belirtilen yapının veya birleşimin bir üyesi olarak belirtilir. Değer, *tanımlayıcıdır* ve bir l değeridir.

Üye seçim ifadelerinin iki formu benzer etkilere sahiptir.

Aslında, üye seçim işlecini (**->**) içeren bir ifade, dönemden önceki ifade, bir işaretçi değerine uygulanan yöneltme işlecinden (<strong>\*</strong>) oluşuyorsa, nokta (**.**) ile bir ifadenin Özet sürümüdür. Bu nedenle,

```cpp
expression->identifier
```

eşdeğerdir

```cpp
(*expression).identifier
```

*ifade* bir işaretçi değeri olduğunda.

## <a name="examples"></a>Örnekler

Aşağıdaki örnekler bu yapı bildirimine başvurur. Bu örneklerde kullanılan yöneltme işleci (<strong>\*</strong>) hakkında daha fazla bilgi için bkz. [yöneltme ve adres işleçleri](../c-language/indirection-and-address-of-operators.md).

```
struct pair
{
    int a;
    int b;
    struct pair *sp;
} item, list[10];
```

`item` Yapı için üye seçimi ifadesi şuna benzer:

```
item.sp = &item;
```

Yukarıdaki örnekte, `item` yapının adresi yapının `sp` üyesine atanır. Bu, `item` kendisi için bir işaretçi içeren anlamına gelir.

```
(item.sp)->a = 24;
```

Bu örnekte, işaretçi ifadesi `item.sp` üyeye bir değer atamak için üye seçim işleci (**->**) ile birlikte kullanılır. `a`

```
list[8].b = 12;
```

Bu ifade, bir yapı dizisinden tek bir yapı üyesini nasıl seçinin gösterir.

## <a name="see-also"></a>Ayrıca bkz.

[Üye Erişim İşleçleri: . ve ->](../cpp/member-access-operators-dot-and.md)
