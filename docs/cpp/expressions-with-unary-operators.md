---
description: 'Hakkında daha fazla bilgi edinin: birli Işleçlere sahip Ifadeler'
title: Birli İşleçli İfadeler
ms.date: 11/04/2016
helpviewer_keywords:
- expressions [C++], unary operators
- unary operators [C++], expressions with
- expressions [C++], operators
ms.assetid: 1217685b-b85d-4b48-9ff4-d90f56a26c1b
ms.openlocfilehash: 6714727d0a4b2c386c37550151df21062534376e
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97186512"
---
# <a name="expressions-with-unary-operators"></a>Birli İşleçli İfadeler

Birli İşleçler bir ifadede yalnızca bir işlenen üzerinde çalışır. Birli işleçler aşağıdaki gibidir:

- [Yöneltme işleci (*)](../cpp/indirection-operator-star.md)

- [Address-of işleci (&)](../cpp/address-of-operator-amp.md)

- [Birli artı işleci (+)](../cpp/unary-plus-and-negation-operators-plus-and.md)

- [Birli olumsuzlama işleci (-)](../cpp/unary-plus-and-negation-operators-plus-and.md)

- [Mantıksal Değilleme İşleci (!)](../cpp/logical-negation-operator-exclpt.md)

- [Tek bir tamamlama işleci (~)](../cpp/one-s-complement-operator-tilde.md)

- [Önek artış işleci (+ +)](../cpp/prefix-increment-and-decrement-operators-increment-and-decrement.md)

- [Önek azaltma işleci (--)](../cpp/prefix-increment-and-decrement-operators-increment-and-decrement.md)

- [Cast işleci ()](../cpp/cast-operator-parens.md)

- [`sizeof` işlecinde](../cpp/sizeof-operator.md)

- [`__uuidof` işlecinde](../cpp/uuidof-operator.md)

- [`alignof` işlecinde](../cpp/alignof-operator.md)

- [`new` işlecinde](../cpp/new-operator-cpp.md)

- [`delete` işlecinde](../cpp/delete-operator-cpp.md)

Bu operatörlerin sağdan sola ilişkilendirilebilirliği vardır. Birli ifadeler genellikle bir sonek veya birincil ifadeden önce gelen sözdizimini içerir.

Aşağıdakiler, birli ifadelerin olası formlarıdır.

- *sonek ifadesi*

- `++` *birli-ifade*

- `--` *birli-ifade*

- *birli işleç* *atama ifadesi*

- **`sizeof`***birli ifade*

- `sizeof(`*tür adı*`)`

- `decltype(`*ifade*`)`

- *Ayırma ifadesi*

- *ayırmayı kaldırma-ifade*

Herhangi bir *sonek* ifadesi bir *birli ifade* olarak değerlendirilir ve herhangi bir birincil ifade bir *sonek ifadesi* olarak kabul edildiğinden, birincil ifadeler de *birli ifade* olarak kabul edilir. Daha fazla bilgi için bkz. [sonek ifadeleri](../cpp/postfix-expressions.md) ve [birincil ifadeler](../cpp/primary-expressions.md).

*Birli işleç* , aşağıdaki simgelerden birini veya daha fazlasını içerir:`* & + - ! ~`

*Cast ifadesi* , türü değiştirmek için isteğe bağlı bir tür dönüştürme içeren birli bir ifadedir. Daha fazla bilgi için bkz. [tür dönüştürme işleci: ()](../cpp/cast-operator-parens.md).

Bir *ifade* herhangi bir ifade olabilir. Daha fazla bilgi için bkz. [ifadeler](../cpp/expressions-cpp.md).

*Ayırma ifadesi* işleci anlamına gelir **`new`** . *Ayırmayı kaldırma ifadesi* işleci anlamına gelir **`delete`** . Daha fazla bilgi için bu konunun önceki kısımlarında bulunan bağlantılara bakın.

## <a name="see-also"></a>Ayrıca bkz.

[Ifade türleri](../cpp/types-of-expressions.md)
