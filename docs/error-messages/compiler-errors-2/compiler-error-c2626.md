---
title: "Derleyici Hatası C2626 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: C2626
dev_langs: C++
helpviewer_keywords: C2626
ms.assetid: 4c283ad0-251b-4571-bc18-468b9836746f
caps.latest.revision: "8"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: 54cee1b985f53e25a0ceb2426231440f1a1bd9bb
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="compiler-error-c2626"></a>Derleyici Hatası C2626
'tanımlayıcısı': bir özel veya korumalı veri üyesi bir anonim yapı ya da UNION izin verilmiyor  
  
 Anonim yapı veya birleşim üyesi genel erişimi olması gerekir.  
  
 Aşağıdaki örnek C2626 oluşturur:  
  
```  
// C2626.cpp  
int main() {  
   union {  
   protected:  
      int j;     // C2626, j is protected  
   private:  
      int k;     // C2626, k is private  
   };  
}  
```  
  
 Bu sorunu gidermek için herhangi bir özel veya korumalı etiket kaldırın:  
  
```  
// C2626b.cpp  
int main() {  
   union {  
   public:  
      int i;   // OK, i is public  
   };  
}  
```