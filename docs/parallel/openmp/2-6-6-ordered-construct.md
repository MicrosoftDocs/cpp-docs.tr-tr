---
title: "2.6.6 ordered yapı | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
ms.assetid: 5b3c1ba5-cfb8-4b05-865b-f446ae1c9f7c
caps.latest.revision: "7"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: 690db7cbc03e9aa9a3b4780dd2b115812c31f984
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="266-ordered-construct"></a>2.6.6 ordered Yapı
Yapılandırılmış blok aşağıdaki bir **sıralı** yönergesi içinde yineleme yürütülebilir sıralı bir döngüde sırayla gerçekleştirilir. Söz dizimi **sıralı** yönergesi aşağıdaki gibidir:  
  
```  
#pragma omp ordered new-linestructured-block  
```  
  
 Bir **sıralı** yönergesi içinde dinamik kapsamı olmalıdır bir **için** veya **için paralel** oluşturun. **İçin** veya **için paralel** hangi yönerge **sıralı** yapı bağlamalar olmalıdır bir **sıralı** açıklandığı gibi belirtilen yan tümcesi [Bölüm 2.4.1](../../parallel/openmp/2-4-1-for-construct.md) sayfasında 11. Yürütülmesi bir **için** veya **için paralel** ile oluşturmak bir **sıralı** yan tümcesi **sıralı** yapıları kesinlikle içinde çalıştırılır sıra, bunlar sıralı bir yürütme döngüsü yürütülmesi.  
  
 Kısıtlamaları **sıralı** yönergesi aşağıdaki gibidir:  
  
-   Yineleme döngüsü ile bir **için** yapı gerekir değil çalıştırma aynı sıralı yönergesi birden çok kez ve onu birden fazla yürütülmelidir değil **sıralı** yönergesi.