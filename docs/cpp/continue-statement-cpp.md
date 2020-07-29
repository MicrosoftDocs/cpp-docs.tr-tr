---
title: continue Deyimi (C++)
ms.date: 11/04/2016
f1_keywords:
- continue_cpp
helpviewer_keywords:
- continue keyword [C++]
ms.assetid: 3c94ee57-f732-4c1d-8537-d0ce5382bfd4
ms.openlocfilehash: 55a81338f1a0f9036a6d42c4bac7c99489c18d64
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/27/2020
ms.locfileid: "87229005"
---
# <a name="continue-statement-c"></a>continue Deyimi (C++)

Denetimin, en küçük kapsayan [Do](../cpp/do-while-statement-cpp.md), [for](../cpp/for-statement-cpp.md)veya [while](../cpp/while-statement-cpp.md) döngüsünün denetim ifadesine aktarılmasını zorlar.

## <a name="syntax"></a>Sözdizimi

```
continue;
```

## <a name="remarks"></a>Açıklamalar

Geçerli yinelemedeki kalan deyimler yürütülmedi. Döngünün sonraki yinelemesi şöyle belirlenir:

- Bir **`do`** veya **`while`** döngüsünde, bir sonraki yineleme, veya deyiminin denetim ifadesini yeniden değerlendirerek başlar **`do`** **`while`** .

- Bir **`for`** döngüde (söz dizimini kullanarak `for( <init-expr> ; <cond-expr> ; <loop-expr> )` ), `<loop-expr>` yan tümce yürütülür. Sonra `<cond-expr>` yan tümce yeniden değerlendirilecektir ve sonuca bağlı olarak, döngü sonlanır ya da başka bir yineleme meydana gelir.

Aşağıdaki örnek, **`continue`** bir ifadenin kod bölümlerini atlamak ve bir sonraki yinelemeye başlamak için nasıl kullanılabileceğini gösterir.

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
[Anahtar sözcükler](../cpp/keywords-cpp.md)
