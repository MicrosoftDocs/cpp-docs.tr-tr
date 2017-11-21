---
title: "Derleyici Hatası C2902 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: C2902
dev_langs: C++
helpviewer_keywords: C2902
ms.assetid: 89d78d0e-78e5-4c2c-a0f9-a60110e9395e
caps.latest.revision: "9"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: 2daad775980c881bb1400c695015bd094ffc14cf
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="compiler-error-c2902"></a>Derleyici Hatası C2902
'belirteci': beklenmeyen belirteç aşağıdaki 'şablon', tanımlayıcı bekleniyor  
  
 Anahtar sözcüğünü izleyen belirteç `template` bir tanımlayıcı değil.  
  
 Aşağıdaki örnek C2902 oluşturur:  
  
```  
// C2902.cpp  
// compile with: /c  
namespace N {  
   template<class T> class X {};  
   class Y {};  
}  
void g() {  
   N::template + 1;   // C2902  
}  
  
void f() {  
   N::template X<int> x1;   // OK  
}  
```  
  
 Ayrıca C2902 genel türler kullanma ortaya çıkabilir:  
  
```  
// C2902b.cpp  
// compile with: /clr /c  
namespace N {  
   generic<class T> ref class GC {};  
}  
  
void f() {  
   N::generic + 1;   // C2902  
   N::generic GC<int>^ x;  
}  
```