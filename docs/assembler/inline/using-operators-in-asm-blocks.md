---
description: 'Hakkında daha fazla bilgi edinin: __asm bloklarında Işleçler kullanma'
title: __asm Bloklarında İşleçler Kullanma
ms.date: 08/30/2018
helpviewer_keywords:
- brackets [ ]
- brackets [ ], __asm blocks
- __asm keyword [C++], operators
- square brackets [ ], __asm blocks
- operators [C++], using in __asm blocks
- square brackets [ ]
ms.assetid: a26ccfd4-40ae-4a61-952f-c417982aa8dd
ms.openlocfilehash: 266d840e6cb407d45c1d3a49bed6a2390e52aa2e
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97121855"
---
# <a name="using-operators-in-__asm-blocks"></a>__asm Bloklarında İşleçler Kullanma

**Microsoft'a Özgü**

Bir **`__asm`** blok, işleç gibi C veya C++ özel işleçlerini kullanamaz **<<** . Ancak, C ve MASM tarafından paylaşılan işleçler, örneğin işleci, \* Derleme dili işleçleri olarak yorumlanır. Örneğin, bir blok dışında **`__asm`** köşeli ayraçlar (**[]**) kapsayan dizi alt simgeleri olarak yorumlanır ve C, dizideki bir öğenin boyutuna otomatik olarak ölçeklendirilir. Bir **`__asm`** blok içinde, hiçbir veri nesnesinden veya etiketten (yalnızca bir dizi değil) ölçeklendirilmemiş bir bayt boşluğu veren MASM Dizin işleci olarak görülür. Aşağıdaki kod farkı göstermektedir:

```cpp
int array[10];

__asm mov array[6], bx ;  Store BX at array+6 (not scaled)

array[6] = 0;         /* Store 0 at array+24 (scaled) */
```

İçin ilk başvuru `array` ölçeklendirilmez, ancak ikincisi. Bir sabiti temel alarak ölçeklendirmeyi elde etmek için **tür** işlecini kullanabileceğinizi unutmayın. Örneğin, aşağıdaki deyimler eşdeğerdir:

```cpp
__asm mov array[6 * TYPE int], 0 ; Store 0 at array + 24

array[6] = 0;                   /* Store 0 at array + 24 */
```

**SON Microsoft 'a özgü**

## <a name="see-also"></a>Ayrıca bkz.

[__Asm bloklarında C veya C++ kullanma](../../assembler/inline/using-c-or-cpp-in-asm-blocks.md)<br/>
