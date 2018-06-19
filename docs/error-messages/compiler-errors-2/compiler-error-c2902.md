---
title: Derleyici Hatası C2902 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C2902
dev_langs:
- C++
helpviewer_keywords:
- C2902
ms.assetid: 89d78d0e-78e5-4c2c-a0f9-a60110e9395e
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 7faa0e3153229c67f38e8f1e265b8195d9567aed
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33245433"
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