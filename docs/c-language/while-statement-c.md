---
description: 'Daha fazla bilgi edinin: while (C)'
title: while Deyimi (C)
ms.date: 11/04/2016
f1_keywords:
- while
helpviewer_keywords:
- while keyword [C]
- while keyword [C], syntax
ms.assetid: d0c970b8-12a9-4827-afb2-a051111834b7
ms.openlocfilehash: 3461372de48980a0591f890fdd366c9373aea78f
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97221858"
---
# <a name="while-statement-c"></a>while Deyimi (C)

**`while`** Deyimi, belirtilen bir ifade false olana kadar bir deyimi tekrarlamanızı sağlar.

## <a name="syntax"></a>Syntax

*yineleme-ekstresi*:<br/>
&nbsp;&nbsp;&nbsp;&nbsp;**while (**  *ifade*  **)**  *deyimi*

*İfade* aritmetik veya işaretçi türünde olmalıdır. Yürütme aşağıdaki gibi devam eder:

1. *İfade* değerlendirilir.

1. *İfade* başlangıçta false ise, **`while`** deyiminin gövdesi hiçbir şekilde yürütülmez ve **`while`** deyimden programdaki sonraki deyime geçer.

   *İfade* true (sıfır dışında) ise, deyiminin gövdesi yürütülür ve işlem 1. adımdan itibaren yinelenir.

**`while`** İfade, bir **`break`** , **`goto`** , veya **`return`** bildiri gövdesinde yürütüldüğünde de sonlanabilir. **`continue`** Döngüsünden çıkmadan bir yinelemeyi sonlandırmak için ifadesini kullanın **`while`** . **`continue`** İfade, denetimi deyimin bir sonraki yinelemesine geçirir **`while`** .

Bu bir **`while`** deyimin örneğidir:

```C
while ( i >= 0 )
{
    string1[i] = string2[i];
    i--;
}
```

Bu örnek, ' den ' e karakter kopyalar `string2` `string1` . `i`0 ' dan büyük veya buna eşitse, `string2[i]` öğesine atanır `string1[i]` ve `i` azaltılır. `i`0 ' ın altına ulaştığında veya bu değerin altına düştüğünde, **`while`** deyimin yürütülmesi sonlanır.

## <a name="see-also"></a>Ayrıca bkz.

[while deyimleri (C++)](../cpp/while-statement-cpp.md)
