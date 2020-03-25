---
title: continue Deyimi (C++)
ms.date: 11/04/2016
f1_keywords:
- continue_cpp
helpviewer_keywords:
- continue keyword [C++]
ms.assetid: 3c94ee57-f732-4c1d-8537-d0ce5382bfd4
ms.openlocfilehash: b3790ecfde0af958b3244cfdaa61524ba78d6267
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/24/2020
ms.locfileid: "80180283"
---
# <a name="continue-statement-c"></a>continue Deyimi (C++)

Denetimin, en küçük kapsayan [Do](../cpp/do-while-statement-cpp.md), [for](../cpp/for-statement-cpp.md)veya [while](../cpp/while-statement-cpp.md) döngüsünün denetim ifadesine aktarılmasını zorlar.

## <a name="syntax"></a>Sözdizimi

```
continue;
```

## <a name="remarks"></a>Açıklamalar

Geçerli yinelemedeki kalan deyimler yürütülmedi. Döngünün sonraki yinelemesi şöyle belirlenir:

- **Do** **veya while döngüsünde,** sonraki yineleme **Do** veya **while** deyiminin denetim ifadesini yeniden değerlendirerek başlar.

- Bir **for** döngüsünde (`for`sözdizimini kullanarak (`init-expr`; `cond-expr`; `loop-expr`)), `loop-expr` yan tümcesi yürütülür. Sonra `cond-expr` yan tümcesi yeniden değerlendirilerek, sonuca bağlı olarak döngü sonlanır ya da başka bir yineleme meydana gelir.

Aşağıdaki örnek, **Continue** ifadesinin kod bölümlerini atlamak ve bir sonraki yinelemeye başlamak için nasıl kullanılabileceğini gösterir.

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
