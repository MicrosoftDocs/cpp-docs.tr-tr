---
title: Yan Etkiler
ms.date: 11/04/2016
helpviewer_keywords:
- expression evaluation, side effects
- side effects in expression evaluation
ms.assetid: d9b3004a-830e-43a0-bea5-8989d501d670
ms.openlocfilehash: 97fbb2bc382216e27139a01d1e803a15bd16160b
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50582574"
---
# <a name="side-effects"></a>Yan Etkiler

Dil belirli bir değerlendirme sırasını garanti eder, ifadelerin değerlendirilme sırasını belirli bir uygulama tarafından dışında tanımlanmış (açıklandığı şekilde [öncelik ve sipariş, değerlendirme](../c-language/precedence-and-order-of-evaluation.md)). Örneğin, aşağıdaki işlev çağrılarında yan etkileri gerçekleşir:

```
add( i + 1, i = j + 2 );
myproc( getc(), getc() );
```

Bir işlev çağrısının bağımsız değişkenler herhangi bir sırayla değerlendirilir. İfade `i + 1` önce değerlendirilebilir `i = j + 2`, veya `i = j + 2` önce değerlendirilebilir `i + 1`. Her durumda sonuç farklıdır. Benzer şekilde, hangi karakter gerçekten geçirilen garanti mümkün değildir `myproc`. Tekli artırma ve azaltma beri işlemi atamaları içerir, bu işlemler, aşağıdaki örnekte gösterildiği gibi yan etkileri neden olabilir:

```
x[i] = i++;
```

Bu örnekte, değerini `x` diğer bir deyişle değiştirilmiş tahmin edilemez. Alt simge değerini yeni veya eski değeri olabilir `i`. Sonucu farklı derleyicilerini veya farklı iyileştirme düzeyleri altında değişebilir.

C yan etkileri değerlendirme sırası tanımlamıyor yukarıda açıklanan iki değerlendirme yöntem doğru olduğundan ve ya da uygulanabilir. Kodunuzun taşınabilir ve açık olduğundan emin olmak için değerlendirme yan etkileri için belirli bir sıraya bağlıdır deyimleri kaçının.

## <a name="see-also"></a>Ayrıca Bkz.

[İfade Değerlendirme](../c-language/expression-evaluation-c.md)