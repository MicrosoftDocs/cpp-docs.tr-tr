---
title: while Deyimi (C++)
ms.date: 11/04/2016
f1_keywords:
- while_cpp
helpviewer_keywords:
- while keyword [C++]
- while keyword [C++], syntax
ms.assetid: 358dbe76-5e5e-4af5-b575-c2293c636899
ms.openlocfilehash: 669618e9807109be18117968b1f5b6f49ec15e07
ms.sourcegitcommit: 1819bd2ff79fba7ec172504b9a34455c70c73f10
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/09/2018
ms.locfileid: "51325984"
---
# <a name="while-statement-c"></a>while Deyimi (C++)

Yürütür *deyimi* kadar sürekli olarak *ifade* sıfır olarak değerlendirilir.

## <a name="syntax"></a>Sözdizimi

```
while ( expression )
   statement
```

## <a name="remarks"></a>Açıklamalar

Testi *ifade* gerçekleşir; döngünün her yürütmesinden önce bu nedenle, bir **sırada** sıfır veya daha fazla kez döngü yürütür. *ifade* integral türünde, bir işaretçi türü veya bir sınıf türünde bir dönüştürmesini integral veya işaretçi türü olmalıdır.

A **sırada** döngü de sonlandırılabilir bir [kesme](../cpp/break-statement-cpp.md), [goto](../cpp/goto-statement-cpp.md), veya [dönüş](../cpp/return-statement-cpp.md) içindeki deyim gövdesi yürütülür. Kullanım [devam](../cpp/continue-statement-cpp.md) çıkmadan geçerli yinelemeyi sonlandırmak için **sırada** döngü. **Devam** denetimi bir sonraki yinelemesine geçirir **sırada** döngü.

Aşağıdaki kod bir **sırada** boşluklar kırpılacak döngü bir dizedeki alt çizgileri:

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