---
title: Yan etkiler | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-language
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- C++
helpviewer_keywords:
- expression evaluation, side effects
- side effects in expression evaluation
ms.assetid: d9b3004a-830e-43a0-bea5-8989d501d670
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 4e6e6dff87e447a3885906130b6a08286643d6a5
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="side-effects"></a>Yan Etkiler
Belirli bir sıraya değerlendirme dil garanti sırasında bir ifade Değerlendirme sırasını belirli uygulama tarafından dışında tanımlanır (kısmında özetlendiği gibi [öncelik ve değerlendirme, sipariş](../c-language/precedence-and-order-of-evaluation.md)). Örneğin, aşağıdaki işlev çağrıları yan etkileri oluşur:  
  
```  
add( i + 1, i = j + 2 );  
myproc( getc(), getc() );  
```  
  
 Bir işlev çağrısı bağımsız değişkenleri herhangi bir sırada değerlendirilebilir. İfade `i + 1` önce değerlendirilmesi `i = j + 2`, veya `i = j + 2` önce değerlendirilmesi `i + 1`. Sonucu, her durumda farklıdır. Benzer şekilde, hangi karakterleri gerçekte geçirilecek garanti mümkün değildir `myproc`. Birli artırma ve azaltma itibaren işlemleri atamaları içerir, bu işlemler, aşağıdaki örnekte gösterildiği gibi yan etkileri neden olabilir:  
  
```  
x[i] = i++;  
```  
  
 Bu örnekte, değeri `x` diğer bir deyişle öngörülemeyen olduğu değiştirdi. Alt simge değerini yeni veya eski değeri olabilir `i`. Sonuç altında farklı derleyicileri ya da farklı iyileştirme düzeylerinin farklılık gösterebilir.  
  
 C yan etkileri Değerlendirme sırasını tanımlamıyor olduğundan, yukarıda açıklanan değerlendirme yöntemlerin her ikisi de doğru olduğundan ve ya da uygulanabilir. Kodunuzu taşınabilir ve açık olduğundan emin olmak için değerlendirme yan etkileri için belirli bir sıraya bağlıdır deyimleri kaçının.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [İfade değerlendirme](../c-language/expression-evaluation-c.md)