---
title: Yan Etkiler
ms.date: 11/04/2016
helpviewer_keywords:
- expression evaluation, side effects
- side effects in expression evaluation
ms.assetid: d9b3004a-830e-43a0-bea5-8989d501d670
ms.openlocfilehash: de5e398afd8b95cfe5596f487a36b6a2d27e3287
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62158479"
---
# <a name="side-effects"></a>Yan Etkiler

İfadelerin değerlendirmesi sırası belirli bir uygulama tarafından tanımlanır. Bu, dilin belirli bir değerlendirme sırasını garanti eder ( [Öncelik ve değerlendirme sırasıyla](../c-language/precedence-and-order-of-evaluation.md)özetlenmiştir). Örneğin, aşağıdaki işlev çağrılarında yan etkileri oluşur:

```
add( i + 1, i = j + 2 );
myproc( getc(), getc() );
```

Bir işlev çağrısının bağımsız değişkenleri herhangi bir sırada değerlendirilebilirler. İfade `i + 1` daha önce `i = j + 2`değerlendirilemeyebilir veya `i = j + 2` daha önce `i + 1`değerlendirilebilir. Sonuç her durumda farklı olur. Benzer şekilde, hangi karakterlerin öğesine gerçekten geçtiğini garanti etmek mümkün değildir `myproc`. Birli artış ve azaltma işlemleri atamalar içerdiğinden, bu gibi işlemler yan etkilere neden olabilir ve aşağıdaki örnekte gösterildiği gibi:

```
x[i] = i++;
```

Bu örnekte, değiştirilen değeri `x` tahmin edilemez. Alt simge değeri, yeni ya da eski değeri olabilir `i`. Sonuç, farklı derleyiciler veya farklı iyileştirme seviyeleri kapsamında değişebilir.

C, yan etkileri değerlendirme sırasını tanımlamadığından, yukarıda bahsedilen değerlendirme yöntemlerinin her ikisi de doğru ve uygulanabilir. Kodunuzun taşınabilir ve açık olduğundan emin olmak için, yan etkilere yönelik belirli bir değerlendirme sırasına bağlı olan deyimlerden kaçının.

## <a name="see-also"></a>Ayrıca bkz.

[İfade Değerlendirme](../c-language/expression-evaluation-c.md)
