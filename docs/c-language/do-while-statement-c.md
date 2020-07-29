---
title: do-while Deyimi (C)
ms.date: 11/04/2016
f1_keywords:
- do
helpviewer_keywords:
- do-while keyword [C]
ms.assetid: f2ac20a6-10c7-4a08-b5e3-c3b3639dbeaf
ms.openlocfilehash: 4a10b9df9f7276eb8e241d76726bca26f2c0cb75
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/27/2020
ms.locfileid: "87218877"
---
# <a name="do-while-statement-c"></a>do-while Deyimi (C)

*Do-while* deyimi, belirtilen bir ifade false olana kadar bir deyimi veya bileşik deyimi tekrarlamanızı sağlar.

## <a name="syntax"></a>Sözdizimi

*yineleme-deyimi*: &nbsp; &nbsp; &nbsp; &nbsp; **`do`** *deyim***while (***ifade***);**        

*Do-while* deyimi içindeki *ifade* , döngünün gövdesi yürütüldükten sonra değerlendirilir. Bu nedenle, döngünün gövdesi her zaman en az bir kez yürütülür.

*İfade* aritmetik veya işaretçi türünde olmalıdır. Yürütme aşağıdaki gibi devam eder:

1. İfade gövdesi yürütülür.

1. Sonra *ifade* değerlendirilir. *İfade* false ise *do-while* deyimi sonlanır ve denetim programdaki sonraki deyime geçer. *İfade* true (sıfır dışında) ise işlem, 1. adımdan itibaren yinelenir.

*Do-while* deyimleri **`break`** , bir, **`goto`** veya **`return`** deyimleri deyimin gövdesinde yürütüldüğünde de sonlanabilir.

Bu, *do-while* ifadesinin bir örneğidir:

```C
do
{
    y = f( x );
    x--;
} while ( x > 0 );
```

Bu *do-while* deyiminde, `y = f( x );` başlangıç değerinden bağımsız olarak iki deyim ve `x--;` yürütülür `x` . Sonra `x > 0` değerlendirilir. `x`0 ' dan büyükse, ifade gövdesi yeniden yürütülür ve yeniden `x > 0` değerlendirilirse. Deyimin gövdesi, `x` 0 ' dan büyük kaldığı sürece tekrar tekrar yürütülür. *Do-while* ifadesinin yürütülmesi `x` 0 veya negatif olduğunda sonlanır. Döngünün gövdesi en az bir kez yürütülür.

## <a name="see-also"></a>Ayrıca bkz.

[do-while ekstresi (C++)](../cpp/do-while-statement-cpp.md)
