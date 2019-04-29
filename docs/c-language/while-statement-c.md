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

`while` İfadesi belirtilen bir ifade false olana kadar bir deyimi yineleyin olanak tanır.

## <a name="syntax"></a>Sözdizimi

*Yineleme deyiminin*:<br/>
&nbsp;&nbsp;&nbsp;&nbsp;**sırada (**  *ifade*  **)**  *deyimi*

*İfade* aritmetik veya işaretçi türünde olmalıdır. Yürütme aşağıdaki gibi çalışır:

1. *İfade* değerlendirilir.

1. Varsa *ifade* başlangıçta yanlış gövdesinin `while` deyimi asla yürütülmez ve denetim geçer `while` programdaki sonraki deyime deyimi.

   Varsa *ifade* true (sıfırdan farklı), deyim gövdesi yürütülür ve adım 1'den itibaren işlem tekrarlanır.

`while` Deyimi de sonlandırılabilir bir **sonu**, `goto`, veya `return` içindeki deyim gövdesi yürütülür. Kullanım **devam** çıkmadan bir yinelemeyi sonlandırmak için deyimi `while` döngü. **Devam** deyimi, denetimi bir sonraki yinelemesine geçirir `while` deyimi.

Bu bir örnektir `while` deyimi:

```C
while ( i >= 0 )
{
    string1[i] = string2[i];
    i--;
}
```

Bu örnek, karakteri kopyalar `string2` için `string1`. Varsa `i` değerinden büyükse veya eşitse 0 `string2[i]` atandığı `string1[i]` ve `i` azaltılır. Zaman `i` ulaştığında veya yürütülmesini 0 düştüğünde `while` deyimini sonlandırır.

## <a name="see-also"></a>Ayrıca bkz.

[while Deyimi (C++)](../cpp/while-statement-cpp.md)
