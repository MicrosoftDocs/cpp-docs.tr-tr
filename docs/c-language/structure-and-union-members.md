---
title: Yapı ve birleşim üyeleri | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-language
ms.topic: language-reference
dev_langs:
- C++
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
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: c244a55b4e0ebdfadf13e5ee0a3120f024d318af
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/18/2018
ms.locfileid: "46099674"
---
# <a name="structure-and-union-members"></a>Yapı ve Birleşim Üyeleri

"Üye seçimi ifadesi", yapılar ve birleşimler üyelerine ifade eder. Böyle bir ifade, seçilen üyenin türü ve değeri vardır.

> *sonek ifadesi* **.** *tanımlayıcı*
> *sonek ifadesi* ** -> ** *tanımlayıcısı*

Bu liste, iki tür üye seçimi ifadeleri açıklar:

1. İlk biçiminde *sonek ifadesi* değerini temsil eder **yapı** veya **birleşim** türü ve *tanımlayıcı* üye adları Belirtilen yapı veya birleşim. İşlem, değeri *tanımlayıcı* ve bir l-değeri ise *sonek ifadesi* bir l değeridir. Bkz: [L-değeri ve r değeri ifadeleri](../c-language/l-value-and-r-value-expressions.md) daha fazla bilgi için.

1. İkinci biçiminde *sonek ifadesi* bir yapı veya birleşim, bir işaretçiyi temsil eder ve *tanımlayıcı* belirtilen yapı veya birleşim üyesi adları. Değer budur *tanımlayıcı* ve bir l değeridir.

Üye seçim ifadeleri iki formunu benzer etkileri olabilir.

Aslında, üye seçme işleci içeren bir ifade (**->**) dönem kullanan bir ifade toplu sürümüdür (**.**) bir süre önce ifade oluşuyorsa Yöneltme işleci (<strong>\*</strong>) bir işaretçi değerine uygulanır. Bu nedenle,

```cpp
expression->identifier
```

eşdeğerdir

```cpp
(*expression).identifier
```

zaman *ifade* bir işaretçi değeridir.

## <a name="examples"></a>Örnekler

Aşağıdaki örnekler, bu yapı bildirimine bakın. Yöneltme işleci hakkında bilgi için (<strong>\*</strong>) Bu örneklerde kullanılan bkz [yöneltme ve adres işleçleri](../c-language/indirection-and-address-of-operators.md).

```
struct pair
{
    int a;
    int b;
    struct pair *sp;
} item, list[10];
```

Bir üye seçme ifadesi `item` yapısı şu şekilde görünür:

```
item.sp = &item;
```

Adresini yukarıdaki örnekte `item` yapısı atanır `sp` yapı üyesi. Diğer bir deyişle `item` kendisi bir işaretçi içerir.

```
(item.sp)->a = 24;
```

Bu örnekte, işaretçi ifadesi `item.sp` üye seçme işleci ile kullanılan (**->**) üyesi için bir değer atamak için `a`.

```
list[8].b = 12;
```

Bu deyim yapıları dizisinden bir tek bir yapı üyesini seçin gösterilmektedir.

## <a name="see-also"></a>Ayrıca Bkz.

[Üye Erişim İşleçleri: . ve ->](../cpp/member-access-operators-dot-and.md)