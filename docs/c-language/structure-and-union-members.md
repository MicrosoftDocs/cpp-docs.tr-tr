---
description: 'Daha fazla bilgi edinin: yapı ve birleşim üyeleri'
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
ms.openlocfilehash: f20074157b28763d1db05487043ba0e1576e2d4c
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97137208"
---
# <a name="structure-and-union-members"></a>Yapı ve Birleşim Üyeleri

"Üye seçim ifadesi", yapıların ve birleşimlerin üyelerine başvurur. Böyle bir ifade, seçilen üyenin değerine ve türüne sahiptir.

> *sonek ifadesi* **.** *Tanımlayıcısını*\
> *sonek ifadesi* **->** *tanımlayıcı*

Bu liste, üye seçim ifadelerinin iki biçimini açıklar:

1. İlk formda, *sonek ifadesi* bir değeri **`struct`** veya türü temsil eder **`union`** ve *tanımlayıcı* adları belirtilen yapının veya birleşimin bir üyesi. İşlemin değeri, *tanımlayıcıdır* ve *sonek ifadesi* bir l-değeri ise bir l değeri olur. Daha fazla bilgi için bkz. [L-Value ve R-Value ifadeleri](../c-language/l-value-and-r-value-expressions.md) .

1. İkinci formda, *sonek ifadesi* bir yapıya veya birleşime yönelik bir işaretçi temsil eder ve *tanımlayıcı* adları belirtilen yapının veya birleşimin bir üyesi olarak belirtilir. Değer, *tanımlayıcıdır* ve bir l değeridir.

Üye seçim ifadelerinin iki formu benzer etkilere sahiptir.

Aslında, üye seçim işlecini () içeren bir ifade, **->** dönemden önceki ifade, <strong>\*</strong> bir işaretçi değerine uygulanan yöneltme işlecinden () oluşuyorsa, nokta (.) ile bir ifadenin Özet sürümüdür. Yani:

```cpp
expression->identifier
```

eşdeğerdir

```cpp
(*expression).identifier
```

*ifade* bir işaretçi değeri olduğunda.

## <a name="examples"></a>Örnekler

Aşağıdaki örnekler bu yapı bildirimine başvurur. Bu örneklerde kullanılan yöneltme işleci () hakkında daha fazla bilgi için <strong>\*</strong> bkz. [yöneltme ve adres işleçleri](../c-language/indirection-and-address-of-operators.md).

```
struct pair
{
    int a;
    int b;
    struct pair *sp;
} item, list[10];
```

Yapı için üye seçimi ifadesi `item` Şuna benzer:

```
item.sp = &item;
```

Yukarıdaki örnekte, `item` yapının adresi `sp` yapının üyesine atanır. Bu, `item` kendisi için bir işaretçi içeren anlamına gelir.

```
(item.sp)->a = 24;
```

Bu örnekte, işaretçi ifadesi üyeye `item.sp` **->** bir değer atamak için üye seçim işleci () ile birlikte kullanılır `a` .

```
list[8].b = 12;
```

Bu ifade, bir yapı dizisinden tek bir yapı üyesini nasıl seçinin gösterir.

## <a name="see-also"></a>Ayrıca bkz.

[Üye Erişim İşleçleri: . ve ->](../cpp/member-access-operators-dot-and.md)
