---
title: while Deyimi (C)
ms.date: 11/04/2016
f1_keywords:
- while
helpviewer_keywords:
- while keyword [C]
- while keyword [C], syntax
ms.assetid: d0c970b8-12a9-4827-afb2-a051111834b7
ms.openlocfilehash: 4a789f248702f33342a19f95710a8ae313da1d94
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62344740"
---
# <a name="while-statement-c"></a>while Deyimi (C)

Deyimi `while` , belirtilen bir ifade false olana kadar bir deyimi tekrarlamanızı sağlar.

## <a name="syntax"></a>Sözdizimi

*yineleme-ekstresi*:<br/>
&nbsp;&nbsp;&nbsp;&nbsp;**while (**  *ifade*  **)**  *deyimi*

*İfade* aritmetik veya işaretçi türünde olmalıdır. Yürütme aşağıdaki gibi devam eder:

1. *İfade* değerlendirilir.

1. *İfade* başlangıçta false ise, `while` deyiminin gövdesi hiçbir şekilde yürütülmez ve `while` deyimden programdaki sonraki deyime geçer.

   *İfade* true (sıfır dışında) ise, deyiminin gövdesi yürütülür ve işlem 1. adımdan itibaren yinelenir.

`while` İfade, bir **kesme**, `goto`veya `return` bildiri gövdesinde yürütüldüğünde da sonlandırılabilir. Döngüyü beklemeden bir yinelemeyi sonlandırmak için Continue ifadesini kullanın. **continue** `while` **Continue** deyimleri, denetimi `while` deyimin bir sonraki yinelemesine geçirir.

Bu bir `while` deyimin örneğidir:

```C
while ( i >= 0 )
{
    string1[i] = string2[i];
    i--;
}
```

Bu örnek, ' den `string2` ' `string1`e karakter kopyalar. `i` 0 ' dan büyük veya buna eşitse, `string2[i]` öğesine `string1[i]` atanır ve `i` azaltılır. 0 `i` ' ın altına ulaştığında veya bu değerin altına düştüğünde `while` , deyimin yürütülmesi sonlanır.

## <a name="see-also"></a>Ayrıca bkz.

[while deyimleri (C++)](../cpp/while-statement-cpp.md)
