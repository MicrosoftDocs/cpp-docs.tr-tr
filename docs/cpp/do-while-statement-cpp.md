---
description: 'Şu konuda daha fazla bilgi edinin: do-while ekstresi (C++)'
title: do-while Deyimi (C++)
ms.date: 11/04/2016
f1_keywords:
- do_cpp
helpviewer_keywords:
- do keyword [C++], do-while
- do-while keyword [C++]
- do keyword [C++]
- while keyword [C++], do-while
ms.assetid: e01e6f7c-7da1-4591-87f9-c26ff848e7b0
ms.openlocfilehash: fed7dc3300651dd35326c1eb28e3078538db1301
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97195495"
---
# <a name="do-while-statement-c"></a>do-while Deyimi (C++)

Belirtilen sonlandırma koşulu ( *ifade*) sıfıra değerlendirilene kadar bir *deyimi* sürekli olarak yürütür.

## <a name="syntax"></a>Syntax

```
do
   statement
while ( expression ) ;
```

## <a name="remarks"></a>Açıklamalar

Sonlandırma koşulunun testi, döngünün her yürütülmesinden sonra yapılır; Bu nedenle, sonlandırma ifadesinin değerine bağlı olarak bir **do-while** döngüsü bir veya daha fazla kez yürütülür. Deyimdeki bir [Break](../cpp/break-statement-cpp.md), [goto](../cpp/goto-statement-cpp.md)veya [Return](../cpp/return-statement-cpp.md) deyimleri yürütüldüğünde **do-while** ifadesini de sonlandırabilirsiniz.

*İfade* aritmetik veya işaretçi türünde olmalıdır. Yürütme aşağıdaki gibi devam eder:

1. İfade gövdesi yürütülür.

1. Sonra *ifade* değerlendirilir. *İfade* false ise **do-while** deyimi sonlanır ve denetim programdaki sonraki deyime geçer. *İfade* true (sıfır dışında) ise işlem, 1. adımdan itibaren yinelenir.

## <a name="example"></a>Örnek

Aşağıdaki örnek **do-while** ifadesini göstermektedir:

```cpp
// do_while_statement.cpp
#include <stdio.h>
int main()
{
    int i = 0;
    do
    {
        printf_s("\n%d",i++);
    } while (i < 3);
}
```

## <a name="see-also"></a>Ayrıca bkz.

[Yineleme Deyimleri](../cpp/iteration-statements-cpp.md)<br/>
[Anahtar sözcükler](../cpp/keywords-cpp.md)<br/>
[while deyimleri (C++)](../cpp/while-statement-cpp.md)<br/>
[for deyimleri (C++)](../cpp/for-statement-cpp.md)<br/>
[Range-based for Deyimi (C++)](../cpp/range-based-for-statement-cpp.md)
