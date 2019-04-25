---
title: do-while Deyimi (C)
ms.date: 11/04/2016
f1_keywords:
- do
- while
helpviewer_keywords:
- do-while keyword [C]
ms.assetid: f2ac20a6-10c7-4a08-b5e3-c3b3639dbeaf
ms.openlocfilehash: 052b02beca49f5de19c6f68cc475edb5f5daf6e2
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62234085"
---
# <a name="do-while-statement-c"></a>do-while Deyimi (C)

*Yapın-sırada* ifadesi belirtilen bir ifade yanlış olana kadar bir deyimi veya bileşik deyim Yinele olanak tanır.

## <a name="syntax"></a>Sözdizimi

*Yineleme deyiminin*: &nbsp; &nbsp; &nbsp; &nbsp; **yapmak** *deyimi* **sırada (** *ifade* **);**

*İfade* içinde bir *yapın-sırada* deyimi, döngü gövdesinin yürütüldükten sonra değerlendirilir. Bu nedenle, döngü gövdesinin her zaman en az bir kez yürütülür.

*İfade* aritmetik veya işaretçi türünde olmalıdır. Yürütme aşağıdaki gibi çalışır:

1. İfade gövdesi yürütülür.

1. Ardından, *ifade* değerlendirilir. Varsa *ifade* false ise *yapın-sırada* deyimi sonlanır ve denetim geçer programdaki sonraki deyime. Varsa *ifade* (sıfırdan farklı) işlem tekrarlanır, adım 1'den itibaren geçerlidir.

*Yapın-sırada* deyimi de sonlandırılabilir bir **sonu**, **goto**, veya **dönüş** deyimi, deyim gövdesi içinde yürütülür.

Bu bir örnektir *yapın-sırada* deyimi:

```C
do
{
    y = f( x );
    x--;
} while ( x > 0 );
```

Bu *yapın-sırada* deyimi, iki deyim `y = f( x );` ve `x--;` başlangıç değerine bakılmaksızın yürütülür `x`. Ardından `x > 0` değerlendirilir. Varsa `x` 0'dan büyük olan deyim gövdesi yeniden yürütülür ve `x > 0` değerlendirilir. Deyim gövdesi sürekli çalıştırılan sürece `x` 0'dan büyük olarak kalır. Yürütülmesini *yapın-sırada* açıklamayı sonlandıran `x` 0 veya negatif olur. Döngü gövdesi en az bir kez yürütülür.

## <a name="see-also"></a>Ayrıca bkz.

[do-while Deyimi (C++)](../cpp/do-while-statement-cpp.md)
