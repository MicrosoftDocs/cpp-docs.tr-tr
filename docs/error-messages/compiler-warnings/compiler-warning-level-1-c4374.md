---
title: "Derleyici Uyarısı (düzey 1) C4374 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: C4374
dev_langs: C++
helpviewer_keywords: C4374
ms.assetid: 4ac9aaec-d815-4b6e-825f-fa872092dd3b
caps.latest.revision: "11"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: 4034825ceea8584529c614bf58483c1af5b8760b
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="compiler-warning-level-1-c4374"></a>Derleyici Uyarısı (düzey 1) C4374
'function1': arabirim yöntemi uygulanmadı sanal olmayan bir yöntemle 'function2'  
  
 Derleyici bekleniyordu [sanal](../../cpp/virtual-specifier.md) anahtar sözcüğü bir yöntemin tanımı üzerinde.  
  
 Aşağıdaki örnek C4374 oluşturur:  
  
```  
// C4374.cpp  
// compile with: /clr /W1 /c /WX  
public interface class I {  
   void f();  
};  
  
public ref struct B {  
   void f() {  
      System::Console::WriteLine("B::f()");  
   }  
};  
  
public ref struct C {  
   virtual void f() {  
      System::Console::WriteLine("C::f()");  
   }  
};  
  
public ref struct D : B, I {};   // C4374  
public ref struct E : C, I {};   // OK  
```