---
title: "Derleyici Hatası C2512 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: C2512
dev_langs: C++
helpviewer_keywords: C2512
ms.assetid: 15206da9-1164-451a-b869-280e00711aad
caps.latest.revision: "9"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 191d56a0f54dacb42d84b1a5f3e121f437746134
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="compiler-error-c2512"></a>Derleyici Hatası C2512
'tanımlayıcısı': kullanılabilir uygun varsayılan oluşturucu yok  
  
 Varsayılan oluşturucu yok, belirtilen sınıf, yapı veya birlik için kullanılabilir. Yalnızca kullanıcı tanımlı oluşturucular sağlanmayan durumunda varsayılan bir oluşturucu derleyici sağlar.  
  
 Bir geçersiz kılma olmayan parametresi alan bir oluşturucu sağlayın ve parametresiz oluşturulacak sınıfınız izin vermek istediğiniz — örneğin, bir dizinin öğeleri olarak — varsayılan bir oluşturucu sağlamanız gerekir. Varsayılan Oluşturucu tüm parametrelerin değerlerini varsayılan bir oluşturucu olabilir.  
  
 Aşağıdaki örnek C2512 oluşturur ve düzeltmek gösterilmektedir:  
  
```  
// C2512.cpp  
// C2512 expected  
struct B {  
   B (char *);  
   // Uncomment the following line to fix.  
   // B() {};  
};  
  
int main() {  
   B b;   
}  
```  
  
 Aşağıdaki örnek, daha hafif C2512 gösterir. Bu hatayı düzeltmek için önce kendi Oluşturucusu sınıfını tanımlamak için kodu yeniden başvurulur:  
  
```  
// C2512b.cpp  
// compile with: /c  
struct S {  
   struct X;  
  
   void f() {  
      X *x = new X();   // C2512 X not defined yet  
   }  
  
};  
  
struct S::X {};  
  
struct T {  
   struct X;  
   void f();  
};  
  
struct T::X {};  
  
void T::f() {  
   X *x = new X();  
}  
```  
  
 C2512 varsayılan yapı bir const veya başvuru veri üyesi içeren bir sınıf için bir çağrı tarafından neden olabilir. Bu üyeler derleyici varsayılan bir oluşturucu oluşturmasını engelleyen bir oluşturucu başlatıcı listesi başlatılması gerekir.  
  
 Aşağıdaki örnek C2512 oluşturur ve düzeltmek gösterilmektedir:  
  
```  
// C2512c.cpp  
// Compile by using: cl /c /W3 C2512c.cpp  
struct S {  
   const int i_;  
   int &r_;   
};   
  
int SumS() {  
   const int ci = 7;  
   int ir = 42;  
  
   S s1; // C2512 - no default constructor available  
   S s2{ci, ir};  // Fix - initialize const and reference members   
   return s2.i_ + s2.r_;  
}  
```