---
title: Parantezlerdeki ifadeler | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-language
ms.topic: language-reference
dev_langs:
- C++
helpviewer_keywords:
- parentheses
- expression evaluation, evaluation order
- expressions [C++], evaluating
- parentheses, expressions
ms.assetid: b8636147-6982-408c-9e64-29e40678ee43
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 5a052dbc666be05d05753c7408b1d09643f09dc8
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/18/2018
ms.locfileid: "46022883"
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

## <a name="see-also"></a>Ayrıca Bkz.

[C Birincil İfadeler](../c-language/c-primary-expressions.md)