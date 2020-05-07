---
title: do-while Deyimi (C)
ms.date: 11/04/2016
f1_keywords:
- do
helpviewer_keywords:
- do-while keyword [C]
ms.assetid: f2ac20a6-10c7-4a08-b5e3-c3b3639dbeaf
ms.openlocfilehash: 3658fe7635ad77db6d6e08ff9d7c30e29d665721
ms.sourcegitcommit: 63784729604aaf526de21f6c6b62813882af930a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/17/2020
ms.locfileid: "79438595"
---
# <a name="do-while-statement-c"></a>do-while Deyimi (C)

*Do-while* deyimi, belirtilen bir ifade false olana kadar bir deyimi veya bileşik deyimi tekrarlamanızı sağlar.

## <a name="syntax"></a>Sözdizimi

*yineleme-deyimi*: &nbsp; &nbsp; &nbsp; &nbsp; **Do***deyimi***while (***ifade***);**        

*Do-while* deyimi içindeki *ifade* , döngünün gövdesi yürütüldükten sonra değerlendirilir. Bu nedenle, döngünün gövdesi her zaman en az bir kez yürütülür.

*İfade* aritmetik veya işaretçi türünde olmalıdır. Yürütme aşağıdaki gibi devam eder:

1. İfade gövdesi yürütülür.

1. Sonra *ifade* değerlendirilir. *İfade* false ise *do-while* deyimi sonlanır ve denetim programdaki sonraki deyime geçer. *İfade* true (sıfır dışında) ise işlem, 1. adımdan itibaren yinelenir.

Deyimdeki bir **Break**, **goto**veya **Return** deyimleri yürütüldüğünde *do-while* ifadesini de sonlandırabilirsiniz.

Bu, *do-while* ifadesinin bir örneğidir:

```C
do
{
    y = f( x );
    x--;
} while ( x > 0 );
```

Bu *do-while* deyiminde, başlangıç değerinden bağımsız olarak `y = f( x );` iki `x--;` deyim ve yürütülür `x`. Sonra `x > 0` değerlendirilir. `x` 0 ' dan büyükse, ifade gövdesi yeniden yürütülür ve `x > 0` yeniden değerlendirilirse. Deyimin gövdesi, 0 ' dan büyük `x` kaldığı sürece tekrar tekrar yürütülür. *Do-while* ifadesinin yürütülmesi 0 veya negatif olduğunda `x` sonlanır. Döngünün gövdesi en az bir kez yürütülür.

## <a name="see-also"></a>Ayrıca bkz.

[do-while ekstresi (C++)](../cpp/do-while-statement-cpp.md)
