---
title: continue Deyimi (C++)
ms.date: 11/04/2016
f1_keywords:
- continue_cpp
helpviewer_keywords:
- continue keyword [C++]
ms.assetid: 3c94ee57-f732-4c1d-8537-d0ce5382bfd4
ms.openlocfilehash: 6fbc4af6a9a56f3406582ea9ba59f4d5759b88a1
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50607486"
---
# <a name="continue-statement-c"></a>continue Deyimi (C++)

En küçük kapsayan denetleme ifade için Denetim aktarımı zorlar [yapmak](../cpp/do-while-statement-cpp.md), [için](../cpp/for-statement-cpp.md), veya [sırada](../cpp/while-statement-cpp.md) döngü.

## <a name="syntax"></a>Sözdizimi

```
continue;
```

## <a name="remarks"></a>Açıklamalar

Kalan tüm geçerli yineleme deyimlerinde yürütülmedi. Döngünün sonraki yinelemesine şu şekilde belirlenir:

- İçinde bir **yapmak** veya **sırada** döngü, sonraki yineleme başlatır, denetleme ifadesiyle reevaluating tarafından **yapmak** veya **sırada** deyimi.

- İçinde bir **için** döngü (söz dizimi kullanılarak `for`(`init-expr`; `cond-expr`; `loop-expr`)), `loop-expr` yan tümcesi yürütülür. Ardından `cond-expr` yan tümcesi yeniden değerlendirimiş ve sonucuna bağlı olarak, döngü ya da sona erer veya başka bir yineleme gerçekleşir.

Aşağıdaki örnekte gösterildiği nasıl **devam** deyimi, kod bölümlerini atlayabilir ve bir döngünün sonraki yinelemesine başlatmak için kullanılabilir.

## <a name="example"></a>Örnek

```cpp
// continue_statement.cpp
#include <stdio.h>
int main()
{
    int i = 0;
    do
    {
        i++;
        printf_s("before the continue\n");
        continue;
        printf("after the continue, should never print\n");
     } while (i < 3);

     printf_s("after the do loop\n");
}
```

```Output
before the continue
before the continue
before the continue
after the do loop
```

## <a name="see-also"></a>Ayrıca bkz.

[Atlama Deyimleri](../cpp/jump-statements-cpp.md)<br/>
[Anahtar Sözcükler](../cpp/keywords-cpp.md)