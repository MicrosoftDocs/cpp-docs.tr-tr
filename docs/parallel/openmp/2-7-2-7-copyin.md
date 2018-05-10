---
title: 2.7.2.7 copyin | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-parallel
ms.topic: conceptual
dev_langs:
- C++
ms.assetid: 76cfb9f8-bf65-4585-adbf-fd933f5606b4
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 7ee711bfb24e7a2a1cbada1a7e01a243e204f4a8
ms.sourcegitcommit: 7019081488f68abdd5b2935a3b36e2a5e8c571f8
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/07/2018
---
# <a name="2727-copyin"></a>2.7.2.7 copyin
**Copyin** yan tümcesi için aynı değer atamak için bir mekanizma sağlar **threadprivate** paralel bölge yürütme Ekipteki her bir iş parçacığı için değişkenleri. Belirtilen her bir değişken için bir **copyin** yan tümcesi, takım ana iş parçacığı değişkeninin değerini kopyalanır, atama gibi paralel bölge başına iş parçacığı özel kopya tarafından. Söz dizimi **copyin** yan tümcesi aşağıdaki gibidir:  
  
```  
  
copyin(  
variable-list  
)  
  
```  
  
 Kısıtlamaları **copyin** yan tümcesi aşağıdaki gibidir:  
  
-   Belirtilen bir değişken **copyin** yan tümcesi erişilebilir, anlaşılır kopya atama işleci olması gerekir.  
  
-   Belirtilen bir değişken **copyin** yan tümcesi olmalıdır bir **threadprivate** değişkeni.