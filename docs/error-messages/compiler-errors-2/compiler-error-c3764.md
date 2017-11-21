---
title: "Derleyici Hatası C3764 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: C3764
dev_langs: C++
helpviewer_keywords: C3764
ms.assetid: af5d254c-8d4a-4dda-aad9-3c5c1257c868
caps.latest.revision: "6"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: 60317bb31b5021d4b9b1b6568d77ae92e06880ce
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="compiler-error-c3764"></a>Derleyici Hatası C3764
'override_function': 'base_class_function' temel sınıf yöntemi geçersiz kılamaz  
  
 Derleyici hatalı oluşturulmuş bir geçersiz kılma algıladı. Örneğin, temel sınıf işlevi değildi `virtual`. Daha fazla bilgi için bkz: [geçersiz kılma](../../windows/override-cpp-component-extensions.md).  
  
## <a name="example"></a>Örnek  
 Aşağıdaki örnek C3764 oluşturur.  
  
```  
// C3764.cpp  
// compile with: /clr /c  
public ref struct A {  
   void g(int);  
   virtual void h(int);  
};  
  
public ref struct B : A {  
   virtual void g(int) override {}   // C3764  
   virtual void h(int) override {}   // OK  
};  
```  
  
## <a name="example"></a>Örnek  
 C3764 bir temel sınıf yöntemi her ikisi de açıkça olmadığında da ortaya çıkabilir ve adlı geçersiz kılındı. Aşağıdaki örnek C3764 oluşturur.  
  
```  
// C3764_b.cpp  
// compile with: /clr /c  
ref struct A {  
   virtual void Test() {}  
};  
  
ref struct B : public A {  
   virtual void Test() override {}  
   virtual void Test2() = A::Test {}   // C3764  
};  
```