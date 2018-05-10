---
title: 2.6.4 atomic yapı | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-parallel
ms.topic: conceptual
dev_langs:
- C++
ms.assetid: e4232ef1-4058-42ce-9de0-0ca788312aba
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 66f0dc8469d1d70b2697df1fe120f10142d90dbe
ms.sourcegitcommit: 7019081488f68abdd5b2935a3b36e2a5e8c571f8
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/07/2018
---
# <a name="264-atomic-construct"></a>2.6.4 atomic Yapı
`atomic` Yönergesi sağlar belirli bellek konumuna birden çok olanağı gösterme yerine otomatik olarak, bir biçimde güncelleştirilir eş zamanlı iş parçacıkları yazma. Söz dizimi `atomic` yönergesi aşağıdaki gibidir:  
  
```  
#pragma omp atomic new-lineexpression-stmt  
```  
  
 İfade deyimi aşağıdaki biçimlerden birine sahip olmalıdır:  
  
 *x binop*= *ifade*  
  
 x ++  
  
 ++ x  
  
 x--  
  
 --x  
  
 Önceki ifadelerinde:  
  
-   *x* skaler türüyle lvalue ifadesidir.  
  
-   *Expr* ifade skaler türüne sahip olan ve belirlenen nesneye başvurmuyor *x*.  
  
-   `binop` Aşırı yüklenmiş bir işleç değil ve biri +, *, -, / &, ^, &#124;, <\<, veya >>.  
  
 Bu uygulama tüm olup yerini alır uygulama tanımlı olmasına rağmen `atomic` yönergeleri ile **kritik** aynı benzersiz olan yönergeleri *adı*, `atomic` yönergesi izinleri daha iyi en iyi duruma getirme. Genellikle donanım yönergeleri kullanılabilir olan en az bir ek yükü atomik güncelleştirme gerçekleştirebilir.  
  
 Yalnızca Yük ve belirlenen nesnesinin deposu *x* olan atomik; değerlendirmesi *expr* atomik değil. Yarış durumları önlemek için tüm güncelleştirmeleri paralel konumunun ile korunması gerektiğini `atomic` yarış durumları boş olduğu bilinen dışındaki yönergesi.  
  
 Kısıtlamaları `atomic` yönergesi aşağıdaki gibidir:  
  
-   Tüm atomik başvuruları program boyunca depolama konumuna x uyumlu bir türde olması gerekir.  
  
## <a name="examples"></a>Örnekler:  
  
```  
extern float a[], *p = a, b;  
/* Protect against races among multiple updates. */  
#pragma omp atomic  
a[index[i]] += b;  
/* Protect against races with updates through a. */  
#pragma omp atomic  
p[i] -= 1.0f;  
  
extern union {int n; float x;} u;  
/* ERROR - References through incompatible types. */  
#pragma omp atomic  
u.n++;  
#pragma omp atomic  
u.x -= 1.0f;  
```