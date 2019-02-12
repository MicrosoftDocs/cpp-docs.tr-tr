---
title: Parantezlerdeki İfadeler
ms.date: 11/04/2016
helpviewer_keywords:
- parentheses
- expression evaluation, evaluation order
- expressions [C++], evaluating
- parentheses, expressions
ms.assetid: b8636147-6982-408c-9e64-29e40678ee43
ms.openlocfilehash: d0105556530161991b46c5ee25cd73f2f995063f
ms.sourcegitcommit: f4be868c0d1d78e550fba105d4d3c993743a1f4b
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 02/12/2019
ms.locfileid: "56149355"
---
# <a name="expressions-in-parentheses"></a>Parantezlerdeki İfadeler

Herhangi bir işlenen türü veya kapalı ifadenin değerini değiştirmeden parantez içine. Örneğin, ifade:

```
( 10 + 5 ) / 5
```

çevresindeki parantezler `10 + 5` değerini anlamına `10 + 5` ilk olarak değerlendirilir ve bu duruma bölme sol işleneni (**/**) işleci. Sonucu `( 10 + 5 ) / 5` 3'tür. Parantez olmadan `10 + 5 / 5` 11'e değerlendirecek.

Parantez işlenen bir ifadede gruplandırılır şeklini etkileyen olsa da, belirli bir tüm durumlarda Değerlendirme sırasını garanti edemez. Örneğin, hangi değeri parantez ya da aşağıdaki ifade, soldan sağa gruplandırma garanti eder `i` alt ifadeler birini olacaktır:

```
( i++ +1 ) * ( 2 + i )
```

Derleyici, herhangi bir sırada çarpma iki tarafının değerlendirmek ücretsizdir. Başlangıç değeri oluşan `i` sıfır, ifadenin bu iki deyimden birini hesaplanamıyor:

```
( 0 + 1 + 1 ) * ( 2 + 1 )
( 0 + 1 + 1 ) * ( 2 + 0 )
```

Özel durum yan etkilerden kaynaklanan açıklanmıştır [yan etkileri](../c-language/side-effects.md).

## <a name="see-also"></a>Ayrıca bkz.

[C Birincil İfadeler](../c-language/c-primary-expressions.md)
