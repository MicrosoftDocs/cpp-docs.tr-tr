---
title: 2.6.6 ordered yapı | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-parallel
ms.topic: conceptual
dev_langs:
- C++
ms.assetid: 5b3c1ba5-cfb8-4b05-865b-f446ae1c9f7c
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: fa66d9fb8a0a9af2fc33497690bfe67a3ea5d717
ms.sourcegitcommit: 7019081488f68abdd5b2935a3b36e2a5e8c571f8
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/07/2018
---
# <a name="266-ordered-construct"></a>2.6.6 ordered Yapı
Yapılandırılmış blok aşağıdaki bir **sıralı** yönergesi içinde yineleme yürütülebilir sıralı bir döngüde sırayla gerçekleştirilir. Söz dizimi **sıralı** yönergesi aşağıdaki gibidir:  
  
```  
#pragma omp ordered new-linestructured-block  
```  
  
 Bir **sıralı** yönergesi içinde dinamik kapsamı olmalıdır bir **için** veya **için paralel** oluşturun. **İçin** veya **için paralel** hangi yönerge **sıralı** yapı bağlamalar olmalıdır bir **sıralı** açıklandığı gibi belirtilen yan tümcesi [Bölüm 2.4.1](../../parallel/openmp/2-4-1-for-construct.md) sayfasında 11. Yürütülmesi bir **için** veya **için paralel** ile oluşturmak bir **sıralı** yan tümcesi **sıralı** yapıları kesinlikle içinde çalıştırılır sıra, bunlar sıralı bir yürütme döngüsü yürütülmesi.  
  
 Kısıtlamaları **sıralı** yönergesi aşağıdaki gibidir:  
  
-   Yineleme döngüsü ile bir **için** yapı gerekir değil çalıştırma aynı sıralı yönergesi birden çok kez ve onu birden fazla yürütülmelidir değil **sıralı** yönergesi.