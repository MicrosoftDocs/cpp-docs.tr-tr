---
title: 2.7.2.8 copyprivate | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-parallel
ms.topic: conceptual
dev_langs:
- C++
ms.assetid: c382348c-c785-45b2-8ee6-a66b76b97f3e
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: c809f297da5059a98915e8055dfe23f45074366f
ms.sourcegitcommit: 7019081488f68abdd5b2935a3b36e2a5e8c571f8
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/07/2018
ms.locfileid: "33691609"
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