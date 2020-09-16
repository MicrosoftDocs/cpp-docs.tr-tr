---
title: continue Deyimi (C)
ms.date: 11/04/2016
f1_keywords:
- continue
helpviewer_keywords:
- loop structures, continue keyword
- continue keyword [C]
ms.assetid: 969f293a-45fe-48a7-b4c6-287ba27a631d
ms.openlocfilehash: 27d1d0aa0e49c5c46e4ea4e010635ca0057c3f85
ms.sourcegitcommit: c1fd917a8c06c6504f66f66315ff352d0c046700
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/16/2020
ms.locfileid: "90684839"
---
# <a name="continue-statement-c"></a>continue Deyimi (C)

Deyimi, denetimi,, **`continue`** **`do`** **`for`** **`while`** **`do`** **`for`** veya deyim gövdesinde kalan tüm deyimleri atlayarak en yakın kapsayan, ya da içinde göründüğü deyimin bir sonraki yinelemesine geçirir **`while`** .

## <a name="syntax"></a>Syntax

*sıçrama-deyim*:<br/>
&nbsp;&nbsp;&nbsp;&nbsp;**devam**

**`do`**, **`for`** , Veya ifadesinin sonraki yinelemesi **`while`** aşağıdaki şekilde belirlenir:

- Bir **`do`** veya deyimi içinde **`while`** , bir sonraki yineleme, veya deyiminin ifadesini yeniden değerlendirerek başlar **`do`** **`while`** .

- **`continue`** Bir deyimindeki deyim, **`for`** deyiminin döngü ifadesinin değerlendirilmesine neden olur **`for`** . Sonra derleyici koşullu ifadeyi yeniden değerlendirir ve sonuca bağlı olarak deyim gövdesini sonlandırır ya da yineler. Açıklaması ve terminalleri hakkında daha fazla bilgi için bkz. [for bildirisi](../c-language/for-statement-c.md) **`for`** .

Bu bir **`continue`** deyimin örneğidir:

```C
while ( i-- > 0 )
{
    x = f( i );
    if ( x == 1 )
        continue;
    y += x * x;
}
```

Bu örnekte, deyimin gövdesi `i` 0 ' dan büyük iken yürütülür. Birincisi `f(i)` öğesine atandı `x` ; ardından, 1 ' `x` e eşitse, **`continue`** ifade yürütülür. Gövdedeki deyimlerin geri kalanı yok sayılır ve yürütme döngünün en üstünde döngünün test değerlendirmesi ile devam eder.

## <a name="see-also"></a>Ayrıca bkz.

[Continue bildirisi](../cpp/continue-statement-cpp.md)
