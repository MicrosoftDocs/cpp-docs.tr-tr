---
title: Birli işleçli ifadeler | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-language
ms.topic: language-reference
dev_langs:
- C++
helpviewer_keywords:
- expressions [C++], unary operators
- unary operators [C++], expressions with
- expressions [C++], operators
ms.assetid: 1217685b-b85d-4b48-9ff4-d90f56a26c1b
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 718b27d14414480a3515a212bc0b272e8cfbb7c2
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/18/2018
ms.locfileid: "46017878"
---
# <a name="expressions-with-unary-operators"></a>Birli İşleçli İfadeler

Birli işleçler yalnızca tek bir işlenen bir ifadede gerçekleştir. Birli işleçleri aşağıdaki gibidir:

- [Yöneltme işleci (*)](../cpp/indirection-operator-star.md)

- [Address-of işleci (&)](../cpp/address-of-operator-amp.md)

- [Tek İşlenenli artı (+)](../cpp/unary-plus-and-negation-operators-plus-and.md)

- [Tekli değilleme işleci (-)](../cpp/unary-plus-and-negation-operators-plus-and.md)

- [Mantıksal değilleme işleci (!)](../cpp/logical-negation-operator-exclpt.md)

- [Birinin tamamlama işleci (~)](../cpp/one-s-complement-operator-tilde.md)

- [Önek artırma işleci (++)](../cpp/prefix-increment-and-decrement-operators-increment-and-decrement.md)

- [Önek azaltma işleci (-)](../cpp/prefix-increment-and-decrement-operators-increment-and-decrement.md)

- [Atama işleci (.)](../cpp/cast-operator-parens.md)

- [sizeof işleci](../cpp/sizeof-operator.md)

- [__uuidof işleci](../cpp/uuidof-operator.md)

- [__alignof işleci](../cpp/alignof-operator.md)

- [New işleci](../cpp/new-operator-cpp.md)

- [delete işleci](../cpp/delete-operator-cpp.md)

Bu işleçler, sağdan sola birleşme özelliği içindedir. Tekli ifade, genellikle bir sonek veya birincil ifade önündeki söz dizimi içerir.

Tekli ifade olası form aşağıda verilmiştir.

- *sonek ifadesi*

- `++` *Tekli ifade*

- `--` *Tekli ifade*

- *birli işleç* *atama ifadesi*

- **sizeof** *tekli ifade*

- `sizeof(` *tür adı* `)`

- `decltype(` *İfade* `)`

- *ayırma-ifadesi*

- *ayırmayı kaldırma ifadesi*

Tüm *sonek ifadesi* değerlendirilir bir *tekli ifade*, ve herhangi bir birincil ifade olduğu kabul edildiği için bir *sonek ifadesi*, olan herhangi bir birincil ifadeler kabul bir *tekli ifade* de. Daha fazla bilgi için [sonek ifadeleri](../cpp/postfix-expressions.md) ve [birincil ifadeler](../cpp/primary-expressions.md).

A *birli işleç* bir veya daha fazla şu sembollerden biri oluşur: `* & + - ! ~`

*Atama ifadesini* türünü değiştirmek için isteğe bağlı bir tür dönüştürme ile birli ifadesidir. Daha fazla bilgi için [atama işleci: ()](../cpp/cast-operator-parens.md).

Bir *ifade* herhangi bir ifade olabilir. Daha fazla bilgi için [ifadeleri](../cpp/expressions-cpp.md).

*Ayırma ifade* başvurduğu **yeni** işleci. *Ayırmayı kaldırma ifade* başvurduğu **Sil** işleci. Daha fazla bilgi için bu konunun önceki kısımlarında bağlantılara bakın.

## <a name="see-also"></a>Ayrıca bkz.

[İfade Türleri](../cpp/types-of-expressions.md)