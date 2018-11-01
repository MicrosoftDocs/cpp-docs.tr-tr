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
ms.openlocfilehash: a871c19942252bf6a1a4901f8854b7b759700cd9
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50432805"
---
# <a name="using-operators-in-asm-blocks"></a>__asm Bloklarında İşleçler Kullanma

**Microsoft'a özgü**

Bir `__asm` blok kullanamaz belirli işleçleri, C veya C++ gibi **<<** işleci. Bununla birlikte, işleçler paylaşılan MASM, C ile gibi \* işleci, derleme dili işletmenler olarak yorumlanır. Örneğin dışında bir `__asm` engelleme, köşeli ayraç (**[]**) olarak C, dizideki bir öğe için otomatik olarak ölçeklenen, dizi indisi kapsayan olarak yorumlanır. İçinde bir `__asm` blok, herhangi bir veri nesnesi veya etiket (yalnızca bir dizi) bir ölçeklendirilmemiş bayt uzaklığı verir MASM dizin işleci olarak görülür. Aşağıdaki kod, farkı göstermektedir:

```cpp
int array[10];

__asm mov array[6], bx ;  Store BX at array+6 (not scaled)

array[6] = 0;         /* Store 0 at array+24 (scaled) */
```

Olan ilk başvurunun `array` ölçeklenmez, ancak saniyedir. Kullanabileceğiniz Not **türü** işleci ölçeklendirme elde etmek için temel bir sabit üzerinde. Örneğin, aşağıdaki ifadeleri eşdeğerdir:

```cpp
__asm mov array[6 * TYPE int], 0 ; Store 0 at array + 24

array[6] = 0;                   /* Store 0 at array + 24 */
```

**END Microsoft özgü**

## <a name="see-also"></a>Ayrıca bkz.

[__asm Bloklarında C veya C++ Kullanma](../../assembler/inline/using-c-or-cpp-in-asm-blocks.md)<br/>