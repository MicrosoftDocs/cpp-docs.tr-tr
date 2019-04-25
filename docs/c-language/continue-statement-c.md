---
title: continue Deyimi (C)
ms.date: 11/04/2016
f1_keywords:
- continue
helpviewer_keywords:
- loop structures, continue keyword
- continue keyword [C]
ms.assetid: 969f293a-45fe-48a7-b4c6-287ba27a631d
ms.openlocfilehash: 983775e6fe9887afa5784358ede1de9583b3afba
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62312569"
---
# <a name="continue-statement-c"></a>continue Deyimi (C)

`continue` Deyimi, denetimi en yakın kapsayan bir sonraki yinelemesine geçirir `do`, `for`, veya `while` göründüğü, kalan tüm deyimlerinde atlama deyimi `do`, `for`, veya `while` deyim gövdesi.

## <a name="syntax"></a>Sözdizimi

*atlama-deyimi*:<br/>
&nbsp;&nbsp;&nbsp;&nbsp;**devam edin.**

Sonraki yinelemesine bir `do`, `for`, veya `while` deyimi aşağıdaki gibi belirlenir:

- İçinde bir `do` veya `while` deyimi, sonraki yineleme başlatır ifade reevaluating tarafından `do` veya `while` deyimi.

- A `continue` deyiminde bir `for` deyimi, döngü ifadesi neden `for` değerlendirilecek ifade. Ardından derleyici koşullu ifade reevaluates ve sonuç bağlı olarak ya da sona erer veya deyim gövdesi yinelenir. Bkz: [deyimi için](../c-language/for-statement-c.md) hakkında daha fazla bilgi için `for` deyimi ve kendi Terminal dışı.

Bu bir örnektir `continue` deyimi:

```
while ( i-- > 0 )
{
    x = f( i );
    if ( x == 1 )
        continue;
    y += x * x;
}
```

Bu örnekte, deyim gövdesi yürütülür ancak `i` 0'dan büyük. İlk `f(i)` atandığı `x`; daha sonra eğer `x` 1'e eşit olduğunu `continue` deyimi yürütülür. Gövde deyimlerin geri kalanını yok sayılır ve döngünün test değerlendirmesi ile döngüsü üstünde yürütmeyi devam ettirir.

## <a name="see-also"></a>Ayrıca bkz.

[continue Deyimi](../cpp/continue-statement-cpp.md)
