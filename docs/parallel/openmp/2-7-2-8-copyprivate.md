---
title: 2.7.2.8 copyprivate | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- C++
ms.assetid: c382348c-c785-45b2-8ee6-a66b76b97f3e
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 21d739fb3ead0512776cfd996b59f1ceab5e8250
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="2728-copyprivate"></a>2.7.2.8 copyprivate
**Copyprivate** yan tümcesi bir değer diğer üyeleri için bir ekibin üyesi yayınlamak için özel bir değişken kullanmak için bir mekanizma sağlar. Paylaşılan bir değişken sağlayan (örneğin, her düzeyde farklı değişken gerektiren özyineleme) zor olacaktır, paylaşılan bir değişken değeri bir alternatifidir. **Copyprivate** yan tümcesi üzerinde yalnızca görünebilir **tek** yönergesi.  
  
 Söz dizimi **copyprivate** yan tümcesi aşağıdaki gibidir:  
  
```  
  
copyprivate(  
variable-list  
)  
  
```  
  
 Etkisini **copyprivate** yan tümcesi, değişken listesinde değişkenleri oluşur ilişkili yapılandırılmış blok yürütülmesi sonra **tek** oluşturmak ve önce herhangi bir iş parçacıkları takım yapısı sonunda engel sol. Ardından, her bir değişken için takım diğer iş parçacıklarında *değişken listesi*, bu değişken (ataması gibi) ilgili değerle tanımlanan olur yapı yürütülen iş parçacığı değişkeninde yapılandırılmış Blok.  
  
 Kısıtlamaları **copyprivate** yan tümcesi aşağıdaki gibidir:  
  
-   Belirtilen bir değişken **copyprivate** yan tümcesi gerekir görünmüyor içinde bir **özel** veya **firstprivate** yan tümcesi için aynı **tek**yönergesi.  
  
-   Varsa bir **tek** ile yönerge bir **copyprivate** yan tümcesi paralel bir bölge içindeki dinamik kapsamı ile karşılaşıldı, tüm değişkenler belirtilen **copyprivate** yan tümcesi olmalıdır Özel kapsayan bağlamında.  
  
-   Belirtilen bir değişken **copyprivate** yan tümcesi erişilebilir anlaşılır kopya atama işleci olması gerekir.