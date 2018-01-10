---
title: 2.7.2.7 copyin | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
ms.assetid: 76cfb9f8-bf65-4585-adbf-fd933f5606b4
caps.latest.revision: "5"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 5ba09b70b3a3591b1f8b427ac107576cfcac7935
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
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