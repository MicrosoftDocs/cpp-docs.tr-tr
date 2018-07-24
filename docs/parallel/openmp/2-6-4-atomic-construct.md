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
ms.openlocfilehash: 3c906a9a9b781f742f525688b77d5f58da16bb10
ms.sourcegitcommit: 7eadb968405bcb92ffa505e3ad8ac73483e59685
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/23/2018
ms.locfileid: "39208139"
---
# <a name="264-atomic-construct"></a>2.6.4 atomic Yapı
`atomic` Yönergesi sağlar belirli bellek konumu birden fazla olasılığını gösterme yerine atomik olarak, bir biçimde güncelleştirilir eşzamanlı iş parçacığı yazma. Söz dizimi `atomic` yönerge aşağıdaki gibidir:  
  
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
  
-   *x* skalar türü ile bir lvalue ifadesidir.  
  
-   *Expr* skaler türüne sahip ifade ve tarafından belirlenen nesnede başvurmuyor *x*.  
  
-   `binop` Aşırı yüklenmiş bir işleç değil ve biri +, \*, -, / &, ^, &#124;, <\<, veya >>.  
  
 Bu uygulama tüm olup yerini alır uygulama tanımlı olmasına rağmen `atomic` yönergeleri ile **kritik** aynı benzersiz yönergeleri *adı*, `atomic` yönergesi izinleri daha iyi iyileştirme. Genellikle donanım yönergeleri atomik güncelleştirme en az bir ek yükü ile gerçekleştirebilirsiniz.  
  
 Yalnızca Yük ve tarafından belirlenen nesnede deposu *x* olan atomik; değerlendirmesi *expr* atomik olması gerekmez. Yarış durumları önlemek için tüm güncelleştirmeleri paralel konumunun ile korunması gerektiğini `atomic` yarış koşulları ücretsiz olduğu bilinen dışındaki yönergesi.  
  
 Kısıtlamaları `atomic` yönerge aşağıdaki gibidir:  
  
-   Tüm atomik başvuruları program boyunca depolama konumuna x uyumlu bir tür olması gerekir.  
  
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