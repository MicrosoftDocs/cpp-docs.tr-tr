---
title: yapın-while deyimi (C++) | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-language
ms.topic: language-reference
f1_keywords:
- do_cpp
dev_langs:
- C++
helpviewer_keywords:
- do keyword [C++], do-while
- do-while keyword [C++]
- do keyword [C++]
- while keyword [C++], do-while
ms.assetid: e01e6f7c-7da1-4591-87f9-c26ff848e7b0
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 37155be11caaee9c609a0e11ddbfeb5d62856903
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/18/2018
ms.locfileid: "46071204"
---
# <a name="do-while-statement-c"></a>do-while Deyimi (C++)

Yürüten bir *deyimi* belirtilen sonlandırma koşulu kadar sürekli olarak ( *ifade*) sıfır olarak değerlendirilir.

## <a name="syntax"></a>Sözdizimi

```
do
   statement
while ( expression ) ;
```

## <a name="remarks"></a>Açıklamalar

Sonlandırma koşulunun testi döngünün her yürütülmesi yapılır; Bu nedenle, bir **yapın-sırada** sonlandırma ifadesinin değerine bağlı olarak bir veya daha fazla kez döngü yürütür. **Yapın-sırada** deyimi de sonlandırılabilir bir [sonu](../cpp/break-statement-cpp.md), [goto](../cpp/goto-statement-cpp.md), veya [dönüş](../cpp/return-statement-cpp.md) deyimi, deyim gövdesi içinde yürütülür.

*İfade* aritmetik veya işaretçi türünde olmalıdır. Yürütme aşağıdaki gibi çalışır:

1. İfade gövdesi yürütülür.

1. Ardından, *ifade* değerlendirilir. Varsa *ifade* false ise **yapın-sırada** deyimi sonlanır ve denetim geçer programdaki sonraki deyime. Varsa *ifade* (sıfırdan farklı) işlem tekrarlanır, adım 1'den itibaren geçerlidir.

## <a name="example"></a>Örnek

Aşağıdaki örnekte **yapın-sırada** deyimi:

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
[Anahtar Sözcükler](../cpp/keywords-cpp.md)<br/>
[while Deyimi (C++)](../cpp/while-statement-cpp.md)<br/>
[for Deyimi (C++)](../cpp/for-statement-cpp.md)<br/>
[Range-based for Deyimi (C++)](../cpp/range-based-for-statement-cpp.md)