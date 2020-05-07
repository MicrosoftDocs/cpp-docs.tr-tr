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
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62233754"
---
# <a name="expressions-in-parentheses"></a>Parantezlerdeki İfadeler

Parantez içinde herhangi bir işleneni, içine alınmış ifadenin türünü veya değerini değiştirmeden ekleyebilirsiniz. Örneğin, ifadesinde:

```
( 10 + 5 ) / 5
```

etrafındaki `10 + 5` parantezler, ilk olarak değerlendirilen ve bölüm `10 + 5` (**/**) işlecinin sol işleneni haline geldiği anlamına gelir. Sonucu 3 ' `( 10 + 5 ) / 5` dir. Parantez olmadan, `10 + 5 / 5` 11 olarak değerlendirilir.

Parantez, işlenenleri bir ifadede gruplandırılma şeklini etkilese de, her durumda belirli bir değerlendirme sırası garantisi vermez. Örneğin, aşağıdaki ifadenin parantezleri veya soldan sağa gruplandırması, değerinin `i` alt ifadelerden birinde ne olacağını garanti eder:

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
