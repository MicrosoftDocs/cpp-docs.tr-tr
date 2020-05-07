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

`continue` Deyimi `do`, denetimi,, veya `for` `while` `do` `for` `while` deyim gövdesinde kalan tüm deyimleri atlayarak en yakın kapsayan, ya da içinde göründüğü deyimin bir sonraki yinelemesine geçirir.

## <a name="syntax"></a>Sözdizimi

*sıçrama-deyim*:<br/>
&nbsp;&nbsp;&nbsp;&nbsp;**devam**

`do`, `for`, Veya `while` ifadesinin sonraki yinelemesi aşağıdaki şekilde belirlenir:

- Bir veya `do` `while` deyimi içinde, bir sonraki yineleme, `do` veya `while` deyiminin ifadesini yeniden değerlendirerek başlar.

- Bir `continue` `for` deyimindeki deyim, `for` deyiminin döngü ifadesinin değerlendirilmesine neden olur. Sonra derleyici koşullu ifadeyi yeniden değerlendirir ve sonuca bağlı olarak deyim gövdesini sonlandırır ya da yineler. Açıklaması ve terminalleri hakkında daha fazla bilgi için bkz. [for bildirisi.](../c-language/for-statement-c.md) `for`

Bu bir `continue` deyimin örneğidir:

```
while ( i-- > 0 )
{
    x = f( i );
    if ( x == 1 )
        continue;
    y += x * x;
}
```

Bu örnekte, deyimin gövdesi 0 ' dan büyük iken `i` yürütülür. İlk `f(i)` olarak öğesine `x`atandı; `x` daha sonra, 1 ' e eşitse, `continue` ifade yürütülür. Gövdedeki deyimlerin geri kalanı yok sayılır ve yürütme döngünün en üstünde döngünün test değerlendirmesi ile devam eder.

## <a name="see-also"></a>Ayrıca bkz.

[Continue bildirisi](../cpp/continue-statement-cpp.md)
