---
title: "Derleyici Hatası C3052 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: C3052
dev_langs: C++
helpviewer_keywords: C3052
ms.assetid: 87480c42-1ceb-4775-8d20-88c54a7bb6a6
caps.latest.revision: "7"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: 59686a585f66092fbf059cc5e84f7da493134b7f
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="compiler-error-c3052"></a>Derleyici Hatası C3052
'var': değişken veri paylaşımı yan default(none) yan tümcesi altında görünmüyor  
  
 Varsa [default(none)](../../parallel/openmp/reference/default-openmp.md) olan kullanıldığında, yapılandırılmış bloğunda kullanılan herhangi bir değişken açıkça ya da belirtilmelidir [paylaşılan](../../parallel/openmp/reference/shared-openmp.md) veya [özel](../../parallel/openmp/reference/private-openmp.md).  
  
 Aşağıdaki örnek C3052 oluşturur:  
  
```  
// C3052.cpp  
// compile with: /openmp /c  
int main() {  
   int n1 = 1;  
  
   #pragma omp parallel default(none) // shared(n1) private(n1)  
   {  
      n1 = 0;   // C3052 use either a shared or private clause  
   }  
}  
```