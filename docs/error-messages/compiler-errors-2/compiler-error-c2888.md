---
title: "Derleyici Hatası C2888 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: C2888
dev_langs: C++
helpviewer_keywords: C2888
ms.assetid: 244f593e-ff25-4dad-b31f-84dafa3bc84a
caps.latest.revision: "7"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: 1d2d24f81bb658ab298998507dcb967bcef6644c
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="compiler-error-c2888"></a>Derleyici Hatası C2888
'tanımlayıcısı': 'namespace' ad alanı içinde Sembol tanımlanamıyor  
  
 A. kapsayan bir ad alanında bir ad alanına ait bir simge tanımlanmalıdır  
  
 Aşağıdaki örnek C2888 oluşturur:  
  
```  
// C2888.cpp  
// compile with: /c  
namespace M {  
   namespace N {  
      void f1();  
      void f2();  
   }  
  
   void N::f1() {}   // OK: namspace M encloses N  
}  
  
namespace O {  
   void M::N::f2() {}   // C2888 namespace O does not enclose M  
}  
```