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
ms.openlocfilehash: cd296192146e76085e1b987e29a377eb621917ae
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
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