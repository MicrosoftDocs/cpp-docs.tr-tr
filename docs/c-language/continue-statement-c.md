---
description: ': Continue bildirisi hakkında daha fazla bilgi edinin (C)'
title: continue Deyimi (C)
ms.date: 11/04/2016
f1_keywords:
- continue
helpviewer_keywords:
- loop structures, continue keyword
- continue keyword [C]
ms.assetid: 969f293a-45fe-48a7-b4c6-287ba27a631d
ms.openlocfilehash: 03e6493310655f20e61156d26b88ae2b08a40cdc
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97293254"
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
