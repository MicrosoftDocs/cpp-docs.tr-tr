---
title: continue Deyimi (C)
ms.date: 11/04/2016
f1_keywords:
- continue
helpviewer_keywords:
- loop structures, continue keyword
- continue keyword [C]
ms.assetid: 969f293a-45fe-48a7-b4c6-287ba27a631d
ms.openlocfilehash: 3cf5d1c25b8edc70bd686ca26ad98b15b970383c
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/27/2020
ms.locfileid: "87218916"
---
# <a name="continue-statement-c"></a>continue Deyimi (C)

Deyimi, denetimi,, **`continue`** **`do`** **`for`** **`while`** **`do`** **`for`** veya deyim gövdesinde kalan tüm deyimleri atlayarak en yakın kapsayan, ya da içinde göründüğü deyimin bir sonraki yinelemesine geçirir **`while`** .

## <a name="syntax"></a>Sözdizimi

*sıçrama-deyim*:<br/>
&nbsp;&nbsp;&nbsp;&nbsp;**devam**

**`do`**, **`for`** , Veya ifadesinin sonraki yinelemesi **`while`** aşağıdaki şekilde belirlenir:

- Bir **`do`** veya deyimi içinde **`while`** , bir sonraki yineleme, veya deyiminin ifadesini yeniden değerlendirerek başlar **`do`** **`while`** .

- **`continue`** Bir deyimindeki deyim, **`for`** deyiminin döngü ifadesinin değerlendirilmesine neden olur **`for`** . Sonra derleyici koşullu ifadeyi yeniden değerlendirir ve sonuca bağlı olarak deyim gövdesini sonlandırır ya da yineler. Açıklaması ve terminalleri hakkında daha fazla bilgi için bkz. [for bildirisi](../c-language/for-statement-c.md) **`for`** .

Bu bir **`continue`** deyimin örneğidir:

```
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
