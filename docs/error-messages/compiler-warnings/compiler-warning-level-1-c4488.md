---
title: "Derleyici Uyarısı (düzey 1) C4488 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: C4488
dev_langs: C++
helpviewer_keywords: C4488
ms.assetid: 55625e46-ddb5-4c7c-99c7-cd4aa9f879bd
caps.latest.revision: "5"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: 1312d279eb9174e0863cae413a0014cc58710131
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="compiler-warning-level-1-c4488"></a>Derleyici Uyarısı (düzey 1) C4488
'function': 'interface_method' arabirim yöntemi uygulamak için 'anahtar sözcüğü' anahtar sözcüğü gerektirir  
  
 Bir sınıfın tüm üyelerini doğrudan devraldığı arabirimi uygulamalıdır. Uygulanan bir üye ortak erişilebilirlik olmalıdır ve sanal olarak işaretlenmelidir.  
  
## <a name="example"></a>Örnek  
 C4488 uygulanan bir üye ortak değil ortaya çıkabilir. Aşağıdaki örnek C4488 oluşturur.  
  
```  
// C4488.cpp  
// compile with: /clr /c /W1 /WX  
interface struct MyI {  
   void f1();  
};  
  
// implemented member not public  
ref class B : MyI { virtual void f1() {} };  // C4488  
  
// OK  
ref class C : MyI {  
public:  
   virtual void f1() {}  
};  
```  
  
## <a name="example"></a>Örnek  
 C4488 uygulanan bir üye sanal işaretlenmemiş ortaya çıkabilir. Aşağıdaki örnek C4488 oluşturur.  
  
```  
// C4488_b.cpp  
// compile with: /clr /c /W1 /WX  
interface struct MyI {  
   void f1();  
};  
  
ref struct B : MyI { void f1() {} };   // C4488  
ref struct C : MyI { virtual void f1() {} };   // OK  
```