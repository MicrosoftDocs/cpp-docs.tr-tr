---
title: "2.6.4 atomic yapı | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
ms.assetid: e4232ef1-4058-42ce-9de0-0ca788312aba
caps.latest.revision: "6"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: ea1cc2474a8420227dcf2b6b6e87f255ce144cf4
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
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
  
-   `binop`Aşırı yüklenmiş bir işleç değil ve biri +, *, -, / &, ^, &#124; <\<, veya >>.  
  
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