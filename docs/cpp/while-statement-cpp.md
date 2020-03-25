---
title: while Deyimi (C++)
ms.date: 11/04/2016
f1_keywords:
- while_cpp
helpviewer_keywords:
- while keyword [C++]
- while keyword [C++], syntax
ms.assetid: 358dbe76-5e5e-4af5-b575-c2293c636899
ms.openlocfilehash: 0dfbbb2865c9cf0a23b04ce213a0e739e29c27da
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/24/2020
ms.locfileid: "80187329"
---
# <a name="while-statement-c"></a>while Deyimi (C++)

*Deyim* sıfıra değerlendirilene kadar *deyimi* tekrar tekrar yürütür.

## <a name="syntax"></a>Sözdizimi

```
while ( expression )
   statement
```

## <a name="remarks"></a>Açıklamalar

*İfadenin* testi, döngünün her yürütmeden önce gerçekleşir; Bu nedenle, bir **while** döngüsü sıfır veya daha fazla kez yürütülür. *ifade* bir integral türünde, bir işaretçi türünde veya bir integral veya işaretçi türüne belirsiz bir şekilde dönüştürmeye sahip bir sınıf türünde olmalıdır.

Bir **while** döngüsü, bir [Break](../cpp/break-statement-cpp.md), [goto](../cpp/goto-statement-cpp.md)ya da deyimin gövdesinde [döndürme](../cpp/return-statement-cpp.md) yürütüldüğünde sonlandırılabilir. **While** döngüsünden çıkmadan geçerli yinelemeyi sonlandırmak için [devam](../cpp/continue-statement-cpp.md) ' i kullanın. denetimi **while** döngüsünün bir sonraki yinelemesine **geçirir.**

Aşağıdaki kod bir dizeden sondaki alt çizgileri kırpmak için **while** döngüsünü kullanır:

```cpp
// while_statement.cpp

#include <string.h>
#include <stdio.h>
char *trim( char *szSource )
{
    char *pszEOS = 0;

    //  Set pointer to character before terminating NULL
    pszEOS = szSource + strlen( szSource ) - 1;

    //  iterate backwards until non '_' is found
    while( (pszEOS >= szSource) && (*pszEOS == '_') )
        *pszEOS-- = '\0';

    return szSource;
}
int main()
{
    char szbuf[] = "12345_____";

    printf_s("\nBefore trim: %s", szbuf);
    printf_s("\nAfter trim: %s\n", trim(szbuf));
}
```

Sonlandırma koşulu, döngünün en üstünde değerlendirilir. Hiçbir alt çizgi yoksa, döngü asla yürütülmez.

## <a name="see-also"></a>Ayrıca bkz.

[Yineleme Deyimleri](../cpp/iteration-statements-cpp.md)<br/>
[Anahtar Sözcükler](../cpp/keywords-cpp.md)<br/>
[do-while Deyimi (C++)](../cpp/do-while-statement-cpp.md)<br/>
[for Deyimi (C++)](../cpp/for-statement-cpp.md)<br/>
[Range-based for Deyimi (C++)](../cpp/range-based-for-statement-cpp.md)
