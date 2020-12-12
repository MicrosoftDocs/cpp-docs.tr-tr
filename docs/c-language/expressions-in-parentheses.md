---
description: 'Daha fazla bilgi edinin: parantez içindeki Ifadeler'
title: Parantezlerdeki İfadeler
ms.date: 11/04/2016
helpviewer_keywords:
- parentheses
- expression evaluation, evaluation order
- expressions [C++], evaluating
- parentheses, expressions
ms.assetid: b8636147-6982-408c-9e64-29e40678ee43
ms.openlocfilehash: fd33cab851f7ec55c395fee62e4300d42365f00f
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97196379"
---
# <a name="expressions-in-parentheses"></a>Parantezlerdeki İfadeler

Parantez içinde herhangi bir işleneni, içine alınmış ifadenin türünü veya değerini değiştirmeden ekleyebilirsiniz. Örneğin, ifadesinde:

```
( 10 + 5 ) / 5
```

etrafındaki parantezler, `10 + 5` `10 + 5` ilk olarak değerlendirilen ve bölüm () işlecinin sol işleneni haline geldiği anlamına gelir **/** . Sonucu 3 ' `( 10 + 5 ) / 5` dir. Parantez olmadan, `10 + 5 / 5` 11 olarak değerlendirilir.

Parantez, işlenenleri bir ifadede gruplandırılma şeklini etkilese de, her durumda belirli bir değerlendirme sırası garantisi vermez. Örneğin, aşağıdaki ifadenin parantezleri veya soldan sağa gruplandırması, değerinin alt ifadelerden birinde ne olacağını garanti eder `i` :

```
( i++ +1 ) * ( 2 + i )
```

Derleyici, her türlü sırada çarpma 'nın iki tarafını değerlendirmek için ücretsizdir. İlk değeri `i` sıfırsa, tüm ifade bu iki deyimden biri olarak değerlendirilebiliyor:

```
( 0 + 1 + 1 ) * ( 2 + 1 )
( 0 + 1 + 1 ) * ( 2 + 0 )
```

Yan etkilerden kaynaklanan özel durumlar [yan etkilere](../c-language/side-effects.md)göre ele alınmıştır.

## <a name="see-also"></a>Ayrıca bkz.

[C birincil Ifadeler](../c-language/c-primary-expressions.md)
