---
title: "Derleyici Hatası C2662 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: C2662
dev_langs: C++
helpviewer_keywords: C2662
ms.assetid: e172c2a4-f29e-4034-8232-e7dc6f83689f
caps.latest.revision: "11"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: e914431ff7303b6689dc7ee1da57e2a11b309a37
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="compiler-error-c2662"></a>Derleyici Hatası C2662
'function': 'this' işaretçisine 'type1' öğesinden 'type2' dönüştürülemiyor  
  
 Derleyici değil dönüştüremedi `this` işaretçi `type1` için `type2`.  
  
 Bu hata, olmayan bir harekete geçirerek kaynaklanabilir`const` üye işlevi bir `const` nesnesi.  Olası çözümler:  
  
-   Kaldırma `const` nesne bildirimi gelen.  
  
-   Ekleme `const` üye işlevi.  
  
 Aşağıdaki örnek C2662 oluşturur:  
  
```  
// C2662.cpp  
class C {  
public:  
   void func1();  
   void func2() const{}  
} const c;  
  
int main() {  
   c.func1();   // C2662  
   c.func2();   // OK  
}  
```  
  
 İle derleme yapılırken **/CLR**, bir işlev çağrılamıyor bir `const` veya `volatile` tam yönetilen türü. Const yönetilen nesneler üzerinde yöntemleri çağrılamaz şekilde bir yönetilen sınıf const üye işlevi bildiremezsiniz.  
  
```  
// C2662_b.cpp  
// compile with: /c /clr  
ref struct M {  
   property M^ Type {  
      M^ get() { return this; }  
   }  
  
   void operator=(const M %m) {  
      M ^ prop = m.Type;   // C2662  
   }  
};  
  
ref struct N {  
   property N^ Type {  
      N^ get() { return this; }  
   }  
  
   void operator=(N % n) {  
      N ^ prop = n.Type;   // OK  
   }  
};  
```  
  
 Aşağıdaki örnek C2662 oluşturur:  
  
```  
// C2662_c.cpp  
// compile with: /c  
// C2662 expected  
typedef int ISXVD;  
typedef unsigned char BYTE;  
  
class LXBASE {  
protected:  
    BYTE *m_rgb;  
};  
  
class LXISXVD:LXBASE {  
public:  
   // Delete the following line to resolve.  
   ISXVD *PMin() { return (ISXVD *)m_rgb; }  
  
   ISXVD *PMin2() const { return (ISXVD *)m_rgb; };   // OK  
};  
  
void F(const LXISXVD *plxisxvd, int iDim) {  
   ISXVD isxvd;  
   // Delete the following line to resolve.  
   isxvd = plxisxvd->PMin()[iDim];  
  
   isxvd = plxisxvd->PMin2()[iDim];    
}  
```