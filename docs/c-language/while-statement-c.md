---
title: while Deyimi (C)
ms.date: 11/04/2016
f1_keywords:
- while
helpviewer_keywords:
- while keyword [C]
- while keyword [C], syntax
ms.assetid: d0c970b8-12a9-4827-afb2-a051111834b7
ms.openlocfilehash: 8095dd8672218239dbcfa879e3df929643e93d90
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/27/2020
ms.locfileid: "87231409"
---
# <a name="while-statement-c"></a>while Deyimi (C)

**`while`** Deyimi, belirtilen bir ifade false olana kadar bir deyimi tekrarlamanızı sağlar.

## <a name="syntax"></a>Sözdizimi

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
