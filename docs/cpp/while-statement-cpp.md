---
description: ': While Ifadesinin hakkında daha fazla bilgi edinin (C++)'
title: while Deyimi (C++)
ms.date: 11/04/2016
f1_keywords:
- while_cpp
helpviewer_keywords:
- while keyword [C++]
- while keyword [C++], syntax
ms.assetid: 358dbe76-5e5e-4af5-b575-c2293c636899
ms.openlocfilehash: 3001760372410222651366416ac74d0cba59f23b
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97302835"
---
# <a name="while-statement-c"></a>while Deyimi (C++)

*Deyim* sıfıra değerlendirilene kadar *deyimi* tekrar tekrar yürütür.

## <a name="syntax"></a>Syntax

```
while ( expression )
   statement
```

## <a name="remarks"></a>Açıklamalar

*İfadenin* testi, döngünün her yürütmeden önce gerçekleşir; Bu nedenle, bir **`while`** döngü sıfır veya daha fazla kez yürütülür. *ifade* bir integral türünde, bir işaretçi türünde veya bir integral veya işaretçi türüne belirsiz bir şekilde dönüştürmeye sahip bir sınıf türünde olmalıdır.

Bir **`while`** döngü, bir [Break](../cpp/break-statement-cpp.md), [goto](../cpp/goto-statement-cpp.md)ya da deyimin gövdesinde [döndürme](../cpp/return-statement-cpp.md) yürütüldüğünde de sonlanabilir. Döngüden çıkmadan geçerli yinelemeyi sonlandırmak için [devam](../cpp/continue-statement-cpp.md) ' i kullanın **`while`** . **`continue`** denetimi döngünün bir sonraki yinelemesine geçirir **`while`** .

Aşağıdaki kod bir **`while`** dizeden sondaki alt çizgileri kırpmak için bir döngü kullanır:

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
[Anahtar sözcükler](../cpp/keywords-cpp.md)<br/>
[do-while ekstresi (C++)](../cpp/do-while-statement-cpp.md)<br/>
[for deyimleri (C++)](../cpp/for-statement-cpp.md)<br/>
[Range-based for Deyimi (C++)](../cpp/range-based-for-statement-cpp.md)
