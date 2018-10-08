---
title: while Statement (C) | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-language
ms.topic: language-reference
f1_keywords:
- while
dev_langs:
- C++
helpviewer_keywords:
- while keyword [C]
- while keyword [C], syntax
ms.assetid: d0c970b8-12a9-4827-afb2-a051111834b7
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 6993f209f5e7c5ab6f56ae886f2d57ba90a19936
ms.sourcegitcommit: 997e6b7d336cddb388bb6e9e56527725fcaa0624
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/08/2018
ms.locfileid: "48860660"
---
# <a name="while-statement-c"></a>while Deyimi (C)

`while` İfadesi belirtilen bir ifade false olana kadar bir deyimi yineleyin olanak tanır.

## <a name="syntax"></a>Sözdizimi

*Yineleme deyiminin*:<br/>
&nbsp;&nbsp;&nbsp;&nbsp;**sırada (***ifade***)***deyimi*

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

## <a name="see-also"></a>Ayrıca Bkz.

[while Deyimi (C++)](../cpp/while-statement-cpp.md)
