---
description: ': Continue bildirisi hakkında daha fazla bilgi edinin (C++)'
title: continue Deyimi (C++)
ms.date: 11/04/2016
f1_keywords:
- continue_cpp
helpviewer_keywords:
- continue keyword [C++]
ms.assetid: 3c94ee57-f732-4c1d-8537-d0ce5382bfd4
ms.openlocfilehash: 6899e5cd249ab5a7a3b786e4b82c9890c08a7183
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97344646"
---
# <a name="continue-statement-c"></a>continue Deyimi (C++)

Denetimin, en küçük kapsayan [Do](../cpp/do-while-statement-cpp.md), [for](../cpp/for-statement-cpp.md)veya [while](../cpp/while-statement-cpp.md) döngüsünün denetim ifadesine aktarılmasını zorlar.

## <a name="syntax"></a>Syntax

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
