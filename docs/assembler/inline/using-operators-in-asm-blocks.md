---
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
ms.openlocfilehash: b6ac9f7174baf1e0ebe41181c6a6f43e7bb3f5d1
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/24/2020
ms.locfileid: "80169103"
---
# <a name="using-operators-in-__asm-blocks"></a>__asm Bloklarında İşleçler Kullanma

**Microsoft 'a özgü**

`__asm` bloğu, **<<** Işleci gibi C C++ veya özel işleçleri kullanamaz. Ancak, C ve MASM tarafından paylaşılan işleçler, \* işleci gibi, derleme dili işleçleri olarak yorumlanır. Örneğin, bir `__asm` bloğunun dışında köşeli ayraçlar ( **[]** ) kapsayan dizi alt simgeleri olarak yorumlanır ve C, dizideki bir öğenin boyutuna otomatik olarak ölçeklendirilir. `__asm` bloğu içinde, hiçbir veri nesnesinden veya etiketten (yalnızca bir dizi değil) ölçeklendirilmemiş bir bayt boşluğu veren MASM Dizin işleci olarak görülür. Aşağıdaki kod farkı göstermektedir:

```cpp
int array[10];

__asm mov array[6], bx ;  Store BX at array+6 (not scaled)

array[6] = 0;         /* Store 0 at array+24 (scaled) */
```

`array` ilk başvurusu ölçeklendirilmez, ikincisi ise. Bir sabiti temel alarak ölçeklendirmeyi elde etmek için **tür** işlecini kullanabileceğinizi unutmayın. Örneğin, aşağıdaki deyimler eşdeğerdir:

```cpp
__asm mov array[6 * TYPE int], 0 ; Store 0 at array + 24

array[6] = 0;                   /* Store 0 at array + 24 */
```

**SON Microsoft 'a özgü**

## <a name="see-also"></a>Ayrıca bkz.

[__asm Bloklarında C veya C++ Kullanma](../../assembler/inline/using-c-or-cpp-in-asm-blocks.md)<br/>
