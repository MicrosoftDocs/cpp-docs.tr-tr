---
title: Birli İşleçli İfadeler
ms.date: 11/04/2016
helpviewer_keywords:
- expressions [C++], unary operators
- unary operators [C++], expressions with
- expressions [C++], operators
ms.assetid: 1217685b-b85d-4b48-9ff4-d90f56a26c1b
ms.openlocfilehash: 26aad64e5b9c7a496c2e6bb131b82740c06abe07
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/24/2020
ms.locfileid: "80188980"
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

- [sizeof işleci](../cpp/sizeof-operator.md)

- [__uuidof işleci](../cpp/uuidof-operator.md)

- [__alignof işleci](../cpp/alignof-operator.md)

- [New işleci](../cpp/new-operator-cpp.md)

- [delete işleci](../cpp/delete-operator-cpp.md)

Bu operatörlerin sağdan sola ilişkilendirilebilirliği vardır. Birli ifadeler genellikle bir sonek veya birincil ifadeden önce gelen sözdizimini içerir.

Aşağıdakiler, birli ifadelerin olası formlarıdır.

- *sonek ifadesi*

- `++` *birli ifade*

- `--` *birli ifade*

- *birli işleç* *atama ifadesi*

- **sizeof** *birli ifadesi*

- `sizeof(` *tür adı* `)`

- `decltype(` *ifade* `)`

- *Ayırma ifadesi*

- *ayırmayı kaldırma-ifade*

Herhangi bir *sonek* ifadesi bir *birli ifade*olarak değerlendirilir ve herhangi bir birincil ifade bir *sonek ifadesi*olarak kabul edildiğinden, birincil ifadeler de *birli ifade* olarak kabul edilir. Daha fazla bilgi için bkz. [sonek ifadeleri](../cpp/postfix-expressions.md) ve [birincil ifadeler](../cpp/primary-expressions.md).

*Birli işleç* , aşağıdaki simgelerden birini veya daha fazlasını içerir: `* & + - ! ~`

*Cast ifadesi* , türü değiştirmek için isteğe bağlı bir tür dönüştürme içeren birli bir ifadedir. Daha fazla bilgi için bkz. [tür dönüştürme işleci: ()](../cpp/cast-operator-parens.md).

Bir *ifade* herhangi bir ifade olabilir. Daha fazla bilgi için bkz. [ifadeler](../cpp/expressions-cpp.md).

*Ayırma ifadesi* **New** işlecine başvurur. *Ayırmayı kaldırma ifadesi* **Delete** işlecine başvurur. Daha fazla bilgi için bu konunun önceki kısımlarında bulunan bağlantılara bakın.

## <a name="see-also"></a>Ayrıca bkz.

[İfade Türleri](../cpp/types-of-expressions.md)
